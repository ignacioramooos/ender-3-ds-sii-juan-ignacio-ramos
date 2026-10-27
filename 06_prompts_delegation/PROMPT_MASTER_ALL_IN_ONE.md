# PROMPT MASTER : TOUT-EN-UN

> **Utilisation :** Copiez l'intégralité du bloc ci-dessous et collez-le directement dans votre onglet Gemini en ligne (**Ender 3 3D Printer Kinematic Analysis**).

```text
Tu es professeur de Sciences Industrielles de l'Ingénieur (SII) enseignant en CPGE MPSI au Lycée Stanislas Cannes (Mme M. Prot).
Tu dois réaliser la modélisation cinématique complète et rigoureuse pour mon DM n°1 de cinématique / schématisation, portant sur mon imprimante 3D personnelle : la Creality Ender 3.

RAPPEL STRICT DU CAHIER DES CHARGES DU DM :
1. Le système comporte 5 sous-ensembles cinématiques avec les noms et couleurs suivants :
   - Châssis fixe (Noir, symbole de bâti hachuré) : Châssis d'aluminium, contient l'électronique entre autres.
   - Vis centrale (Bleu) : Moteur stepper, axe Z.
   - Traverse horizontale (Rouge) : Bouge de haut en bas (axe Z) et tient l'extrudeur.
   - Chariot tête extrudeur (Vert) : Bouge sur l'axe X (droite / gauche).
   - Plateau mobile (Rose clair) : Bouge sur l'axe Y, il est chauffé.
2. On modélise l'axe vertical Z à travers son mécanisme de transmission (Vis centrale + écrou de la Traverse horizontale) en boucle cinématique fermée avec le Châssis fixe.

Fournis une réponse structurée découpée en 4 parties :

### PARTIE A : SOUS-ENSEMBLES CINÉMATIQUES & PARAMÉTRAGE GÉOMÉTRIQUE
1. Présente les 5 sous-ensembles (Châssis fixe, Vis centrale, Traverse horizontale, Chariot tête extrudeur, Plateau mobile) avec leurs couleurs et pièces constitutives.
2. Définis le repère principal R0(O0, x0, y0, z0) direct lié au Châssis fixe et les centres géométriques caractéristiques O1, O2, O3, O4, O5 des liaisons.

### PARTIE B : CARACTÉRISATION DES LIAISONS & TORSEURS CINÉMATIQUES
Pour chacune des 5 liaisons suivantes :
1. Liaison L01 (Châssis fixe / Vis centrale) : Pivot d'axe (O1, z0)
2. Liaison L12 (Vis centrale / Traverse horizontale) : Hélicoïdale d'axe (O2, z0) de pas pz = 8 mm/tour
3. Liaison L02 (Châssis fixe / Traverse horizontale) : Glissière de direction z0 (centre O3)
4. Liaison L23 (Traverse horizontale / Chariot tête extrudeur) : Glissière de direction x0 (centre O4)
5. Liaison L04 (Châssis fixe / Plateau mobile) : Glissière de direction y0 (centre O5)

### PARTIE C : FERMETURE CINÉMATIQUE DE LA BOUCLE Z & GRAPHE DES LIAISONS
1. Écris l'équation de fermeture cinématique de la boucle Z (Châssis fixe -> Vis centrale -> Traverse horizontale -> Châssis fixe) au point O2.
2. Démontre la relation entrée-sortie liant la vitesse d'élévation Vz de la Traverse horizontale à la vitesse de rotation du moteur stepper Z.

### PARTIE D : GUIDE DE DESSIN DU SCHÉMA CINÉMATIQUE 2D ET 3D
Détaille le tracé du schéma 2D dans le plan (O0, x0, z0) et du schéma 3D en perspective cavalière avec le code couleur (Noir, Bleu, Rouge, Vert, Rose clair).
```
