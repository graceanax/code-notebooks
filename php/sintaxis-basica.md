# Sintaxis básica

1. La etiqueta de cierre no es obligatoria a menos que vayamos a combinar con HTML

### Concatenación

Usa comillas sencillas cuando solo vas a imprimir texto

```php
echo "Yo me llamo ".$nombre." ".$apellido;
```

Si necesitas usar variables usa comillas dobles, ya que puede leer variables dentro del texto

```php
echo "Yo me llamo $nombre $apellido \n"
```

### Debugging y comentarios

Para hacer debugging podemos utilizar dos formas:v

```php
// da más información
var_dump( $variable );
// se ve más legible
print_r( $variable );
```
