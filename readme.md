# Demo 01 - Introduction au Github Action

## Mise en place
- Initialiser le repo git
- Pousser le repo sur Github 😲
- Créer une action `.github > workflows > first-action.yaml`

## Syntaxe de base 
Fichier `yaml` -> Fichier structuré par tabulation

```yaml
# Nom du workflow
name: example_syntaxe

# Triggers
on:
  workflow_dispatch:
  push: [<branch-name>]

# Travaux à réaliser
jobs:
  <job_name>:
    ...
```

### Triggers
Ensemble des events écoutés
- Manuellement → Bouton pour lancer le traitement
- Push d'un branche
- Etc...

Liste des events [ici](https://docs.github.com/fr/actions/reference/workflows-and-actions/events-that-trigger-workflows)

### Travaux à réaliser
L'ensemble d'action à faire
- Runner -> Machine virtuel "prêtée" par github
- Actions à faire :
  - Script _(Syntaxe qui depend du terminal !!!)_
  - Utilisation d'action _(Ça sera vue plus tard :p)_