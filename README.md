# Analyseur de BPU

Application web autonome pour chiffrer des cas concrets à partir d'un bordereau de prix
unitaires au format Excel, et en mesurer le résultat net et le rendement horaire.

## Fonctionnement

Un seul fichier HTML, exécuté entièrement dans le navigateur. Le bordereau déposé n'est
envoyé nulle part : il est lu localement, et les saisies restent dans le stockage du
navigateur ou dans un fichier JSON exporté par l'utilisateur.

1. **Import** — lecture du classeur (.xlsx, .xlsm, .xls), un onglet à la fois
2. **Synthèse** — poids du bordereau, montant du marché lorsque les quantités y figurent,
   lignes sur lesquelles se concentre le montant, répartition par famille
3. **Lignes** — toutes les lignes lues, prix modifiables pour chiffrer un bordereau vierge
4. **Coûts et temps** — coût direct et durée d'intervention, ligne par ligne
5. **Cas pratiques** — commandes types composées en choisissant des lignes et des quantités
6. **Résultats** — chiffre d'affaires, coûts, net et net par heure, export Excel
7. **Sauvegarde** — export et import du dossier en JSON

## Export Excel

Le classeur produit comporte trois onglets reliés par des formules : modifier un prix
unitaire ou le coefficient recalcule l'ensemble sans repasser par l'application.

## Dépendances

SheetJS pour la lecture, ExcelJS pour l'écriture, chargés depuis un CDN. Pour un
fonctionnement hors connexion, déposer les deux bibliothèques dans le dépôt et adapter
les balises `script` en chemins relatifs.

## Confidentialité

Aucune donnée n'est incluse dans ce dépôt. Le `.gitignore` écarte les formats de
bordereaux et les fichiers de sauvegarde pour éviter tout ajout involontaire.
