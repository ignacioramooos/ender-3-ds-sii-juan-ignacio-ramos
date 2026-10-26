# Journal d'Audit & d'Ingénierie SII — DM n°1 Creality Ender 3 (MPSI Stanislas)

**Élève :** Juan Ignacio RAMOS — **Classe :** MPSI (Lycée Stanislas)  
**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Statut :** Audit complet, refonte mathématique/graphique et vérification visuelle terminés.

---

## 1. Synthèse de l'Audit Critique CPGE MPSI SII (Anomalies Corrigées)

Une inspection intégrale du dépôt initial au regard des exigences de l'énoncé (Mme Prot & M. Cullaz) et de la norme **AFNOR NF EN ISO 3952** a mis en évidence **6 défauts majeurs** qui ont été intégralement corrigés :

1. **Correction de l'erreur de repère indirect (main gauche) sur le schéma 2D et le guide de tracé :**
   - En projection frontale dans le plan $(O_0, \vec{x}_0, \vec{z}_0)$ avec $\vec{x}_0$ dirigé vers la droite et $\vec{z}_0$ vers le haut, un trièdre orthonormé **direct** ($\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$) impose que $\vec{y}_0$ soit **entrant dans la feuille** ($\otimes\,\vec{y}_0$, pointant vers l'arrière de l'imprimante). L'ancienne version dessinait un point $\odot\,\vec{y}$ (sortant), définissant un repère indirect !
2. **Résolution de la contradiction de signe sur la liaison hélicoïdale à droite $L_{12}$ (Tr8x8) :**
   - Pour une vis à **filetage à droite** ($p_z = 8\text{ mm/tr}$) d'axe $(O_2, \vec{z}_0)$ dans une base directe $\mathcal{B}_0$, la loi de conjugaison intrinsèque du mouvement de l'écrou $E_2$ par rapport à la vis $E_1$ s'écrit avec un signe **positif** :
     $$v_{21}(t) = +\frac{p_z}{2\pi}\,\omega_{21}(t)$$
   - La fermeture cinématique de la chaîne $\{E_0 \to E_1 \to E_2 \to E_0\}$ au point $O_2 \in (O_1, \vec{z}_0)$ donne alors :
     $$\omega_{21}(t) + \omega_{10}(t) = 0 \implies \omega_{21}(t) = -\omega_{10}(t) \quad \text{et} \quad V_z(t) = \dot{z}_2(t) = v_{21}(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t) = +\frac{p_z}{2\pi}\,\omega_m(t)$$
     où $\omega_m(t) = -\omega_{10}(t) > 0$ est la vitesse angulaire motrice de montée (sens horaire de la vis vue de dessus). Cette convention est désormais 100 % cohérente à travers tous les fichiers Markdown, planches HTML et widgets interactifs.
3. **Création du livrable photographique annoté haute définition (`02_photos/RAMOS-Ender3-Details.png` et `.jpg`) :**
   - Intégration de la photo frontale en cours d'impression (`ender 3 img1 venus de milo.png`) et d'un médaillon loupe haute résolution (`ender 3 img2.JPG`) montrant la vis mère trapézoïdale Tr8x8 et le coupleur aluminium en $O_1$.
   - Tracé vectoriel du trièdre global direct $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$, des repères locaux $\mathcal{R}_1 \dots \mathcal{R}_4$, des centres $O_1 \dots O_5$, des paramètres cinématiques $\theta_1(t), z_2(t), x_3(t), y_4(t)$ et des étiquettes fléchées des 5 classes d'équivalence $E_0 \dots E_4$.
4. **Définition explicite des 5 repères locaux ($\mathcal{R}_0$ à $\mathcal{R}_4$) et de la figure plane de changement de base ($\mathcal{B}_0 \to \mathcal{B}_1$) :**
   - Ajout de la planche vectorielle `04_schemas_cinematiques/figures_parametrage_angles.svg` (`.png`) présentant la figure plane de projection $(\vec{x}_0, \vec{y}_0) \to (\vec{x}_1, \vec{y}_1)$ d'angle $\theta_1(t)$ autour de $\vec{z}_0 = \vec{z}_1$ ainsi que le graphe vectoriel des centres géométriques $O_0 \dots O_5$ et la fermeture géométrique $\overrightarrow{O_5 O_4}$.
5. **Refonte intégrale des schémas vectoriels normalisés AFNOR (`graphe_des_liaisons.svg`, `schema_cinematique_2d.svg`, `schema_cinematique_3d.svg`) :**
   - Respect strict de la **bijection des 5 couleurs** ($E_0$ Noir, $E_1$ Bleu, $E_2$ Rouge, $E_3$ Vert, $E_4$ Orange — suppression de la 6e couleur violette erronée sur $L_{12}$).
   - Représentation minimale : une unique liaison glissière équivalente $L_{02}$ en $O_3$ (suppression de la double glissière redondante).
   - Symboles AFNOR 2D et 3D exacts : croix diagonale interne sur les rectangles de glissière 2D, butées axiales sur le pivot $L_{01}$, traits obliques de filetage sur l'hélicoïdale $L_{12}$, glissière $L_{04}$ vue en bout en 2D, et vraie perspective cavalière 3D avec fuyante $\vec{y}_0$ de pente constante $(-2/3)$.
6. **Correction des 4 simulateurs interactifs (`widget_1` à `widget_4`) et création de la feuille de rendu A4 imprimable :**
   - `widget_1_explorateur_3d_2d.html` : repositionnement de la vis mère $Z$ à gauche (`x = -44`), ajout des deux montants verticaux et de la traverse supérieure du bâti $E_0$, utilisation des centres exacts $O_1 \dots O_5$.
   - `widget_2_graphe_simulateur_z.html` et `widget_3_inspecteur_ddl_torseurs.html` : correction du signe de $v_{21}$ et de la solution constructive de $L_{01}$ (roulements internes du moteur NEMA 17 $Z$ + coupleur rigide fendu en alu).
   - `widget_4_modele_3d_centres_o0_o5.html` : affichage des coordonnées de $\overrightarrow{O_5 O_4}$ dans la base SII $\mathcal{B}_0(\vec{x}_0, \vec{y}_0, \vec{z}_0)$ (`[dx, dy, dz]_B0`).
   - Création de `05_dossier_papier/DM1_Feuille_Rendu_Imprimable.html` calquée sur le modèle de la Page 2 de l'énoncé.
