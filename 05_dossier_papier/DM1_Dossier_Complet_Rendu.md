# DM n°1 — Modélisation des Liaisons et Schématisation Cinématique (Dossier Papier Complet)

- **Nom :** RAMOS
- **Prénom :** Juan Ignacio
- **Classe :** CPGE MPSI — Lycée Stanislas
- **Enseignants :** Mme Marianne Prot & M. Cullaz
- **Matière :** Sciences Industrielles de l'Ingénieur (SII) — Séquence 2 (CM4 : *Cinématique du Solide Indéformable*)
- **Système étudié :** Imprimante 3D à dépôt de fil fondu (FDM) **Creality Ender 3 (modèle de base)**
- **Livrables associés :** [`DM1_Feuille_Rendu_Imprimable.html`](DM1_Feuille_Rendu_Imprimable.html) (Feuille A4 officielle Recto-Verso) | [`diagrams_reference.html`](../diagrams_reference.html) (Planches SII)

---

## 1. Présentation Photographique et Paramétrage du Système (Partie III — Exigence 1)

### 1.1. Photo de validation de l'élève avec le système (`RAMOS-Selfie.png`)
Conformément aux exigences de la Partie II de l'énoncé, la photographie atteste de la prise en main effective du système réel personnel de l'élève au laboratoire ou à domicile.

![Selfie de Juan Ignacio Ramos avec l'imprimante 3D Creality Ender 3](../02_photos/RAMOS-Selfie.png)

### 1.2. Photo détaillée du système paramétré avec repères locaux et classes d'équivalence (`RAMOS-Ender3-Details.png`)
La planche photographique ci-dessous présente l'imprimante Creality Ender 3 en phase d'impression nominale (modèle de la *Vénus de Milo*), munie d'une loupe macro sur la chaîne d'entraînement vertical $Z$ (vis trapézoïdale Tr8x8, coupleur aluminium et écrou en laiton). Y sont repérés le repère global orthonormé direct $\mathcal{R}_0$, les 4 repères locaux $\mathcal{R}_1 \dots \mathcal{R}_4$, les centres géométriques $O_1 \dots O_5$, les paramètres cinématiques et le pointage fléché des 5 classes d'équivalence $E_0 \dots E_4$.

![Photo annotée du système Creality Ender 3 avec repères locaux et classes d'équivalence](../02_photos/RAMOS-Ender3-Details.png)

---

## 2. Repères Locaux ($\mathcal{R}_0$ à $\mathcal{R}_4$), Paramétrage Géométrique et Chaîne des Centres

![Figure plane de changement de base et chaîne vectorielle des centres](../04_schemas_cinematiques/figures_parametrage_angles.svg)

### 2.1. Définition du repère global $\mathcal{R}_0$ et des 4 repères locaux mobiles ($\mathcal{R}_1, \mathcal{R}_2, \mathcal{R}_3, \mathcal{R}_4$)

À chaque classe d'équivalence cinématique $E_k$ ($k \in \{0, 1, 2, 3, 4\}$) est attaché un **repère local orthonormé direct** $\mathcal{R}_k(O_{k}, \vec{x}_k, \vec{y}_k, \vec{z}_k)$ :

| Classe | Couleur normalisée | Repère local lié | Origine géométrique | Base orthonormée directe associée | Paramètre cinématique / $\mathcal{R}_0$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **$E_0$** | **Noir** (`#0f172a`) | $\mathcal{R}_0(O_0, \mathcal{B}_0)$ | $O_0$ : base médiane du rail $Y$ | $\mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ fixe | Référence fixe ($\underline{\underline{\equiv\mkern-10mu\perp}}$) |
| **$E_1$** | **Bleu** (`#2563eb`) | $\mathcal{R}_1(O_1, \mathcal{B}_1)$ | $O_1$ : centre du coupleur $Z$ ($L_{01}$) | $\mathcal{B}_1 = (\vec{x}_1, \vec{y}_1, \vec{z}_0)$ tournante | Rotation $\theta_1(t) = (\widehat{\vec{x}_0, \vec{x}_1})$ autour de $\vec{z}_0$ |
| **$E_2$** | **Rouge** (`#dc2626`) | $\mathcal{R}_2(O_3, \mathcal{B}_2)$ | $O_3$ : centre du guidage $Z$ ($L_{02}$) | $\mathcal{B}_2 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation verticale $z_2(t)\,\vec{z}_0$ / $\mathcal{R}_0$ |
| **$E_3$** | **Vert** (`#16a34a`) | $\mathcal{R}_3(O_4, \mathcal{B}_3)$ | $O_4$ : centre du chariot $X$ / buse ($L_{23}$) | $\mathcal{B}_3 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation horizontale $x_3(t)\,\vec{x}_0$ / $\mathcal{R}_2$ |
| **$E_4$** | **Orange** (`#ea580c`) | $\mathcal{R}_4(O_5, \mathcal{B}_4)$ | $O_5$ : centre du chariot plateau $Y$ ($L_{04}$) | $\mathcal{B}_4 = \mathcal{B}_0 = (\vec{x}_0, \vec{y}_0, \vec{z}_0)$ | Translation longitudinale $y_4(t)\,\vec{y}_0$ / $\mathcal{R}_0$ |

- **Orientation directe du trièdre de référence $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ :**
  - $\vec{x}_0$ : horizontal transversal, orienté de la gauche vers la droite en vue de face.
  - $\vec{z}_0$ : vertical ascendant, colinéaire aux montants verticaux et à la vis mère.
  - $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ : horizontal longitudinal, orienté de l'avant vers l'arrière de la machine.  
    > **Attention CPGE MPSI (Règle du trièdre direct) :** En projection frontale dans le plan $(O_0, \vec{x}_0, \vec{z}_0)$ ($\vec{x}_0$ vers la droite, $\vec{z}_0$ vers le haut), le vecteur $\vec{y}_0$ est obligatoirement **entrant dans la feuille** ($\otimes\,\vec{y}_0$).

- **Figure plane de changement de base ($\mathcal{B}_0 \to \mathcal{B}_1$) & Formule de Bour (CM4 § 1.2) :**
  $$\begin{cases}
  \vec{x}_1 = \cos\theta_1(t)\,\vec{x}_0 + \sin\theta_1(t)\,\vec{y}_0 \\
  \vec{y}_1 = -\sin\theta_1(t)\,\vec{x}_0 + \cos\theta_1(t)\,\vec{y}_0 \\
  \vec{z}_1 = \vec{z}_0
  \end{cases}
  \quad \Longrightarrow \quad
  \vec{\Omega}(E_1/E_0) = \dot{\theta}_1(t)\,\vec{z}_0 = \omega_{10}(t)\,\vec{z}_0$$

### 2.2. Vecteurs position des centres géométriques ($O_1$ à $O_5$) et chaîne vectorielle
- $\overrightarrow{O_0 O_1} = -L_x\,\vec{x}_0 + h_1\,\vec{z}_0$ (centre du pivot $L_{01}$ sur l'axe de la vis mère, avec $L_x = 125\text{ mm}$, $h_1 = 45\text{ mm}$).
- $\overrightarrow{O_1 O_2} = z_2(t)\,\vec{z}_0 \implies \overrightarrow{O_0 O_2} = -L_x\,\vec{x}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$ (centre de l'écrou laiton $L_{12}$).
- $\overrightarrow{O_2 O_3} = +L_x\,\vec{x}_0 \implies \overrightarrow{O_0 O_3} = \big(h_1 + z_2(t)\big)\,\vec{z}_0$ (centre de la glissière équivalente $L_{02}$).
- $\overrightarrow{O_3 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 \implies \overrightarrow{O_0 O_4} = x_3(t)\,\vec{x}_0 + d_y\,\vec{y}_0 + \big(h_1 + z_2(t)\big)\,\vec{z}_0$ (centre du chariot de tête / buse $O_4$, avec $d_y = -25\text{ mm}$).
- $\overrightarrow{O_0 O_5} = y_4(t)\,\vec{y}_0 + h_5\,\vec{z}_0$ (centre du chariot du plateau chauffant $O_5$, avec $h_5 = 45\text{ mm}$).

### 2.3. Fermeture géométrique : Vecteur position relative Buse / Plateau ($\overrightarrow{O_5 O_4}$)
En utilisant la relation de Chasles :
$$\overrightarrow{O_5 O_4} = \overrightarrow{O_5 O_0} + \overrightarrow{O_0 O_3} + \overrightarrow{O_3 O_4} = -\overrightarrow{O_0 O_5} + \overrightarrow{O_0 O_3} + \overrightarrow{O_3 O_4}$$
$$\boxed{\overrightarrow{O_5 O_4} = x_3(t)\,\vec{x}_0 + \big(d_y - y_4(t)\big)\,\vec{y}_0 + \big(h_1 - h_5 + z_2(t)\big)\,\vec{z}_0}$$

Par dérivation vectorielle dans le repère $\mathcal{R}_4$ (Formule de Bour avec $\vec{\Omega}(E_4/E_0) = \vec{0}$) :
$$\boxed{\vec{V}(O_4 \in E_3 / E_4) = \left.\frac{\mathrm{d}\overrightarrow{O_5 O_4}}{\mathrm{d}t}\right|_{\mathcal{B}_0} = \dot{x}_3(t)\,\vec{x}_0 - \dot{y}_4(t)\,\vec{y}_0 + \dot{z}_2(t)\,\vec{z}_0}$$
Le mouvement relatif de dépôt du fil est une **translation spatiale découplée à 3 degrés de liberté indépendants**.

---

## 3. Classes d'Équivalence Explicites et Graphe des Liaisons (Partie III — Exigence 2)

### 3.1. Détail exhaustif des pièces constitutives de chaque classe d'équivalence ($E_0$ à $E_4$)

> **Règle impérative du barème :** Conformément à l'énoncé, chaque classe d'équivalence répertorie la totalité des pièces réelles sans omission.

1. **$E_0$ — Bâti fixe (Couleur : Noir — Repère de référence $\mathcal{R}_0$ — Symbole $\underline{\underline{\equiv\mkern-10mu\perp}}$) :**
   $$E_0 = \left\{\begin{array}{l}
   \text{Cadre inférieur en profilés aluminium extrudés V-Slot } 40\times 40\text{ mm (longerons et traverses)}, \\
   \text{Rail central de guidage } Y\text{ en profilé V-Slot } 40\times 40\text{ mm (orienté selon } \vec{y}_0\text{)}, \\
   \text{2 montants verticaux (colonnes } Z\text{) en profilé V-Slot } 20\times 40\text{ mm et traverse haute } 20\times 20\text{ mm}, \\
   \text{Porte-bobine métallique supérieur, 4 patins amortisseurs caoutchouc et visserie châssis M5}, \\
   \text{Stators (corps et flasques fixes) des moteurs pas-à-pas NEMA 17 des axes } Z\text{ et } Y, \\
   \text{Bloc d'alimentation 24 V (MeanWell/Creality), boîtier carte mère et châssis de l'écran LCD}, \\
   \text{Support tendeur avant de courroie } Y\text{ et corps des capteurs de fin de course (Endstops) } Z\text{ et } Y.
   \end{array}\right\}$$

2. **$E_1$ — Arbre moteur & Vis mère $Z$ (Couleur : Bleu — Repère $\mathcal{R}_1$) :**
   $$E_1 = \left\{\begin{array}{l}
   \text{Rotor et arbre de sortie cylindrique ($\varnothing 5\text{ mm}$, méplat en D) du moteur NEMA 17 } Z, \\
   \text{Coupleur cylindrique rigide fendu en alliage d'aluminium + 2 vis de serrage CHC M3}, \\
   \text{Vis mère trapézoïdale en acier inoxydable Tr8x8 ($\varnothing_{\text{nom}} = 8\text{ mm}$, 4 filets à droite, pas } p_z = 8\text{ mm/tr)}.
   \end{array}\right\}$$

3. **$E_2$ — Portique mobile horizontal $X$ (Couleur : Rouge — Repère $\mathcal{R}_2$) :**
   $$E_2 = \left\{\begin{array}{l}
   \text{Profilé aluminium horizontal } X\text{ V-Slot } 20\times 20\text{ mm + platines en acier gauche et droite}, \\
   \text{Écrou trapézoïdal en laiton Tr8x8 fixé sur la platine gauche par 2 vis M3 et rondelles frein}, \\
   \text{Axes boulonnés M5, entretoises, excentriques et bagues intérieures des 6 galets V-wheels } Z, \\
   \text{Stators des moteurs NEMA 17 de l'axe } X\text{ et de l'extrudeur MK8, capteur } X\text{-Endstop, tendeur droit } X.
   \end{array}\right\}$$

4. **$E_3$ — Chariot de tête d'impression / Hotend (Couleur : Vert — Repère $\mathcal{R}_3$) :**
   $$E_3 = \left\{\begin{array}{l}
   \text{Platine chariot } X\text{ en acier plié + axes M5, entretoises, écrou excentrique et bagues intérieures des 3 galets } X, \\
   \text{Corps complet de tête chaude (raccord PC4-M10, radiateur rouge, heatbreak, bloc de chauffe, buse laiton } \varnothing 0{,}4\text{ mm)}, \\
   \text{Cartouche chauffante (24 V / 40 W), thermistance CTN 100 k$\Omega$, carénage métallique et stators des 2 ventilateurs 4010}.
   \end{array}\right\}$$

5. **$E_4$ — Plateau chauffant mobile $Y$ (Couleur : Orange — Repère $\mathcal{R}_4$) :**
   $$E_4 = \left\{\begin{array}{l}
   \text{Platine chariot } Y\text{ en aluminium découpé (chariot en H/Y) sous le lit}, \\
   \text{Axes boulonnés M5, entretoises, 2 excentriques droits et bagues intérieures des 4 galets V-wheels } Y, \\
   \text{4 vis fraisées M4 et 4 molettes crantées de nivellement (bloquées en cours d'impression)}, \\
   \text{Plaque chauffante aluminium ($235\times 235\text{ mm}$, 24 V / 220 W), revêtement BuildTak/verre, 4 pinces et pièce imprimée}.
   \end{array}\right\}$$

### 3.2. Graphe des liaisons normalisé

![Graphe des liaisons normalisé de la Creality Ender 3](../04_schemas_cinematiques/graphe_des_liaisons.svg)

- **Nombre de sommets :** $N = 5$ classes d'équivalence indéformables.
- **Nombre d'arcs :** $L = 5$ liaisons élémentaires normalisées.
- **Nombre cyclomatique :** $\gamma = L - N + 1 = 5 - 5 + 1 = 1$.
- **Structure topologique :** Architecture hybride série-parallèle comportant une boucle fermée élémentaire ($\gamma = 1$) d'élévation $Z$ ($E_0 - E_1 - E_2 - E_0$) et deux chaînes ouvertes séries orthogonales ($E_2 - E_3$ selon $\vec{x}_0$ et $E_0 - E_4$ selon $\vec{y}_0$).

---

## 4. Répertoire Canonique des Liaisons, Torseurs Cinématiques et Fermeture Cinématique

### 4.1. Tableau des 5 liaisons élémentaires et torseurs (Notations officielles CM4)

En mécanique rationnelle CPGE (Cours CM4 § 2), un torseur cinématique $\{\mathcal{V}_{S/R}\}$ est défini par sa **résultante** $\vec{\Omega}_{S/R}$ (vecteur instantané de rotation, invariant par translation du point) et son **moment** $\vec{V}_{A \in S/R}$ (vitesse instantanée du point coïncidant). On présente chaque liaison avec sa double notation (en colonne matricielle $3\times 2$ et intrinsèque en ligne) :

| Liaison | Classes | Famille normalisée & Réalisation technologique | DDL ($N_s / N_c$) & Typologie CM4 | Torseur cinématique $\{\mathcal{V}\}$ exprimé dans $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ |
| :--- | :---: | :--- | :---: | :--- |
| **$L_{01}$** | $E_0 \leftrightarrow E_1$ | **Pivot** d'axe $(O_1, \vec{z}_0)$<br>Roulements à billes du NEMA 17 $Z$ + coupleur alu fendu | $1\text{ DDL } (1\text{R}, 0\text{T})$<br>$N_c = 5$<br>**Torseur Glisseur** d'axe central $(O_1, \vec{z}_0)$ | $\{\mathcal{V}(E_1/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{10}(t) & 0 \end{Bmatrix}_{O_1, \mathcal{B}_0} = \left\{ \dot{\theta}_1(t)\,\vec{z}_0 \;;\; \vec{0} \right\}_{O_1}$ |
| **$L_{12}$** | $E_1 \leftrightarrow E_2$ | **Hélicoïdale** d'axe $(O_2, \vec{z}_0)$<br>Vis Tr8x8 + écrou laiton, filet à droite, $p_z = 8\text{ mm/tr}$ | $1\text{ DDL couplé}$<br>$N_c = 5$<br>**Torseur Hélicoïdal** ($I \neq 0$) | $\{\mathcal{V}(E_2/E_1)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & v_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0}$ avec $v_{21}(t) = +\dfrac{p_z}{2\pi}\,\omega_{21}(t)$ |
| **$L_{02}$** | $E_0 \leftrightarrow E_2$ | **Glissière** de direction $\vec{z}_0$ (en $O_3$)<br>6 galets V-wheels roulant sur les 2 profilés verticaux | $1\text{ DDL } (0\text{R}, 1\text{T})$<br>$N_c = 5$<br>**Torseur Couple** ($\vec{\Omega} = \vec{0}$) | $\{\mathcal{V}(E_2/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & \dot{z}_2(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_z(t)\,\vec{z}_0 \right\}_{\forall P}$ (Champ uniforme) |
| **$L_{23}$** | $E_2 \leftrightarrow E_3$ | **Glissière** de direction $\vec{x}_0$ (en $O_4$)<br>3 galets V-wheels guidés sur le profilé horizontal du portique | $1\text{ DDL } (0\text{R}, 1\text{T})$<br>$N_c = 5$<br>**Torseur Couple** ($\vec{\Omega} = \vec{0}$) | $\{\mathcal{V}(E_3/E_2)\} = \begin{Bmatrix} 0 & \dot{x}_3(t) \\ 0 & 0 \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_x(t)\,\vec{x}_0 \right\}_{\forall P}$ (Champ uniforme) |
| **$L_{04}$** | $E_0 \leftrightarrow E_4$ | **Glissière** de direction $\vec{y}_0$ (en $O_5$)<br>4 galets V-wheels guidés sur le rail central inférieur $Y$ | $1\text{ DDL } (0\text{R}, 1\text{T})$<br>$N_c = 5$<br>**Torseur Couple** ($\vec{\Omega} = \vec{0}$) | $\{\mathcal{V}(E_4/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & \dot{y}_4(t) \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \left\{ \vec{0} \;;\; V_y(t)\,\vec{y}_0 \right\}_{\forall P}$ (Champ uniforme) |

> [!WARNING]
> **Piège de concours MPSI (CM4 § 3.3) :** Le champ des accélérations des points d'un solide n'est **PAS** un torseur en raison du terme d'accélération centripète $\vec{\Omega} \wedge (\vec{\Omega} \wedge \vec{AB})$. De même, il n'est pas équiprojectif.

### 4.2. Fermeture cinématique de la chaîne fermée $Z$ ($E_0 - E_1 - E_2 - E_0$)

> **Règle absolue du cours CM4 (§ 4.3) :** Pour additionner des torseurs cinématiques, ils doivent **impérativement être exprimés au MÊME point géométrique**.

1. **Transport du torseur $\{\mathcal{V}(E_1/E_0)\}$ du point $O_1$ au point commun $O_2$ :**  
   En appliquant la formule fondamentale de Varignon sous sa forme mnémotechnique **BABAR** (CM4 § 1.4) :
   $$\vec{V}(O_2 \in E_1/E_0) = \vec{V}(O_1 \in E_1/E_0) + \overrightarrow{O_2 O_1} \wedge \vec{\Omega}(E_1/E_0)$$
   Comme $\overrightarrow{O_1 O_2} = z_2(t)\,\vec{z}_0 \iff \overrightarrow{O_2 O_1} = -z_2(t)\,\vec{z}_0$ et $\vec{\Omega}(E_1/E_0) = \omega_{10}(t)\,\vec{z}_0$ sont colinéaires :
   $$\vec{V}(O_2 \in E_1/E_0) = \vec{0} + \big(-z_2(t)\,\vec{z}_0\big) \wedge \big(\omega_{10}(t)\,\vec{z}_0\big) = \vec{0}$$

2. **Équation de fermeture cinématique en $O_2$ :**
   $$\{\mathcal{V}(E_2/E_0)\}_{O_2} = \{\mathcal{V}(E_2/E_1)\}_{O_2} + \{\mathcal{V}(E_1/E_0)\}_{O_2}$$
   $$\begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & v_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} + \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{10}(t) & 0 \end{Bmatrix}_{O_2, \mathcal{B}_0}$$

3. **Résolution scalaire et loi d'entrée-sortie :**
   $$\begin{cases}
   \text{Résultante selon } \vec{z}_0 : & 0 = \omega_{21}(t) + \omega_{10}(t) \implies \omega_{21}(t) = -\omega_{10}(t) = -\dot{\theta}_1(t) \\[6pt]
   \text{Moment en } O_2\text{ selon } \vec{z}_0 : & V_z(t) = v_{21}(t) + 0 = +\dfrac{p_z}{2\pi}\,\omega_{21}(t)
   \end{cases}$$
   $$\boxed{V_z(t) = \dot{z}_2(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t) = -\frac{p_z}{2\pi}\,\dot{\theta}_1(t) = +\frac{p_z}{2\pi}\,\omega_m(t)}$$
   où $\omega_m(t) = -\omega_{10}(t) > 0$ est la vitesse angulaire motrice de montée (rotation horaire de la vis vue de dessus).

4. **Cinématique de commande en trapèze de vitesse (CM4 § 5.3) :**  
   Pour éviter les à-coups mécaniques et respecter le couple de saturation du moteur pas-à-pas NEMA 17, la loi de vitesse $\dot{z}_2(t)$ est pilotée selon un profil trapézoïdal à 3 phases :
   - **Phase I (Accélération uniforme) :** $\ddot{z}_2(t) = +\gamma \implies \dot{z}_2(t) = \gamma t$ jusqu'à $V_{\max}$.
   - **Phase II (Régime permanent) :** $\ddot{z}_2(t) = 0 \implies \dot{z}_2(t) = V_{\max}$.
   - **Phase III (Décélération uniforme) :** $\ddot{z}_2(t) = -\gamma \implies \dot{z}_2(t) = -\gamma(t - t_2) + V_{\max}$.
   
   La course totale franchie $\Delta z_2$ s'obtient instantanément par la **méthode géométrique de l'aire** sous le trapèze :
   $$\Delta z_2 = \int_0^{t_3} \dot{z}_2(t)\,\mathrm{d}t = \frac{\big(t_3 + (t_2 - t_1)\big)\cdot V_{\max}}{2}$$
   Avec $p_z = 8\text{ mm/tr}$ et un micropas $1/16$ ($3200\text{ micropas/tr}$), la résolution théorique verticale est de $\delta z = 2{,}5\text{ }\mu\text{m}$.

---

## 5. Schéma Cinématique Minimal 2D en Couleur (Partie III — Exigence 3)

![Schéma cinématique minimal 2D en couleur de la Creality Ender 3](../04_schemas_cinematiques/schema_cinematique_2d.svg)

- **Vue frontale dans le plan $(O_0, \vec{x}_0, \vec{z}_0)$ :** Trièdre direct $\mathcal{R}_0$ avec $\vec{x}_0$ à droite, $\vec{z}_0$ en haut, et $\vec{y}_0$ entrant ($\otimes\,\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$).
- **Bijection des couleurs :** $E_0$ Noir, $E_1$ Bleu, $E_2$ Rouge, $E_3$ Vert, $E_4$ Orange.
- **Symboles AFNOR :** Butées axiales en $O_1$ (Pivot), traits de filetage obliques en $O_2$ (Hélicoïdale), croix diagonales internes sur les coulisseaux en $O_3$ et $O_4$ (Glissières), et glissière vue en bout barrée en $O_5$.

---

## 6. Schéma Cinématique Spatial 3D en Couleur (Partie III — Exigence 4)

![Schéma cinématique spatial 3D en couleur de la Creality Ender 3](../04_schemas_cinematiques/schema_cinematique_3d.svg)

- **Perspective cavalière :** Fuyante longitudinale $\vec{y}_0$ inclinée à $\alpha \approx 34^\circ$ (pente $-2/+3$) avec rapport de réduction $k \approx 0{,}6$.
- **Symboles 3D :** Cylindre à base elliptique et collerettes pour $L_{01}$, cylindre à spires hélicoïdales pour $L_{12}$, parallélépipèdes et prismes droits pour les glissières $L_{02}$, $L_{23}$, $L_{04}$. Toutes les arêtes orientées selon la profondeur sont strictement parallèles à la fuyante $\vec{y}_0$.
