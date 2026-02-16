<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  HEI-Vs Engineering School <h2>AAut Advanced Automation</h2>
  <br>
</h1>

[Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

# AAut Module 04 Overview /  IEC-61131-3 les outils OOP

## Sommaire

- [AAut Module 04 Overview /  IEC-61131-3 les outils OOP](#aaut-module-04-overview---iec-61131-3-les-outils-oop)
  - [Sommaire](#sommaire)
- [Preamble](#preamble)
- [First  part](#first--part)
  - [Aperçu](#aperçu)
  - [Ce qu'il faut retenir](#ce-quil-faut-retenir)
  - [Ce qu'il faut savoir](#ce-quil-faut-savoir)
  - [Mots clés](#mots-clés)
- [Introduction](#introduction)
  - [Notions de programmation orientée objet, ou rappel...](#notions-de-programmation-orientée-objet-ou-rappel)
    - [Principes de base](#principes-de-base)
    - [Avantages de la programmation orientée objet](#avantages-de-la-programmation-orientée-objet)
    - [Les différents éléments](#les-différents-éléments)
    - [Condition de la programmation orientée objet](#condition-de-la-programmation-orientée-objet)
  - [La base, le Function Block](#la-base-le-function-block)
    - [La structure, STRUCT](#la-structure-struct)
- [Ce qui nous intéresse](#ce-qui-nous-intéresse)
- [Module Type Package](#module-type-package)
  - [Le concept](#le-concept)
- [Héritage en IEC 61131-3](#héritage-en-iec-61131-3)
- [Interface et Méthodes.](#interface-et-méthodes)
  - [Méthodes cycliques](#méthodes-cycliques)
  - [Méthodes asynchrones](#méthodes-asynchrones)
- [Notion de Abstract](#notion-de-abstract)
- [Exemples d'apprentissage](#exemples-dapprentissage)

# Preamble
There are two parts in this section the first part explain some basic concepts of OO IEC 61131-3 to understand the PackML OO implementation.

[The second part, the reference](README%20Reference.md) is based on the documentation of Beckhoff, but we do not have enough time to deep in details in all concepts of IEC 61131-3 OO.
[Une ancienne version de  référence en français](Programmation_IEC_61131_3_FR.md) est maintenue, car c'est un des très rares documents IEC 61131-3 OO en français.

# First  part


## Aperçu
- Présentation des principaux éléments de OOP pour IEC 61131-3

- Avantages et inconvénient de OOP

- Quelques notions d'UML/SysML

> *IEC 61131-3 ne permet pas en principe d'allouer dynamiquement des objets. Nous préciserons l'utilisation des symboles UML adaptés à ce cours.*

- Use Case avec Enable et Execute dans le module suivant.

## Ce qu'il faut retenir
-   Disponible mais pas forcément nécessaire.
-   Surtout utiler pour des machines produites en série mais qui doivent être adaptées à différentes applications.
-   La notion OOP est surtout utile pour la création de librairies, **notion qui n'est pas abordée dans le cadre de ce cours**. On se référa au document [Creating PLCopen Compliant Libraries V1_0](https://plcopen.org/node/90?file=166)
-   Attention: peut augmenter la complexité du code, poser des problèmes de maintenance et de robustesse.
-   OOP n'est pas qu'un problème de syntaxe, c'est aussi une méthode de travail qui peut se faire sans les extensions OOP du 61131-3.

> A ma connaissance, au 18 février 2025, il n'existe pas d'autre implémentation de la norme IEC-61131-3 OOP que celle de [Codesys](https://www.codesys.com/) qui est un compilateur largement utilisé par de nombreux fournisseurs de solution PLC.
> > *Il semble que [BR-Automation, ABB Group](https://www.br-automation.com) ait présenté un produit en novembre 2024.*

## Ce qu'il faut savoir
-   Les différents éléments de OOP 61131-3.
-   Principal intéret, le polymorphisme.
-   Utiliser une interface et des méthodes.
-   Le monde Siemens TIA Portal travaille sans OOP.

## Mots clés
-   **inheritance** : Mécanisme permettant à une classe de dériver les propriétés et méthodes d'une autre classe.
-   **interface** : Définition d'un ensemble de méthodes et de propriétés sans implémentation, que les classes peuvent implémenter.
-   **method** : Fonction ou procédure définie dans une classe ou un bloc fonctionnel pour manipuler ses données.
-   **override** : Redéfinition d'une méthode héritée dans une classe dérivée pour en modifier le comportement.
-   **polymorphism** : Capacité à traiter des objets de différentes classes de manière uniforme via des interfaces ou des classes de base.
-   **properties** : Attributs d'une classe ou d'un bloc fonctionnel qui peuvent être lus ou écrits via des méthodes d'accès.
-   **abstract** : Déclaration d'une classe ou d'une méthode qui ne peut pas être instanciée directement et doit être implémentée par une classe dérivée.
-   **encapsulation** : Regroupement des données et des méthodes au sein des classes, avec contrôle d'accès pour protéger les données.
-   **IDE** : Environnement de développement intégré, outil logiciel qui fournit des fonctionnalités complètes pour le développement de logiciels.
- **UML**, **U**nified **M**odeling **L**anguage : Un langage de modélisation standardisé utilisé pour spécifier, visualiser, construire et documenter les artefacts d'un système logiciel. UML offre une façon de représenter graphiquement les concepts de programmation orientée objet, tels que les classes, les objets, les interfaces, les relations, les états et les activités. Il est largement utilisé pour la conception et l'analyse des systèmes logiciels complexes.

- **SysML**, **S**ystems **M**odeling **L**anguage : Un langage de modélisation généraliste utilisé pour spécifier, analyser, concevoir et vérifier des systèmes complexes. SysML est une extension de UML (Unified Modeling Language) et est utilisé pour modéliser des systèmes qui peuvent inclure des éléments matériels, logiciels, de données, de personnel, de procédures et de facilités. Il est particulièrement utile pour les systèmes d'ingénierie qui nécessitent une approche interdisciplinaire.


# Introduction
Nous allons commencer par expliquer dans quelle mesure le language IEC-61131-3 Structured Text est déjà orienté objet, mais sans les extensions spécifiques OOP, Object Oriented Programming.


## Notions de programmation orientée objet, ou rappel...

### Principes de base

Dans la programmation **orientée objet**, le logiciel est divisé en **objets**. Toutes les descriptions relatives à un objet sont regroupées dans un élément, un bloc fonctionnel, par exemple. Les descriptions comprennent les données et les procédures associées à l'objet. De plus, une interface d'accès à l'objet peut être définie via des méthodes et des propriétés.

Cette approche de programmation permet ainsi de développer des objets qui peuvent être réutilisés de manière autonome et indépendamment des conditions spécifiques. Les éléments peuvent être utilisés sans modification dans une ou plusieurs applications.

### Avantages de la programmation orientée objet

La méthode de programmation orientée objet offre de nombreux avantages.

En divisant le logiciel en objets, il est possible de développer une application **claire** et **bien structurée**. Ainsi, l'application et les éléments individuels sont facilement **compréhensibles** et faciles à **étendre**. La **réutilisabilité** des objets de programmation permet de gagner **du temps** et de réduire **les coûts** de développement et de maintenance des applications.

### Les différents éléments
Un langage orienté objet, **OOP**, **Object-oriented programming** se caractérise par les éléments suivants :

- **Classes et Objets** : Les classes définissent des types de données abstraits, et les objets sont des instances de ces classes.
- **Encapsulation** : Les données et les méthodes sont regroupées au sein des classes, et l'accès aux données est contrôlé via des méthodes.
- **Héritage** : Les classes peuvent hériter des propriétés et des méthodes d'autres classes, permettant la réutilisation du code.
- **Polymorphisme** : Les objets peuvent être traités comme des instances de leur classe de base, permettant des méthodes et des propriétés communes.
- **Abstraction** : Les détails complexes sont cachés, ne montrant que les fonctionnalités essentielles.

### Condition de la programmation orientée objet
Comme il est illusoir de prétendre développer un bon projet d'automation sans des spécications correctes, il est illusoir de vouloir développer un bon logiciel sans spécifications correctes, dont diagramme **UML**. Par chance nous disposons maintenant d'un outil puissant et intégré, le **duo Mermaid Class Diagram et Copilot**...

> Ces concepts permettent de structurer le code de manière modulaire et réutilisable, facilitant ainsi la maintenance et l'évolution des logiciels.

## La base, le Function Block
La base de la programmation orientée objet du IEC 61131-3 est un object connu, puisqu'il s'agit du **Function Block**. Il fournit les éléments principaux que sont les **Classes et Objets** ainsi que la notion d'**Encapsulation**.

> Pour être précis:
> > Un Function Block est une classe tant qu'il n'est pas instancié. On utilise par défaut le préfixe **FB_**.
> > Un Function Block devient un objet quand il est déclaré. On utilise par défaut le préfixe **fb**.

```iecst
PROGRAM PRG_Test
VAR
	fbU300_D50	  : FB_U300_D50;
	fbO300_DL	    : FB_O300_DL;
	fbMMS_22_IOL  : FB_MMS_22_IOL;
END_VAR
```
Un bloc fonctionnel est un **POU**, **Program Organization Unit**, qui renvoie une ou plusieurs valeurs lors de son exécution. Les valeurs des variables de sortie et des variables internes sont conservées jusqu'à la prochaine exécution. **Cela signifie que le bloc fonctionnel peut ne pas renvoyer les mêmes valeurs de sortie s'il est appelé plusieurs fois avec les mêmes variables d'entrée**.

### La structure, STRUCT
La structure au même titre que le bloque fonctionnel **est une classe**.

> Pour être précis:
> > Une structure est une classe tant qu'elle n'est pas instanciée. On utilise par défaut le préfixe **ST_**.
> > Une structure devient un objet quand elle est déclarée. On utilise par défaut le préfixe **st**.

```ìecst
TYPE ST_ActiveSensor
   STRUCT
      S_PushButon    : BOOL;
      B_SensorActive : BOOL;
      H_LedStation   : BOOL;
   END_STRUCT;
END_TYPE
```

```iecst
PROGRAM PRG_Test
VAR
  stActiveSensor    : ST_ActiveSensor
END_VAR
```
---

# Ce qui nous intéresse

Il faut revenir à l'introduction, ce qui nous intéresse, c'est l'automation modulaire. Que ce soit pour MTP, ou PackML, la machine d'état est similaire.

<div align="center">
  <figure>
    <img src="./img/MTP_StateMachine.png" 
         alt="Image lost: MTP State Machine.png"
         width="400">
    <figcaption>MTP State Machine</figcaption>
  </figure>
</div>

<div align="center">
  <figure>
    <img src="./img/StateModelV2022.png" 
         alt="Image lost: PackML State Machine.png"
         width="400">
    <figcaption>PackML State Machine</figcaption>
  </figure>
</div>

Ce que cela nous dit finalement, c'est que chaque équipement, nous utiliserons un Equipement Module afin de l'avoir à disposition dans les deux mondes, donc chaque EM devra pouvoir réagir d'une certaine manière dans un état donné.

Dans le monde orienté objet, cela nous dit que chaque objet Equipement Module doit fournir une série de services, nous utiliserons des méthodes en fonction d'un état donné de la machine.

---

# Module Type Package
## Le concept

---

# Héritage en IEC 61131-3
Principe de base

# Interface et Méthodes.

## Méthodes cycliques

## Méthodes asynchrones

---

# Notion de Abstract

---

# Exemples d'apprentissage

---


<!-- Fin du fichier README.md -->