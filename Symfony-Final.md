---
marp: true
theme: gaia
_class: lead
---

# **Symfony**

Symfony FrameWork Commands

---

# Installer **Symfony**

```
wget https://get.symfony.com/cli/installer -O - | bash
```
# Check des requis de  **Symfony**

```
symfony check:requirements
```

# Crée un projet **Symfony**

```
symfony new --version=lts --full projectname
```

---

# Lancée son projet sur le web

```
cd my-project/
symfony server:start
```

# Installer un project **Symfony** exitant 

```
# clone the project
cd projects/
git clone ...
# make composer Install 
cd my-project/
composer install
```
---

# Voir toutes les Commandes **Symfony**

```
php bin/console
```
# Crée un Controller
```
php bin/console make:controller name
                ma:co
```

# Crée une Entity
```
php bin/console make:entity name
                ma:en
```

---
# Créé un Crud
```
php bin/console make:crud
                ma:cr
```

# Crée sa basse de donnée
Tout d'abord validé votre schéma 
```
php bin/console doctrine:schema:validate
                do:sc:va
```
---
puis regarder le status de votre mapping 
```
php bin/console doctrine:migrations:status
                do:mi:st
````
si tout est ok crée votre fichier de migration 
```
php bin/console make:migrations
                ma:mi
```
Et faite votre migration
```
php bin/console doctrine:migrations:migrate
                do:mi:mi
```

---
Si vous avez des fixtures sur votre project symfony
```
php bin/console  doctrine:fixtures:load
                 do:fi:lo
```

# Mettre a jour les fichier css etc..
```
npm run dev 
```
# Fixtures **Symfony**

---
Installation du composer fixtures
```
composer require --dev doctrine/doctrine-fixtures-bundle
```
Crée une fixtures ( déja crée dans l'installation du composer)
```
php bin/console make:fixtures name
                ma:fi
```
Chargée une fictures
```
php bin/console doctrine:fixtures:load
                do:fi:lo
```
---

# Commandes Dangereuse **DataBase**
Cette commande remmet a zero les id
(a ne surtout pas faire sur une machine de prod)

```
php bin/console doctrine:database:drop --force
                do:da:dr
```
Ensuite recrée la database 
```
php bin console doctrine:database:create
                do:da:cr
```
---

Et refaire la migrations 
```
php bin/console doctrine:migrations:migrate
                do:mi:mi
```

# Les Controllers

crée un controller 
```
php bin/console make:controller name
                ma:co
```

---


# Script de Déploiment de Symfony
```
git clone *************
mv nomdudossier nouveaunomdossier
composer install
npm install
php bin/console cache:clear
// passer en mode prod 
// si possible mettre le https
// utiliser letsencrypt
// https://github.com/letsencrypt/letsencrypt
```
---

# Création d'un script Automatisation 

```
#!/bin/bash
php bin/console do:da:dr --force
php bin/console do:da:cr
php bin/console do:mi:mi --no-interaction
# selon le composer utiliser 
php bin/console ha:fi:lo --no-interaction 
```
# Lancée script phpunit
```
bin/phpunit
```
---

# Les Tests **Symfony**
## Installation du composer

```
composer require --dev symfony/phpunit-bridge 
```

## Création du test
```
php bin/console make:unit-test name
```
---

# Les Liens utile pour les tests 
https://github.com/symfony/panther
https://symfony.com/doc/current/testing.html

# Liens VM 
https://docs.docker.com/get-started/
https://www.virtualbox.org/

---