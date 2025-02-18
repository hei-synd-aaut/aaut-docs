<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  HEI-Vs Engineering School <h2>AAut Advanced Automation</h2>
  <br>
</h1>

[Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

# Commentaires sur les URS de la question 1

1. L'interface utilisateur doit offrir une vue d’ensemble du banc de test avec l’affichage des différentes grandeurs mesurées et du statut des instruments : SV1-2, FC1-3, FT1-3, TT.
	- **Imprécis** : "Vue d'ensemble" et "statut des instruments" ne sont pas clairement définis. Il faudrait spécifier quelles informations exactes doivent être affichées et comment le statut des instruments doit être représenté.

> Attention, l'interface est ce que l'utilisateur voit en premier. Même une personne non spécialisée aura des commentaire à faire. Idéelement on proposera un protoype d'interface avant de passer à la réalisation.

> Eviter toute représentation graphique à moins de déjà disposer d'une librairie graphique.

> Lors de ce projet, le client voulait après-coup une représentatin graphique. **On a du la refuser**.

> Lors de ce projet, le client a voulu changer par la suite le type d'unité, cela a entrainé un premier retard du à une incompréhension sur le type d'unité.

2. L'utilisateur doit pouvoir lire en temps réel les valeurs de pression, température et débit pour les MFC et MFM : FC1-3, FT1-3.
	- **Imprécis** : "En temps réel" doit être quantifié. Par exemple, quelle est la fréquence de mise à jour des valeurs ?

> Il peut y avoir une très grande différence selon les types de processus. Pour un axe numérique, on voudra un affichage presque instantané de l'ordre de 40 [ms] / 25 Hz. En chimie on pourra souvent se contenter de l'ordre de la seconde.

3. L'utilisateur doit pouvoir modifier la composition des gaz pour les MFC et MFM : FC1-3, FT1-3 depuis l'interface utilisateur.
	- **Imprécis** : "Modifier la composition des gaz" n'est pas clair. Il faudrait préciser quels paramètres peuvent être modifiés et dans quelles limites.

> Cette partie a nécessité une modification complète de l'accès aux données des appareils. Arpès mise en service. Perte de plus d'une semaine de travail.

1. L'utilisateur doit pouvoir régler le débit des MFC : FC1-3.
	- **Imprécis** : Les plages de réglage des débits ne sont pas spécifiées.

> Il manque la plage et la précision deu réglage.

2. L'utilisateur doit pouvoir régler la pression amont pour le MFM : FT3.
	- **Imprécis** : Les plages de réglage de la pression ne sont pas spécifiées.

3. L'utilisateur doit pouvoir lire la température des éléments chauffants : TE1-3.
	- **Imprécis** : La précision de la lecture de la température n'est pas spécifiée.

4. L'utilisateur doit pouvoir contrôler la température des éléments chauffants et la réguler.
	- **Imprécis** : Les plages de contrôle et les méthodes de régulation ne sont pas spécifiées.

> Il a fallu modifier la vitesse de chauffe en limitant la pente.

> Au moment de la mise en service, il s'est avéré qu'il y avait un délai important entre l'élément de chauffe et la sonde de température. Ce délai rend un PID standard inutilisable. Il faut passer par un Prédicteur de Smith. Le problème n'est pas résolu faute de temps. Il y a un overshoot important lors de la mise en température du système.

5. L'utilisateur doit pouvoir ouvrir/Fermer les vannes de sécurité : SV1-2.
	- **Imprécis** : Les conditions sous lesquelles les vannes peuvent être ouvertes ou fermées ne sont pas spécifiées.

6. L'utilisateur doit pouvoir sauvegarder à intervalles réguliers les différentes valeurs mesurées dans un fichier de type ``*.txt`` ou ``*.csv``.
	- **Imprécis** : Les intervalles de sauvegarde ne sont pas spécifiés.
  
> Il manque surtout la durée de la mesure. Cela a un impact important sur la taille du fichier final.

> Les intervalls sont spécifiés dans les spécifications non fonctionnelles.

7.  L'utilisateur doit pouvoir sauvegarder et ouvrir un fichier de configuration pour les différents éléments du banc.
	 - **Imprécis** : Le format et le contenu exacts du fichier de configuration ne sont pas spécifiés.

