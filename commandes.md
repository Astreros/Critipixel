# Liste des commandes de base

## Base de données

### Configuration :
Configuration du fichier `.env` et création de `.env.local`:
```dotenv
DATABASE_URL="mysql://root@127.0.0.1:3306/!NOM_BASE_DE_DONNEES!?serverVersion=10.4.28-MariaDB&charset=utf8mb4"
```

### Supprimer la base de données
Suppression de la base de données
```bash
symfony console doctrine:database:drop --force --if-exists
```
Suppression de la base de données de test
```bash
symfony console doctrine:database:drop --env=test --force --if-exists
```

### Création de la base de donnée :
Création de la base de donnée
```bash
php bin/console doctrine:database:create
```
Création de la base de donnée d'environnement de test
```bash
php bin/console doctrine:database:create --env=test
```

### Créer les migrations :
Création des migrations
```bash
php bin/console make:migration
```

### Exécuter les migrations :
Exécution des migrations
```bash
php bin/console doctrine:schema:update --force
```
Exécution des migrations d'environnement de test
```bash
php bin/console doctrine:schema:update --env=test --force
```

## Fixtures :
Chargement des fixtures
```bash
php bin/console doctrine:fixtures:load
```
Chargement des fixtures d'environnement de test
```bash
php bin/console doctrine:fixtures:load --env=test
```

## Caches :
Vider le cache de l'environnement de développement :
```bash
php bin/console cache:clear
```