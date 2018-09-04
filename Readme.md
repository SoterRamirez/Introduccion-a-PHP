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