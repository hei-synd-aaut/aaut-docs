<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  <p style="color:grey;">Institute Systems Engineering</p>
  <br>
</h1>

Author: [Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

# Interfaces

Il existe encore parfois des systèmes IACS dont les interfaces sont consititués uniquement de cartes d'interface classique de type Digital In/Out ou Analog In/Out. 

## Exemple Wago Compact Controller 100

<figure>
    <img src="./img/Wago Compact Controller 100.jpg"
         alt="Image lost: Wago Compact Controller 100"
         width= 60%>
    <figcaption>Wago Compact Controller 100</figcaption>
</figure>

> Description du fabricant: [Contrôleur Compact 100; 8DI 4DO 2AI 2AO 2NI1K/PT1K 1RS485; 2 x ETHERNET; SD](https://www.wago.com/ch-fr/contr%C3%B4leur/contr%C3%B4leur-compact-100/p/751-9301)

Ce type de PLC est équipé de:
-   8 Entrées digitales
-   4 Sorties digitales
-   2 Entrées analogiques
-   2 Sorties analogiques.

On note toutefois la présence du terme **RS485** et c'est là que les choses commencent à se compliquer un peu. C'est la aussi que s'arrêtera le cours d'automatisation de base. On décrit en quelques mots ce que permet de faire se type d'interface, mais nous n'aborderons pas sa programmation.

# Principaux interfaces d'un IACS
IACS pour Industrial Automation Control System. Nous utiliserons encore le terme PLC, Programmable Logic Controller, mais dans les systèmes modernes, il faut voir le PLC comme une partie d'un IACS.

RS-232

RS-485

RS-422

Modbus

Modbus RTU

IO-Link

[Exemple Alicat](https://www.alicat.com/support/communication-options-for-alicat-instruments/)

Communication options for Alicat instruments
Every Alicat device is equipped with at least one of the following communication protocols:

    Analog (4-20 mA, 0-10 Vdc, 0-5 Vdc, or 1-5 Vdc)
    ASCII over RS-232 or RS-485
    DeviceNET
    EtherCAT
    EtherNet/IP
    IO-Link
    Modbus RTU
    Modbus TCP/IP
    PROFIBUS
    PROFINET

