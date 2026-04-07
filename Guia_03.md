# Guía de Trabajos Prácticos - Unidad 3
## Materia: Programación 1

## Ejercicios de la Práctica

Unidad Nº 3: Funciones y ámbito de variables

### Preguntas orientadoras

1) Diga en sus palabras qué significa ámbito o alcance de una variable.
2) ¿Cuál es el peligro de que varias funciones vean o puedan modificar una misma variable?
3) ¿Cómo puedo hacer para que varias funciones vean una misma variable sin declararla como global?
4) Realice un esquema que relacione el espacio de trabajo (workspace) con distintos proyectos (projects) y sus respectivos archivos fuente. Indique las funciones que desempeñan el compilador (compiler) y el linkeador (linker) en esas relaciones.
5) Analice el efecto del modificador de variable `static`. Indique qué representa este modificador cuando se lo utiliza para funciones.
6) En qué situaciones es conveniente pasar un parámetro por valor y en cuáles conviene pasarlo por referencia.
7) Mencione una forma equivalente a paso por referencia utilizando paso por valor. ¿Es recomendable utilizar esta forma?
8) Complete cada uno de los siguientes espacios en blanco:
   - En C un módulo de programa o subprograma se conoce como: __________________________.
   - Una función se invoca mediante una ________________.
   - Una variable que es conocida sólo dentro de la función en la cual está definida se conoce como _______.
   - La palabra reservada `______` se utiliza en el encabezado de función para indicar que la misma no retornará un valor o para indicar que la función no contiene parámetros.
   - La ____________ o _____________ le permite al compilador verificar el número, tipos y orden de los argumentos pasados a una función.
   - Una función que se llama a sí misma, ya sea directa o indirectamente es una función _____________.

### Ejercicios

1) Realizar un programa que permita elegir entre calcular el perímetro de una circunferencia, el área de un círculo y el volumen de una esfera. La impresión del menú debe aparecer en una función distinta que la carga de la opción elegida. Ambas definiciones de función, tanto la de impresión del menú como la de lectura de la opción deben aparecer en un único archivo `*.c` distinto al `main.c`. Sus prototipos deben ser definidos en un archivo `.h`. Finalmente imprimir desde el `main` la opción seleccionada.

2) Pedir al usuario que ingrese un valor de radio y generar las funciones que calculen lo indicado en el menú del ejercicio 1. Colocar todas las funciones que se parezcan en un mismo archivo `*.c` distinto del `main.c`. Utilizar la directiva `#include` para incluir las declaraciones de las funciones. Por último mostrar los resultados obtenidos para el radio ingresado.

3) Tipee el siguiente programa en Code Blocks y antes de correrlo comentar cada línea de código indicando que cree que ocurre, luego haga una corrida paso a paso y verifique lo comentado.

```c
#include <stdio.h>

void a_local(void);
void b_static(void);
void c_global(void);

int x_global_local = 1;

int main(void)
{
    int x_global_local = 5;
    printf("La variable x_global_local dentro de main es: %d.\n", x_global_local);

    {
        int x_global_local = 7;
        printf("La variable x_global_local en el subbloque de main es: %d.\n",
                  x_global_local);
    }

    printf("La variable x_global_local en main es: %d.\n", x_global_local);
    a_local();
    b_static();
    c_global();
    printf("\n\n*****Resultados luego de invocar por segunda vez a las funciones a, b"
               " y c*****\n");
    a_local();
    b_static();
    c_global();
    printf("\nLa variable x_global_local en main es: %d.\n", x_global_local);

    return 0;
}

void a_local(void)
{
    int x_global_local = 25;
    printf("\nLa variable x_global_local luego de entrar en a_local es: %d.\n",
              x_global_local);
    x_global_local++;
    printf("La variable x_global_local antes de salir de a_local es: %d.\n",
              x_global_local);
}

void b_static(void)
{
    static int x_global_local = 50;
    printf("\nLa variable x_global_local al entrar en b_static es: %d.\n",
               x_global_local);
    x_global_local++;
    printf("La variable x_global_local antes de salir de b_static es: %d.\n",
              x_global_local);
}

void c_global(void)
{
    printf("\nLa variable x_global_local en c_global es: %d.\n", x_global_local);
    x_global_local *= 10;
    printf("La variable x_global_local antes de salir de c_global es: %d.\n",
              x_global_local);
}
```

4) Encuentre cuáles son los errores existentes en las siguientes secciones de programa:

```c
a) int func_g(void){printf("Dentro de g\n"); int func_h(void){printf("Dentro de h\n");}}

b) int sum(int x, int y)
   {
       int result;
       result = x + y;
   }

c) void product(void)
   {
       int a, b, c, result;
       printf("Ingrese 3 números: ")
       scanf("%d%d%d", a, b, c);
       result = a * b * c;
       printf("El resultado es %d", result);
       return result;
   }
```

5) Una fábrica de artículos electrónicos contrató a 3 vendedores para la promoción y venta de sus productos. El sueldo de cada vendedor será igual al 10% del monto total de su venta. Realizar un programa que cargando el nombre de cada vendedor y su venta, determine:
   - a) El sueldo de cada vendedor.
   - b) El monto total de ventas.
   - c) El porcentaje que representa cada venta sobre el total de ventas realizadas y las diferencias existentes con los otros vendedores.

6) Realizar las siguientes funciones de conversión en un mismo archivo:
   - a) Conversión de decimal a hexadecimal.
   - b) Conversión de hexadecimal a decimal.
   - c) Conversión de decimal a ASCII.

7) Ingrese un número y realice los siguientes cálculos: raíz cuadrada, logaritmo natural, logaritmo en base 10, 5ta potencia, valor absoluto, identifique el entero más próximo por encima y por debajo. *Ayuda: incluya la librería `math.h`.*

8) Calcular la corriente que circula en una resistencia dados los valores de tensión y resistencia. La función `main()` se dedica solo a llamar al resto de las funciones que realizan los cálculos y retornan `void`. *Ayuda: La corriente (I) es igual a la razón entre la tensión (V) y la resistencia (R).*

---

## Ejercicios de Exámenes Anteriores

> Los siguientes ejercicios fueron extraídos de primeros parciales y recuperatorios de años anteriores. Corresponden a los temas de esta unidad.

---

### [1er Recuperatorio 2022] Teoría - Modificador static y paso de parámetros

a) Explique el significado del modificador de ámbito `static`. Dé ejemplos de su uso en lenguaje C cuando se utiliza en la declaración de una variable y en una función.

b) Explique qué significa pasar parámetros a una función por valor y por referencia.

c) ¿Los arreglos se pasan por referencia o por valor?

d) Si al pasar un arreglo como parámetro es necesario asegurar que **no** se modifiquen sus elementos, ¿existe alguna forma en lenguaje C de indicárselo al compilador?

---

### [1er Recuperatorio 2024] Teoría - Uso del modificador static

Explique el significado del modificador de ámbito `static`. Dé ejemplos de su uso en lenguaje C cuando se utiliza:

a) En la declaración de una variable.

b) Con una función.

---

### [1er Parcial 2024] Teoría - Paso por referencia con un solo parámetro

Los vectores son pasados como parámetro a una función por referencia.

a) ¿Cómo puedo asegurar que sus componentes no puedan ser modificadas por la función invocada?

b) En el caso de que la función admita sólo un parámetro y necesite modificar el valor del mismo, ¿es indispensable que sea pasado por referencia? Justifique su respuesta.
