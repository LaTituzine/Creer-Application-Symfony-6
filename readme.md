
# Créer un projet avec Symfony 6

Comment créer une application Symfony 6 avec une base de données.

## Ce dont j'ai besoin

Pour développer une application avec Symfony 6 il faut **PHP 8.1 minimum**, **Composer** et **Symfony CLI**. 
Pour travailler avec une base de données j'utilise le SGBDR MySQL avec Xampp qui me permet également d'avoir PHP.

Liens d'installation :

- [Installer Xampp](https://www.apachefriends.org/fr/index.html)
- [Installer PHP uniquement](https://www.php.net/downloads)
- [Installer MySQL uniquement](https://www.mysql.com/)
- [Installer Composer](https://getcomposer.org/)
- [Installer Symfony CLI](https://symfony.com/download)

Pour vérifier que l'on a tout ce qu'il faut exécuter la commande suivante dans votre terminal :

```
$ symfony check:requirements
```

Pour utiliser la commande symfony il faut avoir au préalable bien installé Symfony CLI sinon elle ne sera pas reconnue.

## Les différentes étapes 

1. **Créer une application avec tous les packages habituellement utilisés via le terminal :**
    ```
    $ symfony new my_project_name --webapp
    ```
2. **Entrer dans son nouveau projet en ligne de commande**
    ```
    $ cd my_project_name
    ```
3. **Démarrer le serveur**
    ```
    $ symfony server:start
    ```
    L'url à laquelle vous pouvez voir l'application est donnée

4. **Vérifier la sécurité de l'application**
    ```
    $ symfony check:security
    ```
5. **Se connecter à MySQL**
    ```
    $ mysql -u root -p
    ```
    Les informations à renseigner dépendent des informations données lors de l'installation de MySQL ou Xampp. La version du server est normalement donnée.

6. **Créer une base de données en ligne de commande**
    ```
    CREATE DATABASE db_name;
    ```
7. **Configurer le fichier .env**
    
    Décommenter et compléter la ligne correspondant à son SGBDR. Ici un exemple pour MySQL
    ```
    DATABASE_URL="mysql://db_user:db_password@127.0.0.1:3306/db_name?serverVersion=server_version&charset=utf8"
    ```

    Si vous êtes connectés en tant que root et que vous n'avez pas précisé de password dans MySQL et que la version du server est la suivante : mariadb-10.4.22. Alors se sera :
    ```
    DATABASE_URL="mysql://root:@127.0.0.1:3306/db_name?serverVersion=mariadb-10.4.22&charset=utf8"
    ```

## Documentation Symfony

- <https://symfony.com/doc/current/setup.html#technical-requirements>
- <https://symfony.com/doc/current/setup.html#running-symfony-applications>
