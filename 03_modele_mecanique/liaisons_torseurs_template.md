# Répertoire des Liaisons Mécaniques et Torseurs Cinématiques ($\{\mathcal{V}(E_j/E_i)\}$)

**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI  
**Conformité :** Norme AFNOR NF EN ISO 3952 — Modélisation des liaisons parfaites

---

## 1. Synthèse des 5 liaisons élémentaires du système

> **Validation de la consigne (Partie I) :** Le système étudié présente **5 liaisons mécaniques élémentaires** réparties en **3 familles de liaisons normalisées distinctes** :
> 1. **Liaison Pivot** ($L_{01}$) — 1 degré de liberté en rotation ($1\text{ R}, 0\text{ T}$) ;
> 2. **Liaison Hélicoïdale** ($L_{12}$) — 1 degré de liberté conjugué rotation-translation ($1\text{ R conjuguée à } 1\text{ T}$) ;
> 3. **Liaison Glissière** ($L_{02}$, $L_{23}$, $L_{04}$) — 1 degré de liberté en translation rectiligne selon les trois directions orthogonales de l'espace ($\vec{z}_0$, $\vec{x}_0$, $\vec{y}_0$).

| Code | Classes reliées | Famille normalisée (AFNOR) | Caractéristique géométrique | Degrés de liberté ($N_c$) | Paramètre cinématique |
| :--- | :--- | :--- | :--- | :---: | :--- |
| **$L_{01}$** | $E_0 \leftrightarrow E_1$ | **Pivot** | Axe $(O_1, \vec{z}_0)$ | $1$ ($\text{R}_{z_0}$) | $\theta_1(t) = (\widehat{\vec{x}_0, \vec{x}_1})$ |
| **$L_{12}$** | $E_1 \leftrightarrow E_2$ | **Hélicoïdale** (filet à droite) | Axe $(O_2, \vec{z}_0) = (O_1, \vec{z}_0)$, pas $p_z = 8\text{ mm/tr}$ | $1$ ($\text{R}_{z_0}\text{-T}_{z_0}$ liés) | $\omega_{21}(t)$ et $v_{21}(t) = +\frac{p_z}{2\pi}\omega_{21}(t)$ |
| **$L_{02}$** | $E_0 \leftrightarrow E_2$ | **Glissière** | Direction $\vec{z}_0$ (en $O_3$) | $1$ ($\text{T}_{z_0}$) | $z_2(t)\,\vec{z}_0$ ($\dot{z}_2(t) = V_z(t)$) |
| **$L_{23}$** | $E_2 \leftrightarrow E_3$ | **Glissière** | Direction $\vec{x}_0$ (en $O_4$) | $1$ ($\text{T}_{x_0}$) | $x_3(t)\,\vec{x}_0$ ($\dot{x}_3(t) = V_x(t)$) |
| **$L_{04}$** | $E_0 \leftrightarrow E_4$ | **Glissière** | Direction $\vec{y}_0$ (en $O_5$) | $1$ ($\text{T}_{y_0}$) | $y_4(t)\,\vec{y}_0$ ($\dot{y}_4(t) = V_y(t)$) |

---

## 2. Analyse détaillée et écriture des torseurs cinématiques dans $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$

### 2.1. Liaison $L_{01}$ entre le bâti $E_0$ et la vis mère $E_1$ : Liaison Pivot d'axe $(O_1, \vec{z}_0)$
- **Réalisation technologique :** Guidage en rotation assuré en interne par les deux roulements rigides à billes du moteur pas-à-pas NEMA 17 de l'axe $Z$ (dont le stator est encastré sur le montant gauche de $E_0$), prolongé par le coupleur rigide fendu en aluminium vers la vis trapézoïdale $E_1$.
- **Degrés de liberté :** 1 rotation d'axe $(O_1, \vec{z}_0)$ ; 0 translation ($\forall P \in (O_1, \vec{z}_0),\; \vec{V}(P \in E_1/E_0) = \vec{0}$).
- **Torseur cinématique en tout point $P$ de l'axe $(O_1, \vec{z}_0)$ :**
  $$\{\mathcal{V}(E_1/E_0)\} = \begin{Bmatrix} \vec{\Omega}(E_1/E_0) = \omega_{10}(t)\,\vec{z}_0 \\ \vec{V}(O_1 \in E_1/E_0) = \vec{0} \end{Bmatrix}_{O_1} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{10}(t) & 0 \end{Bmatrix}_{O_1, \mathcal{B}_0} \quad \text{avec } \omega_{10}(t) = \dot{\theta}_1(t)$$

---

### 2.2. Liaison $L_{12}$ entre la vis mère $E_1$ et le portique $E_2$ : Liaison Hélicoïdale d'axe $(O_2, \vec{z}_0)$
- **Réalisation technologique :** Contact hélicoïdal entre la vis trapézoïdale en acier inoxydable Tr8x8 ($E_1$, diamètre nominal $8\text{ mm}$, filetage à 4 filets à droite, avance par tour / pas hélicoïdal $p_z = 8\text{ mm/tr}$) et l'écrou trapézoïdal en laiton fixé sur la platine gauche du portique ($E_2$). L'axe $(O_2, \vec{z}_0)$ est confondu avec $(O_1, \vec{z}_0)$.
- **Loi de conjugaison hélicoïdale intrinsèque (filetage à droite dans un repère direct $\mathcal{B}_0$) :**
  Pour une liaison hélicoïdale à **filetage à droite** d'axe $(O_2, \vec{z}_0)$ exprimée dans la base directe $\mathcal{B}_0$, le vecteur vitesse de glissement et le vecteur taux de rotation le long de l'axe sont de **même signe** :
  $$\vec{V}(O_2 \in E_2/E_1) = +\frac{p_z}{2\pi}\,\vec{\Omega}(E_2/E_1) \quad \Longleftrightarrow \quad v_{21}(t) = +\frac{p_z}{2\pi}\,\omega_{21}(t)$$
- **Torseur cinématique au centre $O_2$ (ou en tout point de l'axe $(O_1, \vec{z}_0)$) :**
  $$\{\mathcal{V}(E_2/E_1)\} = \begin{Bmatrix} \vec{\Omega}(E_2/E_1) = \omega_{21}(t)\,\vec{z}_0 \\ \vec{V}(O_2 \in E_2/E_1) = v_{21}(t)\,\vec{z}_0 \end{Bmatrix}_{O_2} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & +\dfrac{p_z}{2\pi}\,\omega_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0}$$

> **Point de vigilance méthodologique (Sens physique de montée du portique $E_2$) :**  
> Dans la Creality Ender 3, l'écrou laiton $E_2$ est **bloqué en rotation** par rapport au bâti $E_0$ par la liaison glissière $L_{02}$ ($\vec{\Omega}(E_2/E_0) = \vec{0}$).  
> Par composition des rotations :
> $$\vec{\Omega}(E_2/E_0) = \vec{\Omega}(E_2/E_1) + \vec{\Omega}(E_1/E_0) = \vec{0} \quad \Longrightarrow \quad \omega_{21}(t) = -\omega_{10}(t)$$
> Par conséquent, la vitesse verticale d'élévation du portique $E_2$ par rapport au bâti $E_0$ vaut :
> $$V_z(t) = \dot{z}_2(t) = v_{21}(t) = +\frac{p_z}{2\pi}\,\omega_{21}(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t)$$
> - Pour faire **monter** le portique ($V_z(t) > 0$), l'écrou $E_2$ doit décrire un mouvement relatif positif par rapport à la vis ($\omega_{21}(t) > 0$), ce qui impose que la vis mère $E_1$ tourne dans le **sens horaire vue de dessus** par rapport au bâti ($\omega_{10}(t) = -\omega_m(t) < 0$, où $\omega_m(t) = |\omega_{10}(t)| > 0$ est la vitesse angulaire motrice de montée) :
>   $$V_z(t) = +\frac{p_z}{2\pi}\,\omega_m(t)$$

---

### 2.3. Liaison $L_{02}$ entre le bâti $E_0$ et le portique $E_2$ : Liaison Glissière de direction $\vec{z}_0$
- **Réalisation technologique :** Guidage prismatique bilatéral assuré par **6 galets en POM à profil en V (*V-wheels*)** (3 galets sur la platine gauche, 3 galets sur la platine droite de $E_2$, chacun muni d'un excentrique de précontrainte) roulant sans glisser dans les rainures des deux montants verticaux V-Slot $20\times 40\text{ mm}$ du bâti $E_0$. Sur le schéma cinématique minimal, ces deux guidages parallèles redondants sont représentés par **une unique liaison glissière équivalente $L_{02}$** de centre $O_3$ et de direction $\vec{z}_0$.
- **Propriété du champ des vitesses (translation pure) :** $\vec{\Omega}(E_2/E_0) = \vec{0}$, donc le champ des vecteurs vitesse est uniforme ($\forall P,\; \vec{V}(P \in E_2/E_0) = V_z(t)\,\vec{z}_0 = \dot{z}_2(t)\,\vec{z}_0$).
- **Torseur cinématique en tout point $P$ de l'espace (en particulier en $O_3$ et en $O_2$) :**
  $$\{\mathcal{V}(E_2/E_0)\} = \begin{Bmatrix} \vec{\Omega}(E_2/E_0) = \vec{0} \\ \vec{V}(O_3 \in E_2/E_0) = V_z(t)\,\vec{z}_0 \end{Bmatrix}_{O_3} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & \dot{z}_2(t) \end{Bmatrix}_{\forall P, \mathcal{B}_0}$$

---

### 2.4. Liaison $L_{23}$ entre le portique $E_2$ et la tête d'impression $E_3$ : Liaison Glissière de direction $\vec{x}_0$
- **Réalisation technologique :** Guidage prismatique assuré par **3 galets V-wheels** portés par la platine du chariot de tête $E_3$ (2 galets supérieurs à axes fixes et 1 galet inférieur monté sur écrou excentrique) roulant dans les rainures du profilé aluminium horizontal V-Slot $20\times 20\text{ mm}$ du portique $E_2$. La translation selon $\vec{x}_0$ est commandée par le moteur NEMA 17 de l'axe $X$ via une courroie crantée GT2.
- **Torseur cinématique en tout point $P$ de l'espace (en particulier en $O_4$) :**
  $$\{\mathcal{V}(E_3/E_2)\} = \begin{Bmatrix} \vec{\Omega}(E_3/E_2) = \vec{0} \\ \vec{V}(O_4 \in E_3/E_2) = V_x(t)\,\vec{x}_0 \end{Bmatrix}_{O_4} = \begin{Bmatrix} 0 & \dot{x}_3(t) \\ 0 & 0 \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0}$$

---

### 2.5. Liaison $L_{04}$ entre le bâti $E_0$ et le plateau chauffant $E_4$ : Liaison Glissière de direction $\vec{y}_0$
- **Réalisation technologique :** Guidage prismatique assuré par **4 galets V-wheels** (2 galets gauches à axes fixes et 2 galets droits montés sur écrous excentriques) portés par la platine inférieure en aluminium du plateau $E_4$, roulant dans les rainures latérales du profilé central V-Slot $40\times 40\text{ mm}$ du bâti $E_0$. La translation selon $\vec{y}_0$ est commandée par le moteur NEMA 17 de l'axe $Y$ via une courroie crantée GT2.
- **Torseur cinématique en tout point $P$ de l'espace (en particulier en $O_5$) :**
  $$\{\mathcal{V}(E_4/E_0)\} = \begin{Bmatrix} \vec{\Omega}(E_4/E_0) = \vec{0} \\ \vec{V}(O_5 \in E_4/E_0) = V_y(t)\,\vec{y}_0 \end{Bmatrix}_{O_5} = \begin{Bmatrix} 0 & 0 \\ 0 & \dot{y}_4(t) \\ 0 & 0 \end{Bmatrix}_{\forall P, \mathcal{B}_0}$$
