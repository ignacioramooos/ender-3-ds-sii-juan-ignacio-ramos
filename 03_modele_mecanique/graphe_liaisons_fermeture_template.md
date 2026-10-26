# Graphe des Liaisons Normalisé et Fermeture Cinématique

**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI (Lycée Stanislas)  
**Référence de cours :** Séquence 2 — Cours CM4 : *Cinématique du Solide Indéformable* (§ 4 : *Composition de mouvements*, § 5 : *Mouvements élémentaires*)  
**Conformité :** Norme AFNOR NF EN ISO 3952 — Analyse topologique et cinématique des systèmes

![Graphe des liaisons normalisé de la Creality Ender 3](../04_schemas_cinematiques/graphe_des_liaisons.svg)

---

## 1. Analyse Topologique de la Structure Cinématique

### 1.1. Décompte des sommets, des arcs et nombre cyclomatique $\gamma$
Le graphe des liaisons comporte :
- **$N = 5$ sommets** représentant les **5 classes d'équivalence cinématique indéformables** : $E_0, E_1, E_2, E_3, E_4$. Chaque sommet détaille explicitement ses pièces physiques constitutives et son repère local associé ($\mathcal{R}_0$ à $\mathcal{R}_4$). Le bâti fixe $E_0$ est mis en valeur par un double contour renforcé et le symbole normalisé de masse ($\underline{\underline{\equiv\mkern-10mu\perp}}$).
- **$L = 5$ arcs** représentant les **5 liaisons élémentaires normalisées** : $L_{01}, L_{12}, L_{02}, L_{23}, L_{04}$, issues de **3 familles de liaisons distinctes** (Pivot, Hélicoïdale, Glissière).
- **Nombre cyclomatique $\gamma$ du graphe :**
  $$\gamma = L - N + 1 = 5 - 5 + 1 = 1$$

### 1.2. Décomposition en sous-chaînes cinématiques
La valeur $\gamma = 1$ caractérise une **architecture cinématique hybride (série-parallèle)** composée de :
1. **Une chaîne cinématique fermée élémentaire ($\gamma = 1$) : Boucle d'élévation verticale $Z$ ($E_0 - E_1 - E_2 - E_0$)**  
   Elle transforme la rotation commandée de la vis mère $E_1$ (liaison Pivot $L_{01}$) en une translation verticale pure du portique $E_2$ (liaison Glissière $L_{02}$) via la liaison Hélicoïdale $L_{12}$.
2. **Deux chaînes cinématiques ouvertes indépendantes (structures séries) :**
   - **Branche transversale $X$ ($E_2 - E_3$) :** Liaison Glissière $L_{23}$ de direction $\vec{x}_0$ portée par le portique $E_2$, permettant à la tête d'impression $E_3$ de balayer la largeur du plateau tout en étant entraînée verticalement par $E_2$.
   - **Branche longitudinale $Y$ ($E_0 - E_4$) :** Liaison Glissière $L_{04}$ de direction $\vec{y}_0$ directement liée au bâti $E_0$, assurant le déplacement avant/arrière du plateau chauffant $E_4$ indépendamment du portique $(X, Z)$.

---

## 2. Fermeture Cinématique de la Boucle d'Élévation $Z$ ($E_0 - E_1 - E_2 - E_0$)

### 2.1. Règle Impérative Fondamentale du Cours CM4 (§ 4.3)
> [!IMPORTANT]
> **Règle absolue d'addition des torseurs :**  
> Pour sommer des torseurs cinématiques, ils doivent **IMPÉRATIVEMENT être exprimés au MÊME point géométrique $P$**.  
> Si les torseurs sont donnés en des points différents, il faut impérativement utiliser la **formule de Varignon (Règle BABAR)** pour les transporter au point commun choisi avant toute addition !

La relation de composition de mouvements s'écrit :
$$\{\mathcal{V}(E_2/E_0)\}_P = \{\mathcal{V}(E_2/E_1)\}_P + \{\mathcal{V}(E_1/E_0)\}_P$$

### 2.2. Choix du point de réduction commun $O_2$
Les axes des liaisons Pivot $L_{01}$ et Hélicoïdale $L_{12}$ sont confondus selon la droite $(O_1, \vec{z}_0) = (O_2, \vec{z}_0)$ ($\overrightarrow{O_1 O_2} = z_2(t)\,\vec{z}_0$).  
Par ailleurs, la liaison $L_{02}$ étant une glissière, son torseur est un **torseur couple** (vecteur vitesse uniforme en tout point).  
On choisit donc le point de réduction commun **$O_2$** (centre de l'écrou en laiton) dans la base fixe **$\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$** :

1. **Transport de $\{\mathcal{V}(E_1/E_0)\}$ de $O_1$ en $O_2$ via la formule de Varignon (Règle BABAR — CM4 § 1.4) :**
   $$\vec{V}(O_2 \in E_1/E_0) = \vec{V}(O_1 \in E_1/E_0) + \overrightarrow{O_2 O_1} \wedge \vec{\Omega}(E_1/E_0)$$
   Comme $\overrightarrow{O_2 O_1} = -z_2(t)\,\vec{z}_0$ et $\vec{\Omega}(E_1/E_0) = \omega_{10}(t)\,\vec{z}_0$ sont deux vecteurs colinéaires, leur produit vectoriel est nul :
   $$\vec{V}(O_2 \in E_1/E_0) = \vec{0} + \big(-z_2(t)\,\vec{z}_0\big) \wedge \big(\omega_{10}(t)\,\vec{z}_0\big) = \vec{0}$$
   D'où :
   $$\{\mathcal{V}(E_1/E_0)\}_{O_2} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{10}(t) & 0 \end{Bmatrix}_{O_2, \mathcal{B}_0} \quad \text{avec } \omega_{10}(t) = \dot{\theta}_1(t)$$

2. **Torseur de la liaison Hélicoïdale $L_{12}$ en $O_2$ (filet à droite, pas $p_z = 8\text{ mm/tr}$) :**
   $$\{\mathcal{V}(E_2/E_1)\}_{O_2} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & v_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} \quad \text{avec } v_{21}(t) = +\frac{p_z}{2\pi}\,\omega_{21}(t)$$

3. **Torseur de la liaison Glissière $L_{02}$ en $O_2$ (torseur couple) :**
   $$\{\mathcal{V}(E_2/E_0)\}_{O_2} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} \quad \text{avec } V_z(t) = \dot{z}_2(t)$$

### 2.3. Résolution scalaire et loi d'entrée-sortie
L'égalité matricielle des torseurs en $O_2$ s'écrit :
$$\begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) + \omega_{10}(t) & v_{21}(t) + 0 \end{Bmatrix}_{O_2, \mathcal{B}_0}$$

En projetant sur l'axe $\vec{z}_0$, on obtient le système de deux équations scalaires :
$$\begin{cases}
\text{Équation de résultante (rotation selon } \vec{z}_0\text{) :} & 0 = \omega_{21}(t) + \omega_{10}(t) \quad \Longrightarrow \quad \omega_{21}(t) = -\omega_{10}(t) = -\dot{\theta}_1(t) \\[6pt]
\text{Équation de moment (vitesse selon } \vec{z}_0\text{) :} & V_z(t) = v_{21}(t) = +\dfrac{p_z}{2\pi}\,\omega_{21}(t)
\end{cases}$$

En substituant $\omega_{21}(t) = -\omega_{10}(t)$, on en déduit la **loi d'entrée-sortie cinématique** :
$$\boxed{V_z(t) = \dot{z}_2(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t) = -\frac{p_z}{2\pi}\,\dot{\theta}_1(t) = +\frac{p_z}{2\pi}\,\omega_m(t)}$$
où $\omega_m(t) = -\omega_{10}(t) > 0$ représente la vitesse angulaire motrice de montée (sens horaire de la vis vue de dessus).

### 2.4. Cinématique de commande : Profil de vitesse trapézoïdal (CM4 § 5.3)
Dans les imprimantes 3D équipées de moteurs pas-à-pas NEMA 17, afin de limiter les sollicitations dynamiques et l'à-coup mécanique ($\dot{\gamma}$), le contrôleur applique une **loi de commande en trapèze de vitesse** :
- **Phase I (Accélération uniforme) :** $\ddot{z}_2(t) = +\gamma \implies \dot{z}_2(t) = \gamma t$ jusqu'à atteindre $V_{\max}$.
- **Phase II (Régime permanent uniforme) :** $\ddot{z}_2(t) = 0 \implies \dot{z}_2(t) = V_{\max}$.
- **Phase III (Décélération uniforme) :** $\ddot{z}_2(t) = -\gamma \implies \dot{z}_2(t) = -\gamma(t - t_2) + V_{\max}$.

La course totale franchie $\Delta z_2$ s'obtient instantanément par la **méthode géométrique de l'aire du trapèze** :
$$\Delta z_2 = \int_0^{t_3} \dot{z}_2(t)\,\mathrm{d}t = \frac{\big(t_3 + (t_2 - t_1)\big)\cdot V_{\max}}{2}$$

- **Application numérique Creality Ender 3 :**
  Pour un pas $p_z = 8\text{ mm/tr}$, un tour complet du moteur élève le portique de $8\text{ mm}$.  
  Avec $200\text{ pas/tr}$ et un micro-stepping $1/16$ ($3200\text{ micropas/tr}$, soit $400\text{ micropas/mm}$), la résolution théorique par micropas est de $\delta z = 2{,}5\text{ }\mu\text{m}$.

---

## 3. Loi de Vitesse Relative Buse / Plateau ($E_3 / E_4$)

Pour la dépose du filament, la trajectoire d'impression est définie par la vitesse de la buse ($O_4 \in E_3$) par rapport au lit d'impression ($E_4$).  
Par composition des torseurs le long de la chaîne ouverte reliant $E_4$ à $E_3$ via $E_0$ et $E_2$ :
$$\{\mathcal{V}(E_3/E_4)\} = \{\mathcal{V}(E_3/E_2)\} + \{\mathcal{V}(E_2/E_0)\} + \{\mathcal{V}(E_0/E_4)\} = \{\mathcal{V}(E_3/E_2)\} + \{\mathcal{V}(E_2/E_0)\} - \{\mathcal{V}(E_4/E_0)\}$$

Les trois mouvements relatifs étant des translations pures de directions orthogonales deux à deux ($\vec{x}_0, \vec{z}_0, \vec{y}_0$), la résultante globale est identiquement nulle ($\vec{\Omega}(E_3/E_4) = \vec{0}$).  
Le torseur cinématique buse/plateau est un **torseur couple** s'écrivant en tout point $P$ :
$$\boxed{\{\mathcal{V}(E_3/E_4)\} = \begin{Bmatrix} 0 & V_x(t) \\ 0 & -V_y(t) \\ 0 & V_z(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0} = \begin{Bmatrix} 0 & \dot{x}_3(t) \\ 0 & -\dot{y}_4(t) \\ 0 & +\dfrac{p_z}{2\pi}\,\omega_m(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0}}$$
Ce torseur valide le découplage cartésien total des trois axes de la Creality Ender 3.
