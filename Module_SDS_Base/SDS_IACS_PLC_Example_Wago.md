<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  <p style="color:grey;">Institute Systems Engineering</p>
  <br>
</h1>

Author: [Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

# Un exemple de PLC, Wago Compact 100
Si ce cours comporte une partie générique qui aborde les systèmes d'automatisation avec un certain niveau d'abstraction, comme les machines d'état et quelques construction UML, il est aussi destiné à un usage dirctement pratique.

Le PLC Wago constitue un bon exemple de ce que chaque ingénieur en systèmes industriel devrait être capable de comprendre. 

L'ensemble des données techniques détaillées de ce module sont des termes qui sont indépendants du fournisseur et se retrouvent dans la majorité des produits d'automatisation industrielle.

# Types d'application

> [Liste des termes que l'ingénieur en automatisation doit être capbable de comprendre](https://www.wago.com/ch-fr/contr%C3%B4leur/contr%C3%B4leur-compact-100/p/751-9301)

...

Communication	Maître EtherCAT
EtherNet/IPTM-Adapter (Esclave)
Modbus (TCP, UDP)
EtherCAT-Master
EtherNet/IPTM Adapter (esclave)
EtherNet/IPTM Scanner
Modbus RTU
Interface RS-485
OPC UA Serveur/Client
MQTT
Protocole de télécontrôle, nécessite une licence supplémentaire
BACnet/IP, nécessite une licence supplémentaire
Protocole Ethernet	DHCP
DNS
NTP
FTP
FTPS
SNMP
HTTP
HTTPS
SSH
Visualisation	Visualisation Web
Système d'exploitation	Linux Temps réel (avec patch préemption RT)
CPU	Cortex A7 ; 650 MHz
Langages de programmation selon CEI 61131-3	Diagramme de blocs fonctionnels (FUP)
Continuous Function Chart (CFC)
Liste d'instructions (IL)
Schéma à contacts (LD)
Diagramme de Blocs Fonctionnels (FDB)
Continuous Function Chart (CFC)
Structuré (ST)
Grafcet (SFC)
Environnement de programmation	Node-RED
CODESYS V3.5
Node RED
Possibilités de configuration	ETHERNET-Settings
CODESYS V3.5
ETHERNET Settings
Web-Based-Management
WAGOupload
WAGO Solution Builder
Vitesse de transmission	ETHERNET: 10/100 Mbit/s
Moyen de transmission (Communication/bus de terrain)	ETHERNET: Paire de conducteurs torsadés S-UTP 100 Ω Cat 5 ; 100 m Longueur du conducteur max.
Mémoire principale (RAM)	512MB
Mémoire interne (Flash)	4096MB
Mémoire sauvegardée matériel	128kbyte
Mémoire programme	32 MB
Mémoire données	128 MB
Mémoire sauvegardée logiciel	128,kbyte
Type de cartes mémoire	microSD jusqu'à 32 GB (les caractéristiques ne sont garanties et valables que pour les cartes mémoire WAGO).
Carte mémoire - Embase	Mécanisme push/push
Éléments d'affichage	LED (SYS, RUN), rouge/verte : état système ; LED (USR) rouge/verte : état programmable par l'utilisateur (utilisable par une bibliothèque CODESYS) ; LED (SD) orange : état microSD ; LED (LNK/ACT) verte : connexion réseau Port 1 … 2 ; LED (DI1 … 8) verte : état entrées ; LED (DO1 … 4) verte : état sorties
Éléments de réglage	Commutateur de fonctionnement (RUN, STOP, RESET) ; bouton reset
Tension d'alimentation système	24 V DC (-15 … +20 %); sur niveau de câblage (picoMAX® 3.5 ; connexion Push-in CAGE CLAMP®)
Consommation de courant Système max.	500mA
Tension d'alimentation terrain	24 V DC (-15 … +20 %); sur niveau de câblage (picoMAX® 3.5 ; connexion Push-in CAGE CLAMP®)
consommation de courant Terrain max.	2 000mA
Séparation de potentiel	1250 V (DC 1 min., entre le système et le terrain (sorties digitales))
Nombre d'entrées digitales	8
Caractéristique d'entrée	Type 3 (selo