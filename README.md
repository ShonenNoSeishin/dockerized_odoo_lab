# dockerized_odoo_lab

## Introduction

Ce projet github reprend le projet https://github.com/odoocker et explique comment créer programmer de nouveaux modules odoo sur une instance locale.

-

This github project takes over from https://github.com/odoocker and explains how to create new odoo modules on a local instance.

## Etapes de mise en place - initialisation steps

````bash
# cloner le repo git
git clone git@github.com:odoocker/odoocker.git
# aller dedans
cd odoocker
# créer un fichier env à partir de celui de base
cp .env.example .env && cp docker-compose.override.local.yml docker-compose.override.yml
# lancer le conteneur 
docker-compose up -d
````

## Configuration sur l'interface web - configuration via web interface

Aller sur l'interface web via localhost:8069 et configurer l'accès (le mdp pour les accès à la base de données sont dans le fichier .env s'il faut)

## Création d'un nouveau module - new addon creation

````bash
sudo docker exec -it --user root <nom du conteneur> odoo scaffold <New_module_name> /usr/lib/python3/dist-packages/odoo/custom-addons
````

Le nouveau module sera alors créé dans le conteneur mais vous pourrez le voir au niveau de la machine dans custom-addons grâce au volume partagé. Il sera ensuite aisé de programmer directement sur votre machine. 

-

The new module will then be created in the container, but you'll be able to view it at machine level in custom-addons thanks to the shared volume. It will then be easy to program directly on your machine.

