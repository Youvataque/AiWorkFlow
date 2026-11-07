# AiWorkFlow

Ma manière de développer avec Claude Code. Un plugin qui garde l'IA dans la boucle sans jamais me sortir de la mienne.

## Pourquoi

J'avais besoin de contrôle. De sentir ce que je fais, pourquoi je le fais et comment je le fais. De rester maître à bord, sans pour autant me passer de l'IA.

Les workflows agentiques que je trouvais poussent vers le vibe coding en boîte noire. On décrit vaguement, l'agent produit beaucoup, on valide sans lire, et au bout de trois semaines plus personne ne sait pourquoi le code est comme il est. Ce n'est pas ma façon de travailler.

Je voulais un [Superpowers](https://github.com/obra/superpowers) qui me corresponde. Pas un pilote automatique, du développement agentique maîtrisé. L'IA contredit, cherche les angles morts, écrit les tests et le code. Moi je conçois, je tranche et je comprends ce qui part en prod.

## Les principes

**Je conçois, l'agent contredit puis écrit.** Il commence par un état des lieux factuel, me laisse poser mon archi, puis la challenge. Il ne la remplace pas.

**Il me questionne au lieu de me donner sa liste.** Pour les cas limites, il prépare la sienne en silence, me pose des questions par thème, puis ne me montre que ce que j'ai raté. Une liste toute faite, je la valide sans réfléchir.

**Court.** Plus il y a à lire, plus je dis oui facilement. Les messages tiennent en quelques lignes, le détail vient si je le demande.

**Les tests d'abord, et figés.** Ils sont écrits, vus rouges, puis commités avant le code. Ensuite, seul mon accord autorise à en modifier un.

**Des preuves, pas des promesses.** Rien n'est déclaré fini, corrigé ou passant sans la commande qui le montre. Chaque règle est cassée volontairement pour vérifier que le bon test rougit.

**Pas de correctif à l'aveugle.** Un bug se comprend avant de se corriger, et l'agent me propose la cause et la solution avant de toucher au code.

**Git suit un seul circuit.** Une branche `feature/` ou `fix/` tirée de `develop`, fusionnée en squash dans `develop`, puis `develop` fusionné normalement dans `main` quand je le demande. L'agent n'est jamais coauteur.

## Ce que contient le plugin

| Élément | Rôle |
|---|---|
| `regles.md` | Mes règles permanentes, injectées au démarrage de chaque session par `hooks/session-start` |
| `skills/concevoir-ensemble` | Le parcours d'une fonctionnalité, de l'état des lieux au récap, en neuf étapes |
| `skills/debug-systematique` | Trouver la cause avant de proposer un correctif |
| `skills/verifier-avant-de-conclure` | Aucune annonce de réussite sans preuve fraîche |
| `skills/ecrire-un-skill` | Écrire ou modifier un skill en le testant d'abord sur des agents neufs |
| `scenarios.md` | Les mises en situation qui ont servi à éprouver les skills |

Les skills `concevoir-ensemble` et les règles sont à moi. Les trois autres sont adaptés de Superpowers et prennent le pas sur leurs équivalents.

## Installation

Dans Claude Code

```
/plugin marketplace add Youvataque/AiWorkFlow
/plugin install AiWorkFlow@youvataque
```

Les règles s'appliquent dès la session suivante. Si Superpowers est aussi installé, mieux vaut le désactiver pour éviter que deux méthodes se marchent dessus.

## Crédits

Construit à partir de [Superpowers](https://github.com/obra/superpowers) de Jesse Vincent, sous licence MIT. Les fichiers repris gardent leur `LICENSE.superpowers`.
