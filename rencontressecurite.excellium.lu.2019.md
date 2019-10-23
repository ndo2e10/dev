L'initiative:  **Les rencontres de la sécurité 2019** est organisée par Excellium, société experte dans la sécurité informatique, et propose des échanges et des réflexions sur les tendances dans la sécurité informatique.
Pour sa 6ième édition, qui a eu lieu le 06/06 à Mondorf, elle reprend certaines  bases des éditions précédentes mais sur 1 seule journée:
* une dizaine de conférences
* une vingtaines de speakers
* quelques exposants

Le programme complet est disponible sur le site de l'événement:

http://rencontressecurite.excellium.lu/

Pour les slides c'est par ici: 

https://go.pardot.com/l/251342/2019-06-04/j2cvdq

Voici mon top 3:

## Échanges autour de l'agilité dans les développements et la sécurité

,,avec la participation d'Agile Partner,,

Les méthodes agiles ont été initiées par des développeurs mais ceux-ci ne s'y retrouve plus. En effet, au début le focus était mis sur les développeurs (ou les gens qui produissent dans des projet non IT) et l'expertise technique. Petit à petit ce focus s'est orienté vers les processus, négligeant l'expertise, favorisant les rôles tel que

* Scrum Master
* Product Owner

et donc finalement oubliant que l'équipe est constitué d'autres personnes.

Ce talk parle des dérives de Scrum (qui représente 58% des projets répertoriés dit agiles ), certes un peu caricatural mais souvent juste. 
Les bases agiles portant un message simple basé sur le bon sens en sont dans la pratique complètement exclues:

* The Product Owner is the sole person responsible for managing the Product B acklog.
  * Dans la pratique il manque complétement de vision sur ce qui est fait et doit être fait.
* Cross functional teams: include all competencies and domain knowledge without depending on others outside the team
  * Dans la pratique l'équipe jongle comme elle peut avec les compétences internes et les agendas des experts externes à l'équipe
* Sprint Planning: the plan is created by the collaborative work of the entire Scrum Team.
  * Dans la pratique il a dictature du management relayé par le Product Owner
* Sprint Retrospective: the Scrum Team inspect itself and create a plan for improvements to be enacted during the next Sprint.
  * Dans la pratique l'équipe ne s'améliore pas vraiment, elle ne fait que tourné les rouages existant sans faire avancé le projet finalement.

Il est important de donné de l'autonomie au équipes agiles en leur donnant l'ensemble des compétences nécessaires pour répondre aux besoins du projet, cela inclus notamment un champion sécurité qui au mettre titre que les user stories business amène le spectre sécurité au projet et complète ou ajoute des user stories sécurité.

## Retour d'expérience : Intégration de la sécurité dans des développements agiles
,,avec la participation de LUXHUB,,


Une succès story d'un projet réglementaire mené à bien en mode agile par des développeurs et des ingénieurs sécurités sur une période relativement courte incluant de fortes contraintes métiers et technique.

Le projet en question c'est le développement et la mise en place d'une plate-forme répondant à la nouvelle directive **PSD2: Revised Payment Service Directive** ou **Open Banking** donnant à des **Trusted Third Party** accèss aux API dites publiques des banques. 

Ce que j'ai particulièrement apprécié c'est les détails donnés à la directive et aux briques techniques clés.
Regardez aussi la partie (vers la fin) sur les statistiques du projet: 5900 md! sur un peu plus de 6 mois de travail, ce n'est pas mentionné mais vers la fin du projet ils était 22-23 développeurs!

# Gestion des dépendances dans les développements informatiques Excellium
,,avec la participation de Checkmarx,,


Avec le nombre de dépendances externes (framework, librairies, etc.) croissantes il est important d'avoir un compte-rendu des "exploites" connues afin de mitiger le risque et de planifier la migration/correction et cela au minimum 1x par jour lors du build de nuit du CI. Il existe des outils open source et commerciaux plus ou moins poussive dans la détection mais un bon candidat lorsqu'on a encore rien en place est celui de OWASP: **OWASP Dependency Check**.

La deuxième partie de la présentation était une compagne de **Red team** exploitant une faille **XSS** à travers les outils **Kali** et **Beef**.
Ce qui est marquant c'est à quel point une faille **XSS** qui semble anodine peut servir de tremplin pour une attaque infectant l'ensemble du SI.
