# TLC - Projet - Compte-rendu
Beaugas Charly,
Benveniste Jules

## Etat du projet : fonctionnel


- api : dockerisé et ajouté au docker-compose avec une dépendance sur la bd.
- front : dockerisé, nginx compris, ajouté au docker-compose avec une dépendance sur l'api.
- nginx : configuration faite, nous rencontrons cependant des problèmnes pour l'édition du fichier hosts du container


## Difficultés rencontrées

- Le front ne compilait sur aucune de nos machines et nous avons passé *BEAUCOUP* de temps à essayer de régler ce problème.
- Accès aux vm de la faculté bloqué du 25 au 26/03.


## CD

Nous avions prévu soit d'utiliser Jenkins, soit de créer un repo git vide sur la vm avec un webhook qui pull la branche main quand celle-ci est mise à jour (plus léger puisque nous n'avons pas de CI à implémenter)


## Etat de l'application

- front: fonctionnel;
- api: fonctionnel;
- nginx: fonctionnel - Problème avec la COPY, le fichier ```etc/hosts``` est donc passé par volume.
- letsencrypt: non implémenté;
- ufw: non implémenté;
- chaîne de monitoring: non implémenté;
- keycloak: non implémenté;

 

## Lancer le projet
Aller dans le dossier API (```cd api```)puis exécuter, via votre Terminal de commande, la commande suivante: ```docker-compose up -d```.


Si vous êtes confronté à cette erreur lorsque vous avez effectué la commande **docker-compose**
```Err: CryptographyDeprecationWarning: Python 3.6 is no longer supported by the Python core team.```.
Cela est sans doute dû au deamon docker qui n'est pas lancé, faites la commande suivante: ```sudo docker systemctl start docker```. 

