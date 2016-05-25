
# Comment créer un nouveau critère de personnalisation de contenu (custom content)

## Utilisation de l'objet DataSource

Le système de critères de Victoire repose sur l'objet [*DataSource*](https://github.com/victoire/victoire/Bundle/CriteriaBundle/DataSource/RequestDataSource.php) dont le rôle est de fournir :

- des méthodes qui retournent la valeur qui sert de filtre.
- des paramètres de formulaire qui seront utilisés dans la modale des widgets

## Etude de cas

La version standard de Victoire inclut 2 types de fitres que l'on peut étudier à titre d'exemple :

- un filtre sur la locale (ou language courant) : `_locale`
- un filtre sur le protocole : `scheme` http | https


```php
#Victoire\Bundle\CriteriaBundle\DataSource
<?php

namespace Victoire\Bundle\CriteriaBundle\DataSource;

use Symfony\Component\Form\Extension\Core\Type\ChoiceType;
use Symfony\Component\HttpFoundation\RequestStack;

class RequestDataSource
{
    /**
     * @var RequestStack
     */
    private $requestStack;
    private $availableLocales;

    /**
     * RequestCriteria constructor.
     *
     * @param RequestStack $requestStack
     * @param              $availableLocales
     */
    public function __construct(RequestStack $requestStack, $availableLocales)
    {
        $this->requestStack = $requestStack;
        $this->availableLocales = $availableLocales;
    }

    public function getLocale()
    {
        return $this->requestStack->getCurrentRequest()->getLocale();
    }

    public function getScheme()
    {
        return $this->requestStack->getCurrentRequest()->getScheme();
    }

    public function getLocaleFormParams()
    {
        return [
            'type'    => ChoiceType::class,
            'options' => [
                'choices' => $this->availableLocales,
            ],
        ];
    }

    public function getSchemeFormParams()
    {
        return [
            'type'    => ChoiceType::class,
            'options' => [
                'choices' => [
                    'http'  => 'http',
                    'https' => 'https',
                ],
            ],
        ];
    }
}
```

- La méthode "getLocale" retourne la locale de la requête courante
- La méthode "getLocaleFormParams" retourne le tableau de paramètres nécessaires pour générer un élément de formulaire de type Choice avec les locales activées comme choix.

## Créer un nouveau critère de personnalisation de contenu

Pour cela, il faut donc créer un nouvel objet "DataSource" implémentant chacune des 2 méthodes :

- "getXxx" : définit la valeur Xxx servant de filtre
- "getXxxFormParams" : définit le formulaire intégrant les différentes variables possibles de la valeur Xxx

Pour que cet objet soit reconnu par Victoire comme un _Critère_, il faut le déclarer en tant que service [dans ce fichier](http://github.com/victoire/victoire/Bundle/CriteriaBundle/Resources/config/services.yml) avec le tag suivant :

    tags:
        - { name: victoire_criteria, group: yyy, method: getXxx, alias: xxx }


Le tag propose d'associer un `group` au critère.
Ce groupe est utilisé pour afficher les différents critères par section. Vous êtes libres d'utiliser un groupe déjà existant ou d'en créer un nouveau.

Enfin, n'oubliez pas de réaliser les traductions des variables dans le [fichier de ressources](http://github.com/victoire/victoire/Bundle/CriteriaBundle/Resources/translations/)
