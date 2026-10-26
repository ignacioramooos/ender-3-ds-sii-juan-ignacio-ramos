# Dossier Photographique & Paramétrage sur Système Réel (`02_photos/`)

Ce dossier regroupe l'ensemble des photographies officielles de votre imprimante 3D **Creality Ender 3** (modèle de base) ainsi que la planche de paramétrage et d'identification des pièces prête à être imprimée pour votre rendu papier (Partie III) et jointe à votre envoi numérique (Partie II).

---

## 1. Inventaire des Fichiers du Dossier

| Fichier | Rôle vis-à-vis du sujet de DM | Statut |
| :--- | :--- | :---: |
| **[`RAMOS-Selfie.png`](./RAMOS-Selfie.png)** | **Selfie obligatoire (Partie II & Page 2 du DM) :** Vous montre clairement à côté de votre imprimante Creality Ender 3 personnelle. | ✅ Prêt |
| **[`ender 3 img1 venus de milo.png`](./ender%203%20img1%20venus%20de%20milo.png)** | **Vue frontale en fonctionnement (plan $O_0, \vec{x}_0, \vec{z}_0$) :** Vue de face de l'imprimante en cours d'impression de la *Vénus de Milo*, mettant en évidence le portique X ($E_2$), le chariot de tête ($E_3$), le plateau chauffant Y ($E_4$) et le bâti ($E_0$). | ✅ Prêt |
| **[`ender 3 img2.JPG`](./ender%203%20img2.JPG)** | **Vue rapprochée de la chaîne cinématique Z :** Met en évidence la vis mère trapézoïdale Tr8x8 en acier inoxydable ($E_1$), le coupleur rigide fendu en aluminium ($O_1$), l'écrou en laiton ($O_2$) et le moteur d'extrudeur MK8 ($E_2$). | ✅ Prêt |
| **[`RAMOS-Ender3-Details.png`](./RAMOS-Ender3-Details.png)** & **[`RAMOS-Ender3-Details.jpg`](./RAMOS-Ender3-Details.jpg)** | **Planche officielle annotée (Livrable Partie II & Partie III) :** Intègre la vue frontale (Vénus de Milo) + la loupe arrière de la vis Z (Photo 2), le repère global direct $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$, les repères locaux $\mathcal{R}_1 \dots \mathcal{R}_4$, les centres de liaison $O_1 \dots O_5$, les paramètres cinématiques $\theta_1(t), z_2(t), x_3(t), y_4(t)$ et le pointage normalisé des 5 classes d'équivalence ($E_0$ à $E_4$). | ✅ Généré en HD |

---

## 2. Aperçu Direct de la Planche Annotée (`RAMOS-Ender3-Details.png`)

![Planche de paramétrage et d'identification des classes d'équivalence sur la Creality Ender 3](./RAMOS-Ender3-Details.png)

---

## 3. Rappel des Conventions Géométriques Tracées sur la Photo

Si vous souhaitez repasser ou compléter certaines annotations au feutre fin sur votre tirage papier :

1. **Repère global orthonormé direct $\mathcal{R}_0(O_0, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié au bâti fixe $E_0$ (Noir, symbole $\equiv\mkern-10mu\perp$) :**
   * $\vec{x}_0$ : Horizontal transversal, orienté **vers la droite** (le long du profilé du portique X).
   * $\vec{z}_0$ : Vertical **ascendant** (le long de la vis trapézoïdale et des montants verticaux).
   * $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ : Horizontal longitudinal, orienté **vers l'arrière de la machine** (**entrant** dans le plan de la photo : symbole $\otimes\,\vec{y}_0$).
     > **Attention (règle du trièdre direct en CPGE) :** Avec $\vec{x}_0$ vers la droite et $\vec{z}_0$ vers le haut, le vecteur $\vec{y}_0 = \vec{z}_0 \wedge \vec{x}_0$ est impérativement **entrant** ($\otimes\,\vec{y}_0$), et non sortant !

2. **Repères locaux et paramètres de mouvement des 4 classes mobiles :**
   * **En $O_1$ (Pivot $L_{01}$ d'axe $(O_1, \vec{z}_0)$) :** Repère local $\mathcal{R}_1(O_1, \vec{x}_1, \vec{y}_1, \vec{z}_0)$ lié à la vis mère $E_1$ (Bleu), paramétré par l'angle de rotation $\theta_1(t) = (\widehat{\vec{x}_0, \vec{x}_1})$.
   * **En $O_2$ et $O_3$ (Hélicoïdale $L_{12}$ et Glissière $L_{02}$ d'axe $\vec{z}_0$) :** Repère local $\mathcal{R}_2(O_3, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié au portique $E_2$ (Rouge), paramétré par la cote verticale $z_2(t)\,\vec{z}_0$.
   * **En $O_4$ (Glissière $L_{23}$ de direction $\vec{x}_0$) :** Repère local $\mathcal{R}_3(O_4, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié au chariot de tête $E_3$ (Vert), paramétré par l'abscisse transversale $x_3(t)\,\vec{x}_0$.
   * **En $O_5$ (Glissière $L_{04}$ de direction $\vec{y}_0$) :** Repère local $\mathcal{R}_4(O_5, \vec{x}_0, \vec{y}_0, \vec{z}_0)$ lié au plateau chauffant $E_4$ (Orange), paramétré par la profondeur longitudinale $y_4(t)\,\vec{y}_0$.
