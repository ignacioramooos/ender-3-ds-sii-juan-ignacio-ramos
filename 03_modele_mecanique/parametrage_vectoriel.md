# Paramétrage Géométrique et Cinématique Vectoriel (CPGE MPSI)

---

## 1. Définition du Repère Principal $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié au Bâti $E_0$

Le repère de référence $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ est choisi **orthonormé direct** ($\vec{x}_0 \wedge \vec{y}_0 = \vec{z}_0$) et rigidement lié au bâti fixe $E_0$ :

* **Origine $O_0$ :** Intersection de l'axe médian longitudinal du profilé central de guidage Y ($E_0$) et du plan vertical contenant les axes des montants verticaux Z ($E_0$).
* **Axe $(O_0, \vec{x}_0)$ :** Horizontal transversal, dirigé **de la gauche vers la droite** (face à la machine), colinéaire à la traverse du portique X ($E_2$).
* **Axe $(O_0, \vec{z}_0)$ :** Vertical **ascendant**, colinéaire à l'axe de la vis trapézoïdale Tr8x8 ($E_1$) et aux rainures des montants verticaux 2040 ($E_0$).
* **Axe $(O_0, \vec{y}_0)$ :** Horizontal longitudinal, imposé par la règle du trièdre direct $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$, dirigé **de l'avant vers l'arrière** de la machine, colinéaire au rail central de guidage Y ($E_0$).

---

## 2. Centres Géométriques $O_1$ à $O_5$ et Paramètres Cinématiques

Le graphe des liaisons comporte exactement **5 liaisons élémentaires** :
- Une boucle cinématique fermée d'élévation Z ($E_0 - E_1 - E_2 - E_0$) associant $O_1, O_2, O_3$.
- Deux chaînes cinématiques ouvertes orthogonales de centres $O_4$ ($E_2 - E_3$) et $O_5$ ($E_0 - E_4$).

| Centre | Liaison associée | Classes reliées | Nature et caractéristiques | Repère local associé | Paramètre cinématique |
| :---: | :---: | :---: | :--- | :--- | :--- |
| **$O_1$** | $L_{01}$ | $E_0$ (Noir) / $E_1$ (Bleu) | **Pivot** d'axe $(O_1, \vec{z}_0)$ | $\mathcal{R}_1(O_1, \vec{x}_1, \vec{y}_1, \vec{z}_0)$ lié à $E_1$ | Angle $\theta_1(t) = (\vec{x}_0, \vec{x}_1) = (\vec{y}_0, \vec{y}_1)$ |
| **$O_2$** | $L_{12}$ | $E_1$ (Bleu) / $E_2$ (Rouge) | **Hélicoïdale** d'axe $(O_2, \vec{z}_0) = (O_1, \vec{z}_0)$, pas $p_z = 8\text{ mm/tr}$ | $\mathcal{R}_2(O_3, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié à $E_2$ | Couplage : $z(t) = \dfrac{p_z}{2\pi}\,\theta_1(t)$ |
| **$O_3$** | $L_{02}$ | $E_0$ (Noir) / $E_2$ (Rouge) | **Glissière** de direction $\vec{z}_0$ | $\mathcal{R}_2(O_3, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié à $E_2$ | Translation verticale $z(t)$ selon $\vec{z}_0$ |
| **$O_4$** | $L_{23}$ | $E_2$ (Rouge) / $E_3$ (Vert) | **Glissière** de direction $\vec{x}_0$ | $\mathcal{R}_3(O_4, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié à $E_3$ | Translation transversale $x(t)$ selon $\vec{x}_0$ |
| **$O_5$** | $L_{04}$ | $E_0$ (Noir) / $E_4$ (Orange) | **Glissière** de direction $\vec{y}_0$ | $\mathcal{R}_4(O_5, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié à $E_4$ | Translation longitudinale $y(t)$ selon $\vec{y}_0$ |

---

## 3. Définition Vectorielle Complète des Centres

1. **En $O_1$ (Liaison Pivot $E_0/E_1$) :**
   $$\overrightarrow{O_0 O_1} = -L_x\,\vec{x}_0 + h_1\,\vec{z}_0 \quad (L_x, h_1 \text{ constantes géométriques de } E_0)$$
   * Base mobile $\mathcal{R}_1(O_1, \vec{x}_1, \vec{y}_1, \vec{z}_0)$ :
     $$\vec{x}_1 = \cos\theta_1(t)\,\vec{x}_0 + \sin\theta_1(t)\,\vec{y}_0 \quad \text{et} \quad \vec{y}_1 = -\sin\theta_1(t)\,\vec{x}_0 + \cos\theta_1(t)\,\vec{y}_0$$
   * Vecteur rotation instantané :
     $$\vec{\Omega}(E_1/E_0) = \dot{\theta}_1(t)\,\vec{z}_0$$

2. **En $O_2$ (Liaison Hélicoïdale $E_1/E_2$) :**
   $$\overrightarrow{O_1 O_2} = z(t)\,\vec{z}_0 \quad \Longleftrightarrow \quad \overrightarrow{O_0 O_2} = -L_x\,\vec{x}_0 + \big(h_1 + z(t)\big)\,\vec{z}_0$$
   * Comme $E_2$ est en translation pure par rapport à $E_0$, $\vec{\Omega}(E_2/E_1) = -\dot{\theta}_1(t)\,\vec{z}_0$.
   * Loi de conjugaison hélicoïdale (pas à droite $p_z = 8\text{ mm/tr}$) :
     $$z(t) = \frac{p_z}{2\pi}\,\theta_1(t) \quad \text{et} \quad \dot{z}(t) = \frac{p_z}{2\pi}\,\dot{\theta}_1(t)$$

3. **En $O_3$ (Liaison Glissière $E_0/E_2$) :**
   $$\overrightarrow{O_2 O_3} = L_x\,\vec{x}_0 \quad \Longrightarrow \quad \overrightarrow{O_0 O_3} = \big(h_1 + z(t)\big)\,\vec{z}_0$$
   * $\vec{\Omega}(E_2/E_0) = \vec{0}$ et $\vec{V}(O_3 \in E_2/E_0) = \dot{z}(t)\,\vec{z}_0$.

4. **En $O_4$ (Liaison Glissière $E_2/E_3$) :**
   $$\overrightarrow{O_3 O_4} = x(t)\,\vec{x}_0 + d_y\,\vec{y}_0 \quad (d_y \text{ déport transversal constant selon } \vec{y}_0)$$
   * $\vec{V}(O_4 \in E_3/E_2) = \dot{x}(t)\,\vec{x}_0$.

5. **En $O_5$ (Liaison Glissière $E_0/E_4$) :**
   $$\overrightarrow{O_0 O_5} = y(t)\,\vec{y}_0 + h_5\,\vec{z}_0 \quad (h_5 \text{ hauteur constante du guidage Y})$$
   * $\vec{V}(O_5 \in E_4/E_0) = \dot{y}(t)\,\vec{y}_0$.

---

## 4. Fermeture Géométrique Buse / Plateau (Point d'Impression)

En notant $O_4$ le point d'extrusion de la buse (à une constante géométrique près), la position relative de la buse ($E_3$) par rapport au plateau d'impression ($E_4$) s'exprime dans la base fixe $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ :

$$\overrightarrow{O_5 O_4} = \overrightarrow{O_5 O_0} + \overrightarrow{O_0 O_3} + \overrightarrow{O_3 O_4}$$

$$\boxed{\overrightarrow{O_5 O_4} = x(t)\,\vec{x}_0 + \big(d_y - y(t)\big)\,\vec{y}_0 + \left(h_1 - h_5 + \frac{p_z}{2\pi}\,\theta_1(t)\right)\,\vec{z}_0}$$

> **Structure cinématique :**
> - L'axe X et l'axe Z sont en **chaîne série** ($E_0 \to E_2 \to E_3$) : le déplacement en élévation Z du portique $E_2$ translate simultanément la tête $E_3$.
> - L'axe Y est sur une **chaîne cinématique parallèle indépendante** ($E_0 \to E_4$).
