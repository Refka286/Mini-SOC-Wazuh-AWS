# 03 — Accès au Dashboard Wazuh

## Objectif
Vérifier que le dashboard Wazuh est accessible et préparer la configuration initiale des alertes.

## 1. Ouvrir le navigateur
Accédez à :

```text
https://<EC2_PUBLIC_IP>
```

Si l’adresse IP est filtrée par le groupe de sécurité, utilisez votre adresse IP autorisée.

## 2. Connexion au dashboard
- Login : `admin`
- Mot de passe : le mot de passe initial généré pendant l'installation

> Si vous ne connaissez pas le mot de passe, utilisez le fichier de configuration `wazuh-dashboard` ou le log d'installation pour le retrouver.

## 3. Vérifier les composants
Dans le dashboard, vérifiez que :
- Wazuh Manager est connecté
- L’indexer reçoit des données
- Le dashboard est opérationnel

## 4. Test de collecte de logs
1. Générer un événement de test sur l’instance :

```bash
sudo logger "Test Wazuh alert - Vérification du service"
```

2. Attendre quelques minutes
3. Rechercher l’événement dans le dashboard

## 5. Étapes suivantes
- Configurer une règle de détection personnalisée si nécessaire
- Activer les alertes par e-mail ou webhook pour la surveillance
- Documenter les résultats et les captures d’écran
