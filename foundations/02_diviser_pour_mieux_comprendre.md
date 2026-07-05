# Diviser pour mieux comprendre

## Intention

Montrer comment découper un problème d'IA en responsabilités testables.

## Questions à traiter

- Quels composants isoler en premier ?
- Comment éviter un pipeline monolithique opaque ?
- Quels contrats rendent un système modifiable ?

## Objectifs pédagogiques

- Montrer pourquoi découper un système réduit la complexité observable.
- Distinguer composant, responsabilité, interface et contrat.
- Préparer le chapitre sur interfaces, orchestration et observabilité.
- Donner un critère simple pour repérer un découpage trop grossier ou trop fin.

## Connaissances préalables

- Avoir lu `foundations/01_information_complexite_emergence.md`.
- Comprendre qu'un système produit un comportement global par interactions.
- Savoir qu'une information peut être transformée ou perdue entre composants.

## Notions à introduire

- Composant.
- Responsabilité.
- Frontière.
- Interface.
- Contrat.
- Couplage.
- Cohésion.
- Testabilité.

## Limites du chapitre

- Ne pas détailler encore les patterns d'orchestration.
- Ne pas traiter les agents comme cas principal.
- Ne pas transformer le chapitre en méthode complète de conception logicielle.
- Ne pas comparer d'outils ou de frameworks.

## Déclic visé

Découper un système ne sert pas seulement à organiser du code. Cela sert à rendre les responsabilités observables, testables et remplaçables.

## Problème d'architecture

Un système devient difficile à comprendre quand tout dépend de tout.

Dans un pipeline monolithique, une entrée arrive, plusieurs transformations se produisent, puis une sortie apparaît. Tant que le résultat semble correct, le système donne une impression de simplicité. Mais dès qu'un comportement devient mauvais, il devient difficile de savoir où chercher.

Le problème n'est pas seulement la taille du code. Le problème est l'absence de responsabilités séparées.

Si aucun composant n'a de rôle clair, on ne sait plus :

- quelle information il consomme ;
- quelle transformation il applique ;
- quelle sortie il promet ;
- quelle erreur il peut produire ;
- quel comportement il faut tester.

Diviser un système sert donc d'abord à rendre le raisonnement possible.

## Responsabilité

Une responsabilité décrit ce qu'un composant doit prendre en charge.

Elle doit être assez précise pour permettre une vérification. Dire qu'un composant "gère la connaissance" est trop large. Dire qu'il "sélectionne les passages pertinents d'un corpus pour une question donnée" est plus utile : on peut observer son entrée, sa sortie et ses erreurs.

Une bonne responsabilité répond à trois questions :

- Que reçoit ce composant ?
- Que produit-il ?
- Quelle décision ou transformation lui appartient ?

Si la réponse mélange plusieurs verbes importants, le composant est peut-être trop gros.

## Composant

Un composant est une partie du système à laquelle on attribue une responsabilité stable.

Ce peut être un module logiciel, un service, une étape de pipeline, une fonction, un moteur d'inférence, un index ou un outil. Le format importe moins que la frontière : peut-on expliquer ce que ce composant fait sans expliquer tout le système ?

Un composant utile n'est pas forcément petit. Il est compréhensible par son rôle.

Le bon découpage ne cherche donc pas à multiplier les pièces. Il cherche à faire apparaître les responsabilités qui doivent être testées, remplacées ou observées séparément.

## Frontière

Une frontière indique où s'arrête une responsabilité et où commence une autre.

Sans frontière claire, les erreurs circulent sans nom. Une mauvaise réponse peut venir d'une requête mal formulée, d'une récupération faible, d'un contexte trop court, d'une consigne ambiguë ou d'une sortie de modèle mal vérifiée.

Avec des frontières, on peut poser des questions plus utiles :

- La mauvaise information a-t-elle été sélectionnée ?
- La bonne information a-t-elle été transmise ?
- La transformation attendue a-t-elle été appliquée ?
- Le résultat a-t-il été vérifié avant d'être utilisé ?

Une frontière n'est pas seulement une séparation technique. C'est un point de raisonnement.

## Interface

Une interface décrit comment deux composants échangent.

Elle peut être formelle, comme une API. Elle peut aussi être documentaire, comme un format de prompt, un schéma de sortie, une convention de nommage ou une structure de message.

L'interface doit rendre explicites :

- les entrées attendues ;
- les sorties promises ;
- les erreurs possibles ;
- les informations obligatoires ;
- les informations optionnelles.

Plus l'interface est floue, plus les composants deviennent difficiles à remplacer. Un composant qui reçoit "un peu de contexte" est difficile à tester. Un composant qui reçoit une question, une liste de sources et une contrainte de réponse est beaucoup plus contrôlable.

## Contrat

Un contrat ajoute une attente vérifiable à une interface.

Il ne suffit pas de dire qu'un composant produit une réponse. Il faut savoir ce que cette réponse doit respecter : citer une source, ne pas inventer un fait, signaler une incertitude, conserver un identifiant, respecter un format, ne pas modifier un fichier hors périmètre.

Un contrat permet de transformer une intention en critère d'acceptation.

Dans un système d'IA, les contrats sont importants parce que certaines sorties peuvent être plausibles sans être correctes. Le contrat sert alors de garde-fou : il donne une forme à ce qui doit être vérifié.

## Couplage et cohésion

Deux notions aident à juger un découpage.

La cohésion mesure si les éléments regroupés servent la même responsabilité. Un composant cohésif a une raison claire d'exister.

Le couplage mesure à quel point un composant dépend des détails internes d'un autre. Plus le couplage est fort, plus une modification locale risque de produire des effets inattendus ailleurs.

Un bon découpage cherche donc :

- une cohésion forte à l'intérieur d'un composant ;
- un couplage explicite entre composants.

Il ne cherche pas à supprimer toute dépendance. Un système sans dépendances ne fait rien. Il cherche à rendre les dépendances visibles et maîtrisables.

## Testabilité

Un découpage est utile s'il rend le système plus testable.

Tester tout le système de bout en bout reste nécessaire, mais cela ne suffit pas. Quand un résultat est mauvais, il faut pouvoir isoler l'étape fragile.

Une responsabilité testable permet de vérifier séparément :

- la qualité d'une sélection d'information ;
- la conformité d'un format de sortie ;
- la conservation d'une source ;
- la pertinence d'une transformation ;
- le respect d'une limite de périmètre.

La testabilité donne une valeur concrète au découpage. Si une séparation ne rend rien plus compréhensible, observable ou vérifiable, elle est probablement artificielle.

## Exemple minimal

Reprenons l'assistant qui répond à une question à partir d'un document.

Un découpage minimal peut séparer quatre responsabilités :

- recevoir et normaliser la question ;
- sélectionner les passages pertinents ;
- générer une réponse à partir des passages ;
- vérifier que la réponse reste liée aux sources.

Chaque responsabilité a une entrée, une sortie et un risque propre.

Si la réponse est mauvaise, le diagnostic devient plus précis. Le problème peut venir de la question, de la récupération, de la génération ou de la vérification. Le système reste imparfait, mais il devient inspectable.

## Compromis

Découper aide à comprendre, mais découper coûte.

Trop peu de composants rend le système opaque. Trop de composants peut produire une architecture bruyante, avec beaucoup d'interfaces à maintenir et peu de bénéfice réel.

Le compromis central est donc de découper quand une responsabilité doit être :

- comprise séparément ;
- testée séparément ;
- remplacée séparément ;
- observée séparément.

Si aucune de ces raisons n'existe, le découpage risque d'être décoratif.

## Termes à relier

- Composant : à ajouter au glossaire.
- Responsabilité : à ajouter au glossaire.
- Frontière : à ajouter au glossaire.
- Interface : à ajouter au glossaire.
- Contrat : à ajouter au glossaire.
- Couplage : à ajouter au glossaire.
- Cohésion : à ajouter au glossaire.
- Testabilité : à ajouter au glossaire.

## À retenir

- Découper un système sert à rendre les responsabilités visibles.
- Un composant utile se définit par son rôle, pas par sa taille.
- Une frontière claire transforme une erreur globale en diagnostic local.
- Une interface décrit l'échange ; un contrat rend l'attente vérifiable.
- Un bon découpage améliore la compréhension, l'observation, le remplacement ou le test.

## Limites

Ce chapitre ne propose pas encore de patterns d'orchestration.

Il ne traite pas les agents, la mémoire ou les moteurs d'inférence comme cas principaux. Il prépare seulement le vocabulaire nécessaire pour comprendre pourquoi ces éléments devront avoir des responsabilités explicites dans les chapitres suivants.

## Questions ouvertes

- Quel découpage devient trop fin pour rester maintenable ?
- Quels contrats sont utiles sans rigidifier l'expérimentation ?
- Quand faut-il accepter un composant plus large pour préserver la simplicité ?

## Pour aller plus loin

- Lire ensuite `foundations/03_interfaces_orchestration_observabilite.md`.
- Relier les notions de composant, interface et contrat au modèle de domaine.
- Garder le critère pratique : une séparation doit rendre quelque chose plus observable, testable ou remplaçable.

## Checklist qualité

- [x] Déclic de compréhension identifié.
- [x] Intention unique.
- [x] Questions de conception explicites.
- [ ] Concepts à ajouter au glossaire.
- [x] Responsabilités ou limites clarifiées.
- [x] Compromis d'architecture visibles.
- [x] Limites ou modes d'échec mentionnés.
- [x] Exemple court et maintenable.
- [x] Chapitre lisible seul.
