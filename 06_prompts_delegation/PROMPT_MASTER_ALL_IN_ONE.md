# PROMPT MASTER : TOUT-EN-UN (Pour Gemini 4 Argon High / Modèle Avancé)

> **Utilisation :** Copiez l'intégralité du bloc ci-dessous et collez-le directement dans votre onglet Gemini en ligne (**Ender 3 3D Printer Kinematic Analysis**).

```text
Tu es un professeur agrégé de Sciences Industrielles de l'Ingénieur (SII) enseignant en CPGE MPSI (Lycée Stanislas).
Tu dois réaliser la modélisation cinématique complète et rigoureuse pour mon DM n°1 de cinématique / schématisation, portant sur mon imprimante 3D personnelle : la Creality Ender 3 (modèle de base).

RAPPEL STRICT DU CAHIER DES CHARGES DU DM :
1. Le système doit comporter au minimum 3 LIAISONS MÉCANIQUES DIFFÉRENTES. Il est strictement interdit de modéliser uniquement les 3 axes sous forme de 3 liaisons glissières.
2. Pour respecter cette contrainte, on modélise l'axe vertical Z à travers son mécanisme interne de transmission (vis mère trapézoïdale + écrou laiton) en boucle cinématique fermée avec le portique X et le bâti.
3. Toutes les classes d'équivalence doivent impérativement comporter la liste exhaustive et précise des pièces physiques réelles (tout numéro isolé entraîne un zéro d'après la consigne).
4. Le bâti doit être clairement mis en valeur avec le symbole normalisé de masse/hachures.
5. Les notations des liaisons et les symboles doivent respecter scrupuleusement la norme NF EN ISO 3952 / AFNOR.

Fournis une réponse structurée, exhaustive et directement exploitable découpée en 4 parties :

---

### PARTIE A : DÉCOUPAGE EN CLASSES D'ÉQUIVALENCE & PARAMÉTRAGE GÉOMÉTRIQUE
1. Définis les 5 classes d'équivalence cinématique :
   - E0 : Le Bâti (Châssis fixe) [Couleur : Noir / Symbole de masse]
   - E1 : Ensemble Vis mère Z et rotor moteur [Couleur : Bleu]
   - E2 : Portique transversal X et écrou en laiton [Couleur : Rouge]
   - E3 : Chariot de tête d'impression X (Hotend / buse) [Couleur : Vert]
   - E4 : Plateau chauffant mobile Y [Couleur : Orange]
   Pour CHAQUE classe, liste de manière ultra-précise et exhaustive l'ensemble des pièces réelles de la Creality Ender 3 qui la composent (profilés, moteurs, platines, vis, écrous, galets, carters).
2. Définis le repère principal R0(O0, x0, y0, z0) direct lié au bâti et les centres géométriques caractéristiques O1, O2, O3, O4, O5 des liaisons.

---

### PARTIE B : CARACTÉRISATION DES LIAISONS & TORSEURS CINÉMATIQUES
Pour chacune des 5 liaisons suivantes :
1. Liaison L01 (entre E0 et E1) : Pivot d'axe (O1, z0)
2. Liaison L12 (entre E1 et E2) : Hélicoïdale d'axe (O2, z0) de pas pz = 8 mm/tour
3. Liaison L02 (entre E0 et E2) : Glissière de direction z0 (centre O3)
4. Liaison L23 (entre E2 et E3) : Glissière de direction x0 (centre O4)
5. Liaison L04 (entre E0 et E4) : Glissière de direction y0 (centre O5)

Fournis :
- La désignation normalisée complète (nom, centre, axe/direction, caractéristique géométrique comme le pas).
- La solution constructive réelle sur l'Ender 3 (ex : guidage par galets en V dans profilé aluminium, roulements du moteur NEMA 17, écrou Tr8x8).
- Le torseur cinématique associé {V(j/i)} exprimé sous forme matricielle 6 composantes au point caractéristique.
- Les degrés de liberté autorisés (DDL).

---

### PARTIE C : FERMETURE CINÉMATIQUE DE LA BOUCLE Z & GRAPHE DES LIAISONS
1. Écris l'équation de fermeture cinématique de la boucle Z (E0 -> E1 -> E2 -> E0) :
   {V(E2/E0)} = {V(E2/E1)} + {V(E1/E0)}
2. Projette sur le taux de rotation selon z0 et sur la vitesse linéaire au point O2 selon z0.
3. Démontre la relation entrée-sortie liant la vitesse d'élévation Vz du portique à la vitesse de rotation omega_moteur du moteur pas-à-pas Z.
4. Donne la disposition exacte du Graphe des Liaisons (arcs, nœuds, symboles de masse, indications de chaque liaison) pour que je puisse le reproduire à main levée sans hésitation.

---

### PARTIE D : GUIDE DE DESSIN DU SCHÉMA CINÉMATIQUE 2D ET 3D
1. Schéma 2D (Plan de projection O, x0, z0) :
   - Donne les coordonnées relatives ou le guide pas-à-pas pour positionner chaque élément.
   - Détaille la façon exacte de tracer le symbole AFNOR normalisé de chaque liaison (Pivot verticale avec butées, Hélicoïdale avec son hélice, Glissière verticale et horizontale).
   - Indique la couleur de chaque trait et les hachures du bâti.
2. Schéma 3D (Perspective isométrique) :
   - Indique l'orientation des axes x0, y0, z0.
   - Détaille la façon de dessiner les symboles spatiaux normalisés (cylindre avec collerettes de butée pour le pivot, cylindre à gorge hélicoïdale pour l'hélicoïdale, prismes rectangulaires coulissants pour les glissières).
```
