# Identification des Classes d'Équivalence Cinématique ($E_k$)

**Système étudié :** Imprimante 3D à dépôt de fil fondu (FDM) **Creality Ender 3 (modèle de base)**  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI (Lycée Stanislas)  
**Référence de cours :** Séquence 2 — Cours CM4 : *Cinématique du Solide Indéformable* (§ 1.1 : *Hypothèse du solide indéformable*)  
**Conformité :** Norme AFNOR NF EN ISO 3952 — Schématisation cinématique

![Photo annotée du système Creality Ender 3 avec repères locaux et classes d'équivalence](../02_photos/RAMOS-Ender3-Details.png)

---

## 1. Hypothèses de Modélisation du Solide Indéformable (CM4 § 1.1)

En cinématique rationnelle du solide indéformable, un solide $S$ est dit **indéformable** si la distance géométrique entre deux points quelconques $A$ et $B$ appartenant au solide reste rigoureusement invariante au cours du temps :
$$\forall A, B \in S, \quad \|\vec{AB}\| = \text{constante} \iff \vec{AB}^2 = \text{constante}$$

En conséquence directe :
> Dans tout repère orthonormé direct $\mathcal{R}_S(O_S, \vec{x}_S, \vec{y}_S, \vec{z}_S)$ lié rigidement au solide $S$, le vecteur $\vec{AB}$ est un **vecteur fixe** :
> $$\left.\frac{\mathrm{d}\vec{AB}}{\mathrm{d}t}\right|_{\mathcal{R}_S} = \vec{0}$$

### 1.1. Définition d'une Classe d'Équivalence Cinématique
Une **classe d'équivalence cinématique** (notée $E_k$) regroupe l'ensemble des pièces mécaniques réelles qui sont en **liaison encastrement complète mutuelle** (aucun mouvement relatif possible entre elles) durant la **phase d'impression 3D nominale**. Pour l'étude cinématique, chaque classe $E_k$ est assimilée à un unique solide indéformable idéal.

### 1.2. Organes Exclus des Classes d'Équivalence
1. **Les solides déformables :**
   - Les **courroies crantées souples GT2** des axes $X$ et $Y$ sont des corps déformables en flexion et en translation. Elles constituent la motorisation interne et n'appartiennent à aucune classe d'équivalence.
   - Les **4 ressorts hélicoïdaux de précontrainte** sous le plateau chauffant ne travaillent que lors du réglage manuel initial. En cours d'impression, ils maintiennent le lit rigide sur sa platine (classe $E_4$).
   - Le **tube Bowden en PTFE** guidant le filament polymère et les faisceaux électriques suivent passivement les mouvements sans imposer de guidage mécanique.
2. **Les corps roulants de guidage :**
   - Les bagues extérieures en polyoxyméthylène (POM / Delrin) et les billes d'acier des **13 galets à profil en V (*V-wheels*)** (6 sur l'axe $Z$, 3 sur l'axe $X$, 4 sur l'axe $Y$) assurent le contact de roulement au sein des liaisons glissières. En revanche, leurs **axes boulonnés**, leurs **entretoises cylindriques**, leurs **excentriques de réglage** et leurs **bagues intérieures** sont solidaires du chariot qui les porte.

---

## 2. Tableau Récapitulatif des 5 Classes d'Équivalence ($E_0$ à $E_4$)

À chaque classe d'équivalence cinématique $E_k$ est associé un **repère local orthonormé direct $\mathcal{R}_k$** lié rigidement au solide $E_k$, ainsi qu'une **couleur normalisée unique** respectée rigoureusement sur les schémas cinématiques 2D et 3D :

| Classe | Désignation fonctionnelle | Repère local lié | Couleur normalisée | Mouvement / Rôle cinématique par rapport à $\mathcal{R}_0$ |
| :--- | :--- | :--- | :--- | :--- |
| **$E_0$** | **Bâti fixe** (Châssis V-Slot) | $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Noir** (`#0f172a`) | Référence fixe au repos sur la table ($\underline{\underline{\equiv\mkern-10mu\perp}}$) |
| **$E_1$** | **Arbre moteur & Vis mère $Z$** | $\mathcal{R}_1(O_1, \vec{x}_1, \vec{y}_1, \vec{z}_0)$ | **Bleu** (`#2563eb`) | Rotation d'angle $\theta_1(t)$ autour de l'axe vertical $(O_1, \vec{z}_0)$ |
| **$E_2$** | **Portique mobile horizontal $X$** | $\mathcal{R}_2(O_3, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Rouge** (`#dc2626`) | Translation rectiligne verticale $z_2(t)\,\vec{z}_0$ |
| **$E_3$** | **Chariot de tête d'impression** | $\mathcal{R}_3(O_4, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Vert** (`#16a34a`) | Translation rectiligne transversale $x_3(t)\,\vec{x}_0$ par rapport à $E_2$ |
| **$E_4$** | **Plateau chauffant mobile $Y$** | $\mathcal{R}_4(O_5, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Orange** (`#ea580c`) | Translation rectiligne longitudinale $y_4(t)\,\vec{y}_0$ par rapport à $E_0$ |

---

## 3. Inventaire Exhaustif des Pièces Réelles par Classe d'Équivalence

> **Règle impérative du barème :** *« Si les classes d'équivalence ne sont pas claires (par exemple un numéro seul sans indication des pièces), le graphe ne sera pas corrigé et aucun point ne sera attribué pour la suite du DM. »*

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
