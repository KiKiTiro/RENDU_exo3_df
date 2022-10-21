Bonjour Christophe,

Dans ce dossier vous trouverez mon rendu pour l'exo3.

- Dans le dossier docker la partie faite sur VM (Dockerfile, docker-compose). Afin d'importer la base de donnée dans le serveur mariadb nous avons executer ses 3 commandes:

docker cp students.sql Docker_mariadb_1:/tmp
docker exec -it Docker_mariadb_1 bash
mysql -p < /tmp/students.sql

- Dans le dossier k8s la partie faite sur Windows, pour cela nous avons lancer minikube et son dshboard:

minikube start
minikube dashboard

Malheureusement je suis resté bloquer au provisionnement de mariadb, en effet son pod reste pending pour un probléme de persistant volume claim. Il semble qu'elle pense son pvc unbound. Il est aussi possible que je n'ai pas donner assez de cpu à minikube pour soutenir cette infra.
(voir images dans le dossier README)