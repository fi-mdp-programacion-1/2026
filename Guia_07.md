# Guía de Trabajos Prácticos - Unidad 7
## Materia: Programación 1

## Ejercicios de la Práctica

Unidad Nº 7: Archivos

### Preguntas orientadoras

1) Llene los espacios vacíos:
   - a) La función `______` cierra un archivo.
   - b) El enunciado `______` lee datos de un archivo en una forma similar a la forma en que `scanf` lee a partir de `stdin`.
   - c) La función `______` lee un carácter de un archivo especificado.
   - d) La función `______` lee una línea de un archivo especificado.
   - e) La función `______` abre un archivo.
   - f) La función `______` recoloca el puntero de posición de archivo a una posición específica dentro del archivo.

2) Indique cuáles de las siguientes afirmaciones son verdaderas y cuáles son falsas. Para aquellas que son falsas indique por qué:
   - a) La función `fscanf` no puede ser utilizada para leer datos de la entrada estándar.
   - b) El programador debe utilizar `fopen` explícitamente, para abrir los flujos de entrada estándar, salida estándar y error estándar.
   - c) Si el puntero a posición de archivo apunta a una posición en un archivo secuencial distinto al principio del mismo, el archivo debe ser cerrado y vuelto a abrir para leer a partir del principio del mismo.
   - d) La función `fprintf` puede escribir a la salida estándar.
   - e) Los datos en los archivos de acceso secuencial se actualizan siempre sin sobreescribir otros datos.
   - f) No es necesario buscar en todas las posiciones de un archivo de acceso directo para encontrar la posición buscada.
   - g) La función `fseek` puede buscar únicamente en relación con el principio de un archivo.

3) Escriba un enunciado para que se ejecuten cada una de las siguientes:
   - a) Escriba un enunciado que abra el archivo `"trans.dat"` para lectura y asigne el puntero de archivo regresado a `tf_ptr`.
   - b) Escriba un enunciado que abra el archivo `"newmast.dat"` para escritura y asigne el puntero de archivo regresado a `nf_ptr`.
   - c) Escriba un enunciado que lea una estructura del archivo `"oldmast.dat"`. La estructura está formada por un entero `account_num`, por la cadena `name` y por el punto flotante `current_balance`.
   - d) Escriba un enunciado que lea una estructura del archivo `"trans.dat"`. La estructura está formada por un entero `account_num` y por el punto flotante `dollar_amount`.
   - e) Escriba un enunciado que abra el archivo `"oldmast.dat"` para lectura y asigne el puntero de archivo regresado a `of_ptr`.
   - f) Escriba un enunciado que lea una estructura del archivo `"newmast.dat"`. La estructura está formada por un entero `account_num`, por la cadena `name` y por el punto flotante `current_balance`.

### Ejercicios

1) Implementar una función en C que permita comprobar la existencia de un archivo en algún directorio del sistema de archivos. Luego, escriba un programa en C para testearla.

> **Nota:** la firma podría ser: `int exists(const char *fname)`.

2) Implementar una función en C que permita obtener la longitud de un archivo. Luego, escriba un programa en C para testearla.

> **Nota:** la firma podría ser: `long flen(const char *fname)`.

3) Realizar un programa en C que permita al usuario, a través de un menú, realizar las siguientes acciones:
   - Ingresar el nombre de los invitados a una fiesta.
   - Listar en pantalla todos los nombres actualmente ingresados, leídos desde un archivo de texto.
   - Finalizar el programa.

> **Nota:** Este problema se pensó para que el alumno utilice las funciones `fopen`, `fprintf`, `fscanf` y `fclose`.

4) Realizar un programa en C que permita realizar la copia de un archivo. El programa debe recibir dos argumentos al ser llamado desde la línea de comandos. Si la copia es exitosa se debe retornar el valor `0`, sino otro valor.

5) Realizar un programa en C que permita gestionar una agenda de contactos. De cada contacto se debe registrar: nombre, dirección y teléfono. El programa debe permitir mediante un menú:
   - Agregar un contacto.
   - Modificar sus datos pudiéndolo encontrar a través de su identificador único.
   - Borrar un contacto.
   - Mostrar todos los contactos.
   - Mostrar sólo los contactos que comiencen con una letra determinada.

> **Nota:** Este problema se pensó para que el alumno utilice las funciones `fopen`, `fwrite`, `fread` y `fclose`.

---

## Ejercicios de Exámenes Anteriores

> Los siguientes ejercicios fueron extraídos de segundos parciales y recuperatorios de años anteriores. Corresponden a los temas de esta unidad.

---

### [2do Parcial 2024] Teoría - Identificación de errores en manejo de archivos

Identifique y corrija el/los errores (si existen) en cada uno de los siguientes grupos de sentencias:

```c
a) FILE *fp;
   fp = fopen("mis_datos1.dat", "rb");     // el archivo existe
   fprintf(fp, "Datos = %f\n", 3.1416);    // se debe agregar al archivo "Datos = 3.1416"
   fclose(fp);

b) FILE *fp;                               // archivo con los números del 0 al 9
   int cnt = 0;                            // separados por ", " (coma + espacio)
   fp = fopen("mis_datos3.dat", "r");
   fseek(fp, 0L, SEEK_END);
   fscanf(fp, "%d", &cnt);                 // se quiere obtener: cnt = 9
   fclose(fp);
```

---

### [2do Parcial 2023] Práctica - Lectura de foto RAW binaria y procesamiento de colores

Se necesita desarrollar un programa en lenguaje C que permita recuperar información de un archivo que contiene una foto en formato RAW (datos binarios sin compresión) de dimensiones variables. La cantidad de filas y columnas de la imagen se grabaron como dos valores **al final** del archivo. Cada punto de la foto está compuesto por 4 valores `uint8_t` consecutivos: Red, Green, Blue y Alpha.

El programa debe implementar las funciones que se detallan en el `main()`. El programa recibirá por línea de comandos el nombre del archivo original (`foto.bin`) y el nombre del archivo de salida (`foto_procesada`). Cuando la información a guardar sea texto, agregar extensión `.txt`; si es binaria, extensión `.bin`.

```c
int main(int argc, char *argv[])
{
    validar_parametros();
    recuperar_datos();
    imprimir_datos(...., rojo);     // en pantalla
    imprimir_datos(...., verde);    // en pantalla
    imprimir_datos(...., azul);     // en pantalla
    modificar_datos();
    imprimir_datos(...., alpha);    // en archivo de texto
    ordenar_datos();
    guardar_datos();                // en archivo binario
}
```

Se evaluará:
- La elección del tipo de dato para almacenamiento (memoria mínima posible en STACK y HEAP).
- El archivo debe ser leído la **menor cantidad de veces** posible.
- La impresión debe presentarse como matriz bidimensional, usando tabuladores para separar columnas.
- `modificar_datos()`: reemplaza el campo alpha por el promedio de las otras componentes.
- `ordenar_datos()`: ordena usando la componente alpha como criterio de comparación.
- Los datos se guardan en binario respetando el mismo formato con que fueron leídos.

---

### [2do Parcial 2022] Práctica - Gestión de biblioteca con lectura de archivo binario y menú de ordenamiento

Escriba un programa en lenguaje C que permita gestionar las consultas de una biblioteca sobre sus libros. Los mismos se encuentran almacenados en un archivo binario con la siguiente secuencia continua de bytes:

```
unsigned short  // cantidad de ejemplares almacenados
unsigned short  // cantidad de caracteres del título (incluye '\0') = N
char[0..N-1]    // título del ejemplar
unsigned short  // cantidad de caracteres de los autores (incluye '\0') = M
char[0..M-1]    // autores
unsigned long   // código internacional del ejemplar
unsigned int    // cantidad de páginas
unsigned short  // día de la fecha de publicación
unsigned short  // mes de la fecha de publicación
unsigned short  // año de la fecha de publicación
char            // idioma: 'S' = Spanish, 'E' = English, 'O' = Other
// ... datos del resto de los ejemplares con el mismo formato
```

El programa debe permitir ejecutar distintas tareas de acuerdo con el siguiente menú:

```
Presione un número para seleccionar la operación deseada:
1 – Ordenar libros por título.
2 – Ordenar libros por código.
3 – Ordenar libros por cantidad de páginas.
4 – Ordenar libros por fecha de publicación.
5 – Imprimir biblioteca.
0 – Salir del programa.
```

- El menú se ejecuta hasta que el usuario elija salir y confirme su elección.
- Los datos ordenados reemplazarán a los datos originales (opciones 1 a 4).
- La impresión (opción 5) se realiza tanto por pantalla como en un archivo de texto, usando el mismo formato.

Formato de impresión:
```
Titulo: <nombre>
Autores: <nombres>
Codigo: <código>
Paginas: <n>
Fecha: dd/mm/aaaa
Idioma: <O|S|E>
```

---

### [Recu. 2do Parcial] Práctica - Vectores 3D en archivo binario con punteros a función

En un archivo binario se guardaron N vectores posición del espacio 3D. El primer valor almacenado (tipo `uint32_t`) es la cantidad de vectores; a continuación, la lista de 3 componentes de tipo `int32_t` de cada vector.

Se pide realizar un programa en lenguaje C que:

1. Lea los datos del archivo binario y los almacene en el HEAP (campos `x`, `y`, `z` en una estructura `punto_t`).
2. Cree la estructura `vector_t` con un campo de tipo `punto_t *` y un campo `longitud_cuadrado` (`uint32_t`). Almacene en el HEAP los N vectores.
3. Implemente `enviar_vector(FILE *flujo, const vector_t *vec)`: envía con formato a un flujo genérico los valores del vector.
4. Implemente `imprimir_vectores_longitud(vector_t *vecs, int cant)`: muestra por pantalla los vectores con su longitud al cuadrado.
5. Ordene los vectores de mayor a menor en base a la longitud al cuadrado usando `qsort`. Imprimir antes y después del ordenamiento.
6. Implemente `resta(const vector_t *a, const vector_t *b)` que retorne el vector resultado de `a - b`.
7. Implemente `producto_vectorial(const vector_t *a, const vector_t *b)` que retorne el producto vectorial `a × b`.
8. Implemente la función genérica `guardar_vectores`:

```c
void guardar_vectores(const char *name, const vector_t *vectores, int cant,
                      vector_t *(*vec_op)(const vector_t *, const vector_t *));
```

El programa principal debe invocarla así:

```c
guardar_vectores("resta.txt", vectores, cant, resta);
guardar_vectores("producto_vectorial.txt", vectores, cant, producto_vectorial);
```
