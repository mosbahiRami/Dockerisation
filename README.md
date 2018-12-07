


# SaharaDashboard
Ce présent travail est réalisé dans le cadre du défi: Dockerisation (220) par les membres de l'équipe Bright_side.

Les étapes de création d'un dockerfile :

# stage 1
FROM node:latest as node   ** nous avons utilisé l'image nodeJS
WORKDIR /app               ** nous avons définit le répertoire de travail WORKDIR
COPY . .                   ** nous avons copié le contenu de répertoire pére dans l'image docker
RUN npm install            ** nous avons installé toutes les dépendances mmentionnées dans le fichier package.json
RUN npm run build --prod   

# stage 2
FROM nginx:alpine                                                     ** nous avons utilisé l'image nginx
COPY --from=node /app/dist/SaharaDashboard /usr/share/nginx/html      ** nous avons copié le fichier du projet saharaDashboard dans nginx


Les étapes d'installation :
## Etape 1 :
Il faut tout d'abord accéder au lien https://hub.docker.com/r/rami2018/saharadashboard/ qui présente l'image docker de notre application IoT.
Bien évidemment il faut déjà avoir le docker installé sur votre machine.


## Etape 2 :

Il faut taper cette commande  "docker pull rami2018/saharadashboard" sur le docker CLI afin de télécharger l'image à partir du docker hub.

## Etape 3 :
Il faut taper la commande suivante "docker run --rm -d -p 80:80/tcp saharadashboard:v3" sur le docker CLI qui permet de faire l'exécution de l'image dans un conteneur docker.


## Etape 4 :

C'est la derniére étape qui consiste à affecter une adresse IP automatiquement au conteneur.

Et voilà le projet devient exécutable et prêt à être utilisé.# Dockerisation
