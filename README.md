# Information

This repo is under construction for the first release planned for May, the 1st of 2018.
First release code name will be "Hawking", as an aurevoir to the lately disappeared Stephen Hawking.

# Kytes

It's That I like going up in the air with the clouds, but I also like my feet right there on the ground, here.

Kytes is a software factory exprience, with full devops behavior, and a fullstack approach.

A full devops behavior: Kytes is designed for devops professionals, as a tool.
A fullstack approach: If it takes modifying a bootloader to make an application even better, let's make it possible as easily as an 'mvn update'
And What about pulling A linux kernel module into a Vert-x Java Pipeline?

This software factory project began March, 2018, and will be twin-develoed: From zero day on, Kyte will be implemented both in Java, and Scala language.
This "twin-implementation" is an experience to put design patterns under pressure of the following requirements:
* [Reactive Applications Requirements](https://www.reactivemanifesto.org)
* Ability to deploy to Kubernetes.
* Ability to deploy to Openstack (through heat).
* Ability to deploy using chef.io (release management of chef.io cookbooks, ansible playbooks).
<!-- * Ability to deploy to GCP. -->
<!-- * Ability to deploy to AWS. -->

Like in the car industry, they design a production line for a given car release (lets forget or bear in mind car options lists), Kytes isthere to 
assist you in designing, setting up, and operating production lines for projects, in an organization.

* Install Kytes on a machine, give Kytes hardware, then Kytes starts working for you.
* Once installed,  Only one user is created in Kytes: the property manager.
* You follow a security procedure to activate The initial property manager, which includes changing password before any operation.
* Then you use the initial property manager to create other property managers, or organisation accounts.
* Property managers may create organisations, and there is at least one pmo user created with each organisation. 
* The same user may be both Property manager and PMO, only a PMO, or only a Property Manager (that would be a sysadmin...). 
* Only a PMO user may spawn new production lines for an organization he belongs to. The same user maybe a PMO for several organozations.
* A PMO manages a production line, and may create developer users, and himself, is, a developer user, the PMO may also create an architect role, and himself is, an architect, but it's default, he can revoke from himself architect priviliges, to cease those to a dedicated architect user.
Just like today, office buildings are operated and split-rented to different companies, Kytes is forst a property management system:
the property management system for the infrastructures of all tenants in kytes.

 

# kytes-aerodyne
Une usine logicielle est un infrastructure IT.
Et comme toute infrastructure IT, elle se construit en commençant par le matériel.

Kytes aura la capacité à se déployer:
* à partir d'une infrastructure "bare-metal": à partir de machines "nues", n'ayant aucun OS installé.
* à partir d'une infrastructure provisionnée par une offre IAAS privée (Openstack, openshift, un simple petit VirutalBox installé sur un gros PC...), publique (GCP, AWS), ou hybride.

Dans les deux cas, l'infrastructure provisionnée au départ, devra être "enrollée".

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

# kytes-blown

* `kytes-blown` est un composoant qui permet de gérer des référentiels pour un ensemble de dépendances.
Considérons par exemple, Une ligne de production mis ene place et gérée par `Kytes`, pour un produit.
Cette ligne de production possède un "univers de dépendances", et dans cet univers, l'on a des dépendances utilisées:
 * pour la cible de déploiement de la ligne de production,
 * par l'application (des dépendances de l'applciation donc,
 * par l'un des composants de la ligne de production (un plugin maven, par exemple),
 
* `kytes-blown` fait usage de [Plup](https://pulpproject.org/), mais pas seulement, pour mettre en service et gérer le cycle de vie de repository linux, de repositories maven, de repository "docker-hub", de repository Scala
* `kytes-blown` fait usage de Jgit et Git, pour mettre en service et gérer le cycle de vie de repositories Git , un peu comme [`git-meta`](http://opensource.twosigma.com/git-meta/#1), masi un peu différemment...
# kytes-boutique

Vous permet de gérer la communication extérieure "on a per-product basis".
Une des fonctions basiques est la possibilité de gérer le site web du projet:
* [niveau application] comme une application web scala, en gérant son code source et son pipeline complet de développement
* [niveau comunication] comme une plateforme de communication, surlaquelle vous pouvez publier du contenu. Pour publier ce contenu, vous implémentez votre propre "Publisher", ou utilisez un des "Publisher" standards fournis avec la distribution de `kytes-boutique`.
Ces opérations à ces deux niveaux peuvent être automatisées, les contenus publiés formatés par templates, par
exemple chaque commit & push qui mentionne la résolution d'une "issue", occasionne un post automatique sur le
compte Twitter du projet et sur le compte twitter du développeur auteur du bugfix (et d'autres).

Une autre ensemble de fonctionnalités envisagé concerne la gestion des réseaux sociaux utilisés
comme canaux de communication publics pour le projet. Dans cet ensemble certaines fonctions permettront
d'analyser les données collectées sur les réseaux sociaux, et les autres permettront de publier via les
canaux de communication publics pour le projet.


##  Notes d'implémentation pour kytes-boutique
 
* fera usage de JGit et de la [REST API CLIENT HEROKU]:
      https://devcenter.heroku.com/articles/platform-api-quickstart
 
* Pour automatiser le process  des pipelines aboutissant chez Heroku.
 
* tentative plantée d'implémentation en Java que je peux regarder pour apprendre des erreurs: https://github.com/heroku/direct-to-heroku-client-java
 
* Note intéressante: avec cette REST API Heroku, je vais donc pouvoir interooger la "marketpplace Heroku", afin de proposer de l'autocomplétion de Procfile. Mais aussi je vais pouvoir vérifier, au déploiement, que les add-ons spécifiés dans le Procfile sont bien tous existants dans la marketplace heroku).
 
 
* Un process standard serait:
 * 1. (composants: ide-service-manager) On modifie le code source de l'application qui constitue le site web du projet							
 * 2. (composants: source-code-manager) On commit & push sur le repo de référence de versionning du code source de l'application				
 * 3. (composants: quality-manager) On exécute tous les tests statiques: ceux qui peuvent être exécutés sans exécution de l'application, comme des tests JUnit.
 * 4. (composants: packaging-manager) On build l'application site web
 * 5. (composants: deployment-manager) On déploie l'application site web dans la cible de déploiement. Le déploiement comprend un commit & push du code source des opérations de déploiement, pour respecter le principe Infrastructure as code. Le code source des opérations de déploiements peut par exemple être constitués de scripts `/bin/bash`. Enfin, ce code source des oppérations de déploieemnts a des dépendances, comme le répertoire `stage` Scala, et ces dépendances, qui peuvent être binaires, sont déployées et disponibles dans `kyte-blown`
 * 6. (composants: quality-manager) On exécute tous les tests à l'exécution: Ce sont les tests qui nécessitent un déploiement de l'application dans une cible de déploiement, comme les tests d'intégration, ou les UAT.
   
   
 
* Doc de la REST API Heroku: https://devcenter.heroku.com/articles/platform-api-quickstart 


## Un squelette d'implémentation

