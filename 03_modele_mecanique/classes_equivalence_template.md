# Identification des Classes d'Équivalence Cinématique ($E_k$)

**Système étudié :** Imprimante 3D à dépôt de fil fondu (FDM) **Creality Ender 3 (modèle de base)**  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI  
**Référence :** DM n°1 — Modélisation des liaisons et Schématisation cinématique

![Photo annotée du système Creality Ender 3 avec repères locaux et classes d'équivalence](../02_photos/RAMOS-Ender3-Details.png)

---

## 1. Hypothèses de modélisation et frontière d'étude

Pour modéliser la chaîne cinématique de positionnement spatial $(X, Y, Z)$ de la buse d'extrusion par rapport au plateau d'impression en **phase d'impression nominale**, on adopte les hypothèses de la mécanique des solides indéformables :

1. **Indéformabilité des solides :** Tous les composants structurels (profilés aluminium V-Slot, platines en acier pliées, vis mère en acier inoxydable, tiges et carters) sont supposés parfaitement rigides.
2. **Exclusion des organes déformables de transmission :**
   - Les **courroies crantées souples GT2** des axes $X$ et $Y$ étant des solides déformables, elles n'appartiennent à aucune classe d'équivalence de solides indéformables. Elles constituent la *motorisation interne* qui impose les lois d'entrée $x_3(t)$ et $y_4(t)$.
   - Les **4 ressorts hélicoïdaux de nivellement** sous le plateau chauffant ne sont sollicités que lors du réglage manuel initial (hors impression). En cours d'impression, leur précontrainte maintient le plateau chauffant rigide vis-à-vis de sa platine support en aluminium : l'ensemble forme alors un unique sous-ensemble rigide $E_4$.
   - Le **tube Bowden en PTFE** et les nappes électriques souples suivent passivement les mouvements sans imposer de contrainte géométrique.
3. **Exclusion des éléments roulants de guidage :** Les bagues extérieures en polyoxyméthylène (POM / Delrin) et les billes des **13 galets à profil en V (*V-wheels*)** (6 sur l'axe $Z$, 3 sur l'axe $X$, 4 sur l'axe $Y$) assurent le contact roulant au sein des liaisons glissières $L_{02}$, $L_{23}$ et $L_{04}$. En revanche, leurs **axes vissés**, leurs **entretoises**, leurs **excentriques de réglage** (une fois serrés) et les **bagues intérieures** des roulements sont solidaires du chariot qui les porte.

---

## 2. Tableau récapitulatif des 5 classes d'équivalence ($E_0$ à $E_4$)

À chaque classe d'équivalence cinématique $E_k$ est associé un **repère local orthonormé direct $\mathcal{R}_k$** lié rigidement au solide $E_k$, ainsi qu'une **couleur normalisée unique** respectée sur l'ensemble des schémas cinématiques 2D et 3D :

| Classe | Désignation fonctionnelle | Repère local lié | Couleur normalisée | Mouvement / Rôle cinématique |
| :--- | :--- | :--- | :--- | :--- |
| **$E_0$** | **Bâti fixe** (Châssis V-Slot) | $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Noir** (`#0f172a`) | Référence fixe posée sur la table ($\underline{\underline{\equiv\mkern-10mu\perp}}$) |
| **$E_1$** | **Arbre moteur & Vis mère $Z$** | $\mathcal{R}_1(O_1, \vec{x}_1, \vec{y}_1, \vec{z}_0)$ | **Bleu** (`#2563eb`) | Rotation $\theta_1(t)$ d'axe $(O_1, \vec{z}_0)$ |
| **$E_2$** | **Portique mobile horizontal $X$** | $\mathcal{R}_2(O_3, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Rouge** (`#dc2626`) | Translation verticale $z_2(t)\,\vec{z}_0$ |
| **$E_3$** | **Chariot de tête d'impression** | $\mathcal{R}_3(O_4, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Vert** (`#16a34a`) | Translation horizontale $x_3(t)\,\vec{x}_0$ / $E_2$ |
| **$E_4$** | **Plateau chauffant mobile $Y$** | $\mathcal{R}_4(O_5, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Orange** (`#ea580c`) | Translation longitudinale $y_4(t)\,\vec{y}_0$ / $E_0$ |

---

## 3. Inventaire exhaustif des pièces par classe d'équivalence

> **Règle impérative du barème (Partie III) :** *« Si les classes d'équivalence ne sont pas claires (par exemple un numéro seul sans indication des pièces), le graphe ne sera pas corrigé et aucun point ne sera attribué pour la suite du DM. »*  
> Chaque sous-ensemble ci-dessous détaille explicitement toutes les pièces mécaniques solidaires (en liaison encastrement mutuelle).

### 3.1. Classe $E_0$ — Bâti fixe (Couleur : Noir — Repère de référence $\mathcal{R}_0$)
$$E_0 = \left\{ \begin{array}{l}
\text{Cadre inférieur en profilés aluminium extrudés V-Slot } 40\times 40\text{ mm (2 longerons latéraux + traverse centrale)}, \\
\text{Rail central de guidage } Y\text{ en profilé aluminium V-Slot } 40\times 40\text{ mm (orienté selon } \vec{y}_0\text{)}, \\
\text{2 montants verticaux (colonnes } Z\text{ gauche et droite) en profilé aluminium V-Slot } 20\times 40\text{ mm (selon } \vec{z}_0\text{)}, \\
\text{Traverse supérieure horizontale en profilé aluminium } 20\times 20\text{ mm et porte-bobine métallique supérieur}, \\
\text{4 patins amortisseurs en caoutchouc sous la base et visserie d'assemblage M5 du châssis}, \\
\text{Corps (stator + flasques + équerre de fixation) du moteur pas-à-pas NEMA 17 de l'axe } Z, \\
\text{Corps (stator + support métallique arrière) du moteur pas-à-pas NEMA 17 de l'axe } Y, \\
\text{Support tendeur avant de courroie } Y\text{ et axe de la poulie folle avant } Y, \\
\text{Bloc d'alimentation à découpage 24 V (MeanWell / Creality) vissé sur le montant vertical droit}, \\
\text{Boîtier métallique inférieur de la carte mère et châssis de l'écran de contrôle LCD avant droit}, \\
\text{Corps des interrupteurs de fin de course (Endstops) des axes } Z\text{ (montant gauche) et } Y\text{ (rail arrière)}.
\end{array} \right\}$$

### 3.2. Classe $E_1$ — Ensemble tournant d'entraînement $Z$ (Couleur : Bleu — Repère $\mathcal{R}_1$)
$$E_1 = \left\{ \begin{array}{l}
\text{Rotor et arbre de sortie cylindrique ($\varnothing 5\text{ mm}$, méplat en D) du moteur pas-à-pas NEMA 17 de l'axe } Z, \\
\text{Manchon d'accouplement (coupleur) cylindrique fendu en alliage d'aluminium}, \\
\text{2 vis de pression cylindriques à six pans creux (CHC M3) verrouillant le coupleur sur l'arbre moteur et la vis}, \\
\text{Vis mère trapézoïdale en acier inoxydable Tr8x8 ($\varnothing_{\text{nom}} = 8\text{ mm}$, filetage à droite, pas } p_z = 8\text{ mm/tr)}.
\end{array} \right\}$$

### 3.3. Classe $E_2$ — Portique mobile horizontal $X$ (Couleur : Rouge — Repère $\mathcal{R}_2$)
$$E_2 = \left\{ \begin{array}{l}
\text{Profilé aluminium horizontal de guidage } X\text{ V-Slot } 20\times 20\text{ mm (orienté selon } \vec{x}_0\text{)}, \\
\text{Platine support gauche en acier peint en noir (support moteur } X\text{ et extrudeur) et platine support droite}, \\
\text{Écrou trapézoïdal en laiton Tr8x8 fixé sur la platine gauche par 2 vis M3 et rondelles frein}, \\
\text{Axes boulonnés M5, entretoises cylindriques, excentriques de réglage et bagues intérieures des 6 galets } Z, \\
\text{Corps (stator) du moteur pas-à-pas NEMA 17 de l'axe } X\text{ et corps du moteur NEMA 17 de l'extrudeur MK8}, \\
\text{Corps fixe de l'extrudeur MK8, capot plastique du capteur } X\text{-Endstop et support tendeur droit de courroie } X.
\end{array} \right\}$$

### 3.4. Classe $E_3$ — Chariot de tête d'impression / Hotend (Couleur : Vert — Repère $\mathcal{R}_3$)
$$E_3 = \left\{ \begin{array}{l}
\text{Platine chariot } X\text{ en acier plié peint en noir (avec fentes d'ancrage des deux brins de la courroie GT2)}, \\
\text{Axes boulonnés M5, entretoises, écrou excentrique inférieur et bagues intérieures des 3 galets V-wheels } X, \\
\text{Corps complet de la tête chaude (Hotend MK8) : raccord pneumatique supérieur PC4-M10, dissipateur thermique} \\
\quad \text{à ailettes en aluminium anodisé rouge, barrière thermique (heatbreak), bloc de chauffe en aluminium}, \\
\text{Cartouche chauffante (24 V / 40 W), thermistance CTN 100 k$\Omega$ et buse d'extrusion en laiton ($\varnothing 0{,}4\text{ mm}$)}, \\
\text{Carénage métallique de ventilation et stators des 2 ventilateurs (axial frontal 4010 et radial latéral 4010)}.
\end{array} \right\}$$

### 3.5. Classe $E_4$ — Plateau chauffant mobile $Y$ (Couleur : Orange — Repère $\mathcal{R}_4$)
$$E_4 = \left\{ \begin{array}{l}
\text{Platine inférieure de chariot } Y\text{ en alliage d'aluminium découpé (forme en H/Y sous le lit)}, \\
\text{Axes boulonnés M5, entretoises, 2 excentriques droits et bagues intérieures des 4 galets V-wheels } Y, \\
\text{4 vis fraisées M4 et 4 molettes crantées de nivellement (bloquées en position pendant l'impression)}, \\
\text{Plaque chauffante supérieure en aluminium ($235\times 235\times 3\text{ mm}$, circuit résistif 24 V / 220 W)}, \\
\text{Revêtement d'adhérence amovible (BuildTak / verre) maintenu par 4 pinces métalliques et pièce imprimée}.
\end{array} \right\}$$
