# 2. Fermeture Cinématique de la Boucle Z & Graphe des Liaisons

---

## 1. Fermeture Cinématique de la Boucle $Z$ ($E_0 - E_1 - E_2 - E_0$)

### Équation torsorielle de fermeture cinématique

Par composition des mouvements sur la chaîne fermée $E_0 - E_1 - E_2 - E_0$, la loi de composition des torseurs cinématiques s'écrit :

$$\{\mathcal{V}(E_2/E_0)\} = \{\mathcal{V}(E_2/E_1)\} + \{\mathcal{V}(E_1/E_0)\}$$

Pour exploiter algébriquement cette égalité torsorielle, il est **impératif de réduire les trois torseurs au même point géométrique**. Choisissons le point $O_2$, centre de la liaison hélicoïdale $L_{12}$.

---

### Transport des moments en $O_2$ par la relation de Varignon

1. **Transport de $\{\mathcal{V}(E_2/E_0)\}$ de $O_3$ en $O_2$ :**
   La résultante $\vec{\Omega}(E_2/E_0)$ étant nulle (mouvement de translation pure), le champ des vecteurs vitesse de $E_2/E_0$ est uniforme dans tout l'espace :
   $$\vec{V}(O_2, E_2/E_0) = \vec{V}(O_3, E_2/E_0) + \underbrace{\vec{\Omega}(E_2/E_0)}_{=\,\vec{0}} \wedge \overrightarrow{O_3 O_2} = V_z(t)\,\vec{z}_0$$

2. **Transport de $\{\mathcal{V}(E_1/E_0)\}$ de $O_1$ en $O_2$ :**
   Par application de la formule de changement de point du moment d'un torseur (relation de Varignon) :
   $$\vec{V}(O_2, E_1/E_0) = \vec{V}(O_1, E_1/E_0) + \vec{\Omega}(E_1/E_0) \wedge \overrightarrow{O_1 O_2}$$

   **Démonstration de l'annulation du terme de transport :**
   * Le point $O_1$ appartient à l'axe de la liaison pivot $L_{01}$, donc $\vec{V}(O_1, E_1/E_0) = \vec{0}$.
   * Par construction géométrique de l'axe vertical, la liaison pivot $L_{01}$ et la liaison hélicoïdale $L_{12}$ sont **coaxiales** : elles partagent le même axe géométrique $(O_1, \vec{z}_0)$ de la vis trapézoïdale. Le point $O_2$ appartient donc à la droite $(O_1, \vec{z}_0)$, ce qui se traduit vectoriellement par :
     $$\overrightarrow{O_1 O_2} = z_{12}(t)\,\vec{z}_0$$
   * Le vecteur taux de rotation est $\vec{\Omega}(E_1/E_0) = \omega_m(t)\,\vec{z}_0$.
   * Les deux vecteurs $\vec{\Omega}(E_1/E_0)$ et $\overrightarrow{O_1 O_2}$ étant **colinéaires** (portés tous deux par $\vec{z}_0$), leur produit vectoriel est identiquement nul :
     $$\vec{\Omega}(E_1/E_0) \wedge \overrightarrow{O_1 O_2} = \left(\omega_m(t)\,\vec{z}_0\right) \wedge \left(z_{12}(t)\,\vec{z}_0\right) = \omega_m(t)\,z_{12}(t)\,\underbrace{\left(\vec{z}_0 \wedge \vec{z}_0\right)}_{=\,\vec{0}} = \vec{0}$$
   * On en conclut immédiatement :
     $$\boxed{\vec{V}(O_2, E_1/E_0) = \vec{0}}$$

---

### Projection sur l'axe $\vec{z}_0$ et loi d'entrée-sortie en vitesse

L'équation torsorielle réduite au point $O_2$ dans la base $\mathcal{B}_0$ s'écrit alors :

$$\begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ 0 & V_z(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} = \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_{21}(t) & -\dfrac{p_z}{2\pi}\,\omega_{21}(t) \end{Bmatrix}_{O_2, \mathcal{B}_0} + \begin{Bmatrix} 0 & 0 \\ 0 & 0 \\ \omega_m(t) & 0 \end{Bmatrix}_{O_2, \mathcal{B}_0}$$

En projetant sur l'axe $\vec{z}_0$ :

1. **Équation de résultante selon $\vec{z}_0$ :**
   $$0 = \omega_{21}(t) + \omega_m(t) \iff \omega_{21}(t) = -\omega_m(t)$$

2. **Équation de moment (vitesse linéaire en $O_2$) selon $\vec{z}_0$ :**
   $$V_z(t) = -\frac{p_z}{2\pi}\,\omega_{21}(t) + 0$$

En substituant $\omega_{21}(t) = -\omega_m(t)$ dans l'équation de vitesse, on obtient la **loi d'élévation scalaire (loi d'entrée-sortie cinématique)** :

$$\boxed{V_z(t) = \frac{p_z}{2\pi}\,\omega_m(t)}$$

---

### Relation intégrée et déplacement incrémental pour 1 pas moteur

En notant $V_z(t) = \dfrac{\mathrm{d}Z(t)}{\mathrm{d}t}$ et $\omega_m(t) = \dfrac{\mathrm{d}\theta_m(t)}{\mathrm{d}t}$, la relation devient :

$$\frac{\mathrm{d}Z(t)}{\mathrm{d}t} = \frac{p_z}{2\pi}\,\frac{\mathrm{d}\theta_m(t)}{\mathrm{d}t}$$

Par intégration temporelle entre deux instants quelconques (le rapport de transmission $\dfrac{p_z}{2\pi}$ étant constant), on obtient la relation entre la variation de cote verticale $\Delta Z$ et la rotation angulaire du moteur $\Delta\theta_m$ (exprimée en radians) :

$$\boxed{\Delta Z = \frac{p_z}{2\pi}\,\Delta\theta_m}$$

#### Application numérique pour 1 pas moteur ($\Delta\theta_{\text{pas}} = 1{,}8^\circ$) :

1. **Conversion de l'angle de pas en radians :**
   $$\Delta\theta_{\text{pas}} = 1{,}8^\circ \times \frac{\pi}{180^\circ} = \frac{\pi}{100}\text{ rad} \quad (\text{soit } 200\text{ pas par tour complet})$$

2. **Calcul du déplacement vertical élémentaire $\Delta Z_{\text{pas}}$ avec $p_z = 8\text{ mm/tr}$ :**
   $$\Delta Z_{\text{pas}} = \frac{8}{2\pi} \times \frac{\pi}{100} = \frac{8}{200} = 0{,}04\text{ mm}$$

   $$\boxed{\Delta Z_{\text{pas}} = 0{,}04\text{ mm} = 40\ \mu\text{m}}$$

---

## 2. Graphe des Liaisons

### Description méthodique du tracé sur votre copie

1. **Les nœuds (sommets du graphe) :**
   Tracez **5 cercles (ou ellipses)** bien espacés représentant les 5 classes d'équivalence cinématique : $E_0$, $E_1$, $E_2$, $E_3$ et $E_4$.
2. **Le symbole normalisé de bâti fixe sur $E_0$ :**
   Au bas du cercle $E_0$, tracez un petit segment vertical aboutissant sur un trait horizontal souligné de **hachures obliques parallèles** (symbole normalisé de la référence mécanique / bâti galiléen).
3. **Les arêtes (arcs de liaison) et l'architecture topologique :**
   Le mécanisme possède une structure **mixte** composée d'une **chaîne fermée** (boucle d'élévation $Z$) et de **deux chaînes ouvertes** (axes $X$ et $Y$) :
   * **La boucle fermée $(E_0 - E_1 - E_2 - E_0)$ :**
     * Reliez $E_0$ à $E_1$ par un trait continu annoté : **$L_{01}$ : Pivot $(O_1, \vec{z}_0)$**.
     * Reliez $E_1$ à $E_2$ par un trait continu annoté : **$L_{12}$ : Hélicoïdale $(O_2, \vec{z}_0)$, pas $p_z = 8\text{ mm/tr}$**.
     * Reliez directement $E_0$ à $E_2$ par un second chemin pour fermer le cycle, annoté : **$L_{02}$ : Glissière $(\vec{z}_0)$ en $O_3$**.
   * **La première branche ouverte $(E_2 - E_3)$ :**
     * Depuis le nœud $E_2$, tirez une arête vers le nœud $E_3$ annotée : **$L_{23}$ : Glissière $(\vec{x}_0)$ en $O_4$**.
   * **La seconde branche ouverte $(E_0 - E_4)$ :**
     * Depuis le nœud $E_0$ (du côté opposé à la boucle $Z$ pour aérer le dessin), tirez une arête vers le nœud $E_4$ annotée : **$L_{04}$ : Glissière $(\vec{y}_0)$ en $O_5$**.

### Disposition spatiale recommandée sur votre feuille

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
