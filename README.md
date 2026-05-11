@"
# Belife DT - ETL Agent Reporting

## Description
ETL Apache Hop pour le traitement mensuel des polices d'assurance.
Génère un fichier Excel par agent contenant uniquement ses polices actives.

## Prérequis
- Apache Hop 2.x+
- Java 17 (OpenJDK)
- Variables d'environnement système : HOP_CONFIG_FOLDER, HOP_AUDIT_FOLDER, HOP_OPTIONS

## Structure du projet
- pipelines/     : Pipelines de transformation (.hpl)
- workflows/     : Workflow d'orchestration (.hwf)
- referentiels/  : Fichiers de mapping métier
- config/        : Paramètres de traitement configurables
- input/         : Fichier Excel source mensuel (non versionné)
- output/        : Fichiers Excel générés par agent (non versionnés)

## Lancement
1. Ouvrir Hop GUI
2. Sélectionner projet : belife-dt-etl
3. Sélectionner environnement : DEV
4. Lancer : workflows/wf_traitement_mensuel.hwf

## Paramètres configurables
Voir config/parametres.json
- PERIODE_JOURS   : Nombre de jours pour le filtre de date de modification
- STATUT_FILTRE   : Code statut à retenir (défaut : 00)
- OUTPUT_FILE_PREFIX : Préfixe des fichiers de sortie
"@ | Out-File -FilePath "README.md" -Encoding UTF8