# AGENTS.md

## Intention

Définir les règles éditoriales pour tout contributeur humain ou agent logiciel travaillant dans ce dépôt.

## Règles éditoriales

- Écrire en français clair, technique, sans emphase marketing.
- Préférer les principes, invariants et compromis aux listes d'outils.
- Garder chaque chapitre autonome : contexte, intention, questions, plan, références.
- Ne pas ajouter de contenu long sans mise à jour de la roadmap.
- Relier les concepts au glossaire quand un terme devient central.
- Séparer les faits établis, les hypothèses et les opinions d'architecture.
- Préférer des exemples petits, reproductibles et maintenables.
- Éviter les dépendances temporelles non nécessaires.
- Ne pas transformer un chapitre en tutoriel outil si le sujet est architectural.
- Commencer chaque chapitre par le problème d'architecture, pas par une technologie.
- Définir les responsabilités des composants avant de nommer des produits.
- Expliciter au moins un compromis : coût, latence, qualité, contrôle, sécurité ou maintenabilité.
- Employer le même terme pour le même concept ; si le terme varie, ajouter une note au glossaire.
- Signaler les affirmations temporelles avec prudence et éviter les formulations de type "aujourd'hui le meilleur outil".
- Limiter les listes d'outils à leur rôle dans une comparaison d'architecture.
- Préférer les phrases courtes et les titres descriptifs.
- Ne pas mélanger tutoriel, opinion et référence conceptuelle dans la même section.

## Progression éditoriale

Le livre suit cet ordre : fondations, LLM, moteurs d'inférence, agents, mémoire, orchestration, assistant de développement local, labs, prospective. Ne pas introduire un chapitre applicatif avant les concepts dont il dépend.

## Format attendu

Utiliser `templates/chapter_template.md` pour les chapitres, `templates/concept_card_template.md` pour les notions courtes et `templates/experiment_template.md` pour les labs.

## Checklist qualité d'un chapitre

- Le chapitre répond à une intention unique.
- Les questions à traiter sont formulées comme des questions de conception.
- Les concepts nécessaires sont définis ou reliés au glossaire.
- Les responsabilités des composants sont séparées.
- Les compromis d'architecture sont visibles.
- Les exemples restent courts et ne prennent pas le pas sur le principe.
- Les limites, risques ou modes d'échec sont mentionnés.
- Le chapitre reste lisible sans dépendre d'un autre fichier.
- Les références à des outils servent l'argument, pas l'inverse.
- La conclusion prévue peut tenir en quelques points à retenir.

## Questions à traiter

- Le chapitre clarifie-t-il un principe durable ?
- Les limites et compromis sont-ils explicites ?
- Le texte peut-il être relu indépendamment du reste du livre ?
