# DM n°1 : Modélisation des liaisons et Schématisation cinématique

**Lycée Stanislas — CPGE MPSI**  
**Sciences Industrielles de l'Ingénieur (SII)**  
**Enseignants :** Mme Marianne Prot / M. Cullaz  

---

* **Nom :** RAMOS  
* **Prénom :** Ignacio  
* **Classe :** MPSI  
* **Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  

---

## 1. Préambule : Pièces Exclues des Classes d'Équivalence Cinématique

Une classe d'équivalence cinématique regroupe les solides indéformables sans mouvement relatif entre eux en phase de fonctionnement (**phase d'impression 3D**). Sont donc **strictement exclus** :

1. **Les organes déformables et matière d'œuvre :**
   * Courroies crantées ouvertes GT2 des axes X et Y (pas de $2\text{ mm}$, en néoprène armé de fibres de verre).
   * Tube capillaire en PTFE (*tube Bowden*) d'acheminement du filament.
   * Les 4 ressorts hélicoïdaux de nivellement du plateau et le ressort du levier d'extrudeur.
   * Faisceaux de câbles électriques, nappes de l'écran LCD et gaines textiles.
   * Filament thermoplastique (PLA/ABS/PETG) de $\varnothing 1{,}75\text{ mm}$.
2. **Les éléments roulants de guidage :**
   * Les 13 galets en POM (*V-wheels*) et les 26 roulements à billes 625ZZ associés (billes et bagues extérieures).
   * Les billes des roulements internes des moteurs NEMA 17 et des poulies de renvoi.
3. **La chaîne secondaire d'extrusion et de ventilation :**
   * Rotor du moteur d'extrudeur, roue dentée d'entraînement en laiton, galet presseur U604ZZ et rotors des 4 ventilateurs.

---

## 2. Définition des 5 Classes d'Équivalence Cinématique (CEC)

| Classe | Désignation | Couleur normalisée | Pièces physiques réelles (Creality Ender 3) |
| :---: | :--- | :---: | :--- |
| **$E_0$** | **Bâti fixe** | **Noir** ($\equiv\mkern-10mu\perp$) | 2 traverses latérales en profilé alu 4040 V-Slot avec 4 patins en élastomère, 1 profilé central Y 2040 V-Slot, 1 traverse avant 2020 V-Slot, 2 montants verticaux Z 2040 V-Slot, 1 traverse supérieure 2020 V-Slot et bouchons ABS, stators des moteurs pas-à-pas NEMA 17 Z et Y avec platines support acier/polymère, supports tendeurs de courroie Y et axes fixes de poulie, capteurs de fin de course *Z-Endstop* et *Y-Endstop*, boîtier de carte mère, bloc alimentation 24 V / 360 W, console écran LCD 12864, porte-bobine métallique et visserie structurelle (vis CHC M4/M5 et écrous *T-nuts*). |
| **$E_1$** | **Arbre moteur Z & Vis mère** | **Bleu** | Rotor et arbre de sortie ($\varnothing 5\text{ mm}$) du moteur pas-à-pas Z, coupleur d'accouplement rigide fendu en alliage d'aluminium avec ses 2 vis radiales CHC M3, vis trapézoïdale Tr8x8 en acier inoxydable ($\varnothing 8\text{ mm}$, 4 filets, pas d'avance $p_z = 8\text{ mm/tr}$). |
| **$E_2$** | **Portique mobile X** | **Rouge** | Profilé aluminium horizontal transversal 2020 V-Slot, platines métalliques pliées gauche et droite, écrou trapézoïdal en laiton Tr8x8 fixé par 2 vis CHC M3, axes et entretoises lisses/excentriques des 6 galets V-wheels de guidage Z avec bagues intérieures des roulements, stator du moteur pas-à-pas NEMA 17 X avec son capot et capteur *X-Endstop*, support tendeur courroie X, et corps fixe de l'extrudeur MK8 (stator NEMA 17 et raccord pneumatique PC4-M6). |
| **$E_3$** | **Chariot de tête d'impression** | **Vert** | Platine support du chariot X en tôle d'acier avec fentes d'ancrage de courroie, axes et entretoises lisses/excentriques des 3 galets V-wheels avec bagues intérieures de roulements, raccord pneumatique PC4-M10, radiateur dissipateur rouge à ailettes, barrière thermique (*heatbreak* inox), bloc de chauffe alu avec cartouche 24 V / 40 W et thermistance CTN 100 k$\Omega$, buse d'extrusion en laiton ($\varnothing 0{,}4\text{ mm}$), carénage tôle et stators des 2 ventilateurs 4010. |
| **$E_4$** | **Plateau chauffant mobile Y** | **Orange** | Platine chariot Y en tôle pliée avec ancrage courroie, axes et entretoises des 4 galets V-wheels avec bagues intérieures de roulements, 4 vis M4 et molettes crantées de nivellement (*solidaires de la platine durant l'impression car non réglées en fonctionnement*), plaque d'aluminium chauffante 24 V / 220 W avec thermistance CTN, revêtement texturé *BuildTak* et 4 pinces métalliques de maintien. |

---

## 3. Paramétrage & Repères Locaux

Repère principal orthonormé direct lié au bâti fixe $E_0$ : $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ avec :
* $\vec{x}_0$ : Horizontal, transversal, de gauche à droite.
* $\vec{y}_0$ : Horizontal, longitudinal, de l'avant vers l'arrière ($\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$).
* $\vec{z}_0$ : Vertical ascendant.

**Centres des liaisons et vecteurs positions :**
* $O_1$ : Centre du guidage interne moteur Z : $\overrightarrow{O_0 O_1} = -L_x\,\vec{x}_0 + h_1\,\vec{z}_0$.
* $O_2$ : Centre de l'écrou hélicoïdal laiton : $\overrightarrow{O_0 O_2} = -L_x\,\vec{x}_0 + (h_1 + z(t))\,\vec{z}_0$.
* $O_3$ : Barycentre du guidage vertical du portique X : $\overrightarrow{O_0 O_3} = (h_1 + z(t))\,\vec{z}_0$.
* $O_4$ : Barycentre du chariot tête d'impression : $\overrightarrow{O_3 O_4} = x(t)\,\vec{x}_0 + d_y\,\vec{y}_0$.
* $O_5$ : Barycentre du chariot plateau chauffant : $\overrightarrow{O_0 O_5} = y(t)\,\vec{y}_0 + h_5\,\vec{z}_0$.

**Position relative Buse / Plateau :**
$$\boxed{\overrightarrow{O_5 O_4} = x(t)\,\vec{x}_0 + \big(d_y - y(t)\big)\,\vec{y}_0 + \left(h_1 - h_5 + \frac{p_z}{2\pi}\,\theta_1(t)\right)\,\vec{z}_0}$$

---

## 4. Caractérisation des 5 Liaisons Normalisées & Torseurs Cinématiques

### Tableau des Degrés de Liberté (dans $\mathcal{B}_0$)

| Liaison | Classes reliées | Nature et géométrie | $T_x$ | $T_y$ | $T_z$ | $R_x$ | $R_y$ | $R_z$ | Mobilités ($N_{\text{ddl}}$) |
| :---: | :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **$L_{01}$** | $E_0$ et $E_1$ | **Pivot** d'axe $(O_1, \vec{z}_0)$ | $0$ | $0$ | $0$ | $0$ | $0$ | **$1$** | **$1$** |
| **$L_{12}$** | $E_1$ et $E_2$ | **Hélicoïdale** d'axe $(O_2, \vec{z}_0)$, pas $p_z$ | $0$ | $0$ | **$1^*$** | $0$ | $0$ | **$1^*$** | **$1$** *(couplé)* |
| **$L_{02}$** | $E_0$ et $E_2$ | **Glissière** de direction $\vec{z}_0$ en $O_3$ | $0$ | $0$ | **$1$** | $0$ | $0$ | $0$ | **$1$** |
| **$L_{23}$** | $E_2$ et $E_3$ | **Glissière** de direction $\vec{x}_0$ en $O_4$ | **$1$** | $0$ | $0$ | $0$ | $0$ | $0$ | **$1$** |
| **$L_{04}$** | $E_0$ et $E_4$ | **Glissière** de direction $\vec{y}_0$ en $O_5$ | $0$ | **$1$** | $0$ | $0$ | $0$ | $0$ | **$1$** |

### Torseurs Cinématiques Matriciels dans $\mathcal{B}_0$ :

* **$L_{01}$ (Pivot $E_0 / E_1$) en $O_1$ :**
  $$\{\mathcal{V}(E_1/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_m(t) & 0 \end{Bmatrix}_{O_1, \mathcal{B}_0}$$

* **$L_{12}$ (Hélicoïdale $E_1 / E_2$) en $O_2$ (pas à droite $p_z = 8\text{ mm/tr}$) :**
  $$\{\mathcal{V}(E_2/E_1)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & -\dfrac{p_z}{2\pi}\,\omega_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0}$$

* **$L_{02}$ (Glissière $E_0 / E_2$) en $O_3$ :**
  $$\{\mathcal{V}(E_2/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{O_3, \mathcal{B}_0}$$

* **$L_{23}$ (Glissière $E_2 / E_3$) en $O_4$ :**
  $$\{\mathcal{V}(E_3/E_2)\} = \begin{Bmatrix} 0 & V_x(t) \\ 0 & 0 \\ 0 & 0 \end{Bmatrix}_{O_4, \mathcal{B}_0}$$

* **$L_{04}$ (Glissière $E_0 / E_4$) en $O_5$ :**
  $$\{\mathcal{V}(E_4/E_0)\} = \begin{Bmatrix} 0 & 0 \\ 0 & V_y(t) \\ 0 & 0 \end{Bmatrix}_{O_5, \mathcal{B}_0}$$

---

## 5. Fermeture Cinématique Z & Loi Entrée-Sortie

Considérons le cycle cinématique fermé $\{E_0 \to E_1 \to E_2 \to E_0\}$ réduit au point $O_2$ :
$$\{\mathcal{V}(E_2/E_0)\} = \{\mathcal{V}(E_2/E_1)\} + \{\mathcal{V}(E_1/E_0)\}$$

1. **Transport de moment en $O_2$ par la relation de Varignon :**
   $$\vec{V}(O_2, E_1/E_0) = \vec{V}(O_1, E_1/E_0) + \vec{\Omega}(E_1/E_0) \wedge \overrightarrow{O_1 O_2}$$
   Puisque $\vec{V}(O_1, E_1/E_0) = \vec{0}$ et que $\overrightarrow{O_1 O_2} = z_{12}(t)\vec{z}_0$ est colinéaire à $\vec{\Omega}(E_1/E_0) = \omega_m(t)\vec{z}_0$ :
   $$\vec{\Omega}(E_1/E_0) \wedge \overrightarrow{O_1 O_2} = \vec{0} \quad \Longrightarrow \quad \boxed{\vec{V}(O_2, E_1/E_0) = \vec{0}}$$

2. **Projection scalaire sur l'axe $\vec{z}_0$ :**
   * Rotation : $0 = \omega_{21}(t) + \omega_m(t) \implies \omega_{21}(t) = -\omega_m(t)$.
   * Vitesse linéaire en $O_2$ : $V_z(t) = -\frac{p_z}{2\pi}\omega_{21}(t) + 0$.
   En substituant $\omega_{21}(t) = -\omega_m(t)$ :
   $$\boxed{V_z(t) = \frac{p_z}{2\pi} \cdot \omega_m(t)}$$

3. **Relation intégrée et déplacement incrémental :**
   $$\boxed{\Delta Z = \frac{p_z}{2\pi} \cdot \Delta \theta_m}$$
   * **Pour 1 tour complet ($2\pi\text{ rad}$) :** $\Delta Z = p_z = 8\text{ mm}$.
   * **Pour 1 pas moteur ($1{,}8^\circ = \frac{\pi}{100}\text{ rad}$) :** $\Delta Z_{\text{pas}} = \frac{8}{200} = 0{,}04\text{ mm} = 40\ \mu\text{m}$.

---

## 6. Graphe des Liaisons (Représentation Topologique)

```text
                               L12 : Hélicoïdale (O2, z0)
                                     pas pz = 8 mm/tr
                         ( E1 ) -------------------------- ( E2 )
                           |                               /    \
                           |                              /      \  L23 : Glissière (x0)
        L01 : Pivot (O1, z0)       L02 : Glissière (z0)  /        \       centre O4
                           |             centre O3      /          \
                           |                           /            \
      ( E4 ) ------------ ( E0 ) ----------------------             ( E3 )
        L04 : Glissière     |
        (y0), centre O5   =====  <-- Symbole normalisé du bâti fixe (hachures)
                         ///////
```

---

## 7. Références Visuelles & Simulateurs Interactifs

* **Tableau de bord interactif général :** [`index.html`](file:///Users/ignac/Documents/GitHub/MyRoom/02_AGENTS/tasks/2026-10-21-mpsi-sii-dm1/index.html)
* **Explorateur 3D/2D switchable :** [`04_schemas_cinematiques/widget_1_explorateur_3d_2d.html`](file:///Users/ignac/Documents/GitHub/MyRoom/02_AGENTS/tasks/2026-10-21-mpsi-sii-dm1/04_schemas_cinematiques/widget_1_explorateur_3d_2d.html)
* **Graphe & Simulateur dynamique Z :** [`04_schemas_cinematiques/widget_2_graphe_simulateur_z.html`](file:///Users/ignac/Documents/GitHub/MyRoom/02_AGENTS/tasks/2026-10-21-mpsi-sii-dm1/04_schemas_cinematiques/widget_2_graphe_simulateur_z.html)
* **Inspecteur 6 DDL & Torseurs :** [`04_schemas_cinematiques/widget_3_inspecteur_ddl_torseurs.html`](file:///Users/ignac/Documents/GitHub/MyRoom/02_AGENTS/tasks/2026-10-21-mpsi-sii-dm1/04_schemas_cinematiques/widget_3_inspecteur_ddl_torseurs.html)
* **Modèle 3D spatial $O_0..O_5$ :** [`04_schemas_cinematiques/widget_4_modele_3d_centres_o0_o5.html`](file:///Users/ignac/Documents/GitHub/MyRoom/02_AGENTS/tasks/2026-10-21-mpsi-sii-dm1/04_schemas_cinematiques/widget_4_modele_3d_centres_o0_o5.html)
