# CB SLOT 27 MHz — Antenne CB Invisible via Lunette Dégivrante

**Version 1.0 — Mars 2026**
**© 2026 InfoProject Software — Julien ARNOULD — Tous droits réservés pour usage commercial**

---

## 📡 Description du projet

Le **CB SLOT 27 MHz** est un boîtier d'accord qui transforme la lunette arrière
dégivrante d'un véhicule en antenne CB (Citizens Band, 27 MHz) totalement invisible.

Le système exploite le principe de l'antenne « slot » (fente) : l'ouverture de la
lunette dans la carrosserie métallique forme une fente rayonnante dont le périmètre
est accordé sur 27 MHz. Les fils de dégivrage existants servent d'éléments de
couplage. Un circuit d'isolation DC permet au dégivrage de continuer à fonctionner
normalement pendant l'utilisation radio.

### Caractéristiques

- Fréquence : 26.965 – 27.405 MHz (40 canaux CB européens)
- Impédance : 50 Ohms (via balun 4:1 ou autotransformateur)
- ROS attendu : 1.3:1 à 1.8:1 au centre de bande
- Puissance max : 15W AM / 30W SSB
- Perte estimée : 3 à 6 dB vs quart d'onde extérieur
- Portée typique : 5–15 km FM, 10–30 km SSB
- Visibilité extérieure : **aucune — 100% invisible**
- Coût des composants : ~20–25 EUR

### Contenu du dépôt

```
CB_Slot_27MHz/
├── README.md                          ← Ce fichier
├── LICENSE.md                         ← Licence complète
├── docs/
│   └── antenne_cb_slot_hybride.pdf    ← Documentation technique (7 pages)
├── gerber/
│   ├── CB_Slot_27MHz-B_Cu.gbr        ← Pistes cuivre (bottom)
│   ├── CB_Slot_27MHz-F_SilkS.gbr     ← Sérigraphie (top)
│   ├── CB_Slot_27MHz-B_Mask.gbr      ← Masque de soudure
│   ├── CB_Slot_27MHz-Edge_Cuts.gbr   ← Contour de carte
│   ├── CB_Slot_27MHz-B_Paste.gbr     ← Pâte à souder
│   └── CB_Slot_27MHz.drl             ← Fichier de perçage Excellon
├── CB_Slot_27MHz_JLCPCB.zip          ← ZIP prêt pour commande JLCPCB
└── src/
    └── generate_gerber.py             ← Générateur de fichiers Gerber
```

### Spécifications PCB

- Dimensions : 80 × 50 mm
- Couches : 1 (simple face)
- Matériau : FR4 1.6 mm
- Cuivre : 1 oz (35 µm)
- Finition : HASL
- Fabricant recommandé : JLCPCB, PCBWay, Aisler

---

## ⚖️ Licence

Ce projet est publié sous licence **Creative Commons Attribution —
NonCommercial — ShareAlike 4.0 International (CC BY-NC-SA 4.0)**.

### Ce que vous POUVEZ faire

✅ Utiliser ce design pour un **usage personnel et non-commercial**
✅ Construire le boîtier d'accord pour votre propre véhicule
✅ Modifier et adapter le design à vos besoins
✅ Partager le design modifié ou non, à condition de respecter les termes ci-dessous

### Ce que vous DEVEZ faire

📌 **Créditer l'auteur** : toute utilisation, publication ou partage doit inclure
la mention suivante :

> « CB SLOT 27 MHz — Conception originale : InfoProject Software,
> Julien ARNOULD (2026) — https://github.com/MetalOS666/Antenne-CB-27-Mhz-Slot-Hybride »

📌 **Partager sous la même licence** : si vous modifiez ou adaptez ce design,
vous devez distribuer vos contributions sous la même licence CC BY-NC-SA 4.0.

### Ce que vous NE POUVEZ PAS faire

🚫 **Vendre** ce design, les fichiers Gerber, les PCB fabriqués, ou des kits
basés sur ce design sans autorisation écrite de l'auteur.
🚫 **Commercialiser** un produit dérivé de ce design sans licence commerciale.
🚫 **Retirer ou modifier** les mentions de copyright sur le PCB ou la documentation.

### Licence commerciale

Pour tout usage commercial (vente de kits, PCB, produits assemblés, intégration
dans un produit commercial), contactez :

**InfoProject Software — Julien ARNOULD**
📧 [alias@infoproject-software.com]

---

## 🔒 Propriété intellectuelle

### Antériorité et originalité

Ce design combine des principes connus (antenne slot, isolation DC par
condensateurs, accord LC) de manière originale pour créer un système
d'antenne CB invisible spécifiquement conçu pour la lunette dégivrante
automobile.

Les antériorités connues dans le domaine sont :
- **InTenna** (Microwave Filter Company, ~1975) : antenne slot CB sur vitre
  avec fil additionnel — principe similaire mais implémentation différente
- **Gold Line Secret Sam** (~1975) : concept comparable à l'InTenna
- **Antennes AM/FM intégrées** aux lunettes (Honda, Toyota, GM) : réception
  uniquement, sans circuit d'accord CB

L'originalité de ce design réside dans :
1. L'utilisation directe des fils de dégivrage existants (pas de fil ajouté)
2. L'isolation DC permettant le fonctionnement simultané du dégivrage
3. Le circuit d'accord dédié à la bande CB 27 MHz sur PCB compact
4. La conception en tant que système complet documenté et reproductible

### Preuve d'antériorité

- Date de création : **Mars 2026**
- Auteur : **Julien ARNOULD / InfoProject Software**

---

## 🛠️ Guide de construction rapide

### Nomenclature (BOM)

| Réf.  | Composant                    | Valeur         | Qté |
|-------|------------------------------|----------------|-----|
| C1    | Condensateur céramique       | 100 pF / 1 kV  | 1   |
| C3    | Condensateur céramique       | 100 pF / 1 kV  | 1   |
| L1    | Bobine sur mandrin PVC 25mm  | 1–5 µH (ajust.)| 1   |
| CV    | Condensateur variable        | 10–150 pF      | 1   |
| T1    | Tore ferrite FT-140-43       | Balun 4:1      | 1   |
| J1    | Embase SO-239                | 50 Ohm         | 1   |
| —     | Câble coaxial RG-58          | 50 Ohm         | 2–4m|
| —     | Boîtier ABS                  | ~100×60×30 mm  | 1   |

### Étapes clés

1. Fabriquer ou commander le PCB (80 × 50 mm, simple face)
2. Souder les composants (voir documentation PDF page 6)
3. Repérer les connexions de la lunette dégivrante du véhicule
4. Se brancher EN PARALLÈLE (pas en série !) sur les fils existants
5. Relier la masse du boîtier au châssis (connexion courte, grattée)
6. Passer le coaxial RG-58 jusqu'au poste CB
7. Accorder avec un tosmètre : ajuster L1 et CV pour ROS minimal

⚠️ **La qualité de la connexion de masse est le facteur n°1 de performance.**

---

## ⚠️ Avertissements

- Ce projet est destiné à un usage sur la bande CB (27 MHz) dans le respect
  de la réglementation en vigueur dans votre pays.
- Puissance maximale autorisée : vérifiez la législation locale (4W AM en
  Europe, 12W SSB selon les pays).
- L'auteur décline toute responsabilité en cas de dommage au véhicule, au
  poste CB, ou d'utilisation non conforme à la réglementation.
- Ne jamais émettre sans avoir vérifié le ROS au tosmètre.
- Ce design n'est pas certifié pour un usage commercial ou professionnel.

---

## 📝 Historique des versions

| Version | Date       | Modifications                              |
|---------|------------|--------------------------------------------|
| 1.0     | Mars 2026  | Version initiale — schéma, PCB, documentation |

---

## 🤝 Contributions

Les contributions sont les bienvenues sous réserve d'acceptation de la licence
CC BY-NC-SA 4.0. En soumettant une contribution, vous acceptez que celle-ci
soit publiée sous les mêmes termes.

Pour signaler un bug, proposer une amélioration ou partager vos résultats
de test, ouvrez une issue ou contactez l'auteur.

---

**73 de Julien — InfoProject Software — 2026**
