# PROMPT 2 : IDENTIFICATION DES LIAISONS & TORSEURS CINÉMATIQUES

> **Objectif :** Obtenir la justification mécanique, les degrés de liberté et l'écriture matricielle normalisée des torseurs cinématiques pour l'Ender 3.

```text
Tu es professeur de SII en CPGE MPSI.
Dans le cadre de mon DM n°1 sur l'imprimante 3D Creality Ender 3, caractérise de manière formelle les liaisons mécaniques normalisées (NF EN ISO 3952) suivantes :

1. L01 (E0 / E1) : Liaison Pivot d'axe (O1, z0)
2. L12 (E1 / E2) : Liaison Hélicoïdale d'axe (O2, z0) de pas pz = 8 mm/tour (à pas à droite)
3. L02 (E0 / E2) : Liaison Glissière de direction z0 (centre O3)
4. L23 (E2 / E3) : Liaison Glissière de direction x0 (centre O4)
5. L04 (E0 / E4) : Liaison Glissière de direction y0 (centre O5)

Pour CHAQUE liaison :
- Nom normalisé complet et caractéristiques géométriques.
- Solution constructive réelle sur la machine (guidage par galets POM en V dans rainures profilé alu, roulements à billes du moteur Z, contact vis-écrou).
- Tableau des 6 degrés de liberté (Tx, Ty, Tz, Rx, Ry, Rz : 0 ou 1).
- Écriture formelle du torseur cinématique {V(j/i)} en son centre caractéristique sous forme matricielle 2 colonnes / 3 lignes (taux de rotation à gauche, vecteur vitesse linéaire à droite) dans la base (x0, y0, z0).
```
