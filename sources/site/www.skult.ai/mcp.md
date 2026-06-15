# Source: https://www.skult.ai/mcp

[ACCUEIL](https://www.skult.ai/)/MCP

Intégration MCP

# Connecter Skult à votre agent IA

Le serveur MCP Skult permet à votre agent IA d'accéder directement à vos alertes commerciales, vos contacts et votre pipeline. Une fois connecté, votre agent peut lire, filtrer et mettre à jour vos données Skult en langage naturel — sans quitter votre environnement de travail.

URL du serveur·https://mcp.skult.ai

Claude CodeClaude DesktopCursorWindsurfVS CodeChatGPTCodexAntigravityAutres agents

1

### Ajouter le serveur MCP

claude mcp add --transport http skult https://mcp.skult.ai

2

### Authentification

Au premier lancement, Claude Code ouvre automatiquement une fenêtre de connexion. Entrez vos identifiants Skult et cliquez sur **Autoriser l'accès**.

3

### Vérifier la connexion

claude mcp list

Le serveur skult doit apparaître avec le statut ✓ Connected.

## Outils disponibles

Une fois connecté, votre agent a accès à 7 outils :

| Outil | Type | Description |
| --- | --- | --- |
| get\_alerts | Lecture | Lister vos alertes avec filtres (statut, ville, score) |
| get\_alert\_detail | Lecture | Détail complet d'une alerte : verbatim, contacts, notes |
| get\_pipeline\_stats | Lecture | Vue globale du pipeline par statut |
| search\_contacts | Lecture | Rechercher des contacts enrichis |
| update\_alert\_status | Écriture | Changer le statut d'une alerte |
| update\_alert\_tier | Écriture | Modifier la priorité (1 = haute, 3 = basse) |
| add\_alert\_note | Écriture | Ajouter une note datée sur une alerte |

Exemples en langage naturel

→“Quelles sont mes 5 alertes les plus récentes ?”

→“Passe l'alerte de Liévin en statut À traiter”

→“Ajoute une note 'rappel demain' sur l'alerte de Laon”

→“Combien d'alertes ai-je en cours ?”

## Dépannage

### L'authentification ne s'ouvre pas

Vérifiez que votre client MCP supporte le transport HTTP. Si la fenêtre ne s'ouvre pas automatiquement, copiez l'URL de connexion affichée dans le terminal et ouvrez-la manuellement dans votre navigateur.

### Les outils n'apparaissent pas après connexion

Redémarrez votre agent IA après l'authentification. Si le problème persiste, supprimez puis rajoutez le serveur pour forcer une nouvelle authentification.

### "Invalid credentials" lors de la connexion

Utilisez les mêmes identifiants que pour vous connecter à app.skult.ai. Si vous avez oublié votre mot de passe, utilisez la réinitialisation depuis l'app.

### Un seul agent peut-il accéder aux données de toute l'équipe ?

Non — chaque utilisateur se connecte avec son propre compte Skult. Les données sont isolées par organisation.

## FAQ

### Mes données sont-elles sécurisées ?

Oui. La connexion utilise OAuth 2.0 — votre mot de passe n'est jamais transmis à l'agent. Le token d'accès est stocké localement sur votre machine par votre client IA.

### Puis-je utiliser plusieurs agents en même temps ?

Oui. Chaque client IA (Claude Desktop + Cursor par exemple) peut être connecté simultanément avec le même compte.

### Le MCP fonctionne-t-il hors ligne ?

Non. Le serveur MCP est hébergé et nécessite une connexion internet pour accéder à vos données Skult.

### Que peut faire mon agent avec les outils en écriture ?

Les outils update\_alert\_status, update\_alert\_tier et add\_alert\_note modifient directement vos données. Votre agent doit vous demander confirmation avant d'exécuter ces actions — c'est le comportement par défaut de Claude et des principaux agents IA.

## Prêt à connecter votre agent ?

Choisissez votre outil ci-dessus ou contactez-nous si vous avez besoin d'aide.

[contact@skult.ai](mailto:contact@skult.ai)

Clients supportés

Sur cette page