# 1. Caractérisation des 5 Liaisons et Torseurs Cinématiques (NF EN ISO 3952)

Ce document formalise les 5 liaisons mécaniques de l'imprimante 3D Creality Ender 3 conformément aux exigences formelles des épreuves de Sciences Industrielles de l'Ingénieur (SII) aux concours CPGE.

---

## Rappel du Formalisme Adopté

On note $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ le repère lié au bâti fixe $E_0$ et $\mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ sa base orthonormée directe associée. Le torseur cinématique du mouvement du solide $E_j$ par rapport au solide $E_i$, réduit en un point caractéristique $P$ et exprimé dans la base $\mathcal{B}_0$, est noté sous forme matricielle à 6 composantes (colonne résultante $\vec{\Omega}(E_j/E_i)$ à gauche, colonne moment $\vec{V}(P, E_j/E_i)$ à droite) :

$$\{\mathcal{V}(E_j/E_i)\} = \begin{Bmatrix} \vec{\Omega}(E_j/E_i) \\ \vec{V}(P, E_j/E_i) \end{Bmatrix}_{P} = \begin{Bmatrix} \omega_x & v_x \\ \omega_y & v_y \\ \omega_z & v_z \end{Bmatrix}_{P, \mathcal{B}_0}$$

---

## Tableau Synthétique des Degrés de Liberté (dans $\mathcal{B}_0$)

| Liaison | Classes reliées | Nature et géométrie | $T_x$ | $T_y$ | $T_z$ | $R_x$ | $R_y$ | $R_z$ | Mobilités indépendantes ($N_{\text{ddl}}$) |
| :---: | :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **$L_{01}$** | $E_0$ et $E_1$ | **Pivot** d'axe $(O_1, \vec{z}_0)$ | $0$ | $0$ | $0$ | $0$ | $0$ | **$1$** | **$1$** |
| **$L_{12}$** | $E_1$ et $E_2$ | **Hélicoïdale** d'axe $(O_2, \vec{z}_0)$, pas $p_z$ | $0$ | $0$ | **$1^*$** | $0$ | $0$ | **$1^*$** | **$1$** *(couplage $T_z \leftrightarrow R_z$)* |
| **$L_{02}$** | $E_0$ et $E_2$ | **Glissière** de direction $\vec{z}_0$ en $O_3$ | $0$ | $0$ | **$1$** | $0$ | $0$ | $0$ | **$1$** |
| **$L_{23}$** | $E_2$ et $E_3$ | **Glissière** de direction $\vec{x}_0$ en $O_4$ | **$1$** | $0$ | $0$ | $0$ | $0$ | $0$ | **$1$** |
| **$L_{04}$** | $E_0$ et $E_4$ | **Glissière** de direction $\vec{y}_0$ en $O_5$ | $0$ | **$1$** | $0$ | $0$ | $0$ | $0$ | **$1$** |

*(Note de rigueur pour $L_{12}$ : les composantes $T_z = 1^*$ et $R_z = 1^*$ sont toutes deux non nulles mais liées par la relation de conjugaison des filets ; la liaison hélicoïdale ne possède donc qu'**un seul degré de liberté indépendant**).*

---

## Écriture Formelle des 5 Torseurs Cinématiques dans la Base $\mathcal{B}_0$

### 1. Liaison $L_{01}$ : Pivot d'axe $(O_1, \vec{z}_0)$ entre le bâti $E_0$ et la vis $E_1$
* **Degrés de liberté :** $(T_x, T_y, T_z, R_x, R_y, R_z) = (0, 0, 0, 0, 0, 1)$.
* **Paramètre cinématique :** $\omega_m(t) = \dot{\theta}_m(t)$ désigne la vitesse angulaire de rotation de la vis-mère (et de l'arbre du moteur pas-à-pas Z) par rapport au bâti.
* **Torseur cinématique en $O_1$ :**
  $$\{\mathcal{V}(E_1/E_0)\} = \begin{Bmatrix} \vec{\Omega}(E_1/E_0) = \omega_m(t)\,\vec{z}_0 \\ \vec{V}(O_1, E_1/E_0) = \vec{0} \end{Bmatrix}_{O_1} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_m(t) & 0 \end{Bmatrix}_{O_1, \mathcal{B}_0}$$

---

### 2. Liaison $L_{12}$ : Hélicoïdale d'axe $(O_2, \vec{z}_0)$ entre la vis $E_1$ et le portique $E_2$
* **Degrés de liberté :** $(T_x, T_y, T_z, R_x, R_y, R_z) = (0, 0, 1, 0, 0, 1)$ avec la relation de couplage hélicoïdal de pas $p_z = 8\text{ mm/tr}$ :
  $$v_{21}(t) = -\frac{p_z}{2\pi}\,\omega_{21}(t)$$
  *(Remarque sur la convention de signe : la vis trapézoïdale T8 possède un filetage à droite. En orientant $\omega_m(t)$ positivement dans le sens qui fait monter le portique $E_2$ suivant $+\vec{z}_0$, une rotation de la vis de $+\omega_m\,\vec{z}_0$ par rapport à l'écrou non tournant correspond à $\omega_{21} = -\omega_m$, d'où le signe moins dans la relation locale de $E_2/E_1$ permettant d'obtenir une élévation positive).*
* **Torseur cinématique en $O_2$ :**
  $$\{\mathcal{V}(E_2/E_1)\} = \begin{Bmatrix} \vec{\Omega}(E_2/E_1) = \omega_{21}(t)\,\vec{z}_0 \\ \vec{V}(O_2, E_2/E_1) = v_{21}(t)\,\vec{z}_0 \end{Bmatrix}_{O_2} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & -\dfrac{p_z}{2\pi}\,\omega_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0}$$

---

### 3. Liaison $L_{02}$ : Glissière de direction $\vec{z}_0$ en $O_3$ entre le bâti $E_0$ et le portique $E_2$
* **Degrés de liberté :** $(T_x, T_y, T_z, R_x, R_y, R_z) = (0, 0, 1, 0, 0, 0)$.
* **Paramètre cinématique :** $V_z(t) = \dot{z}_2(t)$ désigne la vitesse linéaire d'élévation verticale du portique par rapport au bâti.
* **Torseur cinématique en $O_3$ :**
  $$\{\mathcal{V}(E_2/E_0)\} = \begin{Bmatrix} \vec{\Omega}(E_2/E_0) = \vec{0} \\ \vec{V}(O_3, E_2/E_0) = V_z(t)\,\vec{z}_0 \end{Bmatrix}_{O_3} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{O_3, \mathcal{B}_0}$$

---

### 4. Liaison $L_{23}$ : Glissière de direction $\vec{x}_0$ en $O_4$ entre le portique $E_2$ et la tête $E_3$
* **Degrés de liberté :** $(T_x, T_y, T_z, R_x, R_y, R_z) = (1, 0, 0, 0, 0, 0)$.
* **Paramètre cinématique :** $V_x(t) = \dot{x}_3(t)$ désigne la vitesse de translation horizontale du chariot porte-buse par rapport au portique $E_2$.
* **Torseur cinématique en $O_4$ :**
  $$\{\mathcal{V}(E_3/E_2)\} = \begin{Bmatrix} \vec{\Omega}(E_3/E_2) = \vec{0} \\ \vec{V}(O_4, E_3/E_2) = V_x(t)\,\vec{x}_0 \end{Bmatrix}_{O_4} = \begin{Bmatrix} 0 & V_x(t) \\ 0 & 0 \\ 0 & 0 \end{Bmatrix}_{O_4, \mathcal{B}_0}$$

---

### 5. Liaison $L_{04}$ : Glissière de direction $\vec{y}_0$ en $O_5$ entre le bâti $E_0$ et le plateau $E_4$
* **Degrés de liberté :** $(T_x, T_y, T_z, R_x, R_y, R_z) = (0, 1, 0, 0, 0, 0)$.
* **Paramètre cinématique :** $V_y(t) = \dot{y}_4(t)$ désigne la vitesse de translation longitudinale du plateau chauffant par rapport au bâti $E_0$.
* **Torseur cinématique en $O_5$ :**
  $$\{\mathcal{V}(E_4/E_0)\} = \begin{Bmatrix} \vec{\Omega}(E_4/E_0) = \vec{0} \\ \vec{V}(O_5, E_4/E_0) = V_y(t)\,\vec{y}_0 \end{Bmatrix}_{O_5} = \begin{Bmatrix} 0 & 0 \\ 0 & V_y(t) \\ 0 & 0 \end{Bmatrix}_{O_5, \mathcal{B}_0}$$
