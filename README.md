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

Les deux premières fonctions qui seront assurées par `isocahedron`, seront donc:
* l' "enrollement" des machines physiques.
* la gestion de l'inventaire des machines physiques.

Ces fonctions seront assurées par un composant nommé `isocahedron`, dont la première version reposera sur le fonctionnement d'un
composant JCA, encapsulé dans un conteneur docker embarquant une distribution Wildfly/JBossEAP minimale.

* Toutes les machines physiques doivent être au préalable configurées en PXE boot +  Wake On LAN (beaucoup plus confortable pour la conception de la configuration kickstart)
* `isocahedron` détecte une nouvelle machine physique dès sa séquence d'amorçage, à condition qu'elle soit dans le même réseau physique: connectée à la même interface physique routeur.
* `isocahedron` propose un dashboard comprenant un onglet "topologie de l'infrastructure": il s'agit d'un schéma que vous pouvez éditer, dans lequel vous pouvez représenter tous les éléments matériels de l'infrastructure à votre ddisposition. Vous pouvez éditer ce dessin (le dashboard est basé sur D3JS), pour ajouter / supprimer / modifier des éléments matériels à votre schéma.
* Si l'élément matériel que vous avez ajouté dans la topologie est détectable par isocaedron, par exemple s'il s'agit d'un serveur, ou d'une simple machine de dev, alors cet élément apparaîtra grsé tant qu'il n'est pas détecté.
* Lorsqu'il est détecté, il n'est plus grisé.
* Réciproquement, lorqsque `isocahedron` détecte un nouvel élément matériel, mais que vosu ne l'aviez pas encore représenté dans le schéma de la topologie, alors un nouvel élément matériel appraît automatiquement.
* Il vous appratient ensuite de renseigner différentes informatiosn quant à ce nouvel élément, et à ajouter ses liens physiques avec les autres éléments de la toplogie.
*  `isocahedron` vosu permet de bootstraper une environnement eclispe complet pour développer une recette kickstart
`isocahedron` détecte une nouvelle machine physique et l'invetorie sur la base d'un de ses ADRESSES MAC, et/ou device UUID.
`isocahedron` fait automatiquement apparaître dans le schéma de la toplogie afficher (comme un noeud isolé, non relié à aucun élément) 

Pour chaque machine inventoriée, `isocahedron` vous propose de litégrer dans le schéma de la topologie de l'infrastructure
