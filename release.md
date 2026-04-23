# Politique de Versioning

Ce document décrit la politique de versioning utilisée pour ce projet, basée sur la spécification SemVer (Semantic Versioning) : MAJOR.MINOR.PATCH.

## Format des Versions

Les versions suivent le format `MAJOR.MINOR.PATCH`, où :
- **MAJOR** : Changements incompatibles (breaking changes)
- **MINOR** : Nouvelles fonctionnalités compatibles
- **PATCH** : Corrections de bugs et améliorations mineures

## Déclenchement des Releases

### Doit-on créer une release candidate pour chaque commit ?

Non, nous ne créons pas de release candidate pour chaque commit. Les release candidates sont réservées aux versions préliminaires majeures ou mineures avant leur publication finale. Pour les versions PATCH, nous procédons directement à la release.

### Est-ce que la release implique une action humaine ?

La release est principalement automatique grâce au workflow GitHub Actions `release.yml`. Elle se déclenche automatiquement sur les push vers la branche `main` lorsque des commits conventionnels sont détectés. Cependant, il est possible de déclencher manuellement une release via l'interface GitHub Actions en spécifiant le type de release (major, minor, patch).

### Crée-t-on des branches différentes pour chaque release ?

Non, nous n'utilisons pas de branches différentes pour chaque release. Toutes les releases sont taguées directement sur la branche `main`. Cette approche simplifie le workflow et évite la prolifération de branches de release.

## Commits Conventionnels

Pour que semantic-release fonctionne correctement, les commits doivent suivre le format conventionnel :

- `feat:` pour les nouvelles fonctionnalités (incrémente MINOR)
- `fix:` pour les corrections de bugs (incrémente PATCH)
- `BREAKING CHANGE:` pour les changements incompatibles (incrémente MAJOR)

Exemples :
- `feat: add user authentication`
- `fix: resolve login issue`
- `feat!: redesign API (BREAKING CHANGE)`

## Workflow de Release

1. Les développeurs poussent des commits conventionnels sur `main`
2. Le workflow CI vérifie les tests et le build
3. Si les commits incluent des changements, semantic-release :
   - Analyse les commits
   - Détermine la nouvelle version
   - Crée un tag Git
   - Génère les notes de release
   - Publie la release sur GitHub avec les artefacts

## Artefacts Générés

Chaque release inclut :
- L'application compilée (dist/)
- Archive tar.gz
- Archive zip
- Notes de release automatiques