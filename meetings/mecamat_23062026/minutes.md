---
title: "GT capitalisation et partage des connaissances matériaux: contributions au mois des GTs 2026"
author: Thomas Helfer, Charles Toulemonde
toc: true
numbersections: true
date: 23/06/2026
lang: fr-fr
link-citations: true
colorlinks: true
geometry:
  - margin=2cm
papersize: a4
figPrefixTemplate: "$$i$$"
tblPrefixTemplate: "$$i$$"
secPrefixTemplate: "$$i$$"
eqnPrefixTemplate: "($$i$$)"
---

Lieu: TEAMS

Participants:

- organisateurs: Thomas Helfer, Charles Toulemonde

# Introduction

Ordre du jour:

- Rappel des objectifs du GT
- Franck Dubois (ASNR): présentation du guide 28
- Sébastien Bocquet, Bénédicte Reine (IRT Saint-Exupéry): présentation
  de VIMSEO
- Pascal Bouda (CEA): plateforme ESCALE

## Rappel des objectifs du GT (Thomas Helfer + Charles Toulemonde)

### Attentes sur les questions d'assurance-qualité des études

Dans le domaine du combustible par exemple.

Le GT n'est pas pour objectif l'imposition d'une solution particulière.

Thomas illustre avec la pratique actuelle à EDF et au CEA avec la chaîne
CADEEX -> LDC-0D -> CADEEX -> MFM -> OCS

Idée d'une capitalisation transversale sur des industriels du temps
long:

- données accessibles et traçables
- démarches cohérentes avec la science ouverte aussi
- lien entre identification et validation à effets séparés
- stabilité des identifications
- formats d'échanges de données

### Thématiques d'intérêt

- liste des logiciels disponibles
- formats d'échanges disponibles
- stabilité dans le temps
- implémentation des LdC
- logiciels d'identification

## Présentations de la journée

- VIMSEO: Sébasien et Bénédicte
- Guide 28 de l'ASNR (Franck Dubois)
- Plateforme ESCALE (Pascal Bouda)

# Présentation de VIMSEO

Temps de la présentation:

- Contexte (IRT Saint-Exupéry)
- Logiciel VIMSEO
- Capitalisation et répétabilité

## Contexte

L'IRT est un institut de recherche mixte académiquee+industrielle. Le
budget annuel est de 40 M€ pour une centaine de personne. C'est un IRT
de filière sur l'aéronautique et la défense. Les partenaires sont AIRBUS
par exemple.

Stratégie: technologies + vertes, TI, fabrications avancées, méthodes
et outils

Les objectifs sont d'introduire des technologies nouvelles.

Activités:
- modèles physiques ou basés sur les données
- application ou développement de méthodes
- aide à la décision
- interopérabilité des modèles

L'objectif final est de transférer à l'industrie.

Pour les nouveaux avions, il sera difficile de faire des systèmes très
complexes basés sur des essais. Les processus de conception utilisent de
plus en plus de la simulation numérique avec des échanges entre modèles.

Au sein d'une équipe, il peut y avoir des manques (continuité,
consistance, standardisation, couverture des bases expérimentales)

## VIMSEO

Le logiciel fait dialoguer plusieurs concepts:

- décomposition des systèmes complexes en composants unitaires: exemple de la
  capacité à exploiter la calibration faite à une petite échelle.
- analyses prenant en compte les incertitudes
- implémentation de modèles et choix de chargements

Fonctionnalités:

- intégration de modèles
- analyses de sensibilités
- production de workflows et de dashboards
- services de lancement de calculs et de bases de données

Cas d'usage:

- identification de paramètres sur plusieurs essais avec pondération
- calibration bayésienne sur des propriétés mesurées
- recherche de la meilleure séquence d'empilement pour réduire l'incertitude
  sur des calibrations
- validation stochastique avec barres d'incertitudes

Illustration:

- pyramide d'implémentation
- calibration et mise à jour d'un modèle jusqu'à l'estimation d'une
  métrique d'erreur

Le workflow de validation peut être couplé à une base de données. MLflow
permet de visualiser.

## Perspectives

Capitalisation des modèles et des données
Collaborations internes
Automatisation des tâches et partage de connaissances
Transfert sur des outils installés chez des clients

GEMSEO est une bibliothèque d'optimisation utilisée par VIMSEO

L'outil est opensource, son domaine s'étend aux matériaux métalliques

## Questions/Réponses

- comment sont calculées les barres d'incertitudes ?
  -> on dispose de plus d'information encore (CDF)
- inférence bayésienne
- solveurs utilisés ?
  -> monosolveur majoritairement
  -> tests de code_aster, craft et fenics
- identification pa version de logiciel ?
  -> on évite de changer de version (Abaqus 2022)
- lois de comportement natives ?
  -> concept de matériaux
  -> possibilité de rentrer une loi
  -> tous les plugins ne sont pas libres
- estimation d'une structure optimale
  -> double boucle d'optimisation
  -> modèles particuliers pour les fibres végétales

# Guide 28 (Franck Dubois)

## Introduction

Franck commence par une présentation de l'ASNR qui est une autorité née de la
fusion entre l'ASN et l'IRSN. L'ASNR mène des missions de contrôle, d'expertise
et de recherche.

Guide 28: qualification des outils de calculs

## Contexte

Démonstration de sûreté des installations nucléaires: étude des accidents,
réalisaion de simulation à l'aide d'OCS
Réglementation: outils de calculs qualifiés
Décision de faire un guide décrivant les préconisations

Pyramide:

- loi > décrêts et arrêtés > décisions ASNR > guides ASNR

GT mi-2014 sur 2 à 3 ans regroupant ASN + IRSN + EDF + CEA

## Guide 28

domaine du guide: thermodydraulique, neutronique, thermomécanique et
physicochimie du combustible.
non couvert par le guide: assurance-qualité qui est de la responsabilité des
exploitants, mais qui peut faire l'objet d'inspections

définitions importantes:

- OCS
- champ d'utilisation visé
- vérification
- validation
- incertitude
- qualification: tampon final par l'exploitant disant que l'outil est apte à
  fournir des résultats utilisables pour la démonstration de sûreté
- méthode
- PIRT

messages:

- version: bien identifier la version utilisée, cela embarque aussi la dimension
  informatique comme les compilateurs
- pas de qualification absolue: la qualification est restreinte à un domaine,
  être qualifié mais pour faire quoi
- notion de méthode: la méthode ne doit pas remettre en question l'outil qualifié

Démarche préconisée:

- validation modèle par modèle
 - validation sur des configurations àà complexité croissante
 - validation intégrale sur les paramètres cibles des scénarios du domaine
   d'utilisation
- réalisation d'un PIRT: analyse physique des scénarios
- vérification: déterminer si les équations sont bien résoluées
- validation à effets séparés des modèles dominants
- validation intégrale de l'OCS et des scénarios: interaction entre les
  différents phénomènes physiques en gardant les mêmes recalages
- transposition au  champ d'utilisation visé
- qualification: l'exploitant la prononce s'il estime l'outil capable de
  calculer les grandeurs d'intérêt et que le domaine d'utilisation est bien dans
  le périmètre

## Conclusion

- précautions: pré, post, couplages
- autres moyens: benchmarks, études de sensibilité, jugement d'experts,
  démarche conservative
- changement de versions: analyse de non-régression, extension de la base de
  validation

## Questions/Réponses

- remarques sur le bon sens du guide et sur la motivation
  -> permet de structurer les démonstrations
  -> côté aéronautique, certaines approches arrivent
  -> cela intéresse l'ASNR qui souhaite faire une suite derrière et qui
     réfléchit sur les incertitudes et l'IA (de confiance et explicable).

# Plateforme ESCALE (Pascal Bouda)

## Introduction

Pascal Bouda travaille au CEA depuis 7 ans, il travaille sur un projet de
développement d'essais 2.0. La présentation se concentre sur des essais bien
particuliers.

Le projet regroupe 7 institutions publiques et 20 personnes dont des doctorants
et des post-docs. L'article fondateur a été publié pour le CSMA 2022. L'outil
a été rendu opensource.
https://gitlab.com/escale_team/escale

## Présentation

Les essais qui sont analysés par la plateforme sont des essais 2.0 intégrant
de la mesure de champs (souvent 2D).

Escale couvre la chaîne complète:
- aquisition: en entrée
- Escale:
  - mesure de champs sinématiques (ou thermiques)
  - projection sur maillage pour comparaison <-
  - maillage + modèle + code ------------------

La difficulté vient du dialogue entre les différentes briques logicielles.
Escale se propose de faciliter le dialogue.

Illustration sur la détection d'un front de fissure Le projet a été
construit itérativement, une base de tests de non-régression permet de
tout résoudre de bout en bout. Ces tests illustrent toutes les
fonctionnalités logicielles.

Escale possède des dépendances externes, parmi lesquels code_aster selon les
besoins. La plateforme possède une interface Python.

## Illustrations

La plateforme est née du besoin de créer un jumeau numérique des essais 2.0,
cela permet de mieux valider les processus.

Briques:

- simulateur d'images déformées (aléatoires ou sur grilles)
- acquisition et extraction des champs cinématiques
- solveur

L'outil dispose d'une interface graphique qui sert à aligner les images et les
maillages.

Plusieurs cas-tests sont montrés:

- calculs de contraintes
- détection de fissures
- comparaison avec les simulations: dialogue essais-calculs intensif
  - outils de lissage des données pour pouvoir comparer avec la simulation
  - complexité à appliquer les conditions aux limites
- identification de paramètres

## Perspectives

Méthodes inverses: extension à plusieurs codes
Partage dans un cadre HPC: performance
feuille de route: packaging, performance, interfaces
besoin de standardiser les données

## Conclusion

- logique d'agrégation
- besoin de standardisation des données
- autres initiatives sur la standardisation
  - choix d'un format ouvert indispensable
  - utilisation de MED et de MADNEX
  - faire attention à ne pas se bloquer avec les formats propriétaires
    des logiciels de mesure de champs
