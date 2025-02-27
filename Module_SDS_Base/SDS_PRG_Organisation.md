<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  <p style="color:grey;">Institute Systems Engineering</p>
  <br>
</h1>

Author: [Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

# Les tags
Le but d'un programme PLC est de piloter une installation réelle composée d'appareil, **devices**, en activant des sorties, **actuateurs**, **actuators**, en fonction des signaux reçus, **sensors**.

Ces signaux sont dans les cas simples reliés à des entrées et sorties logicielle qui au niveaux logiciel sont nommés partois des **tags**. Pour parler de cette liaison entre le hardware et le software on parle parfois aussi de **link** ou de table de **map**.



# Organisation des programmes
Dans un petit programme PLC on peut ne trouver qu'un seul programme. Dans la réalité, on verra que même une petite installation peut rapidement devenir trop complexe à gérer pour un seul programme.

## Proposition
Il n'existe probablement aucune règle, directive ou publication pour l'organisation des programmes dans un PLC. Une bonne organisation du code est pourtant peut-être encore plus importante que la qualité du code elle même. C'est pourquoi nous vous proposons un type d'organisation.

# PRG_Map
Ce programme sert à lier le software avec le hardware. On aurait pu utiliser plusieurs mots clé à choisir entre Map, Link et Tag, entre autres.
Nous choisisson Map avec la défition suivante inspirée par futura-science.com

> *Le mappage de données, communément appelé "mappe", est une stratégie essentielle dans le domaine de l'informatique et de la gestion de données. Cette pratique consiste à associer et aligner des données provenant de sources diverses, souvent hétérogènes en termes de structure, de format et de système*.

## Raison d'être de ce programme
Le principe est de séparer la partie logicielle de la partie matériel. Un logiciel de programmation moderne permet le plus souvent de travailler en mode dit "Simulation", l'objectif étant de pouvoir développer le logiciel indépendament de la présence de la machine. Le rôle principal de ce programme est donc de pouvoir séparer la programmation de la machine et si nécessaire de pouvoir simuler le matériel.

### Exemple

```iecst
// 
//    Global Hardware variables for a project...
//    
//    www.hevs.ch
//    Institut Systemes Industriels / Power & Control
//    Project:    LearnPlc
//    Author:     Cedric Lenoir
//    Date:       2024 Novembre 20
{attribute 'qualified_only'}
VAR_GLOBAL
	// Inputs
	one_I_Bool AT %I*	: BOOL;
	// Outputs
	one_Q_Bool AT %Q* 	: BOOL;
END_VAR
```

```iecst
IF xHardwareExist THEN
    diSensor_1 := one_I_Bool;
    one_Q_Bool := doActuator_1;
ELSE (* Simulate *)
    diSensor_1 := fromMatlab;
    toMatlab := doActuator_1;
END_IF
```
Il suffira donc d'activer une seule variable, ``xHardwareExist`` pour travailler ou non en simulation.

> On peut aussi se placer du côté du technicien responsable de la mise en service de la partie matérielle. Il serai possible de vérifier sur un seul programme la validité du hardware, même si la partie logicielle n'est pas terminée.

# PRG_DeviceManager
La définition de Device selon Oxford Languages: *a thing made or adapted for a particular purpose, especially a piece of mechanical or electronic equipment*, soit une chose fabriquée ou adaptée à un usage particulier, en particulier un équipement mécanique ou électronique.

Dans notre cas, le but principal du Device Manager consiste à mettre en forme les différents signaux hardware pour les rendre directement utilisables par le processus.

## Cas typique, les entrées et sorties analogiques
Une entrée analogique sera convertie par un convertisseur A/D avec un nombre de bits dépendant de la précision souhaitée, par exemple 12 bits.

### Exemple: Beckhoff EL3054
[EL3054 | EtherCAT Terminal, 4-channel analog input, current, 4…20 mA, 12 bit, single-ended](https://www.beckhoff.com/en-en/products/i-o/ethercat-terminals/el3xxx-analog-input/el3054.html).

*The EL3054 analog input terminal processes signals in the range between 4 and 20 mA. The current is digitized to a resolution of 12 bits and is transmitted (electrically isolated) to the higher-level automation device. The input electronics are independent of the supply voltage of the power contacts. In the EL3054 with four inputs, the 24 V power contact is connected to the terminal in order to enable connection of 2-wire sensors without external supply. The power contacts are connected through. The signal state of the EtherCAT Terminal is indicated by light emitting diodes. The error LEDs indicate an overload condition and a broken wire.*

Le convertisseur transmet l'information sous forme d'un **INT**, selon IEC 61131-3, 16 bits signés. Supposons que le sensor soit un capteur de pression. Le rôle du Device Manager est de mettre en forme le signal pour que le programme principal [PRG_Process](#prg_process) puisse directement l'utiliser.

|Description	                 |Manufacturer|Reference	              |Signal |Measured value|Unit|Range|Tag Number|I/O  module|
|--------------------------------|------------|---------------------------|-------|--------------|----|------|---------|-----------|
|Pressure sensor with transmitter|Wika	      |A-10-6-BV325-NBZZ-AA-AGZ-ZW|	4…20mA|Pressure      |bars|-1…1.5|PLC_4.1  |EL3054|

[PRG_Map](#prg_map) fera le lien entre une entrée un tag de type ``PLC_4_1 AT %I*	: INT;`` et la variable ``aiSensor``.

``aiSensor := PLC_4_1``;

PRG_DeviceManager se chargera de convertir ``aiSensor`` en une valeur de type analogique, par exemple ``rPressureVacuum_bar``.

Mais le rôle du Device Manager, via un bloc de type DM_PressureSensor, sera aussi de vérifier la plage de pression se situe bien dans la plage donnée, soit $-1$ à $1.5 [bar]$, pour si nécessaire générer une alarme.

D'une certaine manière on pourrait dire que le Device Manager joue un rôle d'instrumentation.

# PRG_Process
Ce programme gère le processus de l'unité au sens ISA-88 Unit. Dans ce cours, il n'est pas prévu d'aller plus loin que le niveau Unit.

Une unité peut contenir un ou plusieurs équipements, Equipement Module, lui même constitué de 1 ou plusieurs modules de contrôle, Control Module.

Le principe de la modularité veut que dans la mesure du possible on écrive de code qui soit réutilisables, c'est à dire des bloques fonctionnels, ou Function Block.

Le caractère purement cyclique de la prgogrammation PLC et son lien avec le hardware implique qu'il n'est pas possible d'interrompre un programme pour l'analyser. L'écriture des fonctions ou méthodes pose ainsi un problème car leur code est compliqué à analyser et corriger car elles leur code ne peut être visualisé sur l'interface de développement.

Pour cette raison on privilégiera le Function Block, voir le programme. Une bonne méthode consiste souvent à développer un code dans un programme, puis de le convertir en bloque fonctinnel une fois qu'il a été validé.

> Pour rappel, il est possible d'utiliser un programme qui appel un programme. Pour une application avec quelques équipements, on peut parfaitement immaginer que les équipements soient codés sous forme de programme. On aura ainsi un programme principal qui appel un programme Unit qui lui même est constitué de plusieurs programmes Equipement.

> Pour rappel, au niveau du fonctionnement du PLC, chaque programme est appelé par une tâche.
> Chaque tâche se voit attribuer un temps de cycle.

Une tâche unique. Il est en théorie possible d'utiliser plusieurs tâches, par exemple, il peut être nécessaire d'utiliser une tâche particulièrement rapide pour la gestion de certains interfaces vers le hardware. On ce qui concerne le cours d'automatisation de base, nous partons du principe que nous utilisons une seule tâche qui gère l'ensemble des programmes. C'est un général suffisant, même pour des machines relativement complexes.

> La gestion de plusieurs tâches augmente la compexité du logiciel, donc sauf nécessité, on privilégiera une seule tâche.

> Il est possible de gérer l'ordre des tâches dans le gestionnaire de tâche du système de développement. Cependant, il est probablement plus propre et robuste de gérer les programmes dans des appels de programmes tel que ci-dessous.

> Si certains équipements sont similaires, on envisagera de transformer les programmes en Function Blocks

- PRG_Process
- PRG_Unit
- PRG_EM01_UnitNameOne
- PRG_EM02_UnitNameTwo
- PRG_EMxx_UnitNameXX

```iecst
PROGRAM PRG_Process
VAR
  (*Variables for Process*)
END_VAR

PRG_Unit();

(*End of program*)
```

```iecst
PROGRAM PRG_Unit
VAR
  (*Variables for Unit*)
END_VAR

PRG_EM01_UnitNameOne();
PRG_EM02_UnitNameTwo();
PRG_EMxx_UnitNameXX();

(*End of program*)
```

# Programme simple
Pour certaines applications très simples ou du prototypage, on pourra envisager de ne travailler que dans le [PRG_Process](#prg_process) sans passer par le découpage S88. Cependant la séparation Map, Device et Process restera un gain de productivité.

# Autres programmes
Un environnement de type Windows est composé de différents programmes destinés à une application particulière, Word, Matlab, AutoCAD, mais aussi d'applications génériques, File Explorer, Command Prompt, System Information.
Il en va de même pour un environnement IACS. Dans le cadre du laboratoire d'automation de la HEVS, la majorité des programmes sont réalisé en utilisant une composante PackML. Cette composantes permet de gérer les différents états et mode de fonctionnement, les alarmes et les différents paramètres de la machine.