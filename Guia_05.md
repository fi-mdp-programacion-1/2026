# Guía de Trabajos Prácticos - Unidad 5
## Materia: Programación 1

## Ejercicios de la Práctica

Unidad Nº 5: Arreglos y matrices

### Preguntas orientadoras

1) Indique qué es un array o arreglo.
2) Mencione las cosas que no se pueden hacer con un arreglo.
3) Muestre y ejemplifique qué ocurre si no se define de manera correcta la dimensión de un arreglo.
4) Complete los espacios en blanco:
   - a) Los elementos de un arreglo están relacionados entre sí por el hecho de que tienen el mismo ________ y __________.
   - b) El número utilizado para referirnos a un elemento particular de un arreglo se llama ____________.
   - c) Dado un determinado arreglo de nombre `p_vector`. Los cinco elementos que lo componen son: ______, _______, ______, ______, _______.
   - d) El ponerle nombre a un arreglo, indicar su tipo, y especificar el número de elementos dentro del mismo se conoce como ____________.
5) Declare si las siguientes afirmaciones son verdaderas o falsas. En el caso de ser falsas explique por qué:
   - a) Un arreglo puede almacenar muchos tipos diferentes de valores.
   - b) Un índice de arreglo puede ser del tipo de datos `float`.
   - c) Si no se inicializan todos los elementos de un arreglo, los faltantes se inicializan automáticamente con el último valor inicializado.
   - d) Un elemento individual de un arreglo que se pasa a una función, si es modificado en esa función, entonces contendrá el valor modificado.
6) Conteste las siguientes preguntas relacionadas con un arreglo nombrado como `fracciones`:
   - a) Declare el arreglo `fracciones` del tipo `float` de dimensión 8.
   - b) Indique el nombre del cuarto elemento del arreglo.
   - c) Asigne al elemento con índice 5 el valor `1.667`.
   - d) Asigne al quinto elemento el valor `3.347`.
   - e) Imprima todos los elementos del arreglo usando un lazo `for`. Muestre la salida.
   - f) Imprima el sexto elemento de `fracciones` con dos dígitos de precisión a la derecha del punto decimal.
7) Conteste las siguientes preguntas en relación a un arreglo llamado `tabla`:
   - a) Declare el arreglo de tipo entero de 3 columnas y 2 filas.
   - b) Indique cuántos elementos contiene el arreglo.
   - c) Utilice un lazo `for` para inicializar cada elemento del arreglo como la suma de sus índices.
   - d) Asigne el valor 3 al elemento de la primera fila y segunda columna.
   - e) Imprima el valor del elemento del inciso anterior.
8) Encuentre el error en los siguientes segmentos de programa y corrija el error:

```c
a) int b[10] = {0}
   for(i = 0; i <= 10; i++);
   b[ ] = 1;

b) int mvalor[][] = {{1,2,3,4}{5,6,7,8}}

c) a[1,1] = 5;

d) int matriz[][2] = {{2,2},{3,5}};
   printf("%d", matriz);
```

### Ejercicios

1) Declare un vector de 28 elementos tipo `char` e inicialícelo con el abecedario (no incluir la ñ) utilizando una estructura de repetición `for`. Luego mostrarlo en pantalla.

2) Genere una función que permite ingresar los elementos de un vector tipo `char` o imprima el vector previamente cargado. A la función se le deben pasar 3 datos como parámetros: el vector, la longitud del mismo y una variable que indique si se carga el vector (`I`) o se imprime el resultado (`O`).

3) Escriba un programa que inicialice un vector de flotantes y copie el contenido de ese vector en otro mediante una función.

4) Escriba una función que retorne el máximo valor almacenado en un vector de enteros y pruébela mediante un programa.

5) Escriba un programa que pida al usuario tres conjuntos de cinco números flotantes cada uno y cumpla con todo lo que sigue:
   - a) Almacenar los datos en una matriz de 3×5.
   - b) Calcular el promedio de cada fila.
   - c) Calcular el promedio de todos los valores.
   - d) Determinar el máximo entre todos los valores.
   - e) Imprimir todo lo anterior.

6) Realice un programa que permita al usuario ingresar un número desconocido de números enteros y almacenarlos en un vector. Se debe controlar durante el ingreso que los números no se repitan. Luego, a partir de dicho vector, calcular la suma de los valores negativos excluyendo el mínimo y el producto de los valores positivos excluyendo el máximo y el cero.

7) Suponga una pantalla color reducida de 80×60 píxeles en la que la primera dimensión representa el color y las dos restantes representan la posición del pixel. Realizar una función que muestre la pantalla de color azul con un rectángulo que empieza en el pixel (20,30) de 10 puntos de ancho, con ese lado de color verde, y 20 puntos de alto, con ese lado de color rojo. Para mostrar el resultado imprima cada página de color por separado. En la de color azul tiene que aparecer una `B` en cada posición que va pintada y cero en las posiciones que son de otro color. Lo mismo se hace con el color verde poniendo una `G` y con el color rojo poniendo una `R`.

8) Genere las tablas de multiplicar en una tabla de doble entrada. Crear una función que permita elegir qué rango de la tabla se quiere mostrar (Ej.: Mostrar la tabla del 3).

### Actividades extra

1) En una competencia de ciclismo intervienen N deportistas, cada uno realiza dos pruebas, una por tiempo y otra por número de vueltas. Se tienen tres arreglos con los siguientes datos de cada participante: nombre, tiempo en la primera prueba y número de vueltas en la segunda prueba. Imprimir en pantalla 5 columnas en las que se muestre para cada participante: nombre, tiempo en la primera prueba, número de vueltas en la segunda prueba, diferencia de tiempo respecto del más rápido en la primera prueba y diferencia de vueltas respecto del que hizo más vueltas en la segunda prueba.

2) Genere una matriz cuadrada M a partir de un vector V de N elementos enteros no nulos. Luego, imprímala en pantalla.

---

## Ejercicios de Exámenes Anteriores

> Los siguientes ejercicios fueron extraídos de primeros parciales y recuperatorios de años anteriores. Corresponden a los temas de esta unidad.

---

### [1er Parcial 2023] Práctica - Menú con operaciones sobre vectores de longitud variable

Se necesita realizar un programa en lenguaje C para procesar arreglos que cumpla con las siguientes características:

Contar con un menú que permita seleccionar entre siete (7) operaciones, además de la opción de salir (con confirmación):

1. Ingreso de los valores del vector (longitud variable).
2. Imprimir los valores en formato vertical (vector columna).
3. Determinar si un número dado se encuentra entre las componentes del arreglo.
4. Comunicar la cantidad de números pares ingresados.
5. Calcular el valor máximo del vector y en qué índice está almacenado.
6. Imprimir el vector en formato matricial de m filas y n columnas (m×n = longitud original).
7. Imprimir el vector en formato matricial de n filas por m columnas (filas y columnas intercambiadas respecto al punto 6).

El programa deberá estar correctamente modularizado y compilar sin errores ni warnings. Todas las funciones salvo la primera no deberían ser capaces de modificar los valores del vector.

---

### [1er Parcial 2024] Práctica - Menú con operaciones sobre una matriz de unsigned char

Escriba un programa en lenguaje C que cumpla con los siguientes requisitos:

Solicite al usuario que ingrese doce (12) números de tipo `unsigned char` que queden almacenados en una matriz de 3 filas. Puede usarse como punto de partida:

```c
unsigned char datos[] = {217, 156, 134, 98,
                          231, 254, 243, 65,
                          123, 56, 48, 232};
```

Muestre el siguiente menú que permita al usuario efectuar las operaciones indicadas. El mismo debe realizar cualquiera de las funciones seleccionadas mientras que el usuario no quiera abandonar el programa (pidiendo confirmación de salida). Los valores originales **no** deben ser modificados.

```
Por favor elija una opción:
1 – Ingresar valores
2 – Imprimir valores originales
3 – Imprimir valores modificados
4 – Trasponer bits
5 – Multiplicar por un escalar
6 – Sumar columna
7 – Salir
Ingrese una opción: __
```

Observaciones:
- **Opción 4 (Trasponer bits):** Para cada valor de la matriz, hacer un swapping entre los bits correspondientes al valor de la fila y de la columna. Ejemplo: fila 2 (bit2), columna 1 (bit1), valor `0x54 = 84`:
  ```
  b7  b6  b5  b4  b3  b2  b1  b0
   0   1   0   1   0   1   0   0   (original)
   0   1   0   1   0   0   1   0   (swapped → 0x52 = 82)
  ```
- **Opción 5:** Solicitar el número multiplicador. Verificar que no se produzca desborde.
- **Opción 6:** Solicitar el número de columna. Verificar que sea válida. Imprimir: `La suma de los valores de la columna xx es yyyy`.

El programa debe respetar conceptos de modularidad, sin warnings ni errores. Se debe entregar diagrama de flujo de la función que realiza el intercambio de bits.

---

### [Recu. 1er Parcial] Práctica - Matriz de 3×5 y operaciones matriciales

Escriba un programa en lenguaje C que pida al usuario tres conjuntos de cinco números flotantes cada uno y cumpla con todo lo que sigue. Utilizar como datos:

```c
{{2.14, 4.56, 6.54, 9.87, 3.21},
 {5.43, 4.32, 7.65, 1.23, 3.56},
 {4.87, 9.32, 4.67, 8.76, 2.78}}
```

a) Almacenar los datos en una matriz de 3×5.

b) Calcular el promedio de cada fila.

c) Calcular el promedio de todos los valores.

d) Determinar el máximo entre todos los valores.

e) Imprimir todo lo anterior.

Se evaluará la prolijidad del código, el diseño de funciones (nombre, parámetros y valores de retorno), los comentarios y el diagrama de flujo.

---

### [1er Recuperatorio 2022] Práctica - Operaciones sobre una imagen color de 4×6 píxeles

Escribir un programa en lenguaje C que permita realizar operaciones sobre los elementos de una imagen color de 4×6 píxeles. Las mismas **no** deben modificar los datos originales. El programa debe pedir que el usuario elija el tipo de función a realizar de acuerdo al siguiente menú:

```
Presione un número para seleccionar la operación deseada:
1 – Transponer la imagen (intercambiar filas por columnas).
2 – Trazar sobre la imagen una línea roja a 45° (preservando los demás colores).
3 – Pintar el triángulo inferior de la imagen de color magenta (RR=255, BB=255), preservando los demás colores.
4 – Imprimir todos los colores.
5 – Sustituir las componentes de color verde (GG) por sus complementarias.
0 – Salir del programa.
```

La opción 4 debe imprimir la matriz de colores en hexadecimal con las columnas alineadas. La salida debe ser confirmada.

Para probar se utilizan los siguientes valores (componentes BB GG RR 00):

```c
unsigned int memory[] = {
    0x3d2e1f00, 0xff000000, 0x00ff0000, 0x0000ff00,
    0xccbbaa00, 0x30201000, 0xd3e2f100, 0x55332200,
    0x67452300, 0x23768900, 0xb65aa500, 0xbadcfe00,
    0x94ff2800, 0xde1e4000, 0x801e4000, 0xd85e4300,
    0x71000000, 0x7ee0fd00, 0x00000000, 0x00000000,
    0x94ff2800, 0xfd104000, 0x01000000, 0xc02e3e00
};
```

---

### [1er Parcial 2022] Práctica - Operaciones sobre una pantalla de píxeles con menú

Escriba un programa en lenguaje C que permita realizar operaciones sobre los elementos de una pantalla color de 3×4 píxeles. El programa debe pedir que el usuario elija el tipo de función a realizar de acuerdo al siguiente menú:

```
Presione un número para seleccionar la operación deseada:
1 – Transponer la pantalla.
2 – Hacer que la pantalla represente una línea horizontal.
3 – Imprimir todos los colores.
4 – Intercambiar colores.
0 – Salir del programa.
```

- Las opciones 1 y 2 deben invocar funciones que solo impriman el nombre de la operación seleccionada.
- La opción 3 debe imprimir la matriz de colores con columnas alineadas.
- La opción 4 debe solicitar las coordenadas del pixel a modificar (validadas), y permitir intercambiar: RR↔BB, RR↔GG o BB↔GG. Debe imprimirse la matriz original y la versión modificada. La salida debe ser confirmada.

Para probar se utilizará:

```c
int colores[3][4] = {2043453, 255, 65280, 16711680,
                     11189196, 1056816, 15852243, 2241365,
                     2311527, 9008675, 10836662, 16702650};
```

Cada color se almacena en memoria con sus componentes BB GG RR 00.

---

### [1er Recuperatorio 2021] Práctica - Menú con vector de flotantes y operaciones matriciales

Escriba un programa en lenguaje C que cumpla con los siguientes requisitos:

Solicite al usuario que ingrese doce (12) números en formato de punto flotante y queden almacenados en un vector. Se puede utilizar como datos iniciales: `{2.14, 4.56, 6.54, 9.87, 3.21, 5.43, 4.32, 7.65, 1.23, 3.56, 4.87, 9.32}`.

Muestre un menú que permita efectuar las siguientes operaciones (repetir hasta que el usuario confirme la salida):

a) Calcular la **dispersión** de los valores ingresados e imprimir el resultado.

b) A partir de los datos ingresados, crear las posibles matrices cuadradas (2×2 y 3×3) y establecer los elementos ubicados por debajo de la diagonal iguales a 0. Imprimir los resultados.

c) Imprimir los datos con las dimensiones que fije el usuario por teclado (verificar consistencia de dimensiones).

d) Modificar el vector intercambiando los valores en forma especular (el primero con el último, el segundo con el penúltimo, etc.). Imprimir el resultado.

Se evaluará: ausencia de errores y warnings, criterio de modularización y reutilización de funciones.

---

### [Recu. 1er Parcial] Práctica - Máscara de intercambio de bytes entre arreglos

Una matriz de valores enteros de 4×4 determina una máscara que debe aplicarse a dos arreglos de 4 elementos de 32 bits. Si en la posición `[i, j]` de la máscara aparece un `1`, se intercambian entre los i-ésimos enteros de los arreglos el j-ésimo elemento de 8 bits, como se observa en el ejemplo:

```c
mascara  = {{1,0,0,0}, {0,1,0,0}, {0,0,1,0}, {0,0,0,1}};
valores1 = {0x0a1a2a3a, 0x4a5a6a7a, 0x8a9aaaba, 0xcadaeafa};
valores2 = {0x0b1b2b3b, 0x4b5b6b7b, 0x8b9babbb, 0xcbdbebfb};

// Luego de aplicar la máscara:
valores1 = {0x0b1a2a3a, 0x4a5b6a7a, 0x8a9aabba, 0xcadaeafb};
valores2 = {0x0a1b2b3b, 0x4b5a6b7b, 0x8b9baabb, 0xcbdbebfa};
```

Realizar un programa en lenguaje C que muestre los arreglos de valores, aplique la máscara y vuelva a mostrar los arreglos.

Se evaluará la prolijidad del código, el diseño de las funciones (nombre, parámetros y valores de retorno) y los comentarios.

---

### [1er Parcial] Teoría - Acceso fuera de rango en un array y efecto sobre otras variables

Indique qué valor se imprime en la consola de salida luego de ejecutarse el `printf()`. Justifique este comportamiento:

```c
uint8_t array[10];
uint8_t value = 127;
for (int i = 0; i <= 10; i++)
{
    array[i] = i;
}
printf("La variable valor es = %d \n", value);
```

---

### [1er Recuperatorio 2024] Práctica - Menú con operaciones sobre una matriz

Escriba un programa en lenguaje C que opere sobre una matriz de 4 filas y 5 columnas de datos de tipo `short int` (2 bytes) y que cumpla con los siguientes requisitos:

Muestre el siguiente menú que permita al usuario efectuar las operaciones indicadas. El mismo debe asegurarse de que no se puedan seleccionar las opciones 2 a 6 sin que se haya efectuado primero el correcto ingreso de datos. Una vez habilitadas, el usuario puede volver a ingresar nuevos valores si lo requiere. Si se quiere salir se debe pedir confirmación. Los valores originales **no** deben ser modificados salvo que se ejecute la opción 1 nuevamente.

```
Por favor elija una opción:
1 – Ingresar datos
2 – Imprimir matriz
3 – Modificar datos
4 – Vector componentes pares
5 – Vector componentes impares
6 – Imprimir productoria
7 – Salir
Ingrese una opción: __
```
