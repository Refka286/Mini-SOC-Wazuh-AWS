# Plan d'optimisation du projet Mini SOC Wazuh AWS

## 1. Contexte du projet
Ce projet vise à déployer un mini SOC avec Wazuh sur une instance AWS EC2. Il documente la création de l'infrastructure, la préparation du serveur, l'installation de Wazuh et la génération d'alertes de sécurité.

## 2. Objectifs principaux
- Construire un laboratoire sécurisé pour la surveillance de la sécurité.
- Installer et configurer Wazuh Server, Indexer et Dashboard.
- Collecter et analyser des logs de sécurité.
- Rédiger une documentation claire et réutilisable.

## 3. Analyse des points à optimiser
1. Documentation incomplète
   - Le README décrit le projet, mais manque de plan d'action précis et de sections claires sur l'état d'avancement.
   - Le rapport `report/part1-aws-ec2-setup.md` est vide.
2. Progression et suivi
   - Le projet doit bénéficier d'une roadmap claire avec des étapes numérotées.
3. Structure du dépôt
   - La structure est simple, mais peut gagner en lisibilité avec des documents de planification et des rapports bien séparés.
4. Sécurité et bonnes pratiques
   - Le `.gitignore` est déjà bon pour les clés et secrets, mais il faut rester vigilant sur les captures d'écran contenant des IP ou des identifiants.

## 4. Plan d'optimisation recommandé
### Phase 1 — Stabiliser la documentation
- Mettre à jour `README.md` pour inclure :
  - une description du projet
  - les objectifs
  - la structure du dépôt
  - l'état d'avancement
  - les prochaines étapes

- Compléter `report/part1-aws-ec2-setup.md` avec un rapport synthétique de la première étape.

### Phase 2 — Compléter le parcours technique
- Ajouter un document `installation/02-wazuh-installation.md` pour décrire l'installation du serveur Wazuh.
- Ajouter un document `installation/03-wazuh-dashboard.md` pour l'accès au dashboard et l'analyse des alertes.
- Ajouter un document `report/part2-wazuh-installation.md` pour la rédaction des résultats de l'installation.

### Phase 3 — Qualifier et sécuriser
- Décrire les règles de sécurité (Security Group, SSH, HTTPS) et les bonnes pratiques.
- Ajouter une section « conseils de mise en production » : sauvegarde, surveillance, mises à jour.

## 5. Roadmap prioritaire
1. Compléter la documentation existante et la structure du dépôt.
2. Rédiger les étapes manquantes d'installation et de configuration Wazuh.
3. Documenter les tests de détection et la génération d'alertes.
4. Ajouter des captures d'écran structurées dans `screenshots/`.
5. Vérifier le dépôt Git et pousser les changements sur GitHub.

## 6. Recommandations supplémentaires
- Utiliser des noms de fichiers cohérents et explicites.
- Garder les informations sensibles hors du dépôt.
- Ajouter éventuellement un fichier `CONTRIBUTING.md` si d'autres personnes participent.
- Prévoir une version francophone du README si le public cible est français.
