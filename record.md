# Journal d'Audit & d'Ingénierie SII — DM n°1 Creality Ender 3 (MPSI Stanislas)

**Élève :** Juan Ignacio RAMOS — **Classe :** CPGE MPSI (Lycée Stanislas Paris)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — Séquence 2 (CM4 : *Cinématique du Solide Indéformable*)  
**Professeurs :** Mme Marianne Prot & M. Cullaz  
**Système étudié :** Imprimante 3D Creality Ender 3 (modèle de base)  
**Statut :** Audit de conformité approfondi, alignement terminologique CM4 et feuille imprimable A4 finalisés.

---

## 1. Synthèse de l'Audit Approfondi CPGE MPSI SII (Conformité CM4 Stanislas)

Une vérification exhaustive a été menée pour aligner l'ensemble du vocabulaire, des théorèmes et des démonstrations mathématiques sur le support officiel du cours **CM4 : Cinématique du Solide Indéformable** (Séquence 2 : *Modéliser et résoudre pour vérifier les performances cinématiques de systèmes de solides d'une chaîne d'énergie*) :

1. **Hypothèse du solide indéformable (CM4 § 1.1) :**
   - Invariance des distances géométriques ($\forall A, B \in S, \|\vec{AB}\| = \text{cte} \iff \left.\frac{\mathrm{d}\vec{AB}}{\mathrm{d}t}\right|_{R_S} = \vec{0}$).
   - Définition stricte des classes d'équivalence $E_0 \dots E_4$ comme solides indéformables en liaison encastrement complète mutuelle en phase d'impression nominale.

2. **Formule de dérivation vectorielle (Formule de Bour — CM4 § 1.2) :**
   - Application rigoureuse de la formule de Bour pour la dérivation entre repères mobiles ($\left.\frac{\mathrm{d}\vec{u}}{\mathrm{d}t}\right|_{R_1} = \left.\frac{\mathrm{d}\vec{u}}{\mathrm{d}t}\right|_{R_2} + \vec{\Omega}_{R_2/R_1} \wedge \vec{u}$) lors de la projection de $\mathcal{B}_1$ dans $\mathcal{B}_0$ et de la vitesse relative buse/plateau $\vec{V}(O_4 \in E_3/E_4)$.

3. **Formule fondamentale du solide (Varignon — CM4 § 1.3) & Moyen mnémotechnique officiel « BABAR » (CM4 § 1.4) :**
   - Intégration systématique de la formule de Varignon sous sa forme canonique :
     $$\vec{V}_{\mathbf{B} \in S/R} = \vec{V}_{\mathbf{A} \in S/R} + \mathbf{BA} \wedge \vec{\mathbf{\Omega}}_{S/R} = \vec{V}_{\mathbf{A} \in S/R} + \vec{\mathbf{\Omega}}_{S/R} \wedge \vec{\mathbf{AB}}$$
   - Utilisation de la règle BABAR pour le transport sans ambiguïté de signe du torseur pivot $\{\mathcal{V}(E_1/E_0)\}$ du point $O_1$ au point $O_2$ ($\vec{V}(O_2) = \vec{V}(O_1) + \overrightarrow{O_2 O_1} \wedge \vec{\Omega} = \vec{0}$).

4. **Propriété d'équiprojectivité du champ des vitesses (CM4 § 1.5) :**
   - Rappel de l'égalité scalaire $\vec{V}_B \cdot \overrightarrow{AB} = \vec{V}_A \cdot \overrightarrow{AB}$ et de sa condition impérative d'application ($A$ et $B$ doivent obligatoirement appartenir au **MÊME solide indéformable**).

5. **Définition et typologie des torseurs cinématiques (CM4 § 2.5) :**
   - Présentation de la double notation normalisée : **notation matricielle en colonne $3\times 2$** (avec point de réduction en bas à gauche et base de projection en bas à droite) et **notation en ligne intrinsèque** ($\{\mathcal{V}\} = \{ \vec{\Omega} \;;\; \vec{V}_A \}_A$).
   - Classification canonique :
     - **Torseur Glisseur** pour la liaison Pivot $L_{01}$ (automoment nul $I = \vec{\Omega} \cdot \vec{V}_A = 0$, axe central $\Delta(O_1, \vec{z}_0)$ où le moment est nul).
     - **Torseur Hélicoïdal** pour la liaison $L_{12}$ (automoment $I \neq 0$, moment colinéaire à la résultante sur l'axe).
     - **Torseur Couple** pour les liaisons Glissières $L_{02}, L_{23}, L_{04}$ ($\vec{\Omega} = \vec{0}$, champ uniforme de vitesses en tout point de l'espace).
   - Indication systématique du nombre de degrés de liberté autorisés $N_s$ et bloqués $N_c = 6 - N_s$ ($N_s + N_c = 6$).

6. **Piège de concours majeur (CM4 § 3.3) :**
   - Mise en garde explicite : le champ des vecteurs accélération d'un solide indéformable **n'est PAS un torseur** en raison de la présence du terme centripète $\vec{\Omega} \wedge (\vec{\Omega} \wedge \overrightarrow{AB})$.

7. **Composition des torseurs & Règle impérative absolue (CM4 § 4.3) :**
   - Rappel de la règle d'or : *pour faire la somme de torseurs cinématiques, ils doivent obligatoirement être écrits au MÊME point géométrique*.
   - Résolution complète de la fermeture cinématique de la boucle d'élévation $Z$ au point $O_2$ :
     $$\boxed{V_z(t) = \dot{z}_2(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t) = -\frac{p_z}{2\pi}\,\dot{\theta}_1(t) = +\frac{p_z}{2\pi}\,\omega_m(t)}$$

8. **Cinématique de commande en trapèze de vitesse (CM4 § 5.3) :**
   - Profil de vitesse trapézoïdal des moteurs pas-à-pas NEMA 17 (Phase I accélération uniforme, Phase II régime permanent, Phase III décélération uniforme) et détermination de la course par la **méthode de l'aire du trapèze** :
     $$\Delta z_2 = \frac{\big(t_3 + (t_2 - t_1)\big)\cdot V_{\max}}{2}$$

---

## 2. Refonte du Livrable Imprimable A4 (`05_dossier_papier/DM1_Feuille_Rendu_Imprimable.html`)

- **Conformité stricte au Modèle Page 2 de l'énoncé :** Document structuré en **exactement 2 pages A4** (Page 1 = Recto, Page 2 = Verso).
- **Format d'impression optimisé :** Règles CSS `@page { size: A4 portrait; margin: 5mm 7mm; }` et `@media print` garantissant une compilation PDF parfaite en 2 pages (sans saut de page intempestif ni débordement).
- **Richesse du contenu :**
  - **Recto (Page 1) :** Cartouche officiel élève/cours, Selfie de validation, Photo annotée HD du système réel paramétré ($\mathcal{R}_0 \dots \mathcal{R}_4$, $O_1 \dots O_5$), Graphe des liaisons AFNOR avec classes explicites, et Analyse topologique / Hypothèses CM4 ($\gamma = 1$).
  - **Verso (Page 2) :** Schémas cinématiques 2D minimal et 3D spatial côte-à-côte, Figure plane $(\mathcal{B}_0 \to \mathcal{B}_1)$ et vecteur position $\overrightarrow{O_5 O_4}$, Tableau des 5 liaisons avec torseurs en colonne et typologie, et Fermeture cinématique complète de la chaîne $Z$ avec commande trapézoïdale.
- **Régénération des livrables :** `DM1_Feuille_Rendu_Imprimable.pdf` (exactement 2 pages A4) et `DM1_Feuille_Rendu_Imprimable.png`.
