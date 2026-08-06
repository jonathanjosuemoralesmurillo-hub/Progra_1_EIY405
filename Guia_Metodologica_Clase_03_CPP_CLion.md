# Guía metodológica para la Clase 03  
## Colaboración entre clases y paso de objetos en C++

| Campo | Descripción |
|---|---|
| Curso | EIF-201 Programación I |
| Lenguaje | C++ |
| IDE | CLion |
| Población | Estudiantes universitarios de primer ingreso |
| Tema | Colaboración entre clases y paso de objetos |
| Organización sugerida | 3 lecciones |
| Enfoque | Explicación visual, análisis de código y práctica guiada |

---

## 1. Recomendación metodológica general

Para estudiantes universitarios de primer ingreso, se recomienda desarrollar la clase mediante una metodología activa, con explicaciones breves, demostraciones en CLion y ejercicios progresivos.

La clase puede organizarse mediante el siguiente ciclo:

> **Explicación breve → predicción → programación en vivo → práctica estudiantil → revisión**

No se recomienda desarrollar toda la sesión mediante una exposición magistral extensa. Es preferible dividir la clase en bloques cortos en los que el estudiantado pueda observar, participar, programar y explicar.

La intención principal no debe ser solamente memorizar la sintaxis de C++, sino comprender que los programas orientados a objetos están formados por clases que poseen responsabilidades específicas y colaboran entre sí.

---

## 2. Estructura sugerida para cada lección

| Momento | Tiempo aproximado | Actividad |
|---|---:|---|
| Activación | 5–10 minutos | Pregunta, problema o código con un error |
| Microexplicación | 10–15 minutos | Explicación visual de un concepto |
| Programación en vivo | 15–20 minutos | Construcción progresiva en CLion |
| Reto guiado | 20–30 minutos | Modificación o ampliación del código |
| Comparación | 10 minutos | Revisión de algunas soluciones |
| Cierre | 5 minutos | Pregunta de salida o explicación breve |

---

# Lección 1. Varias clases que colaboran

## Propósito

Que el estudiantado comprenda que un sistema puede dividirse en varias clases y que cada clase debe conservar una responsabilidad clara.

## Contenidos

- Responsabilidad de una clase.
- Colaboración entre objetos.
- Composición.
- Asociación simple.
- Archivos `.h` y `.cpp`.
- Uso básico de `#include`.
- Introducción a la declaración adelantada.

---

## Actividad de inicio

Presente inicialmente una clase con demasiadas responsabilidades:

```cpp
class Estudiante {
private:
    std::string nombre;
    std::string provincia;
    std::string canton;
    std::string distrito;
    std::string correo;
    std::string nombreCurso;
    std::string nombreProfesor;
};
```

Realice la siguiente pregunta:

> ¿Toda esta información debería pertenecer directamente a la clase `Estudiante`?

Permita que el estudiantado converse durante dos o tres minutos en parejas.

Después, solicite que propongan clases separadas, por ejemplo:

```text
Estudiante
Direccion
Curso
Profesor
```

---

## Explicación visual

Antes de mostrar la implementación, dibuje las clases y sus relaciones en la pizarra:

```text
Estudiante contiene una Direccion
Estudiante se matricula en un Curso
Curso es impartido por un Profesor
```

Formule preguntas como:

- ¿Cuál es la responsabilidad de `Estudiante`?
- ¿Cuál es la responsabilidad de `Direccion`?
- ¿Qué objeto contiene a otro?
- ¿Cuál clase necesita conocer a cuál?
- ¿Qué atributos pertenecen realmente a cada clase?

---

## Programación en vivo en CLion

Construya el ejemplo progresivamente utilizando los siguientes archivos:

```text
Clase_03_Colaboracion/
├── CMakeLists.txt
├── main.cpp
├── Direccion.h
├── Direccion.cpp
├── Estudiante.h
└── Estudiante.cpp
```

Orden sugerido de construcción:

1. Crear el proyecto en CLion.
2. Crear la clase `Direccion`.
3. Agregar atributos y constructor.
4. Crear la clase `Estudiante`.
5. Incorporar un objeto `Direccion` dentro de `Estudiante`.
6. Crear los objetos en `main.cpp`.
7. Compilar y ejecutar.

Mientras programa, explique las decisiones:

> “La clase `Direccion` representa un concepto independiente.”

> “La clase `Estudiante` contiene una dirección porque esta forma parte de sus datos.”

> “Cada clase debe encargarse únicamente de su propia información.”

---

## Ejemplo base

```cpp
#include <string>

class Direccion {
private:
    std::string calle;

public:
    explicit Direccion(const std::string& calleInicial)
        : calle(calleInicial) {
    }

    std::string getCalle() const {
        return calle;
    }
};
```

```cpp
#include <string>
#include "Direccion.h"

class Estudiante {
private:
    std::string nombre;
    Direccion casa;

public:
    Estudiante(const std::string& nombreInicial,
               const Direccion& direccionInicial)
        : nombre(nombreInicial),
          casa(direccionInicial) {
    }
};
```

---

## Reto guiado

Solicite que cada pareja cambie el dominio del ejemplo, manteniendo la misma estructura.

Opciones:

```text
Sensor + Ubicacion
Producto + Categoria
Paciente + Direccion
Libro + Editorial
Vehiculo + Motor
```

### Producto esperado

Cada equipo debe presentar:

1. Nombre de las dos clases.
2. Responsabilidad de cada clase.
3. Relación entre las clases.
4. Código que compile.
5. Dos objetos creados desde `main()`.

---

## Cierre de la lección 1

Solicite que respondan:

```text
¿Qué significa que dos clases colaboren?
¿Qué responsabilidad tiene cada clase de su ejemplo?
¿Qué error podría producir una clase con demasiadas responsabilidades?
```

---

# Lección 2. Paso de objetos: valor, referencia y puntero

## Propósito

Que el estudiantado comprenda que la forma de recibir un objeto como parámetro determina si el objeto se copia, puede modificarse, se consulta sin copiarse o puede representar ausencia.

## Contenidos

- Paso por valor.
- Paso por referencia.
- Paso por referencia constante.
- Paso mediante puntero.
- Copia y modificación.
- Uso básico de `const`.
- Uso básico de `nullptr`.

---

## Estrategia metodológica

Utilice la secuencia:

> **Predecir → ejecutar → observar → explicar**

No presente las cuatro formas de pasar objetos únicamente como una lista teórica. Permita que el estudiantado observe las diferencias mediante pequeños experimentos.

---

## Experimento 1. Paso por valor

Presente el siguiente código:

```cpp
void cambiarNombre(Estudiante estudiante) {
    estudiante.setNombre("Ana");
}
```

Antes de ejecutar, pregunte:

> Después de llamar la función, ¿cambiará el nombre del objeto original?

Opciones de respuesta:

```text
A. Sí cambia.
B. No cambia.
C. Produce un error.
```

Ejecute el programa y analice el resultado.

Explique que el parámetro recibido por valor es una copia.

---

## Experimento 2. Paso por referencia

Modifique solamente la firma:

```cpp
void cambiarNombre(Estudiante& estudiante) {
    estudiante.setNombre("Ana");
}
```

Pregunte nuevamente:

> ¿Ahora cambiará el objeto original?

Ejecute el programa y compare ambos resultados.

---

## Experimento 3. Referencia constante

Presente:

```cpp
void mostrarEstudiante(const Estudiante& estudiante) {
    std::cout << estudiante.getNombre() << std::endl;
}
```

Explique que esta forma:

- No crea una copia innecesaria.
- Permite consultar el objeto.
- No permite modificarlo dentro de la función.

---

## Experimento 4. Puntero

Presente:

```cpp
void mostrarEstudiante(const Estudiante* estudiante) {
    if (estudiante != nullptr) {
        std::cout << estudiante->getNombre() << std::endl;
    }
}
```

Explique que el puntero puede representar la ausencia de un objeto mediante `nullptr`.

Para estudiantes principiantes, no es necesario profundizar todavía en memoria dinámica. En esta clase, el objetivo es comprender la intención del parámetro.

---

## Analogía didáctica

Puede utilizar la siguiente analogía:

| Forma | Analogía |
|---|---|
| Por valor | Entregar una fotocopia |
| Por referencia | Prestar el documento original |
| Por referencia constante | Permitir leer el original sin modificarlo |
| Por puntero | Entregar una dirección donde podría existir un objeto |

Después de presentar la analogía, vuelva siempre al código para evitar que la explicación quede únicamente en un ejemplo cotidiano.

---

## Comparación de firmas

```cpp
void porValor(Estudiante estudiante);
void porReferencia(Estudiante& estudiante);
void porConstRef(const Estudiante& estudiante);
void porPuntero(Estudiante* estudiante);
```

| Firma | ¿Crea copia? | ¿Puede modificar? | ¿Puede ser `nullptr`? |
|---|---:|---:|---:|
| `Estudiante estudiante` | Sí | Modifica la copia | No |
| `Estudiante& estudiante` | No | Sí | No |
| `const Estudiante& estudiante` | No | No | No |
| `Estudiante* estudiante` | No | Sí | Sí |

---

## Actividad de clasificación

Solicite que seleccionen la forma adecuada para cada situación:

| Situación | Forma recomendada |
|---|---|
| Consultar un estudiante sin copiarlo | `const Estudiante&` |
| Modificar los datos del estudiante | `Estudiante&` |
| Trabajar con una copia independiente | `Estudiante` |
| Permitir que el objeto no exista | `Estudiante*` |

---

## Reto guiado

Cada pareja debe crear tres funciones:

```cpp
void mostrarSensor(const Sensor& sensor);
void actualizarSensor(Sensor& sensor);
void procesarCopia(Sensor sensor);
```

Luego debe explicar:

- Cuál función crea una copia.
- Cuál función modifica el objeto original.
- Cuál función solamente consulta.
- Por qué se utilizó `const`.

---

## Cierre de la lección 2

Solicite que respondan:

```text
¿Cuál es la diferencia entre valor y referencia?
¿Cuándo utilizaría const&?
¿Cuándo podría ser útil un puntero?
```

---

# Lección 3. Diseño de un minisistema

## Propósito

Integrar la colaboración entre clases y el paso de objetos mediante el diseño de un pequeño sistema.

## Modelo sugerido

```text
Cliente
Pedido
LineaPedido
Producto
```

## Situación inicial

Presente el siguiente caso:

> Un cliente realiza un pedido. El pedido contiene varias líneas. Cada línea representa un producto, una cantidad y un precio unitario.

Antes de escribir código, solicite que identifiquen:

```text
Sustantivos → posibles clases
Datos → posibles atributos
Acciones → posibles métodos
```

---

## Análisis del problema

| Elemento | Representación posible |
|---|---|
| Cliente | Clase |
| Pedido | Clase |
| Producto | Clase |
| Línea de pedido | Clase |
| Cantidad | Atributo |
| Precio | Atributo |
| Agregar producto | Método |
| Calcular subtotal | Método |
| Mostrar pedido | Método |

---

## Pregunta central

> ¿Quién necesita conocer a quién?

Dibuje las relaciones:

```text
Cliente realiza Pedido
Pedido contiene LineaPedido
LineaPedido referencia Producto
```

Explique que no todas las clases necesitan conocer directamente a todas las demás.

---

## Construcción incremental en CLion

### Etapa 1. Crear las clases

```cpp
class Cliente;
class Producto;
class LineaPedido;
class Pedido;
```

### Etapa 2. Crear objetos simples

Desde `main.cpp`, crear:

- Un cliente.
- Dos productos.
- Un pedido.

### Etapa 3. Incorporar colaboración

Agregar métodos como:

```cpp
void mostrarProducto(const Producto& producto);
void mostrarCliente(const Cliente& cliente);
```

### Etapa 4. Probar el sistema

Verificar que:

- Cada clase tenga una responsabilidad clara.
- Los atributos sean privados.
- Los objetos se pasen mediante `const&` cuando solamente se consultan.
- El programa compile y ejecute correctamente.

---

## Actividad guiada alternativa

Modelar un sistema de biblioteca utilizando:

```text
Biblioteca
Libro
Usuario
Prestamo
```

Requisitos:

1. Identificar las responsabilidades.
2. Dibujar quién conoce a quién.
3. Implementar al menos tres clases.
4. Crear objetos desde `main()`.
5. Registrar un préstamo.
6. Utilizar `const&` donde corresponda.
7. No exponer directamente los atributos privados.

---

# 3. Trabajo en parejas

Se recomienda utilizar programación por parejas.

## Roles

### Conductor

- Escribe el código.
- Ejecuta el programa.
- Realiza los cambios acordados.

### Navegante

- Revisa el código.
- Formula preguntas.
- Detecta errores.
- Explica lo que se está haciendo.

Cambie los roles cada 10 o 15 minutos.

Esto ayuda a evitar que una sola persona realice todo el ejercicio.

---

# 4. Uso pedagógico de errores

Los errores de compilación deben convertirse en oportunidades de aprendizaje.

Prepare algunos errores pequeños de forma intencional:

- Falta de `;`.
- Nombre incorrecto del constructor.
- Archivo `.h` no incluido.
- Método declarado, pero no implementado.
- Uso de `.` en lugar de `->`.
- Intento de modificar un objeto `const`.
- Dependencia circular entre encabezados.
- Parámetro pasado por valor cuando se esperaba modificar el original.

## Procedimiento de depuración

Solicite que sigan estos pasos:

1. Leer el primer error.
2. Identificar el archivo.
3. Identificar la línea.
4. Explicar el mensaje con sus palabras.
5. Formular una hipótesis.
6. Cambiar una sola cosa.
7. Compilar nuevamente.

---

# 5. Preguntas que puede utilizar durante la clase

En lugar de entregar inmediatamente la solución, formule preguntas como:

- ¿Qué objeto se está copiando?
- ¿La función necesita modificar el objeto?
- ¿Podría utilizarse `const&`?
- ¿Esta clase realmente necesita conocer a la otra?
- ¿Cuál es la responsabilidad de esta clase?
- ¿El error se encuentra en el `.h`, en el `.cpp` o en `main.cpp`?
- ¿Qué sucedería si eliminamos `const`?
- ¿El objeto original cambia?
- ¿Qué relación existe entre estas clases?

---

# 6. Evaluación formativa

No evalúe únicamente si el programa compila.

| Dimensión | Evidencia |
|---|---|
| Comprensión | Explica por qué utiliza valor, referencia o puntero |
| Diseño | Cada clase posee una responsabilidad clara |
| Encapsulamiento | Los atributos se mantienen privados |
| Colaboración | Las clases se comunican correctamente |
| Implementación | El programa compila y ejecuta |
| Explicación | El estudiante puede justificar sus decisiones |

---

## Ticket de salida

Al finalizar la clase, solicite responder:

```text
1. Explique una diferencia entre composición y asociación.
2. ¿Cuándo utilizaría const&?
3. ¿Cuál es la diferencia entre copiar y referenciar un objeto?
4. Mencione un error que encontró durante la clase.
5. Explique cómo resolvió ese error.
```

---

# 7. Organización sugerida del proyecto en CLion

```text
Semana_03/
├── Leccion_01_Colaboracion/
│   ├── CMakeLists.txt
│   ├── main.cpp
│   ├── Direccion.h
│   ├── Direccion.cpp
│   ├── Estudiante.h
│   └── Estudiante.cpp
├── Leccion_02_Paso_Objetos/
│   ├── CMakeLists.txt
│   ├── main.cpp
│   ├── Estudiante.h
│   └── Estudiante.cpp
└── Leccion_03_Mini_Sistema/
    ├── CMakeLists.txt
    ├── main.cpp
    ├── Cliente.h
    ├── Cliente.cpp
    ├── Producto.h
    ├── Producto.cpp
    ├── LineaPedido.h
    ├── LineaPedido.cpp
    ├── Pedido.h
    └── Pedido.cpp
```

---

# 8. Progresión de aprendizaje

```text
Lección 1:
Identificar responsabilidades y relaciones entre clases.

Lección 2:
Decidir cómo pasar los objetos entre funciones.

Lección 3:
Integrar las decisiones en un pequeño sistema.
```

---

# 9. Recomendaciones para estudiantes de primer ingreso

- Utilizar ejemplos cercanos a su realidad.
- Evitar programas demasiado extensos.
- Mostrar resultados visibles rápidamente.
- Alternar explicación y práctica.
- Permitir que predigan el resultado antes de ejecutar.
- Utilizar errores reales para enseñar depuración.
- Trabajar en parejas.
- Pedir que expliquen sus decisiones.
- No introducir demasiados conceptos nuevos al mismo tiempo.
- Mantener un proyecto organizado en CLion.
- Dar instrucciones cortas y verificables.
- Cerrar cada actividad con una conclusión concreta.

---

# 10. Idea central de la clase

> Los sistemas orientados a objetos están formados por objetos que colaboran. Cada clase debe poseer una responsabilidad clara y la firma de una función debe comunicar si un objeto se copia, se modifica, se consulta o puede estar ausente.
