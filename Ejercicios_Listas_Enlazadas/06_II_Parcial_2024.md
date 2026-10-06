# II Parcial 2024

Lista simplemente enlazada de estudiantes.

```text
Lista <>---- n ---- Estudiante

Estudiante
  - string nombre
  - string id
  - string annioIngreso
  - bool activo
  - bool promedio
```

Suponga implementadas Estudiante y Nodo, con sus métodos básicos.

Implemente solo estos métodos de Lista:

- buscarEstudiante(): recibe el id de un estudiante y retorna true si está en la lista, o false si no.
- insertaFinal(): recibe un puntero a un estudiante y lo agrega al final si no estaba ya. Use buscarEstudiante().
- copiaLista(): recibe una Lista de estudiantes y agrega a la lista actual los estudiantes de la lista recibida. Use insertaFinal().
- eliminaNoActivos(): elimina de la lista actual todos los nodos con estudiantes no activos.
