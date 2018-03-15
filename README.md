# Kytes

It's That I like going up in the air with the clouds, but I so like my feet right there on the ground, here.

Kytes is a software factory exprience, with full devops behavior, and a fullstack approach.

A full devops behavior: Kytes is designed for devops professionals, as a tool.
A fullstack approach: If it takes modifying a bootloader to make an application even better, let's make it possible as easily as an 'mvn update'
And What about pulling A linux kernel module into a Vert-x Java Pipeline?

This software factory project began March, 2018.


Une usine logicielle est un infrastructure IT.
Et comme toute infrastructure IT, elle se construit en commençant par le matériel.

Kytes aura la capacité à se déployer:
* à partir d'une infrastructure "bare-metal": à partir de machines "nues", n'ayant aucun OS installé.
* à partir d'une infrastructure provisionnée par une offre IAAS privée (Openstack, openshift, un simple petit VirutalBox installé sur un gros PC...), publique (GCP, AWS), ou hybride.

DAns les deux cas, l'infrastructure provisionnée au départ, devra être "enrollée".

Les deux premières fonctions qui seront assurées par `kytes-aerodyne`, seront donc:
* l' "enrollement" des machines physiques.
* la gestion de l'inventaire des machines physiques.

Ces fonctions seront assurées par un composant nommé `kytes-aerodyne`, dont la première version reposera sur le fonctionnement d'un
composant JCA, encapsulé dans un conteneur docker embarquant une distribution Wildfly/JBossEAP minimale.

* Toutes les machines physiques doivent être au préalable configurées en PXE boot +  Wake On LAN (beaucoup plus confortable pour la conception de la configuration kickstart)
* `kytes-aerodyne` détecte une nouvelle machine physique dès sa séquence d'amorçage, à condition qu'elle soit dans le même réseau physique: connectée à la même interface physique routeur.
* `kytes-aerodyne` détecte une nouvelle machine physique et l'identifie par une ADRESSE MAC, et/ou device UUID.
* `kytes-aerodyne` propose un dashboard comprenant un onglet "topologie de l'infrastructure": il s'agit d'un schéma que vous pouvez éditer, dans lequel vous pouvez représenter tous les éléments matériels de l'infrastructure à votre ddisposition. Vous pouvez éditer ce dessin (le dashboard est basé sur D3JS), pour ajouter / supprimer / modifier des éléments matériels à votre schéma.
* Si l'élément matériel que vous avez ajouté dans la topologie est détectable par isocaedron, par exemple s'il s'agit d'un serveur, ou d'une simple machine de dev, alors cet élément apparaîtra grsé tant qu'il n'est pas détecté.
* Lorsqu'il est détecté, il n'est plus grisé.
* Réciproquement, lorqsque `kytes-aerodyne` détecte un nouvel élément matériel, mais que vous ne l'aviez pas encore ajouté dans le schéma de la topologie, alors un nouvel élément matériel appraît automatiquement.
* Il vous appartient ensuite de renseigner différentes informations quant à ce nouvel élément, et à ajouter ses liens physiques avec les autres éléments de la toplogie.
* `kytes-aerodyne` vous permet de bootstraper une environnement eclispe complet pour développer une recette kickstart, pour chaque nouvel élément physique pour lequel le PXE booting est possible. Cela permet à `kytes-aerodyne` de proposer un DRP "bare-metal".


`kytes-aerodyne` fait automatiquement apparaître dans le schéma de la toplogie afficher (comme un noeud isolé, non relié à aucun élément) 

Pour chaque machine inventoriée, `kytes-aerodyne` vous propose de litégrer dans le schéma de la topologie de l'infrastructure
