# Source: https://www.skult.ai/blog/ia-qualification-opportunites-secteur-public

[BLOG](https://www.skult.ai/blog)/Intelligence artificielle·AVR '26·5 MIN

# Comment l'IA qualifie une opportunité dans le secteur public

De la délibération brute au signal qualifié : le pipeline de traitement que nous avons construit pour scorer chaque opportunité détectée.

![Pierre James](https://www.skult.ai/_next/image?url=%2Fteam%2Fpierre-james.webp&w=3840&q=75)

Pierre JamesCEO, Skult

![Comment l'IA qualifie une opportunité dans le secteur public](https://www.skult.ai/_next/image?url=%2Fblog%2Fia-qualification-opportunites-secteur-public%2Fcover.webp&w=3840&q=75)

De la délibération brute au signal qualifié : derrière chaque alerte Skult se cache un pipeline de traitement qui analyse, extrait, score et contextualise l'information. Voici comment ça fonctionne.

## Le problème du volume

Il y a environ 35 000 collectivités territoriales en France. Chacune produit régulièrement des documents publics : procès-verbaux de conseils, délibérations, rapports d'orientation budgétaire, comptes administratifs. À l'échelle nationale, ce sont des millions de pages produites chaque année.

Aucune équipe commerciale ne peut les lire manuellement. Mais ces documents contiennent les signaux les plus précoces d'un achat public : un projet qui émerge, un budget qui se précise, un besoin qui devient prioritaire.

L'enjeu est donc double : détecter ces signaux à grande échelle, et ne remonter que ceux qui ont une réelle valeur commerciale pour l'équipe qui les reçoit.

## Le pipeline de traitement

Le traitement d'un document source passe par plusieurs étapes successives avant de générer une alerte.

D'abord, la collecte. Nos agents surveillent en continu les sources officielles — portails des collectivités, publications institutionnelles, bases de données ouvertes. Quand un nouveau document est détecté, il est ingéré et préparé pour l'analyse.

Ensuite, la segmentation. Les documents publics ont des structures très variables — certains font 3 pages, d'autres 150. Le document est découpé en segments thématiques cohérents, chaque segment étant analysé indépendamment avant une synthèse globale.

## Extraction d'entités et de signaux

La phase d'extraction cherche à identifier dans le texte plusieurs types d'informations :

- **Entités nommées** — collectivité concernée, montant mentionné, date ou délai, type de projet
- **Signaux d'intention** — verbes d'action (voter, prévoir, lancer, étudier), formulations budgétaires
- **Contexte sectoriel** — domaine technique (IT, énergie, voirie, RH), type d'infrastructure concernée
- **Urgence et maturité** — le projet est-il en phase d'étude, d'arbitrage ou de décision ?

Ces extractions permettent de construire une représentation structurée de chaque signal potentiel, indépendamment du format ou du style rédactionnel du document source.

Exemple extrait d'un DOB

"Le rapport d'orientation budgétaire 2026 prévoit une enveloppe de 150 000 € pour la modernisation du système d'information RH, avec une consultation à lancer avant le second semestre."

Signaux extraits : SIRH · 150 000 € · consultation H2 2026 · Collectivité X

## Scoring de l'opportunité

Toutes les alertes ne se valent pas. Le scoring permet de prioriser les signaux selon plusieurs critères : la précision du signal (vague mention vs. enveloppe chiffrée), la maturité du projet (intention vs. décision), la correspondance avec l'ICP du client, et la présence d'éléments facilitateurs comme un référencement central d'achat.

Le score final est exprimé sur 10 et accompagné d'une justification en langage naturel, pour que le commercial comprenne immédiatement pourquoi ce signal a été remonté.

## Les limites de l'IA sur ce type de données

Les documents administratifs posent des défis spécifiques aux modèles de langage. Le style est souvent très formel, elliptique, et les formulations indirectes sont fréquentes. Un "sujet évoqué en séance" peut valoir autant qu'une délibération votée, mais seulement si on comprend le contexte institutionnel.

C'est pourquoi le pipeline n'est pas un simple passage dans un LLM généraliste. Il combine plusieurs modèles spécialisés, des règles métier explicites, et une supervision humaine sur les cas limites. L'IA est un outil de traitement à grande échelle — pas un oracle.

## Conclusion

La qualification d'une opportunité B2G par l'IA n'est pas un problème de NLP académique. C'est un problème d'ingénierie appliquée, où chaque étape du pipeline — collecte, segmentation, extraction, scoring — doit être calibrée pour le domaine spécifique des marchés publics.

Le résultat, quand c'est bien fait, est une alerte que le commercial peut utiliser immédiatement : avec le bon interlocuteur, le bon contexte, et le bon moment.

Voir les signaux sur votre secteur

Setup en moins de 48h.

[Demander une démo →](https://www.skult.ai/demander-une-demo)

[Retour au blog](https://www.skult.ai/blog)