# Journal d'Ingénierie SII — DM n°1 Creality Ender 3 (MPSI — Lycée Stanislas Cannes)

**Élève :** Juan Ignacio RAMOS — **Classe :** CPGE MPSI (Lycée Stanislas Cannes)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — Cinématique du Solide Indéformable  
**Professeur :** Mme M. Prot  
**Système étudié :** Imprimante 3D Creality Ender 3

---

## 1. Synthèse de la Modélisation Cinématique

1. **Hypothèse du solide indéformable :**
   - Invariance des distances géométriques ($\forall A, B \in S, \|\vec{AB}\| = \text{cte} \iff \left.\frac{\mathrm{d}\vec{AB}}{\mathrm{d}t}\right|_{R_S} = \vec{0}$).
   - Définition des 5 sous-ensembles cinématiques comme solides indéformables en phase d'impression nominale :
     - **Châssis fixe (Noir)** : *Châssis d'aluminium, contient l'électronique entre autres.*
     - **Vis centrale (Bleu)** : *Moteur stepper, axe $Z$.*
     - **Traverse horizontale (Rouge)** : *Bouge de haut en bas (axe $Z$) et tient l'extrudeur.*
     - **Chariot tête extrudeur (Vert)** : *Bouge sur l'axe $X$ (droite / gauche).*
     - **Plateau mobile (Rose clair)** : *Bouge sur l'axe $Y$, il est chauffé.*

2. **Formule de dérivation vectorielle (Formule de Bour) :**
   - Application de la formule de Bour pour la dérivation entre repères mobiles ($\left.\frac{\mathrm{d}\vec{u}}{\mathrm{d}t}\right|_{R_0} = \left.\frac{\mathrm{d}\vec{u}}{\mathrm{d}t}\right|_{R_1} + \vec{\Omega}_{R_1/R_0} \wedge \vec{u}$) lors de la projection de $\mathcal{B}_1$ dans $\mathcal{B}_0$ et de la vitesse relative buse/plateau $\vec{V}(O_4 \in \text{Chariot}/\text{Plateau})$.

3. **Formule fondamentale du solide (Varignon) :**
   - Transport du torseur pivot $\{\mathcal{V}(\text{Vis}/\text{Châssis})\}$ du point $O_1$ au point $O_2$ :
     $$\vec{V}(O_2 \in \text{Vis}/\text{Châssis}) = \vec{V}(O_1 \in \text{Vis}/\text{Châssis}) + \overrightarrow{O_2 O_1} \wedge \vec{\Omega}(\text{Vis}/\text{Châssis}) = \vec{0}$$

4. **Définition et typologie des torseurs cinématiques :**
   - **Torseur Glisseur** pour la liaison Pivot $L_{01}$ d'axe $(O_1, \vec{z}_0)$.
   - **Torseur Hélicoïdal** pour la liaison Hélicoïdale $L_{12}$ d'axe $(O_2, \vec{z}_0)$ et de pas $p_z = 8\text{ mm/tr}$.
   - **Torseur Couple** pour les liaisons Glissières $L_{02}, L_{23}, L_{04}$ ($\vec{\Omega} = \vec{0}$, champ uniforme de vitesses en tout point).

5. **Fermeture cinématique de la boucle $Z$ (Châssis fixe — Vis centrale — Traverse horizontale) :**
   - Réduction au même point géométrique $O_2$ :
     $$\boxed{V_z(t) = \dot{z}_2(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t) = -\frac{p_z}{2\pi}\,\dot{\theta}_1(t) = +\frac{p_z}{2\pi}\,\omega_m(t)}$$

---

## 2. Historique des Révisions et Mises à Jour

### Révision 1 — Structuration initiale du dossier et des simulateurs
- Création du portail interactif `index.html`, des planches `diagrams_reference.html`, de la feuille A4 `05_dossier_papier/DM1_Feuille_Rendu_Imprimable.html` et des 4 simulateurs interactifs (`widget_1` à `widget_4`).
- Génération de la planche photographique annotée `02_photos/RAMOS-Ender3-Details.png` / `.jpg` et des 4 schémas vectoriels SVG/PNG (`graphe_des_liaisons`, `schema_cinematique_2d`, `schema_cinematique_3d`, `figures_parametrage_angles`).

### Révision 2 — Simplification terminologique, mise à jour visuelle et alignement Lycée Stanislas Cannes
- **Établissement et professeur :** Mise à jour dans tous les fichiers de l'établissement (**Lycée Stanislas Cannes**) et de l'unique professeure de SII (**Mme M. Prot**).
- **Simplification de la photo annotée (`02_photos/RAMOS-Ender3-Details.png` & `.jpg`) et de la nomenclature globale :**
  - Remplacement des intitulés techniques complexes ($E_0[\mathcal{R}_0] \dots E_4[\mathcal{R}_4]$) par les 5 sous-ensembles clairs et synthétiques :
    1. **Châssis fixe** : *Châssis d'aluminium, contient l'électronique entre autres.*
    2. **Vis centrale** : *Moteur stepper, axe $Z$.*
    3. **Traverse horizontale** : *Bouge de haut en bas (axe $Z$) et tient l'extrudeur.*
    4. **Chariot tête extrudeur** : *Bouge sur l'axe $X$ (droite / gauche).*
    5. **Plateau mobile** : *Bouge sur l'axe $Y$, il est chauffé.*
- **Changement de couleur du Plateau mobile (Rose clair `#f472b6`) :**
  - Remplacement de la couleur du **Plateau mobile** par un **rose clair** (`#f472b6`) sur la photo annotée, le graphe des liaisons, les schémas 2D et 3D, les légendes, la feuille A4 imprimable et les simulateurs 3D/2D.
- **Épuration et agrandissement des schémas :**
  - Suppression des encadrés de texte superflus sous le graphe des liaisons et sous le modèle 3D afin de donner un espace maximal aux modélisations dans `04_schemas_cinematiques/graphe_des_liaisons.svg`, `05_dossier_papier/DM1_Feuille_Rendu_Imprimable.html`, `diagrams_reference.html` et `04_schemas_cinematiques/widget_4_modele_3d_centres_o0_o5.html`.
  - Suppression de toutes les mentions non demandées.
- **Régénération complète des livrables :** `02_photos/RAMOS-Ender3-Details.png` (`.jpg`), les 4 SVGs et PNGs dans `04_schemas_cinematiques/`, ainsi que `05_dossier_papier/DM1_Feuille_Rendu_Imprimable.pdf` et `.png`.
