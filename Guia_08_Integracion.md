# Guía de Integración - Exámenes Completos
## Materia: Programación 1

> Esta guía contiene los exámenes completos de años anteriores organizados cronológicamente. Está pensada para la preparación integral antes de cada instancia evaluativa.
>
> **Cronograma de temas:**
> - **1er Parcial:** Unidades 1–5 (introducción, tipos/E-S, funciones, estructuras de control, arreglos)
> - **2do Parcial:** Unidades 6–7 (punteros/memoria dinámica, archivos)

---

## Año 2022

### [1er Parcial 2022]

#### Parte Teórica

1. ¿Cuáles fueron las tecnologías que definieron cada una de las 4 primeras generaciones de computadoras?

2. ¿Cuáles son las diferencias más significativas entre la primera y la segunda generación de computadoras?

3. ¿Qué representaciones gráficas existen para describir un algoritmo? Comente brevemente cada una.

4. Responda brevemente:
   a) ¿Cuál es la diferencia entre un compilador y un intérprete?
   b) ¿Cuáles son las estructuras básicas del lenguaje estructurado?
   c) ¿Cuál es la función de un programa ensamblador?

5. Identifique y corrija el/los errores en cada una de las siguientes sentencias:

```c
a) Scanf("%d", variable_tipo_int);

b) if (x=y);
   {
       printf (%d es igual a %d\n", x);
   }

c) Printf ("El valor ingresado es: %d\n, &valor")

d) Printf("La suma es %d\n," x+y);
```

6. Indique todos los posibles valores de las variables utilizadas que hacen `resultado` verdadero:

```c
resultado = (c>='a' && c<='z' || c>='A' && c<='Z');
resultado = ((a>2) || (b==4)) && (!c);
resultado = ((15>i)>(14<i)) && (!(k>(70%2)));
```

7. Indique qué valor se le asigna a la variable `entero` y por qué:

```c
#include <stdio.h>

#define VALOR 3.4176927e-3

int main(void)
{
    int entero = 50;
    float fValor = VALOR;

    if(fValor == VALOR)
    {
        entero = 100/37;
    }
    else
    {
        entero = 200/19;
    }

    return 0;
}
```

#### Parte Práctica

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

### [1er Recuperatorio 2022]

#### Parte Teórica

1. Explique el significado del modificador de ámbito `static`. Dé ejemplos de su uso en lenguaje C cuando se utiliza en la declaración de una variable y en una función.

2. Explique qué significa pasar parámetros a una función:
   a) Por valor y por referencia.
   b) ¿Los arreglos se pasan por referencia o por valor?
   c) Si al pasar un arreglo como parámetro es necesario asegurar que **no** se modifiquen sus elementos, ¿existe alguna forma en lenguaje C de indicárselo al compilador?

3. Justifique la salida que produce el siguiente fragmento de código C para la entrada especificada. Indique y justifique el contenido residual del buffer `stdin`:

```c
int i, j;
float k;
scanf("\n %d %f %d", &i, &j, &k); // ENTRADA: 5.2 7 8
printf("\n %d %d %e", i, j, k);   // IMPRIME: 5 1045220557 9.809089e-045
```

4. Explique por qué las salidas de las sentencias `printf` tienen la forma mostrada (siendo el último tramo valores basura que existen en memoria):

```c
unsigned char cadena1[4] = {0x68, 0157, 0x6C, 0x61};
unsigned char cadena2[10] = "unodostres";
printf("\n %s", cadena1); // IMPRIME: holaqQkòÜº▄~Ä'v║æ¢û£
printf("\n %s", cadena2); // IMPRIME: unodostresholaqQkòÜº▄~Ä'v║æ¢û£
```

Introduzca todas las correcciones necesarias para que el código muestre sólo:
```
hola
unodostres
```

5. Explicar el efecto del siguiente algoritmo sobre `unsigned char uc = 0x1A` y `unsigned char m = 017`. Indicar los valores intermedios y el resultado final.

```c
unsigned char resultado = 0;
for (int i = 0; i < 8; i++) {
    if (uc & (1 << i))
        resultado |= (m >> i) & 0x01 ? (1 << i) : 0;
}
```

#### Parte Práctica

Escriba un programa en lenguaje C para operar sobre una imagen color de 4×6 píxeles (los datos originales no deben ser modificados). Muestre un menú que permita efectuar las siguientes operaciones (repetir hasta que el usuario confirme la salida):

1. Transponer la imagen.
2. Trazar una línea roja a 45°.
3. Pintar el triángulo inferior de magenta (RR=255, BB=255).
4. Imprimir todos los colores en hexadecimal.
5. Sustituir la componente verde (GG) por su complementaria.

Datos de prueba (vector de 24 `unsigned int`, almacenamiento BB GG RR Alpha):
```c
unsigned int memory[] = {
    0x3d2e1f00, 0xff000000, 0x00ff0000, 0x0000ff00,
    0xabcdef00, 0x12345600, 0xfedcba00, 0x98765400,
    0x11223300, 0x44556600, 0x77889900, 0xaabbcc00,
    0xddeeff00, 0x00112200, 0x33445500, 0x66778800,
    0x99aabb00, 0xccddef00, 0x010203ff, 0x040506ff,
    0x070809ff, 0x0a0b0cff, 0x0d0e0fff, 0x10111200
};
```

---

### [2do Parcial 2022]

#### Parte Práctica

Escriba un programa en lenguaje C para gestionar una biblioteca. Los datos se almacenan en un archivo binario con el siguiente formato:

- `unsigned short`: cantidad de ejemplares.
- Por cada ejemplar: título (longitud + string), autores (longitud + string), código (`unsigned long`), páginas (`unsigned int`), fecha de publicación (día, mes, año como `unsigned short`), idioma (`char`: `'S'`=español, `'E'`=inglés, `'O'`=otro).

El programa debe mostrar el siguiente menú (repetir hasta que el usuario salga):

```
1 – Ordenar libros por título.
2 – Ordenar libros por código.
3 – Ordenar libros por cantidad de páginas.
4 – Ordenar libros por fecha de publicación.
5 – Imprimir biblioteca (en pantalla y en archivo de texto).
0 – Salir (con confirmación).
```

Se evaluará: ausencia de errores y warnings, modularización, manejo correcto del archivo binario con longitudes variables.

---

## Año 2023

### [1er Parcial 2023]

#### Parte Teórica

1. ¿Cuáles fueron las tecnologías que definieron cada una de las 4 primeras generaciones de computadoras? ¿Cuáles son las diferencias más significativas entre la primera y la segunda generación?

2. ¿Qué representaciones gráficas existen para describir un algoritmo? Comente brevemente cada una.

3. Identifique y corrija el/los errores en cada una de las siguientes sentencias:

```c
a) Scanf("%d", variable_tipo_int);

b) if (x=y);
   {
       printf (%d es igual a %d\n", x);
   }

c) Printf ("El valor ingresado es: %d\n, &valor")

d) Printf("La suma es %d\n," x+y);
```

4. Explique qué pasos de programación debería efectuar para obtener un vector de caracteres cuyos valores se carguen de acuerdo a los valores de los 8 bits de una variable de tipo `char`. Si el bit analizado es `1`, en la posición correspondiente del vector debe almacenarse una `'s'`; en caso contrario, una `'n'`.

   Muestre qué valores se obtienen para `c = 0x1A`.

5. Indique qué valor se le asigna a la variable `entero` y por qué:

```c
#include <stdio.h>
#define VALOR 3.4176927e-3

int main(void) {
    int entero = 50;
    float fValor = VALOR;
    if(fValor == VALOR) { entero = 100/37; }
    else                { entero = 200/19; }
    return 0;
}
```

6. Indique las cuatro formas de incrementar en 1 una variable entera en lenguaje C.

7. Se tiene la siguiente secuencia de instrucciones en un programa escrito en C:

```c
int main()
{
    double dValor;
    int iValor;
    char cValor[8];

    // funciones que asignan valores a las variables

    printf("%e\n%d\n%s", dValor, iValor, cValor);

    return 0;
}
```

Al ejecutar en modo debug y frenar en el `return`, se consulta la memoria con `Address: cValor, Bytes: 32`, obteniendo:

```
0x61fe0c: 31 41 42 43 44 39 38 30 | 40 33 66 1a a3 c7 75 7b
0x61fe1c: 57 04 60 c0 b0 14 02 00 | 00 00 00 00 c7 13 40 00
```

Considerando que el orden de almacenamiento en memoria es `cValor/iValor/dValor` (uno a continuación del otro), indique qué se imprimirá en pantalla. Justifique brevemente.

#### Parte Práctica

Escriba un programa en lenguaje C con al menos 7 funciones que permita procesar arreglos de enteros con el siguiente menú (repetir hasta que el usuario salga):

```
1 – Ingreso de valores (longitud variable, máximo 50).
2 – Imprimir valores en formato de vector columna.
3 – Determinar si un número está en el arreglo.
4 – Contar cantidad de números pares.
5 – Calcular el valor máximo y su índice.
6 – Imprimir en formato matricial m×n (dimensiones a elección del usuario).
7 – Imprimir en formato matricial n×m (traspuesta).
0 – Salir.
```

Las opciones 2–7 no pueden ejecutarse sin haber cargado datos primero (opción 1). Se evaluará: ausencia de errores y warnings, criterio de modularización y reutilización de funciones.

---

### [2do Parcial 2023]

#### Parte Teórica

1. Indique si son verdaderas (V) o falsas (F) las siguientes afirmaciones, justificando brevemente en todos los casos:

   a) Una unión (`union`) permite almacenar simultáneamente todos sus miembros en la misma dirección de memoria.

   b) Las estructuras (`struct`) siempre se pasan a funciones por referencia.

   c) Un puntero a `int` y un puntero a `char` tienen el mismo tamaño en un sistema de 64 bits.

   d) Incrementar un puntero a `int` en 1 avanza 1 byte en memoria.

   e) Las variables locales a una función se almacenan en el stack.

2. Corrija las siguientes asignaciones de punteros (indique el error y la corrección):

```c
a) int *p = 5;
b) int x = 10; int **pp = &x;
c) float f = 3.14; int *p = &f;
d) int arr[5]; int *p = arr[0];
```

3. Se tiene el siguiente fragmento de código:

```c
short **ptr = (short **)malloc(3 * sizeof(short *));
ptr[0] = (short *)malloc(4 * sizeof(short));
ptr[1] = (short *)malloc(4 * sizeof(short));
ptr[2] = (short *)malloc(4 * sizeof(short));
```

Suponga que `malloc` asignó:
- `ptr` en `0x009A1898`
- `ptr[0]` en `0x009A18B0`
- `ptr[1]` en `0x009A18C0`
- `ptr[2]` en `0x009A18D0`

Y que el volcado de memoria muestra los siguientes bytes (little-endian, `short` = 2 bytes):

```
0x009A1898: B0 18 9A 00  C0 18 9A 00  D0 18 9A 00  00 00 00 00
0x009A18B0: 01 00 02 00  03 00 04 00  05 00 06 00  07 00 08 00
0x009A18C0: 09 00 0A 00  0B 00 0C 00  0D 00 0E 00  0F 00 10 00
0x009A18D0: 11 00 12 00  13 00 14 00  15 00 16 00  17 00 18 00
```

Calcule el valor hexadecimal de: `ptr[1][2]`, `**ptr`, `*ptr`, `*(ptr+2)`, `&ptr[1][1]`, `ptr[0][6]`.

#### Parte Práctica

Escriba un programa en C que procese una foto en formato RAW binario. El archivo tiene el siguiente formato: secuencia de píxeles (cada uno formado por 4 `uint8_t`: R, G, B, Alpha), y al final del archivo los valores de `filas` y `columnas` (un `uint16_t` cada uno).

El programa recibe por línea de comandos el nombre del archivo de entrada y el nombre del archivo de salida. El `main()` debe invocar las siguientes funciones:

1. `validar_parametros()` – verifica que los argumentos sean válidos.
2. `recuperar_datos()` – lee el archivo binario y carga los datos.
3. `imprimir_datos(..., canal)` – imprime en pantalla la matriz del canal especificado (rojo, verde o azul).
4. `modificar_datos()` – reemplaza el canal Alpha de cada píxel por el promedio de R, G, B.
5. `imprimir_datos(..., alpha)` – imprime la matriz Alpha modificada en un archivo de texto.
6. `ordenar_datos()` – ordena los píxeles por valor Alpha (ascendente).
7. `guardar_datos()` – guarda los datos modificados en el archivo de salida binario con el mismo formato.

Se evaluará: ausencia de errores y warnings, modularización, uso correcto de `fread`/`fwrite`/`fseek`.

---

## Año 2024

### [1er Parcial 2024]

#### Parte Teórica

1. Explicar el comportamiento de las siguientes sentencias, indicando en qué caso las utilizaría. En todos los casos `valor` representa una variable entera:

```c
a) valor & 0x80000
b) valor & 0x00001
c) valor >> 4
d) valor << 32
```

2. De acuerdo al teorema de Böhm y Jacopini (1966), todo programa puede escribirse utilizando únicamente tres estructuras básicas de control. Se debe catalogar un nuevo lenguaje que implementa sólo sentencias secuenciales, lazos `for()` y bucles `do-while()`. ¿Se puede realizar cualquier programa con este nuevo lenguaje? Justifique su respuesta.

3. Los vectores son pasados como parámetro a una función por referencia.
   a) ¿Cómo puedo asegurar que sus componentes no puedan ser modificadas por la función invocada?
   b) En el caso de que la función admita sólo un parámetro y necesite modificar el valor del mismo, ¿es indispensable que sea pasado por referencia? Justifique su respuesta.

4. Identifique y corrija el/los errores en cada una de las siguientes sentencias:

```c
a) Scanf("%d", variable_tipo_int);

b) if (x=y);
   {
       printf (%d es igual a %d\n", x);
   }

c) Printf ("El valor ingresado es: %d\n, &valor")

d) Printf("La suma es %d\n," x+y);
```

#### Parte Práctica

Escriba un programa en lenguaje C que opere sobre una matriz `unsigned char` de 3 filas y 12 columnas (o equivalentemente, 3 filas con 12 valores por fila). El programa debe mostrar el siguiente menú:

```
1 – Ingresar valores.
2 – Imprimir valores originales.
3 – Imprimir valores modificados.
4 – Trasponer bits: para cada elemento, hacer swap entre el bit de la fila y el bit de la columna.
5 – Multiplicar todos los elementos por un escalar (verificar desborde).
6 – Sumar una columna (validar columna válida).
7 – Salir (con confirmación).
```

La opción 4 (trasposición de bits): dado el elemento en posición (fila, columna), intercambiar el bit en posición `fila` con el bit en posición `columna` dentro del byte. Por ejemplo: elemento en fila 2, col 1 con valor `0x54 = 0101 0100b` → swap bit2 y bit1 → `0x52 = 0101 0010b`.

Datos de prueba:
```c
unsigned char datos[] = {217, 156, 134, 98, 231, 254, 243, 65, 123, 56, 48, 232};
```

Se evaluará: ausencia de errores y warnings, criterio de modularización.

---

### [1er Recuperatorio 2024]

#### Parte Teórica

1. Se tiene el siguiente programa para probar cómo se almacenan en memoria los números enteros y flotantes:

```c
#include <stdio.h>

int main()
{
    int entero = 3;
    float flotante = 1.5;

    printf("Ingreso un flotante: ");
    scanf("%d", &flotante);
    printf("Ingreso un entero: ");
    scanf("%f", &entero);

    printf("\n\nValor del int = %d; y del float = %.8e\n", entero, flotante);

    return 0;
}
```

Cuando se le solicita que ingrese un flotante el usuario teclea `2.75<Enter>`. El programa entonces finaliza. Indique si el comportamiento del programa es el adecuado, y explique por qué se muestran esos valores en la consola de salida.

2. Indique todos los posibles valores de las variables utilizadas que hacen `resultado` verdadero:

```c
resultado = (c>='a' && c<='z' || c>='A' && c<='Z');
resultado = ((a>2) || (b==4)) && (!c);
resultado = ((15>i)>(14<i)) && (!(k>(70%2)));
```

3. Explique el significado del modificador de ámbito `static`. Dé ejemplos de su uso en lenguaje C cuando se utiliza:
   a) En la declaración de una variable.
   b) Con una función.

4. Explique por qué las salidas de las sentencias `printf` tienen la forma mostrada:

```c
unsigned char cadena1[4] = {0x68, 0157, 0x6C, 0x61};
unsigned char cadena2[10] = "unodostres";
printf("\n %s", cadena1); // IMPRIME: holaqQkòÜº▄~Ä'v║æ¢û£
printf("\n %s", cadena2); // IMPRIME: unodostresholaqQkòÜº▄~Ä'v║æ¢û£
```

Introduzca todas las correcciones necesarias para que el código muestre sólo:
```
hola
unodostres
```

5. Para cada una de las siguientes afirmaciones, indique si es verdadera (V) o falsa (F). En caso de ser falsa, indique cuál es el error. Justifique brevemente:

   a) Las computadoras de la primera generación se programaban en B (lenguaje que sirvió de base al C).

   b) Aunque el consumo de las computadoras valvulares era mucho mayor que las transistorizadas, su confiabilidad era mayor.

   c) Con la aparición de los circuitos integrados se posibilitó un avance significativo en el diseño de periféricos que le brindó una mayor flexibilidad a la computadora.

   d) Un bus de direcciones de 32 bits permite manejar un banco de memoria de 8 GBytes.

   e) Un lenguaje compilado siempre es mucho más rápido que uno interpretado.

#### Parte Práctica

Escriba un programa en lenguaje C que opere sobre una matriz de 4 filas y 5 columnas de datos de tipo `short int` (2 bytes) y que cumpla con los siguientes requisitos:

Muestre el siguiente menú (las opciones 2 a 6 no pueden seleccionarse sin que se haya ejecutado correctamente la opción 1; si se quiere salir, pedir confirmación):

```
Por favor elija una opción:
1 – Ingresar datos
2 – Imprimir matriz
3 – Modificar datos: poner MSB=0 en cada elemento; contar bits en 1; si cantidad impar → MSB=1.
4 – Vector de componentes con índice lineal par (imprimir como vector columna).
5 – Vector de componentes con índice lineal impar.
6 – Productoria de la diagonal (verificar desborde).
7 – Salir
```

Los valores originales **no** deben ser modificados salvo que se ejecute la opción 1 nuevamente.

Datos de prueba:
```c
short datos[4][5] = {
    {0x7FAA, 0xFFFF, 0x7FFF, 0x8FFF, 0xF000},
    {0x1234, 0x5678, 0x9ABC, 0xDEF0, 0x1111},
    {0x2222, 0x3333, 0x4444, 0x5555, 0x6666},
    {0x7777, 0x8888, 0x9999, 0xAAAA, 0xBBBB}
};
```

---

### [2do Parcial 2024]

#### Parte Teórica

1. Identifique y corrija los errores en el siguiente código de manejo de archivos:

```c
// Caso a: se intenta escribir en modo lectura binaria
FILE *fp = fopen("mis_datos1.dat", "rb");
fprintf(fp, "%d %f", valor_int, valor_float);
fclose(fp);

// Caso b: se intenta leer el número 9 pero el puntero está al final
FILE *fp = fopen("mis_datos3.dat", "r");
fseek(fp, 0L, SEEK_END);
fscanf(fp, "%d", &numero);
fclose(fp);
```

2. Se tiene el siguiente fragmento de código:

```c
short **ptr = (short **)malloc(3 * sizeof(short *));
for (int i = 0; i < 3; i++)
    ptr[i] = (short *)malloc(4 * sizeof(short));
```

`malloc` asignó `ptr` en `0x009A1898`. El volcado de memoria a partir de esa dirección muestra:

```
Dirección     Bytes (little-endian)
0x009A1898:   98 18 9A 00   A8 18 9A 00   B8 18 9A 00   00 00 00 00
0x009A18A8:   01 00 02 00   03 00 04 00   05 00 06 00   07 00 08 00
0x009A18A8:   09 00 0A 00   0B 00 0C 00   0D 00 0E 00   0F 00 10 00
0x009A18B8:   11 00 12 00   13 00 14 00   15 00 16 00   17 00 18 00
```

Calcule el valor hexadecimal de: `ptr[1][2]`, `**ptr`, `*ptr`, `*(ptr+2)`, `&ptr[1][0]`.

#### Parte Práctica

Escriba un programa en C para gestionar una agenda de contactos. El programa recibe 7 parámetros por línea de comandos:

```
./agenda datos.bin 54 223 1102334 "Armando Esteban Quito" datos.txt
```

donde los parámetros son: nombre del archivo binario de entrada, código de país, código de área, número telefónico, nombre del nuevo contacto, nombre del archivo de texto de salida.

**Formato del archivo binario:** por cada contacto se almacena: `CC` (1 byte sin signo: cantidad de caracteres del nombre incluyendo `\0`), nombre (string de longitud `CC`), `pais` (2 bytes sin signo), `area` (2 bytes sin signo), `numero` (4 bytes sin signo). Al final del archivo: `NC` (2 bytes sin signo: cantidad total de contactos).

El programa debe:
1. Validar los parámetros de línea de comandos.
2. Recuperar los datos del archivo binario.
3. Mostrar todos los contactos en pantalla (Nombre + país-área-número).
4. Ordenar los contactos por nombre de forma ascendente y mostrarlos.
5. Modificar el nombre del contacto cuyo teléfono coincide con los parámetros ingresados, y mostrar la lista actualizada.
6. Guardar la lista ordenada en el archivo de texto de salida (reutilizando la función de impresión).

Datos de prueba:
```c
{"Tom y Jerry",      {56, 225, 1122331}},
{"Los Pitufos",      {54, 223, 1102334}},
{"La Pantera Rosa",  {55, 224, 1102334}}
```

Se evaluará: ausencia de errores y warnings, manejo correcto del archivo binario, modularización, uso correcto de `malloc`/`free`.

---

## Índice de Temas por Examen

| Examen | Teoría | Práctica |
|--------|--------|----------|
| 1er Parcial 2022 | U1: generaciones, algoritmos, compilador; U2: printf/scanf, tipos, expresiones lógicas, IEEE 754 | U5: arreglos 2D, menú, operaciones sobre píxeles |
| 1er Recu. 2022 | U3: static, paso por referencia; U2: scanf/tipos, cadenas sin `\0` | U5: arreglos 2D, operaciones sobre imagen |
| 2do Parcial 2022 | — | U7: archivo binario con strings de longitud variable, ordenamiento |
| 1er Parcial 2023 | U1: generaciones, algoritmos; U2: printf, IEEE 754, memoria; U3: funciones | U5: arreglos, menú completo con 7 funciones |
| 2do Parcial 2023 | U6: punteros dobles, malloc, V/F, corrección | U7: archivos RAW binarios, procesamiento de imagen |
| 1er Parcial 2024 | U2: operadores bit a bit; U1: Böhm-Jacopini; U3: paso por referencia y const | U5: arreglos 2D, menú con trasposición de bits |
| 1er Recu. 2024 | U2: scanf/tipos; U3: static; U1: generaciones V/F; expresiones lógicas; cadenas | U5: arreglos 2D, short int, operaciones por bits |
| 2do Parcial 2024 | U7: errores en fopen/fseek; U6: punteros dobles, malloc | U7: archivo binario con strings, agenda de contactos |
