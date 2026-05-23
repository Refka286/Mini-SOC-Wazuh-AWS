# Rapport — Partie 1 : AWS EC2 Setup

## Résumé
La première phase du projet est terminée : l’instance EC2 a été créée et préparée pour l’installation de Wazuh.

## Travaux réalisés
- Création de l’instance Amazon Linux 2023
- Configuration du groupe de sécurité avec accès SSH et HTTPS restreint
- Préparation du stockage 50 GiB
- Génération et utilisation d’une clé SSH au format `.ppk`
- Vérification des ressources système avec `free -h`, `df -h`, `uname -m`, et `nproc`

## Résultats
- L’instance est opérationnelle
- Les règles de sécurité sont en place
- L’environnement est prêt pour l’installation de Wazuh

## Observations
- La configuration est adaptée à un mini SOC de test
- Il est important de garder le serveur accessible uniquement depuis une adresse IP de confiance
- Les informations sensibles restent hors du dépôt
