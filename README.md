# Documentacion de Yii2


##Configuraciones del template basic

**Iniciar el proyecto en un servidor**

> php -S localhost:8000 -t carpetadelproyecto


##Descripcion de las carpetas en el template basic

**assets**

> Incluye los archivos .js y .css referenciados en la pagina web y que dependen de la app

**commands**

> Esto incluye los controladores usados en la linea de comandos

**config**

> Esto incluye los controladores usados en la pagina web

**mail**

> Es el repositorio de las plantillas de los correos

**models**

> Esto incluye los modelos usados en toda la app

**runtime**

> Estos es usado desde yii2 para almacenar en tiempo de ejecucion los datos como logs

**test**

> Esto es un repositorio de todos los test(Unitarios, funcionales, entre otros)

**vendor**

> Esto incluye el repositorio de modulos externos, administrador por Composer

**views**

> Esto contiene las vistas que son renderizadas por los controladores

**web**

> Es el punto de entrada para la pagina web


##Configuraciones del template advanced

**Configuracion de inicio**

> php init

**Configuracion de la base de datos en la ruta /common/config/main-local.php**

> php yii migrate

**Iniciar el proyecto en un servidor**

> php -S localhost:8000 -t frontend/web

> php -S localhost:8000 -t backend/web


##Configuracion del archivo web/index.php, el cual inicia el framework

**Inluye el framework**

> require(__DIR__ . '/../vendor/yiisoft/yii2/Yii.php');

**Obtiene la configuracion**

> $config = require(__DIR__ . '/../config/web.php');

**Lanzador de la aplicacion**

> (new yii\web\Application($config))->run();


##Configuracion del archivo config/web(basic App) y (backend o frontend)/config/main(advanced App)

> Id: Es el nombre de la aplicacion.

> basePath: Permite encontrar el directorio en donde se encuentra yii alojado.

> cookieValidationKey: Es la clave privada para validar a los usuarios que utilizan el recordarme en la app.

```php
    <?php
    return [
        'id' => 'crmapp',
        'basePath' => realpath(__DIR__ . '/../'),
        'components' => [
        'request' => [
        'cookieValidationKey' => 'your secret key here',
        ],
        ],
    ];
```

##Activar el UrlManager para las urls limpias

> Debemos ir a la carpeta config\web y busca la linea donde sale comentado el UrlManager y descomentarla para poder empezar a utilizar la funcionalidad


##Definiendo un Controller

> Los controllers deben tener como minimo el namespace \app\controllers; y el use \yii\web\Controller;

> La llamada al controlador mediante la url es: http://host/controller/action

```php
    <?php namespace app\controllers;
    
    use \yii\web\Controller;
    
    class SiteController extends Controller
    {
        public function actionIndex()
        {
        return 'Our CRM';
        }
    }
```



