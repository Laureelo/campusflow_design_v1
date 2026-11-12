# Design system v1

## Couleurs

| Rôle | Valeur | Usage | Contraste |
|---|---|---|---|
| Couleur de marque (graine) | #EC3013 | Bouton flottant, logo, grands éléments | Icône blanche dessus : 4,2:1 (seuil de 3:1 pour un élément graphique, atteint) |
| Action principale | #C42B13 | Fond des boutons pleins, liens | Texte blanc dessus : 5,67:1. Sur fond clair : 5,54:1 |
| Fond | #FFFBFF | Fond des écrans | |
| Texte | #1F1B1A | Titres et texte courant | 16,7:1 sur le fond |
| Texte secondaire | #5C5755 | Sous-titres, cours, dates | 6,95:1 sur le fond |
| Réussite | #1B6B3A | Tâche terminée | 6,38:1 sur le fond |
| Erreur, retard | #B3261E | Repère « En retard », erreurs de saisie | 6,38:1 sur le fond |

Le rapport minimal pour du texte courant est de 4,5:1 (WCAG AA). La couleur de marque #EC3013 donne seulement 4,2:1 avec du blanc, ce qui est insuffisant pour du texte. Je la garde donc pour les grands éléments et je prends #C42B13 pour tout ce qui porte du texte.

## Typographie

Police : Roboto (par défaut sur Android, échelle Material 3).

| Style | Taille | Usage |
|---|---|---|
| Titre d'écran | 22 sp | Barre d'application |
| Titre de tâche | 16 sp | Ligne de liste |
| Texte | 14 sp | Détails, formulaires |
| Légende | 12 sp | Cours et date sous un titre |

Le texte doit rester utilisable à 200 % de la taille système : aucune hauteur fixe sur les lignes de texte.

## Espacements et formes

- Espacements : 4, 8, 12, 16, 24 dp
- Marge latérale des écrans : 16 dp
- Rayon des cartes : 12 dp
- Boutons pleins : forme en pilule
- Cible tactile minimale : 48 × 48 dp

## Trois composants

**Ligne de tâche.** Icône d'état à gauche (cercle vide ou coché), titre au centre qui prend la place restante et se coupe avec des points de suspension, sous-titre avec le cours et la date, repère « En retard » en rouge à droite. Hauteur 62 dp. Le libellé lu par un lecteur d'écran regroupe le titre, le cours et l'échéance.

**Bouton plein.** Fond #C42B13, texte blanc 14 sp, hauteur 52 dp, désactivé quand l'action n'est pas possible (par exemple « Marquer comme fait » sur une tâche déjà terminée).

**Barre de navigation.** Trois destinations (Échéances, Cours, Profil), icône et libellé, chacune d'au moins 48 dp de large, destination active mise en évidence.

## Tailles de fenêtre visées

| Classe | Largeur | Appareil | Structure |
|---|---|---|---|
| Compacte | moins de 600 dp | Téléphone (cible : 360 × 800) | Une colonne, barre de navigation en bas |
| Moyenne | 600 à 839 dp | Petite tablette | Une colonne élargie |
| Étendue | 840 dp et plus | Tablette, paysage | Liste et détail côte à côte |

La classe compacte est celle qu'on traite en premier, car c'est le téléphone des étudiants.

## Traduction en Flutter

```dart
ThemeData(
  colorScheme: ColorScheme.fromSeed(seedColor: const Color(0xFFEC3013)),
  useMaterial3: true,
)
```

La graine est #EC3013 comme en cours. À vérifier une fois l'application lancée : les couleurs générées par `fromSeed` doivent aussi respecter les rapports de contraste ci-dessus, sinon on les remplace par les valeurs de ce tableau.
