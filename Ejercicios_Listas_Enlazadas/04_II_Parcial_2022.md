# II Parcial 2022

Lista enlazada de trabajadores.

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

Suponga implementadas Persona y Puesto.
El estado vale "activo" o "cesado".

De la clase Lista implemente:

- insertarTrabajador: recibe un trabajador y lo inserta al final. No se permiten IDs repetidos. Si ya está con estado "cesado", se cambia a "activo" y se actualizan sus datos.
- ceseEmpleado(): recibe un id y cambia el estado a cesado.
- retornaLista(): crea y retorna una lista nueva solo con los trabajadores cesados.
- sueldoPlanilla(): suma los sueldos brutos de los trabajadores activos.
- eliminaCesados(): elimina los cesados y retorna cuántos eliminó.
