## Bonnes pratiques Restful API | Java | Spring Boot
Dans ce repo, je vous partage quelques bonnes pratiques Restful API Java | Spring Boot.

*Notez que je suis toujours dans le processus d'apprentissage - probablement sans fin :)-*

### Qu'est-ce que REST ?
---
C'est l'abréviation de Representational State Transfer.

L'API REST transfère une représentation d'une ressource (données) qui réside sur le serveur (dans la base de données) au client. La représentation peut être sous forme de JSON, XML ou même HTML.

Les données transférées par l'API REST sont organisées selon une conception. On peut donc dire que REST est une architecture de données.

L'API REST se compose de six contraintes :
- **Architecture Client — Serveur** — Cette règle assure la séparation des préoccupations. Le client gère les problèmes d'interface utilisateur tandis que le serveur gère les problèmes de persistance des données. En retour, nous obtenons un système hautement portable où une fois l'API REST peut gérer différents clients.
- **Statelessness** — Aucune donnée client ne peut être stockée sur le serveur entre les requêtes. Si l'état du client est pertinent pour les requêtes, il doit être envoyé avec les requêtes. Si le serveur doit enregistrer les sessions client, il doit être enregistré dans une base de données pendant une période donnée.
- **Capacité de mise en cache** — Toutes les réponses doivent être marquées comme pouvant être mises en cache ou non. Si la réponse peut être modifiée en permanence, nous ne devons pas les mettre en cache. La capacité de mise en cache est importante pour les performances de l'API REST. 
- **Système en couches** - Le client ne peut pas savoir / ne devrait pas se soucier s'il s'est directement connecté au serveur d'origine ou à l'intermédiaire en cours de route. Cela signifie que REST vous permet d'avoir une architecture système en couches et que la demande peut être envoyée via différentes couches. Cela contribue à la sécurité et à l'évolutivité (CDN, serveur d'autorisation).
- **Code à la demande** — L'API REST peut transférer des fichiers JavaScript exécutables et des composants compilés vers le client en cas de besoin.
- **Interface uniforme** — Comme son nom l'indique, il devrait y avoir une interface pour les ressources qui sont exposées aux clients API. Une ressource dans le serveur ne doit avoir qu'un seul URI logique pour récupérer ou manipuler la ressource.

**Qu'est-ce que l'API RESTful ?** — L'API REST peut être dérivée à l'aide de nombreux protocoles (Ex : HTTP, FTP). En pratique une API qui suit les contraintes REST + HTTP (utilisation des méthodes HTTP) s'appelle RESTful API.
Ainsi, si vous souhaitez implémenter un service,
- basé sur une architecture client-serveur
- et souhaitez servir différents clients via le protocole HTTP
- et souhaitez utiliser les contraintes REST décrites ci-dessus

vous pouvez sélectionner l'architecture RESTful pour votre service.

### Qu'est-ce que la conception d'API ?
---
La conception d'API fait référence au processus de développement d'interfaces de programmation d'applications (API) qui exposent des données et des fonctionnalités d'application à l'usage des développeurs et des utilisateurs.

### Meilleures pratiques de conception d'API
---
En général, une conception d'API efficace aura les caractéristiques suivantes :
- Facile à lire et à utiliser 
- Difficile à abuser
- Complet et concis

Voici quelques recommandations générales :
- 𝗨𝘀𝗲 𝗻𝗼𝘂𝗻𝘀 𝗶𝗻𝘀𝘁𝗲𝗮𝗱 𝗼𝗳 𝘃𝗲𝗿𝗯𝘀
- 𝗨𝘀𝗲 𝗽𝗹𝘂𝗿𝗮𝗹 𝗿𝗲𝘀𝗼𝘂𝗿𝗰𝗲 𝗻𝗼𝘂𝗻𝘀 
- Être cohérent
- 𝗞𝗲𝗲𝗽 𝗶𝘁 𝘀𝗶𝗺𝗽𝗹𝗲
- 𝗨𝘀𝗲 𝗽𝗿𝗼𝗽𝗲𝗿 𝘀𝘁𝗮𝘁𝘂𝘀 𝗰𝗼𝗱𝗲𝘀
	- 200 pour succès général
	- 201 pour création réussie
	- 202 (Accepté)
	- 400 pour requêtes incorrectes
	- 401 pour requêtes non autorisées
	- 403 pour autorisations manquantes
	- 404 pour ressources manquantes
	- 5xx pour erreurs internes
- 𝗗𝗼𝗻'𝘁 𝗿𝗲𝘁𝘂𝗿𝗻 𝗽𝗹𝗮𝗶𝗻 𝘁𝗲𝘅𝘁
- Noms d'attributs en camelCase
- Mettez les données en cache pour améliorer les performances
- 𝗗𝗼 𝗽𝗿𝗼𝗽𝗲𝗿 𝗲𝗿𝗿𝗼𝗿 𝗵𝗮𝗻𝗱𝗹𝗶𝗻𝗴
- 𝗛𝗮𝘃𝗲 𝗴𝗼𝗼𝗱 𝘀𝗲𝗰𝘂𝗿𝗶𝘁𝘆 𝗽𝗿𝗮𝗰𝘁𝗶𝗰𝗲𝘀
	- Utilisez OAuth2 pour sécuriser votre API.
	- Utilisez un jeton Bearer à expiration automatique pour l'authentification ( Authorisation: Bearer f0ca4227-64c4-44e1-89e6-b27c62ac2eb6).
	- Exiger HTTPS.
	- Envisagez d'utiliser des jetons Web JSON .
	- Appliquez l'utilisation des en-têtes Content-Type et Accept-Type même si vous utilisez JSON par défaut pour les requêtes et les réponses.
- Utiliser pagination
- Versionner les API
- D𝗼𝗰𝘂𝗺𝗲𝗻𝘁er les 𝗔𝗣𝗜 (ex: Swagger, OpenAPI)
- Les API sont également conformes à la norme HATEOAS car elle facilite la vie des consommateurs de votre API
- Implémenter et surveiller un non mis en cache `/health` endpoint, par exemple GET `/api/health`

*Bon apprentissage... Bon codage...*

[Source d'article](https://connect2grp.medium.com/restful-756145aa751c)