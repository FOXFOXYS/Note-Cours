---
marp: true
theme: gaia
_class: lead

---

# **Symfony**

Symfony FrameWork Commands

---

# installer **Symfony**

```
wget https://get.symfony.com/cli/installer -O - | bash
```

# Check des requis de  **Symfony**

```
symfony check:requirements
```

# Cree projet **Symfony**

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
```

# Crée une Entity
```
php bin/console make:entity name
```

---

# Créé une base de donnée **Symfony**
tout d'abord il vous faut crée le crud de vos entity 
```
php bin/console make:crud
```
ensuite validée le shéma 
```
php bin/console doctrine:schema:validate
```
puis regarder le status de votre mapping 
```
php bin/console doctrine:migrations:status
````
---
si tout est ok crée votre fichier de migration 
```
php bin/console make:migrations
```
Et faite votre migration
```
php bin/console doctrine:migrations:migrate
```
# Fictures **Symfony**

Installation du composer fictures
```
composer require --dev doctrine/doctrine-fixtures-bundle
```
---
Crée une fictures ( déja crée dans l'installation du composer)
```
php bin/console make:fictures name
```
chargée une fictures
```
php bin/console doctrine:fictures:load
```
# Commandes Dangereuse **DataBase**
Cette commande remmet a zero les id
(a ne surtout pas faire sur une machine de prod)

---
```
php bin/console doctrine:database:drop --force
```
Ensuite recrée la database 
```
php bin console doctrine:database:create
```
Et re faire la migrations 
```
php bin/console doctrine:migrations:migrate
```

### Update 08/07/2020 Author: Foxy




