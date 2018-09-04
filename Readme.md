¿Que es PHP?

PHP es un lenguaje de programación de propósito general de alto nivel que fue diseñado especialmente para el desarrollo de aplicaciones web.

Es interpretado, multiplataforma, open source, el cual ha sido muy popular en los últimos años.

Que si es!!!

- Es un lenguaje interpretado, necesitas un interprete de php en la pc para ejecutarlo
- Es un lenguaje multiplataforma (Win, linux, MacOS)
- Es open source, el codigo fuente esta disponible!
- Tienes muchas integraciones

Que no es!!

- No es lenguaje compilado (codigo+interprete)
- No esta hecho para crear app desktop

[Documentación oficial](http://php.net/manual/es/)

# Herramienta

XAMMP - [Desargar](https://www.apachefriends.org/es/index.html)


VSCode 

[Keyboard shortcuts for macOS](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)

[Keyboard shortcuts for Windows ](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)

[Keyboard shortcuts for Linux](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf)

# Template que usaremos

Favor de ver la carpeta: **Template**

# Sintaxis de PHP

Hagamos el ejemplo más sencillo para trabajar con PHP. Siempre que usemos PHP usaremos lo siguiente: `<?php ?>` todo lo que pongamos dentro de esto será lo que el servidor va a interpretar como código php, lo que esté fuera lo ignorará.

Para acceder a él lo haremos `localhost:8080/hello.php` porque el servidor abre por defecto el archivo index y nuestro nuevo archivo se llama hello.php.

Es importante que un archivo que contiene código php tenga la extensión `.php`.
Todas las sentencias de código se separarán con un ';' (punto y coma).

# Variables tipos de datos y cadenas

Una variable puede ser una pequeña cajita en la que puedes almacenar un valor y este lo pueden usar para realizar alguna opración.

Para declararla usarmos el símbolo de `$` y en seguida el nombre, este puede ser un `_` o una `letra`.

PHP no es estáticamente tipado, es decir que no tenemos que decirle qué tipo de dato es esa variable. Además es débilmente tipado porque podemos fácilmente cambiar el tipo de dato, es decir PHP ejecuta una conversión de datos interna.

En PHP Tenemos dos tipos de cadenas, las que son simples y las que son dobles.

Las variables en PHP son dinamicas, es decir que pueden cambiar su valor durante el codigo.

```
<?php
$name = 'Soter Ramirez';
?>
```

```
 <h1><?php echo $name; ?></h1>
```

Para concatenar variables y etiquetas html usamos `.`

Ejemplo

```
echo "mi nombre es" . $var_nombre . "<br>";
```

# Tipos de datos en PHP

PHP cuenta con muchos tipos de datos, sin embargo en este momento nos vamos a enfocar en los mas importantes y utilizados que son boolean, integer, float, string, array y NULL.

## Tipos escalares

- boolean:
  Representa solamente un valor verdadero o falso. Valores válidos: true (verdadero) false (falso)

[Documentación](http://php.net/manual/es/language.types.boolean.php)

```
true;
$b = false;
?>
```

- Integer: Representa un numero entero positivo, negativo o 0.

http://php.net/manual/es/language.types.integer.php

```
123;
$b = 0;
$c = 7763;
?>
```

- float o double: Representa un número de punto flotante, existen problemas de precisión con los números flotantes debido a la naturaleza binaria de las computadoras.

http://php.net/manual/es/language.types.float.php

```
12.24;
$b = 1.5e3;
$c = 7E-10;
?>
```

- string:

  - Representa una cadena de caracteres.
  - Existen 4 formas de representar una cadena. Las 2 principales son usando comillas simples o comillas dobles.
  - Usando comillas simples donde el texto será exactamente como se escribe.
  - Usando comillas dobles permite usar caracteres de escape y además expanden los nombres de las variables, es decir sustituye el valor de las variables dentro de las cadenas.
  - Hay 2 formas adicionales llamadas Heredoc y Nowdoc que sirven para crear cadenas de múltiples líneas.

## Tipos compuestos

- array:
Representa una coleccion de valores, aunque por defecto PHP usara indices numericos, la realidad es que la estructura se representa como un mapa que colecciona pares llave-valor. La Sinatxis para definir un arreglo sera a partir de corchetes cuadrados aunque en versiones anteriores de PHP era necesario usar la funcion array(). Las llaves pueden ser enteros o cadenas y los valores pueden ser de cualquier tipo de PHP, incluso de tipo array. http://php.net/manual/es/language.types.array.php
```
array(
    "curso1" => "php",
    "curso2" => "js",
);

// a partir de PHP 5.4
$array = [
    "curso1" => "php",
    "curso2" => "js",
];

// índices numéricos
$array = [
    "php",
    "js",
];
?>
```
- object:
Representa una instancia de una clase. Este tema lo veremos mas a fondo en la clase de Programación Orientada a Objetos.
```
class Car
{
    function move()
    {
        echo "Going forward..."; 
    }
}

$myCar = new Car();
$myCar->move();
?>
```
- callable:
Es un tipo de dato especial que representa a algo que puede ser “llamado”, por ejemplo una función o un método.
```
function(array $array) {
    if (count($array) == 0) { return null; }
    return $array[0];
};

// Este es nuestro arreglo
$values = [3, 2, 1];

// Usamos nuestro callable y se imprime el valor 3
echo $firstOfArray($values);
?>
iterable:
A partir de PHP 7.1 iterable es un pseudo tipo de datos que puede ser recorrido.
function foo(iterable $iterable) {
    foreach ($iterable as $valor) {
        // ...
    } 
}

?>
```
## Tipos especiales:
- resource:
Es un tipo de dato especial que representa un recurso externo, por ejemplo un archivo externo a tu aplicación.
```
"c:\\dir\\file.txt", "r");
?>
```
- NULL:
Es un valor especial que se usa para representar una variable sin valor. http://php.net/manual/es/language.types.null.php
```
$a = null; 
?>
```

# Arreglos
Almacenamos datos en una variable, ahora trataremos de almacenar más datos en una misma variable.

Estas variables que almacenan más de un dato se conocen como Arreglos y su sintáxis se va a indicar con [ ] (corchetes).

PHP utiliza índices para localizar a los elementos dentro de la variable.

La estructura de Arreglos en PHP es conocida como mapa, lo que quiere decir que tiene una composición de llave valor.

Además un arreglo puede contener más arreglos y cada uno de ellos seguirá la misma estructura.

Algo que debes saber es que en PHP podrás almacenar diferentes tipos de datos en un mismo arreglo.

# Condicionales y Ciclos
Las condiciones nos permiten tomar decisiones en el código, si se cumple la condición entonces se ejecutarán ciertas instrucciones sino se cumple se ejecutarán otras. Estas se denotan por la instrucción if.

Los ciclos funcionan de la mano con las condiciones, en este caso si se cumple la instrucción se estará ejecutando repetidas veces una instrucción dada.

Hemos agregado los jobs de forma manual accediendo al arreglo a través de sus índices, hacer esto podría traer errores y no podríamos controlarlo si tuvieramos muchos jobs. Ahora veamos una mejor forma de hacerlo con ciclos.

- El primero que tenemos es Do While que va a involucrar la inicialización de variables y condiciones.
- El segundo que veremos es For que es una forma más simplificada de usar todos los elementos que componen los ciclos.

# While vs DO While 

## Ciclos
Como mencionamos en nuestra clase anterior, los ciclos o bucles son de total importancia cuando desarrollamos software pues nos permiten repetir un bloque de acciones y en consecuencia re-utilizar mejor nuestro código, en este momento ya hablamos de cómo funciona el ciclo for y el ciclo do-while.

Ahora vamos a revisar un par de ciclos adicionales en PHP los cuales también es importante conocer. Toma en cuenta que la mayoría de las cosas se pueden hacer de diferentes maneras por lo tanto es importante que elijas bien cual es el ciclo que mejor se adapta a tu problema.

## while vs. do… while
En el apunte anterior hablamos del ciclo do while, aquí lo compararemos con otro ciclo llamado while, recapitulemos el funcionamiento de do… while:

Cuando creamos un ciclo do… while, le decimos a PHP que ejecute cierto bloque de código siempre y cuando la condición que tengas dentro se siga evaluando como verdadera.

Esta es la sintaxis de un ciclo do… while
```
do {
   codigo…
} while (condicion)
```
El ciclo while funciona de la misma manera, pero la diferencia principal es que la evaluación se llevará a cabo al iniciar el ciclo:
```
while (condicion) {
   codigo...
}
```
La principal diferencia es que el ciclo do while garantiza que el código interno se ejecutará al menos 1 vez, mientras que en el ciclo while si la condición es falsa desde un inicio, es posible que el ciclo nunca se ejecute

http://php.net/manual/es/control-structures.while.php

http://php.net/manual/es/control-structures.do.while.php

## foreach
El ciclo foreach nos brinda una solución simple para iterar sobre los valores de un arreglo, la sintaxis es la siguiente:
```
foreach ($array as $valor) {
    sentencias que pueden usar $valor
}
```

En esta sintaxis nos encontramos con 4 partes:

- La palabra reservada foreach simplemente indica el inicio de nuestro bloque
- Dentro de paréntesis se escribe el nombre del arreglo que vamos a estar iterando, este arreglo debe estar definido previamente, en este ejemplo es $arreglo
- La palabra “as” seguido de un nombre de variable que usaremos para acceder al elemento del arreglo que estamos accediendo, esta variable no debe existir previamente y solo la podrán usar dentro de este bloque. En el ejemplo es $valor.
- Entre llaves “{ }” todas las acciones que queremos repetir, en el momento en que se ejecute el ciclo la variable que definimos para iterar (en el ejemplo $valor) ya existe y podrá ser usada en esta sección, piensa que el valor de esta variable estará cambiando en cada iteración.

Suponiendo que en el ejemplo anterior `$array = [‘uno’, ‘dos’, ‘tres’]`, el ciclo se repetirá 3 veces y en cada iteración la variable $valor contendrá el elemento del arreglo correspondiente, es decir, en la primera iteración $valor será igual a ‘uno’, en la segunda `$valor` será igual a ‘dos’ y en la tercera $valor será igual a ‘tres’.

Existe una sintaxis alternativa que nos permite no solo conocer el valor, también nos permitirá conocer la llave, de este modo tendremos acceso tanto a la llave como al valor del elemento del arreglo:
```
foreach ($array as $llave => $valor) {
    sentencias que pueden usar $llave y $valor
}
```
http://php.net/manual/es/control-structures.foreach.php

# Operadores, Condicionales, Continue y Break
PHP tenemos el operador de comparación (==) y diferente de (!=).

Tenemos la sentencia continue la cuál al ejecutarse hará que se itere a la siguiente línea del arreglo. Y la sentencia break que hará que el ciclo se termine.

Los incrementos, de acuerdo a la documentación funcionan así:

```
++$a
```
Pre-incremento, incrementa $a en uno, y luego retorna $a

```
--$a
```
Post incremento, retorna $a y luego incrementa $a en uno

Pueden leer esta información en http://php.net/manual/es/language.operators.increment.php

# Operadores
Antes de continuar hablando de operadores es importante mencionar que existe un concepto conocido como precedencia de operadores el cual nos permitirá saber en qué orden se deben ejecutar los operadores que se encuentren en una sola sentencia.

Por ejemplo, en la sentencia:

1 + 2 * 3

Se ejecutará primero la operación **2 * 3 **
Luego se ejecutará la suma con 1

Esto es debido a que * tiene más valor en la precedencia que el +.

Una forma sencilla de controlar la precedencia es utilizando () paréntesis, de esta forma podemos forzar el orden que nosotros queramos, por ejemplo (1 + 2) * 3 será una versión diferente y se ejecutará primero la suma y luego la multiplicación.

Te dejo el enlace por si quieres consultar más información al respecto. http://php.net/manual/es/language.operators.precedence.php

Ahora continuemos hablando sobre los tipos de operadores, algunos ya los vimos, pero de igual forma vamos a reforzarlos enfocándonos en los más importantes.

## Operadores aritméticos
http://php.net/manual/es/language.operators.arithmetic.php

Funcionan para realizar operaciones aritméticas.

Ejemplo | Nombre | Resultado
| -- | -- | -- |
+$a|	Identidad	| Conversión de $a a int o float según el caso.
-$a	| Negación |	Opuesto de $a.
$a + $b	|Adición	| Suma de $a y $b.
$a - $b	|Sustracción| 	Diferencia de $a y $b.
$a * $b	|Multiplicación| 	Producto de $a y $b.
$a / $b	|División| 	Cociente de $a y $b.
$a % $b	|Módulo	| Resto de $a dividido por $b.
$a ** $b|	Exponenciación| 	Resultado de elevar $a a la potencia $bésima. Introducido en PHP 5.6.

## Operadores de asignación
http://php.net/manual/es/language.operators.assignment.php

El operador principal de asignación es el símbolo = (igual). Es importante tener en cuenta que este operador no sirve para comparar, normalmente del lado izquierdo del operador tendremos una variable, y este operador sirve para asignar el resultado de lo que se encuentre a la derecha a dicha variable.

$variable = 5;

Lo que tenemos en la derecha puede ser un valor, otra variable, o el resultado de una operación o función.

También existen otros operadores de asignación que se combinan con operadores aritméticos o para strings y nos permiten simplificar algunas sentencias dentro de PHP. Estos son ejemplos de cómo funcionan:
```
$a += $b $a = $a + $b
$a -= $b $a = $a - $b
$a *= $b $a = $a * $b
$a /= $b $a = $a / $b
$a %= $b $a = $a % $b
$a .= $b $a = $a . $b
```
## Operadores de comparación
http://php.net/manual/es/language.operators.comparison.php

Nos permiten comparar valores.

Ejemplo | Nombre | Resultado
| -- | -- | -- |
$a == $b|	Igual	| TRUE si $a es igual a $b después de la manipulación de tipos.
$a === $b|	Idéntico |	TRUE si $a es igual a $b, y son del mismo tipo.
$a != $b|	Diferente |	TRUE si $a no es igual a $b después de la manipulación de tipos.
$a <> $b|	Diferente	| TRUE si $a no es igual a $b después de la manipulación de tipos.
$a !== $b |	No idéntico |	TRUE si $a no es igual a $b, o si no son del mismo tipo.
$a < $b	| Menor que	| TRUE si $a es estrictamente menor que $b.
$a > $b	| Mayor que |	TRUE si $a es estrictamente mayor que $b.
$a <= $b|	Menor o igual que	| TRUE si $a es menor o igual que $b.
$a >= $b |	Mayor o igual que |	TRUE si $a es mayor o igual que $b.
$a <=> $b	| Nave espacial	| Un integer menor que, igual a, o mayor que cero cuando $a es respectivamente menor que, igual a, o mayor que $b. Disponible a partir de PHP 7.
$a ?? $b ?? $c |	Fusión de null |	El primer operando de izquierda a derecha que exista y no sea NULL. NULL si no hay valores definidos y no son NULL. Disponible a partir de PHP 7.

## Operadores de incremento/decremento
http://php.net/manual/es/language.operators.increment.php

Permiten incrementar o decrementar un valor en 1.

Ejemplo | Nombre | Resultado
| -- | -- | -- |
++$a	|Pre-incremento|	Incrementa $a en uno, y luego retorna $a.
$a++	|Post-incremento|	Retorna $a, y luego incrementa $a en uno.
--$a	|Pre-decremento	|Decrementa $a en uno, luego retorna $a.
$a--	|Post-decremento|	Retorna $a, luego decrementa $a en uno.

Es muy importante entender cómo afecta el lugar donde se establece el operador, ejemplo:
```
$a = 1;
echo $a++;
echo $a;
echo ++$a;
echo $a;
```
imprime
```
1
2
3
3
```
## Operadores lógicos
http://php.net/manual/es/language.operators.logical.php

Nos permiten combinar resultados de comparaciones.

Ejemplo | Nombre | Resultado
| -- | -- | -- |
$a and $b|	And (y)	|TRUE si tanto $a como $b son TRUE.
$a or $b|	Or (o inclusivo)	|TRUE si cualquiera de $a o $b es TRUE.
$a xor $b|	Xor (o exclusivo)	|TRUE si $a o $b es TRUE, pero no ambos.
! $a	|Not (no)	|TRUE si $a no es TRUE.
$a && $b|	And (y)	|TRUE si tanto $a como $b son TRUE.
$a || $b|	Or (o inclusivo)	|TRUE si cualquiera de $a o $b es TRUE.

## Operadores para strings
Existen 2 operadores para strings el . (punto) que nos permite concatenar cadenas, y el .= que ya fue visto anteriormente y nos permite simplificar la sintaxis de concatenar algo a una misma cadena, ejemplo:
```
$var1 = ‘Hola ’ . ‘ php’;
$var1 .= ‘!!!’;
echo $var1;
```
imprime
```
Hola php!!!
```
## Operadores para arrays
http://php.net/manual/es/language.operators.array.php

Ejemplo | Nombre | Resultado
| -- | -- | -- |
$a + $b	|Unión	Unión de $a y $b.
$a == $b|	Igualdad|	TRUE si $a i $b tienen las mismas parejas clave/valor.
$a === $b|	Identidad|	TRUE si $a y $b tienen las mismas parejas clave/valor en el mismo orden y de los mismos tipos.
$a != $b|	Desigualdad|	TRUE si $a no es igual a $b.
$a <> $b|	Desigualdad	|TRUE si $a no es igual a $b.
$a !== $b|	No-identidad|	TRUE si $a no es idéntica a $b.


El operador + devuelve el array del lado derecho añadido al array del lado izquierdo; para las claves que existan en ambos arrays, serán utilizados los elementos del array de la izquierda y serán ignorados los elementos correspondientes del array de la derecha.