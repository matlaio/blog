---
title: "Signer ses commits sur Git avec GPG"
date: 2024-09-06T18:30:14+02:00
draft: false
categories: ['git', 'sécurité']
tags: ['git', 'sécurité', 'bash', 'terminal', 'gpg']
---

Lors du `push`, le serveur Git demande vos informations pour s'authentifier. Plusieurs méthodes d'authentification existent :
* via login/password
* via token
* via clé SSH

Ces trois méthodes authentifient l'utilisateur afin de pouvoir récupérer son profil Git (droit de push, droit de merge...).

Cependant, les projets communautaires avec des milliers de commits sont victimes de convoitises pour introduire du code malicieux.
L'une des surfaces d'attaque est de réussir à 'voler' l'authentification de l'utilisateur.  
Par exemple, subtiliser le token d'un utilisateur avec le rôle *admin*. Cet admin peut valider et *push* du code sur la branche *master*.
Puis, le pirate pourra créer et publier une nouvelle version du projet, par exemple en compromettant un package Python sur *pip*.

L'une des solutions visant à réduire la surface d'attaque est de signer ses commits.  
La signature des commits permet de s'assurer que le code provient bien de l'utilisateur à l'origine du commit. Le mécanisme de signature utilisé est GPG.
Pour ce faire, il est nécessaire de créer la clé privée et la clé publique associée.  
La clé privée est utilisée pour signer le commit, tandis que la clé publique doit être soumise au serveur Git (Github, Gitlab...), 
afin que le serveur puisse vérifier la signature du commit avec la clé publique.

## Configurer son environnement
Les pré-requis suivants sont nécessaires :
* Git
* GPG (installer avec Git Bash sur Windows)

Nous utiliserons un terminal pour réaliser les différentes étapes.  
Sur Windows, il est préférable d'utiliser Git Bash, car sinon vous risquez d'avoir des problèmes avec la configuration de GPG et Git. 
Par défaut Git cherche les clés dans le répertoire `%USERPROFILE%\.gnupg`, tandis que GPG via Powershell/Console lit le répertoire  `%USERPROFILE%\AppData\Roaming\gnupg`

Les étapes suivantes couvrent la création jusqu'au *push* du premier commit signé :

## Créer la clé GPG
```bash
$ gpg --full-generate-key
```
* utiliser RSA par défaut.
* choisir 4096 bits pour accroître la robustesse.
* l'expiration à 0 pour avoir une clé valide sans date de péremption. Sinon pour 12 mois alors mettre 12m.
* renseigner le nom de la clé, par exemple le nom du compte Git.
* le mail doit être le même que celui de l'utilisateur Git.
* valider puis saisir le mot de passe.

{{< notice "tip" >}}
Je recommande de garder précieusement votre mot de passe dans un endroit sécurisé comme un gestionnaire de mot passe.  
Attention, il n'existe aucun moyen de retrouver le mot de passe perdu d'une clé !
{{< /notice >}}

## Créer un backup de la clé
Cette étape est facultative, mais est recommandée afin de conserver sa clé en sécurité dans un autre endroit autre que son PC.
Récupération de la clé :
```bash
$ gpg --list-secret-keys --keyid-format LONG
```
Cette commande renvoie la liste des clés existantes avec les identifiants associés.

Dans l'exemple ci-dessous utiliser l'identifiant de clé longue (souligné BA286856AF0B6AE8E5B7D2A9CB229937293F6BD7).

{{< highlight go "hl_lines=8, linenostart=199" >}}
$  gpg --list-secret-keys --keyid-format LONG
gpg: checking the trustdb
gpg: marginals needed: 3  completes needed: 1  trust model: pgp
gpg: depth: 0  valid:   2  signed:   0  trust: 0-, 0q, 0n, 0m, 0f, 2u
/c/Users/mat/.gnupg/pubring.gpg
-------------------------------
sec   rsa4096/CB229937293F6BD7 2024-09-07 [SC]
      BA286856AF0B6AE8E5B7D2A9CB229937293F6BD7
uid                 [ultimate] moncomptegi (clé pour git) <addressemailducompte@git.com>
ssb   rsa4096/8DAD0CE415B39CFE 2024-09-07 [E]
...
{{< / highlight >}}


Exporter la clé privée :
```bash
gpg --armor --export <ID clé> > public_key.asc
```

Exporter la clé privée :
```bash
gpg --armor --export-secret-keys  <ID clé> > private_key.asc
```

{{< notice "tip" >}}
Garder la clé privée que pour vous. Elle ne doit jamais être partagée.  
De mon côté, je la stocke dans le gestionnaire de mot de passe KeePassXC.
{{< /notice >}}


### Ajouter la clé privée dans sa configuration Git
Maintenant, nous devons configurer Git pour qu'il utilise la bonne clé privée afin de signer les commits.
Je recommande de renseigner la clé GPG uniquement avec le profil local de Git.
C'est-à-dire que la clé est seulement utilisée pour le répertoire Git concerné et non en global sur l'ensemble du PC.
Cette configuration permet de jongler facilement entre plusieurs comptes Git et projets Git.

Avant d'associer la clé, il est nécessaire de se placer dans le répertoire du projet Git.
```bash
$ cd <mon projet git>
$ git config --local user.signingkey <ID clé>
```

Activation du GPG sur Git :
```bash
git config --local commit.gpgsign true
```

### Tester et vérifier la signature d'un commit
Encore une fois, placer son terminal dans le projet Git.  
Modifier un fichier et commit les changements.  
Saisir le mot de passe de la clé privée dans la fenêtre qui apparaît. Vous devez saisir le mot de passe de la clé.
```bash
git add myfile.txt
git commit -m "Test GPG"
```

Vérifier le commit dans l'historique.
```bash
git log --show-signature
```

La commande affiche que le commit a été signé et que cette signature est valide.
```bash
$ git log --show-signature
commit bb9ee688485e4f12fcfb5cde059921d1ce377b68 (HEAD -> master)
gpg: Signature made Sat Sep  1 19:22:28 2024
gpg:                using RSA key BA286856AF0B6AE8E5B7D2A9CB229937293F6BD7
gpg: Good signature from "moncomptegi (clé pour git) <addressemailducompte@git.com>" [ultimate]
Author: moncomptegit <userlocal>
Date:   Sat Sep 1 19:22:28 2024 +0200
```
Dans cet exemple, le commit a été signé, puis la l'option `show-signature` a validé la signature.


### Associer la clé à son compte (Github, Gitlab, Gitea...)
La clé publique doit être associée à son compte sur le serveur Git. Cela permettra au serveur de valider tous vos commits.  
Cette étape est simple à réaliser, il suffit se référer à la documentation de Github, Gitlab...  

Dans un premier temps, il faut récupérer ça clé publique. Ne pas envoyer (et jamais) envoyer la clé privée.
```bash
gpg --armor --export <ID clé>
```
Copier l'ensemble de la clé publique (inclus la ligne début `----- Begin PGP ...` et la ligne de fin `-----END PGP ...` )
Exemple de copie (tronqué volontairement) :
```bash
$ gpg --armor --export BA286856AF0B6AE8E5B7D2A9CB229937293F6BD7
-----BEGIN PGP PUBLIC KEY BLOCK-----

mQINBGbcK6QBEACh6bkHfr+r2M9o/WeFSPk8J3dg/XAE+1xY24H7vLN4SCXx0jcU
i60uqCyw+JhI8I2CtCggoM39Goe6B4lfULcvbRPwIAbf321f13YoldL8aI/qXiLb
gXFxlVgzfPF4+fypafbZKfu6rV/Y+bEQNCb/LDppua2anu3bkgZGcbrA0Mqq0W0w
FrGK3W3nqCvkC5qB4E8S1i025hJEoBwaB1Y5XlwIs8hSrTz4LDm+L52zSsJ5OhVW
....
-----END PGP PUBLIC KEY BLOCK-----

```

Enfin, cette clé publique doit être ajoutée à votre compte Git.  
Sur vos prochains commits, Git affichera que le commit est vérifié.

## Conclusion
Dans cet article, nous avons vu comment configurer GPG. Cette configuration est simple à appliquer et rapidement de nombreux bénéfices.
En effet, la sécurité de vos commits est augmentée grâce à la signature et le serveur Git est capable de vérifier que la signature 
correspond bien à votre profil. Enfin, la signature est applicable localement à un projet avec `--local` ou globalement avec `--global` en fonction des usages multicomptes ou mono comptes Git. 