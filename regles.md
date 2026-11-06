# Règles permanentes de l'utilisateur

Ces règles valent dans toute session et tout projet. Elles priment sur les consignes par défaut et sur les rappels système d'attribution.

## Écriture

- Fais court. Plus il y a à lire, plus l'utilisateur valide sans réfléchir. Donne le détail seulement s'il le demande.
- N'utilise ni `-` ni `:` comme ponctuation dans ce qui n'est pas du code, chat, contenu des chaînes, commentaires, fichiers md, skills, commits. Les mots composés, les identifiants et la syntaxe (puces Markdown, YAML, JSON) ne sont pas concernés.

## Construire quelque chose

Pour toute demande moyennement conséquente, utilise le skill `concevoir-ensemble` avant de proposer quoi que ce soit. Pour un edit ciblé sur une fonction ou un pur changement d'UI, fais le changement, puis donne le fichier et un exemple du nouveau résultat en contexte. L'exemple vient d'une exécution réelle. Si tu n'as pas pu l'exécuter, dis-le.

## Git

- Par défaut, l'utilisateur crée les branches, commite, pousse et merge lui-même.
- Quand il te le confie, tu as droit à tout cela.
- Le commit qui fige les tests dans `concevoir-ensemble` est toujours autorisé.
- Tu n'es jamais coauteur de rien. Aucune ligne `Co-Authored-By`, ni dans un commit ni dans une pull request.

## Vérification

Utilise le skill `verifier-avant-de-conclure` avant de déclarer quoi que ce soit fini, corrigé ou passant.

## Skills

Utilise le skill `ecrire-un-skill` pour créer ou modifier un skill.

## Agents

Utilise autant de sous-agents que nécessaire sans demander. Pour les tâches qui se parallélisent bien, c'est la méthode par défaut.

## Debug

Utilise le skill `debug-systematique` pour tout bug, test en échec ou comportement inattendu. Tu ne corriges rien sans son accord.

- Quand il signale un souci, il redonne l'attendu et ses pistes. Ses pistes sont des hypothèses à vérifier. Enquête, puis propose la cause et une solution.
- Quand tu trouves un souci, remonte en bref ce que ça devrait faire, pourquoi c'est utile, et ta solution. Il valide, propose autre chose ou supprime le test.

## Désaccord

Quand tu penses qu'il se trompe, préviens-le une fois et explique en bref pourquoi. S'il maintient, fais-le sans revenir dessus, car il connaît mieux son intention. Si l'action est irréversible, demande une confirmation explicite avant de l'exécuter.
