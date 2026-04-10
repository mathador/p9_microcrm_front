# MicroCRM - Frontend

Ce projet est la partie Frontend de l'application MicroCRM, développée avec Angular 17.

## Prérequis

- Node.js v20+
- npm

##### Dépendances

- [NPM >= 10.2.4](https://www.npmjs.com/)

##### Procédure

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

#### Client

##### Construire l'image

```shell
docker build -t orion-microcrm-front:latest .
```

##### Exécuter l'image

```shell
docker run -it --rm -p 80:80 -p 443:443 orion-microcrm-front:latest
```

L'application sera disponible sur https://localhost.
