# DM n°1 — Modélisation des Liaisons et Schématisation Cinématique (Dossier Papier Complet)

- **Nom :** RAMOS
- **Prénom :** Juan Ignacio
- **Classe :** MPSI — Lycée Stanislas
- **Enseignants :** Mme Marianne Prot & M. Cullaz
- **Système étudié :** Imprimante 3D à dépôt de fil fondu (FDM) **Creality Ender 3 (modèle de base)**
- **Livrable imprimable A4 :** [`DM1_Feuille_Rendu_Imprimable.html`](DM1_Feuille_Rendu_Imprimable.html) | [`Planches SII`](../diagrams_reference.html)

---

## 1. Présentation Photographique et Paramétrage du Système (Partie III — Exigence 1)

### 1.1. Photo de l'élève avec le système validé (`RAMOS-Selfie.png`)
![Selfie de Juan Ignacio Ramos avec l'imprimante 3D Creality Ender 3](../02_photos/RAMOS-Selfie.png)

### 1.2. Photo détaillée du système paramétré avec repères locaux et classes d'équivalence (`RAMOS-Ender3-Details.png`)
![Photo annotée du système Creality Ender 3 avec repères locaux et classes d'équivalence](../02_photos/RAMOS-Ender3-Details.png)

---

## 2. Repères Locaux ($\mathcal{R}_0$ à $\mathcal{R}_4$), Paramétrage Géométrique et Chaîne des Centres

![Figure plane de changement de base et chaîne vectorielle des centres](../04_schemas_cinematiques/figures_parametrage_angles.svg)

### 2.1. Définition du repère global $\mathcal{R}_0$ et des 4 repères locaux mobiles ($\mathcal{R}_1, \mathcal{R}_2, \mathcal{R}_3, \mathcal{R}_4$)

À chaque classe d'équivalence cinématique $E_k$ ($k \in \{0, 1, 2, 3, 4\}$) est attaché un **repère local orthonormé direct** $\mathcal{R}_k(O_{k}, \vec{x}_k, \vec{y}_k, \vec{z}_k)$ :

| Classe | Couleur | Repère local lié | Origine géométrique | Base orthonormée directe associée | Paramètre de mouvement |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **$E_0$** | **Noir** | $\mathcal{R}_0(O_0, \mathcal{B}_0)$ | $O_0$ : base médiane du rail $Y$ | $\mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ fixe | Référence fixe ($\underline{\underline{\equiv\mkern-10mu\perp}}$) |
| **$E_1$** | **Bleu** | $\mathcal{R}_1(O_1, \mathcal{B}_1)$ | $O_1$ : centre du coupleur $Z$ ($L_{01}$) | $\mathcal{B}_1 = (\vec{x}_1, \vec{y}_1, \vec{z}_0)$ tournante | Rotation $\theta_1(t) = (\widehat{\vec{x}_0, \vec{x}_1})$ autour de $\vec{z}_0$ |
| **$E_2$** | **Rouge** | $\mathcal{R}_2(O_3, \mathcal{B}_2)$ | $O_3$ : centre du guidage $Z$ ($L_{02}$) | $\mathcal{B}_2 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation verticale $z_2(t)\,\vec{z}_0$ / $\mathcal{R}_0$ |
| **$E_3$** | **Vert** | $\mathcal{R}_3(O_4, \mathcal{B}_3)$ | $O_4$ : centre du chariot $X$ / buse ($L_{23}$) | $\mathcal{B}_3 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation horizontale $x_3(t)\,\vec{x}_0$ / $\mathcal{R}_2$ |
| **$E_4$** | **Orange** | $\mathcal{R}_4(O_5, \mathcal{B}_4)$ | $O_5$ : centre du chariot plateau $Y$ ($L_{04}$) | $\mathcal{B}_4 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation longitudinale $y_4(t)\,\vec{y}_0$ / $\mathcal{R}_0$ |

- **Orientation directe de $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ :**
  - $\vec{x}_0$ : horizontal transversal (de la gauche vers la droite en vue de face).
  - $\vec{z}_0$ : vertical ascendant (colinéaire aux montants verticaux $Z$ et à la vis mère).
  - $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ : horizontal longitudinal (dirigé de l'avant vers l'arrière de la machine, donc **entrant $\otimes\,\vec{y}_0$** en vue de face $(O_0, \vec{x}_0, \vec{z}_0)$).

- **Figure plane de changement de base ($\mathcal{B}_0 \to \mathcal{B}_1$) :**
  $$\begin{cases}
  \vec{x}_1 = \cos\theta_1(t)\,\vec{x}_0 + \sin\theta_1(t)\,\vec{y}_0 \\
  \vec{y}_1 = -\sin\theta_1(t)\,\vec{x}_0 + \cos\theta_1(t)\,\vec{y}_0 \\
  \vec{z}_1 = \vec{z}_0
  \end{cases}
  \quad \Longrightarrow \quad
  \vec{\Omega}(E_1/E_0) = \dot{\theta}_1(t)\,\vec{z}_0 = \omega_{10}(t)\,\vec{z}_0$$

### 2.2. Vecteurs position des centres géométriques ($O_1$ à $O_5$) et fermeture géométrique
- $\overrightarrow{O_0 O_1} = -L_x\,\vec{x}_0 + h_1\,\vec{z}_0$ (centre du pivot $L_{01}$ sur l'axe de la vis mère, avec $L_x = 125\text{ mm}$, $h_1 = 45\text{ mm}$).
- $\overrightarrow{O_1 O_2} = z_2(t)\,\vec{z}_0 \implies \overrightarrow{O_0 O_2} = -L_x\,\vec{x}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$ (centre de l'écrou laiton $L_{12}$).
- $\overrightarrow{O_2 O_3} = +L_x\,\vec{x}_0 \implies \overrightarrow{O_0 O_3} = \big(h_1 + z_2(t)\big)\,\vec{z}_0$ (centre de la glissière équivalente $L_{02}$).
- $\overrightarrow{O_3 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 \implies \overrightarrow{O_0 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$ (centre du chariot de tête / buse $O_4$).
- $\overrightarrow{O_0 O_5} = y_4(t)\,\vec{y}_0 + h_5\,\vec{z}_0$ (centre du chariot du plateau chauffant $O_5$).
- **Vecteur position relative de la buse ($O_4 \in E_3$) par rapport au plateau ($O_5 \in E_4$) :**
  $$\boxed{\overrightarrow{O_5 O_4} = x_3(t)\,\vec{x}_0 + \big(d_y - y_4(t)\big)\,\vec{y}_0 + \big(h_1 - h_5 + z_2(t)\big)\,\vec{z}_0}$$

---

## 3. Classes d'Équivalence Explicites et Graphe des Liaisons (Partie III — Exigence 2)

### 3.1. Détail explicite des pièces de chaque classe d'équivalence ($E_0$ à $E_4$)

1. **$E_0$ — Bâti fixe (Noir, repère $\mathcal{R}_0$, mis en valeur par $\underline{\underline{\equiv\mkern-10mu\perp}}$) :**
   $$E_0 = \left\{\begin{array}{l}
   \text{Châssis en profilés aluminium V-Slot (cadre inférieur } 40\times 40,\text{ rail central } Y\text{ } 40\times 40, \\
   \quad \text{2 montants verticaux } Z\text{ } 20\times 40,\text{ traverse supérieure } 20\times 20\text{) + porte-bobine + 4 patins caoutchouc}, \\
   \text{Stators (corps fixes) des moteurs pas-à-pas NEMA 17 des axes } Z\text{ et } Y, \\
   \text{Bloc d'alimentation 24 V, boîtier carte mère, écran LCD, tendeur avant } Y,\text{ capteurs } Z\text{- et } Y\text{-Endstop}.
   \end{array}\right\}$$

2. **$E_1$ — Arbre moteur & Vis mère $Z$ (Bleu, repère $\mathcal{R}_1$) :**
   $$E_1 = \left\{\begin{array}{l}
   \text{Rotor et arbre de sortie ($\varnothing 5\text{ mm}$) du moteur pas-à-pas NEMA 17 de l'axe } Z, \\
   \text{Coupleur cylindrique fendu rigide en alliage d'aluminium + 2 vis de serrage CHC M3}, \\
   \text{Vis mère trapézoïdale en acier inoxydable Tr8x8 ($\varnothing 8\text{ mm}$, filetage à droite, pas } p_z = 8\text{ mm/tr)}.
   \end{array}\right\}$$

3. **$E_2$ — Portique mobile horizontal $X$ (Rouge, repère $\mathcal{R}_2$) :**
   $$E_2 = \left\{\begin{array}{l}
   \text{Profilé aluminium horizontal } X\text{ V-Slot } 20\times 20\text{ mm + platines supports gauche et droite en acier}, \\
   \text{Écrou trapézoïdal en laiton Tr8x8 fixé sur la platine gauche par 2 vis M3}, \\
   \text{Axes boulonnés M5, entretoises, excentriques et bagues intérieures des 6 galets V-wheels de guidage } Z, \\
   \text{Stators des moteurs NEMA 17 de l'axe } X\text{ et de l'extrudeur MK8, capteur } X\text{-Endstop, tendeur droit } X.
   \end{array}\right\}$$

4. **$E_3$ — Chariot de tête d'impression / Hotend (Vert, repère $\mathcal{R}_3$) :**
   $$E_3 = \left\{\begin{array}{l}
   \text{Platine chariot } X\text{ en acier plié + axes M5, entretoises, excentrique et bagues intérieures des 3 galets } X, \\
   \text{Tête chaude complète (raccord PC4-M10, radiateur rouge, heatbreak, bloc de chauffe, buse laiton } \varnothing 0{,}4\text{ mm)}, \\
   \text{Carénage métallique de tête et stators des 2 ventilateurs 4010 (refroidissement radiateur et buse)}.
   \end{array}\right\}$$

5. **$E_4$ — Plateau chauffant mobile $Y$ (Orange, repère $\mathcal{R}_4$) :**
   $$E_4 = \left\{\begin{array}{l}
   \text{Platine chariot } Y\text{ en aluminium + axes M5, entretoises, 2 excentriques et bagues intérieures des 4 galets } Y, \\
   \text{4 vis M4 et 4 molettes crantées de nivellement (fixes en cours d'impression)}, \\
   \text{Plaque chauffante en aluminium ($235\times 235\text{ mm}$, 24 V / 220 W), revêtement BuildTak, 4 pinces et pièce imprimée}.
   \end{array}\right\}$$

### 3.2. Graphe des liaisons normalisé

![Graphe des liaisons normalisé de la Creality Ender 3](../04_schemas_cinematiques/graphe_des_liaisons.svg)

---

## 4. Répertoire des Liaisons, Torseurs Cinématiques et Fermeture de Chaîne

### 4.1. Tableau des 5 liaisons élémentaires (3 familles distinctes) et torseurs dans $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$

| Liaison | Classes | Famille AFNOR & Caractéristique | Torseur cinématique $\{\mathcal{V}(E_j/E_i)\}$ exprimé dans $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ |
| :--- | :---: | :--- | :--- |
| **$L_{01}$** | $E_0 - E_1$ | **Pivot** d'axe $(O_1, \vec{z}_0)$ | $\{\mathcal{V}(E_1/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{10}(t) & 0 \end{Bmatrix}_{O_1, \mathcal{B}_0}$ avec $\omega_{10}(t) = \dot{\theta}_1(t)$ |
| **$L_{12}$** | $E_1 - E_2$ | **Hélicoïdale** d'axe $(O_2, \vec{z}_0)$, filet à droite, pas $p_z = 8\text{ mm/tr}$ | $\{\mathcal{V}(E_2/E_1)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & v_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0}$ avec $v_{21}(t) = +\dfrac{p_z}{2\pi}\,\omega_{21}(t)$ |
| **$L_{02}$** | $E_0 - E_2$ | **Glissière** de direction $\vec{z}_0$ (en $O_3$) | $\{\mathcal{V}(E_2/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0}$ avec $V_z(t) = \dot{z}_2(t)$ |
| **$L_{23}$** | $E_2 - E_3$ | **Glissière** de direction $\vec{x}_0$ (en $O_4$) | $\{\mathcal{V}(E_3/E_2)\} = \begin{Bmatrix} 0 & V_x(t) \\ 0 & 0 \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0}$ avec $V_x(t) = \dot{x}_3(t)$ |
| **$L_{04}$** | $E_0 - E_4$ | **Glissière** de direction $\vec{y}_0$ (en $O_5$) | $\{\mathcal{V}(E_4/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & V_y(t) \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0}$ avec $V_y(t) = \dot{y}_4(t)$ |

### 4.2. Fermeture cinématique de la boucle d'élévation $Z$ ($E_0 - E_1 - E_2 - E_0$)
En réduisant au point $O_2 \in (O_1, \vec{z}_0)$ la relation de composition des torseurs cinématiques $\{\mathcal{V}(E_2/E_0)\} = \{\mathcal{V}(E_2/E_1)\} + \{\mathcal{V}(E_1/E_0)\}$ :
$$\begin{cases}
\text{Résultante selon } \vec{z}_0 : & 0 = \omega_{21}(t) + \omega_{10}(t) \implies \omega_{21}(t) = -\omega_{10}(t) \\[4pt]
\text{Moment en } O_2\text{ selon } \vec{z}_0 : & V_z(t) = v_{21}(t) + 0 = +\dfrac{p_z}{2\pi}\,\omega_{21}(t)
\end{cases}
\quad \Longrightarrow \quad
\boxed{V_z(t) = \dot{z}_2(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t) = +\frac{p_z}{2\pi}\,\omega_m(t)}$$
où $\omega_m(t) = -\omega_{10}(t) > 0$ est la vitesse angulaire motrice de montée (rotation horaire de la vis vue de dessus).

---

## 5. Schéma Cinématique Minimal 2D en Couleur (Partie III — Exigence 3)

![Schéma cinématique minimal 2D en couleur de la Creality Ender 3](../04_schemas_cinematiques/schema_cinematique_2d.svg)

---

## 6. Schéma Cinématique Spatial 3D en Couleur (Partie III — Exigence 4)

![Schéma cinématique spatial 3D en couleur de la Creality Ender 3](../04_schemas_cinematiques/schema_cinematique_3d.svg)
