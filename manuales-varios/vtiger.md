# Vtiger

1. Cuándo migramos se deben migrar dos archivos por usuario de la carpeta de sesiones `user_privileges` o aparecerá un error que no tenemos permiso. Debe haber 2 archivos para cada usuario: `user-privileges-.php`_y `sharing-privileges-`_`.php`
2. Asignamos permisos a la carpeta de nuevo `chown -R www-data:www-data user_privileges` y `chmod 777 user_privileges`
