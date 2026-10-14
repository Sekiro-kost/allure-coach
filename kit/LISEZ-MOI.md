# Kit coach course à pied avec Claude et COROS

Ce kit te donne un coach : il analyse tes données COROS, cale tes zones cardiaques, construit un plan pour ta course, l'envoie sur ta montre et te monte un dashboard. Le dashboard se met à jour tout seul. Tu peux y déplacer ou échanger une séance (appui long sur la tuile), l'alléger ou la renforcer : la montre suit. Il te dit aussi si tu es en forme pour la séance du jour, compare le prévu et le réalisé après chaque séance, et affiche la météo de tes sorties. En option : un programme de renfo, une fiche Jour J avec la prévision météo du départ, une frise de saison, et un bilan chaque dimanche où Claude propose d'ajuster la semaine suivante.

## Ce qu'il te faut

- Claude avec Cowork (plan payant).
- Une montre COROS, et le connecteur **Coros** ajouté dans claude.ai → Réglages → Connecteurs.
- Facultatif : le connecteur **Open-meteo** (même endroit) pour la météo de tes sorties et la prévision du jour de course.

## Installation (5 minutes)

1. Dans Claude, crée un projet, par exemple « Course à pied ».
2. Ajoute les deux fichiers du kit dans les fichiers du projet :
   - `GUIDE-CLAUDE.md`
   - `coach-dashboard-template.html`
3. Démarre une tâche Cowork dans ce projet et écris : **« Lance le kit coach course »**.
4. Réponds aux questions (ta course, ta date, ton objectif, tes jours dispo). Claude te présente tes zones, son diagnostic et le plan avant de l'envoyer sur ta montre.

## Bon à savoir

- Si tu as déjà un plan d'une autre application d'entraînement sur ta montre, retire-le dans l'app COROS : Claude ne peut modifier que les plans qu'il a créés.
- La première fois que tu ouvres le dashboard, Claude te demande d'autoriser l'accès à COROS pour cette page.
- Pour ne pas confirmer chaque déplacement de séance, passe l'outil « updateTrainingPlan » du connecteur Coros en « Toujours autoriser ».
- Ouvre toujours le dashboard depuis Claude (barre latérale ou galerie), pas dans un navigateur : c'est ce qui permet la synchro avec la montre.
- Dans le calendrier, un tap ouvre le détail de la séance ; un appui long la déplace ou l'échange avec une autre séance. La montre récupère le changement à sa prochaine synchro avec l'app COROS.
- Le renfo reste dans le dashboard : COROS n'accepte pas ces séances.
- Rien n'est modifié sur ta montre sans ton accord.
