1. Diseñar un programa en PHP que muestre nuestro nombre y apellidos sin hacer uso de variables 
```php
<?php
    echo "Jrodriiguezg";
?>
``` 

2. El mismo programa haciendo uso de variables 
```php
<?php
    $nombreapeliidos="jrodriguezg";
    echo $nombreapellidos;
?>
```
3. Diseñar un programa en PHP que dadas dos variables de tipo float con los valores que sean realice las operaciones, sum , resta, mult, division y resto, y muestre el resultado, (una calculadora)
```php
<?php
$numero1="12";
$numero2="2";

$suma=$numero1 + $numero2
$resta=$numero1 - $numero2
$multiplicacion=$numero1 * $numero2
$division=$numero1 / $numero2
$resto=$numero 1% $numero2

echo $suma; 
echo $resta;
echo $multiplicacion;
echo $division;
echo $resto; 
?>
```
4. Modificar el programa anterior que muestre esa informacion mediante una lista en HTML 

5. Diseñar un programa en PHP que simule el lanzamiento de una moneda de manera que ese lanzamiento lo vamos a controlar con la funcion rand(min,max) y esto se lo asignamos a una variable llamada tirada, si sale el valor minimo, mostramos la cara de una moneda, y si sale el maximo mostramos la otra cara

Cara: https://upload.wikimedia.org/wikipedia/commons/5/56/Reverso_1_euro.jpg

cruz: https://i.etsystatic.com/43431483/r/il/a41576/5032219716/il_680x540.5032219716_f0gs.jpg

6. Diseñar un programa en PHP que indique el mayor de tres numeros 
Si el numero 1 es mayor que el numero 2 y menor que el numero 3 

<?php
        $num1 = 12;
        $num2 = 8;
        $num3 = 2;
        if ($num1 > $num2 && $num1 > $num3){
            echo "El numero" . $num1 . "es el mayor";
        }else ($num2 > $num3 && num2 > $num1){
            echo "El numero" . $num2 . "es el mayor"; 
        } elif ($num3 > $num2 && $num3 > $num1){
            echo 
        }
?>

pseucodigo: 
si el numero 1 es mayor que el numero 2 y menor que el numero 3
entonces el mayor es el numero 1
sino si el numero 2 es mayor que el numero 3 y menor que el numero 1
entonces el mayor es el numero 2
sino si el numero 3 es mayor que el numero 2 y menor que el numero 1
entonces el mayor es el numero 3


7. Diseñar un programa en PHP que sean dos dados y al lanzarlos den premios 

pseudocodigo 
Define lista de premios 

Lanzar los dados
Si sale 1 da el premio X


## Ejercicios muy basicos 

1. Visualizar un mensaje de bienvenida 

<?php 
 echo "Hola mundo!";
?>

2. Guarda tu nombre y edad en 2 variables y visualiza el texto mi nombre es .. y tengo .. años

<?php 
$nomb = "Jrodriguez";
$edad = "23"; 

echo "Mi nombre es" . $nomb . "y tengo" . $edad . "años";
?>

3. Calcular la suma , producto, división entera y resto de la división entera de 2 numeros guardados en variables y visualizarlos.

<?php
$num1 = "12";
$num2 = "2";

$suma = $num1 + $num2;
$producto = $num1 * $num2;
$division = $num1 / $num2;
$resto = $num1 % $num2;

echo "La suma es" . $suma .;
echo "El producto es" . $producto .;
echo "La division es" . $division .;
echo "El resto es" .$resto .;
?>

4. Calcular el cuadrado de un número y visualizarlo

<?php 
$num1 = "56";

$cuadrado = $num1 * $num1; 

echo "El cuadrado de" . $num1 . "es" . $cuadrado .; 
?>

5. Calcular el 10% de un número y visualizar 

<?php 
$num1 = "34"; 

$porcentaje = $num1 * 0.1;
echo "El 10% de" . $num1. "es" . $porcentaje .;
?>

6. Calcular el cuadrado de la suma y el de la diferencia de dos números

<?php
$num1 = "34";
$num2 = "56";

$cuadrado_suma = ($num1 + $num2) * ($num1 + $num2);
echo "El cudrado de la suma es" . $cuadrado_suma .;

$cuadrado_resta = ($num1 - $num2) * ($num1 - $num2);
echo "El cuadrado de la resta es" . $cuadrado_resta .;
?>


7. Calcular la longitud de una circunferencia y el área del círculo de un radio determinado
<?php
$n1 = "24";

$circunferencia = 2 * 3,14 * $n1;

$area = 3,14 * $n1 * $n1;

echo "La circunferencia es" . $circunferencia .;
echo "El area es" . $area .;
?>

8. Calcular la división con decimales de dos números

<?php
$n1 = "24,4";
$n2 = "0,21";

$division = $n1 / $n2;

echo "La division es" . $division .;
?>



9. Calcular el resto de la división entera de dos números 

<?php
$n1 = "24,4";
$n2 = "0,21";

$resto = $n1 % $n2;

echo "El resto es" . $resto .;
?>

10. Incrementar en 1 el valor de una variable
<?php
$n1 = "23";

$incrementar = ++$n1 ;
echo "El incremento es" . $incrementar .;
?>


11. Incrementar en 5 el valor de una variable

<?php
$n1 = "45";

$incremento = $n1 += 5;
echo "El incremento es" . $incremento .;
?>

12. Decrementar en 1 el valor de una variable

<?php 
$n1 = "83";

$decremento = --$n1;
echo "El decremento es" . $decremento .;
?>

13. Decrementar en 5 el valor de una variable 

<?php
$n1 = "94";

$decremento = $n1 -= 5;
echo "El decremento es" . $decremento .;
?>

13. Decrementar en 6 el valor de una variable

<?php
$n1 = "123";

$decremento = $n1 -= 6;
echo "El decremento es" . $decremento .;
?>  

14. Cambiar el signo a un dato 

<?php
$n1 = "-24";
