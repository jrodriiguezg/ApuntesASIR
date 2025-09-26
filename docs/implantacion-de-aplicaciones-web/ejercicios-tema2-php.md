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