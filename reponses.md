## Partie 01

**Q1.2.** Au clic, un effet d'encre (ripple) se propage depuis le point
touché. Sans onTap, la ligne ne réagit pas : aucun effet visuel, ni action.

**Q1.4.**
- dense: true -> ligne plus compacte (hauteur et texte réduits)
- isThreeLine: true -> place pour un sous-titre sur 2 lignes,
  icône et trailing alignés en haut
- enabled: false -> texte grisé, le tap est désactivé

**Question de réflexion.**
leading est l'élément placé au début (à gauche) de la ligne, souvent une icône
ou un avatar ; trailing est placé à la fin (à droite), souvent une action,
une flèche ou une valeur. Un ListTile doit avoir une largeur contrainte car il
est construit avec des Row internes qui ont besoin d'une largeur finie pour
répartir leurs éléments : dans un parent à largeur infinie (ex. Row sans
Expanded), il y a une erreur de layout.


## Partie 02

**Q2.1.** Message : "RenderFlex overflowed by ... pixels on the bottom"
(bande jaune et noire). Une Column ne défile pas : si ses enfants dépassent
la hauteur de l'écran, ils débordent.

**Q2.3.** ListTile.divideTiles ajoute automatiquement les séparateurs entre
les éléments, avec le style du thème. Moins de code, pas de Divider à
répéter ni à oublier.

**Q2.5.** ListView(children: ...) construit TOUS les éléments d'un coup, même
ceux hors écran. ListView.builder ne construit que les éléments visibles (à la
demande) : pour 1000 livres, c'est bien plus rapide et économe en mémoire.

**Q2.8.** Sans Expanded : "Vertical viewport was given unbounded height".
Une Column donne une hauteur illimitée à ses enfants, et un ListView vertical
veut prendre toute la hauteur disponible : il ne peut pas la calculer.
Expanded lui donne l'espace restant de la Column.

**Q2.9.** shrinkWrap: true fait prendre au ListView la taille de son contenu,
et NeverScrollableScrollPhysics désactive son défilement propre. Utile pour
une petite liste dans une page qui défile déjà (SingleChildScrollView). À
éviter sur de longues listes car tous les éléments sont construits.