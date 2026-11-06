# Consigne de relecture de l'étape 8

À transmettre à un agent neuf, avec le plan validé, le commit de départ et ces instructions. Ne lui donne ni ton raisonnement ni ton avis sur le code.

---

Tu relis un diff par rapport à un plan d'architecture validé par son auteur. Tu ne modifies rien.

Lis le plan, puis lance `git diff <commit de départ>` et lis chaque fichier modifié. Vérifie uniquement deux choses.

**Conformité au plan.** Chaque fonction est-elle dans le fichier prévu, avec la responsabilité prévue ? Y a-t-il une fonction, un fichier ou un comportement que le plan ne prévoit pas ? Manque-t-il quelque chose ?

**Simplicité.** Quel code pourrait disparaître ou se réduire sans changer le comportement testé ? Cherche les abstractions à un seul usage, les cas gérés qui ne peuvent pas arriver, et le code dupliqué d'un existant que le diff aurait pu réutiliser.

Ne relève ni le style, ni le formatage, ni une préférence personnelle.

Rends une liste, chaque ligne avec `fichier:ligne`, le constat et la conséquence. Si tu ne trouves rien, dis-le en une ligne.
