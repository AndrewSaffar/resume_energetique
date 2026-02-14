# Agent d'Extraction d'Informations Climatiques (ESG)

## Présentation

Ce projet implémente un pipeline basé sur un modèle de langage (LLM)
permettant d'extraire automatiquement des informations climatiques
structurées à partir de rapports ESG du secteur de l'énergie.

L'objectif est de transformer des documents narratifs non structurés
(rapports PDF) en données JSON exploitables pour l'analyse.

------------------------------------------------------------------------

## Problématique

Les entreprises énergétiques publient des rapports ESG contenant :

-   Des engagements de carboneutralité\
-   Des cibles de réduction d'émissions\
-   Des indicateurs Scope 1 / 2 / 3\
-   Des investissements de transition\
-   Des projets d'énergie renouvelable\
-   Des risques climatiques

Ces documents sont riches mais difficiles à exploiter automatiquement.

Ce projet vise à concevoir un agent capable de :

1.  Résumer un rapport complexe\
2.  Extraire des informations climatiques structurées\
3.  Vérifier la cohérence interne des données\
4.  Réduire le risque d'hallucination via des contrôles déterministes

------------------------------------------------------------------------

## Architecture du système

Rapport PDF → Extraction du texte → Résumé structuré (LLM) → Extraction
ESG (LLM) → Validation → JSON final

------------------------------------------------------------------------

## Stratégie de validation

-   Conformité au schéma JSON\
-   Vérification des types\
-   Cohérence chronologique\
-   Validation des plages numériques\
-   Traçabilité via extraits source

------------------------------------------------------------------------

## Limites

-   Validation partiellement assistée par LLM\
-   Absence de système RAG\
-   Pas d'évaluation quantitative formelle

------------------------------------------------------------------------

## Philosophie du projet

Ce projet privilégie :

-   La structuration des données\
-   La modularité\
-   La validation systématique\
-   L'applicabilité au secteur énergie / climat

## Reproductibilité

Pour exécuter ce code vous-meme, clonez d'abord le repo.
Ensuite, exécutez:
```
conda env create -f environment.yml
conda activate conda_env
```

Vous devrez également créer une clé API ici: https://aistudio.google.com/ et l'ajouter dans un fichier .env de cette maniere:
`GEMINI_API_KEY = <VOTRE__CLE_API>` 

Souvenez-vous que les LLMs sont non déterministes, donc les résultats varieront d'une exécution à l'autre.

## Données

Le rapport utilisé comme exemple pour le développement est disponible publiquement sur le site officiel de l'entreprise.

Pour respecter les droits d'auteur, le PDF n'est pas inclus  dans ce repo.

Les utilisateurs sont libres de télécharger n'importe quel rapport ESG public et de le placer dans le dossier `\documents`.

Note: Les outputs exemples dans ce repo utilisent des noms d'entreprise anonymisés.
La pipeline faite pour etre agnostiques du rapport.