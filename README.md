cv-terminal
CV interactif sous forme de terminal web — HTML/CSS/JS vanilla, aucune dépendance.
Présentation
L'idée m'est venue de faire quelque chose d'un peu différent d'un CV classique. Plutôt qu'un PDF, j'ai voulu créer une page web qui imite un terminal Linux, dans laquelle on navigue avec des commandes.
C'est un fichier HTML unique, sans framework, sans build step. Ça se déploie n'importe où.
Commandes disponibles
CommandeDescriptionwhoamiPrésentation rapidecat skillsCompétences techniquescat projectsProjets réaliséscat formationParcours de formationgit logHistorique / expérienceskubectl get meVue DevOps du profilcontactCoordonnéeshelpListe toutes les commandesclearEfface le terminal
Sécurité
Les entrées utilisateur sont échappées avant insertion dans le DOM — protection contre les injections XSS. Les tentatives d'injection sont détectées et bloquées.
Déploiement
Le projet est déployé sur Vercel : baptiste-rabussier.vercel.app
Pour déployer sa propre version :
bashnpm i -g vercel
vercel
Ou simplement importer le repo dans Vercel via l'interface web, aucune configuration nécessaire.
Stack

HTML / CSS / JavaScript vanilla
Police JetBrains Mono
Déployé sur Vercel
