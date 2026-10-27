# Identification des Sous-ensembles Cinématiques

**Système étudié :** Imprimante 3D à dépôt de fil fondu (FDM) **Creality Ender 3**  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI (Lycée Stanislas Cannes)  
**Professeur :** Mme M. Prot

![Photo annotée du système Creality Ender 3](../02_photos/RAMOS-Ender3-Details.png)

---

## 1. Hypothèses de Modélisation du Solide Indéformable

En cinématique du solide indéformable, un solide $S$ est dit **indéformable** si la distance géométrique entre deux points quelconques $A$ et $B$ appartenant au solide reste invariante au cours du temps :
$$\forall A, B \in S, \quad \|\vec{AB}\| = \text{constante} \iff \left.\frac{\mathrm{d}\vec{AB}}{\mathrm{d}t}\right|_{\mathcal{R}_S} = \vec{0}$$

Chaque sous-ensemble cinématique regroupe les pièces mécaniques réelles qui sont solidaires entre elles durant la phase d'impression 3D nominale.

---

## 2. Tableau Récapitulatif des 5 Sous-ensembles Cinématiques

À chaque sous-ensemble est associé un **repère local orthonormé direct $\mathcal{R}_k$**, ainsi qu'une **couleur unique** respectée sur le graphe et sur les schémas cinématiques 2D et 3D :

| Sous-ensemble | Description synthétique | Repère local lié | Couleur | Mouvement par rapport au Châssis fixe ($\mathcal{R}_0$) |
| :--- | :--- | :--- | :--- | :--- |
| **Châssis fixe** | Châssis d'aluminium, contient l'électronique entre autres | $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Noir** (`#0f172a`) | Référence fixe au repos sur la table ($\underline{\underline{\equiv\mkern-10mu\perp}}$) |
| **Vis centrale** | Moteur stepper, axe $Z$ | $\mathcal{R}_1(O_1, \vec{x}_1, \vec{y}_1, \vec{z}_0)$ | **Bleu** (`#2563eb`) | Rotation d'angle $\theta_1(t)$ autour de l'axe vertical $(O_1, \vec{z}_0)$ |
| **Traverse horizontale** | Bouge de haut en bas (axe $Z$) et tient l'extrudeur | $\mathcal{R}_2(O_3, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Rouge** (`#dc2626`) | Translation rectiligne verticale $z_2(t)\,\vec{z}_0$ |
| **Chariot tête extrudeur** | Bouge sur l'axe $X$ (droite / gauche) | $\mathcal{R}_3(O_4, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Vert** (`#16a34a`) | Translation rectiligne transversale $x_3(t)\,\vec{x}_0$ sur la Traverse |
| **Plateau mobile** | Bouge sur l'axe $Y$, il est chauffé | $\mathcal{R}_4(O_5, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ | **Rose clair** (`#f472b6`) | Translation rectiligne longitudinale $y_4(t)\,\vec{y}_0$ sur le Châssis |

---

## 3. Détail des Pièces par Sous-ensemble

1. **Châssis fixe (Noir — Repère de référence $\mathcal{R}_0$) :**  
   *Châssis d'aluminium, contient l'électronique entre autres* : profilés aluminium V-Slot du cadre inférieur ($40\times 40\text{ mm}$), rail central de guidage $Y$ ($40\times 40\text{ mm}$), 2 montants verticaux $Z$ ($20\times 40\text{ mm}$), traverse supérieure ($20\times 20\text{ mm}$), stators des moteurs stepper $Z$ et $Y$, alimentation 24 V, boîtier carte mère et écran LCD.

2. **Vis centrale (Bleu — Repère $\mathcal{R}_1$) :**  
   *Moteur stepper, axe $Z$* : rotor et arbre de sortie ($\varnothing 5\text{ mm}$) du moteur stepper de l'axe $Z$, coupleur cylindrique fendu en aluminium, vis centrale trapézoïdale en acier inoxydable Tr8x8 ($\varnothing 8\text{ mm}$, filetage à droite, pas $p_z = 8\text{ mm/tr}$).

3. **Traverse horizontale (Rouge — Repère $\mathcal{R}_2$) :**  
   *Bouge de haut en bas (axe $Z$) et tient l'extrudeur* : profilé aluminium horizontal $X$ ($20\times 20\text{ mm}$), platines latérales en acier gauche et droite, écrou trapézoïdal en laiton Tr8x8, galets V-wheels de guidage vertical $Z$, stators des moteurs stepper de l'axe $X$ et de l'extrudeur.

4. **Chariot tête extrudeur (Vert — Repère $\mathcal{R}_3$) :**  
   *Bouge sur l'axe $X$ (droite / gauche)* : platine chariot $X$ en acier, 3 galets V-wheels de guidage $X$, tête chaude complète (radiateur rouge, barrière thermique, bloc de chauffe, buse d'extrusion en laiton $\varnothing 0{,}4\text{ mm}$), carénage et ventilateurs.

5. **Plateau mobile (Rose clair — Repère $\mathcal{R}_4$) :**  
   *Bouge sur l'axe $Y$, il est chauffé* : platine inférieure de chariot $Y$, 4 galets V-wheels de guidage sur le rail central $Y$, molettes de nivellement, plaque chauffante supérieure en aluminium ($235\times 235\text{ mm}$, 24 V / 220 W) et revêtement BuildTak.
