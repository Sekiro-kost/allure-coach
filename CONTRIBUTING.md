# Contribuer

Merci de ton intérêt. Quelques règles pour garder le dépôt propre.

## Avant d'ouvrir une issue

- Précise la version du kit (voir [`CHANGELOG.md`](CHANGELOG.md)), si le connecteur Coros et Open-meteo sont connectés, et ce que tu as fait juste avant le problème.
- **Retire toute donnée personnelle** : prénom, FC, lieu, dates de course, lien de ton dashboard. Une capture d'écran de la démo (`exemples/demo.html`) suffit souvent.

## Proposer un changement

1. Fais ta modification dans `kit/coach-dashboard-template.html` et, si le schéma `COACH` change, dans `kit/GUIDE-CLAUDE.md` (schéma, guidage et exemples).
2. Régénère la démo : `python3 scripts/build-demo.py`.
3. Ouvre `exemples/demo.html` dans ton navigateur et parcours les onglets : aucune erreur dans la console.
4. Ajoute une ligne dans [`CHANGELOG.md`](CHANGELOG.md).

## Principes

- **Aucune donnée personnelle dans le modèle.** Tout ce qui est propre à l'athlète passe par `COACH`. Les onglets facultatifs (Renfo, Jour J, Saison) disparaissent quand leurs données sont absentes.
- **Le modèle doit survivre à des données manquantes** : une montre sans VFC ne doit pas faire tomber la page.
- Pas de dépendance externe nouvelle dans la page publiée : seuls les hôtes de scripts autorisés par les artifacts de Claude fonctionnent.
- `exemples/exemple-coach.json` reste fictif.
