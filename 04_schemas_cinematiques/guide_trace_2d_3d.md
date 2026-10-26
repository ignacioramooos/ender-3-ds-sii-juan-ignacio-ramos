# Guide de Tracé Normalisé des Schémas Cinématiques 2D et 3D en Couleur

**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI  
**Norme de référence :** AFNOR NF EN ISO 3952 (Schémas cinématiques — Symboles graphiques)

---

## 1. Convention de couleurs (Bijection stricte : 1 couleur = 1 classe d'équivalence)

> **Règle d'or en CPGE SII :** Sur un schéma cinématique en couleur, **une couleur représente exclusivement une classe d'équivalence cinématique $E_k$** (et jamais une liaison isolée). Un symbole de liaison entre $E_i$ et $E_j$ est donc impérativement tracé avec les **deux couleurs** de $E_i$ et $E_j$. Il est strictement interdit d'introduire une 6e couleur arbitraire.

| Classe d'équivalence | Couleur de tracé | Feutre / Crayon conseillé | Repère local lié |
| :--- | :--- | :--- | :--- |
| **$E_0$ — Bâti fixe** | **Noir** | Stylo feutre fin noir ($0{,}5\text{ mm}$) | $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ |
| **$E_1$ — Arbre moteur & Vis mère $Z$** | **Bleu** | Feutre fin bleu | $\mathcal{R}_1(O_1, \vec{x}_1, \vec{y}_1, \vec{z}_0)$ |
| **$E_2$ — Portique mobile horizontal $X$** | **Rouge** | Feutre fin rouge | $\mathcal{R}_2(O_3, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ |
| **$E_3$ — Chariot de tête d'impression** | **Vert** | Feutre fin vert | $\mathcal{R}_3(O_4, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ |
| **$E_4$ — Plateau chauffant mobile $Y$** | **Orange** | Feutre fin orange | $\mathcal{R}_4(O_5, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ |

---

## 2. Schéma Cinématique Minimal 2D en Couleur — Vue Frontale $(O_0, \vec{x}_0, \vec{z}_0)$

![Schéma cinématique minimal 2D en couleur de la Creality Ender 3](schema_cinematique_2d.svg)

### 2.1. Attention au sens du trièdre direct $\mathcal{R}_0$ en projection plane !
En vue de face dans le plan $(O_0, \vec{x}_0, \vec{z}_0)$ :
- L'axe $\vec{x}_0$ pointe horizontalement vers la **droite**.
- L'axe $\vec{z}_0$ pointe verticalement vers le **haut**.
- Pour que la base $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ soit **orthonormée directe**, on doit avoir $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$. Par la règle de la main droite, le vecteur $\vec{y}_0$ est donc **entrant dans la feuille** (dirigé vers l'arrière de l'imprimante) et se représente impérativement par un **cercle barré d'une croix $\otimes\,\vec{y}_0$** (et **surtout pas** $\odot$, qui définirait un repère indirect !).

### 2.2. Protocole de tracé à la main du schéma 2D (étape par étape)

1. **Étape 1 — Tracer le trièdre direct $\mathcal{R}_0$ et le bâti $E_0$ (en NOIR) :**
   - En bas à gauche, tracer les axes $\vec{x}_0$ (droite), $\vec{z}_0$ (haut) et le symbole $\otimes\,\vec{y}_0$ (entrant).
   - Tracer la ligne de base horizontale du bâti $E_0$ soulignée de **hachures obliques à $45^\circ$**, et marquer l'origine $O_0$.
   - À gauche, élever le montant vertical unique du bâti $E_0$ selon $\vec{z}_0$ (le schéma cinématique minimal ne représente qu'un seul montant pour l'unique liaison glissière équivalente $L_{02}$ du graphe des liaisons), coiffé d'un rappel de hachures de bâti.
   - Tracer une potence horizontale noire partant du bas du montant vers la droite jusqu'à l'axe de la vis mère en $O_1$, et y dessiner le **corps rectangulaire extérieur** de la liaison pivot $L_{01}$ avec hachures de bâti.

2. **Étape 2 — Tracer la vis mère $E_1$ et la liaison Pivot $L_{01}$ (en BLEU) :**
   - Tracer en pointillés fins l'axe vertical $(O_1, \vec{z}_0) = (O_2, \vec{z}_0)$ à droite du montant noir.
   - Tracer la tige verticale continue bleue de la vis mère $E_1$ traversant le rectangle noir en $O_1$ et montant jusqu'en haut du portique.
   - De part et d'autre du rectangle noir en $O_1$, tracer **deux petits traits horizontaux bleus perpendiculaires à l'axe** (symboles normalisés des **butées axiales** qui distinguent la liaison *Pivot* de la liaison *Pivot glissant*).
   - Ajouter la flèche courbe bleue du paramètre angulaire $\theta_1(t) = (\widehat{\vec{x}_0, \vec{x}_1})$ autour de l'axe $\vec{z}_0$.

3. **Étape 3 — Tracer le portique $E_2$ et les liaisons $L_{02}$ et $L_{12}$ (en ROUGE et BLEU) :**
   - En $O_3$ sur le montant vertical noir, tracer un **rectangle vertical rouge** muni d'une **croix diagonale interne rouge** (symbole AFNOR 2D d'une liaison *Glissière* vue de profil, empêchant toute confusion avec un pivot glissant). Ajouter la flèche verticale rouge $z_2(t)\,\vec{z}_0$.
   - En $O_2$ sur la tige verticale bleue (à la même hauteur que $O_3$), tracer le **rectangle rouge de l'écrou** traversé par la tige bleue, et ajouter **deux traits obliques parallèles bleus** à l'intérieur du rectangle (symbole AFNOR 2D du filet hélicoïdal de $L_{12}$).
   - Relier rigidement le rectangle $O_3$ au rectangle $O_2$ par un trait horizontal rouge, puis prolonger ce trait horizontal rouge vers la droite pour former la poutre du portique $E_2$.

4. **Étape 4 — Tracer le chariot de tête $E_3$ et la liaison Glissière $L_{23}$ (en VERT) :**
   - En $O_4$ sur la poutre horizontale rouge du portique, tracer un **rectangle horizontal vert** muni de sa **croix diagonale interne verte** (liaison glissière $L_{23}$ d'axe $(O_4, \vec{x}_0)$). Ajouter la flèche horizontale verte $x_3(t)\,\vec{x}_0$.
   - Sous le rectangle vert, descendre un trait vertical vert terminé par un triangle pointant vers le bas pour représenter la buse d'extrusion ($\varnothing 0{,}4\text{ mm}$).

5. **Étape 5 — Tracer le plateau chauffant $E_4$ et la liaison Glissière $L_{04}$ vue en bout (en ORANGE et NOIR) :**
   - À l'aplomb de $O_0$, élever un court segment vertical noir jusqu'au centre $O_5$, coiffé d'un **petit rectangle noir barré d'une croix** (section droite du rail prismatique $Y$ appartenant à $E_0$, vu en bout car son axe $\vec{y}_0$ est perpendiculaire à la feuille).
   - Entourer ce rectangle noir par un **rectangle extérieur orange** (coulisseau du chariot $Y$ appartenant à $E_4$), surmonté d'un segment vertical et d'un large **plateau horizontal orange** à rebords représentant le lit chauffant $E_4$.
   - À côté de $O_5$, indiquer le mouvement longitudinal par le symbole $\otimes\,y_4(t)\,\vec{y}_0$.

---

## 3. Schéma Cinématique Spatial 3D en Couleur — Perspective Axonométrique / Cavalière

![Schéma cinématique spatial 3D en couleur de la Creality Ender 3](schema_cinematique_3d.svg)

### 3.1. Règles de la perspective cavalière normalisée
Pour que le schéma 3D soit rigoureux et lisible :
- Le plan frontal $(O_0, \vec{x}_0, \vec{z}_0)$ est dessiné en vraie grandeur : $\vec{x}_0$ est horizontal vers la droite, $\vec{z}_0$ est vertical vers le haut.
- L'axe de profondeur $\vec{y}_0$ (entrant vers l'arrière de la machine) est représenté par une **fuyante rectiligne inclinée vers le haut et la droite** d'angle $\alpha \approx 34^\circ$ (pente exacte de $-2$ carreaux verticaux pour $+3$ carreaux horizontaux) et de rapport de réduction $k \approx 0{,}6$.
- **Règle de parallélisme absolu :** Toutes les arêtes orientées selon $\vec{y}_0$ (axe $\vec{y}_0$ du trièdre, rail central $Y$ du bâti, arêtes fuyantes des trois prismes de glissière $L_{02}, L_{23}, L_{04}$ et bords latéraux du plateau chauffant $E_4$) doivent être **strictement parallèles à cette même fuyante** !

### 3.2. Tableau de correspondance des symboles AFNOR 2D $\leftrightarrow$ 3D

| Liaison | Symbole normalisé 2D (Projection plane) | Symbole normalisé 3D (Perspective cavalière) | Couleurs utilisées |
| :--- | :--- | :--- | :--- |
| **$L_{01}$ : Pivot** $(O_1, \vec{z}_0)$ | Rectangle traversé par l'arbre + 2 barres d'arrêt axiales | **Cylindre creux** vertical (base elliptique) traversé par l'arbre + **2 collerettes/butées axiales** | Cylindre **Noir** ($E_0$) + Arbre & butées **Bleus** ($E_1$) |
| **$L_{12}$ : Hélicoïdale** $(O_2, \vec{z}_0)$ | Rectangle d'écrou + 2 traits obliques internes de filetage | **Cylindre vertical** contenant une **courbe hélicoïdale** (3 spires obliques) | Cylindre **Rouge** ($E_2$) + Tige & hélice **Bleues** ($E_1$) |
| **$L_{02}$ : Glissière** $(O_3, \vec{z}_0)$ | Rectangle vertical avec croix diagonale interne | **Prisme droit à section rectangulaire** (parallélépipède 3D) coulissant sur une tige prismatique | Prisme **Rouge** ($E_2$) sur montant **Noir** ($E_0$) |
| **$L_{23}$ : Glissière** $(O_4, \vec{x}_0)$ | Rectangle horizontal avec croix diagonale interne | **Prisme droit à section rectangulaire** horizontal coulissant sur la poutre $X$ | Prisme **Vert** ($E_3$) sur poutre **Rouge** ($E_2$) |
| **$L_{04}$ : Glissière** $(O_5, \vec{y}_0)$ | Deux rectangles concentriques vus en bout avec croix centrale | **Prisme droit à section rectangulaire** orienté selon la **fuyante $\vec{y}_0$** | Prisme **Orange** ($E_4$) sur rail fuyant **Noir** ($E_0$) |
