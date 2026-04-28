
## 1. Qu'est-ce qu'une API(Application Programming Interface) REST ?

Une API REST (Representational State Transfer) est un style d'architecture pour concevoir des services web. Elle permet a des applications (frontend, mobile, autres serveurs...) de communiquer entre elles de maniere standardisee via le protocole HTTP/HTTPS.
Elle repose sur des principes simples et standardises pour echanger des donnees, generalement au format JSON ou XML.


### Principes cles de REST (Richardson Maturity Model)
- Client-Server : l'API separe clairement le client (ex.: une app mobile ou un site web) du serveur (ex.: un backend qui stocke les donnees). Les deux communiquent via des requetes HTTP.
- Sans etat (Stateless): chaque requête contient toutes les informations necessaires pour etre comprise par le serveur. Le serveur ne stocke aucune information sur l'etat du client entre deux requetes. pas de session cote serveur.
- Cacheable : les reponses du serveur peuvent etre mises en cache (stockes temporairement) pour ameliorer les perfomances.
- Uniform Interface (Interface uniforme) : Les interactions entre client et serveur doivent suivre des regles standardisees:
                                           - Utilisation des methodes HTTP
                                           - Utilisation des URLs pour identifier les ressources 
                                           - Utilisation des codes de statut HTTP (ex.: 200 pour "OK", 404 pour "Non trouve").
- Layered System (Systeme en couches) : L'API peut etre composee de plusieurs couches (ex.: securite, cache, serveur d'application etc.), mais le client n'a pas besoin de savoir comment ces couches sont organisees.
- Code on Demand (optionnel) : Le serveur peut envoyer du code executable (ex.: JavaScript) au client pour etendre ses fonctionnalites.

### A quoi ca sert?
- Connecter des applications: Par exemple, une appli mobile qui recupere les donnees d'un serveur distant.
- Integrer des services: Comme afficher une carte Google Maps sur un site web.
- Automatiser des taches: Synchroniser des donnees entre deux systemes(ex.: un CRM et un outil de facturation).

### Pourquoi un REST est si populaire ?
- Simple : utilise des standards HTTP existants
- Scalable: Adapte aux apllications qui doivent gerer beaucoup de requetes
- Flexible: Fonctionne avec presque tous les langages de programmation.
---

## 2. Les Methodes HTTP (Verbes HTTP)

Voici les methodes les plus utilisees dans les API REST :

| Methode   | Nom courant     | Utilisation                           |
|-----------|-----------------|---------------------------------------|
| GET       | Lire            | Recuperer une ou plusieurs ressources |
| POST      | Creer           | Creer une nouvelle ressource          |
| PUT       | Remplacer       | Remplacer completement une ressource  |
| PATCH     | Modifier        | Modifier partiellement une ressource  |
| DELETE    | Supprimer       | Supprimer une ressource               |

### Autres methodes utiles :
- HEAD : comme GET mais sans corps de reponse
- OPTIONS : retourne les methodes HTTP autorisees sur une route

---

## 3. Les Routes (Endpoints)

Dans une API REST, une route (ou endpoint) est une URL specifique qui permet d’acceder a une ressource ou a une fonctionnalite particuliere de l'API.
Chaque Route est associee a une methode HTTP (comme GET, POST ...) qui definit le type d'operation a effectuer sur la ressource.

### Exemples concrets avec convention de nommage recommandee

Si tu as une API pour gerer une liste de livres, voici quelques exemples de routes:

GET    /livres             → Recuperer la liste de tous les livres
GET    /livres/42          → Recuperer les details du livre avec l'ID 42
POST   /livres             → Creer ou ajouter un nouveau livre a la liste
PUT    /livres/42          → Mettre a jour les informations du livre avec l'ID 42
DELETE /livres/42          → Supprimer le livre avec l'ID 42.

### A quoi sert une route?

- Identifier une ressource: Chaque route pointe vers une ressource specifique (ex.: un utilisateur, un produit, un article).
- Definir une action: la methode HTTP utilisee (GET, POST, etc...) indique l'action a effectuer (lire , creer, modifier, supprimer).
- Structurer l'API: les routes organisent l'API de maniere logique et previsible.

En resume, une route dans une API REST, c'est comme une adresse qui te permet d'acceder a une fonctionnalite precise de l'API.