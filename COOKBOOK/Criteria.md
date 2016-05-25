
# Comment créer un nouveau critère de Personnalisation de contenu (custom content)

Le système de critères de victoire repose sur un objet "DataSource".
Cet objet à le rôle de fournir des paramètre de formulaire qui seront utilisés dans la modale de Widget, ainsi que des méthodes qui ont pour rôle de retrouner la valeur sur laquelle filtrer.

Un exemple simple est implémenté dans victoire pour filtrer sur la langue courante (`_locale`) et sur le protocole (`scheme` http | https) dans l'objet `Victoire\Bundle\CriteriaBundle\DataSource`

On peut voir qu'il a une méthode "getLocale" qui retourne la locale de la requête courante, ainsi qu'une méthode "getLocaleFormParams" qui retourne le tableau de paramètre nécessaire pour générer un élément de formulaire de type Choice avec les locales activées comme choix.

Pour ajouter un nouveau critère, il faut donc créer un nouvel objet "DataSource" implémentant une méthode "getXxx" ainsi qu'une méthode "getXxxFormParams".
Pour que cet objet soit reconnu par Victoire comme un Critère, il faut le déclarer en tant que service avec le tag suivant:

    tags:
        - { name: victoire_criteria, group: yyy, method: getXxx, alias: xxx }


Le tag propose d'associer un `group` au critère.
Ce groupe est utilisé pour afficher les différents critères par section. Vous êtes libres d'utiliser un groupe déjà existant ou d'en créer un nouveau.
