# Graphe des Liaisons Normalisé et Fermeture Cinématique

**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI  
**Conformité :** Norme AFNOR NF EN ISO 3952 — Analyse topologique et cinématique des systèmes

![Graphe des liaisons normalisé de la Creality Ender 3](../04_schemas_cinematiques/graphe_des_liaisons.svg)

---

## 1. Analyse topologique de la structure cinématique

### 1.1. Décompte des sommets, des arcs et nombre cyclomatique $\gamma$
Le graphe des liaisons comporte :
- **$N = 5$ sommets** représentant les **5 classes d'équivalence cinématique** : $E_0, E_1, E_2, E_3, E_4$, dont chacune détaille explicitement ses pièces constitutives et son repère local associé ($\mathcal{R}_0$ à $\mathcal{R}_4$). Le bâti fixe $E_0$ est mis en valeur par un contour renforcé et le symbole normalisé de référence fixe ($\underline{\underline{\equiv\mkern-10mu\perp}}$).
- **$L = 5$ arcs** représentant les **5 liaisons élémentaires** : $L_{01}, L_{12}, L_{02}, L_{23}, L_{04}$, issues de **3 familles de liaisons distinctes** (Pivot, Hélicoïdale, Glissière).
- **Nombre cyclomatique $\gamma$ du graphe :**
  $$\gamma = L - N + 1 = 5 - 5 + 1 = 1$$

### 1.2. Décomposition en sous-chaînes cinématiques
La valeur $\gamma = 1$ traduit une **architecture cinématique hybride (série-parallèle)** composée de :
1. **Une chaîne fermée élémentaire ($\gamma = 1$) : Boucle d'élévation verticale $Z$ ($E_0 - E_1 - E_2 - E_0$)**  
   Elle transforme la rotation commandée de la vis mère $E_1$ (liaison Pivot $L_{01}$) en une translation verticale pure du portique $E_2$ (liaison Glissière $L_{02}$) par l'intermédiaire de la liaison Hélicoïdale $L_{12}$.
2. **Deux chaînes ouvertes indépendantes (structures séries) :**
   - **Branche transversale $X$ ($E_2 - E_3$) :** Liaison Glissière $L_{23}$ de direction $\vec{x}_0$ portée par le portique $E_2$, permettant à la tête d'impression $E_3$ de balayer la largeur du plateau tout en étant entraînée verticalement par $E_2$.
   - **Branche longitudinale $Y$ ($E_0 - E_4$) :** Liaison Glissière $L_{04}$ de direction $\vec{y}_0$ directement liée au bâti $E_0$, assurant le déplacement avant/arrière du plateau chauffant $E_4$ indépendamment du portique $(X, Z)$.

---

## 2. Fermeture cinématique de la boucle d'élévation $Z$ ($E_0 - E_1 - E_2 - E_0$)

Pour déterminer la loi d'entrée-sortie du mécanisme de montée/descente de l'axe $Z$, on écrit la **relation de composition des torseurs cinématiques** sur la chaîne fermée $E_0 \to E_1 \to E_2 \to E_0$ :
$$\{\mathcal{V}(E_2/E_0)\} = \{\mathcal{V}(E_2/E_1)\} + \{\mathcal{V}(E_1/E_0)\}$$

### 2.1. Choix du point de réduction commun
Les axes des liaisons Pivot $L_{01}$ et Hélicoïdale $L_{12}$ sont confondus selon la droite $(O_1, \vec{z}_0) = (O_2, \vec{z}_0)$, car l'arbre du moteur $Z$ et la vis trapézoïdale sont coaxiaux ($\overrightarrow{O_1 O_2} = z_2(t)\,\vec{z}_0$).  
Par ailleurs, la liaison $L_{02}$ étant une glissière de direction $\vec{z}_0$, le torseur $\{\mathcal{V}(E_2/E_0)\}$ est un **torseur couple** (son vecteur vitesse est uniforme en tout point de l'espace).  
On réduit donc les trois torseurs au même point **$O_2$** et dans la même base fixe **$\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$** :

1. **Transport de $\{\mathcal{V}(E_1/E_0)\}$ de $O_1$ en $O_2$ (formule de Varignon / équiprojectivité) :**
   $$\vec{V}(O_2 \in E_1/E_0) = \vec{V}(O_1 \in E_1/E_0) + \vec{\Omega}(E_1/E_0) \wedge \overrightarrow{O_1 O_2} = \vec{0} + \big(\omega_{10}(t)\,\vec{z}_0\big) \wedge \big(z_2(t)\,\vec{z}_0\big) = \vec{0}$$
   D'où :
   $$\{\mathcal{V}(E_1/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{10}(t) & 0 \end{Bmatrix}_{O_2, \mathcal{B}_0} \quad \text{avec } \omega_{10}(t) = \dot{\theta}_1(t)$$

2. **Torseur de la liaison Hélicoïdale $L_{12}$ en $O_2$ (filetage à droite, pas $p_z = 8\text{ mm/tr}$) :**
   $$\{\mathcal{V}(E_2/E_1)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & v_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} \quad \text{avec } v_{21}(t) = +\frac{p_z}{2\pi}\,\omega_{21}(t)$$

3. **Torseur de la liaison Glissière $L_{02}$ en $O_2$ :**
   $$\{\mathcal{V}(E_2/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} \quad \text{avec } V_z(t) = \dot{z}_2(t)$$

### 2.2. Système d'équations scalaires et loi d'entrée-sortie
L'égalité des éléments de réduction en $O_2$ donne :
$$\begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) + \omega_{10}(t) & v_{21}(t) + 0 \end{Bmatrix}_{O_2, \mathcal{B}_0}$$

En projetant sur l'axe $\vec{z}_0$, les deux équations non triviales sont :
$$\begin{cases}
\text{Équation de résultante (rotation selon } \vec{z}_0\text{) :} & 0 = \omega_{21}(t) + \omega_{10}(t) \quad \Longrightarrow \quad \omega_{21}(t) = -\omega_{10}(t) \\[6pt]
\text{Équation de moment (vitesse selon } \vec{z}_0\text{) :} & V_z(t) = v_{21}(t) = +\dfrac{p_z}{2\pi}\,\omega_{21}(t)
\end{cases}$$

En substituant $\omega_{21}(t) = -\omega_{10}(t)$, on obtient la **loi d'entrée-sortie cinématique** du système vis-écrou $Z$ :
$$\boxed{V_z(t) = \dot{z}_2(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t) = -\frac{p_z}{2\pi}\,\dot{\theta}_1(t) = +\frac{p_z}{2\pi}\,\omega_m(t)}$$
où $\omega_m(t) = -\omega_{10}(t)$ désigne la vitesse angulaire motrice dans le sens d'élévation du portique (sens horaire de la vis vue de dessus).

- **Application numérique (Creality Ender 3) :**  
  Pour un pas hélicoïdal $p_z = 8\text{ mm/tr}$ :
  - Un tour complet du moteur $Z$ ($\Delta\theta_m = 2\pi\text{ rad}$) élève le portique $E_2$ de $\Delta z_2 = 8{,}0\text{ mm}$.
  - Avec un moteur NEMA 17 de $200\text{ pas/tr}$ piloté en micropas $1/16$ ($3200\text{ micropas/tr}$, soit $400\text{ micropas/mm}$), la résolution verticale théorique est de $\delta z = \dfrac{8\text{ mm}}{3200} = 2{,}5\text{ }\mu\text{m}$.

---

## 3. Loi de vitesse relative globale de dépôt du filament ($E_3 / E_4$)

Pour piloter l'impression 3D, le G-code commande la vitesse du point d'extrusion de la buse ($O_4 \in E_3$) par rapport au plateau d'impression ($E_4$). Par composition des mouvements le long de la chaîne cinématique ouverte reliant $E_4$ à $E_3$ via $E_0$ et $E_2$ :
$$\{\mathcal{V}(E_3/E_4)\} = \{\mathcal{V}(E_3/E_2)\} + \{\mathcal{V}(E_2/E_0)\} + \{\mathcal{V}(E_0/E_4)\} = \{\mathcal{V}(E_3/E_2)\} + \{\mathcal{V}(E_2/E_0)\} - \{\mathcal{V}(E_4/E_0)\}$$

Les trois mouvements étant des translations pures de directions deux à deux orthogonales ($\vec{x}_0, \vec{z}_0, \vec{y}_0$), le mouvement de la tête $E_3$ par rapport au plateau $E_4$ est une **translation spatiale à 3 degrés de liberté indépendants** ($\vec{\Omega}(E_3/E_4) = \vec{0}$) dont le torseur cinématique s'écrit en tout point $P$ :
$$\boxed{\{\mathcal{V}(E_3/E_4)\} = \begin{Bmatrix} 0 & V_x(t) \\ 0 & -V_y(t) \\ 0 & V_z(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \begin{Bmatrix} 0 & \dot{x}_3(t) \\ 0 & -\dot{y}_4(t) \\ 0 & +\dfrac{p_z}{2\pi}\,\omega_m(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0}}$$
