# MicroCRM Projet 9 - Gérez un projet d'intégration et de déploiement continue

MicroCRM est une application de démonstration basique ayant pour objectif de servir de socle pour le module "Projet 9 - Gérez un projet d'intégration et de déploiement continue".

L'application MicroCRM est une implémentation simplifiée d'un ["CRM" (Customer Relationship Management)](https://fr.wikipedia.org/wiki/Gestion_de_la_relation_client). Les fonctionnalités sont limitées à la création, édition et la visualisations des individus liés à des organisations.

![Page d'accueil](./screenshots/screenshot_1.png)
![Édition de la fiche d'un individu](./screenshots/screenshot_2.png)

# MicroCRM - Frontend

Ce projet est la partie Frontend de l'application MicroCRM, développée avec Angular 17.

## Prérequis

- Node.js v20+
- npm

### Dépendances

- [NPM >= 10.2.4](https://www.npmjs.com/)

### Procédure

1. (La première fois seulement) Installer les dépendances NodeJS:

   ```shell
   npm install
   ```

2. Démarrer le service de développement:

   ```shell
   npx @angular/cli serve
   ```

Puis ouvrir l'URL http://localhost:4200 dans votre navigateur.

### Exécution des tests

**Dépendances**

- Google Chrome ou Chromium

Dans votre terminal:

```shell
$CHROME_BIN='C:\Program Files\Google\Chrome\Application\chrome.exe'
npm test
```
Le navigateur s'ouvre et affiche les résultats

### Images Docker

#### Construire l'image

```shell
docker build -t orion-microcrm-front:latest .
```

#### Exécuter l'image

```shell
docker run -it --rm -p 80:80 -p 443:443 orion-microcrm-front:latest
```

L'application sera disponible sur https://localhost.
