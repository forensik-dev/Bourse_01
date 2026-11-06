# Bourse_01

Gestion boursière — visualiseur de portefeuille à partir d'un export CSV EasyBourse.

## Contenu

| Fichier | Description |
|---|---|
| `portefeuille.html` | Page autonome (HTML + CSS + JS, aucun serveur requis) pour afficher un portefeuille boursier à partir d'un CSV |
| `portefeuille-temps-reel.html` | Page autonome pour suivre un portefeuille en temps réel : cours rafraîchis automatiquement, gains/pertes, ROI et rendement annualisé |

## Utilisation

1. Ouvrir `portefeuille.html` dans un navigateur (double-clic, usage 100 % local).
2. Cliquer sur le bouton bleu **« Import CSV intraday »** (en haut à droite de l'en-tête « Bourse »).
3. Sélectionner le fichier CSV exporté depuis EasyBourse.

La page affiche alors :

- des **cartes de résumé** : valeur totale, +/- value des positions, rendement global ;
- les **informations du compte** présentes dans le CSV (type de compte, date de valorisation, soldes, totaux) — la ligne « Votre compte » est masquée ;
- le tableau **Positions Actives** avec toutes les colonnes du CSV : valeur, code ISIN, place de cotation, position, quantité, cours, prix moyen, valorisation, +/- value, performance (%) et poids. Les valeurs en perte apparaissent en rouge, en gain en vert.

## Suivi en temps réel (`portefeuille-temps-reel.html`)

1. Ouvrir `portefeuille-temps-reel.html` dans un navigateur (usage 100 % local).
2. Ajouter des positions (ticker Stooq, quantité, prix d'achat, date d'achat) ou charger le portefeuille d'exemple.
3. Les cours sont rafraîchis automatiquement (intervalle réglable en haut à droite, rafraîchissement manuel possible).

La page affiche :

- des **cartes de résumé** : valorisation totale, gains/pertes (en € et en %), ROI global et rendement annualisé du portefeuille ;
- le tableau des **positions** : cours actuel, variation du jour, valorisation, capital investi, gain/perte en € et en %, ROI et rendement annualisé par ligne ;
- les positions sont enregistrées dans le `localStorage` du navigateur ; un cours manuel peut être saisi si le ticker est indisponible.

## Format du CSV attendu

Export « Valorisation intraday » d'EasyBourse :

- séparateur `;` ;
- décimales à la virgule (ex : `11,125`) ;
- encodage Windows-1252 ;
- le tableau des positions commence à la ligne d'en-tête `Valeur;Code Isin;...`.

## Développement

Aucune dépendance, aucun build : un seul fichier statique. Les modifications se font directement dans `portefeuille.html`, via une branche et une pull request.
