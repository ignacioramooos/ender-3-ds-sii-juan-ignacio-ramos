# Graphe des Liaisons et Fermeture Cinématique

**Système étudié :** Imprimante 3D Creality Ender 3  
**Matière :** Sciences Industrielles de l'Ingénieur (SII) — CPGE MPSI (Lycée Stanislas Cannes)  
**Professeur :** Mme M. Prot

![Graphe des liaisons de la Creality Ender 3](../04_schemas_cinematiques/graphe_des_liaisons.svg)

---

## 1. Structure du Graphe des Liaisons

Le graphe des liaisons comporte :
- **5 sommets** représentant les **5 sous-ensembles cinématiques** : **Châssis fixe** (Noir, bâti $\underline{\underline{\equiv\mkern-10mu\perp}}$), **Vis centrale** (Bleu), **Traverse horizontale** (Rouge), **Chariot tête extrudeur** (Vert) et **Plateau mobile** (Rose clair).
- **5 liaisons** : $L_{01}$ (Pivot), $L_{12}$ (Hélicoïdale), $L_{02}$ (Glissière $Z$), $L_{23}$ (Glissière $X$), $L_{04}$ (Glissière $Y$).
- **Architecture :** Une chaîne fermée d'élévation verticale $Z$ (Châssis fixe — Vis centrale — Traverse horizontale) et deux chaînes ouvertes orthogonales ($X$ et $Y$).

---

## 2. Fermeture Cinématique de la Boucle d'Élévation $Z$

La relation de composition des torseurs cinématiques réduits au même point $O_2 \in (O_1, \vec{z}_0)$ s'écrit :
$$\{\mathcal{V}(\text{Traverse}/\text{Châssis})\}_{O_2} = \{\mathcal{V}(\text{Traverse}/\text{Vis})\}_{O_2} + \{\mathcal{V}(\text{Vis}/\text{Châssis})\}_{O_2}$$

1. **Transport de $\{\mathcal{V}(\text{Vis}/\text{Châssis})\}$ de $O_1$ en $O_2$ via la formule de Varignon :**
   $$\vec{V}(O_2 \in \text{Vis}/\text{Châssis}) = \vec{V}(O_1 \in \text{Vis}/\text{Châssis}) + \overrightarrow{O_2 O_1} \wedge \vec{\Omega}(\text{Vis}/\text{Châssis}) = \vec{0} + \big(-z_2(t)\,\vec{z}_0\big) \wedge \big(\omega_{10}(t)\,\vec{z}_0\big) = \vec{0}$$

2. **Résolution scalaire et loi d'entrée-sortie :**
   $$\begin{cases}
   \text{Résultante selon } \vec{z}_0 : & 0 = \omega_{21}(t) + \omega_{10}(t) \quad \Longrightarrow \quad \omega_{21}(t) = -\omega_{10}(t) = -\dot{\theta}_1(t) \\[6pt]
   \text{Moment en } O_2\text{ selon } \vec{z}_0 : & V_z(t) = v_{21}(t) = +\dfrac{p_z}{2\pi}\,\omega_{21}(t)
   \end{cases}$$

   D'où la **loi d'entrée-sortie cinématique** :
   $$\boxed{V_z(t) = \dot{z}_2(t) = -\frac{p_z}{2\pi}\,\omega_{10}(t) = -\frac{p_z}{2\pi}\,\dot{\theta}_1(t) = +\frac{p_z}{2\pi}\,\omega_m(t)}$$
   où $\omega_m(t) = -\omega_{10}(t) > 0$ représente la vitesse angulaire motrice de montée ($p_z = 8\text{ mm/tr}$).
