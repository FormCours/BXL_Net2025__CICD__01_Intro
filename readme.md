# Demo 01 - Introduction au Github Action

## Part 1 : Syntaxe

### Mise en place
- Initialiser le repo git
- Pousser le repo sur Github 😲
- Créer une action `.github > workflows > first-action.yaml`

### Syntaxe de base 
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

#### Triggers
Ensemble des events écoutés
- Manuellement → Bouton pour lancer le traitement
- Push d'un branche
- Etc...

Liste des events [ici](https://docs.github.com/fr/actions/reference/workflows-and-actions/events-that-trigger-workflows)

#### Travaux à réaliser
L'ensemble d'action à faire
- Runner -> Machine virtuel "prêtée" par github
- Actions à faire :
  - Script _(Syntaxe qui depend du terminal !!!)_
  - Utilisation d'action _(Ça sera vue plus tard :p)_

  
## Part 2 : Variables

### Mise en place
- Nouveau fichier `workflow` 
- Push sur Gihtub
- Utilisation de variable & secrets :
  - Définir une "zone" `env` dans le workflow (Public !)
  - Définir dans les parametres du repo Github
  - Manipuler les variables d'event du workflow (Lié au déclenchement)

### Syntaxe d'utilisation

#### Variable d'env local : 
Utilisation
- Sous linux : `$VAR_NAME`
- Sous Powershell : `$env:VAR_NAME`

#### Variable et secrets dans Github
Aller à `Setting > Secrets and variables > Actions` pour configurer les variables.

Deux types de configuration : 
- Repository: Toujours accessible
- Environment: Accessible si le job utilise `environment: env-name`.

Utilisation
- variables : `${{ vars.VAR_NAME }}`  
- secrets : `${{ secrets.VAR_NAME }}`
