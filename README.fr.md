# Buy Decision Tool

[English](README.md) · [Italiano](README.it.md) · **Français**

👉 **[Guide rapide : installation et utilisation en 2 minutes](GUIDE.fr.md)**

Un seul fichier HTML qui vous aide à décider **quoi acheter en premier**. Il combine cinq techniques connues en un seul classement :

| Technique | Ce qu'elle fait ici |
|---|---|
| **Matrice de décision pondérée** | Vous notez chaque article de 1 à 10 sur des critères que vous choisissez et pondérez. Le prix et le coût par utilisation sont notés automatiquement. |
| **MoSCoW** | Must / Should / Could / Won't have. Multiplie le score ; les « Won't have » sont exclus. |
| **Matrice d'Eisenhower** | Urgent × important. Multiplie le score et place chaque article dans l'un des quatre quadrants. |
| **Coût par utilisation** | Prix ÷ (utilisations par mois × durée de vie prévue en mois). |
| **Règle d'attente** | Les articles attendent quelques jours (ou semaines, au-dessus d'un seuil de prix) avant de pouvoir être conseillés. Cela filtre les achats impulsifs. |

Il propose aussi :

- **Lots** : liez les articles à acheter ensemble. Un lot est classé, budgété et conseillé comme un seul achat.
- **Valeur et rapport qualité-prix** : une matrice à quatre secteurs (Bonne affaire, Investissement, Petit plaisir, À éviter) qui réunit tous les critères sur deux axes : les notes manuelles donnent la valeur, le prix et le coût par utilisation donnent le rapport qualité-prix.
- **Budget** : en parcourant le classement, il indique ce que vous pouvez acheter maintenant, ce qui est encore en attente et ce qui dépasse le budget.
- **Notes** pour chaque article (liens, modèles, magasins, doutes).
- **État** de chaque article : *Acheté* et *Plus nécessaire* le déplacent dans une archive (hors classement et budget) ; *Reporté de N jours ou mois* le retire du classement jusqu'à cette date et l'affiche parmi les *Reportés* dans les résultats.
- **Descriptions** sous chaque champ et réglage, que vous pouvez masquer une fois connues. Les réglages sont regroupés en sous-onglets : budget et devise, règle d'attente, critères, données et sauvegarde, fonctionnement.
- **Langues** : français, anglais, italien. La page suit la langue du navigateur et propose un sélecteur.
- **Devises** : EUR, USD, GBP, CHF, CAD, AUD, JPY.
- **Sauvegarde** : téléchargez vos données en JSON et réimportez-les n'importe où.

## Utilisez-le où vous voulez

Pas de serveur, pas de compte. Vos données restent là où vous ouvrez la page.

1. **Sur votre ordinateur.** Téléchargez [`buy-decision-tool.html`](buy-decision-tool.html) et ouvrez-le dans n'importe quel navigateur (Safari, Chrome, Firefox, Edge). Les données sont enregistrées dans le stockage local de ce navigateur.
2. **Sur votre site ou hébergement.** C'est un fichier statique : placez-le sur n'importe quel hébergement statique (votre GitHub Pages, Netlify, un NAS, un intranet). Les données de chaque visiteur restent dans son navigateur.
3. **Dans votre compte claude.ai.** Demandez à Claude de publier `buy-decision-tool.html` comme artifact avec la capability `db` (et `downloads` pour les sauvegardes). La page détecte claude.ai d'elle-même et enregistre dans la base de données de cet artifact au lieu du navigateur : vous retrouvez la même liste sur chaque appareil où vous êtes connecté.

La page charge deux polices depuis Google Fonts. Si elles ne sont pas disponibles (par exemple hors ligne), elle utilise les polices du système et fonctionne quand même.

## Vos données

- **Mode navigateur** (options 1 et 2) : les données sont dans le `localStorage` du navigateur pour cette page. Effacer les données du site, utiliser une fenêtre privée ou changer de navigateur vous fait repartir d'une liste vide. Utilisez régulièrement **Télécharger une sauvegarde**, et **Importer un JSON** pour restaurer.
- **Mode claude.ai** (option 3) : les données sont dans la base de données de votre artifact, privées tant que vous ne le partagez pas.
- Le fichier de sauvegarde est du JSON simple : vous pouvez le lire, le garder dans votre cloud ou le passer d'un mode à l'autre.

La page affiche un rappel quand votre dernière sauvegarde a plus de 8 jours.

## Calcul du score

```
score final = score de la matrice pondérée × facteur MoSCoW × facteur Eisenhower
```

- Matrice pondérée : moyenne des notes de 1 à 10, pondérée par les poids des critères. Les critères automatiques donnent 10 à l'article le moins cher et 1 au plus cher (linéaire entre les deux).
- MoSCoW : Must ×1, Should ×0,75, Could ×0,5, Won't = exclu.
- Eisenhower : urgent et important ×1,2, important seulement ×1, urgent seulement ×0,8, ni l'un ni l'autre ×0,6.
- Règle d'attente : un article encore en attente reste dans le classement mais n'est pas conseillé.
- Budget : en parcourant le classement, chaque article (ou lot) prêt passe en **Acheter** s'il tient dans le budget restant, sinon **Hors budget**.

Chacune des trois méthodes (matrice, MoSCoW, Eisenhower) peut être désactivée dans **Réglages → Méthodes de classement**, avec un lien vers la page Wikipédia de chacune. Si les trois sont désactivées, le classement suit uniquement le prix.

Tout est en JavaScript simple dans le fichier HTML : vous pouvez le lire et le modifier.

## Avertissement

C'est un outil d'aide, pas un conseil. Les résultats dépendent uniquement de ce que vous saisissez, peuvent être erronés, et la décision finale vous appartient. Voir [DISCLAIMER.md](DISCLAIMER.md#français).

## Licence

[MIT](LICENSE) © 2026 Rolando Chioda
