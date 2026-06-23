---
title: Enclenchement du Groupe de Travail Mécamat sur la capitalisation et le partage des connaissances matériau
author: Charles Toulemonde, Thomas Helfer
date: 27/01/2026
lang: fr-FR
link-citations: true
colorlinks: true
toc: true
toc-depth: 3
numbersections: true
geometry:
  - margin=2cm
papersize: a4
figPrefixTemplate: "$$i$$"
tblPrefixTemplate: "$$i$$"
secPrefixTemplate: "$$i$$"
eqnPrefixTemplate: "($$i$$)"
---

# Participants

- [Yves Chemisky](mailto:Yves.Chemisky@univ-grenoble-alpes.fr)
- [Pierre Olivier SANTACREU](mailto:pierre-olivier.santacreu@aperam.com)
- [Fabrice Detrez](mailto:fabrice.detrez@univ-eiffel.fr)
- [Florian Devlaminck](mailto:Florian.DEVLAMINCK@cea.fr)
- [Aldo Marano](mailto:aldo.marano@onera.fr)
- [Adam Najem](mailto:adam.najem@ensam.eu)
- [Pierre Emmanuel Léger](mailto:pierreemmanuel.leger@aperam.com)
- [Arnaud Lejeune](mailto:arnaud.lejeune@univ-fcomte.fr)
- [Frederic PERALES](mailto:frederic.perales@asnr.fr)
- [Jeremy Bleyer](mailto:jeremy.bleyer@enpc.fr)
- [Pascal Bouda](mailto:pascal.bouda@cea.fr)
- [Bénédicte Reine](mailto:benedicte.reine@irt-saintexupery.com)
- [Basile Marchand](mailto:basile.marchand@simvia.tech)
- [Jacques Besson](mailto:jacques.besson@minesparis.psl.eu)
- [Francois Curtit](mailto:francois.curtit@edf.fr)
- [Marius Duvillard](mailto:Marius.DUVILLARD@cea.fr)
- [Vincent Fardeau](mailto:vincent.fardeau@cea.fr)
- [Charles Toulemonde](mailto:charles.toulemonde@edf.fr)
- [Thomas Helfer](mailto:thomas.helfer@cea.fr)

# Déroulement

Thomas Helfer et Charles Toulemonde présentent l'historique de la
mobilisation dans MECAMAT sur les outils liés à la connaissance des
matériaux : identification, base de données.

Thomas présente les contraintes apportées par le guide 28 et le GT VAES
de l'institut tripartite (EDF/Framatome/CEA). Charles précise que la
démarche intéresse les industriels pour des questions d'assurance
qualité mais aussi les scientifiques pour des questions de
reproductibilité (science ouverte).

Sur le domaine du combustible, EDF et CEA ont mis en place une chaîne
numérique allant de la capitalisation des données expérimentales à
l'identifications des lois de comportement. L'ensemble donne lieu à la
mise en oeuvre de tests de non-régression permettant de tester la
stabilité de l'édifice.

Bien que cet historique soit fortement influencé par les activités des
organisateurs, Charles et Thomas rappellent que:

- la thématique est générale et transversale pour les industriels et les
  académiques,
- les thèmes abordés sont complémentaires de ceux des autres GT MECAMAT.

Charles présente quelques thématiques d'intérêt *a priori*, dans le but
de diriger le tour de table:

- Liste des logiciels disponibles (opensource/commerciaux)
- Format d’échanges des données expérimentales, au-delà d’Abaqus/UMAT
  - Stockage des données de grandes tailles (analyse d’images, tomographie)
- Stabilité dans le temps:
  - Intégration continue
- Implémentation des lois de comportement
- Fiabilité des lois générées par intelligence artificielle
- Logiciels d’identification
- Bases de capitalisation
- Transfert vers l’ingénierie, études
- Codes et normes, type RCCM

# Tour de table

## Bénédicte Reine: Matériaux composites, base de données de capitalisation

- [GEMSEO](https://gemseo.readthedocs.io/en/stable/): open-source.
  Optimisation multi-domaine.
- VIMSEO: (partiellement open-source) permet la modélisation de
  comportement matériau.

Utilisation des lois dans `Abaqus`, occasionnellement dans `FEnICS`.

Solution commerciale de capitalisation (TEEXMA, Bassetti).

Intérêt pour la question des incertitudes.

## Pascal Bouda (CEA Saclay): Comportement dynamique des matériaux métalliques

- Interprétation d'essais par corrélation d'images
- Champs denses
- Problématique du stockage
- Echanges des données
- Identification par FEMU

Lien avec d'autres groupes de travail

- Photomechanics
- Plateforme ESCALE, co-développée par Onera, Centrale Nantes, Centrale Lille, etc... ?
  - Centrée sur le dialogue

## Jérémy Bleyer (Laboratoire Navier)

- Gros sujet au labo Navier sur la capitalisation de lois multiphysiques
- JAXMat: librarie open-source basée sur JAX
  - CPU/GPU
- Identification sur champs complet couplant JAXMat
- Benchmarks standardisés pour les différentes solutions
  d'implémentation des lois basés sur des réseaux de neurones

Code cible principal: `FEniCS`
Projet ERC `Automatix`

Lien avec le GDR "IA Mat"

## Marius Duvillard (CEA Cadarache)

- Identification de lois de comportements basés sur des réseaux de
  neurones:
  - Intérêt pour l'apprentissage automatique à base de réseaux de
    neurones sur des matériaux de type matrice-inclusion.
  - Respect des contraintes physiques 
  - Intérêt pour la librairie de `JAXMat`. Travaux pour le passage
    `JAXMat` -> `MFront`

## Jacques Besson (Centre des Matériaux)

Problématique de dépouillement automatisé des essais et répétables.

- Début du développement d'un logiciel nommée `DatMecha`
  - Capitalisation des données expérimentales (courbes intégrales,
    images, observations post-essais)
  - Dépouillement automatique: Rp02, J02, etc..
    - Nécessité de capitaliser les procédures de dépouillement jusque là
      éparpillés dans des fichiers EXCEL passés de la main à la main.
  - Utilisation dans le cadre du project ANR Messia
  - Pas d'interfaçage avec des logiciels d'identification
  - Pas encore open-source
  - Utilisation au centre de matériaux et à Natran
  - Une IHM existe

Jacques pose la problématique de l'identification des lois de
comportement sur structure (éprouvettes CT): calculs coûteux, couplage à
un code aux éléments finis.

## Basile Marchand (SIMVIA)

Travaux avec MatAndSim puis identification avec mesure de champs:

- Lien avec code_aster
- Base de données matériau dans code_aster (génie civil)
- Essais automatisés : traction monotone, fatigue

Basile fait état de remonter client sur la question de la constitution
de base de données matériaux.

Question du partage des connaissances matériaux dans X codes, notamment
pour les codes et norme.

## François Curtit (EDF Renardières)

François travaille sur le sujet de la standardisation des essais et sur
la traçabilité des données depuis plus de 15 ans. EDF s'est penché sur
le sujet et a développé l'outil CADEEX pour gérer les essais et
capitaliser les données.

- Développeur de la base de données `CADEEX`, interne à EDF (non
  open-source actuellement)
  - Standardisation des résultats
  - Automatisation des dépouillements

- Format d'échange `madnex` (partiellement open-source)
  - Stockage des données expérimentales
  - Stockage des lois de comportements et tests de non-régression

## Pierre-Emmanuel Léger, Pierre Olivier SANTACREU (Aperam)

Industriel fabricant des produit plats en acier inoxydable depuis plus
de 20 ans qui possède de nombreuses données expérimentales selon
plusieurs standards en fonction des besoins des clients.

- Base de capitalisation
  - Essais
  - Propriétés physiques
- Identification des lois de comportement (Voce, etc..)
- Problématiques:
  - Fournir des données travaillées et/ou identification de lois de comportement
  - Profils de clients variés
    - Fourniture des coefficients uniquement pour des lois standard (pas
      implémentation).
  - Travail sur l'automatisation des identifications
  - Format d'échanges

Utilisation de Z-Mat, Z-Set et Abaqus pour l'identification

Cible: Open-Radioss, LS-Dyna, ...

## Aldo Marano (Onera): comportement des matériaux métalliques (endomamgement/fatique)

Standardisation et partage des mesures de champs.

Essais très riches et traitement difficiles

Identification à l'échelle des mesures de champs

Communauté cible: industriels et académiques

Outil logiciel open-source: PyMicro (Centre des matériaux)
  - https://pymicro.readthedocs.io/en/latest/
  - permet de fusionner différents types de données. interfaces entre
    mesures de champs et calculs de la micro-structure.
  - Publication des jeux de données PyMicro dans une démarche de science
    ouverte.

Intérêt pour la question d'un format standardisé.

## Arnaud Lejeune (FEMTO-ST)

- Identification de lois de comportement par nano-identation.
  Problématique type plasticité cristalline
- MFront/couplé Ansys 
- Identification par FEMU (suite de la thèse d'Alexandre Bourceret)

Code MIC2M (accessible en ligne) développé par Fabrice Richard sur la
question de l'indentificabilité.

ANR en cours avec partage de données obtenus par nano-identation

## Florian Devlaminck, Vincent Fardeau

- Travaux autour de l'utilisation de CADEEX au CEA
- Intérêt autour de l'utilisation directe du format `MADNEX`

## Fabrice Détrez (Gustave Eiffel): matériaux polymère

Spécialisé sur la modélisation multi-échelles de la sonde atomique au
calcul de structures.

- Outils utilisés
  - LAMPS (dynamique moléculaire)
  - Outils FEM variés (maison, `FEniCS`)
- Projet sur l'optimisation de matériaux bio-sourcés
  - Création de base données augmentés par de la simulation
    multi-échelle (démarche science-ouverte). Données chères à obtenir.
  - Elasticité, fluage, vieillissement

## Frédéric Péralès (ASNR)

- En charge de la capitalisation des données mécaniques au sein de l'ASNR
  - Création d'une plateforme
    - Lois de comportement multiphysiques
    - Multi-échelles

- Développeur du code X-Per
- Utilisation de `MFront` pour l'échanges des données
- Benchmarking avec `code_aster`
- Utilisation de très nombreux outils `Abaqus`, `FEniCS`, `X-Per`,
  `code_aster`, `Cast3M`, `LS-Dyna`

- Combustible et béton

## Yves Chemisky (Université de Grenoble)

- Ingénierie médicale
  - Comportement des tissus biologiques
  - Planification chirugicale
    - Patient spécifique
  - Lois de comportement

Question forte de la responsabilité.
Validation des modèles comme des dispositifs médicaux.
Pas de normalisation.

- Développeur principal d'une solution open-source `Simcoon`
  - Aide au développement de nouvelle lois de comportement
  - Utilisation de lois IA (réseau récurrent)
    - Question de la fiabilité de ce type de lois

Ponts vers `Abaqus` et potentiellement vers `Ansys`

# Conclusions/perspectives

- Rédaction du compte-rendu
- Proposition de groupes de travail par thématiques (voir annexe pour description détaillée)
  - Bases de données de capitalisation des résultats expérimentaux,
    dépouillement automatisé, format de capitalisation
  - Logiciels d’identification de lois de comportement
  - Bibliothèque d’implémentation des lois de comportement
  - Lois de comportement basées sur une approche IA
  - Transférabilité aux études d’ingénierie, codes et normes
- Organisation de futures réunions
- Organisation du mois des GTs
- Participation à la conférence MATERIAUX 2026 (Grenoble)

# Annexes

## Personnes s'étant déclarées intéressées

- [Bénédicte Reine](mailto:benedicte.reine@irt-saintexupery.com)
- [Pierre Olivier Santacreu](mailto:pierre-olivier.santacreu@aperam.com)
- [Pierre Emmanuel Léger](mailto:pierreemmanuel.leger@aperam.com)
- [LONGUET Arnaud (SAFRAN AIRCRAFT ](mailto:arnaud.longuet@safrangroup.com)
- [NAJEM Adam](mailto:adam.najem@ensam.eu)
- [Henry Proudhon](mailto:henry.proudhon@minesparis.psl.eu)
- [Aldo Marano](mailto:aldo.marano@onera.fr)
- [Xavier Boyat](mailto:xavier.boyat@aperam.com)
- [Sylvia Feld-Payet](mailto:sylvia.feld-payet@onera.fr)
- [Jean-Charles Passieux](mailto:passieux@insa-toulouse.fr)
- [Pascal Bouda](mailto:pascal.bouda@cea.fr)
- [Lionel Marcin](mailto:lionel.marcin2@safrangroup.com)
- [Fabrice Detrez](mailto:fabrice.detrez@univ-eiffel.fr)
- [Sylvain Leclercq](mailto:sylvain.leclercq@edf.fr)
- [Frederic Dubois](mailto:frederic.dubois@umontpellier.fr)
- [Jeremy Bleyer](mailto:jeremy.bleyer@enpc.fr)
- [Clément Jailin](mailto:clement.jailin@ens-paris-saclay.fr)
- [Jean-Baptiste Le Bail](mailto:jb.lebail@matandsim.fr)
- [Rian Seghir](mailto:rian.seghir@ec-nantes.fr)
- [Frederic Péralès](mailto:frederic.perales@asnr.fr)
- [Marius Duvillard](mailto:Marius.DUVILLARD@cea.fr)
- [Florian Devlaminck](mailto:Florian.DEVLAMINCK@cea.fr)
- [Vincent Fardeau](mailto:vincent.fardeau@cea.fr)
- [Maxime Mollens](mailto:maxime.mollens@edf.fr)
- [Francois Curtit](mailto:francois.curtit@edf.fr)
- [Jean Francois Rit](mailto:j-f.rit@edf.fr)
- [Yves Chemisky](mailto:Yves.Chemisky@univ-grenoble-alpes.fr)
- [Jacques Besson](mailto:jacques.besson@minesparis.psl.eu)
- [Myriam Berny](mailto:myriam.berny@safrangroup.com)
- [Akram El Abdi](mailto:akram.el-abdi@edf.fr)
- [Fabrice Richard](mailto:fabrice.richard@univ-fcomte.fr)
- [Yves Gaillard](mailto:yves.gaillard@univ-fcomte.fr)
- [Arnaud Lejeune](mailto:arnaud.lejeune@univ-fcomte.fr)
- [Basile Marchand](mailto:basile.marchand@simvia.tech)
- [Charles Toulemonde](mailto:charles.toulemonde@edf.fr)
- [Thomas Helfer](mailto:thomas.helfer@cea.fr)

## Contributions potentielles aux travaux du GT

### Bases de données de capitalisation des résultats expérimentaux, dépouillement automatisé, format de capitalisation

#### Porteurs potentiels 

François Curtit, Bénédicte Reine, Aldo Marano

#### Présentation potentielles

- Présentation de Cadeex (F. Curtit)
- Présentation de DatMecha (Jacques Besson)
- Présentation de Aperam
- Présentation de Escale + REX GRD Photomechanics (Pascal Bouda)
- Présentation de PyMicro (Aldo Marano)

#### Thématiques d'intérêt

- Format de stockage et bibliothèque de manipulation
- Stockage des données de grandes tailles:
  - Mesures de champs par corrélation d'image
  - Tomographie (non abordé lors de la réunion)

### Logiciels d'identification de lois de comportement

#### Porteurs potentiels

Akram El Abdi, Charles Toulemonde, Reine Bénédicte

#### Présentation potentielles

- Présentation d'Akram 
- Présentation de Fabrice Richard

#### Thématiques d'intérêt

- Incertitudes
- Identificabilité
- Technique d'identification basés sur des champs denses (FEMU)

### Bibliothèque d'implémentation des lois de comportement

#### Porteurs potentiels

Jérémy Bleyer, Yves Chemisky, Thomas Helfer, Jacques Bessson

#### Présentations potentielles

- Présentation de `JAXMat` (Jérémy Bleyer)
- Présentation de `Simcoon` (Yves Chemisky)

#### Thématique d'intérêt

- Interface unifiée pour les codes (`MGIS` ?)

#### Perspectives

Solliciter Laurent Stainier autour de `MatLIB` ?

### Lois de comportement basées sur une approche IA

#### Porteurs potentiels

Jérémy Bleyer, Yves Chemisky, Marius Duvillard

#### Thématiques d'intérêt:

- Pérennité des framework (`PyTorch`, `TensorFlow`, `JAX`, ...)
- Fiabilité et interprétabilité des lois
- Justification dans des dossiers de sûreté

#### Perspectives Lien avec le GT "Apprentissage profond en mécanique des matériaux"

### Transférabilité aux études d'ingénierie, codes et normes

#### Porteurs potentiels

Frédéric Péralès, Basile Marchand, Thomas Helfer, Charles Toulemonde

#### Thématiques

- Format d'échanges standardisés
- Tests de non-régressions et tests d'intégration
- Base de données
- Diffusion des outils

#### Présentations potentiels

- Présentation du guide 28 par l'ASNR
- Présentation des outils développés par le CEA/EDF et Framatome autour
  de la validation à effets séparées.

<!--
# Discussion



## Généralités sur les démarches AQ des participants

## Thématiques d'intérêt

- Lois IA
- Automatisation des développements
- Capitation des données sur mesures de champs
- Format d'échanges

## Solutions logicielles évoquées

### Logiciel de capitalisation

- DatMecha
- Cadeex

### Format de stockage des données expérimentales

- `madnex`

### Logiciels d'identification

- `LDC-0D`

### Implémentation de lois de comportement

- `JaxMat`
- `A-MAT`
- `Simcoon`
- `MFront`

### Logiciels de simulations cible

- `Cast3M`
- `code_aster`
- `Europlexus`
- `Manta`
- `MFEM/MGIS`
- `FEniCS`
- `A-Set`
- `Abaqus`
- `Ansys`
- `X-Per`
-->