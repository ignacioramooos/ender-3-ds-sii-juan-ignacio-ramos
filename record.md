# Expediente : CPGE MPSI SII - DM n°1 (Creality Ender 3)

- **Date :** 2026-10-21 / 2026-10-22
- **Étudiant :** Ignacio Ramos (MPSI Stanislas Cannes)
- **Professeurs :** Mme Marianne Prot / M. Cullaz
- **Système d'étude :** Imprimante 3D Creality Ender 3 (modèle de base)
- **Architecture de travail :**
  - Antigravity : Infrastructure, organisation des fichiers, intégration et mise en page.
  - Argon High : Modélisation cinématique, torseurs matriciels dans $\mathcal{B}_0$, dérivation de Varignon et topologie du graphe.

---

## 1. État des Livrables & Validation

- [x] **01_emails :**
  - `email_validation_part1.md` : E-mail formel de validation rédigé et vérifié.
  - `email_rendu_part2.md` : E-mail formel de rendu numérique avec selfie et clause poster.
- [x] **02_photos :**
  - `RAMOS-Selfie.png` : Photo de l'élève avec l'Ender 3 récupérée et classée.
  - `guide_preparation_photos.md` : Guide d'annotation géométrique.
- [x] **03_modele_mecanique :**
  - `classes_equivalence_template.md` : Préambule d'exclusion exhaustif + inventaire complet des 5 classes.
  - `parametrage_vectoriel.md` : Définition vectorielle des centres $O_1..O_5$ et fermeture géométrique buse/plateau.
  - `liaisons_torseurs_template.md` : Caractérisation des 5 liaisons, DDL et torseurs matriciels 6 composantes dans $\mathcal{B}_0$.
  - `graphe_liaisons_fermeture_template.md` : Démonstration analytique au point $O_2$ (Varignon, annulation par colinéarité, $V_z = \frac{p_z}{2\pi}\omega_m$, $\Delta Z_{\text{pas}} = 40\,\mu\text{m}$) et graphe topologique.
- [x] **04_schemas_cinematiques :**
  - `guide_trace_2d_3d.md` : Guide de dessin manuel AFNOR.
  - `widget_1_explorateur_3d_2d.html` : Simulateur interactif Three.js 3D/2D switchable avec fiches liaisons.
  - `widget_2_graphe_simulateur_z.html` : Graphe des liaisons dynamique et simulateur d'entrée-sortie Z avec KPIs.
  - `widget_3_inspecteur_ddl_torseurs.html` : Inspecteur interactif des 6 DDL et torseurs matriciels temps réel.
  - `widget_4_modele_3d_centres_o0_o5.html` : Modèle 3D spatial avec trièdres des centres $O_0$ à $O_5$ et HUD vecteur $\overrightarrow{O_5 O_4}$.
- [x] **05_dossier_papier :**
  - `DM1_Dossier_Complet_Rendu.md` : Document d'assemblage maître complet mis à jour selon le corrigé type.
- [x] **06_prompts_delegation :**
  - Tous les prompts archivés pour traçabilité.
- [x] **Tableau de bord unifié :**
  - `index.html` : Hub interactif complet avec KaTeX, onglets de navigation et simulateurs embarqués.
