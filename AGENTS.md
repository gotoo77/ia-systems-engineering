# AGENTS.md

## Intention

Définir le protocole d'intervention des agents IA qui travaillent sur ce dépôt.

## Rôle du document

Ce fichier est la source de vérité pour le comportement attendu des agents. Il ne remplace pas les autres fichiers de gouvernance ; il indique comment les utiliser avant de modifier le dépôt.

## Documents à lire

Toute session agentique doit commencer par lire :

1. `bmad/00_operating_model.md`
2. `bmad/03_next_action.md`
3. `GOVERNANCE.md`
4. `DOMAIN_MODEL.md`
5. `DEPENDENCIES.md`

Avant toute modification significative, compléter ensuite avec :

1. Lire `VISION.md` pour vérifier le cap.
2. Lire `PHILOSOPHY.md` pour appliquer les principes d'arbitrage.
3. Lire `STYLE_GUIDE.md` pour appliquer les règles d'écriture.
4. Lire `QUALITY_CHECKLIST.md` pour valider le changement.
5. Lire `CONTRIBUTING.md` pour respecter le workflow contributeur.

## Protocole d'intervention

- Identifier le fichier source de vérité avant d'ajouter une règle.
- Si l'utilisateur dit `next`, appliquer strictement `bmad/00_operating_model.md`.
- Analyser l'impact sur la progression pédagogique.
- Rechercher les doublons avec les fichiers existants.
- Vérifier que le périmètre du chapitre reste stable.
- Proposer une extraction si un sujet devient autonome.
- Mettre à jour `GLOSSARY.md`, `ROADMAP.md` ou `TABLE_OF_CONTENTS.md` seulement si le changement l'exige.
- Ne pas rédiger de contenu long sans validation du cadrage.

## Critères de refus

Refuser ou proposer une alternative si une demande :

- contourne les sources de vérité ;
- ajoute du volume sans clarifier le problème traité ;
- introduit un outil sans responsabilité architecturale claire ;
- duplique un concept déjà porté ailleurs ;
- mélange plusieurs responsabilités dans un même fichier ;
- affaiblit la progression pédagogique.

## Questions à traiter

- Quelle source de vérité gouverne ce changement ?
- Le changement respecte-t-il les frontières du modèle de domaine ?
- Les dépendances pédagogiques restent-elles cohérentes ?
- Le dépôt devient-il plus maintenable après modification ?
