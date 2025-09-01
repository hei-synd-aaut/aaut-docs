<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  Advanced Industrial Automation
  <br>
</h1>

Course shortname: **AAut**


Author: [Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

---

# Aperçu général
Ce cours est la suite du cours [Industrial Automation Base](https://github.com/hei-synd-autb/autb-docs). Il approfondi les principes de gestion d'un projet d'automation et les complète avec des notions de programmation orientée objet selon [IEC 61131-3:2025](https://webstore.iec.ch/en/publication/68533).

Les travaux pratiques sont basés sur une structure logicielle [PackML](https://www.isa.org/products/isa-tr88-00-02-2022-machine-and-unit-states-an-imp) OO développée dans le laboratoire d'automation de la [HEVS](https://www.hevs.ch) et [disponible en Open Source](./HEVS_CtrlX_Pack/README.md).

Les lignes directrices de ce cours sont la **robustesse** et l'**optimisation du processus de développement**.


# Liste des modules

## AAut [MOD 01 System Engineering](./AAut_MOD_01_System_Engineering/README.md)
Fournit une liste d'outils pour l'aide à la conception d'un programme d'automation.


## AAut [MOD 02 Specification](/AAut_MOD_02_Specification/README.md)
Une introduction sur la spécification des processus pour l'automatisation, couvrant des concepts tels que les **V-Diagram**, **GMP**, GAMP® 5, et le cycle de vie des systèmes automatisés. Il explique l'importance des spécifications, les différentes composantes d'un système, et les principes de gestion de la qualité. Le document inclut également des exemples pratiques, des exercices, et des annexes pour aider à la rédaction des spécifications **URS**, **FS**, et **DS**. Enfin, il aborde les tests de validation, les **coûts des changements**, et fournit des ressources supplémentaires pour approfondir les connaissances.


## AAut [MOD 03 S88 Process Model](/AAut_MOD_03_S88_Model/README.md)
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