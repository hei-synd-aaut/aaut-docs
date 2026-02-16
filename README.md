<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  Advanced Automation
  <br>
</h1>

Course : **AAut**


Author: [Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

---

# General Overview
This course is a continuation of the [Industrial Automation Base](https://github.com/hei-synd-autb/autb-docs) course. It delves deeper into the principles of managing an automation project and complements them with concepts of object-oriented programming according to [IEC 61131-3:2025](https://webstore.iec.ch/en/publication/68533).

The practical work is based on a [PackML](https://www.isa.org/products/isa-tr88-00-02-2022-machine-and-unit-states-an-imp) OO software structure developed in the automation laboratory of [HEVS](https://www.hevs.ch).


## What is advanced automation? 

If we contrast it with basic or classical automation, it would be:

## Modular automation

Modular automation is an advanced manufacturing approach that breaks production lines into independent, standardized, and interchangeable units or equipment modules that can be quickly reconfigured, added, or removed to adapt to changing production needs. Unlike rigid, monolithic systems, this flexible approach uses, plug-and-produce, technology—often via Module Type Package, MTP.—to reduce downtime and speed up product changes.
> 
Module Type Package mainly focus on the process industry and is sometimes compared to PackML for the discrete process. See: [Cross-industry state of the art analysis of modular automation](https://openhsu.ub.hsu-hh.de/entities/publication/14839). Some main concepts or Module Type Package are very similar to those of PackML, in both standards we can find the concepts of standard state machine and standard equipment.
Concepts of Module Type Package can be found in production, but also in laboratories of the biotechnologies. [Establishment of a fully automated microtiter plate-based system for suspension cell culture and its application for enhanced process optimization](https://pubmed.ncbi.nlm.nih.gov/27399304/).

### Key Aspects of Modular Automation:
#### Flexibility & Scalability
Production lines can be easily adapted to produce different products, ideal for high-mix/low-volume manufacturing.

#### Standardized Interoperability
Modules are designed with standardized interfaces, like MTP, allowing them to communicate and function together regardless of the manufacturer.

#### Reduced Downtime & Faster Time-to-Market
Because modules are pre-engineered and tested, reconfiguring a line takes hours or days instead of weeks.

#### Key Components
Often includes autonomous mobile robots, AMRs, compact DC-powered components, and modular conveyor systems.

### Main Benefits:
####	Lower Total Cost of Ownership
Reusable modules reduce the need for entirely new equipment for every product change.
####	Improved Efficiency
Allows for parallel engineering and optimized workflow.

####	Industry 4.0 Compatibility
Supports smart manufacturing by enabling modular, data-driven production. 
Modular automation is widely used in industries requiring high flexibility, such as pharmaceuticals, food and beverage, electronics, and automotive industries.

In other words, advanced automation should not be seen so much as a new technology for developing new products, but rather as the efficient use of existing technologies to accelerate the time to market for new products while reducing automation costs. At the risk of digressing, a unfortunately common mistake is to try to reduce costs by cutting corners on hardware. However, human costs often predominate, and any savings on hardware prices frequently result in a larger increase in development costs.

### A trilogy
We therefore present advanced automation as a trilogy that includes
- **Modular automation,** which we base on PackML and present through the PackML principle.

- Effective project management using several **GMP principles** based on the V-model. [Qualification is documented evidence that a specific piece of equipment, facility, or system is fit/ready for its intended use. It is further divided into DQ, IQ, OQ, and PQ](https://pharmastate.academy/qualification-v-model-approach-qualification-matrix-qualification-activity/).

- **Object-oriented programming** for managing modularity at the software level.

> Note: We primarily favor PackML for reasons of expertise and hardware. Our laboratories use Cartesian robots, which are better suited to implementing discrete processes, including GMP principles and V-models.

---

# Liste des modules

## AAut [MOD 01 Object Oriented Programming](./AAut_MOD_01_IEC_61131_OOP_Introduction/README.md)
An introduction to IEC 61131-3 is necessary for understanding the course. A detailed approach would require more time.


## AAut [MOD 02 Specification](/AAut_MOD_02_Specification/README.md)
Une introduction sur la spécification des processus pour l'automatisation, couvrant des concepts tels que les **V-Diagram**, **GMP**, GAMP® 5, et le cycle de vie des systèmes automatisés. Il explique l'importance des spécifications, les différentes composantes d'un système, et les principes de gestion de la qualité. Le document inclut également des exemples pratiques, des exercices, et des annexes pour aider à la rédaction des spécifications **URS**, **FS**, et **DS**. Enfin, il aborde les tests de validation, les **coûts des changements**, et fournit des ressources supplémentaires pour approfondir les connaissances.


## AAut [MOD 03 S88 Physical Model](/AAut_MOD_03_S88_Model/README.md)
Ce module traite de la norme **ISA-88** pour la modélisation et la gestion des processus industriels, en particulier pour les systèmes de production par lots. Il explique les concepts clés tels que le **modèle physique**, le modèle procédural et les recettes, et fournit des exemples concrets de leur application. Le document aborde également les différences entre les **processus continus, discrets et par lots**, ainsi que l'importance de la normalisation pour l'interopérabilité des systèmes. Enfin, il mentionne la norme ISA-95 pour la gestion des ressources d'entreprise et propose des exercices pratiques pour appliquer les concepts appris.

## AAut [Module 04, IEC 61131-3 OOP Tools](./AAut_MOD_04_IEC_61131_OOP_TOOLS/README.md)
Ce module propose une synthèse de tous les outils, extensions de langages, disponibles via IEC-61131-3 pour les fonctions spécifigues OOP, Object-Oriented Programming. **Une partie seulement sera traitée en détail dans ce cours**.

## AAut [Module 05, IEC 61131-3 OOP practice](./AAut_MOD_05_IEC_61131_OOP_InPractice/README.MD)
Présentation du labo du 12 mars.


## AAut [Module 06, PackML](./AAut_MOD_06_TR88_Pack/README.md)
Une introduction à PackML.

## AAut [Module 07, PackML](./AAut_MOD_07_Pack_Components/README.md)
Ce document détaille l'implémentation de la norme PackML 2022 pour la gestion des états et des modes d'une machine industrielle, en utilisant des blocs fonctionnels IEC-61131-3.
Il présente les concepts clés tels que les transitions d'états, les commandes, les alarmes, et les modes, tout en fournissant des exemples de code et des outils comme Node-RED pour la visualisation.
L'objectif est de simplifier le développement de machines complexes tout en assurant leur configurabilité et leur conformité aux normes industrielles.

## AAut OT S88 IEC
Voir ceci: https://www.isa.org/intech-home/2018/november-december/features/cybersecure-isa-88-recipes-and-control-with-iec-61

Lien encore ici: [New Module S88 OT](New_OT_ISA88_IEC.md)

## AAut [Module 10, PackSafety](./AAut_MOD_10_Pack_Safety/)
Ce document explore les principes de sécurité des machines, en mettant l'accent sur les normes ISO 12100 et ISO 13489 pour l'évaluation et la réduction des risques. Il aborde également des concepts tels que la sécurité intrinsèque, les zones ATEX, et l'utilisation de technologies comme Ethernet-APL pour les environnements dangereux. Enfin, des exemples pratiques et des questions permettent d'appliquer ces notions à des cas concrets.

## AAut [Annex 01, System engineering](./AAut_Annex_01_System_Engineering/README.md).
Some tools to work with UML diagrams in Visual Studio Code, including OO Class diagrams.