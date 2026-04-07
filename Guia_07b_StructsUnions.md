# Guía de Trabajos Prácticos - Unidad 7b
## Materia: Programación 1
### Estructuras, Uniones y Typedef en C

> Esta guía cubre el uso de estructuras (`struct`), uniones (`union`) y alias de tipo (`typedef`) en C/C++, fundamentales en programación de sistemas embebidos e interfaces de bajo nivel.
>
> **Temas cubiertos:**
> 1. Declaración y uso de `struct`
> 2. Estructuras anidadas y arrays de estructuras
> 3. `typedef` para alias de tipos
> 4. `union` y uso de memoria compartida
> 5. Punteros a estructuras y paso por referencia
> 6. Aplicaciones en sistemas embebidos

---

## Preguntas orientadoras

1. ¿Qué es una estructura (`struct`) en C? ¿En qué se diferencia de un array?

2. ¿De qué depende el tamaño en bytes de una estructura? ¿Qué es el *padding* o alineación?

3. ¿Cuáles son las ventajas y desventajas del manejo de estructuras respecto a variables independientes?

4. ¿Qué es `typedef`? ¿Para qué se usa? Dé un ejemplo con una estructura.

5. ¿Qué es una unión (`union`)? ¿En qué se diferencia de una estructura en cuanto al almacenamiento?

6. ¿Cuándo conviene usar una unión en lugar de una estructura? Dé un ejemplo concreto de aplicación en sistemas embebidos.

7. ¿Puede una estructura contener otra estructura como miembro? ¿Y un puntero a sí misma?

8. ¿Cómo se accede a los miembros de una estructura a través de un puntero? ¿Qué operador se usa?

---

## Completar espacios en blanco

Complete los siguientes enunciados con el término correcto:

- Una ________ es una colección de variables relacionadas bajo un mismo nombre, donde cada variable ocupa su propio espacio de almacenamiento.
- Una ________ es una colección de variables bajo el mismo nombre donde todas las variables **comparten** el mismo espacio de almacenamiento.
- Las variables declaradas dentro de una estructura se conocen como sus _________.
- La palabra reservada _________ introduce una declaración de estructura.
- La palabra reservada _________ se utiliza para crear un sinónimo (alias) de un tipo de datos previamente definido.
- La palabra reservada _________ se utiliza para introducir una definición de unión.
- El operador _________ accede a los miembros de una estructura mediante un puntero.
- El tamaño de una unión es igual al tamaño de su miembro _________.

---

## Verdadero o falso

Indique si las siguientes afirmaciones son verdaderas o falsas. Justifique las falsas:

1. Una estructura puede contener como miembro a otra estructura del mismo tipo (no un puntero a sí misma, sino la estructura completa).
2. Los miembros de una estructura comparten el mismo espacio de almacenamiento.
3. `typedef struct Punto { int x; int y; } Punto;` define un alias `Punto` para la estructura.
4. Una unión puede almacenar simultáneamente valores de distintos tipos sin que se pisen entre sí.
5. En C, el tamaño de `struct { char a; int b; }` puede ser mayor que `sizeof(char) + sizeof(int)` por cuestiones de alineación.
6. El operador `->` equivale a `(*ptr).miembro`.

---

## Acceso a estructuras anidadas

Dadas las siguientes definiciones:

```c
typedef struct {
    int dia;
    int mes;
    int anio;
} Fecha;

typedef struct {
    char nombre[50];
    char apellido[50];
    Fecha nacimiento;
    float sueldo;
} Empleado;

typedef struct {
    Empleado empleados[100];
    int cantidad;
} Empresa;
```

Escriba las expresiones C necesarias para:

a) Acceder al día de nacimiento del tercer empleado de una variable `Empresa empresa`.

b) Asignar el sueldo 85000.0 al empleado en la posición `i`.

c) Dado un puntero `Empleado* pe`, acceder a su mes de nacimiento.

d) Copiar el nombre del primer empleado al quinto empleado.

e) Determinar cuántos bytes ocupa `sizeof(Empleado)`. ¿Puede ser diferente entre plataformas? ¿Por qué?

---

## Ejercicios

### Ejercicio 1 — Fracciones con estructuras

Defina una estructura `Fraccion` con numerador y denominador enteros. Implemente las siguientes funciones:

```c
Fraccion crear(int num, int den);
Fraccion sumar(Fraccion a, Fraccion b);
Fraccion multiplicar(Fraccion a, Fraccion b);
Fraccion dividir(Fraccion a, Fraccion b);
Fraccion inverso(Fraccion a);
void simplificar(Fraccion* f);   // divide por el MCD
void imprimir(Fraccion f);       // formato: "3/4"
```

Pruebe las operaciones con un `main` que realice al menos 5 operaciones distintas e imprima los resultados simplificados.

**Extensión:** Agregue validación para denominador cero (usar `assert` o retornar un valor centinela).

---

### Ejercicio 2 — Números complejos

Modifique el ejercicio anterior (o cree una nueva estructura `Complejo`) para trabajar con números complejos en forma rectangular (parte real + parte imaginaria). Implemente:

```c
Complejo crear(double real, double imag);
Complejo sumar(Complejo a, Complejo b);
Complejo multiplicar(Complejo a, Complejo b);
double modulo(Complejo c);
double fase(Complejo c);         // en radianes
Complejo desdePolares(double mod, double fase);
void imprimir(Complejo c);       // formato: "3.0 + 2.0i"
```

Pruebe convirtiendo de rectangular a polar y viceversa, verificando que la conversión ida y vuelta preserve el número original (con tolerancia de `1e-9`).

---

### Ejercicio 3 — Registro de alumnos

Defina una estructura `Alumno` con los siguientes campos:

```c
typedef struct {
    char nombre[50];
    char apellido[50];
    int edad;
    float nota_parcial1;
    float nota_parcial2;
    float nota_recuperatorio;  // -1 si no rindió
} Alumno;
```

Implemente funciones para:

a) Calcular el **promedio final** del alumno. Si rindió recuperatorio, reemplaza la peor nota de los parciales.

b) Determinar si el alumno **aprobó** (promedio ≥ 6.0) y si **promocionó** (promedio ≥ 7.0 sin recuperatorio).

c) Cargar por teclado un array de `N` alumnos (N ingresado por el usuario).

d) Imprimir un listado con nombre, apellido, promedio y condición (Reprobado / Aprobado / Promocionado).

e) Calcular e imprimir el promedio general del curso y la cantidad de aprobados.

---

### Ejercicio 4 — Cumpleaños de amigos (array fijo)

Defina una estructura `Persona` con nombre (string) y fecha de cumpleaños (día y mes, usar estructura anidada `Fecha`). Implemente un programa que:

a) Cargue datos de **20 amigos** por teclado.

b) Busque y muestre todos los amigos que cumplen en un **día y mes** dados por el usuario.

c) Muestre cuántos amigos cumplen en cada mes del año.

d) Encuentre el mes con más cumpleaños.

---

### Ejercicio 5 — Cumpleaños de amigos (cantidad dinámica)

Modifique el ejercicio anterior para que la cantidad de amigos sea **dinámica**: el usuario ingresa cuántos son al inicio, y el array se reserva con `malloc`/`calloc`. Al finalizar, libere la memoria con `free`.

**Extensión:** Permita agregar amigos durante la ejecución (usando `realloc`).

---

### Ejercicio 6 — Estadísticas de tornillos

Una fábrica produce tornillos y quiere estadísticas de producción. Cada tornillo tiene `longitud` (mm, float) y `diámetro` (mm, float). Implemente:

a) Una estructura `Tornillo` y un programa que cargue datos de **N** tornillos.

b) Calcule e imprima:
   - Media de longitudes y de diámetros.
   - Desvío estándar de longitudes.
   - Tornillo con mayor longitud y con mayor diámetro.
   - Porcentaje de tornillos que cumplen una especificación dada (longitud en rango `[lmin, lmax]` Y diámetro en rango `[dmin, dmax]`).

c) Permita al usuario ingresar las especificaciones y muestre cuántos tornillos las cumplen.

---

### Ejercicio 7 — Base de clientes de concesionaria

Una empresa de automóviles necesita una base de datos de clientes. Cada cliente tiene: nombre, apellido, teléfono (string) y e-mail (string). Implemente un programa con menú que permita:

```
1. Agregar cliente.
2. Buscar cliente por apellido.
3. Listar todos los clientes.
4. Eliminar cliente por teléfono.
0. Salir.
```

Use un **array estático** de hasta 100 clientes con un contador de cantidad actual.

---

### Ejercicio 8 — Base de clientes sin duplicados

Modifique el ejercicio anterior para **evitar duplicados por número de teléfono**: al agregar un cliente, verifique si ya existe un registro con el mismo teléfono. Si existe, muestre un mensaje de error y no lo agregue.

**Extensión:** Permita modificar los datos de un cliente existente dado su teléfono.

---

### Ejercicio 9 — Sistema de pacientes con menú

Implemente un sistema de gestión de pacientes de un consultorio médico. Cada paciente tiene:

```c
typedef struct {
    int  id;
    char nombre[50];
    char apellido[50];
    char obra_social[50];  // "Particular" si no tiene
    Fecha fecha_nacimiento;
    char telefono[20];
} Paciente;
```

El programa debe manejar un **array dinámico** (usando `malloc`/`realloc`) y proveer un menú con:

```
1. Alta de paciente (asignar ID automático incremental).
2. Consulta por ID.
3. Consulta por apellido (puede haber varios resultados).
4. Listar pacientes por obra social.
5. Listar todos los pacientes (ordenados por apellido).
6. Baja de paciente por ID.
0. Salir.
```

**Requisito de embebidos:** Imprima el tamaño en bytes de la estructura `Paciente` al iniciar el programa. Explique en comentarios qué campos podrían reducirse para optimizar memoria en un sistema con recursos limitados.

---

## Aplicación en Sistemas Embebidos

### Ejercicio 10 — Registros de hardware con `union`

En sistemas embebidos es común acceder a registros de hardware tanto como un valor entero completo (para escritura rápida) como campo a campo (para configuración individual de bits). La técnica usa una `union` de una estructura de bits con un entero:

```c
typedef union {
    struct {
        unsigned int modo     : 2;  // bits 0-1: modo de operación (0=entrada, 1=salida, 2=AF, 3=analog)
        unsigned int velocidad: 2;  // bits 2-3: velocidad (0=baja, 1=media, 2=alta, 3=muy alta)
        unsigned int pull     : 2;  // bits 4-5: pull-up/down (0=ninguno, 1=up, 2=down)
        unsigned int reservado: 2;  // bits 6-7: reservado
    } bits;
    unsigned char valor;            // acceso al byte completo
} RegistroGPIO;
```

a) Declare un arreglo de 8 registros `RegistroGPIO gpio[8]` representando 8 pines de un microcontrolador.

b) Configure el pin 3 como salida de alta velocidad sin pull-up/down **accediendo campo a campo** (`gpio[3].bits.modo = ...`).

c) Realice la misma configuración escribiendo **el byte completo** (`gpio[3].valor = ...`). Verifique que el resultado es el mismo.

d) Imprima el valor hexadecimal de cada registro (`printf("GPIO[%d] = 0x%02X\n", ...)`).

e) Explique en comentarios por qué esta técnica es útil en embebidos y qué ventaja tiene sobre usar máscaras de bits manualmente.

---

### Ejercicio 11 — Protocolo de comunicación serie

En comunicaciones embebidas (UART, SPI, I2C) los datos se empaquetan en tramas. Defina estructuras para representar una trama de comunicación simple:

```c
typedef struct {
    unsigned char inicio;       // 0xAA = inicio de trama
    unsigned char tipo;         // 0x01=datos, 0x02=ack, 0x03=error
    unsigned char longitud;     // longitud del payload en bytes
    unsigned char payload[64];  // datos
    unsigned char checksum;     // XOR de todos los bytes anteriores
} Trama;
```

Implemente:

a) `void calcularChecksum(Trama* t)` — calcula el checksum XOR de inicio, tipo, longitud y payload.

b) `int verificarTrama(const Trama* t)` — retorna 1 si el checksum es válido, 0 si no.

c) `void imprimirTrama(const Trama* t)` — imprime la trama en formato hexadecimal.

d) `void serializarTrama(const Trama* t, unsigned char* buffer)` — copia la trama a un buffer de bytes (simulando envío por UART).

e) `void deserializarTrama(Trama* t, const unsigned char* buffer)` — reconstruye la trama desde un buffer de bytes.

Pruebe enviando y recibiendo una trama y verificando que el checksum es correcto.

---

## De Parciales Anteriores

### [Parcial PE] — Teoría: Structs, unions y typedef

1. ¿Cuál es la diferencia entre `struct` y `union`? ¿En qué situaciones conviene usar cada uno?

2. ¿Qué es el *memory alignment* o alineación de datos? ¿Por qué `sizeof(struct { char a; int b; })` puede devolver 8 en lugar de 5?

3. ¿Para qué se usa `#pragma pack(1)` o `__attribute__((packed))`? ¿Qué ventajas y desventajas tiene?

4. Explique la técnica de `union` de struct de bits con entero para acceder a registros de hardware. ¿Por qué es útil en sistemas embebidos?

5. ¿Puede una función devolver una `struct` por valor en C? ¿Es eficiente? ¿Cuándo es preferible pasar por puntero?

---

### [Parcial PE] — Práctica: Sistema de sensores

Implemente un sistema de monitoreo de sensores para un sistema embebido. Cada sensor tiene:

```c
typedef union {
    float    valor_float;
    int      valor_int;
    unsigned char bytes[4];    // acceso byte a byte (para transmisión serie)
} DatoSensor;

typedef struct {
    unsigned char id;
    char          nombre[20];
    unsigned char tipo;        // 0=temperatura, 1=presión, 2=humedad, 3=nivel
    DatoSensor    dato;
    Fecha         ultima_lectura;
    unsigned char activo;      // 0=inactivo, 1=activo
} Sensor;
```

El sistema debe:

a) Cargar datos de hasta 16 sensores (límite típico de un sistema embebido pequeño).

b) Mostrar el valor de cada sensor activo con su nombre y tipo.

c) Serializar todos los sensores activos a un array de bytes (simulando transmisión por UART) usando el campo `bytes` de la unión.

d) Calcular el valor promedio de todos los sensores de tipo `temperatura` (tipo 0) interpretando el valor como `float`.

e) Imprimir un mapa de memoria: offset en bytes de cada campo de `Sensor` usando `offsetof(Sensor, campo)`.