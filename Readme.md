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