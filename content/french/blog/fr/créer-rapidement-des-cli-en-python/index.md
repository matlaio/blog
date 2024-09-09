---
title: "Créer rapidement des CLI en Python"
date: 2024-09-09T23:31:27+02:00
draft: true
categories: ['cli', 'pyhton']
tags: ['cli', 'python', 'script', 'terminal']
---

En tant qu'informaticien, j'ai pour principe d'éviter de faire des tâches redondantes avec un ordinateur.
Je déteste répéter plusieurs fois une même action alors qu'il existe un moyen pour l'automatiser.
Avant de commencer une nouvelle tâche ou demande, je prends toujours un peu de temps pour réfléchir, si cette tâche est ponctuelle ou 
si dans le futur, je serai amener à la refaire.  
Pour le cas d'une demande éphémère (one shot) alors aucune automatisation n'est nécessaire.  
Mais par contre, si je pense qu'il est pertinent d'automatiser alors, je commence une réflexion pour décrire le processus à développer.

Dans cet article, je vais décrire comment je développe rapidement des petits outils CLI (en ligne de commande, pour en anglais command line interface). Il existe un grand de nombre de langages et de bibliothèques pour développer des CLI avec une tendance pour le Go et le Rust. Pour ma part, je vais faire un focus sur le développement avec Python et la bibliothèque native *argparse*. 

Mon objectif est d'avoir un code simple à lire avec un nombre réduit de dépendances. 
La performance ne paraît pas primordiale pour la création de petits outils qui seront pour la plupart exécutés sur un PC.  
Attention pour des scripts à déployer en production avec de potentiels impacts, il faut étudier quel sera langage utilisé sans
négliger les tests unitaire et d'intégration (même pour un CLI, il faut faire des tests).  


## Comprendre la syntaxe des CLI
Sur Linux, j'apprécie travailler avec le terminal car les commandes respectent toutes le même pattern.
Ci-dessous le pattern d'une commande avec le vocabulaire associé :
* la commande. 
Exemple `ls`.
* les options simples. 
Exemple `-l`.
* les options longues. Avoir un mot explicite à la place d'une simple lettre. 
Exemple `--human-readable` (l'option simple existe avec `-h`).
* les options courtes combinées. 
Exemple `-l -a` ou identique à `-la`.
* les options avec paramètres.
Exemple `-I "*.log"` ou identique à `--ignore "*.log"`.
* les arguments. Partie obligatoire ou optionnelle en fonction des commandes. Exemple `my/path`.

Vous avez compris que je me suis basé sur la commande `ls` qui est utilisé pour afficher les informations d'un répertoire et son contenu.
Il est possible de combiner tous le vocabulaire vu ci-dessus en une seule commande : `ls -la --human-readable -I "*.log" my/path`.  

Pour développer des scripts CLI en python, je me base sur ce vocabulaire afin de conserver une logique de fonctionnement universelle.
De plus, le langage python étant permissif pour la création de script, il est important quelques règles dans le but de faciliter l'usage des scripts. Et aussi de pouvoir améliorer après plusieurs semaines de pause sans être perdu dans le code !


## Les options classiques d'un script CLI
Avec l'expérience, on remarque souvent des options identiques dans les CLI. En effet, les options suivantes sont souvent présentes, malgrès qu'aucune règle Linux l'impose :
* `-h --help` pour afficher l'aide.
* `-v --verbose` pour afficher des logs étendus.
* `-d --debug` pour afficher des logs très verbeux. Souvent on retrouve soit l'option `-v` ou `d` mais rarement les deux réunis.
* `-v --version` pour afficher la version. Parfois le `-v`ne sert pas pour le mode verbose mais est utilisé pour afficher la version.

Les options présentées sont des repères pour les utilisateurs. À titre personnel, il m'arrive fréquemment d'utiliser `-h` pour afficher l'aide quand j'ai besoin de comprendre le fonctionnement d'une commande et découvrir les différentes options disponibles.


## Développer son CLI en Python
TODO trouver un exemple.