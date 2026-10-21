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