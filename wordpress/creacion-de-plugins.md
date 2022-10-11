# Creación de plugins

1. Crear carpeta en wp-content/plugins, con el nombre del nuevo plugin
2. Crear un archivo php con el nombre del plugin ejemplo:
3. Agregar esta cabecera al archivo: control-academico-full-ol.php

```php
<?php
/*
Plugin Name: Control académico Full Ol
Description: Listado de alumnos y calificaciones
Version: 0.1.0
Author: Graceanax - NBS full ol
Author URI: http://nbs.education
Text Domain: cafl
*/
```

### Estructura de páginas

```
/plugin-name
     plugin-name.php
     uninstall.php
     /languages
     /includes
     /admin
          /js
          /css
          /images
     /public
          /js
          /css
          /images
```

### Funciones importantes

La función de WordPress `plugin_dir_path(`**`FILE`**`)` le permite incluir archivos de su carpeta de complementos, proporcionando la ruta completa al directorio que almacena el nuevo complemento.

```php
// Create a function called "wporg_get_foo" if it doesn't already exist 
if ( ! function_exists( 'wporg_get_foo' ) ) { 
    function wporg_get_foo() { 
        return get_option( 'wporg_option_foo' ); 
    } 
}

// verificar si es admin
if ( is_admin() ) {
    // we are in admin mode
    require_once __DIR__ . '/admin/plugin-name-admin.php';
}
```

{% embed url="https://www.hostinger.com/tutorials/how-to-create-wordpress-plugin" %}
Muy buena documentación de iniciación
{% endembed %}

{% embed url="https://www.hostinger.com/tutorials/debug-wordpress" %}

