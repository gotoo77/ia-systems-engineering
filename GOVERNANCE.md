# Governance

## Intention

Clarifier les sources de vérité du dépôt documentaire.

## Rôle du document

Ce fichier définit quel document porte quelle responsabilité. Il évite que les règles éditoriales, les critères de validation et le modèle conceptuel soient dupliqués dans plusieurs fichiers.

## Sources de vérité

- `VISION.md` : cap du projet.
- `PHILOSOPHY.md` : principes d'arbitrage.
- `DOMAIN_MODEL.md` : concepts et frontières.
- `DEPENDENCIES.md` : graphe pédagogique.
- `STYLE_GUIDE.md` : règles d'écriture.
- `QUALITY_CHECKLIST.md` : critères de validation.
- `AGENTS.md` : protocole d'intervention des agents.
- `CONTRIBUTING.md` : workflow contributeur.
- `architecture/adr/` : mémoire des décisions structurantes.

## Règle de maintenance

Une règle ne doit vivre que dans son fichier source de vérité. Les autres fichiers doivent référencer cette source au lieu de recopier la règle.

## Ordre d'arbitrage

1. Vérifier le cap dans `VISION.md`.
2. Trancher selon les principes de `PHILOSOPHY.md`.
3. Valider les concepts avec `DOMAIN_MODEL.md`.
4. Vérifier les dépendances dans `DEPENDENCIES.md`.
5. Appliquer la forme définie par `STYLE_GUIDE.md`.
6. Valider avec `QUALITY_CHECKLIST.md`.
7. Consigner une décision structurante dans `architecture/adr/` si elle change la phase, la structure ou les responsabilités du projet.

## Questions à traiter

- Quelle source de vérité porte cette décision ?
- Une règle est-elle dupliquée ailleurs ?
- Le changement renforce-t-il la maintenabilité du dépôt ?
