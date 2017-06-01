---
cookbook: true
---

# Créer un nouveau widget

Générez un widget en lançant la commande dans le terminal

```
$ php bin/console victoire:generate:widget
```

- Donner le nom du widget (sans préciser widget qui viendra directement à la fin)
- Le code généré permet d’intégrer directement à Packagist
- Définir le répertoire cible (par défaut dans le dossier source du projet)
- Définir le format
- Générer la classe du widget
- Définir les champs de formulaire du widget

On peut vérifier dans le dossier source, le widget est présent et les éléments bien générés
Dans le dossier views, on utilise le parent qui appelle les éléments du formulaire

- Mettre à jour le schéma de données via le terminal

```
$ php bin/console doctrine:schema:update —force
```

- nettoyer le cache pour apporter la traduction
```
$ php bin/console cache:clear
```
Pour l’affichage d’un widget (`show.html.twig`) on peut accéder aux variables du widget directement en faisant `{{variable}}`

Il est également possible de customiser le rendu des formulaires

## Mode Business Entity
Dans le fichier Business Entity, il faut :
- Ajouter le widget en tant qu’annotation aux classes Business Entity
- Ajouter l’annotation BusinessProperty avec le type des classes

Dans le fichier Widget, il faut :
- Ajouter les BusinessProperty à chaque champ du widget

## Heritage
On peut indiquer le niveau de hiérarchie des widgets, qui récupère les infos d’autres widgets
## Créer un nouveau thème
- Créer un nouveau dossier au nom du widget Bundle dans `app/ressources`
- Créer un dossier `views`
- Créer un fichier `showTheme.html.twig` dans lequel on va personnaliser la vue `show.html.twig`
- Nettoyer le cache via la commande suivante
````
$ php bin/console cache:clear
````
Dans Victoire, le thème est alors disponible en cliquant sur le widget en mode Style
