# II Examen 2025

Lista enlazada de clientes.

La lista guarda clientes dinámicos. Cada cliente tiene un tipo (A, B o C) y se asocia con una dirección.

Suponga ya implementadas las clases del diagrama, con sus atributos y métodos básicos. Implemente solo estos métodos de Lista:

- buscaCliente(): recibe una cédula y retorna true si el cliente está en la lista, o false si no.
- agregarFinal(): recibe un cliente dinámico y lo agrega al final si no existe otro con la misma cédula. Use buscaCliente().
- buscaClientesProvincia(): recibe el nombre de una provincia y retorna una lista nueva con los clientes de esa provincia. La lista actual no se modifica.
- actualizaDescuento(): recibe un decimal nuevoPorceDesc y un char tipo (A, B o C). Actualiza el porcentaje de descuento de los clientes de ese tipo que estén al día (alDia en true).
- fucionaLista(): recibe una lista y agrega al final de la lista actual los clientes que todavía no están, sin dejar cédulas repetidas. Use métodos ya implementados.
- ComparaLista(): recibe una lista y retorna true si es igual a la lista actual. Son iguales si tienen los mismos clientes en las mismas posiciones.
