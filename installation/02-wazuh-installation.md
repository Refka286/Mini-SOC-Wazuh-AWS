# 02 — Installation de Wazuh

## Objectif
Installer et configurer le serveur Wazuh sur l’instance AWS EC2 préparée dans la première étape.

## Pré-requis
- EC2 Amazon Linux 2023 opérationnel
- Accès SSH à l'instance
- Ports nécessaires ouverts dans le groupe de sécurité : 22 (SSH), 443 (HTTPS)
- Au moins 50 GiB de stockage et 8 Go de RAM pour un mini SOC de test

## 1. Mettre à jour le système

```bash
sudo yum update -y
sudo yum install -y curl unzip
```

## 2. Télécharger et exécuter le script Wazuh

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
sudo bash ./wazuh-install.sh -a
```

### Explication
- Le script officiel installe le serveur Wazuh, l’indexeur et le dashboard.
- L’option `-a` lance une installation automatique avec les composants par défaut.

## 3. Vérifier l’installation

```bash
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-api
sudo systemctl status wazuh-dashboard
```

## 4. Configurer le firewall local (si applicable)

Si `firewalld` est utilisé :

```bash
sudo firewall-cmd --permanent --add-port=443/tcp
sudo firewall-cmd --reload
```

## 5. Commandes utiles

| Commande | Description |
|---------|-------------|
| `sudo systemctl status wazuh-manager` | Vérifie le service Wazuh Manager |
| `sudo journalctl -u wazuh-manager -f` | Affiche les logs en continu |
| `sudo /var/ossec/bin/ossec-control status` | Vérifie l’état des modules Wazuh |

## 6. Prochaines vérifications
- Vérifier que le service Wazuh Dashboard est actif
- Vérifier l’accès HTTPS depuis un navigateur
- Préparer les captures d’écran de l’installation
