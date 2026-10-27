# Répertoire des Liaisons Mécaniques et Torseurs Cinématiques

**Système étudié :** Imprimante 3D Creality Ender 3  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI (Lycée Stanislas Cannes)  
**Professeur :** Mme M. Prot

---

## 1. Structure d'un Torseur Cinématique et Transport

Un torseur cinématique $\{\mathcal{V}(S_j/S_i)\}$ est constitué de :
1. **La Résultante $\vec{\Omega}(S_j/S_i)$ :** Vecteur vitesse instantanée de rotation de $S_j$ par rapport à $S_i$.
2. **Le Moment $\vec{V}(P \in S_j/S_i)$ :** Vecteur vitesse instantanée au point $P$.

Pour transporter un torseur d'un point $A$ à un point $B$, on applique la **formule de Varignon** :
$$\vec{V}(B \in S_j/S_i) = \vec{V}(A \in S_j/S_i) + \overrightarrow{BA} \wedge \vec{\Omega}(S_j/S_i)$$

---

## 2. Synthèse des 5 Liaisons de la Creality Ender 3

| Code | Sous-ensembles reliés | Famille | Caractéristique géométrique | DDL ($N_s / N_c$) | Paramètre cinématique |
| :--- | :---: | :--- | :--- | :---: | :--- |
| **$L_{01}$** | Châssis fixe $\leftrightarrow$ Vis centrale | **Pivot** | Axe $(O_1, \vec{z}_0)$ | $1\text{ (1R, 0T)}$ • $N_c = 5$ | $\theta_1(t) = (\widehat{\vec{x}_0, \vec{x}_1})$ |
| **$L_{12}$** | Vis centrale $\leftrightarrow$ Traverse horizontale | **Hélicoïdale** | Axe $(O_2, \vec{z}_0)$, pas $p_z = 8\text{ mm/tr}$ (filet à droite) | $1\text{ couplé}$ • $N_c = 5$ | $\omega_{21}(t)$ et $v_{21}(t) = +\frac{p_z}{2\pi}\omega_{21}(t)$ |
| **$L_{02}$** | Châssis fixe $\leftrightarrow$ Traverse horizontale | **Glissière** | Direction $\vec{z}_0$ (en $O_3$) | $1\text{ (0R, 1T)}$ • $N_c = 5$ | $z_2(t)\,\vec{z}_0$ ($\dot{z}_2(t) = V_z(t)$) |
| **$L_{23}$** | Traverse horizontale $\leftrightarrow$ Chariot tête extrudeur | **Glissière** | Direction $\vec{x}_0$ (en $O_4$) | $1\text{ (0R, 1T)}$ • $N_c = 5$ | $x_3(t)\,\vec{x}_0$ ($\dot{x}_3(t) = V_x(t)$) |
| **$L_{04}$** | Châssis fixe $\leftrightarrow$ Plateau mobile | **Glissière** | Direction $\vec{y}_0$ (en $O_5$) | $1\text{ (0R, 1T)}$ • $N_c = 5$ | $y_4(t)\,\vec{y}_0$ ($\dot{y}_4(t) = V_y(t)$) |

---

## 3. Écriture des Torseurs Cinématiques dans $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$

### 3.1. Liaison $L_{01}$ (Châssis fixe $\leftrightarrow$ Vis centrale) : Liaison Pivot d'axe $(O_1, \vec{z}_0)$
$$\{\mathcal{V}(\text{Vis}/\text{Châssis})\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{10}(t) & 0 \end{Bmatrix}_{O_1, \mathcal{B}_0} = \left\{ \dot{\theta}_1(t)\,\vec{z}_0 \;;\; \vec{0} \right\}_{O_1}$$

### 3.2. Liaison $L_{12}$ (Vis centrale $\leftrightarrow$ Traverse horizontale) : Liaison Hélicoïdale d'axe $(O_2, \vec{z}_0)$
$$\{\mathcal{V}(\text{Traverse}/\text{Vis})\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & v_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} = \left\{ \omega_{21}(t)\,\vec{z}_0 \;;\; +\frac{p_z}{2\pi}\,\omega_{21}(t)\,\vec{z}_0 \right\}_{O_2}$$

### 3.3. Liaison $L_{02}$ (Châssis fixe $\leftrightarrow$ Traverse horizontale) : Liaison Glissière de direction $\vec{z}_0$
$$\{\mathcal{V}(\text{Traverse}/\text{Châssis})\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & \dot{z}_2(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_z(t)\,\vec{z}_0 \right\}_{\forall P}$$

### 3.4. Liaison $L_{23}$ (Traverse horizontale $\leftrightarrow$ Chariot tête extrudeur) : Liaison Glissière de direction $\vec{x}_0$
$$\{\mathcal{V}(\text{Chariot}/\text{Traverse})\} = \begin{Bmatrix} 0 & \dot{x}_3(t) \\ 0 & 0 \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_x(t)\,\vec{x}_0 \right\}_{\forall P}$$

### 3.5. Liaison $L_{04}$ (Châssis fixe $\leftrightarrow$ Plateau mobile) : Liaison Glissière de direction $\vec{y}_0$
$$\{\mathcal{V}(\text{Plateau}/\text{Châssis})\} = \begin{Bmatrix} 0 & 0 \\ 0 & \dot{y}_4(t) \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_y(t)\,\vec{y}_0 \right\}_{\forall P}$$
