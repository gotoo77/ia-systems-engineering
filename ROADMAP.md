# Roadmap

## Intention

Planifier l'écriture par lots incrémentaux, sans figer trop tôt le contenu final.

## Milestone 0 - Charte

- Stabiliser `VISION.md`.
- Stabiliser `PHILOSOPHY.md`.
- Stabiliser `STYLE_GUIDE.md`.
- Aligner `AGENTS.md`, `CONTRIBUTING.md` et les templates.

## v0.1 - Fondations

- Stabiliser les chapitres `docs/` et `foundations/`.
- Définir le vocabulaire de base.
- Poser les critères de qualité système.

### Critères de publication v0.1

- Les chapitres `docs/` et `foundations/` ont une intention, un périmètre et une checklist cohérents.
- Les concepts racines sont alignés avec `DOMAIN_MODEL.md`.
- Les dépendances pédagogiques de `foundations/` sont explicites dans `DEPENDENCIES.md`.
- Aucun chapitre de fondation n'anticipe les sections `llm/`, `agents/`, `memory/` ou `orchestration/` au-delà d'une ouverture.
- Les liens Markdown sont vérifiés.

## v0.2 - LLM

- Expliquer tokens, contexte, embeddings et hallucinations.
- Clarifier ce que le modèle sait faire et ce que le système doit prendre en charge.
- Relier capacités, limites et modes d'échec.

## v0.3 - Moteurs d'inférence

- Comparer les rôles des moteurs d'inférence.
- Documenter les compromis local, serveur, batch et interactif.

## v0.4 - Agents

- Clarifier le modèle agentique.
- Décrire tool use, MCP et sandboxing.
- Comparer les familles d'assistants de développement.

## v0.5 - Mémoire, RAG et indexation

- Définir les patterns de récupération.
- Distinguer mémoire courte, longue et externe.
- Introduire l'indexation de code.

## v0.6 - Architectures complètes

- Formaliser les patterns d'orchestration.
- Ajouter les critères d'observabilité et d'évaluation.
- Décrire l'architecture d'un assistant de développement local comme étude de cas.

## v0.7 - Labs

- Construire les labs minimaux.
- Valider les patterns sur Git, tests et RAG de code.
- Documenter les résultats sans transformer les labs en tutoriels longs.

## v1.0 - Assistant de développement local

- Construire le parcours complet d'un assistant de développement local.
- Relier fondations, LLM, moteurs, agents, mémoire et orchestration.
- Montrer les décisions d'architecture de bout en bout.

## Prospective

- Séparer tendances robustes et spéculations.
- Documenter le self-scaffolding.
- Explorer l'inference-time scaling.

## Questions à traiter

- Quel lot apporte le plus de valeur pédagogique immédiate ?
- Quels chapitres doivent rester conceptuels ?
- Quels labs valident les patterns sans alourdir le dépôt ?
