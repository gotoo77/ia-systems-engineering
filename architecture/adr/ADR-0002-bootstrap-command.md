# ADR-0002 - Commande bootstrap

## Intention

Définir une commande unique pour préparer le passage de la conception à la production.

## Statut

Proposé.

## Contexte

Le dépôt dispose d'une gouvernance, d'un modèle de domaine, d'un graphe pédagogique, d'un workflow BMAD et d'une ADR de passage en production. Il manque un protocole unique qui vérifie ces éléments avant de déclarer le projet prêt pour `M1 - Production`.

La commande `bootstrap` doit éviter deux dérives :

- lancer la production alors que l'architecture documentaire n'est pas stable ;
- continuer à raffiner le système de pilotage sans jamais produire de contenu.

## Décision

Créer une commande one-shot `bootstrap`.

Elle sert uniquement à préparer et valider le passage `M0 - Architecture validée` vers `M1 - Production`.

`bootstrap` doit :

1. vérifier la gouvernance ;
2. vérifier les liens ;
3. vérifier le graphe pédagogique ;
4. vérifier les ADR ;
5. vérifier BMAD ;
6. lancer une `design-review` ;
7. produire un verdict `GO` ou `NO GO` ;
8. si `GO`, marquer M0 comme validé et préparer M1 ;
9. débloquer la première tâche de production ;
10. se retirer ou être marquée comme exécutée.

## Contraintes

- `bootstrap` ne rédige aucun chapitre.
- `bootstrap` ne corrige pas automatiquement les problèmes découverts.
- `bootstrap` ne passe pas M1 si la revue signale une ambiguïté structurelle majeure.
- `bootstrap` ne doit être exécutée qu'une seule fois.

## Conséquences

- La transition vers la production devient explicite et vérifiable.
- La commande `next` reste le mode de production ordinaire après M1.
- Tout refus de passage en M1 doit générer des tâches BMAD plutôt qu'une correction improvisée.

## Alternatives rejetées

- Passer en production avec `next` directement : trop implicite.
- Ajouter une phase manuelle non tracée : trop fragile.
- Garder `bootstrap` disponible après M1 : inutile et source de confusion.

## Questions à traiter

- Quels critères exacts déterminent le verdict `GO` ?
- Quelle tâche devient la première tâche de production ?
- Comment marquer proprement `bootstrap` comme exécutée ?
