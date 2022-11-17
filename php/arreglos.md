# Arreglos

Para definir un arreglo en PHP tenemos 2 formas:

```php
// Forma 1
$MiArreglo = [1,2,3];
// Forma 2
$MiArreglo2 = Array(1,2,3);

```

### Arreglos asociativos

Nos permite no solo usar subíndices, nos permite agregarle nombres a las propiedades

<pre class="language-php"><code class="lang-php"><strong>// Se permite dejar la coma en el último item
</strong><strong>$edades = array(
</strong>    "Carlos" => 50,
    "Ana" => 31,
);
echo "La edad de Carlos es {$edades['Carlos']}"

// Opción 2
$personas= array(
    "Carlos" => array(=
        "edad" => 20,
        "apellido" => "Santana"
        ),
    "Ana" => 31,
);
echo "La edad de Carlos es {$edades['Carlos']}"</code></pre>

