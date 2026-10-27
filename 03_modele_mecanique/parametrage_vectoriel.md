# Paramétrage Géométrique, Repères Locaux ($\mathcal{R}_0$ à $\mathcal{R}_4$) et Chaîne des Centres

**Système étudié :** Imprimante 3D Creality Ender 3  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI (Lycée Stanislas Cannes)  
**Professeur :** Mme M. Prot

![Figure plane de changement de base et chaîne vectorielle des centres](../04_schemas_cinematiques/figures_parametrage_angles.svg)

---

## 1. Définition du Repère Global $\mathcal{R}_0$ et des Repères Locaux $\mathcal{R}_1$ à $\mathcal{R}_4$

On associe à chacun des 5 sous-ensembles cinématiques un **repère local orthonormé direct** $\mathcal{R}_k(O_{k}, \vec{x}_k, \vec{y}_k, \vec{z}_k)$ :

### 1.1. Repère global de référence $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié au Châssis fixe
- **Origine $O_0$ :** Point fixe appartenant au Châssis fixe, situé à la base médiane du rail $Y$.
- **Base orthonormée directe $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ :**
  - $\vec{x}_0$ : vecteur unitaire horizontal transversal, dirigé de la **gauche vers la droite** (en regardant l'imprimante de face).
  - $\vec{z}_0$ : vecteur unitaire **vertical ascendant**, colinéaire aux montants $Z$ et à l'axe de la Vis centrale.
  - $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ : vecteur unitaire horizontal longitudinal (profondeur), dirigé de **l'avant vers l'arrière** de l'imprimante, colinéaire au rail central du Plateau mobile.
  - En projection frontale dans le plan $(O_0, \vec{x}_0, \vec{z}_0)$ ($\vec{x}_0$ vers la droite, $\vec{z}_0$ vers le haut), le vecteur $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ est **entrant dans la feuille** ($\otimes\,\vec{y}_0$).

### 1.2. Repères locaux attachés aux sous-ensembles

| Sous-ensemble | Repère local lié | Origine géométrique | Base vectorielle liée | Nature du mouvement / $\mathcal{R}_0$ |
| :--- | :--- | :--- | :--- | :--- |
| **Châssis fixe** | $\mathcal{R}_0(O_0, \mathcal{B}_0)$ | $O_0$ (base du rail $Y$) | $\mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Référence fixe ($\underline{\underline{\equiv\mkern-10mu\perp}}$) |
| **Vis centrale** | $\mathcal{R}_1(O_1, \mathcal{B}_1)$ | $O_1$ : centre du coupleur $Z$ (liaison $L_{01}$) | $\mathcal{B}_1 = (\vec{x}_1, \vec{y}_1, \vec{z}_0)$ tournante | Rotation d'angle $\theta_1(t)$ autour de $(O_1, \vec{z}_0)$ |
| **Traverse horizontale** | $\mathcal{R}_2(O_3, \mathcal{B}_2)$ | $O_3$ : centre du guidage vertical $Z$ ($L_{02}$) | $\mathcal{B}_2 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation rectiligne verticale $z_2(t)\,\vec{z}_0$ |
| **Chariot tête extrudeur** | $\mathcal{R}_3(O_4, \mathcal{B}_3)$ | $O_4$ : centre du chariot $X$ / buse ($L_{23}$) | $\mathcal{B}_3 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation horizontale $x_3(t)\,\vec{x}_0$ / $\mathcal{R}_2$ |
| **Plateau mobile** | $\mathcal{R}_4(O_5, \mathcal{B}_4)$ | $O_5$ : centre du chariot plateau $Y$ ($L_{04}$) | $\mathcal{B}_4 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation longitudinale $y_4(t)\,\vec{y}_0$ / $\mathcal{R}_0$ |

---

## 2. Figure Plane de Changement de Base ($\mathcal{B}_0 \to \mathcal{B}_1$) & Formule de Bour

La rotation de la Vis centrale par rapport au Châssis fixe autour de l'axe vertical $(O_1, \vec{z}_0)$ est paramétrée par l'angle orienté :
$$\theta_1(t) = \left(\widehat{\vec{x}_0, \vec{x}_1}\right) = \left(\widehat{\vec{y}_0, \vec{y}_1}\right) \quad \text{autour de } \vec{z}_0 = \vec{z}_1 \text{ (sortant } \odot \text{ en vue de dessus)}$$

- **Relations géométriques de projection directe :**
  $$\begin{cases}
  \vec{x}_1 = \cos\theta_1(t)\,\vec{x}_0 + \sin\theta_1(t)\,\vec{y}_0 \\
  \vec{y}_1 = -\sin\theta_1(t)\,\vec{x}_0 + \cos\theta_1(t)\,\vec{y}_0 \\
  \vec{z}_1 = \vec{z}_0
  \end{cases}$$

- **Vecteur vitesse instantanée de rotation de la Vis centrale :**
  $$\vec{\Omega}(\text{Vis}/\text{Châssis}) = \dot{\theta}_1(t)\,\vec{z}_0 = \omega_{10}(t)\,\vec{z}_0$$

---

## 3. Paramétrage des Centres Géométriques des Liaisons ($O_1$ à $O_5$)

1. **Centre $O_1$ de la liaison Pivot $L_{01}$ (Châssis fixe — Vis centrale) :**  
   $$\overrightarrow{O_0 O_1} = -L_x\,\vec{x}_0 + h_1\,\vec{z}_0$$
2. **Centre $O_2$ de la liaison Hélicoïdale $L_{12}$ (Vis centrale — Traverse horizontale) :**  
   $$\overrightarrow{O_1 O_2} = z_2(t)\,\vec{z}_0 \quad \Longrightarrow \quad \overrightarrow{O_0 O_2} = -L_x\,\vec{x}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$$
3. **Centre $O_3$ de la liaison Glissière $L_{02}$ (Châssis fixe — Traverse horizontale) :**  
   $$\overrightarrow{O_0 O_3} = \overrightarrow{O_0 O_2} + \overrightarrow{O_2 O_3} = \big(h_1 + z_2(t)\big)\,\vec{z}_0$$
4. **Centre $O_4$ de la liaison Glissière $L_{23}$ (Traverse horizontale — Chariot tête extrudeur) :**  
   $$\overrightarrow{O_3 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 \quad \Longrightarrow \quad \overrightarrow{O_0 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$$
5. **Centre $O_5$ de la liaison Glissière $L_{04}$ (Châssis fixe — Plateau mobile) :**  
   $$\overrightarrow{O_0 O_5} = y_4(t)\,\vec{y}_0 + h_5\,\vec{z}_0$$

---

## 4. Fermeture Géométrique : Vecteur Buse / Plateau ($\overrightarrow{O_5 O_4}$)

Par la relation de Chasles sur la chaîne des centres :
$$\overrightarrow{O_5 O_4} = -\overrightarrow{O_0 O_5} + \overrightarrow{O_0 O_3} + \overrightarrow{O_3 O_4} = x_3(t)\,\vec{x}_0 + \big(d_y - y_4(t)\big)\,\vec{y}_0 + \big(h_1 - h_5 + z_2(t)\big)\,\vec{z}_0$$

Par dérivation vectorielle dans la base $\mathcal{B}_0$ :
$$\boxed{\vec{V}(O_4 \in \text{Chariot} / \text{Plateau}) = \dot{x}_3(t)\,\vec{x}_0 - \dot{y}_4(t)\,\vec{y}_0 + \dot{z}_2(t)\,\vec{z}_0}$$
