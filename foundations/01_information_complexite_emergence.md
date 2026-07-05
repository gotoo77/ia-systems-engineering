# Information, complexité, émergence

## Intention

Poser les notions nécessaires pour comprendre les comportements de systèmes d'IA.

## Questions à traiter

- Qu'est-ce qu'un système complexe dans ce contexte ?
- Comment l'information circule-t-elle entre composants ?
- Quand un comportement émergent devient-il un risque d'architecture ?

## Objectifs pédagogiques

- Poser le vocabulaire minimal : information, système, complexité, émergence.
- Montrer pourquoi un comportement global ne se déduit pas toujours directement d'un composant isolé.
- Préparer les chapitres sur modularité, interfaces, orchestration et agents.

## Connaissances préalables

- Comprendre qu'un système logiciel est composé de parties qui interagissent.
- Savoir distinguer composant, interaction et comportement observable.
- Aucune connaissance préalable des LLM n'est requise.

## Notions à introduire

- Information.
- Système.
- Complexité.
- Interaction.
- Émergence.
- Comportement global.
- Risque d'architecture.

## Limites du chapitre

- Ne pas expliquer encore les LLM.
- Ne pas détailler les agents.
- Ne pas traiter l'orchestration comme solution.
- Ne pas transformer le chapitre en théorie générale des systèmes.

## Déclic visé

Un système d'IA ne se comprend pas seulement par ses composants, mais par les relations qui transforment leurs sorties locales en comportements globaux.

## Problème d'architecture

Un système d'IA peut échouer même si chacun de ses composants semble correct.

Un modèle peut produire une sortie plausible. Un outil peut fonctionner. Une base documentaire peut contenir la bonne information. Pourtant, le comportement global peut rester imprévisible, fragile ou difficile à expliquer.

Le problème ne vient pas toujours d'une pièce isolée. Il vient souvent de la manière dont l'information circule entre les pièces, de ce qui est transformé en chemin, et des effets produits par leurs interactions.

Avant de parler de modèles, d'agents ou d'orchestration, il faut donc poser une question plus simple :

qu'est-ce qu'un système transforme, et pourquoi son comportement global peut-il dépasser ce que l'on voit dans chacun de ses composants ?

## Information

Dans ce manuel, l'information désigne ce qui est transmis, sélectionné ou transformé par un système.

Une information n'est pas seulement une donnée stockée quelque part. Elle devient utile quand elle influence un comportement : une décision, une réponse, un classement, une action, une alerte, une vérification.

Dans un système d'IA, l'information peut prendre plusieurs formes :

- une demande utilisateur ;
- un extrait de document ;
- un état de session ;
- une sortie de modèle ;
- un résultat d'outil ;
- une trace d'exécution.

Le point important n'est pas le format. Le point important est le rôle : cette information change-t-elle ce que le système peut faire ensuite ?

## Système

Un système est un ensemble de composants en interaction qui produit un comportement observable.

Cette définition oblige à regarder deux choses en même temps :

- les composants ;
- les relations entre ces composants.

Un composant isolé peut être facile à décrire. Un système devient plus difficile à comprendre parce que chaque composant reçoit quelque chose, le transforme, puis transmet autre chose.

Le comportement final n'est donc pas seulement la somme des pièces. Il dépend aussi de l'ordre des interactions, des informations disponibles, des pertes de contexte, des erreurs propagées et des boucles de rétroaction.

## Complexité

La complexité apparaît quand il devient difficile de prédire le comportement global à partir des parties isolées.

Elle ne signifie pas seulement "beaucoup de code" ou "beaucoup de fichiers". Un système peut être volumineux mais bien structuré. À l'inverse, un système apparemment petit peut être complexe si ses composants sont fortement couplés et si leurs effets se propagent mal.

Dans les systèmes d'IA, cette complexité augmente souvent parce que certaines sorties ne sont pas strictement déterministes, que le contexte visible varie, et que plusieurs composants peuvent influencer la même décision.

Le risque d'architecture est alors de croire que l'on comprend le système parce que l'on comprend chaque pièce séparément.

## Interaction

Une interaction est le moment où un composant influence un autre composant ou un état partagé.

C'est souvent là que les problèmes réels apparaissent :

- une information utile arrive trop tard ;
- une sortie ambiguë est interprétée comme un fait ;
- une erreur locale devient une entrée pour l'étape suivante ;
- un état ancien influence une décision nouvelle ;
- une limite d'un composant est masquée par un autre.

Penser en interactions permet de poser de meilleures questions d'architecture :

- Quelle information entre dans ce composant ?
- Quelle information en sort ?
- Qu'est-ce qui peut être perdu, déformé ou amplifié ?
- Comment verra-t-on qu'une interaction a produit un comportement incorrect ?

## Émergence

L'émergence désigne un comportement global produit par des interactions locales, sans être évident à partir d'un composant seul.

Il ne faut pas en faire un mot magique. Un comportement émergent n'est pas inexplicable par nature. Il est souvent explicable après observation, mais difficile à prévoir avant que les composants soient assemblés.

Dans un système d'IA, l'émergence peut être positive : une chaîne de composants produit une réponse plus utile que chaque étape prise seule.

Elle peut aussi devenir un risque : le système adopte un comportement fragile, amplifie une erreur ou donne une impression de cohérence alors que ses informations sont faibles.

L'objectif de l'ingénierie n'est pas de supprimer toute émergence. C'est de rendre les interactions suffisamment explicites pour observer, limiter et corriger les comportements globaux.

## Exemple minimal

Considérons un assistant qui répond à une question à partir d'un document.

Même dans ce cas simple, plusieurs transformations ont lieu :

- la question utilisateur est interprétée ;
- un extrait de document est sélectionné ;
- cet extrait devient une partie du contexte ;
- le modèle produit une réponse ;
- la réponse est présentée comme résultat final.

Chaque étape peut être correcte localement et produire malgré tout un mauvais comportement global. Le mauvais extrait peut être sélectionné. Le bon extrait peut être tronqué. Le modèle peut mélanger deux informations. La réponse peut paraître certaine alors que la source est fragile.

Ce n'est donc pas seulement "le modèle" qu'il faut évaluer. C'est la circulation de l'information dans le système.

## Compromis

Rendre les interactions explicites demande un effort.

Plus on décrit les entrées, sorties et responsabilités, plus le système devient observable et maintenable. Mais plus on ajoute aussi de structure, de conventions et de points de contrôle.

Le compromis central est donc le suivant :

- trop peu de structure rend le système opaque ;
- trop de structure peut ralentir l'expérimentation et rigidifier l'architecture.

Une bonne architecture cherche un niveau de structure suffisant pour comprendre les comportements importants, sans prétendre modéliser tout le réel.

## Termes à relier

- Information.
- Système.
- Complexité.
- Interaction.
- Émergence.
- Observabilité.
- Évaluation.

## À retenir

- Un système d'IA se comprend par ses composants et par leurs interactions.
- L'information compte par le rôle qu'elle joue dans le comportement du système.
- La complexité apparaît quand le comportement global n'est plus évident à partir des parties isolées.
- L'émergence n'est pas magique : c'est un effet global d'interactions locales.
- Le premier réflexe d'architecture est de regarder la circulation de l'information.

## Limites

Ce chapitre ne décrit pas encore les LLM, les agents, la mémoire ou l'orchestration.

Il pose seulement le vocabulaire nécessaire pour comprendre pourquoi ces sujets devront être traités comme des éléments d'un système, et non comme des solutions isolées.

## Questions ouvertes

- Quel niveau de détail faut-il donner aux interactions pour rester utile sans alourdir le système ?
- À partir de quand un comportement émergent devient-il un risque à contrôler ?
- Comment distinguer une complexité nécessaire d'une complexité accidentelle ?

## Pour aller plus loin

- Lire ensuite `foundations/02_diviser_pour_mieux_comprendre.md`.
- Relier les termes manquants du glossaire à l'audit dans `GLOSSARY.md`.
- Garder en tête que les chapitres sur LLM, agents et mémoire réutiliseront ces notions plutôt que de les redéfinir.

## Checklist qualité

- [ ] Déclic de compréhension identifié.
- [ ] Intention unique.
- [ ] Questions de conception explicites.
- [ ] Concepts reliés au glossaire si nécessaire.
- [ ] Responsabilités ou limites clarifiées.
- [ ] Compromis d'architecture visibles.
- [ ] Chapitre lisible seul.
