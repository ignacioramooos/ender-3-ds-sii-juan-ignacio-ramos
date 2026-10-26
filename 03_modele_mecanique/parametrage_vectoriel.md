# Paramétrage Géométrique, Repères Locaux ($\mathcal{R}_0$ à $\mathcal{R}_4$) et Chaîne des Centres

**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI  
**Conformité :** Programme officiel MPSI — Paramétrage des mécanismes et fermeture géométrique

![Figure plane de changement de base et chaîne vectorielle des centres](../04_schemas_cinematiques/figures_parametrage_angles.svg)

---

## 1. Définition du repère de référence $\mathcal{R}_0$ et des repères locaux $\mathcal{R}_1, \mathcal{R}_2, \mathcal{R}_3, \mathcal{R}_4$

Conformément à la consigne de la Partie III (*« Paramétrez votre système en y ajoutant les repères locaux nécessaires »*), on associe à chaque classe d'équivalence cinématique $E_k$ ($k \in \{0, 1, 2, 3, 4\}$) un **repère local orthonormé direct** $\mathcal{R}_k(O_{k}, \vec{x}_k, \vec{y}_k, \vec{z}_k)$ :

### 1.1. Repère global de référence $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié au bâti fixe $E_0$
- **Origine $O_0$ :** Point fixe appartenant au bâti $E_0$, situé à l'intersection de l'axe longitudinal médian du rail $Y$ ($40\times 40\text{ mm}$) et du plan frontal contenant les axes des deux montants verticaux $Z$ ($20\times 40\text{ mm}$).
- **Base orthonormée directe $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ :**
  - $\vec{x}_0$ : vecteur unitaire horizontal transversal, dirigé de la **gauche vers la droite** (en regardant l'imprimante de face), colinéaire au profilé du portique $X$.
  - $\vec{z}_0$ : vecteur unitaire **vertical ascendant**, colinéaire aux deux montants $Z$ et à l'axe de la vis mère trapézoïdale.
  - $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ : vecteur unitaire horizontal longitudinal (profondeur), dirigé de **l'avant vers l'arrière** de l'imprimante, colinéaire au rail central du plateau $Y$.
  - **Vérification du caractère direct :** $\vec{x}_0 \wedge \vec{y}_0 = \vec{z}_0$, $\vec{y}_0 \wedge \vec{z}_0 = \vec{x}_0$ et $\vec{z}_0 \wedge \vec{x}_0 = \vec{y}_0$. En projection frontale dans le plan $(O_0, \vec{x}_0, \vec{z}_0)$ ($\vec{x}_0$ vers la droite, $\vec{z}_0$ vers le haut), le vecteur $\vec{y}_0$ est donc **entrant dans la feuille** (noté $\otimes\,\vec{y}_0$).

### 1.2. Repères locaux attachés aux solides mobiles ($E_1, E_2, E_3, E_4$)

| Solide | Repère local lié | Origine géométrique | Base vectorielle liée | Nature du mouvement / $\mathcal{R}_0$ |
| :--- | :--- | :--- | :--- | :--- |
| **$E_0$** | $\mathcal{R}_0(O_0, \mathcal{B}_0)$ | $O_0 \in E_0$ (base du rail $Y$) | $\mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Référence fixe |
| **$E_1$** | $\mathcal{R}_1(O_1, \mathcal{B}_1)$ | $O_1$ : centre du coupleur $Z$ (liaison $L_{01}$) | $\mathcal{B}_1 = (\vec{x}_1, \vec{y}_1, \vec{z}_1)$ avec $\vec{z}_1 = \vec{z}_0$ | Rotation d'angle $\theta_1(t)$ autour de $(O_1, \vec{z}_0)$ |
| **$E_2$** | $\mathcal{R}_2(O_3, \mathcal{B}_2)$ | $O_3$ : centre du guidage vertical $Z$ ($L_{02}$) | $\mathcal{B}_2 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation rectiligne verticale $z_2(t)\,\vec{z}_0$ |
| **$E_3$** | $\mathcal{R}_3(O_4, \mathcal{B}_3)$ | $O_4$ : centre du chariot $X$ / buse ($L_{23}$) | $\mathcal{B}_3 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation horizontale $x_3(t)\,\vec{x}_0$ / $\mathcal{R}_2$ |
| **$E_4$** | $\mathcal{R}_4(O_5, \mathcal{B}_4)$ | $O_5$ : centre du chariot plateau $Y$ ($L_{04}$) | $\mathcal{B}_4 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation longitudinale $y_4(t)\,\vec{y}_0$ / $\mathcal{R}_0$ |

> **Remarque fondamentale :** Les classes $E_2$, $E_3$ et $E_4$ n'étant animées que de mouvements de translation par rapport au bâti $E_0$, leurs bases vectorielles restent à tout instant parallèles à $\mathcal{B}_0$ ($\mathcal{B}_2 = \mathcal{B}_3 = \mathcal{B}_4 = \mathcal{B}_0$). Seule la vis mère $E_1$ tourne par rapport au bâti, ce qui nécessite l'introduction de la base tournante $\mathcal{B}_1(\vec{x}_1, \vec{y}_1, \vec{z}_0)$ et d'une unique figure plane de changement de base.

---

## 2. Figure plane de changement de base ($\mathcal{B}_0 \to \mathcal{B}_1$)

La rotation de la vis mère $E_1$ par rapport au bâti $E_0$ autour de l'axe $(O_1, \vec{z}_0)$ est paramétrée par l'angle orienté :
$$\theta_1(t) = \left(\widehat{\vec{x}_0, \vec{x}_1}\right) = \left(\widehat{\vec{y}_0, \vec{y}_1}\right) \quad \text{autour de } \vec{z}_0 = \vec{z}_1 \text{ (sortant } \odot \text{ en vue de dessus)}$$

- **Formules de projection directe de $\mathcal{B}_1$ dans $\mathcal{B}_0$ :**
  $$\begin{cases}
  \vec{x}_1 = \cos\theta_1(t)\,\vec{x}_0 + \sin\theta_1(t)\,\vec{y}_0 \\
  \vec{y}_1 = -\sin\theta_1(t)\,\vec{x}_0 + \cos\theta_1(t)\,\vec{y}_0 \\
  \vec{z}_1 = \vec{z}_0
  \end{cases}$$

- **Vecteur taux de rotation instantané de $E_1$ par rapport à $E_0$ :**
  $$\vec{\Omega}(E_1/E_0) = \dot{\theta}_1(t)\,\vec{z}_0 = \omega_{10}(t)\,\vec{z}_0$$

---

## 3. Paramétrage des centres géométriques des liaisons ($O_1$ à $O_5$)

On définit rigoureusement la position de chaque centre de liaison dans le repère de référence $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ à l'aide des **constantes géométriques de construction** ($L_x, h_1, d_y, h_5$) et des **4 paramètres cinématiques dépendant du temps** ($\theta_1(t), z_2(t), x_3(t), y_4(t)$) :

1. **Centre $O_1$ de la liaison Pivot $L_{01}$ ($E_0 - E_1$) :**  
   Point fixe sur l'axe de la vis mère $Z$, au centre du coupleur rigide aluminium :
   $$\overrightarrow{O_0 O_1} = -L_x\,\vec{x}_0 + h_1\,\vec{z}_0$$
   où $L_x = 125\text{ mm}$ est le déport latéral gauche de l'axe de la vis mère par rapport au plan médian $(O_0, \vec{y}_0, \vec{z}_0)$, et $h_1 = 45\text{ mm}$ sa cote verticale au-dessus de $O_0$.

2. **Centre $O_2$ de la liaison Hélicoïdale $L_{12}$ ($E_1 - E_2$) :**  
   Centre de l'écrou trapézoïdal en laiton Tr8x8 solidaire de la platine gauche du portique $E_2$, mobile le long de l'axe $(O_1, \vec{z}_0)$ :
   $$\overrightarrow{O_1 O_2} = z_2(t)\,\vec{z}_0 \quad \Longrightarrow \quad \overrightarrow{O_0 O_2} = \overrightarrow{O_0 O_1} + \overrightarrow{O_1 O_2} = -L_x\,\vec{x}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$$
   où $z_2(t) \in [0, 250\text{ mm}]$ est la **cote verticale d'élévation** du portique $E_2$.

3. **Centre $O_3$ de la liaison Glissière équivalente $L_{02}$ ($E_0 - E_2$) :**  
   Origine du repère local $\mathcal{R}_2$ lié au portique $E_2$, située à la même hauteur que l'écrou $O_2$ mais ramenée dans le plan médian $(O_0, \vec{y}_0, \vec{z}_0)$ (soit $\overrightarrow{O_2 O_3} = +L_x\,\vec{x}_0$) :
   $$\overrightarrow{O_0 O_3} = \overrightarrow{O_0 O_2} + \overrightarrow{O_2 O_3} = \big(h_1 + z_2(t)\big)\,\vec{z}_0$$

4. **Centre $O_4$ de la liaison Glissière $L_{23}$ ($E_2 - E_3$) et de la buse d'extrusion :**  
   Origine du repère local $\mathcal{R}_3$ lié au chariot de tête $E_3$, mobile selon $\vec{x}_0$ le long du profilé du portique $E_2$ :
   $$\overrightarrow{O_3 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 \quad \Longrightarrow \quad \overrightarrow{O_0 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$$
   où $x_3(t) \in [-110\text{ mm}, +110\text{ mm}]$ est l'**abscisse transversale** de la tête d'impression et $d_y = -25\text{ mm}$ est le déport frontal constant de la buse en avant du portique.

5. **Centre $O_5$ de la liaison Glissière $L_{04}$ ($E_0 - E_4$) :**  
   Origine du repère local $\mathcal{R}_4$ lié au plateau chauffant $E_4$, mobile selon $\vec{y}_0$ le long du rail central du bâti $E_0$ :
   $$\overrightarrow{O_0 O_5} = y_4(t)\,\vec{y}_0 + h_5\,\vec{z}_0$$
   où $y_4(t) \in [-110\text{ mm}, +110\text{ mm}]$ est l'**ordonnée longitudinale** du plateau chauffant et $h_5 = 45\text{ mm}$ est la cote verticale constante de la surface supérieure du plateau.

---

## 4. Fermeture géométrique : Vecteur position relative Buse / Plateau ($\overrightarrow{O_5 O_4}$)

En utilisant la relation de Chasles sur la chaîne des centres passant par l'origine $O_0$ du bâti :
$$\overrightarrow{O_5 O_4} = \overrightarrow{O_5 O_0} + \overrightarrow{O_0 O_3} + \overrightarrow{O_3 O_4} = -\overrightarrow{O_0 O_5} + \overrightarrow{O_0 O_3} + \overrightarrow{O_3 O_4}$$

On obtient l'expression vectorielle exacte de la position de la buse ($O_4 \in E_3$) par rapport au plateau ($O_5 \in E_4$) projetée dans la base $\mathcal{B}_0$ :
$$\boxed{\overrightarrow{O_5 O_4} = x_3(t)\,\vec{x}_0 + \big(d_y - y_4(t)\big)\,\vec{y}_0 + \big(h_1 - h_5 + z_2(t)\big)\,\vec{z}_0}$$

En choisissant l'origine des hauteurs telle que $h_1 = h_5$ (buse effleurant le plateau en $z_2 = 0$) et l'origine de l'axe $Y$ en $d_y$, les trois coordonnées cartésiennes $(X_{\text{imp}}, Y_{\text{imp}}, Z_{\text{imp}})$ du point de dépôt de filament dans le repère de la pièce imprimée sur le plateau $E_4$ sont découplées :
$$\begin{cases}
X_{\text{imp}}(t) = \overrightarrow{O_5 O_4} \cdot \vec{x}_0 = +x_3(t) \\
Y_{\text{imp}}(t) = \overrightarrow{O_5 O_4} \cdot \vec{y}_0 = d_y - y_4(t) \\
Z_{\text{imp}}(t) = \overrightarrow{O_5 O_4} \cdot \vec{z}_0 = +z_2(t)
\end{cases}$$

Par dérivation vectorielle dans la base $\mathcal{B}_4 = \mathcal{B}_0$ liée au plateau $E_4$, la vitesse relative de dépose du filament s'écrit immédiatement :
$$\boxed{\vec{V}(O_4 \in E_3 / E_4) = \left.\frac{\mathrm{d}\overrightarrow{O_5 O_4}}{\mathrm{d}t}\right|_{\mathcal{B}_0} = \dot{x}_3(t)\,\vec{x}_0 - \dot{y}_4(t)\,\vec{y}_0 + \dot{z}_2(t)\,\vec{z}_0}$$
