# Guía de Trabajos Prácticos - Unidad 6
## Materia: Programación 1

## Ejercicios de la Práctica

Unidad Nº 6: Punteros, strings y asignación dinámica de memoria

### Preguntas orientadoras

1) De acuerdo a lo mencionado en filminas anteriores, identifique la potencialidad del tipo de variable puntero. ¿Qué cuestiones resuelve?

2) Complete los siguientes espacios:
   - Un puntero es una variable que contiene como valor _______.
   - Los tres valores que pueden utilizarse para inicializar un puntero son ______, _______, _________.
   - El operador `______` regresa la posición en memoria donde está almacenado su operando.
   - El operador `______` regresa el valor del objeto hacia el cual apunta su operando.
   - La función `______` se utiliza para asignar memoria de forma dinámica.
   - La función `______` asigna memoria dinámicamente para un arreglo que inicializa los elementos a cero.
   - La función `______` modifica el tamaño de un bloque de memoria previamente asignada.
   - La función `______` libera la zona de memoria para que pueda ser reutilizada.

3) Para cada una de las siguientes, escriba un enunciado que ejecute la tarea indicada. Suponga que se han declarado las variables de punto flotante `number1 = 7.3` y `number2`:
   - Declare la variable `fptr` que sea un puntero a un flotante.
   - Asigne la dirección de la variable `number1` al puntero `fptr`.
   - Imprima el valor del objeto señalado por `fptr`.
   - Asigne el valor del objeto al que señala con `fptr` a la variable `number2`.
   - Imprima el valor de `number2`.
   - Imprima la dirección de `number1` utilizando `%p`.
   - Imprima la dirección almacenada en `fptr`. Utilice el especificador de conversión `%p`.

4) Escriba un enunciado para cada una de las siguientes operaciones. Suponga que la variable `c` de tipo `int`, las variables `d`, `e`, y `f` del tipo `float`, la variable `cptr` es del tipo `char*` y los arreglos `s1[100]` y `s2[100]` son del tipo `char`:
   - Convierta en una letra mayúscula el carácter almacenado en `c` y asigne el mismo a `c`.
   - Determine si lo almacenado en `c` es un dígito.
   - Convierta la cadena `"1234567"` a `long` e imprima el valor.
   - Determine si el valor de la variable `c` es un carácter de control.
   - Lea desde el teclado una línea de texto al arreglo `s1`. No utilice `scanf`.
   - Imprima lo almacenado en `s1` sin utilizar `printf`.
   - Asigne a `ptr` la posición de la última ocurrencia de `c` en `s1`.
   - Imprima el valor de `c` sin utilizar `printf`.
   - Convierta la cadena `"8.63582"` a `double` e imprima el valor.
   - Determine si el valor de `c` es una letra.
   - Lea un carácter del teclado y almacene dicho carácter en `c`.
   - Asigne a `ptr` la posición de la primera ocurrencia de `s2` en `s1`.
   - Determine si el valor de `c` es un carácter de impresión.
   - Lea los valores `float` a partir de la cadena `"1.37 10.3 9.432"`.
   - Copie la cadena almacenada en `s2` al arreglo `s1`.
   - Compare la cadena `s1` con la cadena `s2` e imprima el resultado.
   - Agregue 10 caracteres de la cadena en `s2` a `s1`.
   - Determine la longitud de `s1` e imprima el resultado.
   - Convierta la cadena `"-21"` a `int` e imprima el valor.

### Ejercicios

1) En la siguiente imagen se muestra una función que permite calcular el valor promedio de un vector de N flotantes. Reescriba la función mediante notación y aritmética de punteros.

2) Escribir un programa que permita ordenar de manera ascendente y descendente un vector de enteros de longitud desconocida.

> **Nota:** No se puede usar la función de librería `qsort`, usted debe investigar los algoritmos de ordenamiento por su cuenta.

3) Escribir un programa que permita testear una función llamada `longitud_cadena`, la cual debe recibir un puntero a `char` y retornar la cantidad de caracteres incluido el carácter `'\n'`.

4) Escribir un programa que permita testear una función propia, que realice la misma operación que la función de librería `strcpy`.

5) Escribir un programa que permita sumar dos matrices de las mismas dimensiones. El usuario debe ingresar la cantidad de filas y columnas de cada una, luego se debe mostrar en pantalla el resultado.

> **Nota:** Suponga que las matrices son A y B, entonces el resultado de la suma se debe guardar en A.

6) Escribir un programa que permita ingresar una matriz de m×n, calcular la matriz transpuesta de la matriz ingresada e imprimir el resultado en pantalla.

> **Nota:** Intente encontrar la solución más eficiente.

### Actividades extra

1) Refactorice el ejercicio Extra 1 de la guía 5.1 haciendo uso de punteros.

---

## Ejercicios de Exámenes Anteriores

> Los siguientes ejercicios fueron extraídos de segundos parciales y recuperatorios de años anteriores. Corresponden a los temas de esta unidad.

---

### [2do Parcial 2023] Teoría - Punteros: V/F y corrección de asignaciones

**Parte A - Verdadero o Falso (justificar si es falso):**

a) Las uniones se inicializan de la misma manera que las estructuras.

b) Las estructuras se pasan siempre a las funciones por referencia.

c) Los punteros de diferentes tipos no pueden ser asignados uno al otro.

d) Incrementar un puntero a un tipo de dato `int` siempre produce el mismo resultado que incrementar un puntero a un tipo de dato `float`.

e) Las variables almacenadas en el stack son accesibles desde cualquier función.

**Parte B - Asignaciones de punteros incorrectas:**

Indicar cuáles de las siguientes asignaciones son incorrectas y cómo se corregirían:

```c
a)  int *ptri, a = 10;
    ptri = &a;
    double *ptrf, x = 5.0;
    ptrf = &x;
    ptrf = ptri;          // ¿correcto?

b)  char *ptrc;
    *ptrc = 'a';          // ¿correcto?

c)  int n;
    int *ptrn = &n;
    ptrn = 9;             // ¿correcto?

d)  int *ptrn = NULL;
    *ptrn = 9;            // ¿correcto?
```

---

### [2do Parcial 2023] Teoría - Puntero doble y lectura de memoria

Se tienen las siguientes sentencias escritas en lenguaje C y los resultados de la reserva de memoria del puntero doble. Se muestra también el contenido de la memoria más relevante:

```c
short **ptr;

ptr = (short **)malloc(2 * sizeof(short *));  // valor retornado: 0x005E1898
*ptr = (short *)malloc(5 * sizeof(short));
*(ptr+1) = (short *)malloc(5 * sizeof(short));

0x5e1898: d8 18 5e 00 00 19 5e 00
0x5e18d8: 00 01 02 03 04 05 06 07 08 09 0a 0b 0c 0d 0e 0f
0x5e18e8: 10 11 12 13 14 15 16 17 ...
```

Sabiendo que los datos se guardan siempre en posiciones consecutivas de memoria a partir del valor retornado por `malloc` (en orden creciente) y que `sizeof(short)` retorna 2, indique los valores que se obtendrían en los siguientes casos (expresados como números hexadecimales):

```c
a) ptr[1][2] =
b) **ptr =
c) *ptr =
d) *(ptr+2) =
e) &ptr[1][1] =
f) ptr[0][6] =
```

---

### [2do Parcial 2024] Teoría - Puntero doble: lectura de memoria con tabla

Se tienen las siguientes sentencias escritas en lenguaje C:

```c
short **ptr;

ptr = (short **)malloc(2 * sizeof(short *));  // valor retornado: 0x009A1898
*ptr = (short *)malloc(5 * sizeof(short));
*(ptr+1) = (short *)malloc(5 * sizeof(short));
```

Con el contenido de memoria dado en el examen, indique los valores que se obtendrían en los siguientes casos (expresados como números hexadecimales):

```c
a) ptr[1][2] =
b) **ptr =
c) *ptr =
d) *(ptr+2) =
e) &ptr[1][0] =
```

---

### [2do Parcial] Teoría - Relación punteros/arreglos y comportamiento de realloc

Responda las siguientes preguntas teóricas:

a) ¿Cuál es la relación entre punteros y arreglos?

b) ¿Cuál es la relación entre una unión y una struct?

c) ¿Qué pasa si se invoca la función `free` pasándole un puntero a un arreglo creado estáticamente?

d) Explique cómo se comporta la función `realloc` según los diferentes valores de sus parámetros. (Complete la siguiente tabla):

| Buffer | Size en bytes | Comportamiento |
|--------|--------------|----------------|
| `NULL`   | 0            | |
| `NULL`   | ≠ 0          | |
| ≠ `NULL` | 0            | |
| ≠ `NULL` | ≠ 0          | |

---

### [2do Parcial 2024] Práctica - Agenda de contactos con lectura de archivo binario

Escriba un programa en lenguaje C para gestionar una agenda de contactos. El programa debe aceptar 6 parámetros por línea de comandos:

```
datos.bin  54  223  1102334  "Armando Esteban Quito"  datos.txt
```

- `datos.bin`: archivo de entrada en formato binario.
- `54 223 1102334`: código de país, área y número del contacto a modificar.
- `"Armando Esteban Quito"`: nuevo nombre del contacto cuyo teléfono coincide.
- `datos.txt`: archivo de salida en formato texto.

Validar la cantidad de parámetros recibidos. El formato del archivo binario es una sucesión continua de bytes:

```
CC0 nombre0 pais0 area0 numero0
...
CCNC-1 nombreNC-1 paisNC-1 areaNc-1 numeroNC-1
NC
```

Donde:
- `NC` (2 bytes sin signo): número de contactos.
- `CCi` (1 byte sin signo): cantidad de caracteres del nombre (incluido `\0`).
- `paisi` (2 bytes), `areai` (2 bytes) y `numeroi` (4 bytes): información del teléfono.

El programa debe:
1. Mostrar los datos recuperados en pantalla.
2. Ordenar los contactos por nombre de manera ascendente.
3. Modificar el nombre del contacto cuyo teléfono coincide con los parámetros recibidos.
4. Guardar en el archivo de salida reutilizando la misma función que imprime en pantalla.

Datos de prueba en caso de no poder leer el archivo binario:

```c
{
    {12, "Tom y Jerry",      {56, 225, 1122331}},
    {12, "Los Pitufos",      {54, 223, 1102334}},
    {15, "La Pantera Rosa",  {55, 224, 1102334}}
}
```
