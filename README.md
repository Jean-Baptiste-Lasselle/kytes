# Information

This repo is under construction for the first release scheduled May, the 1st of 2018.
First release code name will be "Hawking", as an aurevoir to the lately disappeared Stephen Hawking.

# Kytes

It's That I like going up in the air with the clouds, but I also like my feet right there on the ground.

Kytes aims at making you able draw all you can from the machines that you've got (until the boss answers yes for more pods on GCP),  while what
you're doing on that infrastructure is developing / managing lifecycle of an application, on behalf of an organization.

Kytes orginated because I wanted real full bare metal Backup Restore procedure at home, for my personal projects.
Meaning I wanted:
* a one-clic backup procedure on a running Kytes instance.
* a one-clic, bare-metal restore procedure to a brand new hardware machine.
* hardware dependency management:  Within the scope of dependency management, Kytes will offer same features, whether the dependency relation is between two hardware dependencies (to devices), or between a hardware dependency and a software dependency..
* and hardware inventory management with obsolescence and tco monitoring (aka wife's the ultimate ruthless boss, and wants to know how much all that really costs).


Kytes is a software factory exprience, with full devops behavior, and a fullstack approach.
A full devops behavior: Kytes is designed for devops professionals, as a tool.
A fullstack approach: If it takes modifying a bootloader to make an application even better, let's make it possible as easily as an 'mvn update'. 
And What about pulling A linux kernel module into a Vert-x Java Pipeline?

This software factory project began March, 2018, and will be implemented both in Java, and Scala language.
This "twin-implementation" is an experience to put design patterns under pressure of the following requirements:
* [Reactive Applications Requirements](https://www.reactivemanifesto.org)
* Ability to deploy to Kubernetes.
* Ability to deploy to Openstack (through heat).
* Ability to deploy using well know tools like chef.io and ansible (release management of chef.io cookbooks, ansible playbooks).
<!-- * Ability to deploy to GCP. -->
<!-- * Ability to deploy to AWS. -->

Like in the car industry, they design a production line for a given car release (lets forget or bear in mind car options lists), Kytes is there to 
assist you in designing, setting up, and operating production lines for projects, in an organization.
Kytes' production lines are [`kytes-pipeline`](#kytes-pipelines)

* Install Kytes on a machine, give Kytes hardware, then Kytes starts working for you.
* Once installed,  Only one user is created in Kytes: that user is both `top-manager` user and `property manager` user. 
* Only one user may be `top-manager` user, and that `top-manager` user may delegate `property manager` role to another user.
* You follow a security procedure to activate The initial property manager, which includes setting new password before any operation.
* Then you use the initial property manager to create other users, like `property manager` users, pmos, architects, developers, or organization.
* Property managers may create organizations, and there is one default pmo user created with each organization. 
* You create an organization as a property manager, and you do that to work on an software and provide your deliveries to that organization.
* With the default PMO user created with the new organization, you then create a new production line. That new production line delivers to an organization. Kytes therefore considers organizations as customers of the `property-manager`.
* and a only a property manager may replace current PMO of a production line, with a new PMO user.
* The same user may be both Property manager and PMO, only a PMO, or only a Property Manager (that would be a ceo, or a business unit manager). 
* Only a PMO user may spawn new production lines for an organization he works for. The same user maybe a PMO for several production lines of organizations.
* A PMO manages a production line, and may create developer users, and himself, is, a developer user, the PMO may also create an architect role, and himself is, an architect, but it's default, he can revoke from himself architect priviliges, to cease those to a dedicated architect user.
Just like today, office buildings are operated and split-rented to different companies, Kytes is forst a property management system:
the property management system for the infrastructures of all tenants in kytes.

 
# Kytes Ground Control

##  Kytes Ground Control
`kytes-ground-control` is responsible for authentication & access control in Kytes.
Kytes Ground Control exposes its features through a Web GUi, and a RESTful API.
 It consists of a web GUI, and a command line client, and Ground Control itself.
When any user realises an action, he has to be authenticated and granted authorization by Ground Control.
Ground Control is in charge of Identity management and Access Control.

##  Kytes Ground Control's client

Kytes Ground control comes with a client called `kytes-cli`, which is just a command line client for the Kytes Ground Control 's RESTful API.
`kytes-cli`, works pretty much like the Heroku client, meaning you can use it, starting by authenticating, and
then you can command line any command that Ground Control gives you access to: manage your pipelines, applications development production lines, etc... It is called the 
Kytes Ground Control Client, or Ground Control Client, or Kytes client, as you wish.
Ground Control Exposes a RESTful API with which you can execute any combination of commands you may execute with the Kytes Ground Control Client.

Kytes Ground Control's client authentication method may be configured in Kytes configuration, and 
will support integration with Linux PAM (is there a Windows PAM somewhere...?), OAuth2, SAML, and 2/3 other popular and robust authentication methods.

 
# kytes-property-manager


`kytes-property-manager` is Kytes component responsible for managing Kytes' own infrastructure:
 * You install Kytes on a small machine,
 * You start Kytes, it is said to be on bootstrap state. In that state, you cannot start using Kytes, it needs an infrastructure (a physical) to play with.
 * You give Kytes an infrastructure to play with (I'll explain how to do that). That infrastructure might be reduced to the initial machine you installed Kytes on.
 * then Kytes uses that infrastructure to fully scale out to the entire infrastructure,
 * and now Kytes changes state from bootstrap to operational, and you can start using Kytes to fullstack-manage softwares for an organization.


## kytes-aerodyne

A software factory, and even more a solution to manage software factories, sits on a hardware infrastructure.
From another completely different point of view, hardware can be a direct dependency of a piece of software.
In the below documentation for Kytes, I use a small specific terminology:
* I call here below a "dependency", anything you might call a piece of software, whether it be A U-boot version, A Linux Kernel Module, or a Java Vert-X component.
* Let `chantilly`, be such a piece of software: I consider `chantilly` is a dependency of itself: `chantilly` is a dependency of `chantilly`, for indeed, you need `chantilly` to deploy `chantilly`.
* Let `chantilly`, be a dependency: I say a dependency of `chantilly` is of degree zero, if it is directly referenced (mentioned) in the dependency list of `chantilly`, and cannot be infered from another dependency mentioned in the same list.
* Let `chantilly`, be a dependency: For every positive & not null integer K, I say a dependency `D` of `chantilly` is of degree K + 1, if and only if `D` is a dependency of degree zero of dependency of degree K of `chantilly`. 
* Let `chantilly`, be a dependency: The dependencies of degree zero of `chantilly` are:
 * `chantilly` 's own source code,
 * `chantilly` deployments targets provisioning recipes,
 * `chantilly` deployment recipes
 
Piece of cake, ain't it?

Well, from that kind 
 

`kytes-aerodyne` is Kytes component responsible for managing Kytes' own infrastructure:
 * You install Kytes on a small machine,
 
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

Pour chaque machine inventoriée, `kytes-aerodyne` vous propose de l'intégrer dans le schéma de la topologie de l'infrastructure

<!--
## kytes-iaas-manager

`kytes-iaas-manager` is responsible for setting up (provisioning) the `kytes-iaas-provider` based on configuration.
`kytes-iaas-manager` is also responsible for oprating the `kytes-iaas-provider`:
* managing all `kytes-iaas-provider` lifecycle :
 * updates,
 * upgrades,
 * security,
 * DRP (with automatic backups scheduling, and automatic restore procedures),
 * managing users (CRUD opeartions on users)
 
All in all, `kytes-iaas-manager` does infrastructure management, Kytes' own infrastructure management, which why it is part of `kytes-property-manager`

-->

# kytes-iaas

Une fois que Kytes a pris le contrôle de l'infrastructure physique que vous avez mis à sa disposition, `kytes-iaas` met une offre IAAS
à la disposition des aux autres composants Kytes:

À chaque fois qu'une demande de provisionning d'une infrastructure est émise par un composant Kytes, c'est `kytes-iaas` qui répondra à la demande.
Ce sera par exemple le cas, lorsqu'une cible de déploiement sera conçue et construite pour une ligne de production, ou lorsque Kytes provisionera
des serveurs JMeter Jenkins, etc.. pour faire les builds au sein d'un pipeline


## kytes-iaas providers

`kytes-iaas` acts with one IAAS provider. That provider may use hybrid cloud behind the scene, but it's still a one unique IAAS provider.
With this logic in mind, `kytes-iaas` will be implemented so as to provide a unified IAAS RESTful API thats uses multiple IAAS providers

A `kytes-iaas` provider is a component that will offer IAAS service to all other components
Kytes will provide a small implementation of a IAAS provider, but you may as well set a third party IAAS solution as a `kytes-iaas` provider:
* A Vagrant installation
* An Openstack Installation
* An Openstack Installation with Kubernetes inside a tenant
* A Kubernetes Installation inside a couple of dumb VirutalBox VMs
Pluging in IAAS providers like that makes the `kytes-iaas` provider an "API adapter": it will be implemented as such, translating the third party orchestration API into the `kytes-iaas-api` exposed to other Kytes componentsd
That way other Kytes components, are not aware of the IAAS provider computing down there.

# kytes-provisioner

Ce composant peut-être "pluggué"; d'habitude, je "plug" Ansible.

`kytes-provisioner` is there to realise all provisioning operations on infrastructures provvided by [`kytes-iaas`](#kytes-iaas)
I may have fun implementing that myself, but basically what I want to do with `kytes-provisioner`, is exactly what [ansible](http://docs.ansible.com/ansible) or [chef.io](https://www.chef.io/) can do, really well.
So What I'll start with implementing Kytes so has to be able to define a chef.io or ansible installation, as a provisioning provider for `kytes-provisioner`.
You may plug all chef.io, ansible, and my own implementations, as provisioning providers to provide fullstack provisioning capability.
And you may write recipes for chef.io, ansible and other provisioning tools to publish as deployment assets offered to your application users.

# kytes-pipelines

As Kytes pipelines are polyglote by design, and all the below listed pipeline components are polyglotes by design.
Kytes wants a developer to be able to feel he's still on the same project, while he jumps
from one dependency, to another, starting from a root project.* (the rpoject he 's working on).

By Jumping from one dependency, to another, Kytes means:
* automatic loading of the source code of the dependency into an ide-project inside your IDE (like importing maven projects inside eclipse), without restart, 
* automatic loading of all IDE tooling to switch to a "language-oriented IDE perspective" : meaning Kytes re-confgures your IDE so that you have programming language specific IDE capabilities, according the dependency' programming language. For example, you have automatic grammar checks with error higlighting and fix tips, code snippets management, source code files format management, smart-auto-completion, refactoring, searching the source code capabilities.
* automatic creation of a kytes pipeline for the dependency if the dependency has not yet one inside Kytes:

          You're using Kytes, so your developing at least one application. Let's call `chantilly`, that application.
          You're developing `chantilly` in Kytes, so you're doing that with at least one kytes pipeline.
          Since any Kytes pipeline has a "deployment target provisioning recipe", then, for any dependency of `chantilly`, there exists in Kytes at least
          one provisioning recipe, that can deploy that dependency: the "deployment target provisioning recipe" of the pipeline you use for `chantilly`.

As long as the developer has not "jumped" to a given dependency, there already exists a pipeline for that dependency, but it has no source code management, meaning it contains only "deployment recipe" and "deployment target provisioning recipe" for the dependency.
Plus this default pipeline is idle, meaning the "deployment recipe" and the "deployment target provisioning recipe" only are pointers to the "deployment recipe" and the "deployment target provisioning recipe" of  another pipeline, in which the dependency is used.
When you jump on the dependency, you load the whole pipeline including:

* [`application source code`], used by [`kytes-pipeline-ide`](##kytes-pipeline-ide), and owned by [the scm service](##kytes-pipeline-scm)
* [`build recipe`], used and owned by [`kytes-pipeline-packager`](##kytes-pipeline-packager)
* [`deployment target provisioning recipe`], (used and owned by [`kytes-iaas`](#kytes-iaas)) (utilisée et gérée par [`kytes-iaas`](#kytes-iaas))
* ["deployment recipe"], (used and owned by [`kytes-provisioner`](#kytes-provisioner) (utilisée et gérée par [`kytes-provisioner`](#kytes-provisioner))

In a Kytes pipeline, the git repo used for source code versionning management is called the dependency' source code versionning referential. ( le référentiel de versionning du code source de l'application).

* 

## kytes-pipeline-ide

The Kytes clients exists as a maven plugin, and a m2e extension to use the Kytes plugin within eclipse.

## kytes-pipeline-scm
## kytes-pipeline-qa
This guy can run tests and analysis with Fossology, Checkstyle, JMeter, Jenkins, Junit (and al friends and cousins mockitos), Netflix' Simian army, with full metrics reporting management.
He spawns you a quality manager for each of your product lines.
He:
* spawns all the qa tools (servers like Jenkins, JMeter, ...)
* runs the test against the soure code of your application.
* aggregates, persists and process tests results, and releases an end Quality Assurance reporting, based on computed test results data.
* Any user with `qa` role on a production line, may also load the production line Quality Assurance Book, which contains every thing that affects Quality Assurance for the production line.
  In the Quality Assurance Book, you may find (edit and publish to [`kytes-beamer`](#kytes-beamer)) stuff like:
  * JUnit tests (a java projects source code),
  * Jenkins files, 
  * provision recipe for the test deployment targets (which is a test parameter for load testing your application),
  * provision recipe for all the qa tools which will run and compute the tests. This includes purchasing servers, containers, or kubern8s service at `kytes-iaas`, for qa tools provisioning 
  * definition, configuration, and versionning of the metrics used to asses quality of your application.  At every Build, Metrics set configuration is commited & pushed to a git repo standing for Quality management versionning. Imagine there configuration scripts and custom modules for your private elastic search installation...
## kytes-pipeline-packager
This service does all the packaging work.
any pafckaging artefact is published to `kytes-beamer`, on a proper repository ( a private docker hub, a maven repository such as artifactory)
## kytes-pipeline-deployer
This service does all the application's deployment work.
De plus lorsqu'un développeur fullstack voudra changer la recette de provisionning d'une cible de déploiement, ou en créer une nouvelle, 
## kytes-pipeline-deployment-target-manager
The above listed features are those of the `kytes-pipeline-deployment-target-manager`, but also happen to
be the `kytes-iaas-api` main features:
	### it can spawn the deployment target
	This service asks for, and gets an infrastructure from [`kytes-iaas`](#kytes-iaas), and then applies [`deployment target provisioning recipe`] on that infrastructure.
	When finished with that work the deployment target of the pipeline is ready to receive deployments.
	### it can monitor the pipeline's running deployment target, offering:

	 - Monitoring from system to business level with things like SLF4J / Logstash / Kibana 
	 - Visualization of monitoring data on the main Kytes PMO/Architect/developer dashboards, 
	 - Possibility to stream all monitoring data flow to an external monitoring system. (with log routing techniques)
	### it can snpashot/restore states of the deployment target
	such as what you can do with glance in openstack

Just imagine all those tasks today, described in yuir project's pom.xml file:
Imagine that the kytes-pipeline takes your big pom.xml (or parent pom.xml, with children pom.xml's), and copies it to 25 different Docker containers (or Kubernetes services)
Then imagine every one of those 25 guys, do each one of the tasks discribed in your huge pom.xml.
It's how Kytes builds up its pipelines, making them scalable: You can easily with just a server or two, power a pipeline with the work of thousands of containers...
With this principle of turning a pipeline into a micro-service bouquet, Kytes makes you well think your build process, from a fullstack point of view:


Kytes lets you jump on any dependency of your app, regardless of which recipe this dependency is deployed with.
The main mentioned recipes are [`deployment target provisioning recipe`], or with the [`deployment recipe`].
<!--
Those two recipes may be split into sub-recipes, and when such a split is conducted, it results in either a paralell, or 
sequential execution. Any execution  whether it be paralell or sequential, begins with an input, and ends with an output.
Thus, when splitting a recipe, you split into chained executions, each execution being either paralell, or sequential.
-->
Kytes will offer simple and very handy GUI tools (and Kytes Ground Control API equivalent features) to split 
recipes into subrecipes, so as to obtain a micro-service definition.




# kytes-beamer

* `kytes-beamer` est un composoant qui permet de gérer des référentiels pour un ensemble de dépendances.
* Dans `kytes-beamer` toute  dépendance a (2 + N + P)  référentiels:
  * (1 référentiel)  le référentiel de versionning de son code source,
  * (1 référentiel)  le référentiel de toutes ses releases (ce sont donc des binaires), les releases poubvant être classées et gérées par périmètres (on a toujours un périmètre local lorsque l'on se fait une eptite release pour juste test à un niveau local, puis on a le périmètre  projet, pour tous les développeurs sur el projet,puis le périmètre organization, pour tous les projets de l'organization, pusi au-dessus le niveau utuilsateur, qui veut utuliser un même référentiel de bibliothèques pour toutes les organizations pourt lesquelles il travaille)
  * (N référentiels) le référentiel de chacune de ses recettes de provision d'une cible de déploiement, 
  * (P référentiels) le référentiel de versionning de chacune de ses recettes de déploiements. Chaque recette de déploiement est associée à une version d'une recette de provision d'une cible de déploiement,
 
Considérons par exemple une ligne de production mise en place et gérée par `Kytes`, pour un produit.

Cette ligne de production possède un "univers de dépendances", et dans cet univers, l'on a des dépendances utilisées:
  * par la cible de déploiement de la ligne de production,
  * par l'application (des dépendances de l'applciation donc),
  * par l'un des composants de la ligne de production (un plugin maven, par exemple),

* `kytes-beamer` fait usage de [Plup](https://pulpproject.org/), mais pas seulement, pour mettre en service et gérer le cycle de vie de repository linux, de repositories maven, de repository "docker-hub", de repository Scala
* `kytes-beamer` fait usage de Jgit et Git, pour mettre en service et gérer le cycle de vie de repositories Git , un peu comme [`git-meta`](http://opensource.twosigma.com/git-meta/#1), masi un peu différemment...

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
<!--
* tentative plantée d'implémentation en Java que je peux regarder pour apprendre des erreurs: https://github.com/heroku/direct-to-heroku-client-java
 -->
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

```

#!/bin/bash
############################################################
############################################################
# 					Compatibilité système		 		   #
############################################################
############################################################

# ----------------------------------------------------------
# [Pour Comparer votre version d'OS à
#  celles mentionnées ci-dessous]
# 
# ¤ distributions Ubuntu:
#		lsb_release -a
#
# ¤ distributions CentOS:
# 		cat /etc/redhat-release
# 
# 
# ----------------------------------------------------------

# ----------------------------------------------------------
# testé pour:
# 
# 
# 
# 
# ----------------------------------------------------------
# (Ubuntu)
# ----------------------------------------------------------
# 
# ¤ [TEST-KO]
#
# 	[Distribution ID: 	Ubuntu]
# 	[Description: 		Ubuntu 16.04 LTS]
# 	[Release: 			16.04]
# 	[codename:			xenial]
# 
# 
# 
# 
# 
# 
# ----------------------------------------------------------
# (CentOS)
# ----------------------------------------------------------
# 
# 
# 
# ...
# ----------------------------------------------------------


############################################################
# -- https://devcenter.heroku.com/articles/getting-started-with-scala
############################################################
# à partir de la ligne suivante, toute ligne qui commence
# par "# ", est une commadne linux exécutable si onla dé-commente.
############################################################
############################################################
############################################################
# -- 			environnement des opérations			 --#
############################################################
############################################################
export NOM_APPLICATION_HEROKU=kytes-public-pr-endpoint
export NOM_FICHIER_APPLICATION_PACKAGEE=$NOM_APPLICATION_HEROKU
# -- =============>>>>>>>> Ce script prend en premier argument:
# -- la liste des arguments à passer à l'exécution de
# -- l'application scala déployée.
# -- Les arguments ainsi passés ne doivent pas être paramétrés
# -- par l'environnement Heroku, comme par exemple:
# -- 	-Dhttp.port=${PORT}   =>   c'est une variable propre aux environnements Heroku

export LISTE_ARGUMENTS_EXECUTION_SCALA_APP=""
# les paramèteres que je peux passer en argument de ce script 
export LISTE_ARGUMENTS_EXECUTION_SCALA_APP_SANS_PARAMETRES_HEROKU=""
for i in {0..$#}
do
    LISTE_ARGUMENTS_EXECUTION_SCALA_APP_SANS_PARAMETRES_HEROKU=$LISTE_ARGUMENTS_EXECUTION_SCALA_APP_SANS_PARAMETRES_HEROKU" $i"
done
# -- les paramètres que je suis préfère passer en dur dans le
# -- code source de cette recette, quelle qu'en soit la raison.
export LISTE_ARGUMENTS_EXECUTION_SCALA_APP_AVEC_PARAMETRES_HEROKU="-Dhttp.port=${PORT} -Ddb.default.url=${DATABASE_URL}"
LISTE_ARGUMENTS_EXECUTION_SCALA_APP=$LISTE_ARGUMENTS_EXECUTION_SCALA_APP_SANS_PARAMETRES_HEROKU" "$LISTE_ARGUMENTS_EXECUTION_SCALA_APP_AVEC_PARAMETRES_HEROKU

export TIMESTAMPUNIQUE=$(date +\"%d-%m-%Y-%HHeures%Mmin%SSec\")
export OPERATIONS_HOME=$HOME/heroku-production/ops/$TIMESTAMPUNIQUE
export REPERTOIRE_OP_GIT=$OPERATIONS_HOME/source-initial
export REPERTOIRE_OP_SUR_CODE_SRC=$OPERATIONS_HOME/manips-code-source
# export REPERTOIRE_DEPLOIEMENT_APP_SCALA='$HOME/kytes-public-relations'
export URI_REPO_CODE_SOURCE=https://github.com/Jean-Baptiste-Lasselle/siteweb-usinelogicielle.com
# mkdir -p $OPERATIONS_HOME
mkdir -p $REPERTOIRE_OP_GIT
mkdir -p $REPERTOIRE_OP_SUR_CODE_SRC


# -- 
# -- Pour le cas où je souhaite que le client Heroku 
# -- utilise un proxy HTTP ou HTTPS 
# -- 
# export HTTP_PROXY=http://adresseIPdeMONproxyHTTP:portnumber
# export HTTPS_PROXY=http://adresseIPdeMONproxyHTTPS:portnumber

############################################################
############################################################
# --    			exécution des opérations		    -- #
############################################################
############################################################
# 
# -- Il s'agit de d'automatiser les opérations standard du
# -- cycle de développement d'une application de type scala website,
#
# -- Avec cette automatisation, je créérai un nouveau module Kytes: `kytes-pr`
# -- Lorsque l'on gère le cyle de vie d'une application avec kytes, dans
# -- la ligne de production, `kytes-pr` permet d'automatiser la gestion
# -- des publications du site web publié pour communiquer sur l'application
# 
# -- Kytes utilsiera `kytes-pr` pour gérer les comunications publiées sur le site web du projet https://kytes.io
# 
# -- 
# -- le client Heroku fait usage de Git
# -- 
# -- Installation Git
PKG_OK=$(dpkg-query -W --showformat='${Status}\n' git |grep "install ok installed")
if [ "" == "$PKG_OK" ]; then
   echo "Installing git..."
   sudo apt-get git
   clear
else
   echo "Git is already installed"
fi
echo "Proceeding with operations flow..."
# -- installation du client heroku
wget -qO- https://cli-assets.heroku.com/install-ubuntu.sh
chmod +x ./install-ubuntu.sh
 ./install-ubuntu.sh
 
# -- authentification interactive
heroku login

############################# INITIALISATION PROJET
############################# INITIALISATION PROJET
############################# INITIALISATION PROJET
############################# INITIALISATION PROJET
############################# 
############################# Il faut créer le projet Heroku, et faire un premier déploiement du code source importé du repo Git "$URI_REPO_CODE_SOURCE"
############################# 
############################# 
# -- récupération initiale code source application
git clone "$URI_REPO_CODE_SOURCE" $REPERTOIRE_OP_GIT

# -- on travaillera sur une copie de la version récupérée, on
# -- ne modifie pas directement la version récupérée initialement.
cp -rf $REPERTOIRE_OP_GIT/* $REPERTOIRE_OP_SUR_CODE_SRC

cd $REPERTOIRE_OP_SUR_CODE_SRC
# -- 
# -- On doit "créer un projet heroku", qui
# -- représente notre application, chez Heroku, dans notre compte.
# -- On peut donc certainement créer plusieurs projets pour un même compte Heroku.
# -- 
# -- La commande `heroku-create` génère un nom randomisé pour l'application, mais
# -- on peut fixer ce nom en le passant en paramètre de la commande `heroku create`
heroku create $NOM_APPLICATION_HEROKU

# -- 
# J'ajoute un fichier Procfile en me débarassant de l'éventuel existant.
# -- 
rm -f ./Procfile
echo "# kytes public relations' endpoint deployment procedure." >> ./Procfile
# le Procfile a une syntaxe spécifique, je ne peux utiliser les commandes /bin/bash
echo "# kytes public relations' endpoint ne nécessite qu'un seul process (dyno), de type web: c'est un site web vitrine du projet" >> ./Procfile
echo "web: target/universal/stage/bin/$NOM_FICHIER_APPLICATION_PACKAGEE $LISTE_ARGUMENTS_EXECUTION_SCALA_APP" >> ./Procfile
# echo "web: target/universal/stage/bin/software-factory -Dhttp.port=${PORT} -Dplay.evolutions.db.default.autoApply=true -Ddb.default.driver=org.postgresql.Driver -Ddb.default.url=${DATABASE_URL}" >> ./Procfile
# echo "console: target/universal/stage/bin/play-getting-started -main scala.tools.nsc.MainGenericRunner -usejavacp" >> ./Procfile

# -- version scriptée /bin/bash, dépréciée pour Heroku
# echo "rm -rf -p $REPERTOIRE_DEPLOIEMENT_APP_SCALA" >> ./Procfile
# echo "mkdir -p $REPERTOIRE_DEPLOIEMENT_APP_SCALA" >> ./Procfile
# echo "# package" >> ./Procfile
# echo "sbt dist" >> ./Procfile
# echo "cp -rf ./target/universal/stage/* $REPERTOIRE_DEPLOIEMENT_APP_SCALA" >> ./Procfile
# echo "# run" >> ./Procfile
# echo "$REPERTOIRE_DEPLOIEMENT_APP_SCALA/bin/$NOM_FICHIER_APPLICATION_PACKAGEE $LISTE_ARGUMENTS_EXECUTION_SCALA_APP" >> ./Procfile




# -- Là en fait j'ai un problème: comment faire pour ajouter ce nouveau fichier dans le remote  
git add Procfile
git commit -m 'Ajout du Procfile Heroku, par `kytes-pr`, pour définir la procédure de déploiement de l application dans instance Heroku '
git tag deploiement-initial-$NOM_APPLICATION_HEROKU-$TIMESTAMPUNIQUE -m "deploiement-initial-[$NOM_APPLICATION_HEROKU]-[$TIMESTAMPUNIQUE] L'application déployée est exactement la dernière versiond ela branche master dans le repo git [$URI_REPO_CODE_SOURCE] "
# -- es-ce que ça fera le commit & push vers [$URI_REPO_CODE_SOURCE]? TODO: à vérifier.
git push master && git push --tags master
# -- Et maintneant, on peut déployer l'application UNE PREMIERE FOIS chez Heroku
git push heroku master && git push --tags heroku master



# - exemple de sortie standard de cette commande:
# -- Creating nameless-lake-8055 in organization heroku... done, stack is cedar-14
# -- http://nameless-lake-8055.herokuapp.com/ | https://git.heroku.com/nameless-lake-8055.git
# -- Git remote heroku added

# -- La commande `heroku-create` créée un repo git remote dans les infrastructures Heroku.
# -- et ce remote git repo est automatiquement associé au repo git local trouvé dans  $REPERTOIRE_OP_SUR_CODE_SRC :
# -- Donc, après la commande  `heroku-create`, le remote origin n'est plus [$URI_REPO_CODE_SOURCE], mais [le git remote "heroku" créé dans l'infrastructure Heroku, par la commande `heroku-create`]


# ##############  EDITER LE CODE SOURCE DE L'APPLICATION
# -- Pour préciser à Heroku les commandes à exécuter au déploiement de l'application, on


# ##############  EDITER LE ./build.sbt && ./project/plugins.sbt
# -- J'y ajoute les dépendances nécessaires pour le plugin [sbt-native-packager]
echo ' ' >> ./project/plugins.sbt
echo 'addSbtPlugin("com.typesafe.sbt" % "sbt-native-packager" % "1.3.2")' >> ./project/plugins.sbt

# -- Là en fait j'ai un problème: comment faire pour ajouter ce nouveau fichier dans le remote  
git add ./build.sbt && git add ./project/plugins.sbt
# git commit -m "Modification des fichiers ./build.sbt && git ./project/plugins.sbt, par `kytes-pr`, pour définir la procédure de build de l'application "
# git tag build-$NOM_APPLICATION_HEROKU-$TIMESTAMPUNIQUE -m "build-[$NOM_APPLICATION_HEROKU]-[$TIMESTAMPUNIQUE] Modification des fichiers build.sbt et ./project/plugins.sbt, par [kytes-pr], pour définir la procédure de build  de l'application [$NOM_APPLICATION_HEROKU]"
# -- Et maintneant, on peut builder l'application en une seule commande
sbt dist

# ##############  PROCFILE
# -- Pour préciser à Heroku les commandes à exécuter au déploiement de l'application, on
# -- doit les spécifier dans un ficheir de nom "Procfile", à la racine du
# -- projet git dans lequel on a fait le `heroku login`

rm -f ./Procfile
echo "# kytes public relations' endpoint deployment procedure." >> ./Procfile
# -- le Procfile a une syntaxe spécifique, je ne peux utiliser les commandes /bin/bash
echo "# kytes public relations' endpoint ne nécessite qu'un seul process (dyno), de type web: c'est un site web vitrine du projet" >> ./Procfile


echo "web: target/universal/stage/bin/$NOM_FICHIER_APPLICATION_PACKAGEE $LISTE_ARGUMENTS_EXECUTION_SCALA_APP" >> ./Procfile
# echo "web: target/universal/stage/bin/software-factory -Dhttp.port=${PORT} -Dplay.evolutions.db.default.autoApply=true -Ddb.default.driver=org.postgresql.Driver -Ddb.default.url=${DATABASE_URL}" >> ./Procfile
# echo "console: target/universal/stage/bin/play-getting-started -main scala.tools.nsc.MainGenericRunner -usejavacp" >> ./Procfile

# -- version scriptée /bin/bash, dépréciée pour Heroku
# echo "rm -rf -p $REPERTOIRE_DEPLOIEMENT_APP_SCALA" >> ./Procfile
# echo "mkdir -p $REPERTOIRE_DEPLOIEMENT_APP_SCALA" >> ./Procfile
# echo "# package" >> ./Procfile
# echo "sbt dist" >> ./Procfile
# echo "cp -rf ./target/universal/stage/* $REPERTOIRE_DEPLOIEMENT_APP_SCALA" >> ./Procfile
# echo "# run" >> ./Procfile
# echo "$REPERTOIRE_DEPLOIEMENT_APP_SCALA/bin/$NOM_FICHIER_APPLICATION_PACKAGEE $LISTE_ARGUMENTS_EXECUTION_SCALA_APP" >> ./Procfile



# ##############  RE-DEPLOIEMENT
# -- on met à jour le timestamp
TIMESTAMPUNIQUE=$(date +\"%d-%m-%Y-%HHeures%Mmin%SSec\")
# -- 
# -- Je versionne les fichiers modifiés
git add Procfile ./build.sbt ./project/plugins.sbt */* */*.*
git commit -m 'Ajout du Procfile Heroku, par `kytes-pr`, pour définir la procédure de déploiement de l application dans instance Heroku '
git tag deploiement-$NOM_APPLICATION_HEROKU-$TIMESTAMPUNIQUE -m "deploiement-[$NOM_APPLICATION_HEROKU]-[$TIMESTAMPUNIQUE] Fichiers de configuration de build modifiés:[] Procfile Heroku, par [kytes-pr], pour définir la procédure de déploiement de l'application dans l'instance Heroku "
# -- Et maintneant, on peut déployer l'application en une seule commande
git push heroku master && git push --tags heroku master
# -- es-ce que le git tag va être pris en compte? TODO ==>> à vérifier dans les tests.
# -- Conclusion: on n'a a aucun moment précisé d'adresse IP de nom de domaine pour une cible de déploiement, 

# -- La commande `heroku open` permet d'accéder directement à l'applciation (sans connaître d'URL).
# heroku open





# ##############  SCALE UP/DOWN
# -- Aficher le statut des "dynos" (unité de scale up chez Heroku)
heroku ps
# -- Il n'y a aucun service (0 "dynos"), je dois obtenir une erreur avec `heroku open`
heroku ps:scale web=0
# -- Je fais un premier scale up: Il y a un service (1 "dynos"), je dois obtenir une réponse OK de mon application Scala avec `heroku open`
heroku ps:scale web=1









# ##############  LOGGING
# -- La commande `heroku logs --tail` permet de rediriger le flux des logs de l'application en
# -- cours d'exécution (dans l'infrastructure Heroku) vers la sortie standard de cette machine:
# heroku logs --tail
# -- Pour réaliser cette redirection de logs, le client Heroku utilise [l'API Logplex](https://github.com/heroku/logplex)
# -- TODO: Dans kytes, permettre la supervision d'une l'application déployée chez Heroku, en utilisant l'API logplex, comme le client, et en faisant de l'output de cube-logplex sur Kibana
# -- TODO: Dans Kytes, faire en sorte que les cible de déploiement puissent être supervisées par une alternative de cube-logplex (avec analyse "time-series", et routeur distribué de logs). [Les meileurs packages de logging que j'ai vu, c'est du Logstash / Kibana, avec analyses en times series par un moteur affublé de capacité de machine-learning. ça ne devrait pas être très difficile à remonter.]
# -- Première alternative à essayer: ELK http://linuxfr.org/news/gestion-des-logs-avec-logstash-elasticsearch-kibana + https://logz.io/learn/complete-guide-elk-stack/

# -- La commande `heroku logs --tail` comprend plusieurs options intéressantes:
# -- pour visualiser les logs de l'application uniquement
# heroku logs --tail --source app
# -- pour visualiser les logs système uniquement
# heroku logs --tail --source heroku
# -- pour leslogs de l'API Heroku (utilisée par le client):
# -- permet notamment de superviser l'activité de tous les
# -- développeurs sur cette instance de projet Heroku.
# heroku logs --tail --source app --dyno api


# -- Heroku offre des services additionnels payants pour le logging, et chacun de ces
# -- services (payants?) peut être utilisés avec des options spécifiques et
# -- documentées pour chaque service.
# heroku logs --tail autres_options_specifiques_a_chaque_service_additionnel
# -- >>>>> les services offerts sont du genre Logstash / Kibana. // 


# ##############  ONE-OFF DYNO : pour exécuter des commandes dans le conteneur Heroku
# -- You can run a command, typically scripts and applications that are
# -- part of your app, in a one-off dyno using the heroku run command.
# -- It can also be used to launch a console process attached to your local terminal for
# -- experimenting in your app’s environment, or code that you deployed with your application:
# heroku run console


# ##############  TODO: voir les "config vars" ... pas sûr que ce me soit très utile, dans la mesure où il faut modifier le code source.
# -- https://devcenter.heroku.com/articles/getting-started-with-scala#define-config-vars
# -- =>> sert notamment pour paramétrer l'application pourles différentes cibles de déploiement: dev, integration preprod, prod
# -- affiche toutes les varibles de la configuration
# heroku config
# -- permet de définir une variable dans la configuration, et de fixer sa valeur
# heroku config:set NOM_DE_MA_VARIABLE=asie
# -- permet de supprimer la définition d'une variable dans la configuration
# heroku config:unset NOM_DE_MA_VARIABLE
# -- permet d'obtenir la valeur d'une variable particulière.
# heroku config:get NOM_DE_MA_VARIABLE
# -- >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>> OK LES VARIABLES UTILISEES DANS LE Procfile  SONT CELLES DISPONIBLES DANS CETTE CONFIGURATION


# ##############  ADD-ONS : 
# -- Okay, donc en fait la notion de "add-on" Heroku, c'est pour rajouter des dépendances à la cible de déplooiement Heroku.
# -- Par exemple, il faut ajouter un add-on, pour pouvoir utilsier une BDD, ou un service Logstash, dans un cible de déploiement Heroku..
# -- Il y a donc des petites notions de packaging à mettre au clair pour les addons (dans quel(s) ficheir(s) de configuration précise-t-on les add-ons à ajouter à la cible de déploiement?
# -- le client HEROKU va chercher les add-ons dans un rrepository distant qu'éHeroku appelle "marketplace"
# -- Reste à tester s'il y a bien des add-ons qu'on peut utiliser gratuitement.

# ##############  TODO: utiliser une base de données ds la cible de déploiement Heroku
# -- 
# -- 
# -- 
# -- 




# #############     CONCLUSION: `kyte-boutique` fera usage de JGit et de la [REST API CLIENT HEROKU]:
# -- 
# --      https://devcenter.heroku.com/articles/platform-api-quickstart
# -- 
# -- Pour automatiser le process  des pipelines aboutissant chez Heroku.
# -- 
# -- tentative plantée d'implémentation en Java que je peux regarder pour apprendre des erreurs: https://github.com/heroku/direct-to-heroku-client-java
# -- 
# -- Note intéressante: avec cette REST API Heroku, je vais donc pouvoir interooger la "marketpplace Heroku", afin de proposer de l'autocomplétion de Procfile. Mais aussi je vais pouvoir vérifier, au déploiement, que les add-ons spécifiés dans le PRocfile sont bien tous existants dans la marketplace heroku).
# -- 
# -- 
# -- Un process standard serait:
# -- 
# --  1. On modifie le code source de l'application qui constitue le site web du projet							(composants: ide-service-manager)
# --  2. On commit & push sur le repo de référence de versionning du code source de l'application				(composants: source-code-manager)
# --  3. On exécute tous les tests statiques:																	(composants: quality-manager)
# --     ceux qui peuvent être exécutés sans exécution de l'application, comme des tests JUnit.
# --  4. On build l'application site web																		(composants: packaging-manager)
# --  5. On déploie l'application site web dans la cible de déploiement 										(composants: deployment-manager)
# --  6. On exécute tous les tests à l'exécution:																(composants: quality-manager)
# --     Ce sont les tests qui nécessitent un déploiement de l'application dans une
# --     cible de déploiement, comme les tests d'intégration, ou les UAT.
# --  7. 
# --  2. 
# --   
# --   
# -- 
# -- Doc de la REST API Heroku: https://devcenter.heroku.com/articles/platform-api-quickstart 
# -- 


```
