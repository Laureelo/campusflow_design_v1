# Wireframes

Cinq écrans en basse fidélité, au format 360 × 800 dp, dans le dossier `wireframes`.

| # | Écran | Fichier |
|---|---|---|
| 1 | Connexion | wireframes/01_login.svg |
| 2 | Échéances (trois variantes) | wireframes/02_deadlines_A.svg, 02_deadlines_B.svg, 02_deadlines_C.svg |
| 3 | Détail d'une tâche | wireframes/03_detail.svg |
| 4 | Nouvelle tâche | wireframes/04_new_task.svg |
| 5 | Profil | wireframes/05_profile.svg |

La navigation principale est une barre inférieure avec trois destinations (Échéances, Cours, Profil), parce que ce sont trois destinations de même niveau, atteignables au pouce.

## Écran Échéances : trois variantes

**Variante A : liste de la semaine.** Une liste simple des tâches de la semaine, avec un repère « Demain » ou « En retard » à droite et un bouton flottant pour ajouter.

![Variante A](wireframes/02_deadlines_A.svg)

**Variante B : groupée par cours.** Les tâches sont rangées sous le nom de leur cours.

![Variante B](wireframes/02_deadlines_B.svg)

**Variante C : bandeau de jours.** Une rangée de sept jours en haut, puis les tâches du jour choisi.

![Variante C](wireframes/02_deadlines_C.svg)

## Choix : la variante A

Évaluation avec les cinq questions de la grille du cours.

| Question | A | B | C |
|---|---|---|---|
| 1. Répond au besoin du persona ? | Oui : on voit ce qui est dû cette semaine (job story 1) | En partie : l'urgence est dispersée entre les cours | En partie : il faut choisir un jour pour voir ses tâches |
| 2. Parcours le plus court ? | Oui : tout est visible dès l'ouverture, ajout en 3 appuis (bouton +, champ titre, Enregistrer) | Idem pour l'ajout, mais il faut parcourir plusieurs groupes | Non : un appui de plus pour changer de jour |
| 3. Accessible ? | Oui : lignes de 62 dp, bouton flottant de 56 dp | Oui : lignes de 52 dp | Non : les jours font 40 dp de large, sous le minimum de 48 dp |
| 4. Réalisable en Flutter ? | Oui : ListView.builder et ListTile | Oui : mais en-têtes de groupe à gérer | Oui : mais un calendrier demande plus de code |
| 5. Cohérent avec le design system ? | Oui : composant carte de tâche | Oui | Ajoute un composant (sélecteur de jour) |

La variante A est retenue. Elle répond directement à la job story 1, c'est la plus courte, et c'est celle qui respecte tous les seuils d'accessibilité sans modification. La variante B pourra servir plus tard comme filtre sur l'écran Cours.

## Écrans de détail

![Connexion](wireframes/01_login.svg)
![Détail](wireframes/03_detail.svg)
![Nouvelle tâche](wireframes/04_new_task.svg)
![Profil](wireframes/05_profile.svg)
