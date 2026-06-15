# Source: https://www.skult.ai/blog/llm-extraction-informations-documents-administratifs

[BLOG](https://www.skult.ai/blog)/Intelligence artificielle·JAN '26·6 MIN

# LLM et documents administratifs : les défis de l'extraction d'information

Les délibérations, rapports et PV municipaux ne ressemblent à aucun autre texte. Voici les techniques que nous utilisons pour en extraire des signaux fiables.

![Pierre James](https://www.skult.ai/_next/image?url=%2Fteam%2Fpierre-james.webp&w=3840&q=75)

Pierre JamesCEO, Skult

![LLM et documents administratifs : les défis de l'extraction d'information](https://www.skult.ai/_next/image?url=%2Fblog%2Fllm-extraction-informations-documents-administratifs%2Fcover.webp&w=3840&q=75)

Les délibérations, rapports et procès-verbaux municipaux ne ressemblent à aucun autre texte. Voici les techniques que nous utilisons chez Skult pour en extraire des signaux commerciaux fiables — et les pièges que nous avons appris à éviter.

## La spécificité des documents administratifs

Un procès-verbal de conseil municipal n'est pas un article de presse, un rapport d'entreprise, ou un document contractuel. C'est un genre textuel avec ses propres conventions : style administratif formel, formules consacrées, références croisées à des délibérations antérieures, abréviations institutionnelles, et une structure très variable d'une collectivité à l'autre.

Les LLM généralistes ont été entraînés sur de grandes quantités de texte web et académique. Ils performent mal sur ce type de corpus sans adaptation. Un modèle qui "comprend" Shakespeare peut échouer à interpréter correctement "DGS" ou "UGAP" dans leur contexte institutionnel.

## Les défis de l'extraction

Trois défis principaux se posent lors de l'extraction d'information dans les documents publics :

### L'implicite institutionnel

Un document peut dire "le conseil prend acte de la présentation du DSI concernant le renouvellement du système de paie" sans jamais mentionner de budget. Pour un humain expert, c'est un signal fort. Pour un LLM non contextual isé, c'est une phrase anodine.

### La discontinuité

Le sujet d'intérêt commercial peut être mentionné dans trois points différents de l'ordre du jour, sans lien explicite entre eux. La synthèse nécessite une compréhension globale du document, pas seulement locale.

### La polysémie administrative

Des termes comme "mission", "programme", "projet" ont des sens très précis en droit administratif qui diffèrent du sens commun. Une mauvaise interprétation peut fausser toute l'analyse.

## Techniques utilisées

Pour adresser ces défis, nous combinons plusieurs approches :

- Prompt engineering spécialisé avec un vocabulaire administratif injecté dans le contexte système
- Classification en plusieurs passes : un premier modèle filtre la pertinence globale, un second extrait les entités spécifiques
- Règles métier explicites pour les patterns récurrents (formulations budgétaires, expressions de vote, délais)
- Validation croisée entre plusieurs extractions du même passage pour détecter les incohérences
- Base de connaissance institutionnelle (sigles, organismes, types de procédures) injectée comme contexte

Exemple de passage difficile

"M. le Maire rappelle que suite aux conclusions du rapport de la chambre régionale des comptes, il conviendra d'engager une réflexion sur l'évolution du système d'information financier dans le cadre du prochain DOB."

Signal extrait : réforme SI financier · phase exploratoire · prochain exercice budgétaire · initiateur : exécutif municipal

## Chunking et contexte

Un document de 80 pages ne peut pas être envoyé en bloc dans une fenêtre de contexte. Le découpage (chunking) est une étape critique qui influence directement la qualité de l'extraction. Un découpage trop granulaire perd le contexte ; trop large, il dépasse les limites du modèle.

Nous utilisons un chunking sémantique qui respecte les frontières de points d'ordre du jour — la structure naturelle des PV de conseils — plutôt qu'un découpage mécanique par nombre de tokens. Chaque chunk est enrichi avec un en-tête de contexte global (collectivité, date, type de session) pour éviter les ambiguïtés.

## Hallucination et fiabilité

Le risque d'hallucination est particulièrement critique dans notre contexte : une alerte inventée envoyée à un commercial est pire qu'une alerte manquée. Elle génère de la méfiance envers le système et des contacts intempestifs auprès de collectivités.

Notre approche : toujours ancrer les extractions dans le verbatim source. Chaque alerte est accompagnée du passage exact du document qui a généré le signal. Si le modèle ne peut pas citer le texte source, l'alerte n'est pas générée. C'est une contrainte forte qui réduit la sensibilité, mais garantit la fiabilité des alertes remontées.

## Conclusion

L'extraction d'information sur les documents administratifs publics est un problème d'ingénierie NLP appliqué, pas un problème de recherche. Les techniques existent — prompt engineering, multi-pass, anchoring sur le verbatim — mais leur assemblage correct dans un pipeline de production fiable demande une expertise spécifique du domaine. C'est ce que nous avons construit chez Skult sur deux ans d'itérations.

Voir les signaux sur votre secteur

Setup en moins de 48h.

[Demander une démo →](https://www.skult.ai/demander-une-demo)

[Retour au blog](https://www.skult.ai/blog)