# Operadores

### Operadores lógicos

Son los operadores que nos ayudan a combinar dos o mas afirmaciones para definir si una oración es cierta o falsa. Su uso esta basado en tablas de verdad.![](<../.gitbook/assets/image (2).png>)

<pre class="language-php"><code class="lang-php">// AND
$valor1 and $valor2
$valor1 &#x26;&#x26; $valor2

// Or
$valor1 or $valor2
$valor1 || $valor2

// Not
<strong>NOT $valor1
</strong><strong>!$valor1</strong></code></pre>

### Operadores aritméticos

![](<../.gitbook/assets/image (1).png>)

### Operadores relacionales

Nos ayudan a comparar dos o más valores



| `==`  | _Igual a_           |
| ----- | ------------------- |
| `===` | _Idéntico a_        |
| `!=`  | _Diferente de_      |
| `<>`  | _Diferente de_      |
| `!==` | _No idéntico a_     |
| `>`   | _Mayor que_         |
| `>=`  | _Mayor o igual que_ |
| `<`   | _Menor que_         |
| `<=`  | _Menor o igual que_ |
| `<=>` | _Nave espacial_     |
| `??`  | _Fusión de null_    |

#### Operador nave espacial

El operador nave espacial se emplea para comparar dos expresiones. Devuelve -1, 0 o 1 cuando $a es respectivamente menor, igual, o mayor que $b.

```php
// Números enteros
echo 1 <=> 1; // 0
echo 1 <=> 2; // -1
echo 2 <=> 1; // 1

// Números decimales
echo 1.5 <=> 1.5; // 0
echo 1.5 <=> 2.5; // -1
echo 2.5 <=> 1.5; // 1
 
// Cadenas de caracteres
echo "a" <=> "a"; // 0
echo "a" <=> "b"; // -1
echo "b" <=> "a"; // 1
```

#### Fusión de null

```php
// Si la edad de juanito no esta definida, dame la de pepito
$Edad_de_pepito = 23;
echo $Edad_de_juanito ?? $Edad_de_pepito;
```

### Otros operadores

| Operador | Descripción      |
| -------- | ---------------- |
| `=`      | _Asignación_     |
| `+=`     | _Incremento_     |
| `++`     | _Incremento_     |
| `-=`     | _Decremento_     |
| `--`     | _Decremento_     |
| `*=`     | _Multiplicación_ |
| `/=`     | _División_       |
| `.=`     | _Concatenación_  |

### Precedencia de operadores

¿Primero suma y luego asigna? o ¿Primero asigna y luego suma

```php
$contador = 0;
$nuevo_valor = $contador++;
```

Primero asigna y luego suma
