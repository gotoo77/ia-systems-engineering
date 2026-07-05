# Quality Checklist

## Intention

Fournir une grille de vérification commune avant d'accepter une contribution éditoriale.

## Rôle du document

Ce fichier sert de contrôle qualité. Il ne remplace pas le jugement éditorial ; il rend explicites les critères minimaux de cohérence, de modularité et de maintenabilité.

## Checklist chapitre

- [ ] Le chapitre répond à une intention unique.
- [ ] Le problème est posé avant la solution.
- [ ] Le pourquoi est expliqué avant le comment.
- [ ] Les questions à traiter sont des questions de conception.
- [ ] Les concepts nécessaires sont définis ou reliés au glossaire.
- [ ] Les responsabilités des composants sont séparées.
- [ ] Les compromis d'architecture sont visibles.
- [ ] Les limites, risques ou modes d'échec sont mentionnés.
- [ ] Les exemples restent courts et maintenables.
- [ ] Les références à des outils servent l'argument.
- [ ] Le chapitre reste lisible seul.
- [ ] Le déclic de compréhension visé est identifiable.

## Checklist architecture documentaire

- [ ] La source de vérité concernée est identifiée dans `GOVERNANCE.md`.
- [ ] Le changement respecte la progression pédagogique.
- [ ] Aucun doublon évident n'est introduit.
- [ ] Le contenu n'élargit pas inutilement le périmètre d'un chapitre.
- [ ] Une extraction de chapitre a été envisagée si le sujet devient autonome.
- [ ] `TABLE_OF_CONTENTS.md` et `ROADMAP.md` sont mis à jour si nécessaire.

## Checklist v0.1 publiable

- [ ] `docs/` et `foundations/` ont un rôle clair dans la progression pédagogique.
- [ ] Les concepts racines sont nommés de façon cohérente dans `DOMAIN_MODEL.md`, `DEPENDENCIES.md` et les chapitres concernés.
- [ ] Les chapitres de fondation restent centrés sur les principes, pas sur les outils.
- [ ] Les limites de chaque chapitre de fondation sont explicites.
- [ ] Les ouvertures vers LLM, agents, mémoire et orchestration ne remplacent pas les sections dédiées.
- [ ] Les liens Markdown ajoutés pointent vers des fichiers existants.
- [ ] La prochaine version prévue est identifiable dans `ROADMAP.md`.

## Questions à traiter

- Le changement améliore-t-il la compréhension durable du lecteur ?
- Le dépôt reste-t-il plus simple à maintenir après cette modification ?
- Le contenu ajouté appartient-il vraiment au fichier modifié ?
