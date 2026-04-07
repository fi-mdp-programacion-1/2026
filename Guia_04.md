# Guía de Trabajos Prácticos - Unidad 4
## Materia: Programación 1

## Ejercicios de la Práctica

Unidad Nº 4: Estructuras de control

### Preguntas orientadoras

1) En la teoría se habló de las investigaciones realizadas por Böhm y Jacopini. Las mismas demostraron que se podían escribir programas sin utilizar la palabra reservada `goto` y que todos los programas podían ser escritos en términos de sólo 3 estructuras de control. Mencione cuáles son esas estructuras de control.
2) Indique el funcionamiento básico de la estructura `if`/`else`.
3) Especifique en qué situación se utiliza una estructura selectiva doble.
4) Indique cuál es el inconveniente de las estructuras `if` anidadas y mencione qué estructura podría reemplazarlas y bajo qué condiciones.
5) Escriba una breve explicación de las estructuras repetitivas explicadas e indique las diferencias entre ellas.
6) ¿Para qué se utilizan los bloques anidados?
7) Una estructura de selección _____________ se utiliza para ejecutar una acción cuando una condición es verdadera, y otra acción cuando la condición es falsa.
8) La estructura de repetición _____________ especifica que un enunciado o grupo de enunciados debe ser ejecutado de forma repetida, en tanto cierta condición se mantenga verdadera.
9) Indique si los siguientes enunciados son verdaderos o falsos y si alguno es falso explique por qué:
   - a) El caso `default` se requiere en la estructura de selección `switch`.
   - b) El enunciado `break` se requiere en el caso `default` de una estructura `switch`.
   - c) La estructura `do-while` repite las instrucciones mientras una condición sea cierta.
   - d) La estructura `while` ejecuta las sentencias al menos una vez sin importar la condición.

### Ejercicios

> Para **TODOS** los ejercicios realizar el diagrama de flujo correspondiente.

1) Escribir un programa que:
   - Pida al usuario un carácter.
   - Si el carácter es A, B, C o D, el programa deberá devolver los caracteres 1, 2, 3 o 4 respectivamente; en caso contrario devolverá 0.
   - Utilice la sentencia `switch`.

2) Dado como datos la matrícula de un alumno, el semestre en el que está inscrito y promedio, determine si el mismo es apto para pertenecer a alguna de las profesiones que tiene la universidad. Si el alumno es aceptado, se debe imprimir su matrícula, carrera y la palabra "Aceptado".
   - Si el semestre es mayor a 6 y el promedio es mayor o igual a 8.8 puede estudiar **INGENIERÍA**.
   - Si el semestre es mayor o igual a 6 y el promedio mayor que 8.5 puede estudiar **MEDICINA**.
   - Si el semestre es mayor que 5 y el promedio mayor o igual que 8.3 puede estudiar **LICENCIATURA**.
   - Si el semestre es mayor o igual a 3 y el promedio mayor o igual a 7.8 puede estudiar **TÉCNICO**.

3) Escriba un programa que solicite un año e indique si es bisiesto.

> **Nota:** un año es bisiesto cuando es múltiplo de 4 pero no de 100, o múltiplo de 400.

4) Diseñe un programa que lea tres caracteres y los imprima en orden alfabético.

5) Dadas las componentes real e imaginaria de dos números complejos y uno de los símbolos pertenecientes al conjunto `[+, -, *, /]`, aplicar la estructura `switch` para reflejar la operación.

6) Escribir un programa que permita efectuar el cálculo del área de un cuadrado, un círculo o un triángulo equilátero según la opción seleccionada por el usuario a través de un menú.

7) Mostrar por pantalla los términos de la sucesión `1, 3, 6, 10, 15, 21, 28, ...` que sean menores al número K.

8) Ingresar para cada uno de los meses del año, las temperaturas máximas y mínimas de cada día (ordenadas por mes):
   - Para cada uno de los meses mostrar por pantalla la máxima y la mínima, como así también el día en que se produjeron.
   - Mostrar por pantalla la temperatura máxima anual, el día y el mes en que se registró.

9) Escribir un programa que permita ingresar un número desconocido de valores reales. Se pide calcular el promedio de los números que se encuentran en el intervalo (A, B), A < B ambos de tipo numérico real.

   Ejemplo: `A = 3.5`, `B = 6.5`. Conjunto de Valores = `2, 4, 5.5, 7, 3.5, 5.5, 1.25` → Promedio = `5`

10) Modifique el ejercicio 6 para que el programa muestre el menú de opciones de manera repetitiva hasta que el usuario seleccione la opción de salir del programa. Dicha opción debe ser parte del menú.

### Actividades extra

1) Las computadoras están jugando un papel creciente en la educación. Escriba un programa que ayudaría a un alumno de escuela primaria a repasar las tablas del 1 al 9 y a realizar cuentas rápidas con números de dos cifras. Para ello realice un menú en el que el alumno elija si quiere hacer multiplicaciones, sumas o quiere abandonar el programa. El menú deberá mostrarse hasta que el alumno no quiera practicar más. Para generar los números utilice la función `rand()`. Si el alumno acierta la cuenta muestre el mensaje "Bien hecho"; de lo contrario escriba "Vuelve a intentarlo".

> **Ayuda:** para generar números aleatorios del 0 al 9 se utiliza la expresión `rand()%10`. De la misma forma para números del 0 al 99 se usa `rand()%100`.

2) Escriba una función llamada `verificar_multiplo` que determine, para un par de enteros, si el segundo es múltiplo del primero. La función debe tomar dos argumentos enteros y regresar verdadero si el segundo es múltiplo del primero y falso de no ser así.

3) Realizar una función recursiva que permita obtener el producto de dos números positivos `a` y `b`, aplicando el concepto de "sumar `a` veces el valor `b`".

4) Desarrollar una función recursiva que permita calcular el término n-ésimo de la sucesión de Fibonacci, la cual se define por partes de la siguiente forma:

```
F(n) = 0            para n = 0
F(n) = 1            para n = 1
F(n) = F(n-1)+F(n-2)  para n > 1
```

5) Se ingresa por teclado un conjunto de números uno a uno. Contar cuántas veces se presenta el valor 10, el 20, el 30 y el 40 y cuántos números distintos a estos se presentan. Cortar el proceso cuando el número ingresado sea `-1`.

6) Determinar e imprimir los números impares comprendidos entre `a` y `b`, siendo `a` y `b` datos.

7) El factorial de un entero no negativo n se escribe como `n!` y se define:

```
n! = n * (n-1) * (n-2) * ... * 1    (para n >= 1)
n! = 1                               (para n = 0)
```

   - Escriba un programa que lea un entero no negativo, y que calcule e imprima su factorial.
   - Escriba un programa que estime el valor de la constante matemática *e*, utilizando la fórmula: `e = 1 + 1/1! + 1/2! + 1/3! + …`
   - Escriba un programa que calcule el valor de: `e(x) = 1 + x/1! + x²/2! + x³/3!`

---

## Ejercicios de Exámenes Anteriores

> Los siguientes ejercicios fueron extraídos de primeros parciales y recuperatorios de años anteriores. Corresponden a los temas de esta unidad.

---

### [1er Parcial 2022] Teoría - Expresiones lógicas: valores que hacen verdadero el resultado

Indique todos los posibles valores de las variables utilizadas que hacen resultado verdadero:

```c
resultado = (c>='a' && c<='z' || c>='A' && c<='Z');
resultado = ((a>2) || (b==4)) && (!c);
resultado = ((15>i)>(14<i)) && (!(k>(70%2)));
```

---

### [1er Parcial 2022 / 2023] Teoría - Identificación y corrección de errores en sentencias C

Identifique y corrija el/los errores en cada una de las siguientes sentencias:

```c
a) Scanf("%d", variable_tipo_int);

b) if (x=y);
   {
       printf (%d es igual a %d\n", x);
   }

c) Printf ("El valor ingresado es: %d\n, &valor")

d) Printf("La suma es %d\n," x+y);
```

---

### [1er Parcial] Teoría - Comportamiento de un bucle for con ámbito de variables

Se tiene el siguiente fragmento de código:

```c
19    for(int i=0, j=0; i<j; i++, ++j);
20    {
21        printf("Los valores de i y j son: %d, %d\n", i, j);
22    }
```

Al compilar se producen los siguientes errores:
```
error: 'i' undeclared (first use in this function)
error: 'j' undeclared (first use in this function)
```

a) Indique por qué se producen los errores y cómo se corrigen.

b) ¿Cuántas veces se imprimirá el mensaje y cuáles serán los valores de `i` y `j`?

c) ¿Qué modificaciones deben realizarse para que se impriman los valores 6 veces?

---

### [1er Parcial] Teoría - Comportamiento de if con asignación en condición

Indique qué frase se imprime al ejecutar el siguiente bloque de código y por qué:

```c
uint8_t a = 0xFE;
uint8_t par = a & 1;
if (par = 0)
    printf("La variable es par");
else
    printf("La variable es impar");
```
