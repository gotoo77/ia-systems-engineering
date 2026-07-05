# BMAD Decision Log

## Intention

Tracer les décisions structurantes du projet documentaire.

## Rôle du document

Ce fichier garde la mémoire des décisions qui influencent l'architecture documentaire, le modèle de domaine, les dépendances ou la gouvernance.

## Format

Chaque entrée doit contenir :

- date ;
- décision ;
- contexte ;
- impact ;
- fichiers concernés ;
- alternatives rejetées.

## Décisions

### 2026-07-05 — Création du pilotage BMAD

- **Décision** : créer un système BMAD dédié au pilotage du dépôt documentaire.
- **Contexte** : le projet doit pouvoir être repris par une commande opérationnelle `next`.
- **Impact** : les sessions futures doivent commencer par `bmad/00_operating_model.md` et `bmad/03_next_action.md`.
- **Fichiers concernés** : `bmad/*`, `AGENTS.md`, `README.md`.
- **Alternatives rejetées** : piloter uniquement depuis `ROADMAP.md`, car la roadmap n'encode pas une file de tâches exécutable.

### 2026-07-05 — Formalisation du passage en production

- **Décision** : créer `ADR-0001 - Passage en mode Production`.
- **Contexte** : le projet doit savoir quand passer de la conception documentaire à la production sans relancer le débat à chaque session.
- **Impact** : le passage en production dépend de `M0 - Architecture validée` et d'une revue de phase.
- **Fichiers concernés** : `architecture/adr/ADR-0001-production-gate.md`, `GOVERNANCE.md`, `bmad/*`.
- **Alternatives rejetées** : lancer directement la rédaction ; attendre une architecture parfaite.

### 2026-07-05 — Registre des commandes opérationnelles

- **Décision** : créer `COMMANDS.md` comme registre minimal des commandes utilisateur.
- **Contexte** : le dépôt doit pouvoir être piloté par des ordres stables comme `next`, `review`, `sync` ou `design-review`.
- **Impact** : les agents doivent consulter `COMMANDS.md` quand une commande explicite est utilisée.
- **Fichiers concernés** : `COMMANDS.md`, `AGENTS.md`, `GOVERNANCE.md`, `README.md`, `bmad/00_operating_model.md`.
- **Alternatives rejetées** : multiplier les protocoles dispersés dans `AGENTS.md` ; ajouter une couche de processus plus lourde avant production de contenu.

### 2026-07-05 — Commande one-shot bootstrap

- **Décision** : définir `bootstrap` comme commande de préparation du passage `M0 - Architecture validée` vers `M1 - Production`.
- **Contexte** : le projet a besoin d'un déclencheur explicite pour vérifier la gouvernance, les ADR, BMAD et le graphe pédagogique avant de produire.
- **Impact** : `bootstrap` lance une revue de phase et produit un verdict `GO` ou `NO GO` sans rédiger de chapitre.
- **Fichiers concernés** : `COMMANDS.md`, `architecture/adr/ADR-0002-bootstrap-command.md`, `architecture/adr/ADR-0001-production-gate.md`.
- **Alternatives rejetées** : lancer directement `next` en production ; conserver une validation de phase implicite.

### 2026-07-05 — Design review M0 : NO GO

- **Décision** : ne pas passer en `M1 - Production` à ce stade.
- **Contexte** : la revue M0 confirme que la gouvernance existe, mais que les critères d'acceptabilité du modèle de domaine et du graphe pédagogique ne sont pas encore objectivés.
- **Impact** : la production des chapitres reste bloquée ; les tâches BMAD minimales restantes sont ajoutées.
- **Fichiers concernés** : `bmad/02_backlog.md`, `bmad/03_next_action.md`, `bmad/06_decision_log.md`.
- **Alternatives rejetées** : passer en production avec des critères implicites ; relancer une amélioration illimitée du système.

### 2026-07-05 — Clôture M0 et passage en M1 Production

- **Décision** : valider M0 et passer en `M1 - Production`.
- **Contexte** : les critères objectifs de sortie M0 sont définis dans `ADR-0001` et satisfaits par les artefacts existants.
- **Impact** : `BMAD-009` devient la seule tâche `READY`; les changements majeurs de gouvernance deviennent exceptionnels.
- **Fichiers concernés** : `architecture/adr/ADR-0001-production-gate.md`, `architecture/adr/ADR-0003-m1-production.md`, `bmad/02_backlog.md`, `bmad/03_next_action.md`.
- **Alternatives rejetées** : prolonger M0 pour perfectionner le modèle de domaine ; produire directement un chapitre complet.

### 2026-07-05 — Recadrage de `foundations/03`

- **Décision** : limiter `foundations/03` aux interfaces, contrats et frontières de composants.
- **Contexte** : orchestration et observabilité apparaissaient trop tôt comme sujets complets dans les fondations.
- **Impact** : orchestration, observabilité, évaluation et feedback restent annoncés mais sont approfondis dans les sections aval.
- **Fichiers concernés** : `foundations/03_interfaces_orchestration_observabilite.md`, `DEPENDENCIES.md`.
- **Alternatives rejetées** : rédiger un chapitre d'architecture complète dans les fondations ; renommer ou déplacer le fichier immédiatement.

### 2026-07-05 — Rôle des labs

- **Décision** : définir les labs comme expériences de validation d'hypothèses d'architecture.
- **Contexte** : les labs risquaient de devenir des tutoriels outils ou des chapitres conceptuels parallèles.
- **Impact** : chaque lab doit partir d'une hypothèse, produire une observation et éclairer une décision d'architecture.
- **Fichiers concernés** : `labs/README.md`, `templates/experiment_template.md`, `DEPENDENCIES.md`.
- **Alternatives rejetées** : documenter des installations pas à pas ; utiliser les labs pour introduire des concepts centraux avant les chapitres.

## Questions à traiter

- Cette décision change-t-elle la structure du projet ?
- Une alternative importante a-t-elle été rejetée ?
