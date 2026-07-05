# Observations

## Rôle

Capturer les observations issues du pilotage réel du dépôt avant toute tentative d'extraction d'un framework réutilisable.

Ce fichier n'est pas une source de vérité normative. Il sert de carnet d'expérience : les idées notées ici sont des candidats, pas des règles.

## Principe

Ne pas inventer le framework à l'avance.

Observer plusieurs décisions réelles, repérer les invariants qui survivent, puis seulement ensuite envisager une extraction.

## Format d'observation

Chaque observation doit rester courte.

```md
### OBS-000 — Titre court

- **Constat** :
- **Hypothèse** :
- **Signal positif** :
- **Risque** :
- **Statut** : CANDIDAT | À CONFIRMER | REJETÉ
```

## Observations initiales

### OBS-001 — Une seule tâche READY réduit la dispersion

- **Constat** : le protocole `next` force une exécution séquentielle et limite les dérives.
- **Hypothèse** : une seule tâche `READY` améliore la continuité et la vérifiabilité du travail.
- **Signal positif** : les sessions récentes se terminent avec un périmètre clair, un commit ciblé et une prochaine action identifiable.
- **Risque** : le système peut devenir trop rigide si les dépendances sont mal entretenues.
- **Statut** : CANDIDAT

### OBS-002 — Le système doit servir le contenu

- **Constat** : la gouvernance aide tant qu'elle permet de produire mieux, pas tant qu'elle se multiplie.
- **Hypothèse** : une règle de fermeture évite que la méthode devienne le projet.
- **Signal positif** : le passage M0 -> M1 a été décidé par critères de sortie plutôt que par perfectionnement continu.
- **Risque** : ajouter des fichiers de pilotage peut masquer l'absence de production réelle.
- **Statut** : CANDIDAT

### OBS-003 — Les décisions structurantes gagnent à devenir des ADR

- **Constat** : les ADR rendent les changements de phase et d'architecture discutables et traçables.
- **Hypothèse** : même un dépôt documentaire bénéficie d'une mémoire de décision proche d'un projet logiciel.
- **Signal positif** : les décisions M0 et M1 sont retrouvables sans relire toute la conversation.
- **Risque** : transformer chaque micro-choix en ADR produirait du bruit.
- **Statut** : À CONFIRMER

### OBS-004 — Les chapitres comme composants clarifient les responsabilités

- **Constat** : traiter chaque chapitre comme un composant aide à définir son périmètre, ses dépendances et ses limites.
- **Hypothèse** : cette analogie est transférable à d'autres corpus de connaissance.
- **Signal positif** : le modèle de domaine et la table de dépendances réduisent les chevauchements.
- **Risque** : pousser l'analogie logicielle trop loin peut rendre l'écriture artificielle.
- **Statut** : CANDIDAT

### OBS-005 — Les sources de vérité uniques réduisent la dette documentaire

- **Constat** : séparer vision, principes, modèle de domaine, dépendances et checklist évite les règles contradictoires.
- **Hypothèse** : toute architecture documentaire maintenable a besoin de responsabilités explicites.
- **Signal positif** : les modifications récentes référencent les sources au lieu de recopier les règles.
- **Risque** : trop de sources de vérité peuvent devenir difficiles à parcourir.
- **Statut** : CANDIDAT

### OBS-006 — Les architectures se découvrent par l'expérience

- **Constat** : "Les meilleures architectures ne sont peut-être pas celles que l'on invente. Ce sont celles que l'on découvre en observant attentivement ce qui survit à l'expérience."
- **Hypothèse** : un framework robuste doit être extrait d'expériences répétées plutôt que conçu abstraitement au départ.
- **Signal positif** : plusieurs règles actuelles du dépôt viennent d'observations concrètes plutôt que d'une doctrine préalable.
- **Risque** : transformer trop vite une belle formulation en invariant non testé.
- **Statut** : CANDIDAT
