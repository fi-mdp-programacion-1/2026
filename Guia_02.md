# Guía de Trabajos Prácticos - Unidad 2
## Materia: Programación 1

## Ejercicios de la Práctica

Unidad Nº 2: Tipos de datos y E/S

### Preguntas orientadoras

1) Mencione por qué resulta de importancia que un dato tenga un tipo de dato asociado.
2) Identifique los tipos de datos mencionados en clase y verifique el rango (valores mínimo y máximo) de cada uno de acuerdo al tamaño establecido.
3) Mencione en qué casos se utiliza el tipo de dato `void`.
4) Escriba el formato de declaración de los tipos de datos variables y constantes y mencione cuál es la diferencia entre ambos.
5) Indique en qué casos se utiliza el casting y piense cuáles pueden ser los riesgos al utilizarlo. Dé ejemplos.
6) Indique qué ocurre cuando se realiza una operación entre datos de diferente tipo.
7) Establezca la diferencia entre el operador `==` y el operador `=`. Piense en ejemplos.
8) Genere el esqueleto básico de un programa en C (archivos de cabecera, funciones, programa principal).
9) Enumere las ventajas de generar funciones o subprogramas.
10) Identifique cuál es la diferencia entre la declaración, la definición y la invocación de una función. Muestre en qué parte del programa va ubicada cada una y por último realice un ejemplo.
11) Mencione qué significa pasar parámetros por valor.
12) Analice las distintas formas de finalizar un programa y piense qué implicancias tiene cada una.
13) Muestre la diferencia entre las funciones `printf` y `puts`. Respecto de `printf`, identifique cuál es su "potencialidad" y también cuál es su "peligrosidad".

### Ejercicios

1) ¿Cuál es la salida que produce las siguientes llamadas a la función `printf`?

```c
a) printf("%6d,%4d", 86, 1040)
b) printf("%12.5e", 30.253)
c) printf("%.4f", 83.162)
d) printf("%-6.2g", .0000009979)
```

2) Escriba el formato que debe incluirse en la función `printf` para que se muestre una variable `x` de tipo `float` en los siguientes casos:
   - Notación exponencial; justificado a la izquierda en un campo de tamaño 8 y 1 dígito después del punto decimal.
   - Notación exponencial; justificado a la derecha en un campo de tamaño 10 y 6 dígitos después del punto decimal.
   - Notación decimal fija; justificada a la izquierda en un campo de tamaño 8 y 3 dígitos después del punto decimal.
   - Notación decimal fija; justificada a la derecha en un campo de tamaño 6; sin dígitos después del punto decimal.

3) Suponga que se llama a la función `scanf`:

```c
scanf("%d%f%d", &i, &x, &j)
```

Si el usuario ingresa: `10.3 5 6<enter>`. ¿Cuáles serán los valores de `i`, `x` y `j` suponiendo que `i` y `j` son variables de tipo `int` y `x` es variable de tipo `float`?

4) Escribir un programa que permita ingresar un código ASCII, por ejemplo el 66, y luego imprima el carácter al cual corresponde.

5) La masa de una molécula de agua es aproximadamente `3.10E-23` g. Una pinta de agua pesa aproximadamente 425 gramos. Escribir un programa que solicite una cantidad de agua (en pintas) y muestre el número de moléculas de agua correspondiente.

6) Escriba un programa que permita al usuario ingresar una fecha en el formato `dd/mm/yyyy` y la imprima en formato `yyyymmdd`.

### Actividades extra

1) Los libros se identifican con un número ISBN (International Standard Book Number). Los ISBNs asignados después del 1 de enero del 2007 contienen 13 dígitos, dispuestos en 5 grupos: `978-0-393-97950-3` (ejemplo). El primer grupo (prefijo GSI) puede ser 978 o 979. El identificador de grupo especifica el lenguaje o país de origen. El código del editor identifica el editor. El número de artículo es el identificador que el editor le asigna a cada libro. El grupo final es un dígito verificador. Escribir un programa que separe en grupos un ISBN ingresado por el usuario.

> **Nota:** el número de dígitos de cada grupo puede variar. Probar el programa con varios ISBNs de libros conocidos.

2) Utilizando `printf`, el carácter asterisco (`*`) y el carácter suma (`+`) mostrar un dibujo en pantalla.

---

## Ejercicios de Exámenes Anteriores

> Los siguientes ejercicios fueron extraídos de primeros parciales y recuperatorios de años anteriores. Corresponden a los temas de esta unidad.

---

### [1er Parcial 2024] Teoría - Operadores bit a bit

Explicar el comportamiento de las siguientes sentencias, indicando en qué caso las utilizaría. En todos los casos `valor` representa una variable entera.

```c
a) valor & 0x80000
b) valor & 0x00001
c) valor >> 4
d) valor << 32
```

---

### [1er Recuperatorio 2024] Teoría - Comportamiento de scanf con tipos incorrectos

Se tiene el siguiente programa para probar cómo se almacenan en memoria los números enteros y flotantes:

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

Para probarlo, cuando se le solicita que ingrese un flotante el usuario teclea `2.75<Enter>`. El programa entonces finaliza.

Indique si el comportamiento del programa es el adecuado, y explique por qué se muestran esos valores en la consola de salida.

---

### [1er Recuperatorio 2024] Teoría - Posibles valores que hacen verdadera una expresión

Indique todos los posibles valores de las variables utilizadas que hacen resultado verdadero:

```c
resultado = (c>='a' && c<='z' || c>='A' && c<='Z');
resultado = ((a>2) || (b==4)) && (!c);
resultado = ((15>i)>(14<i)) && (!(k>(70%2)));
```

---

### [1er Recuperatorio 2022] Teoría - Cadenas sin terminador nulo y buffer stdin

a) Explique por qué las salidas de las sentencias `printf` tienen la forma mostrada (siendo el último tramo valores basura que existen en memoria):

```c
unsigned char cadena1[4] = {0x68, 0157, 0x6C, 0x61};
unsigned char cadena2[10] = "unodostres";
printf("\n %s", cadena1); // IMPRIME: holaqQkòÜº▄~Ä'v║æ¢û£
printf("\n %s", cadena2); // IMPRIME: unodostresholaqQkòÜº▄~Ä'v║æ¢û£
```

b) Introduzca todas las correcciones necesarias para que el código muestre sólo:
```
hola
unodostres
```

---

### [1er Recuperatorio 2022] Teoría - Justificación de salida con scanf y tipos incompatibles

Justifique la salida que produce el siguiente fragmento de código C para la entrada especificada. Indique y justifique el contenido residual del buffer `stdin`:

```c
int i, j;
float k;
scanf("\n %d %f %d", &i, &j, &k); // ENTRADA: 5.2 7 8
printf("\n %d %d %e", i, j, k);   // IMPRIME: 5 1045220557 9.809089e-045
```

---

### [1er Parcial 2023] Teoría - Representación en memoria y operaciones bit a bit

Explique qué pasos de programación debería efectuar para obtener un vector de caracteres cuyos valores se carguen de acuerdo a los valores de los 8 bits de una variable de tipo `char`. Si el bit analizado es `1`, en la posición correspondiente del vector debe almacenarse una `'s'`; en caso contrario, una `'n'`.

Ejemplo: si la variable tiene el valor `0xC3` (binario `11000011`) se obtiene un vector `{'s', 's', 'n', 'n', 'n', 'n', 's', 's'}`.

Muestre qué valores se obtienen para `c = 0x1A`.

---

### [1er Parcial 2022 / 2023] Teoría - Comportamiento de tipos de datos y representación IEEE 754

Indique qué valor se le asigna a la variable `entero` y por qué:

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

---

### [1er Parcial 2023] Teoría - Lectura del contenido de memoria y printf

Se tiene la siguiente secuencia de instrucciones en un programa escrito en C:

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

Considerando que el orden de almacenamiento en memoria es `cValor/iValor/dValor` (uno a continuación del otro), indique qué se imprimirá en pantalla. Justifique brevemente su respuesta.

---

### [1er Parcial] Teoría - Manipulación de bits sobre un registro

Se tiene una variable de tipo `uint8_t` que representa el contenido de un registro externo mediante el cual se monitorea y controla un dispositivo. Realice las operaciones necesarias de forma de:

a) Hacer que el bit 3 adopte el valor `1` (independientemente del valor que tenga), sin modificar el resto de los bits.

b) Hacer que el bit 6 adopte el valor `0` (independientemente del valor que tenga), sin modificar el resto de los bits.
