# BMAD Next Action

## Intention

Piloter la prochaine action exécutable du dépôt.

## Rôle du document

Ce fichier est le point d'entrée de la commande opérationnelle `next`. Une session agentique doit sélectionner la première tâche au statut `READY`, l'exécuter seule, mettre à jour son statut, puis s'arrêter.

## File de tâches

### BMAD-001 — Valider le système BMAD

- **Epic** : EPIC-00
- **Statut** : DONE
- **Contexte** : le dossier `bmad/` vient d'être créé et doit être vérifié comme système de pilotage.
- **Fichiers concernés** : `bmad/*`, `AGENTS.md`, `README.md`
- **Critères d'acceptation** : les fichiers BMAD existent ; `next` est défini ; `AGENTS.md` référence le démarrage agentique ; aucun chapitre n'est modifié.
- **Dépendances** : aucune.

### BMAD-002 — Consolider les sources de vérité

- **Epic** : EPIC-00
- **Statut** : DONE
- **Contexte** : `GOVERNANCE.md` doit devenir le point d'entrée des responsabilités documentaires.
- **Fichiers concernés** : `GOVERNANCE.md`, `README.md`, `CONTRIBUTING.md`
- **Critères d'acceptation** : chaque fichier de gouvernance a une responsabilité unique ; les doublons évidents sont supprimés.
- **Dépendances** : BMAD-001.

### BMAD-003 — Formaliser le format d'un concept

- **Epic** : EPIC-01
- **Statut** : DONE
- **Contexte** : `DOMAIN_MODEL.md` liste les concepts mais doit stabiliser leur format.
- **Fichiers concernés** : `DOMAIN_MODEL.md`, `templates/concept_card_template.md`
- **Critères d'acceptation** : le format conceptuel est clair ; les champs responsabilité, frontières, relations et contre-exemples sont présents.
- **Dépendances** : BMAD-002.

### BMAD-004 — Définir les frontières contexte, mémoire, RAG

- **Epic** : EPIC-01
- **Statut** : DONE
- **Contexte** : ces concepts risquent de se chevaucher dans plusieurs chapitres.
- **Fichiers concernés** : `DOMAIN_MODEL.md`, `GLOSSARY.md`
- **Critères d'acceptation** : les frontières sont explicites ; les confusions fréquentes sont listées.
- **Dépendances** : BMAD-003.

### BMAD-005 — Définir les frontières modèle, inférence, moteur

- **Epic** : EPIC-01
- **Statut** : DONE
- **Contexte** : le chapitre sur les moteurs dépend de ces frontières.
- **Fichiers concernés** : `DOMAIN_MODEL.md`, `GLOSSARY.md`, `engines/01_pourquoi_un_moteur_inference.md`
- **Critères d'acceptation** : les responsabilités de chaque concept sont séparées ; aucun contenu de chapitre n'est rédigé.
- **Dépendances** : BMAD-003.

### BMAD-006 — Transformer le graphe pédagogique en table de dépendances

- **Epic** : EPIC-02
- **Statut** : DONE
- **Contexte** : `DEPENDENCIES.md` contient un graphe initial mais pas encore de table exploitable.
- **Fichiers concernés** : `DEPENDENCIES.md`
- **Critères d'acceptation** : chaque section principale a prérequis, concepts introduits et concepts réutilisés.
- **Dépendances** : BMAD-003.

### BMAD-007 — Identifier les chapitres à renommer

- **Epic** : EPIC-03
- **Statut** : DONE
- **Contexte** : certains fichiers sont nommés par outils plutôt que par responsabilité.
- **Fichiers concernés** : `agents/`, `engines/`, `memory/`, `TABLE_OF_CONTENTS.md`
- **Critères d'acceptation** : une proposition de renommage est listée sans appliquer les renommages.
- **Dépendances** : BMAD-006.

### BMAD-008 — Recadrer les frontières de `foundations/03`

- **Epic** : EPIC-03
- **Statut** : DONE
- **Contexte** : interfaces, orchestration et observabilité sont regroupées trop tôt.
- **Fichiers concernés** : `foundations/03_interfaces_orchestration_observabilite.md`, `DEPENDENCIES.md`
- **Critères d'acceptation** : un plan de recadrage est proposé sans rédaction complète.
- **Dépendances** : BMAD-006.

### BMAD-009 — Préparer le cadrage du premier chapitre fondateur

- **Epic** : EPIC-04
- **Statut** : DONE
- **Contexte** : aucun chapitre ne doit être rédigé avant stabilisation du domaine.
- **Fichiers concernés** : `foundations/01_information_complexite_emergence.md`, `DOMAIN_MODEL.md`, `DEPENDENCIES.md`
- **Critères d'acceptation** : objectifs, prérequis, notions et limites sont cadrés.
- **Dépendances** : M1 validé par `architecture/adr/ADR-0003-m1-production.md`.

### BMAD-010 — Définir le rôle des labs

- **Epic** : EPIC-05
- **Statut** : DONE
- **Contexte** : les labs doivent valider des hypothèses d'architecture, pas devenir des tutoriels.
- **Fichiers concernés** : `labs/`, `templates/experiment_template.md`, `DEPENDENCIES.md`
- **Critères d'acceptation** : rôle, format et critères de validation des labs sont explicités.
- **Dépendances** : BMAD-002.

### BMAD-011 — Créer une checklist v0.1 publiable

- **Epic** : EPIC-06
- **Statut** : DONE
- **Contexte** : la version v0.1 doit avoir un périmètre vérifiable.
- **Fichiers concernés** : `ROADMAP.md`, `QUALITY_CHECKLIST.md`, `bmad/04_definition_of_done.md`
- **Critères d'acceptation** : critères de publication v0.1 explicites.
- **Dépendances** : BMAD-006, BMAD-010.

### BMAD-012 — Auditer le glossaire comme langage du domaine

- **Epic** : EPIC-01
- **Statut** : DONE
- **Contexte** : le glossaire doit refléter le modèle de domaine, pas seulement définir des mots.
- **Fichiers concernés** : `GLOSSARY.md`, `DOMAIN_MODEL.md`
- **Critères d'acceptation** : termes manquants identifiés ; aucune définition longue ajoutée sans validation.
- **Dépendances** : BMAD-003.

### BMAD-013 — Préparer la Design Review M0

- **Epic** : EPIC-00
- **Statut** : DONE
- **Contexte** : le passage en production doit être décidé par une revue de phase, pas par inertie.
- **Fichiers concernés** : `architecture/adr/ADR-0001-production-gate.md`, `bmad/06_decision_log.md`, `QUALITY_CHECKLIST.md`
- **Critères d'acceptation** : critères de revue M0 listés ; rôle `Knowledge Program Manager` pris en compte ; aucune rédaction de chapitre lancée.
- **Dépendances** : BMAD-002, BMAD-006, BMAD-010.

### BMAD-014 — Définir les critères GO/NO GO de M0

- **Epic** : EPIC-00
- **Statut** : DONE
- **Contexte** : la design review M0 a montré que les critères "acceptable" doivent devenir vérifiables avant passage en production.
- **Fichiers concernés** : `architecture/adr/ADR-0001-production-gate.md`, `QUALITY_CHECKLIST.md`, `bmad/04_definition_of_done.md`
- **Critères d'acceptation** : critères M0 objectivables ; verdict GO/NO GO reproductible ; aucune rédaction de chapitre.
- **Dépendances** : BMAD-001.

### BMAD-015 — Identifier la première tâche de production M1

- **Epic** : EPIC-06
- **Statut** : DONE
- **Contexte** : le passage en M1 doit débloquer une première tâche de production clairement définie, pas une intention vague de rédaction.
- **Fichiers concernés** : `bmad/03_next_action.md`, `ROADMAP.md`, `TABLE_OF_CONTENTS.md`
- **Critères d'acceptation** : première tâche M1 identifiée ; dépendances explicites ; aucun chapitre produit.
- **Dépendances** : BMAD-009, BMAD-013, BMAD-014.

## Lot M1 - Production v0.1

### BMAD-016 — Rédiger une première version courte du chapitre fondateur 01

- **Epic** : EPIC-04
- **Statut** : DONE
- **Contexte** : le chapitre `foundations/01` est cadré ; il faut produire une première version maintenable sans chercher la perfection.
- **Fichiers concernés** : `foundations/01_information_complexite_emergence.md`
- **Critères d'acceptation** : le problème précède la solution ; les concepts information, système, complexité, interaction et émergence sont introduits ; les limites du chapitre sont respectées ; les sections finales obligatoires sont présentes.
- **Dépendances** : BMAD-009, BMAD-011.

### BMAD-017 — Relire le chapitre fondateur 01 contre la checklist v0.1

- **Epic** : EPIC-06
- **Statut** : DONE
- **Contexte** : la première version doit être relue comme un composant documentaire avant d'étendre la rédaction.
- **Fichiers concernés** : `foundations/01_information_complexite_emergence.md`, `QUALITY_CHECKLIST.md`, `DEPENDENCIES.md`
- **Critères d'acceptation** : les écarts sont corrigés ou listés ; aucun nouveau sujet autonome n'est enfoui dans le chapitre ; les dépendances pédagogiques restent cohérentes.
- **Dépendances** : BMAD-016.

### BMAD-018 — Cadrer le chapitre `foundations/02`

- **Epic** : EPIC-04
- **Statut** : DONE
- **Contexte** : le chapitre sur la division des responsabilités doit s'appuyer sur le chapitre fondateur 01.
- **Fichiers concernés** : `foundations/02_diviser_pour_mieux_comprendre.md`, `DEPENDENCIES.md`
- **Critères d'acceptation** : objectifs, prérequis, notions, limites et déclic visé sont explicités ; aucun chapitre complet n'est rédigé.
- **Dépendances** : BMAD-017.

### BMAD-019 — Rédiger une première version courte du chapitre `foundations/02`

- **Epic** : EPIC-04
- **Statut** : READY
- **Contexte** : après cadrage, le chapitre doit expliquer le découpage en responsabilités testables.
- **Fichiers concernés** : `foundations/02_diviser_pour_mieux_comprendre.md`
- **Critères d'acceptation** : le chapitre reste centré sur les principes ; les contrats et responsabilités sont reliés aux fondations ; les sections finales obligatoires sont présentes.
- **Dépendances** : BMAD-018.

### BMAD-020 — Cadrer le chapitre `foundations/03` après recadrage

- **Epic** : EPIC-04
- **Statut** : BLOCKED
- **Contexte** : `foundations/03` doit rester centré sur interfaces, contrats et frontières de composants.
- **Fichiers concernés** : `foundations/03_interfaces_orchestration_observabilite.md`, `DEPENDENCIES.md`
- **Critères d'acceptation** : objectifs, prérequis, notions, limites et déclic visé sont explicités ; orchestration et observabilité restent des ouvertures.
- **Dépendances** : BMAD-017.

### BMAD-021 — Rédiger une première version courte du chapitre `foundations/03`

- **Epic** : EPIC-04
- **Statut** : BLOCKED
- **Contexte** : après cadrage, le chapitre doit préparer l'architecture sans anticiper les sections aval.
- **Fichiers concernés** : `foundations/03_interfaces_orchestration_observabilite.md`
- **Critères d'acceptation** : le chapitre explique les interfaces et contrats ; il annonce orchestration et observabilité sans les détailler ; les sections finales obligatoires sont présentes.
- **Dépendances** : BMAD-020.

### BMAD-022 — Aligner les pages `docs/` avec v0.1

- **Epic** : EPIC-06
- **Statut** : BLOCKED
- **Contexte** : les pages d'entrée doivent préparer la lecture de v0.1 sans devenir une introduction générale trop longue.
- **Fichiers concernés** : `docs/`, `README.md`, `TABLE_OF_CONTENTS.md`
- **Critères d'acceptation** : les pages `docs/` orientent vers le parcours v0.1 ; les liens sont cohérents ; aucun chapitre conceptuel n'est dupliqué.
- **Dépendances** : BMAD-017.

### BMAD-023 — Auditer la publiabilité de v0.1

- **Epic** : EPIC-06
- **Statut** : BLOCKED
- **Contexte** : avant release, v0.1 doit être vérifiée contre la checklist et la Definition of Done.
- **Fichiers concernés** : `ROADMAP.md`, `QUALITY_CHECKLIST.md`, `bmad/04_definition_of_done.md`, `TABLE_OF_CONTENTS.md`
- **Critères d'acceptation** : les critères v0.1 sont satisfaits ou les écarts sont listés ; aucune correction hors périmètre n'est appliquée ; une recommandation `GO` ou `NO GO` est produite.
- **Dépendances** : BMAD-019, BMAD-021, BMAD-022.

## Questions à traiter

- Quelle est la première tâche `READY` ?
- Ses dépendances sont-elles satisfaites ?
- Que faudra-t-il rendre `READY` après son exécution ?
