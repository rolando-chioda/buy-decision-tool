# Guide rapide

[English](GUIDE.md) · [Italiano](GUIDE.it.md) · **Français**

> Ce n'est pas un outil de gestion de budget : si vous mettez un article dans la liste, c'est que vous pouvez vous le permettre. Il sert seulement à décider si et quand l'acheter.

## Installation

Il n'y a rien à installer. Choisissez une option :

1. **Sur votre ordinateur** : téléchargez [`buy-decision-tool.html`](https://github.com/rolando-chioda/buy-decision-tool/raw/main/buy-decision-tool.html) et ouvrez-le d'un double-clic. Les données restent dans ce navigateur.
2. **Sur votre site** : déposez le fichier sur n'importe quel hébergement statique. Chaque visiteur garde ses données dans son navigateur.
3. **Sur claude.ai** : demandez à Claude de publier le fichier comme artifact avec les capabilities `db` et `downloads`. Les données sont enregistrées dans votre compte et vous suivent sur chaque appareil.

## Utilisation

1. **Réglages** : choisissez la devise. Si vous le souhaitez, modifiez les critères et leurs poids.
2. **Articles → + Ajouter un article** : saisissez le nom, le prix, MoSCoW, urgent/important, les utilisations par mois, la durée de vie et les notes de 1 à 10 des critères. Cliquez sur une ligne pour revoir les données, puis sur **Modifier** pour les changer.
3. **★ Résultats** : voyez le prochain achat conseillé, ce qui est prêt et ce qui est encore en attente. Cliquez sur une ligne pour voir tous les détails.
4. **Après l'achat** : dans ★ Résultats, utilisez le menu d'état à côté de l'article (sans l'ouvrir) et choisissez *Acheté*, *Plus nécessaire* ou *Reporté* de N jours ou mois.
5. **Sauvegarde** : dans Réglages → Données et sauvegarde, utilisez souvent **Télécharger une sauvegarde (JSON)**. Pour restaurer, utilisez **Importer un JSON**.

Pour essayer : Réglages → Données et sauvegarde → **Charger l'exemple**.

Les résultats sont seulement indicatifs : voir l'[avertissement](DISCLAIMER.md#français).
