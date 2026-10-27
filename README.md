# DM n°1 SII — Modélisation des Liaisons & Schématisation Cinématique (Creality Ender 3)

**Élève :** Juan Ignacio RAMOS — **Classe :** CPGE MPSI (Lycée Stanislas Cannes)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — Cinématique du Solide Indéformable  
**Professeur :** Mme M. Prot  
**Système étudié :** Imprimante 3D à dépôt de fil fondu (FDM) **Creality Ender 3**

![Photo annotée du système Creality Ender 3](02_photos/RAMOS-Ender3-Details.png)

---

## 1. Accès Direct aux Livrables Numériques et Papier

Tous les documents demandés pour le rendu papier et numérique ont été intégralement réalisés en haute résolution vectorielle (SVG/PDF) et matricielle (PNG/JPG) :

| Livrable | Fichiers numériques haute résolution (prêts à imprimer ou recopier) |
| :--- | :--- |
| **Feuille de rendu A4 complète (3 pages A4)** | [`05_dossier_papier/DM1_Feuille_Rendu_Imprimable.html`](05_dossier_papier/DM1_Feuille_Rendu_Imprimable.html) • [`05_dossier_papier/DM1_Feuille_Rendu_Imprimable.pdf`](05_dossier_papier/DM1_Feuille_Rendu_Imprimable.pdf) • [`05_dossier_papier/DM1_Dossier_Complet_Rendu.md`](05_dossier_papier/DM1_Dossier_Complet_Rendu.md) |
| **Planches de référence SII (3 planches)** | [`diagrams_reference.html`](diagrams_reference.html) • [`index.html`](index.html) (Portail interactif global) |
| **1. Système annoté avec sous-ensembles et centres** | [`02_photos/RAMOS-Ender3-Details.png`](02_photos/RAMOS-Ender3-Details.png) • [`02_photos/RAMOS-Ender3-Details.jpg`](02_photos/RAMOS-Ender3-Details.jpg) • [`04_schemas_cinematiques/figures_parametrage_angles.svg`](04_schemas_cinematiques/figures_parametrage_angles.svg) |
| **2. Graphe des liaisons (bâti $\underline{\underline{\equiv\mkern-10mu\perp}}$)** | [`04_schemas_cinematiques/graphe_des_liaisons.svg`](04_schemas_cinematiques/graphe_des_liaisons.svg) • [`04_schemas_cinematiques/graphe_des_liaisons.png`](04_schemas_cinematiques/graphe_des_liaisons.png) |
| **3. Schéma cinématique 2D en couleur** | [`04_schemas_cinematiques/schema_cinematique_2d.svg`](04_schemas_cinematiques/schema_cinematique_2d.svg) • [`04_schemas_cinematiques/schema_cinematique_2d.png`](04_schemas_cinematiques/schema_cinematique_2d.png) |
| **4. Schéma cinématique 3D en couleur** | [`04_schemas_cinematiques/schema_cinematique_3d.svg`](04_schemas_cinematiques/schema_cinematique_3d.svg) • [`04_schemas_cinematiques/schema_cinematique_3d.png`](04_schemas_cinematiques/schema_cinematique_3d.png) |

---

## 2. Les 5 Sous-ensembles Cinématiques et Code Couleur

1. **Châssis fixe (Noir)** : Châssis d'aluminium, contient l'électronique entre autres.
2. **Vis centrale (Bleu)** : Moteur stepper, axe $Z$.
3. **Traverse horizontale (Rouge)** : Bouge de haut en bas (axe $Z$) et tient l'extrudeur.
4. **Chariot tête extrudeur (Vert)** : Bouge sur l'axe $X$ (droite / gauche).
5. **Plateau mobile (Rose clair)** : Bouge sur l'axe $Y$, il est chauffé.

---

## 3. Aperçu des Schémas Vectoriels

### 3.1. Graphe des Liaisons
![Graphe des liaisons](04_schemas_cinematiques/graphe_des_liaisons.svg)

### 3.2. Schéma Cinématique Minimal 2D en Couleur — Vue Frontale $(O_0, \vec{x}_0, \vec{z}_0)$
![Schéma cinématique minimal 2D en couleur](04_schemas_cinematiques/schema_cinematique_2d.svg)

### 3.3. Schéma Cinématique Spatial 3D en Couleur — Perspective Axonométrique / Cavalière
![Schéma cinématique spatial 3D en couleur](04_schemas_cinematiques/schema_cinematique_3d.svg)

### 3.4. Figure Plane de Changement de Base ($\mathcal{B}_0 \to \mathcal{B}_1$) & Chaîne Vectorielle des Centres
![Figure plane de changement de base et chaîne vectorielle des centres](04_schemas_cinematiques/figures_parametrage_angles.svg)

---

## 4. Architecture Complète du Dépôt

```text
.
├── index.html                                           # Portail interactif global (Dossier + Feuille A4 + 4 Simulateurs)
├── diagrams_reference.html                              # 3 Planches de référence SII (KaTeX + SVG haute précision)
├── README.md                                            # Documentation principale et aperçu des livrables
├── record.md                                            # Journal d'ingénierie et historique des modifications
├── 01_emails/                                           # Courriels de validation (Partie I) et rendu numérique (Partie II)
├── 02_photos/
│   ├── RAMOS-Selfie.png                                 # Selfie officiel de l'élève avec la Creality Ender 3
│   ├── RAMOS-Ender3-Details.png / .jpg                  # Livrable photo annotée HD (5 sous-ensembles + loupe Z + centres)
│   ├── ender 3 img1 venus de milo.png                   # Photo principale en impression (Vénus de Milo)
│   ├── ender 3 img2.JPG                                 # Photo macro arrière de la vis centrale Tr8x8 et du coupleur Z
│   └── guide_preparation_photos.md                      # Documentation du dossier photographique
├── 03_modele_mecanique/
│   ├── classes_equivalence_template.md                  # Inventaire des 5 sous-ensembles et repères R0..R4
│   ├── parametrage_vectoriel.md                         # Paramétrage géométrique, figure plane (B0 -> B1) et vecteur O5O4
│   ├── liaisons_torseurs_template.md                    # Répertoire des 5 liaisons et torseurs cinématiques dans B0
│   └── graphe_liaisons_fermeture_template.md            # Graphe des liaisons et fermeture cinématique de la boucle Z
├── 04_schemas_cinematiques/
│   ├── graphe_des_liaisons.svg / .png                   # Graphe des liaisons vectoriel
│   ├── schema_cinematique_2d.svg / .png                 # Schéma cinématique minimal 2D en couleur (projection frontale)
│   ├── schema_cinematique_3d.svg / .png                 # Schéma cinématique spatial 3D en couleur (perspective cavalière)
│   ├── figures_parametrage_angles.svg / .png            # Figure plane de changement de base et chaîne vectorielle O0..O5
│   ├── guide_trace_2d_3d.md                             # Protocole de tracé à la main 2D/3D
│   ├── widget_1_explorateur_3d_2d.html                  # Simulateur 1 : Explorateur interactif 3D/2D (Three.js)
│   ├── widget_2_graphe_simulateur_z.html                # Simulateur 2 : Graphe interactif et fermeture cinématique Z
│   ├── widget_3_inspecteur_ddl_torseurs.html            # Simulateur 3 : Inspecteur des 6 DDL et matrices de torseurs
│   └── widget_4_modele_3d_centres_o0_o5.html            # Simulateur 4 : Modèle 3D spatial des centres O0..O5 et vecteur O5O4
└── 05_dossier_papier/
    ├── DM1_Feuille_Rendu_Imprimable.html / .pdf / .png  # Feuille de rendu papier A4 imprimable
    └── DM1_Dossier_Complet_Rendu.md                     # Dossier écrit complet intégrant photos, schémas et démonstrations
```
