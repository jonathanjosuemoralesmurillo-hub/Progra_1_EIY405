# II Parcial 2024

Matriz de reservaciones de un teatro.

Un teatro representa las reservaciones en una matriz cuadrada de tamaño Tam x Tam. Cada espacio está asociado o no con una reservación. Cada reservación se asocia con un cliente.

```text
ColeccionMatriz
  - Reservacion*** m
  - int tam

Reservacion
  - int precio
  - int numFila
  - int numColumna
  - Cliente* elCliente
  - float calcularMontoDescuento()

Cliente
  - string nombre
  - string id
```

- Cada reservación corresponde a un asiento. El asiento queda definido por numFila y numColumna.
- calcularMontoDescuento() retorna el descuento que se rebaja del precio. Si no hay descuento, retorna cero.

La matriz es dinámica y contiene punteros a objetos dinámicos de Reservacion. Al crear la colección, cada posición se inicializa en NULL.

Implemente solo estos métodos de ColeccionMatriz:

- destructor: libera la memoria que se requiera.
- reservaIndividual: recibe fila, columna y un puntero a cliente. Si el asiento está disponible, crea la reservación y le asigna sus atributos. Si no está disponible, no crea nada. El precio de toda reservación es 1000 colones.
- disponiblesFila: recibe una fila f y un entero n. Verifica si en esa fila hay n espacios consecutivos disponibles. Retorna la columna a partir de la cual existen, o -1 si no.
- reservaMultiple: recibe un cliente y un entero n. Crea las n reservaciones en la primera fila que tenga n espacios consecutivos. Si ninguna fila los tiene, no reserva. Reutilice reservaIndividual y disponiblesFila.
- ingresoTaquilla: calcula el ingreso por venta de asientos. A cada reservación se le resta su monto de descuento.
- reservacionesCliente: recibe el id de un cliente y retorna cuántas reservaciones hizo.
- corrimientoFila: recibe una fila f y agrupa a la derecha todas las reservaciones de esa fila, sin dejar asientos libres en medio. No altere el orden; solo córralas hacia la derecha.
