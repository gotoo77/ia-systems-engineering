# Table des matières

## Intention

Donner une vue stable de la progression pédagogique du manuel.

## Parcours principal

1. `docs/00_preface.md`
2. `docs/01_pourquoi_ce_livre_existe.md`
3. `docs/02_comment_lire_ce_livre.md`
4. `foundations/01_information_complexite_emergence.md`
5. `foundations/02_diviser_pour_mieux_comprendre.md`
6. `foundations/03_interfaces_orchestration_observabilite.md`
7. `llm/01_ce_qu_est_un_llm.md`
8. `llm/02_tokens_contexte_hallucinations.md`
9. `llm/03_embeddings_quantification_modeles_locaux.md`
10. `engines/01_pourquoi_un_moteur_inference.md`
11. `engines/02_llama_cpp_ollama_mlx_vllm.md`
12. `agents/01_pourquoi_les_agents.md`
13. `agents/02_continue_cline_aider_openhands_codex.md`
14. `agents/03_tool_use_mcp_sandboxing.md`
15. `memory/01_rag.md`
16. `memory/02_memoire_courte_longue_terme.md`
17. `memory/03_indexation_code_tree_sitter.md`
18. `orchestration/01_patterns_d_orchestration.md`
19. `orchestration/02_multi_agents.md`
20. `orchestration/03_observabilite_evaluation_feedback.md`
21. `assistant-dev/01_architecture_assistant_dev_local.md`
22. `labs/01_assistant_local_minimal.md`
23. `labs/02_agent_git_tests.md`
24. `labs/03_rag_sur_un_depot_code.md`
25. `prospective/01_self_scaffolding.md`
26. `prospective/02_inference_time_scaling.md`
27. `prospective/03_vers_les_systemes_intelligents.md`

## Supports

- `GOVERNANCE.md`
- `VISION.md`
- `PHILOSOPHY.md`
- `DOMAIN_MODEL.md`
- `DEPENDENCIES.md`
- `STYLE_GUIDE.md`
- `QUALITY_CHECKLIST.md`
- `GLOSSARY.md`
- `ROADMAP.md`
- `CONTRIBUTING.md`
- `AGENTS.md`
- `templates/chapter_template.md`
- `templates/concept_card_template.md`
- `templates/experiment_template.md`

## Renommages candidats

Ces propositions visent à remplacer les titres centrés sur des outils par des titres centrés sur les responsabilités. Elles ne doivent pas être appliquées sans tâche dédiée.

| Fichier actuel | Problème | Slug candidat |
| --- | --- | --- |
| `engines/02_llama_cpp_ollama_mlx_vllm.md` | Le titre liste des moteurs au lieu de nommer le critère architectural. | `engines/02_choisir_un_moteur_d_inference` |
| `agents/02_continue_cline_aider_openhands_codex.md` | Le titre liste des produits au lieu de nommer le type de système étudié. | `agents/02_assistants_de_developpement_agentiques` |
| `agents/03_tool_use_mcp_sandboxing.md` | Le titre mélange capacité, protocole et contrôle d'exécution. | `agents/03_outils_protocoles_et_sandboxing` |
| `memory/01_rag.md` | Le titre nomme directement le pattern sans expliciter le problème de récupération. | `memory/01_recuperation_documentaire_et_rag` |
| `memory/03_indexation_code_tree_sitter.md` | Le titre met `tree-sitter` au centre au lieu de l'indexation structurelle. | `memory/03_indexation_structurelle_du_code` |

## Questions à traiter

- L'ordre de lecture reste-t-il cohérent avec les dépendances conceptuelles ?
- Un chapitre applicatif arrive-t-il trop tôt ?
- Un nouveau chapitre doit-il être ajouté au parcours principal ou rester en support ?
