# II Parcial 2021

Matriz de habitaciones de un hotel.

El hotel Ocean Drive Madrid tiene 4 pisos y 6 habitaciones por piso. Implemente un contenedor matricial, clase ContenedorM, de 4 filas y 6 columnas. Cada casilla guarda un objeto dinámico de tipo Habitacion.

Atributos de Habitacion:

- numHabitac : int
- numCamasAdult : int
- numCamasNinos : int
- estado : char
- desc : bool

El estado puede ser `O` (ocupado), `D` (desocupado) o `M` (mantenimiento).

Al alquilar una habitación se clasifica a las personas. Si desc es true, las camas de niños tienen 50% de descuento, sin pasar el cupo de niños. Si desc es false, no hay descuento. Ocupada significa alquilada.

En toda habitación hay 2 camas de adulto y 3 camas de niño. Cada cama de niño cuesta 15000 por día y cada cama de adulto 20000 por día. La habitación se cobra completa aunque llegue una sola persona. Hay como máximo 24 habitaciones.

Escriba en ContenedorM el método double obtenerRecaudoDiarioTotal(). Según el estado de cada habitación, retorna el dinero recaudado en un día. Desocupada o en mantenimiento no genera ganancia.

- Escriba Habitacion, ContenedorM y sus .h y .cpp.
- Permita establecer el estado de una habitación: desocupada, mantenimiento u ocupada.
- Imprima la matriz con el número de habitación y el estado D, M u O.
- Calcule e imprima la recaudación total del hotel por día.
