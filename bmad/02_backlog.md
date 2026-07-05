# BMAD Backlog

## Intention

Lister les tâches initiales du projet documentaire.

## Rôle du document

Ce fichier sert de réservoir de tâches. L'exécution opérationnelle se fait depuis `bmad/03_next_action.md`.

## Tâches initiales

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
- **Statut** : READY
- **Contexte** : ces concepts risquent de se chevaucher dans plusieurs chapitres.
- **Fichiers concernés** : `DOMAIN_MODEL.md`, `GLOSSARY.md`
- **Critères d'acceptation** : les frontières sont explicites ; les confusions fréquentes sont listées.
- **Dépendances** : BMAD-003.

### BMAD-005 — Définir les frontières modèle, inférence, moteur

- **Epic** : EPIC-01
- **Statut** : BLOCKED
- **Contexte** : le chapitre sur les moteurs dépend de ces frontières.
- **Fichiers concernés** : `DOMAIN_MODEL.md`, `GLOSSARY.md`, `engines/01_pourquoi_un_moteur_inference.md`
- **Critères d'acceptation** : les responsabilités de chaque concept sont séparées ; aucun contenu de chapitre n'est rédigé.
- **Dépendances** : BMAD-003.

### BMAD-006 — Transformer le graphe pédagogique en table de dépendances

- **Epic** : EPIC-02
- **Statut** : TODO
- **Contexte** : `DEPENDENCIES.md` contient un graphe initial mais pas encore de table exploitable.
- **Fichiers concernés** : `DEPENDENCIES.md`
- **Critères d'acceptation** : chaque section principale a prérequis, concepts introduits et concepts réutilisés.
- **Dépendances** : BMAD-003.

### BMAD-007 — Identifier les chapitres à renommer

- **Epic** : EPIC-03
- **Statut** : BLOCKED
- **Contexte** : certains fichiers sont nommés par outils plutôt que par responsabilité.
- **Fichiers concernés** : `agents/`, `engines/`, `memory/`, `TABLE_OF_CONTENTS.md`
- **Critères d'acceptation** : une proposition de renommage est listée sans appliquer les renommages.
- **Dépendances** : BMAD-006.

### BMAD-008 — Recadrer les frontières de `foundations/03`

- **Epic** : EPIC-03
- **Statut** : BLOCKED
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
- **Statut** : TODO
- **Contexte** : les labs doivent valider des hypothèses d'architecture, pas devenir des tutoriels.
- **Fichiers concernés** : `labs/`, `templates/experiment_template.md`, `DEPENDENCIES.md`
- **Critères d'acceptation** : rôle, format et critères de validation des labs sont explicités.
- **Dépendances** : BMAD-002.

### BMAD-011 — Créer une checklist v0.1 publiable

- **Epic** : EPIC-06
- **Statut** : BLOCKED
- **Contexte** : la version v0.1 doit avoir un périmètre vérifiable.
- **Fichiers concernés** : `ROADMAP.md`, `QUALITY_CHECKLIST.md`, `bmad/04_definition_of_done.md`
- **Critères d'acceptation** : critères de publication v0.1 explicites.
- **Dépendances** : BMAD-006, BMAD-010.

### BMAD-012 — Auditer le glossaire comme langage du domaine

- **Epic** : EPIC-01
- **Statut** : BLOCKED
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

## Questions à traiter

- La tâche est-elle assez petite pour être exécutée en une session ?
- Les critères d'acceptation permettent-ils une vérification objective ?
