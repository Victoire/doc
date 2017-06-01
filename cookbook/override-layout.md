---
cookbook: true
---

# Surcharger le layout

Quand on lance un nouveau site, on a besoin d'ajouter le style du projet, les scripts ainsi que d'ajouter des blocks.
Pour commencer, il faut comprendre l'architecture d'un projet Victoire au niveau des layouts et identifier le rôle des différents fichiers de template:

## Architecture

### 0. VictoireCoreBundle:Layout:base.html.twig

C'est le niveau 0 de l'architecture. Il défini le markup de base de la page et les différents blocks de base à remplir dans les niveaux suppérieurs, il est inutile de trop s'y attarder.

- **html_attr**
- **head**
  - **meta**
  - **head_script**
  - **head_style**
  - **head_icons**
- **container_attributes**
- **container_class**
- **container_attr**
- **body**
  - **body_header**
  - **body_content**
  - **body_footer**
- **foot_script**
- **foot_script_additional**
- **javascript**

### 1. VictoireCoreBundle:Layout:layout.html.twig

C'est le fichier le plus important de l'architecture car il ajoute tout ce qu'il y a de spécifique à Victoire à savoir les scripts.

### 2. VictoireCoreBundle:Layout:defaultLayout.html.twig

Ce fichier est vide de base, il ne sert qu'à définir le layout par défaut de l'application, c'est généralement ce fichier que vous surchargerez pour y mettre votre logique.

## Mécanismes de surcharge

### Modifier le layout par défaut

Créez le fichier `app/Resources/VictoireCoreBundle/Layout/defaultLayout.html.twig` afin de définir le style, le script et le markup commun à toutes les pages communes de votre application.

### Créer un layout personnalisé

Parfois, vous aurez besoin de créer un layout spécifique à une partie de votre application, par exemple, pour l'espace utilisateur qui doit avoir un header particulier.

Il faudra créer le fichier et ajouter le markup ou les slots additionnels comme ceci:

```twig

```

puis il faudra le déclarer dans la configuration de victoire_core:

```yml
victoire_core:
    user_class: "AppBundle\\Entity\\User\\User"
    business_entity_debug: false
    layouts:
        defaultLayout: "Layout par default"
        myUserspaceLayout: "Espace utilisateur"
```

### Est-ce qu'il y a une quelconque interaction avec mon backend ?

> Nope.

Victoire n'amène que le front, tout ce qui se passe dans le backend ne le regarde pas aussi s'il y a des choses à partager, on pourra imaginer le faire via l'utilisation d'`embed` ou d'`include`.
