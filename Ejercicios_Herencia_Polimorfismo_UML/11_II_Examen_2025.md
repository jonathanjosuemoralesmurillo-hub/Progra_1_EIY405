# II Examen 2025

Lista de clientes. Cada cliente tiene tipo A, B o C y se asocia con una dirección. Los clientes son objetos dinámicos.

Suponga ya implementadas las clases del diagrama. Implemente solo estos métodos de Lista:

- buscaCliente(): recibe una cédula y retorna true si el cliente está en la lista.
- agregarFinal(): recibe un cliente dinámico y lo agrega al final si no hay otra cédula igual. Use buscaCliente().
- buscaClientesProvincia(): recibe una provincia y retorna una lista nueva con esos clientes. La lista actual no cambia.
- actualizaDescuento(): recibe nuevoPorceDesc y un char tipo (A, B o C). Actualiza el descuento de los clientes de ese tipo que estén al día (alDia en true).
- fucionaLista(): recibe una lista y agrega al final los clientes que no estén ya, sin cédulas repetidas.
- ComparaLista(): retorna true si las dos listas tienen los mismos clientes en las mismas posiciones.
