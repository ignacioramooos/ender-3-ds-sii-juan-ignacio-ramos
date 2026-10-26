# Paramétrage Géométrique, Repères Locaux ($\mathcal{R}_0$ à $\mathcal{R}_4$) et Chaîne des Centres

**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI (Lycée Stanislas)  
**Référence de cours :** Séquence 2 — Cours CM4 : *Cinématique du Solide Indéformable* (§ 1.2 : *Formule de Bour*, § 6 : *Mouvement plan sur plan*)  
**Conformité :** Programme officiel MPSI — Paramétrage géométrique et dérivation vectorielle

![Figure plane de changement de base et chaîne vectorielle des centres](../04_schemas_cinematiques/figures_parametrage_angles.svg)

---

## 1. Définition du Repère Global $\mathcal{R}_0$ et des Repères Locaux $\mathcal{R}_1$ à $\mathcal{R}_4$

Conformément à l'énoncé de la Partie III (*« Paramétrez votre système en y ajoutant les repères locaux nécessaires »*), on associe à chaque classe d'équivalence cinématique $E_k$ ($k \in \{0, 1, 2, 3, 4\}$) un **repère local orthonormé direct** $\mathcal{R}_k(O_{k}, \vec{x}_k, \vec{y}_k, \vec{z}_k)$ :

### 1.1. Repère global de référence $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié au bâti fixe $E_0$
- **Origine $O_0$ :** Point fixe appartenant au bâti $E_0$, situé à l'intersection de l'axe longitudinal médian du rail $Y$ ($40\times 40\text{ mm}$) et du plan frontal contenant les axes des deux montants verticaux $Z$ ($20\times 40\text{ mm}$).
- **Base orthonormée directe $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ :**
  - $\vec{x}_0$ : vecteur unitaire horizontal transversal, dirigé de la **gauche vers la droite** (en regardant l'imprimante de face), colinéaire au profilé du portique $X$.
  - $\vec{z}_0$ : vecteur unitaire **vertical ascendant**, colinéaire aux deux montants $Z$ et à l'axe de la vis mère trapézoïdale.
  - $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ : vecteur unitaire horizontal longitudinal (profondeur), dirigé de **l'avant vers l'arrière** de l'imprimante, colinéaire au rail central du plateau $Y$.
  - **Vérification du caractère direct :** $\vec{x}_0 \wedge \vec{y}_0 = \vec{z}_0$, $\vec{y}_0 \wedge \vec{z}_0 = \vec{x}_0$ et $\vec{z}_0 \wedge \vec{x}_0 = \vec{y}_0$.  
    > **Attention CPGE MPSI (Trièdre direct en projection plane) :** En projection frontale dans le plan $(O_0, \vec{x}_0, \vec{z}_0)$ ($\vec{x}_0$ vers la droite, $\vec{z}_0$ vers le haut), le vecteur $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ est obligatoirement **entrant dans la feuille** (noté $\otimes\,\vec{y}_0$).

### 1.2. Repères locaux attachés aux solides mobiles ($E_1, E_2, E_3, E_4$)

| Solide | Repère local lié | Origine géométrique | Base vectorielle liée | Nature du mouvement / $\mathcal{R}_0$ |
| :--- | :--- | :--- | :--- | :--- |
| **$E_0$** | $\mathcal{R}_0(O_0, \mathcal{B}_0)$ | $O_0 \in E_0$ (base du rail $Y$) | $\mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Référence fixe ($\underline{\underline{\equiv\mkern-10mu\perp}}$) |
| **$E_1$** | $\mathcal{R}_1(O_1, \mathcal{B}_1)$ | $O_1$ : centre du coupleur $Z$ (liaison $L_{01}$) | $\mathcal{B}_1 = (\vec{x}_1, \vec{y}_1, \vec{z}_0)$ tournante | Rotation d'angle $\theta_1(t)$ autour de $(O_1, \vec{z}_0)$ |
| **$E_2$** | $\mathcal{R}_2(O_3, \mathcal{B}_2)$ | $O_3$ : centre du guidage vertical $Z$ ($L_{02}$) | $\mathcal{B}_2 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation rectiligne verticale $z_2(t)\,\vec{z}_0$ |
| **$E_3$** | $\mathcal{R}_3(O_4, \mathcal{B}_3)$ | $O_4$ : centre du chariot $X$ / buse ($L_{23}$) | $\mathcal{B}_3 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation horizontale $x_3(t)\,\vec{x}_0$ / $\mathcal{R}_2$ |
| **$E_4$** | $\mathcal{R}_4(O_5, \mathcal{B}_4)$ | $O_5$ : centre du chariot plateau $Y$ ($L_{04}$) | $\mathcal{B}_4 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation longitudinale $y_4(t)\,\vec{y}_0$ / $\mathcal{R}_0$ |

> **Remarque fondamentale de cinématique :** Les solides $E_2$, $E_3$ et $E_4$ n'étant animés que de mouvements de translation pure par rapport au bâti $E_0$ ($\vec{\Omega} = \vec{0}$), leurs bases vectorielles restent à tout instant strictement parallèles à $\mathcal{B}_0$ ($\mathcal{B}_2 = \mathcal{B}_3 = \mathcal{B}_4 = \mathcal{B}_0$). Seule la vis mère $E_1$ tourne par rapport au bâti, ce qui nécessite l'introduction d'une unique figure plane de changement de base $(\mathcal{B}_0 \to \mathcal{B}_1)$.

---

## 2. Figure Plane de Changement de Base ($\mathcal{B}_0 \to \mathcal{B}_1$) & Formule de Bour

La rotation de la vis mère $E_1$ par rapport au bâti $E_0$ autour de l'axe vertical $(O_1, \vec{z}_0)$ est paramétrée par l'angle orienté :
$$\theta_1(t) = \left(\widehat{\vec{x}_0, \vec{x}_1}\right) = \left(\widehat{\vec{y}_0, \vec{y}_1}\right) \quad \text{autour de } \vec{z}_0 = \vec{z}_1 \text{ (sortant } \odot \text{ en vue de dessus)}$$

- **Relations géométriques de projection directe :**
  $$\begin{cases}
  \vec{x}_1 = \cos\theta_1(t)\,\vec{x}_0 + \sin\theta_1(t)\,\vec{y}_0 \\
  \vec{y}_1 = -\sin\theta_1(t)\,\vec{x}_0 + \cos\theta_1(t)\,\vec{y}_0 \\
  \vec{z}_1 = \vec{z}_0
  \end{cases}$$

- **Formule de dérivation vectorielle (Formule de Bour — CM4 § 1.2) :**
  Pour tout vecteur $\vec{u}(t)$ :
  $$\left.\frac{\mathrm{d}\vec{u}}{\mathrm{d}t}\right|_{R_0} = \left.\frac{\mathrm{d}\vec{u}}{\mathrm{d}t}\right|_{R_1} + \vec{\Omega}(R_1/R_0) \wedge \vec{u}$$
  En appliquant à $\vec{x}_1$ (vecteur fixe dans $R_1$) :
  $$\left.\frac{\mathrm{d}\vec{x}_1}{\mathrm{d}t}\right|_{R_0} = \vec{0} + \big(\dot{\theta}_1(t)\,\vec{z}_0\big) \wedge \vec{x}_1 = \dot{\theta}_1(t)\,\vec{y}_1$$
  Le vecteur vitesse instantanée de rotation de la vis s'écrit donc :
  $$\vec{\Omega}(E_1/E_0) = \dot{\theta}_1(t)\,\vec{z}_0 = \omega_{10}(t)\,\vec{z}_0$$

---

## 3. Paramétrage des Centres Géométriques des Liaisons ($O_1$ à $O_5$)

On définit la position de chaque centre de liaison dans le repère de référence $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ à l'aide des constantes géométriques ($L_x, h_1, d_y, h_5$) et des 4 paramètres cinématiques dépendant du temps ($\theta_1(t), z_2(t), x_3(t), y_4(t)$) :

1. **Centre $O_1$ de la liaison Pivot $L_{01}$ ($E_0 - E_1$) :**  
   $$\overrightarrow{O_0 O_1} = -L_x\,\vec{x}_0 + h_1\,\vec{z}_0$$
   avec $L_x = 125\text{ mm}$ (déport latéral gauche) et $h_1 = 45\text{ mm}$ (hauteur du coupleur).

2. **Centre $O_2$ de la liaison Hélicoïdale $L_{12}$ ($E_1 - E_2$) :**  
   Centre de l'écrou trapézoïdal en laiton Tr8x8 monté sur la platine gauche du portique :
   $$\overrightarrow{O_1 O_2} = z_2(t)\,\vec{z}_0 \quad \Longrightarrow \quad \overrightarrow{O_0 O_2} = -L_x\,\vec{x}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$$
   où $z_2(t) \in [0, 250\text{ mm}]$ est la **cote d'élévation verticale** du portique.

3. **Centre $O_3$ de la liaison Glissière équivalente $L_{02}$ ($E_0 - E_2$) :**  
   Origine du repère $\mathcal{R}_2$ ramenée dans le plan médian $(O_0, \vec{y}_0, \vec{z}_0)$ ($\overrightarrow{O_2 O_3} = +L_x\,\vec{x}_0$) :
   $$\overrightarrow{O_0 O_3} = \overrightarrow{O_0 O_2} + \overrightarrow{O_2 O_3} = \big(h_1 + z_2(t)\big)\,\vec{z}_0$$

4. **Centre $O_4$ de la liaison Glissière $L_{23}$ ($E_2 - E_3$) et de la buse :**  
   Origine du repère $\mathcal{R}_3$ lié au chariot de tête :
   $$\overrightarrow{O_3 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 \quad \Longrightarrow \quad \overrightarrow{O_0 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$$
   où $x_3(t) \in [-110\text{ mm}, +110\text{ mm}]$ est l'**abscisse transversale** et $d_y = -25\text{ mm}$ est le déport en avant du portique.

5. **Centre $O_5$ de la liaison Glissière $L_{04}$ ($E_0 - E_4$) :**  
   Origine du repère $\mathcal{R}_4$ lié au plateau chauffant :
   $$\overrightarrow{O_0 O_5} = y_4(t)\,\vec{y}_0 + h_5\,\vec{z}_0$$
   où $y_4(t) \in [-110\text{ mm}, +110\text{ mm}]$ est l'**ordonnée longitudinale** et $h_5 = 45\text{ mm}$ est la cote verticale de la surface supérieure du plateau.

---

## 4. Fermeture Géométrique : Vecteur Buse / Plateau ($\overrightarrow{O_5 O_4}$)

Par la relation de Chasles sur la chaîne des centres :
$$\overrightarrow{O_5 O_4} = \overrightarrow{O_5 O_0} + \overrightarrow{O_0 O_3} + \overrightarrow{O_3 O_4} = -\overrightarrow{O_0 O_5} + \overrightarrow{O_0 O_3} + \overrightarrow{O_3 O_4}$$
$$\boxed{\overrightarrow{O_5 O_4} = x_3(t)\,\vec{x}_0 + \big(d_y - y_4(t)\big)\,\vec{y}_0 + \big(h_1 - h_5 + z_2(t)\big)\,\vec{z}_0}$$

En choisissant les origines de sorte que $h_1 = h_5$ (buse effleurant le lit à $z_2 = 0$) :
$$\begin{cases}
X_{\text{imp}}(t) = +x_3(t) \\
Y_{\text{imp}}(t) = d_y - y_4(t) \\
Z_{\text{imp}}(t) = +z_2(t)
\end{cases}$$

Par dérivation vectorielle dans la base $\mathcal{B}_4 = \mathcal{B}_0$ (Formule de Bour) :
$$\boxed{\vec{V}(O_4 \in E_3 / E_4) = \left.\frac{\mathrm{d}\overrightarrow{O_5 O_4}}{\mathrm{d}t}\right|_{\mathcal{B}_0} = \dot{x}_3(t)\,\vec{x}_0 - \dot{y}_4(t)\,\vec{y}_0 + \dot{z}_2(t)\,\vec{z}_0}$$
Le mouvement relatif de dépôt du fil fondu est une translation spatiale à 3 degrés de liberté totalement découplés.
