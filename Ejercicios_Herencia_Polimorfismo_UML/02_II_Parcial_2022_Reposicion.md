# II Parcial 2022 (reposición)

Nombrar y dibujar relaciones, y la herencia Persona, Trabajador y Puesto.

## Relaciones

Nombre la relación y dibújela.

1. La clase Lista se relaciona con la clase Nodo. Cada objeto Nodo solo podrá formar parte de una única Lista.

2. La clase Nodo se relaciona con la clase Estudiante. Cada estudiante puede estar vinculado por más de un nodo al mismo tiempo, porque puede formar parte de varias listas diferentes.

3. La clase Juego se relaciona con la clase Dado, con el fin de obtener un puntaje aleatorio.

4. Existe Estudiante y EstudianteBecado. EstudianteBecado cuenta con los mismos métodos y atributos que un Estudiante, y además con tipo de beca y porcentaje de exoneración.

5. Cada Estudiante se relaciona con un HistorialAcadémico muy específico, el cual incluye todas sus notas.

6. La clase Control debe hacer uso de la clase Calendario, con el fin de hacer cálculos sobre fechas.

7. Explique las características del especificador de acceso protected.

8. Suponga una clase Contenedora tipo matriz que administra una matriz dinámica (M x M) de personas dinámicas. Existe composición entre la Contenedora y las personas. Implemente el constructor y el destructor.

## Herencia

Una empresa desea una lista de todos sus trabajadores. Cada trabajador se relaciona con un puesto.

```text
Lista <>---- n ---- Trabajador
Persona
  - nombre : string
  - id : string
  - provincia : string
        ^
        | herencia
Trabajador
  - vacaciones : int
  - sueldoBruto : int
  - estado : string
        ----> Puesto
                - nombre : string
                - codigo : string
                - salarioBase : float
```

Suponga implementadas las clases Persona y Puesto.
El atributo estado vale "activo" o "cesado".

Implemente la clase Trabajador:

- Declaración (.h). Establezca la herencia. De los métodos, solo el prototipo del constructor.
- Constructor con 6 parámetros, invocando de forma explícita al constructor del padre.

De la clase Lista:

- insertarTrabajador: recibe un trabajador y lo inserta al final. No se permiten IDs repetidos. Si ya está con estado "cesado", se cambia a "activo" y se actualizan sus datos.
- ceseEmpleado(): recibe un id y cambia el estado a cesado.
- sueldoPlanilla(): suma los sueldos brutos de los trabajadores activos.
- eliminaCesados(): elimina los cesados y retorna cuántos eliminó.
- retornaLista(): crea y retorna una lista nueva solo con los cesados.
