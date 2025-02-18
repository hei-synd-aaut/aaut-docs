<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  HEI-Vs Engineering School <h2>AAut Advanced Automation</h2>
  <br>
</h1>

[Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

# AAut Module 03 /  S88 Model

## Aperçu
- Afin de maitriser la complexité d'une installation d'automation, il est nécessaire de pouvoir en créer un model. Ce model doit permettre à l'ingénieur de créer l'architecture de son insallation, que ce soit au niveau de sa structure ou de son comportement.
- Un sysème d'automation regroupe plusieurs spécialisations, un model permet de partager l'information entre les différentes parties prenantes.

## Entités de normalisation
Il existe deux principaux comités de normalisation qui proposent des models, à savoir l'ISA, International Society of Automation, basée aux Etats Unis, mais dont le fonctionnement est basé sur la participation d'entités indépendantes des pays, et l'IEC, International Electrotechnical Commission, dont les membres sont des entités nationales. Ces deux comités travaillent souvent ensembles et ceraines normes peuvent se retrouver avec des contenus similaire mais des numérotations différentes, comme  ISA-88 Batch Control qui devient IEC 61512 Batch Control.

## Artificial Intelligence Notice
Les documents ISA ou IEC ne sont pas libres de droits, c'est pourquoi il n'est pas possible de fournir des éléments complets de ces documents. Cet aspect peut poser des problèmes de propriété intellectuelle, notamment avec le développement de l'intelligence artificielle. D'où la note ci-dessous reprise telle quelle du site de l'ISA.

> ISA prohibits the entry of ISA standards and related ISA intellectual property (“ISA IP”) into any form of Artificial Intelligence (AI) tools, such as ChatGPT. Additionally, creating derivatives of ISA IP using AI is also prohibited without express written permission from ISA’s CEO. In the case of such use, ISA will suspend a licensee’s access to ISA IP, and further legal action will be considered. Please review ISA's Terms and Conditions for further information.

## Ce qu'il faut retenir:
Ce cours est basé sur ISA-88, nommé aussi S88. ISA-88 est conçu à la base pour l'industrie du processus, comme la chimie, mais les concepts peuvent être repris pour modéliser d'autres types de processus.

Un des thèmes clé de ISA-88 est une séparation entre l'aspect procedure, une recette, et sa composante physique. L'objectif est de construire des installations modulaires qui puissent être utilisées pour produire différentes variantes de produit.

> Un model ISA-88 n'implique pas obligatoirement un processus automatique. L'humain a aussi son rôle à jouer dans certaines étapes.

## Ce qu'il faut savoir
- Modéliser la structure physique d'un processus simple à l'aide de ISA-88, Unit, Equipment Model, Control Module.
- Connaître les différents types de processus.
- Décrire le comportement d'un processus avec des phrases simples et modéliser son comportement à l'aide d'un diagramme d'activité.

## Mots clés

- **ISA-88**: A standard for batch control that provides models and terminology for the design and operation of batch processes. / *Une norme pour le contrôle des lots qui fournit des modèles et une terminologie pour la conception et l'exploitation des processus par lots.*
- **Process Cell**: A collection of units, equipment and control modules that work together to perform a specific process / *Un ensemble d'unités, d'équipements et de modules de contrôle qui travaillent ensemble pour réaliser un processus spécifique.*
- **Unit**: A functional entity within a process cell that performs a specific set of tasks. / *Une entité fonctionnelle au sein d'une cellule de processus qui effectue un ensemble spécifique de tâches.*
- **EM Equipment Module**: A functional grouping of equipment that can perform a finite number of specific processing activities. / *Un regroupement fonctionnel d'équipements capable d'effectuer un nombre fini d'activités de traitement spécifiques.*
- **CM Control Module**: A module that provides direct control over a process through actuators and sensors. / *Un module qui fournit un contrôle direct sur un processus via des actionneurs et des capteurs.*
- **Procedure**: The highest level of procedural control that defines the strategy for performing a major processing action. / *Le niveau le plus élevé de contrôle procédural qui définit la stratégie pour réaliser une action de traitement majeure.*
- **Operation**: A set of ordered phases that define a major processing sequence within a unit. / *Un ensemble de phases ordonnées qui définissent une séquence de traitement majeure au sein d'une unité.*
- **Phase**: The smallest element of procedural control that accomplishes a specific process-oriented task. / *Le plus petit élément de contrôle procédural qui accomplit une tâche spécifique orientée processus.*
- **Batch**: A finite quantity of material produced by a batch process. / *Une quantité finie de matière produite par un processus par lots.*
- **Continuous Manufacturing**: A process where materials are continuously fed through the equipment and the output is a continuous flow. / *Un processus où les matériaux sont continuellement alimentés à travers l'équipement et la sortie est un flux continu.*
- **Discrete Batch**: A process where materials are processed in distinct batches, each with a finite quantity. / *Un processus où les matériaux sont traités en lots distincts, chacun avec une quantité finie.*
- **ERP**, **Entreprise Ressource Planning** / *Planification des Ressources de l'Entreprise PRE*.
- **MES**, **Manufacturing Execution System** / *Système d'Exécution de la Fabrication (SEF)*.
- **SCADA (Supervisory Control and Data Acquisition)**: A system used for remote monitoring and control of industrial processes. It collects data from sensors and instruments located at remote sites and transmits it to a central computer for processing and control. / *Un système utilisé pour la surveillance et le contrôle à distance des processus industriels. Il collecte des données à partir de capteurs et d'instruments situés sur des sites distants et les transmet à un ordinateur central pour traitement et contrôle.*

<div align="center">
  <figure>
    <img src="./img/Résumé des différents niveaux d&apos;automatisation.webp"
       alt="Image lost: Résumé des différents niveaux d&apos;automatisation.webp">
    <figcaption>Résumé des différents niveaux d&apos;automatisation, Source: 
    www.erp-information.com</figcaption>
  </figure>
</div>

Les différents logiciels qui composent la pyramide ci-dessus sont très souvent conçus par des entités différentes, une des raisons d'être de la normalisation est de simplifier la communication entre ces différents niveaux.

Il existe pour certains types d'industries, transports ferroviaires: [IEC 61375](https://webstore.iec.ch/en/publication/5397), [IEC 62278](https://webstore.iec.ch/en/publication/6747), [IEC 62425](https://webstore.iec.ch/en/publication/7001), [IEC 62888](https://webstore.iec.ch/en/publication/30007), pour l'automatisation des réseaux de distribution d'énergie électrique de type SmartGrid, on parlera [IEC 61850](https://iec61850.dvl.iec.ch/). **Dans la cadre de cours, nous aborderons principalement le niveau PLC, soit l'automatisation au niveau machine, couvert par [ISA-88](https://www.isa.org/standards-and-publications/isa-standards/isa-standards-committees/isa88)**.


# Introduction
En guise d'introduction, je propose celle du [document proposé en annexe](./documentation/Que%20faire%20d'ISA88%20et%20ISA95.pdf):
## Vénérables standards du siècle dernier 
1995, tout début 2000: les standards ISA88 et ISA95 sont anciens. Ont ils atteint leurs objectifs ?  Sont ils encore d’actualité, Quelle est leur position dans la mouvance Industrie 4.0, IIOT, IA ?  Réponses courtes: 
- Non, leurs objectifs n’ont pas été atteints; 
- 0ui, ils sont plus que jamais utiles à l’industrie 
- Ils doivent participer à la mise en œuvre des initiatives industrielles X.0, Futur, smart et des nouvelles » technologies de l’information pour développer l’agilité fonctionnelle et 
architecturale.


# 	S-88 & PackML, Classes de processus industriels
Il ne s’agit pas de rentrer en détail dans les différents types de processus industriels. Cela dépasse le cadre de ce cours. En revanche, ce cours s’inspire en grande partie du modèle physique décrit dans la norme ISA-88 et du PackML qui en dérive et sera décrit plus bas. PackML qui concerne plus les processus discrets fait l'objet d'un module séparé.

<figure>
  <img src="./img/Batch vs Continuous Manufacturing.jpg"
     alt="Image lost: Batch vs Continuous Manufacturing.jpg">
  <figcaption>Batch vs Continuous Manufacturing, Source: www.researchgate.net</figcaption>
</figure>

##	Processus, lots et traitements par lots
Selon ISA 88, un processus est une séquence d'activités chimiques, physiques ou biologiques pour la conversion, le transport ou stockage de matière ou d'énergie. Les procédés de fabrication industrielle peuvent généralement être classés sous forme de fabrication continue de pièces discrètes ou par lots. La classification d'un processus dépend de si la sortie du processus apparaît dans un flux continu, « Continuous », en quantités finies de pièces « Discrete parts manufacturing », ou en quantités finies de matière « Batches ».
Bien que certains aspects de cette norme puissent s'appliquer à la fabrication de pièces discrètes ou aux processus continus, la norme ISA88 ne traite pas spécifiquement de ces types de processus.
La réalité est que de nombreux ingénieurs, dont l’auteur de ce cours se sont intéressés à l’application de la norme aux processus discret et continus. On peut notamment se référer à l’ouvrage « WBF, Applying ISA-88 in discrete and continuous manufacturing ».

##	Continuous processes
Dans un processus continu, les matériaux sont passés en flux continu à travers l'équipement de traitement. Une fois établi dans un état de fonctionnement stable, la nature du processus ne dépend pas de la durée de fonctionnement. Les démarrages, transitions et arrêts ne contribuent généralement pas à la réalisation du traitement souhaité. Au niveau de l’ISA, les processus continus sont traités dans « ISA106, Procedure Automation for Continuous Process Operations »

##	 Discrete parts manufacturing processes
Dans un processus de fabrication de pièces discrètes, les produits sont classés en lots de production basés sur les matières premières communes, les exigences de production et les historiques de production. Dans un processus de fabrication de pièces discrètes, une quantité spécifiée de produit se déplace comme une unité (groupe de pièces) entre les postes de travail, et chaque pièce conserve son identité unique.

<figure>
  <img src="./img/Discrete Batch High-precision assembly systems for medical devices..webp"
     alt="Image lost: Discrete Batch High-precision assembly systems for medical devices..webp">
  <figcaption>Discrete Batch High-precision assembly systems for medical devices  Source: www.pharmaceutical-technology.com</figcaption>

##	Batch processes
Les traitements par lots abordés dans cette norme conduisent à la production de quantités finies de matières (lots) en soumettant des quantités de matières premières à un ordre défini d'actions de traitement à l'aide d'un ou plusieurs équipements. Le produit fabriqué par un processus par lots est appelé un lot. Les processus par lots sont des processus discontinus. Les processus par lots ne sont ni
discret ni continus ; cependant, ils présentent les deux caractéristiques.

> L'expérience montre qu'il est parfaitement possible d'utiliser le modèle ISA-88 pour les différents types de processus.

#	Machine
Dans la suite de ce cours, nous allons souvent retrouver le terme « machine ». Voici la définition d’une machine selon la directives européenne (DIRECTIVE 2006/42/CE) qui est généralement appliquée en Suisse.

*Une vérification faite en janvier 2025 montre que cette norme est toujours d'actualité*

##	Article 2
- a)	« Machine » :
  - ensemble équipé ou destiné à être équipé d'un système d'entraînement autre que la force humaine ou animale appliquée directement, composé de pièces ou d'organes liés entre eux dont au moins un est mobile et qui sont réunis de façon solidaire en vue d'une application définie,
  - ensemble visé au premier tiret, auquel manquent seulement des organes de liaison au site d'utilisation ou de connexion aux sources d'énergie et de mouvement,
  - ensemble visé au premier et au deuxième tirets prêt à être installé et qui ne peut fonctionner en l'état qu'après montage sur un moyen de transport ou installation dans un bâtiment ou une construction,
  - ensemble de machines visées au premier, au deuxième et au troisième tirets ou de quasi-machines visées au point g*) qui, afin de concourir à un même résultat, sont disposées et commandées de manière à être solidaires dans leur fonctionnement,
  - ensemble de pièces ou d'organes liés entre eux, dont un au moins est mobile, qui sont réunis en vue de soulever des charges et dont la seule force motrice est une force humaine directement appliquée ;
…
- g)	«quasi-machine» :
ensemble qui constitue presque une machine, mais qui ne peut assurer à lui seul une application définie. Un système d'entraînement est une quasi-machine. La quasi-machine est uniquement destinée à être incorporée ou assemblée à d'autres machines ou à d'autres quasi-machines ou équipements en vue de constituer une machine à laquelle la présente directive s’applique ;

#	ISA 88

##	Qu’est-ce que le S88 ?
S88 est un modèle et une méthodologie pour la conception et la gestion d'un contrôle de production flexible. La maintenabilité est améliorée grâce à une structure meilleure et universelle. À l'origine, la norme S88 est conçue pour l'industrie par lots/ « batch manufacturing », mais elle est également applicable dans les processus discrets et continus. S88 est une norme pour améliorer la manipulation des processus de production.

Si S88 est la notation la plus répandue, on retrouve cette normalisation au niveau [IEC 61512-1](https://webstore.iec.ch/en/publication/5528)

L’idée de S88 est de découpler le produit et sa recette, la procédure, de ses équipements le modèle physique et du processus.

Pour l’automaticien, l’avantage est de donner un vocabulaire et une méthodologie. Cette norme est relativement ancienne, elle date de 1995, révisée en 2010, *ANSI/ISA 88.00.01-2010*, mais elle continue à se développer et à être étudier. Il y a quelques débats sur l’utilité de la norme S88, mais pour en débattre, il est nécessaire d'en connaitre les principes.

Si je dois retenir un argument c’est celui-ci: *vous pouvez parfaitement développer votre propre méthodologie interne à votre entreprise. Cependant le jour où vous voudrez vendre un machine à une multinationale, il risque d’être compliqué d’expliquer pourquoi votre machine est incapable de communiquer correctement avec les autres machines de la chaînes par ce qu’elle utilise un découpage fonctionnel différent des autres. D’autre part, si votre machine fait partie d’une chaîne globale, si l’ensemble de la chaîne est arrêté dans l’état « Held », vous risquez de devoir perdre un temps considérable simplement pour adapter le mode « Pause » de votre machine en « Held »*.

Si le S88 gère principalement les systèmes de contrôle, il existe une autre norme qui ne sera que mentionnée ici sans être approfondie. C’est le S95, ou ISA-95 (IEC 62264) qui est l’équivalent du S88 au niveau ERP, Entreprise Ressource Planning.

Pour terminer, si la norme S88 n’est pas forcément la mieux adaptée à chaque machine, elle a le mérite d’exister et plusieurs articles montre qu’elle peut être adaptée avec succès, avec des gains en productivité avéré dans plusieurs domaines de l’automation. C’est une bonne base de travail. Finalement les ingénieurs qui la critiquent le plus sont surtout ceux qui ne la connaissent pas ou ne la comprennent pas.

##	Modèles
L’une des idées fondamentales de S88 est de découpler les modèles procéduraux (la recette), du modèles physiques et du processus.
L’idée étant qu’avec un seul modèles physique combiné à différentes procédures on pourra réaliser différents processus.
Si l’on prend l’exemple d’un robot. Le robot sera le modèle physique. Il est parfaitement imaginable que ce robot soit piloté en mode manuel par un opérateur. Dans ce cas extrême, le model procédural sera inexistant. Cet aspect-là est essentiel à garder à l’esprit au moment où il faudra passer à la réalisation.
Historiquement, les premier PLC se résumaient à des « bornier intelligents » pour le model physique, alors que des « ordinateurs » pilotaient le model procédural. Avec la « montée en puissance » des PLC cette barrière a tendance à s’estomper. C’est pour cette raison que le model S88, relativement ancien garde sa modernité. Ce n’est qu’avec une délimitation claire au niveau du logiciel du PLC que l’on conservera, voir améliorera la modularité d’une unité de production.

 <figure>
  <img src="./img/S88 Model overview.png"
     alt="Image lost: S88 Model overview.png">
  <figcaption>S88 Model overview</figcaption>
</figure>

##	The Physical Model
De fait, le model physique est la base du concept ISA-88.

###	Physical model en général
Les équipements sont modélisés à l'aide du modèle physique. Ce modèle a une hiérarchie de sept niveaux. Il donne un aperçu des équipements disponibles dans l'entreprise. Sur la base de cette vue d'ensemble, les gens peuvent définir les possibilités d'une installation.
Les trois niveaux les plus élevés, Entreprise, Site et Area sont importants pour l'administration, mais moins importants pour la conception d'une installation de production. Plus de détails sur ces niveaux peuvent être trouvés dans la norme S95.

 <figure>
  <img src="./img/S88 Physical Model.png"
     alt="Image lost: S88 Physical Model.png">
  <figcaption>S88 Physical Model</figcaption>
</figure>

Les quatre niveaux les plus bas, Process Cell, Unit, Equipement Module et Control Module sont importants pour l'installation de production. Chaque composant physique d'un contrôle automatisé doit correspondre à l'un de ces niveaux.

###	Process Cell
Une cellule de traitement contient toutes les unités et tous les équipements nécessaires pour fabriquer un lot ou un produit. Une cellule de traitement peut contenir plus d'équipement que nécessaire pour un lot individuel.

La réalité est plus complexe, mais cette définition suffit pour le cours d’automation. Pour plus de détails on se réfèrera à la norme ou à la littérature spécialisée.
Note
La différence entre le modèle physique d’une unité de production orientée « S88-Bach » et une ligne d’assemblage ou de « packaging » se situe au niveau de la désignation. Fondamentalement, le principe reste le même.

|S88 Line Hierarchy|Packaging Line Hierarchy|
|-----------|--------------|
|![](./img/S88%20Line%20Hierarchy.png)|![](./img/Packaging%20Line%20Hierarchy.png)|
   

###	Unit
Le terme « Unit » est plus ou moins abstrait en ce qui concerne le ou les équipements, « Equipment Module » qui lui sont associés. L'unité peut réaliser des activités qui apportent une valeur ajoutée au produit. En d'autres termes, une unité est un outil de fabrication associé (ou non) à l'instrumentation et aux équipements associés.

Lors de la conception d’une installation de production, vous devez « déterminer » les unités. Si l'équipement a besoin d'une recette pour s'exécuter, il s'agit d'une unité. Si l'équipement n'a pas besoin d'une recette pour s'exécuter, il appartient à une unité.

Avec cela, vous décidez de la flexibilité. Une unité effectue une activité de traitement majeure. Une unité est active sur une pièce ou sur l'ensemble du lot. Aucun lot ne peut être traité simultanément dans la même unité, une unité ne peut être active que sur un lot à la fois. Chaque unité fonctionne indépendamment des autres unités, en fonction de leurs procédures unitaires appropriées et des paramètres de formule.
Une unité contient un certain nombre de modules d'équipement, « Equipment Module » et de modules de commande, « Control Module ».

#### Small Container Filling Machine for Endless Liner
Exemple d'une unité de remplissage de container de l'entreprise [Burgener AG à Viège](https://www.burgener-ag.ch). Une manière simple de définir une unité, ou machine, consiste en la présence d'un PLC, Programmable Logic Computer et d'un HMI, Human Machine Interface.

 <figure>
  <img src="./img/Small Container Filling Machine for Endless Liner.png"
     alt="Image lost: Small Container Filling Machine for Endless Liner.png">
  <figcaption>Small Container Filling Machine for Endless Liner, Souce: www.burgener-ag.ch</figcaption>
</figure>

###	Equipment Module
La norme S88 définit un module d'équipement comme « un groupe fonctionnel d'équipement qui peut effectuer un nombre fini d'activités de traitement mineures spécifiques ». En d'autres termes, les modules d'équipement regroupent des dispositifs physiques pour exécuter une ou plusieurs fonctions spécifiques. Un module d'équipement peut être constitué de modules de commande ou d'autres modules d'équipement.
Un module d'équipement contient tous les équipements et fonctions de contrôle nécessaires à l'exécution de sa fonction process.

Plusieurs unités peuvent partager des modules d'équipement, par exemple plusieurs réservoirs peuvent partager la même canalisation et la même pompe. Si un module d’équipement ne peut fonctionner qu’avec une seule unité à la fois, on parle de « ressource à usage exclusif ». Si elle peut agir simultanément sur plus d’une unité, on parle de « ressource à usage partagé ».
Malgré ce qui précède, un module d'équipement appartient en général à une seul unité. Cela vaut également pour les modules de commande.

|Equipment Module|Control Module|
|-----------|--------------|
|![](./img/Equipment%20Module.jpg)|![](./img/Control%20Module.jpg)|

Pour le Control Module ci-dessus, j'utilise souvent la notion de gripper.

> Un **gripper**, ou préhenseur, est un dispositif utilisé dans les systèmes de manipulation robotisés pour saisir, tenir et relâcher des objets. Il est souvent équipé de doigts ou de pinces qui peuvent être actionnés pour s'adapter à différentes formes et tailles d'objets. Les grippers sont essentiels dans les applications d'automatisation industrielle pour effectuer des tâches telles que le déplacement, l'assemblage et l'emballage de pièces.

###	Control Module
Du point de vue du contrôle, un module de contrôle est traité comme une seule entité. Chaque module de commande fournit une connexion directe au processus via des actionneurs et des capteurs. Un module de contrôle appartient au modèle physique, mais toutes les pièces ne sont pas nécessaires physiques. Une pièce peut être un sous-programme API.
Dans leur forme la plus simple, les modules de contrôle peuvent simplement être des pilotes de périphériques, mais ils peuvent également fournir des méthodes robustes de contrôle de périphériques, y compris des fonctions telles que les modes automatique et manuel, le mode de simulation, les autorisations ou les verrouillages, les alarmes.

Contrairement à un module d'équipement, un module de contrôle ne peut pas exécuter de procédures de recette.

L’instrumentation peut être utilisée par plusieurs modules de contrôle, par exemple deux modules de contrôle « dose d’eau » et « dose de crème » peuvent utiliser le même débitmètre comme instrumentation commune. Un dispositif de contrôle (par ex. Vanne, moteur) doit être contrôlé par un (et un seul) module de contrôle.

<figure>
  <img src="./img/Unit Vertical Filler.png"
     alt="Image lost: Unit Vertical Filler.png">
  <figcaption>Unit Vertical Filler</figcaption>
</figure>


###	Equipment or control module ?
Parfois, il n'est pas facile de décider si un appareil est un module d'équipement ou un module de commande. Cela dépend de la fonctionnalité. Les modules de contrôle, Control Module ne peuvent pas exécuter les commandes à partir de recettes, contrairement aux modules d'équipement. Les modules d'équipement sont les plus petites entités sur lesquelles une recette peut agir.

Exemple: un « pick and place »

Pour un axe numérique utilisé en équipement, Equipment Module, on trouvera une commande du type « Pick » & « Place », c’est-à-dire un module qui prend une pièce et place une pièce, on reste au niveau fonctionnel (Functional Specification, FS) sans rentrer dans les détails. Pour un module de contrôle, Control Module on trouvera plutôt une commande du type : « Move back », « Close gripper », « Move forward », « Open gripper » on rentre dans le détails du mouvement (Design Specification, DS).

### Décomposition d'un Control Module
Il n'est pas exlu qu'un Control Module soit lui-même décomposé en entités plus petites. A titre personnel, j'utilse régulièrement la notion de **Device** ou **Device Module**. La notion de **Device** ne fait toutefois par partie de ISA 88. Si l'on prend le gripper ci-dessus, il est équipé à la fois d'un actionneur et d'une mesure. Si l'on prend une vanne de régulation telle que représentée dans le diagramme P&ID ci-dessous, on trouvera probablement un actionneur pneumatique et une mesure de position du pointeau de la vanne.

Si cet notion de Device n'existe pas dans le language ISA-88. elle peut être utile comme terme génériques aux différents éléments d'un Control Module. Même si officielement ISA-88 dit qu'un Control Module peut lui même être composé de plusieurs Control Modules, cette notion reste cependant difficile à gérer au niveau logiciel PLC.

### Un exemple de modélisation d'une unité représentée par son schéma P&ID.

<figure>
  <img src="./img/Example of P&ID Diagram.png"
     alt="Image lost: Example of P&ID Diagram.png">
  <figcaption>Exemple de diagramme P&ID</figcaption>
</figure>

<figure>
  <img src="./img/SysML version of P&ID Reactor (partial).png"
     alt="Image lost: SysML version of P&ID Reactor (partial).png">
  <figcaption>SysML version of P&ID Reactor (partial)</figcaption>
</figure>

C'est ce type de décomposition qu'il doit être possible de dessiner en automatisation de base.

## The Procedural Control Model

Le contrôle procédural ordonne aux actions orientées équipement de se dérouler dans une séquence ordonnée afin d'exécuter une tâche orientée processus.

Le contrôle procédural est composé d'éléments procéduraux qui sont combinés de manière hiérarchique pour accomplir la tâche d'un processus complet tel que défini par le modèle de processus. La hiérarchie des éléments procéduraux identifiés et nommés comprend des procédures, des procédures unitaires, des opérations et des phases.

 <figure>
  <img src="./img/S88 Procedural Model.png"
     alt="Image lost: S88 Procedural Model.png">
  <figcaption>S88 Procedural Model</figcaption>
</figure>

###	Procedure
La procédure est le niveau le plus élevé de la hiérarchie et définit la stratégie pour effectuer une action de traitement majeure telle que la création d'un lot. Il est défini en termes d'un ensemble ordonné de procédures unitaires.

#### Un exemple de procédure est :
« Produire 250 exemplaires d’une fixation de ski, model LX ».

###	Unit procedure
Une procédure d'unité consiste en un ensemble ordonné d'opérations qui provoquent une séquence de production contiguë au sein d'une unité. Une seule opération est présumée être active dans une unité à la fois. Une opération est menée à son terme dans une seule unité, Unit. Cependant, plusieurs procédures unitaires d'une même procédure peuvent s'exécuter simultanément, chacune dans des unités différentes.

#### Exemples de procédures
Charger les éléments à assembler sur une plaque de base
Assembler les différents composants.
Décharger les éléments terminés dans un panier à compartiments.

###	Opération
Une opération est un ensemble ordonné de phases qui définit une séquence de traitement majeure qui fait passer le matériau traité d'un état à un autre, impliquant généralement un changement chimique ou physique. Il est souvent souhaitable de localiser les limites des opérations à des points de la procédure où le traitement normal peut être suspendu en toute sécurité.

#### Voici quelques exemples d’opérations :
- Monter la plaque d’appuis sur la plaque de base
- Insérer le ressort de verrouillage
- Insérer le bouton en caoutchouc
- Contrôler la qualité du montage avec une caméra intelligente

###	Phase
Le plus petit élément de contrôle procédural qui peut accomplir une tâche orientée processus est une phase. Une phase peut être subdivisée en parties plus petites.
Une phase peut émettre une ou plusieurs commandes ou provoquer une ou plusieurs actions, telles que :
- Activation et désactivation des types de régulation de base et orientés état et spécification de leurs points de consigne et valeurs de sortie initiales
- Réglage, effacement et modification de l'alarme et d'autres limites
- Définition et modification des constantes de contrôleur, des modes de contrôleur et des types d'algorithmes
- Lecture des variables de processus, telles que la densité du gaz, la température du gaz et le débit volumétrique à partir d'un débitmètre, et calcul du débit massique à travers le débitmètre
- Effectuer des contrôles d'autorisation des opérateurs.
L'exécution d'une phase peut entraîner :
- Des commandes au contrôle de base ;
- des commandes à d'autres phases (dans la même entité d'équipement ou dans une autre)
- et / ou la collecte de données.

Le but de la phase est de provoquer ou de définir une action orientée processus, tandis que la logique ou l'ensemble des étapes qui composent une phase sont spécifiques à l'équipement.

#### Voici des exemples de phases :
- Saisir une pièce de type X44.
- Insérer la pièce X44 sur la plaque X42.
- Presser la pièce X44
- Controller la position de la pièce X44.
- Incrémenter le nombre de pièce X44
Phases et commandes
Une phase est le niveau le plus bas du modèle de procédure. Il existe deux versions d'une phase. Une phase de recette est abstraite, elle est gérée par un logiciel de recette (base de données). Une phase d'équipement est définie pour un matériel spécifique. En fait, une phase d'équipement peut être un sous-programme de logiciel qui contrôle l'équipement. La plupart des phases d'équipement sont programmées dans des automates.
Une phase peut être un bloc fonctionnel dans un projet PLC.
L’idée principale est de séparer au maximum lors de l’écriture du code ce qui est du domaine du pilotage de l’équipement, de celui qui concerne sa fonctionnalité.

Par exemple :

Un portique 3 axes avec un gripper peut être utilisé sur une machine comme « dépalettiseur » ou « palettiseur ». C’est-à-dire soit pour charger des pièces à assembler sur une machine, soit pour décharger des pièces assemblées sur la machine.
Toute la logique interne du portique concerne l’équipement, Equipment Module.
Le pilotage en « palettiseur » ou « dépalettiseur » concerne la procédure, ce peut être une phase.
La disposition des pièces sur la barquette où sont disposées les pièces, ou l’emplacement choisi pour charger la pièce sur la machine peut faire partie de la recette.
La nuance n’est pas forcément aisée à comprendre. Cela signifie qu’au sein du même programme PLC on retrouvera des éléments de code qui « appartiennent » au model procédural alors que d’autres seront attaché au modèle physique.

##	The Process Model
 
<figure>
  <img src="./img/S88 Process Model.png"
     alt="Image lost: S88 Process Model.png">
  <figcaption>S88 Process Model</figcaption>
</figure>

Pour la définition du Process, voir ci-dessus, Classes de processus industriels.

###	Process stages
Le processus se compose d'une ou plusieurs étapes de processus qui sont organisées en un ensemble ordonné, qui peut être en série, en parallèle ou les deux. Une étape de processus fait partie d'un processus qui fonctionne généralement indépendamment des autres étapes du processus. Il en résulte généralement une séquence planifiée de changements chimiques ou physiques dans le matériau traité.

Les étapes typiques du processus peuvent être les suivantes :
- Charger les éléments à assembler sur une plaque de base.
- Assembler les différents composants.
- Décharger les éléments terminés dans un panier à compartiments.

###	Process Operations
Chaque étape du processus consiste en un ensemble ordonné d'une ou plusieurs opérations de processus. Les opérations de traitement représentent des activités de traitement majeures. Une opération de processus entraîne généralement un changement chimique ou physique du matériau traité.

Les opérations de processus typiques peuvent être les suivantes :
- Monter la plaque d’appuis sur la plaque de base
- Insérer le ressort de verrouillage
- Insérer le bouton en caoutchouc
- Contrôler la qualité du montage avec une caméra intelligente

###	Process Actions
Chaque opération de processus peut être subdivisée en un ensemble ordonné d'une ou plusieurs actions de processus qui exécutent le traitement requis par l'opération de processus. Les actions de processus décrivent des activités de traitement mineures qui sont combinées pour constituer une opération de processus. Les actions de processus typiques peuvent être les suivantes :
- Pick part X21
- Check colour of X21
- Place part X21
- Weld part X21
- Move plate to next station

<figure>
  <img src="./img/S88 Relations.png"
     alt="Image lost: S88 Relations.png">
  <figcaption>S88 Relations</figcaption>
</figure>

##	« Receipt », les recettes
Les recettes sont un des concepts de base du model S88. Une des bases de sa modularité.
Cependant, la notion de recette est avant tout une notion ISA-88 dans sa description fondamentale qu’est le « Batch ».
Dans la dérivation « Discrete parts manufacturing processes », on a plutôt l’habitude d’utiliser le terme de variante(s).

### Recettes
La notion de recette est très importante, principalement dans l’industrie du process, industrie chimique, agro-alimentaire... L’idée est de pouvoir utiliser la même installation pour différents types de produits et rationnaliser ainsi les coûts d’infrastructure. Pour donner un exemple simple, selon les produits à fabriquer on passera par différents tuyaux et différentes cuves, on va plus loin que la simple notion de paramètres. Des logiciels dédiés existent sur le marché, cependant, le détail de l’implémentation des recette dépasse le cadre de ce cours.

### Forme la plus simple
Dans sa forme la plus simple, une recette pourrait être éditée comme une séquence linéaire dans un tableau Excel puis exportée dans un fichier *.XML ou *.CSV et finalement transmise à la machine :

|N°	|Phase	|Paramètre	|Valeur	|Type|
|---|------|----------|-------|----|
|1	|Remplir |Eau	|1000 kg	|Entrée|
|2	|Ajouter |Sel	|50 kg	|Entrée|
|3	|Chauffer |Vapeur	50|°C	|Process|
|4	|Ajouter |Sucre	30 |kg	|Entrée|

#### Exemple de format CSV, *pour information*.
Un fichier CSV (Comma-Separated Values) est un format de fichier texte utilisé pour stocker des données tabulaires, telles que celles d'une feuille de calcul ou d'une base de données. Chaque ligne du fichier représente un enregistrement, et chaque champ de l'enregistrement est séparé par une virgule (ou un autre délimiteur, comme un point-virgule). Les fichiers CSV sont largement utilisés pour l'importation et l'exportation de données entre différents logiciels.

Dans cet exemple, le fichier CSV contient trois enregistrements avec cinq champs : N°,Phase,Paramètres de phase,Paramètre,Valeur et Type.

```csv
N°,Phase,Paramètres de phase,Paramètre,Valeur,Type
1,Remplir,Eau,1000 kg,Entrée
2,Ajouter,Sel,50 kg,Entrée
3,Chauffer,Vapeur,50°C,Process
4,Ajouter,Sucre,30 kg,Entrée
```

#### Exemple de fichier XML, *pour information*

Un fichier XML (Extensible Markup Language) est un format de fichier texte utilisé pour structurer, stocker et transporter des données. XML utilise des balises pour définir les éléments de données, ce qui permet de représenter des informations de manière hiérarchique et lisible par les humains et les machines.

Les fichiers XML sont couramment utilisés pour **échanger des données entre différentes applications et systèmes**, ainsi que pour **configurer des applications** et des services web.
L'avantage du fichier XML par rapport au XML est sa robustesse. Il est presque impossible de confondre un champ avec un autre. Par contre, il est plus volumineux et plus complexe à traiter.

Point intéressant: un fichier XML avec une entête peut être facilement ouvert avec n'importe quel Browser ou directement avec Excel.

```xml
<Recette>
  <Phase>
    <N>1</N>
    <Nom>Remplir</Nom>
    <Parametres>
      <Parametre>
        <Nom>Eau</Nom>
        <Valeur>1000 kg</Valeur>
        <Type>Entrée</Type>
      </Parametre>
    </Parametres>
  </Phase>
  <Phase>
    <N>2</N>
    <Nom>Ajouter</Nom>
    <Parametres>
      <Parametre>
        <Nom>Sel</Nom>
        <Valeur>50 kg</Valeur>
        <Type>Entrée</Type>
      </Parametre>
    </Parametres>
  </Phase>
  <Phase>
    <N>3</N>
    <Nom>Chauffer</Nom>
    <Parametres>
      <Parametre>
        <Nom>Vapeur</Nom>
        <Valeur>50°C</Valeur>
        <Type>Process</Type>
      </Parametre>
    </Parametres>
  </Phase>
  <Phase>
    <N>4</N>
    <Nom>Ajouter</Nom>
    <Parametres>
      <Parametre>
        <Nom>Sucre</Nom>
        <Valeur>30 kg</Valeur>
        <Type>Entrée</Type>
      </Parametre>
    </Parametres>
  </Phase>
</Recette>
```

[Le fichier suivant est un fichier complet avec des paramètres XML](./Recette_XML_File.xml).

##	Mode et états S88
Les modes et les états du S88 sont traités dans le [PackML qui fait l'objet d'un module séparé](../03%20S6%20Module%20Pack/03%20S6%20Module%20Pack%20Model.md). qui dérive du S88 mais les définit de manière plus précise.

Les états du PackML et du S88 sont légèrement différents. Si une définition stricte des états du S88 est nécessaire, on se réfèrera à la norme ISA-88. Il sera plus facile de partir de la machine d’état du PackML pour l’adapter au S88 que l’inverse.

Il faut bien garder en tête que le model « procédural » se fout de savoir si le model physique est géré par un automate « ou pas ». Typiquement le model physique pourrait très bien être un « humain » auquel le model procédural donne des ordres et attend une quittance pour passer à l’étape suivante.

##	Commentaire
Pour l’automaticien, il y a deux cas de figure. Soit il travaille dans un environnement S88 et ce chapitre servira d’introduction. Soit il travaille dans un environnement en dehors de S88 et il sera intéressant de s’en inspirer.

Dans un projet complexe, la définition des éléments de la machine, ces modes de fonctionnement et la définition des différents états est un élément très important pour le travail de l’automaticien. Prenons l’exemple d’un robot cartésien composé de trois moteurs linéaires équipés de règles relatives et équipé de quelques éléments de sécurité comme le STO, Safe Torque Off, SOS, Safe Operating Stop et SLS, Safe Limited Speed.

A un moment donné dans le cycle de la machine, il va falloir :
- mettre ces axes sous tension,
- procéder à leur prise de référence,
- les placer dans leur position initiale,
- les placer dans une position de dégagement en cas d’arrêt temporaire de la machine,
- les arrêter lors de l’information d’arrêt d’urgence,
- les mettre hors tension avant la coupure de l’arrêt d’urgence,
- les placer en vitesse lente pour accéder à des réglages,
- permettre leur mouvement manuel,
- faire des cycles pas à pas lors de la mise en service…

Il est plus que probable que les simples états Start et Stop, pour autant qu’ils soient même définis soient suffisants pour définir le contexte dans lequel le robot cartésien va pouvoir évoluer

#	[ISA 95](https://www.isa.org/standards-and-publications/isa-standards/isa-standards-committees/isa95), ou [IEC 62264](https://www.iso.org/standard/57308.html), *pour information*.
**Les fonctions couvertes par ISA 95 sortent du cadre de ce cours**. Elles se situent « en dessus » de la norme ISA 88 pour faire le lien avec les logiciels de gestion d’entreprise, Enterprise Resource Planning, ERP.

La norme ISA 95 se compose de 11 fonctions stratégiques pour l’amélioration du pilotage de la production Chacune d’elles est associée à une fiche qui décrit comment se situe la fonction dans un système Manufacturing Execution System, MES et en détaille les principales tâches.

Les 11 fonctions de la norme ISA-95
  1.  Contrôle et d’allocation des ressources
  2.  Dispatching de la production
  3.  Collecte et d’acquisition de données
  4.	Gestion de la qualité
  5.	Gestion des procédés de fabrication
  6.	Planification et de suivi
  7.	Analyse de la performance
  8.	Gestion des opérations et d’ordonnancement
  9.	Gestion de la documentation
  10.	Gestion de la main d’œuvre
  11.	Gestion de la maintenance

# Pour alimenter votre réflexion sur une base ISA-95
<div align="center">
  <figure>
    <img src="./img/Automation_Pyramid_752K9D7VCA_1300.avif"
       alt="Image lost: Automation_Pyramid_752K9D7VCA_1300.avif">
    <figcaption>Source: Katti, Badarinath. (2020). Ontology-Based Approach to Decentralized Production Control in the Context of Cloud Manufacturing Execution Systems. 10.13140/RG.2.2.11486.46402</figcaption>
  </figure>
</div>

[Cette image est tirée d'un article du site de Flow-Fuse](https://flowfuse.com/blog/2023/08/isa-95-automation-pyramid-to-unified-namespace/), qui est l'éditeur de la brique logicielle que nous utilisons avec Node-RED pour l'édition des interfaces utilisateurs dans les cours pratiques.

En voici un résumé rédigé avec Copilot ainsi que deux questions posées à Copilot.

- [Résumé de la page Flow-Fuse résumée par Copilot](#pourquoi-la-pyramide-dautomatisation-bloque-la-transformation-numérique).
- Question à Copilot: [Qu'est-ce qu'un namespace unifié (UNS) ?](#quest-ce-quun-namespace-unifié-uns-)
- Question à Copilot: [Est-ce que OPC-UA peut être considéré comme un UNS ?](#est-ce-que-opc-ua-peut-être-considéré-comme-un-uns-)

## Pourquoi la pyramide d'automatisation bloque la transformation numérique

### Introduction
La pyramide d'automatisation ISA-95 traditionnelle a été une pierre angulaire de l'automatisation industrielle. Cependant, elle pose des défis significatifs aux efforts de transformation numérique.

### La pyramide d'automatisation
Le modèle pyramidal organise les systèmes d'entreprise en niveaux hiérarchiques, des dispositifs physiques en bas à la planification d'entreprise en haut. Cette structure crée des silos, entravant le flux de données et l'intégration.

### Namespace unifié
Un namespace unifié (UNS) offre une solution en fournissant une source unique de vérité pour toutes les données. Il élimine les silos, permettant un échange de données fluide et une prise de décision en temps réel.

### Avantages du UNS
- **Accessibilité améliorée des données**: Toutes les données sont accessibles en temps réel.
- **Flexibilité accrue**: Intégration plus facile des nouvelles technologies.
- **Meilleure prise de décision**: Les données en temps réel soutiennent des décisions éclairées.

### Conclusion
Passer de la pyramide d'automatisation à un namespace unifié est crucial pour réussir la transformation numérique dans les environnements industriels.

### Résumé
La pyramide d'automatisation ISA-95, bien que fondamentale, crée des barrières à la transformation numérique. L'adoption d'un namespace unifié peut surmonter ces barrières en permettant l'accès et l'intégration des données en temps réel, facilitant ainsi une meilleure prise de décision et une flexibilité technologique accrue.

### Qu'est-ce qu'un namespace unifié (UNS) ?

Un namespace unifié (UNS) est une architecture de gestion des données qui centralise toutes les informations d'une organisation dans un seul espace de noms. Cela signifie que toutes les données, qu'elles proviennent de capteurs, de systèmes de contrôle, de logiciels de gestion ou d'autres sources, sont accessibles et interconnectées de manière cohérente et uniforme.

Le UNS permet de surmonter les limitations des systèmes hiérarchiques traditionnels en éliminant les silos de données. Il facilite l'intégration des technologies de l'Internet des objets (IoT), des systèmes de gestion de la production (MES), des systèmes de planification des ressources d'entreprise (ERP) et d'autres outils numériques. En conséquence, les entreprises peuvent accéder à des données en temps réel, améliorer leur prise de décision et accroître leur agilité opérationnelle.

Les principaux avantages d'un UNS incluent :
- **Centralisation des données** : Toutes les données sont stockées et accessibles à partir d'un seul endroit.
- **Interopérabilité** : Les systèmes disparates peuvent communiquer et échanger des informations sans barrières.
- **Évolutivité** : Facilité d'ajouter de nouvelles sources de données et technologies sans restructurer l'architecture existante.
- **Visibilité en temps réel** : Accès instantané aux données actuelles pour une prise de décision rapide et informée.

En adoptant un UNS, les entreprises peuvent transformer leurs opérations et tirer pleinement parti des initiatives de transformation numérique.


### Est-ce que OPC-UA peut être considéré comme un UNS ?

OPC-UA (Open Platform Communications Unified Architecture) est souvent considéré comme une technologie clé pour la mise en œuvre d'un namespace unifié (UNS). OPC-UA est un protocole de communication indépendant de la plateforme qui permet l'échange sécurisé et fiable de données dans les environnements industriels.

#### Caractéristiques de OPC-UA en tant que UNS :
- **Interopérabilité** : OPC-UA permet la communication entre différents systèmes et dispositifs, facilitant l'intégration des données.
- **Sécurité** : Il offre des fonctionnalités de sécurité robustes, y compris l'authentification, l'autorisation et le cryptage des données.
- **Scalabilité** : OPC-UA peut évoluer pour répondre aux besoins des petites installations comme des grandes entreprises.
- **Modélisation de l'information** : Il permet de structurer et de modéliser les données de manière cohérente, ce qui est essentiel pour un UNS.

En résumé, OPC-UA peut être utilisé comme une base pour créer un namespace unifié, en fournissant les outils nécessaires pour centraliser et intégrer les données de manière sécurisée et évolutive.

> OPC-UA sera brièvement abordé dans la suite de ce cours d'automatisation.



