# Répertoire des Liaisons Mécaniques et Torseurs Cinématiques ($\{\mathcal{V}(E_j/E_i)\}$)

**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI (Lycée Stanislas)  
**Référence de cours :** Séquence 2 — Cours CM4 : *Cinématique du Solide Indéformable*  
**Conformité :** Norme AFNOR NF EN ISO 3952 — Modélisation des liaisons mécaniques parfaites

---

## 1. Rappels Théoriques Fondamentaux du Cours CM4

### 1.1. Définition et Structure d'un Torseur Cinématique
Un torseur cinématique $\{\mathcal{V}(S_j/S_i)\}$ est un couple ordonné constitué de deux champs vectoriels :
1. **La Résultante $\vec{\Omega}(S_j/S_i)$ :** Vecteur vitesse instantanée de rotation de $S_j$ par rapport à $S_i$. C'est un **vecteur libre**, indépendant du point de réduction géométrique.
2. **Le Moment $\vec{V}(P \in S_j/S_i)$ :** Champ affine antisymétrique des vitesses (vitesse instantanée du point coïncidant appartenant à $S_j$ passant par $P$ à l'instant $t$).

### 1.2. Relation de Transport du Torseur (Formule du solide / Varignon — Règle « BABAR »)
Pour transporter l'expression d'un torseur d'un point $A$ à un point $B$, on applique la **formule de Varignon** (CM4 § 1.3), mémorisée par la règle mnémotechnique **BABAR** (CM4 § 1.4) :
$$\vec{V}(B \in S_j/S_i) = \vec{V}(A \in S_j/S_i) + \overrightarrow{BA} \wedge \vec{\Omega}(S_j/S_i) = \vec{V}(A \in S_j/S_i) + \vec{\Omega}(S_j/S_i) \wedge \overrightarrow{AB}$$

### 1.3. Propriété d'Équiprojectivité (CM4 § 1.5)
$$\forall A, B \in S, \quad \vec{V}(B \in S/R) \cdot \overrightarrow{AB} = \vec{V}(A \in S/R) \cdot \overrightarrow{AB}$$
> **Condition impérative :** $A$ et $B$ doivent appartenir physiquement au **MÊME solide indéformable**.

### 1.4. Typologie des Torseurs Cinématiques (CM4 § 2.5)
1. **Torseur Couple ($\vec{\Omega} = \vec{0}$, $\vec{V} \neq \vec{0}$) :** Moment uniforme en tout point de l'espace. Caractérise un **mouvement de translation** (Glissières $L_{02}, L_{23}, L_{04}$).
2. **Torseur Glisseur ($\vec{\Omega} \neq \vec{0}$, automoment $I = \vec{\Omega} \cdot \vec{V}_A = 0$) :** Il existe une droite centrale appelée **axe instantané de rotation $\Delta$** sur laquelle le moment est nul ($\forall P \in \Delta, \vec{V}_P = \vec{0}$). Caractérise une **rotation pure autour d'un axe** (Pivot $L_{01}$).
3. **Torseur Hélicoïdal (Automoment $I = \vec{\Omega} \cdot \vec{V}_A \neq 0$) :** Le moment est colinéaire à la résultante sur l'axe central. Caractérise le **mouvement hélicoïdal vis-écrou** ($L_{12}$).

> [!WARNING]
> **Piège de concours MPSI (CM4 § 3.3) :** Le champ des accélérations n'est **PAS un torseur** en raison de la présence du terme de double produit vectoriel $\vec{\Omega} \wedge (\vec{\Omega} \wedge \overrightarrow{AB})$ (accélération centripète). De même, le champ des accélérations n'est pas équiprojectif.

---

## 2. Synthèse des 5 Liaisons Normalisées de la Creality Ender 3

Le système comporte **5 liaisons élémentaires** réparties en **3 familles normalisées distinctes** (respectant le cahier des charges de la Partie I) :

| Code | Classes reliées | Famille AFNOR | Caractéristique géométrique | DDL ($N_s / N_c$) | Typologie CM4 | Paramètre cinématique |
| :--- | :---: | :--- | :--- | :---: | :--- | :--- |
| **$L_{01}$** | $E_0 \leftrightarrow E_1$ | **Pivot** | Axe $(O_1, \vec{z}_0)$ | $1\text{ (1R, 0T)}$<br>$N_c = 5$ | **Torseur Glisseur** d'axe $(O_1, \vec{z}_0)$ | $\theta_1(t) = (\widehat{\vec{x}_0, \vec{x}_1})$ |
| **$L_{12}$** | $E_1 \leftrightarrow E_2$ | **Hélicoïdale** | Axe $(O_2, \vec{z}_0)$, pas $p_z = 8\text{ mm/tr}$ (filet à droite) | $1\text{ couplé}$<br>$N_c = 5$ | **Torseur Hélicoïdal** ($I \neq 0$) | $\omega_{21}(t)$ et $v_{21}(t) = +\frac{p_z}{2\pi}\omega_{21}(t)$ |
| **$L_{02}$** | $E_0 \leftrightarrow E_2$ | **Glissière** | Direction $\vec{z}_0$ (en $O_3$) | $1\text{ (0R, 1T)}$<br>$N_c = 5$ | **Torseur Couple** ($\vec{\Omega} = \vec{0}$) | $z_2(t)\,\vec{z}_0$ ($\dot{z}_2(t) = V_z(t)$) |
| **$L_{23}$** | $E_2 \leftrightarrow E_3$ | **Glissière** | Direction $\vec{x}_0$ (en $O_4$) | $1\text{ (0R, 1T)}$<br>$N_c = 5$ | **Torseur Couple** ($\vec{\Omega} = \vec{0}$) | $x_3(t)\,\vec{x}_0$ ($\dot{x}_3(t) = V_x(t)$) |
| **$L_{04}$** | $E_0 \leftrightarrow E_4$ | **Glissière** | Direction $\vec{y}_0$ (en $O_5$) | $1\text{ (0R, 1T)}$<br>$N_c = 5$ | **Torseur Couple** ($\vec{\Omega} = \vec{0}$) | $y_4(t)\,\vec{y}_0$ ($\dot{y}_4(t) = V_y(t)$) |

---

## 3. Analyse Détaillée et Écriture des Torseurs dans $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$

### 3.1. Liaison $L_{01}$ ($E_0 \leftrightarrow E_1$) : Liaison Pivot d'axe $(O_1, \vec{z}_0)$
- **Réalisation technologique :** Guidage en rotation assuré par les deux roulements rigides à billes internes du moteur pas-à-pas NEMA 17 de l'axe $Z$ (dont le stator est encastré sur le montant gauche de $E_0$), prolongé par le coupleur rigide fendu en aluminium vers la vis trapézoïdale $E_1$.
- **Degrés de liberté :** $N_s = 1$ en rotation ($\text{R}_{z_0}$), $N_c = 5$ degrés bloqués ($\forall P \in (O_1, \vec{z}_0), \vec{V}(P \in E_1/E_0) = \vec{0}$).
- **Torseur cinématique (Notations CM4 § 2.3) :**
  $$\{\mathcal{V}(E_1/E_0)\} = \begin{Bmatrix} \vec{\Omega}(E_1/E_0) \\ \vec{V}(O_1 \in E_1/E_0) \end{Bmatrix}_{O_1} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{10}(t) & 0 \end{Bmatrix}_{O_1, \mathcal{B}_0} = \left\{ \dot{\theta}_1(t)\,\vec{z}_0 \;;\; \vec{0} \right\}_{O_1}$$
  C'est un **torseur glisseur** dont l'axe central est la droite $(O_1, \vec{z}_0)$.

---

### 3.2. Liaison $L_{12}$ ($E_1 \leftrightarrow E_2$) : Liaison Hélicoïdale d'axe $(O_2, \vec{z}_0)$
- **Réalisation technologique :** Contact hélicoïdal entre la vis trapézoïdale Tr8x8 en acier inoxydable ($E_1$, 4 filets à droite, pas hélicoïdal $p_z = 8\text{ mm/tr}$) et l'écrou trapézoïdal en laiton fixé sur la platine gauche du portique ($E_2$).
- **Loi de conjugaison hélicoïdale intrinsèque (CM4 § 5.6) :**
  Pour un filetage à droite dans un repère direct $\mathcal{B}_0$ :
  $$v_{21}(t) = +\frac{p_z}{2\pi}\,\omega_{21}(t) \quad \iff \quad \vec{V}(O_2 \in E_2/E_1) = +\frac{p_z}{2\pi}\,\vec{\Omega}(E_2/E_1)$$
- **Torseur cinématique :**
  $$\{\mathcal{V}(E_2/E_1)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & v_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} = \left\{ \omega_{21}(t)\,\vec{z}_0 \;;\; +\frac{p_z}{2\pi}\,\omega_{21}(t)\,\vec{z}_0 \right\}_{O_2}$$
  C'est un **torseur hélicoïdal** d'automoment non nul $I = \vec{\Omega} \cdot \vec{V} = +\frac{p_z}{2\pi}\omega_{21}^2 \neq 0$.

---

### 3.3. Liaison $L_{02}$ ($E_0 \leftrightarrow E_2$) : Liaison Glissière de direction $\vec{z}_0$
- **Réalisation technologique :** Guidage prismatique bilatéral assuré par 6 galets V-wheels en POM (3 à gauche, 3 à droite avec excentriques de rattrapage de jeu) roulant dans les rainures des profilés verticaux du bâti $E_0$. Sur le schéma cinématique minimal, il est modélisé par **une unique liaison glissière équivalente** de centre $O_3$.
- **Propriété du champ des vitesses (Translation pure — CM4 § 5.1) :** $\vec{\Omega}(E_2/E_0) = \vec{0}$, donc le champ des vitesses est uniforme en tout point de l'espace.
- **Torseur cinématique :**
  $$\{\mathcal{V}(E_2/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & \dot{z}_2(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_z(t)\,\vec{z}_0 \right\}_{\forall P}$$
  C'est un **torseur couple**.

---

### 3.4. Liaison $L_{23}$ ($E_2 \leftrightarrow E_3$) : Liaison Glissière de direction $\vec{x}_0$
- **Réalisation technologique :** Guidage prismatique assuré par 3 galets V-wheels portés par le chariot de tête $E_3$ roulant dans le profilé horizontal du portique $E_2$.
- **Torseur cinématique :**
  $$\{\mathcal{V}(E_3/E_2)\} = \begin{Bmatrix} 0 & \dot{x}_3(t) \\ 0 & 0 \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_x(t)\,\vec{x}_0 \right\}_{\forall P}$$
  C'est un **torseur couple**.

---

### 3.5. Liaison $L_{04}$ ($E_0 \leftrightarrow E_4$) : Liaison Glissière de direction $\vec{y}_0$
- **Réalisation technologique :** Guidage prismatique assuré par 4 galets V-wheels sous le plateau chauffant $E_4$ roulant sur le rail central $Y$ du bâti $E_0$.
- **Torseur cinématique :**
  $$\{\mathcal{V}(E_4/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & \dot{y}_4(t) \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_y(t)\,\vec{y}_0 \right\}_{\forall P}$$
  C'est un **torseur couple**.
