# documentacionYii


##Configuraciones del template basic

**Iniciar el proyecto en un servidor**

> php -S localhost:8000 -t carpetadelproyecto

##Configuraciones del template advanced

**Configuracion de inicio**

> php init

**Configuracion de la base de datos en la ruta /common/config/main-local.php**

> php yii migrate

**Iniciar el proyecto en un servidor**

> php -S localhost:8000 -t frontend/web

> php -S localhost:8000 -t backend/web


##Configuracion del archivo web/index.php, la cual inicia el framework

**Inluye el framework**

> require(__DIR__ . '/../vendor/yiisoft/yii2/Yii.php');

**Obtiene la configuracion**

> $config = require(__DIR__ . '/../config/web.php');

**Lanzador de la aplicacion**

> (new yii\web\Application($config))->run();


##Configuracion del archivo config/web(basic App) y backend(frontend)/config/main(advanced App)

```php
    <?php
    return [
    'id' => 'crmapp',
    'basePath' => realpath(__DIR__ . '/../'),
    'components' => [
    'request' => [
    'cookieValidationKey' => 'your secret key here',
    ],
    ],];
```