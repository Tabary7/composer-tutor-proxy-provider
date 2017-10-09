# composer-tutor-proxy-provider

Permets aux differentes applications d'avoir un proxy vers intra-tuteur-api

## Installation

Modifier `composer.json` :

```
{
    // ...
    "require": {
        "etna/tutor-proxy-provider": "1.0.0"
    },
    "repositories": [
       {
           "type": "composer",
           "url": "https://blu-composer.herokuapp.com"
       }
   ]
}
```

## Utilisation

### Déclarer le composant

Le composant `etna/config-provider` met à disposition une classe permettant de faire utiliser ce proxy a notre application.

```
use ETNA\Silex\Provider as ETNAProvider;

class EtnaConfig implements ServiceProviderInterface
{
    public function register(Application $app)
    {
        ...
        $app->register(new ETNAProvider\TutorProxy\TutorProxy());
        ...
    }
}
```
