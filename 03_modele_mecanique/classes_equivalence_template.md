# Classes d'Équivalence Cinématique (CEC) — Creality Ender 3

> **Norme CPGE MPSI / AFNOR :** Une classe d'équivalence cinématique regroupe l'ensemble des solides indéformables n'ayant aucun mouvement relatif entre eux durant la phase de fonctionnement étudiée (**phase d'impression 3D**).

---

## Préambule Obligatoire : Pièces Exclues des Classes d'Équivalence

Sont **strictement exclus** des classes cinématiques $E_0$ à $E_4$ :

1. **Les pièces déformables (organes de transmission souples, ressorts et matière d'œuvre) :**
   * La **courroie crantée ouverte de l'axe X** et la **courroie crantée ouverte de l'axe Y** (profil GT2, pas de $2\text{ mm}$, largeur $6\text{ mm}$, en néoprène armé de fibres de verre).
   * Le **tube de guidage capillaire en PTFE** (*tube Bowden*) reliant la sortie de l'extrudeur à l'entrée de la tête d'impression.
   * Les **4 ressorts hélicoïdaux de compression** de nivellement du plateau chauffant et le **ressort hélicoïdal de mise en pression** du levier d'extrudeur.
   * Les **faisceaux de câbles électriques**, nappes souples de l'écran et gaines textiles tressées.
   * Le **filament thermoplastique** (PLA/ABS/PETG) de diamètre $1{,}75\text{ mm}$.

2. **Les éléments roulants réalisant les liaisons par roulement :**
   * Les **13 galets de guidage à profil en V (*V-wheels*) en POM** (Polyoxyméthylène / Delrin) ainsi que les **billes et les bagues extérieures** de leurs roulements rigides à billes internes (type 625ZZ, à raison de 2 roulements par galet, soit 26 roulements) : 6 galets entre $E_2$ et $E_0$, 3 galets entre $E_3$ et $E_2$, et 4 galets entre $E_4$ et $E_0$.
   * Les **billes des roulements internes** des moteurs pas-à-pas NEMA 17 et les **poulies folles de renvoi** (axes X et Y) avec leurs billes.

3. **La chaîne cinématique secondaire d'extrusion et de ventilation :**
   * Le rotor du moteur d'extrudeur (et sa roue dentée d'entraînement en laiton), le galet presseur à gorge sur roulement U604ZZ, ainsi que les hélices (rotors) des 4 ventilateurs.

---

## 1. Tableau Récapitulatif des 5 Classes d'Équivalence

| Classe | Désignation fonctionnelle | Code couleur normalisé | Mouvement par rapport au bâti $E_0$ |
| :---: | :--- | :---: | :--- |
| **$E_0$** | **Bâti fixe** | **Noir** (+ symbole $\equiv\mkern-10mu\perp$) | Solide de référence fixe |
| **$E_1$** | **Arbre moteur Z / Vis d'entraînement Z** | **Bleu** | Rotation d'axe $(O_1, \vec{z}_0)$ |
| **$E_2$** | **Portique mobile de l'axe X (Traverse X)** | **Rouge** | Translation rectiligne de direction $\vec{z}_0$ |
| **$E_3$** | **Chariot de tête d'impression (Hotend)** | **Vert** | Translation plane (selon $\vec{z}_0$ + selon $\vec{x}_0$) |
| **$E_4$** | **Plateau chauffant mobile de l'axe Y** | **Orange** | Translation rectiligne de direction $\vec{y}_0$ |

---

## 2. Inventaire Exhaustif des Pièces Physiques Réelles

### Classe $E_0$ : Bâti fixe — Couleur : Noir (avec symbole normalisé du bâti $\equiv\mkern-10mu\perp$)
* **Châssis mécano-assemblé en profilés d'aluminium extrudé anodisé noir à rainures en V (*V-Slot*) :**
  * **2 traverses basses latérales (pieds gauche et droit)** en profilé aluminium **4040 V-Slot**, équipées de **4 patins amortisseurs antidérapants en élastomère** collés sous leurs faces inférieures.
  * **1 traverse basse centrale (rail de guidage de l'axe Y)** en profilé aluminium **2040 V-Slot** orienté verticalement, assemblée orthogonalement aux deux pieds 4040.
  * **1 traverse basse avant** en profilé aluminium **2020 V-Slot** reliant les deux pieds 4040.
  * **2 montants verticaux (colonnes de guidage de l'axe Z, gauche et droit)** en profilé aluminium **2040 V-Slot**, vissés par le dessous des pieds 4040 via 4 vis CHC M5$\times$45.
  * **1 traverse supérieure de fermeture du portique fixe** en profilé aluminium **2020 V-Slot**, coiffant le sommet des deux montants 2040 (assemblée par 4 vis CHC M5$\times$25), et ses **2 bouchons caches d'extrémité en ABS noir**.
* **Organes fixes de motorisation et de guidage des axes Z et Y :**
  * **Stator (carcasse fixe)** du moteur pas-à-pas **NEMA 17 de l'axe Z** (modèle 42-34) et les bagues extérieures de ses roulements internes.
  * **Équerre support du moteur Z** en polymère injecté noir, fixée à la base du montant vertical gauche 2040 par 2 vis CHC M4$\times$18 et **2 écrous marteaux (*T-nuts*) M4**.
  * **Stator (carcasse fixe)** du moteur pas-à-pas **NEMA 17 de l'axe Y** (modèle 42-34) et les bagues extérieures de ses roulements internes.
  * **Platine support moteur Y** en tôle d'acier découpée et pliée peinte en noir, fixée à l'extrémité arrière du profilé central Y 2040.
  * **Support tendeur de courroie Y** en tôle d'acier pliée fixé à l'extrémité avant du profilé central Y, l'**axe cylindrique fixe de la poulie folle de renvoi Y**, et la bague intérieure du roulement de cette poulie.
* **Capteurs de fin de course (*Endstops*), électronique et alimentation :**
  * **Capteur de fin de course optique/mécanique de l'axe Z (*Z-Endstop*)** : circuit imprimé (PCB), corps du microrupteur à levier métallique, support en plastique moulé à butée latérale, fixé sur le montant gauche 2040 par 2 vis M4 et écrous *T-nuts*.
  * **Capteur de fin de course de l'axe Y (*Y-Endstop*)** : circuit imprimé (PCB), corps du microrupteur et platine support fixée à l'arrière du profilé central Y 2040.
  * **Boîtier électronique principal** en tôle d'acier pliée noire fixé à l'avant gauche, renfermant la **carte mère Creality** (entretoises + vis M3), le lecteur de carte micro-SD, le connecteur micro-USB, et le **stator du ventilateur axial 4010** de refroidissement de l'électronique.
  * **Bloc d'alimentation à découpage 24 V DC / 360 W** : boîtier métallique en aluminium fixé sur le flanc arrière du montant vertical droit 2040 par 2 vis CHC M4$\times$20, son boîtier bornier inférieur en plastique noir, l'interrupteur secteur bipolaire à bascule et l'embase secteur IEC C14.
  * **Module d'interface homme-machine (écran LCD 12864)** : platine console inclinée en tôle d'acier pliée noire fixée à l'avant du pied droit 4040, circuit imprimé de l'écran monochrome, buzzer piézoélectrique et corps fixe du codeur rotatif.
  * **Ensemble porte-bobine** : équerre en tôle d'acier pliée noire fixée sur la traverse supérieure 2020 (vis M4 + écrous *T-nuts*), tube cylindrique porte-bobine fileté en plastique noir et son grand écrou moleté de blocage.
  * **Visserie d'assemblage structurel du châssis** : ensemble des vis CHC M5 et M4, rondelles plates, rondelles frein *Grower* et écrous marteaux (*T-nuts*) liant ces éléments.

---

### Classe $E_1$ : Arbre moteur Z / Vis d'entraînement Z — Couleur : Bleu
* **Rotor et arbre de sortie cylindrique ($\varnothing 5\text{ mm}$ à méplat)** du moteur pas-à-pas **NEMA 17 de l'axe Z** (ainsi que les bagues intérieures de ses roulements de guidage internes).
* **Coupleur rigide fendu (manchon d'accouplement) en alliage d'aluminium** ($\varnothing 5\text{ mm}$ alésage inférieur / $\varnothing 8\text{ mm}$ alésage supérieur) et ses **2 vis de serrage radial CHC M3** assurant l'encastrement avec l'arbre moteur et la vis.
* **Vis mère à filet trapézoïdal Tr8x8 en acier inoxydable** (diamètre nominal $d = 8\text{ mm}$, pas du profil $2\text{ mm}$ à 4 filets, soit un **pas hélicoïdal d'avance $p_z = 8\text{ mm/tr}$**).

---

### Classe $E_2$ : Portique mobile de l'axe X (Traverse X) — Couleur : Rouge
* **Structure du portique et organes de liaison avec $E_1$ et $E_0$ :**
  * **Traverse horizontale de guidage de l'axe X** en profilé aluminium **2020 V-Slot** anodisé noir.
  * **Platine chariot Z gauche (platine porte-moteur X et extrudeur)** en tôle d'acier découpée et pliée peinte en noir, encastrée à l'extrémité gauche du profilé 2020 par 2 vis CHC M4$\times$16.
  * **Platine chariot Z droite** en tôle d'acier découpée et pliée peinte en noir, encastrée à l'extrémité droite du profilé 2020 par 2 vis CHC M4$\times$16.
  * **Écrou trapézoïdal en laiton Tr8x8 à collerette**, fixé sur le retour horizontal de la platine chariot Z gauche par 2 vis CHC M3 et rondelles frein.
  * **Axes et entretoises des 6 galets V-wheel de guidage Z** (3 sur la platine gauche, 3 sur la platine droite) : **4 entretoises cylindriques lisses en aluminium** (galets extérieurs), **2 entretoises excentriques à six pans en acier** (galets intérieurs permettant le réglage de précharge sans jeu sur les montants 2040), les 6 vis CHC M5$\times$30, les 6 écrous frein *Nylstop* M5, et les **bagues intérieures** des 12 roulements 625ZZ.
* **Motorisation de l'axe X, renvoi et parties fixes de l'extrudeur déporté (*Bowden*) :**
  * **Stator (carcasse)** du moteur pas-à-pas **NEMA 17 de l'axe X** (modèle 42-34), fixé sur la platine chariot Z gauche par 4 vis CHC M3.
  * **Capot protecteur en plastique moulé noir** (portant le QR code Creality) vissé sur le moteur X, et le **capteur de fin de course de l'axe X (*X-Endstop*)** (PCB + corps du microrupteur logé sous ce capot).
  * **Support tendeur de courroie X** en tôle d'acier pliée fixé à l'extrémité droite du profilé 2020 (par 2 vis CHC M4 et écrous *T-nuts*), l'**axe fixe de la poulie folle de renvoi X** et la bague intérieure de son roulement.
  * **Parties statiques de l'extrudeur MK8 déporté** : **stator** du moteur pas-à-pas **NEMA 17 d'extrusion** (modèle 42-40), embase fixe de l'extrudeur en plastique moulé noir (et son levier presseur qui reste quasi-immobile une fois le filament engagé), vis pivot M3 et **raccord pneumatique instantané (*pneufit*) PC4-M6** en laiton maintenant l'entrée du tube PTFE.

---

### Classe $E_3$ : Chariot de tête d'impression (Tête d'extrusion) — Couleur : Vert
* **Chariot et guidage sur la traverse X :**
  * **Platine support de tête (chariot X)** en tôle d'acier pliée peinte en noir, comportant à sa base les deux fentes d'ancrage où sont bloqués les **2 embouts sertis en laiton** de la courroie GT2 de l'axe X.
  * **Axes et entretoises des 3 galets V-wheel de guidage X** : **2 entretoises cylindriques lisses en aluminium** (galets supérieurs), **1 entretoise excentrique hexagonale en acier** (galet inférieur de mise en précharge), les 3 vis à tête bombée six pans creux (TBHC) M5$\times$30, les 3 écrous frein *Nylstop* M5, et les **bagues intérieures** des 6 roulements 625ZZ.
* **Tête thermique d'impression (*Hotend* type MK8) et système de ventilation :**
  * **Raccord pneumatique instantané supérieur (*pneufit*) PC4-M10** vissé au sommet du radiateur.
  * **Dissipateur thermique (radiateur à ailettes)** en alliage d'aluminium anodisé rouge, fixé sur la platine chariot X par 2 vis CHC M3$\times$16.
  * **Barrière thermique (*heatbreak*)** : tube de liaison fileté en acier inoxydable reliant le dissipateur froid au bloc chaud.
  * **Bloc de chauffe (*heater block*)** en alliage d'aluminium, équipé de sa **cartouche chauffante cylindrique** (24 V / 40 W, immobilisée par une vis sans tête HC M3), de sa **sonde thermistance CTN 100 k$\Omega$** (immobilisée par une vis cruciforme M3), et de sa **gaine isolante thermique** (chaussette silicone ou bande fibre de verre/Kapton).
  * **Buse d'extrusion (*nozzle*)** en laiton filetée M6 (calibre d'origine $\varnothing 0{,}4\text{ mm}$), vissée à chaud contre le *heatbreak* dans le bloc de chauffe.
  * **Carénage de ventilation (capot de tête)** en tôle d'acier pliée peinte en noir, fixé sur la platine chariot X par 2 vis M3.
  * **Stator du ventilateur axial 4010** (24 V, refroidissement continu du dissipateur rouge, vissé par 4 vis M3 à l'intérieur du carénage) et **stator du ventilateur radial à turbine 4010** (24 V, refroidissement du filament déposé, vissé sur le flanc droit du carénage avec sa **buse de soufflage directionnelle** en plastique noir).

---

### Classe $E_4$ : Ensemble Plateau chauffant mobile (Axe Y) — Couleur : Orange

> **Justification mécanique indispensable en CPGE :** Le réglage de planéité (nivellement du plateau par les 4 molettes et ressorts) s'effectue **hors impression**. Durant le cycle d'impression, les 4 ressorts hélicoïdaux fortement précontraints maintiennent une distance constante entre le plateau chauffant et la platine chariot Y : ces deux sous-ensembles n'ont **aucun mouvement relatif en fonctionnement normal** et appartiennent donc à la **même classe d'équivalence cinématique $E_4$**.

* **Chariot inférieur et guidage sur le rail central Y :**
  * **Platine chariot Y** en tôle d'acier découpée et pliée peinte en noir, comprenant la patte centrale inférieure dans laquelle viennent s'encastrer les **2 embouts sertis en laiton** de la courroie GT2 de l'axe Y.
  * **Axes et entretoises des 4 galets V-wheel de guidage Y** : **2 entretoises cylindriques lisses en aluminium** (côté gauche), **2 entretoises excentriques hexagonales en acier** (côté droit, pour annuler le jeu sur le profilé 2040), les 4 vis M5, les 4 écrous frein *Nylstop* M5, et les **bagues intérieures** des 8 roulements 625ZZ.
  * **4 vis de nivellement à tête fraisée M4** et les **4 grandes molettes crantées de réglage** en plastique noir à insert métallique fileté M4.
* **Lit chauffant (*Heatbed*) et surface d'impression :**
  * **Plaque du plateau chauffant en alliage d'aluminium** ($235 \times 235 \times 3\text{ mm}$) intégrant sur sa face inférieure le **circuit imprimé résistif chauffant** (24 V / 220 W), la **thermistance CTN** collée au centre inférieur, et le **capot passe-câble d'angle en plastique noir** (à l'arrière gauche).
  * **Revêtement d'adhérence amovible en polycarbonate texturé** (surface *BuildTak* noire siglée Ender, d'origine sur l'Ender 3 de base) et les **4 pinces à dessin métalliques (clips)** l'immobilisant sur la plaque d'aluminium.
