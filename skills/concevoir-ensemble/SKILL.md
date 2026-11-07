---
name: concevoir-ensemble
description: À utiliser dès que l'utilisateur demande de construire ou de modifier quelque chose de moyennement conséquent (feature, refonte, plusieurs fichiers ou responsabilités), avant toute proposition d'archi, de test ou de code. Prend le pas sur superpowers:brainstorming, writing-plans et test-driven-development. Ne s'applique ni à un edit ciblé sur une fonction, ni à un pur changement d'UI.
---

# Concevoir ensemble

L'utilisateur conçoit, l'agent contredit puis écrit. Le but est qu'il comprenne ce qui est fait et puisse en être fier sans relire chaque ligne.

## Forme des messages

Chaque message est court, quelques lignes, le détail seulement sur demande. Plus il y a à lire, plus il valide sans réfléchir.

## Hors méthode

Pour un edit ciblé sur une fonction ou un pur changement d'UI, fais le changement et dis-le.

## Les étapes

À chaque changement d'étape, demande en une ligne « Je ferme [fichiers] et j'ouvre [fichiers] ? », avec des liens `fichier:ligne`.

1. **État des lieux.** Lis le périmètre, puis donne uniquement des faits, ce qui existe, où, ce qui s'y branche. Le message contient des constats et se termine par une question ouverte sur la façon dont l'utilisateur voit l'archi. Il ne contient ni piste, ni recommandation, ni jugement sur la faisabilité.
2. **Son archi.** Il pose les fonctions, les fichiers, les responsabilités, qui fait quoi, quand, comment, pourquoi. S'il demande explicitement ta proposition, donne-la.
3. **Contre-proposition.** Corrige sa logique, angles morts, effets de bord, règles du projet. Échangez jusqu'à son accord explicite.
4. **Cas limites.**
   - Écris d'abord ta propre liste dans `/tmp/<sujet>-cas-limites.md`, sans la montrer ni la citer.
   - Pose une batterie de 3 à 5 questions sur un seul thème (concurrence, droits, états…). Elles sont ancrées dans ce projet, ne contiennent pas la réponse, et ne se résument pas à « et si c'est vide ? ».
   - Attends ses réponses, puis passe au thème suivant.
   - Une fois les thèmes épuisés, montre seulement ce qu'il n'a pas trouvé, séparé de ses cas. Signale aussi ce qu'il a trouvé et qui n'était pas dans ta liste. Échangez, élaguez.
5. **Tests rouges.**
   - Pose les signatures vides de son plan, puis écris les tests.
   - Lance-les. Chacun doit échouer sur son assertion, une erreur de méthode manquante ne compte pas.
   - Corrige les erreurs de mise en place à ce stade uniquement. Signale tout test déjà vert.
   - Commite les tests seuls, sur la branche `feature/` ou `fix/` du chantier, tirée de `develop`. Ce commit les fige.
6. **Code.** Implémente selon son plan, au plus simple. `git diff <commit> -- tests` doit rester vide.
7. **Contre-épreuve.** Casse chaque règle dans le code, vérifie que le bon test passe au rouge, restaure.
8. **Relecture neuve.** Lance un agent neuf avec `consigne-relecture.md`, le plan et le commit de départ, sans ton raisonnement. Traite ou remonte ce qu'il trouve.
9. **Récap.** Pour chaque fichier, donne les fonctions et les lignes en liens `fichier:ligne`. Ajoute les écarts au plan et le résultat de la suite de tests. Rien d'autre, il fait une review rapide.

## Quand ça ne colle pas

Dès qu'un test figé contredit le code, ou que le plan ne tient pas, arrête-toi sur ce point et remonte l'écart, ton hypothèse et ce que tu proposes. Cela reste vrai s'il est absent ou pressé, il retrouve alors le test rouge et le diagnostic.

Une fois les tests figés, seul son accord autorise à modifier un test, assertion ou mise en place.
