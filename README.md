# DM n°1 SII — Modélisation des Liaisons & Schématisation Cinématique (Creality Ender 3)

**Élève :** Juan Ignacio RAMOS — **Classe :** CPGE MPSI (Lycée Stanislas Paris)  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — Séquence 2 (CM4 : *Cinématique du Solide Indéformable*)  
**Enseignants :** Mme Marianne Prot & M. Cullaz  
**Système étudié :** Imprimante 3D à dépôt de fil fondu (FDM) **Creality Ender 3 (modèle de base)**  
**Norme de référence :** AFNOR NF EN ISO 3952 (Schémas cinématiques — Symboles graphiques)

![Photo annotée du système Creality Ender 3 avec repères locaux et classes d'équivalence](02_photos/RAMOS-Ender3-Details.png)

---

## 1. Accès Direct aux Livrables Numériques et Papier (Partie III)

Tous les documents demandés pour le rendu papier (Partie III de l'énoncé) ont été intégralement réalisés et rendus numériquement en haute résolution vectorielle (SVG) et matricielle (PNG/JPG) :

| Livrable demandé (Partie III de l'énoncé) | Fichiers numériques haute résolution (prêts à imprimer ou recopier) |
| :--- | :--- |
| **Feuille de rendu A4 complète (Modèle Page 2 de l'énoncé)** | [`05_dossier_papier/DM1_Feuille_Rendu_Imprimable.html`](05_dossier_papier/DM1_Feuille_Rendu_Imprimable.html) • [`05_dossier_papier/DM1_Dossier_Complet_Rendu.md`](05_dossier_papier/DM1_Dossier_Complet_Rendu.md) |
| **Planches de référence SII (3 planches A4)** | [`diagrams_reference.html`](diagrams_reference.html) • [`index.html`](index.html) (Portail interactif global) |
| **1. Système paramétré avec repères locaux ($\mathcal{R}_0$ à $\mathcal{R}_4$) et pièces** | [`02_photos/RAMOS-Ender3-Details.png`](02_photos/RAMOS-Ender3-Details.png) • [`02_photos/RAMOS-Ender3-Details.jpg`](02_photos/RAMOS-Ender3-Details.jpg) • [`04_schemas_cinematiques/figures_parametrage_angles.svg`](04_schemas_cinematiques/figures_parametrage_angles.svg) |
| **2. Graphe des liaisons (classes d'équivalence explicites + bâti $\underline{\underline{\equiv\mkern-10mu\perp}}$)** | [`04_schemas_cinematiques/graphe_des_liaisons.svg`](04_schemas_cinematiques/graphe_des_liaisons.svg) • [`04_schemas_cinematiques/graphe_des_liaisons.png`](04_schemas_cinematiques/graphe_des_liaisons.png) |
| **3. Schéma cinématique 2D en couleur** | [`04_schemas_cinematiques/schema_cinematique_2d.svg`](04_schemas_cinematiques/schema_cinematique_2d.svg) • [`04_schemas_cinematiques/schema_cinematique_2d.png`](04_schemas_cinematiques/schema_cinematique_2d.png) |
| **4. Schéma cinématique 3D en couleur** | [`04_schemas_cinematiques/schema_cinematique_3d.svg`](04_schemas_cinematiques/schema_cinematique_3d.svg) • [`04_schemas_cinematiques/schema_cinematique_3d.png`](04_schemas_cinematiques/schema_cinematique_3d.png) |

---

## 2. Aperçu des Schémas Vectoriels Normalisés (AFNOR NF EN ISO 3952)

### 2.1. Graphe des Liaisons Normalisé
![Graphe des liaisons normalisé](04_schemas_cinematiques/graphe_des_liaisons.svg)

### 2.2. Schéma Cinématique Minimal 2D en Couleur — Vue Frontale $(O_0, \vec{x}_0, \vec{z}_0)$
![Schéma cinématique minimal 2D en couleur](04_schemas_cinematiques/schema_cinematique_2d.svg)

### 2.3. Schéma Cinématique Spatial 3D en Couleur — Perspective Axonométrique / Cavalière
![Schéma cinématique spatial 3D en couleur](04_schemas_cinematiques/schema_cinematique_3d.svg)

### 2.4. Figure Plane de Changement de Base ($\mathcal{B}_0 \to \mathcal{B}_1$) & Chaîne Vectorielle des Centres
![Figure plane de changement de base et chaîne vectorielle des centres](04_schemas_cinematiques/figures_parametrage_angles.svg)

---

## 3. Architecture Complète du Dépôt

```text
.
├── index.html                                           # Portail interactif global (Dossier + Feuille A4 + 4 Simulateurs)
├── diagrams_reference.html                              # 3 Planches de référence SII (KaTeX + SVG haute précision)
├── README.md                                            # Documentation principale et aperçu des livrables
├── record.md                                            # Journal d'ingénierie et synthèse de l'audit CPGE SII
├── 01_emails/                                           # Courriels de validation (Partie I) et rendu numérique (Partie II)
├── 02_photos/
│   ├── RAMOS-Selfie.png                                 # Selfie officiel de l'élève avec la Creality Ender 3
│   ├── RAMOS-Ender3-Details.png / .jpg                  # Livrable photo annotée HD (repères locaux R0..R4 + loupe Z + pièces)
│   ├── ender 3 img1 venus de milo.png                   # Photo principale en impression (Vénus de Milo)
│   ├── ender 3 img2.JPG                                 # Photo macro arrière de la vis trapézoïdale Tr8x8 et du coupleur Z
│   └── guide_preparation_photos.md                      # Documentation du dossier photographique
├── 03_modele_mecanique/
│   ├── classes_equivalence_template.md                  # Inventaire exhaustif des 5 classes d'équivalence E0..E4 et repères R0..R4
│   ├── parametrage_vectoriel.md                         # Paramétrage géométrique, figure plane (B0 -> B1) et vecteur O5O4
│   ├── liaisons_torseurs_template.md                    # Répertoire des 5 liaisons et torseurs cinématiques dans B0
│   └── graphe_liaisons_fermeture_template.md            # Graphe des liaisons et fermeture cinématique de la boucle Z
├── 04_schemas_cinematiques/
│   ├── graphe_des_liaisons.svg / .png                   # Graphe des liaisons vectoriel normalisé
│   ├── schema_cinematique_2d.svg / .png                 # Schéma cinématique minimal 2D en couleur (projection frontale)
│   ├── schema_cinematique_3d.svg / .png                 # Schéma cinématique spatial 3D en couleur (perspective cavalière)
│   ├── figures_parametrage_angles.svg / .png            # Figure plane de changement de base et chaîne vectorielle O0..O5
│   ├── guide_trace_2d_3d.md                             # Protocole de tracé à la main 2D/3D et règles AFNOR
│   ├── widget_1_explorateur_3d_2d.html                  # Simulateur 1 : Explorateur interactif 3D/2D (Three.js)
│   ├── widget_2_graphe_simulateur_z.html                # Simulateur 2 : Graphe interactif et fermeture cinématique Z
│   ├── widget_3_inspecteur_ddl_torseurs.html            # Simulateur 3 : Inspecteur des 6 DDL et matrices de torseurs
│   └── widget_4_modele_3d_centres_o0_o5.html            # Simulateur 4 : Modèle 3D spatial des centres O0..O5 et vecteur O5O4
└── 05_dossier_papier/
    ├── DM1_Feuille_Rendu_Imprimable.html                # Feuille de rendu papier A4 calquée sur la Page 2 de l'énoncé
    └── DM1_Dossier_Complet_Rendu.md                     # Dossier écrit complet intégrant photos, schémas et démonstrations
```
