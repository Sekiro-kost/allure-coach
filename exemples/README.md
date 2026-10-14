# Exemples

- `exemple-coach.json` : l'objet `COACH` d'un athlète **fictif** (Camille, 10 km, objectif 52:00). Sert de modèle de remplissage : chaque champ du schéma de `kit/GUIDE-CLAUDE.md` y apparaît. Le champ `_demo` n'est lu que par `scripts/build-demo.py`.
- `demo.html` : le dashboard rempli avec cet exemple. Ouvre-le dans ton navigateur. Il ne se connecte à rien, les dates se calent sur la semaine en cours. Fichier généré : ne le modifie pas à la main.

Pour le régénérer après avoir modifié le modèle ou l'exemple :

```
python3 scripts/build-demo.py
```

L'exemple ne touche jamais à un vrai projet : il ne passe ni par un artifact ni par ta base de données, seulement par ce dossier.
