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

# Funciones

Las funciones se denotan en PHP por la palabra reservada Function y nos servirán para llamar y reutilizar código en nuestros proyectos.

Cuando trabajemos con funciones es muy importante cuidar el scope (alcance) de las variables pues, algunas podrán ser accesadas y otras no.

Las funciones en PHP pueden o no regresar un dato particular. Si deseamos hacerlo podemos indicarlo con la palabra reservada return.

# Agregando archivos externos
Organizaremos mejor nuestro código para ello lo separaremos en otro archivo llamado jobs.php.

Usaremos la palabra reservada include para hacer que el archivo index incluya el archivo jobs.php, si lo encuentra lo incluye pero si no nos mostrará un warning. Existe otro llamado require que si no lo encuentra nos muestra un error en todo el archivo.

```
include(‘archivo.php’);
include_once(‘archivo.php’);
require(‘archivo.php’);
require_once(‘archivo.php’);
```
Todas estas funciones, cumplen, redundantemente la misma funcion. Incluyen archivo externo, haciendolo formar parte del archivo que estamos ejecutando actualmente.

Las diferencias más radicales son que:

- **include**: agrega un archivo sin importar si ya fué agregado. Si el archivo no existe, solo arroja un warning como mensaje de error.
- **include_once**, al igual que include, agrega el archivo pero solo una vez. Si el archivo ya había sido agregado anteriormente, arroja un warning.
    - Si el archivo no existe, tambien mostrará warning.
- **require**, agrega un archivo las veces que se llame a la funcion sin importar si estaba agregado o no. PERO, si el archivo no existe, arroja un error fatal.
require_once, permite agregar el archivo externo una sola vez. Si se repite, arroja error fatal y si el archivo no existe, tambien arroja error fatal y termina la ejecución del programa.

# Programación Orientada a Objetos
La programación orientada a objetos nos ayudará a estructurar mejor nuestros programas. PHP a partir de su versión 5 tiene implementaciones orientadas a objetos, lo que lo hace tener código más reutilizable y mantenible.

Una clase es una plantilla o definición de algo. Y una instacia es la representación concreta de la clase.

Encapsulamiento será el nivel de visibilidad que querramos darle a alguna variable, para ello podemos utilizar los modificadores de acceso, private, public, protected, etc.

Con la palabra reservada `this` estaremos haciendo referencia a la variable que pertenece a la clase.

## Clase y objetos
Una clase define los datos y la lógica de un objeto. La lógica se divide en funciones (métodos) y variables (propiedades).

Para definir una propiedad:
```
class Coche {
    public $color;
}
```
Para definir un método:
```
class Coche {
    public function getColor()
    {
        // Contenido de la función
    }
}
```
Para crear un objeto hay que instanciar una clase:
```
class Coche {
 // Contenido de la clase
}

$miCoche = new Coche(); // Objeto
```
La clase es como una plantilla que define características y funciones. El objeto agrupa los datos de la clase y permite utilizarlos desde una unidad.

Podemos definir las características de un coche de la siguiente forma:

```
class Coche {
    public $color;
    public $potencia;
    public $marca;
}

$miCoche = new Coche();
$miCoche->color = 'rojo';
$miCoche->potencia = 120;
$miCoche->marca = 'audi';
```

De momento sólo hemos definido propiedades del objeto. Si queremos mostrar alguna característica ahora:

```
echo 'Color del coche: ' . $miCoche->color; // Muestra Color del coche: rojo
```
Ahora vamos a definir un método que devuelve una propiedad:
```
class Coche {
    //...

    public function getColor()
    {
        return $this->color;
    }
}
```
El método getColor() nos permite devolver el color del objeto instanciado. La variable $this se puede utilizar en cualquier método, y hace referencia al objeto que hemos instanciado, en este caso $miCoche. Podemos obtener el mismo resultado que antes para mostrar el color del coche pero ahora utilizando un método para mostrar la propiedad color:
```
//...
echo 'Color del coche: ' . $miCoche->getColor();
```
Las propiedades pueden tener valores por defecto:
```
class Coche {
    public $color = 'rojo';
//...
}
```
De esta forma siempre que se instancie un objeto de la clase Coche, éste será de color rojo a no ser que se modifique después.

# Constructores y Métodos

El Método constructor nos permitirá inicializar valores default así como también pasar datos como parámetro.

Todas las funciones que tienen __ antes del nombre de la función se conocen como métodos mágicos.

**Uso de __construct():**
- __construct se utiliza para la inserción de parametros y dependencias para construir el objeto. No necesita ser llamado ya que lo hace automaticamente cuando se crea un objeto.

**Uso de __destruct():**
- Al igual que __construct, __destruct se llama automaticamente al finalizar los procesos del objeto creado. se utiliza para eliminar referencia del objeto creado, el cual liberará la memoria utilizada al crear ese objeto. casi no se utiliza en programas pequeños. pero puede servir como por ejemplo cerrar la conexion a una base de datos al terminar de hacer un consulta. __destruct nunca se le debe pasar variables como parametros.

**Uso de __get()**
- __get() sirve para poder acceder a una variable, que no pueda ser accedida afuera de la clase(ya sea private o protected). para esto se tiene que pasar el nombre de la variable que se quiere acceder como argumento del metodo. Al igual que construct y destruct, no necesita ser llamada ya que lo hace automaticamente. Si intentamos acceder a la variable sin el uso del metodo magico __get, lanzará una excepción.

**Uso de __set():**
- __set que sirve ya sea para cambiar el valor de una propiedad que no es accesible afuera de la clase se tiene que pasar por medio del argumento del metodo la propiedad a acceder y el valor nuevo que desea cambiar. Igual sirve para crear nuevas propiedades de la clase

- NOTA: El uso de estos `__get() y __set()` por ser lentos lentos, no facilitan el autocompletado de código en los IDE, hacen que el mantenimiento y refactorizar sea más largo y complicado. En su lugar se pueden emplear getters y setters.

**Uso de __isset():**
- Con __isset() se verifica la existencia de una propiedad o array. se lanza al llamar a isset() o a empty() sobre propiedades inaccesibles.

**Uso de __unset():**
- Con __unset() se elimina una propiedad de la clase. dicho en otras palabras, se invoca cuando se usa unset() sobre propiedades inaccesibles…

**Uso de __sleep():**
- El método sleep sera invocado cuando pasemos el objeto por la función serialize, de esta forma podremos prepararlo para ser almacenado o para lo que queramos, como siempre el limite es la imaginación de cada cual y los posibles usos que se le pueden dar a esto son muchísimos. Hay que tener en cuenta que siempre ha de devolver un array, es preferible no usar sleep a hacer un return que no sea un array porque php dará un error.

**Uso de __wakeup():**
- El método wakeup se encarga de realizar exactamente lo contrario que sleep, en el momento que deserializamos un objeto con unserialize se invoca a este método, para por ejemplo, restablecer la conexión con la base de datos, o alterar algún atributo.

**Uso de __call():**
- Se utiliza el método mágico __call() para llamar una función que sea inaccesible afuera de la clase

**Uso de __callStatic():**
- Si el método al que se quiere llamar es static se puede emplear __callStatic(). Este método funciona de la misma forma que __call() pero la sintaxis con la que llamar a los métodos será como a los métodos estáticos.

# Herencia 

Una de las características más importantes de la programación orientada a objetos es la de la herencia. Ésta consiste en que, cuando una clase hereda a otra, obtiene por defecto todas sus propiedades (métodos y atributos), pudiendo definir algunas adicionales. Esto se expresa mediante la palabra clave extends y el nombre de la clase padre, al definir una clase hija que hereda de ésta.

Las propiedades que tengan la visibilidad de privada no serán accesibles desde esta nueva clase, aunque seguirán existiendo dentro del objeto.

En cualquier momento podemos sobreescribir las propiedades del método padre, así como acceder directamente a las mismas mediante la palabra reservada parent .

Las clases pueden ser extensiones de otras clases. La clase extendida o derivada tiene todas las variables y funciones de la clase base (herencia) y lo que se agregue en la definición extendida.

Los métodos de herencia y sus miembros pueden ser evitados, redeclarándolos con el mismo nombre con el que los definió la clase padre, a menos que la clase padre haya definido un método como final.

Es muy conveniente utilizar require_once cuando queremos utilizar herencia e incluir clases que están en otros archivos.

Dentro de nuestra clase hijo podemos sobrescribir algún método del padre, esto es un concepto que conocemos como polimorfismo. Lo que polimorfismo quiere decir es que tendremos un método que va a funcionar de acuerdo con su contexto donde es llamado.

Si tenemos propiedades con la palabra private en nuestra clase padre, desde nuestra clase hija no podremos acceder a esta propiedad, pero si queremos que siga siendo privada y que las clases hijas tengan acceso podemos usar la palabra clave protected.

Ahora que ya tenemos una idea de cómo funciona la herencia de clases, vamos a ver cada uno de los modificadores.

1. Public
- Las propiedades y métodos public son accesibles desde cualquier parte del script, siendo este modificador el más fácil de usar. En PHP 4 las variables se declaraban con "var" y eran public, pero esa forma de denominarlas está obsoleta y puede generar algunos warnings.
```
class Perro
{
    public $nombre;
    public function ladrar(){
        print "Guau!";
    }
}
class Bulldog extends Perro {
    public function ladrar(){
        print "Woof!";
    }
}
$cachorro = new Bulldog();
$cachorro->nombre = "BunBuns";
print $cachorro->nombre; // Devuelve: BunBuns
```
Por defecto todas las propiedades y funciones son public. No es necesario especificar public, pero es mejor hacerlo para que sea más legible. Con los métodos puedes no utilizar ninguna palabra y escribir directamente function. Con las propiedades en cambio necesitas una palabra por lo menos, sino da un error de sintaxis, ya que sino no hay manera de saber qué propiedades tiene una clase. Nunca hay que usar var, siempre un modificador.

2. Private
El problema de las propiedades y métodos public es que se permite llamar a los métodos y establecer las propiedades desde cualquier lado del script. En el ejemplo anterior, si en lugar de crear un objeto Bulldog, creamos un objeto Perro e intentamos establecer nombre, nos dará un fatal error: Cannot access private property.
```
class Perro
{
    private $nombre;
    public function ladrar(){
        print "Guau!";
    }
}
$cachorro = new Perro();
$cachorro->nombre = "BunBuns"; // Fatal error
```
No se podrá ni mostrar ni modificar el nombre. Para hacerlo se utilizan getters y setters, métodos public para poder acceder a estas propiedades y métodos private desde otras partes del script:
```
class Perro
{
    private $nombre;
    public function ladrar(){
        print "Guau!";
    }
    public function setNombre($nombre){
        $this->nombre = $nombre;
    }
    public function getNombre(){
        return $this->nombre;
    }
}
$cachorro = new Perro();
$cachorro->setNombre("Chicken");
echo $cachorro->getNombre(); // Devuelve: Chicken
```
Sin embargo, si desde un objeto que es instancia de una clase heredada se intenta modificar el valor private, PHP lo que hace es crear una varable pública y una privada. Vamos a partir del ejemplo que hemos puesto en public, y cambiar la propiedad a private:
```
class Perro
{
    private $nombre;
    private function ladrar(){
        print "Guau!";
    }
}
class Bulldog extends Perro {}
$cachorro = new Bulldog();
$cachorro->nombre = "BunBuns";
var_dump($cachorro);
/*
Devuelve:
object(Bulldog)[1]
  private 'nombre' (Perro) => null
  public 'nombre' => string 'BunBuns' (length=7)
*/
// Los métodos en cambio no se pueden usar:
$cachorro->ladrar(); // Fatal error: Call to private method
```
Ahora hay dos variables, una privada que no se puede modificar y es null porque no se le ha asignado ningún valor, y otra public que crea PHP. Esto es algo confuso, por lo que lo mejor es evitar esta situación. Los métodos y propiedades privados sólo deben ser accedidos por la clase en la que se encuentran, las clases hijas no pueden acceder a ellos. Para ello se utiliza el modificador protected.

3. Protected
Las propiedades y métodos marcados como protected son accesibles a través de la clase donde se crean y sus descendientes:
```
class Perro
{
    protected $nombre;
    protected function ladrar(){
        print "Guau!";
    }
}
class Bulldog extends Perro {
    public function ladrarBulldog(){
        // Podemos acceder a ladrar() de la clase Perro
        return $this->ladrar();
    }
    public function setNombre($nombre){
        $this->nombre = $nombre;
    }
    public function getNombre(){
        print $this->nombre;
    }
}
```
Diferentes ejemplos de acceso a propiedades protected:
```
$cachorro = new Bulldog();
// Podemos acceder a la función ladrar() desde ladrarBulldog():
$cachorro->ladrarBulldog(); // Devuelve Guau!
// No podemos acceder a ladrar() desde el objeto cachorro:
$cachorro->ladrar(); // Fatal error: Call to protected method Perro::ladrar()
// Tampoco podemos asignarle un nombre, pues $nombre también es protected
$cachorro->nombre = "Hunky"; // Fatal Error: Cannot access protected property
// Si podemos asignarle un valor con el método setNombre():
$cachorro->setNombre("Hunky");
// Y mostrarlo con getNombre():
echo $cachorro->getNombre(); // Devuelve: Hunky
```