# cv-terminal

CV interactif sous forme de terminal web — HTML/CSS/JS vanilla, aucune dépendance.

## Présentation

L'idée m'est venue de faire quelque chose d'un peu différent d'un CV classique. Plutôt qu'un PDF, j'ai voulu créer une page web qui imite un terminal Linux, dans laquelle on navigue avec des commandes.

C'est un fichier HTML unique, sans framework, sans build step. Ça se déploie n'importe où.

## Commandes disponibles

| Commande | Description |
|---|---|
| `whoami` | Présentation rapide |
| `cat skills` | Compétences techniques |
| `cat projects` | Projets réalisés |
| `cat formation` | Parcours de formation |
| `git log` | Historique / expériences |
| `kubectl get me` | Vue DevOps du profil |
| `contact` | Coordonnées |
| `help` | Liste toutes les commandes |
| `clear` | Efface le terminal |

## Sécurité

Les entrées utilisateur sont échappées avant insertion dans le DOM — protection contre les injections XSS. Les tentatives d'injection sont détectées et bloquées.

## Déploiement

Le projet est déployé sur Vercel : [baptiste-rabussier.vercel.app](https://baptiste-rabussier.vercel.app)

Pour déployer sa propre version :

```bash
npm i -g vercel
vercel
```

Ou simplement importer le repo dans Vercel via l'interface web, aucune configuration nécessaire.

## CI/CD

Une pipeline GitHub Actions se déclenche automatiquement à chaque push sur `main`.

Elle vérifie trois choses avant de déployer :

| Étape | Outil | Rôle |
|---|---|---|
| Lint HTML | HTMLHint | Vérifie la syntaxe HTML |
| Lint JS | ESLint | Analyse le JavaScript inline |
| Scan sécurité | Trivy | Détecte les vulnérabilités critiques |
| Déploiement | Vercel CLI | Mise en prod si tout est OK |

Si une étape échoue, le déploiement est bloqué.

Le workflow est dans `.github/workflows/ci.yml`.

## Stack

- HTML / CSS / JavaScript vanilla
- Police [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)
- Déployé sur Vercel
- CI/CD via GitHub Actions
