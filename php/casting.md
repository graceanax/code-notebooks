---
description: Definimos o forzamos que un tipo de dato sea otro tipo de dato
---

# Casting

El _Casting_ es la manera de indicar al interprete de PHP para forzar el cambio de un tipo de dato a otro deseado. Se puede acceder a esta utilidad anteponiendo el _tipo de dato_ entre paréntesis antes de un valor o una variable al momento de la asignación o inicialización.

Las siguientes definiciones ayudan a forzar el cambio de tipos en PHP:

* `(array)` forzado al tipo arreglo
* `(bool)` forzado al tipo booleano
* `(boolean)` forzado al tipo booleano
* `(double)` forzado al tipo ‘punto flotante’
* `(float)` forzado al tipo ‘punto flotante’
* `(int)` forzado al tipo entero
* `(integer)` forzado al tipo entero
* `(object)` forzado al tipo objeto
* `(string)` forzado al tipo ‘cadena de texto’

A continuación, se muestra un par de ejemplos de lo mencionado:

```php
$numerito = "5";
$numerito = (int) $numerito;
var_dump($numerito);

$flag = 1;  // int(1)
$flag = (bool) $flag;  // bool(true)
```
