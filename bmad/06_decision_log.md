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

## Questions à traiter

- Cette décision change-t-elle la structure du projet ?
- Une alternative importante a-t-elle été rejetée ?
