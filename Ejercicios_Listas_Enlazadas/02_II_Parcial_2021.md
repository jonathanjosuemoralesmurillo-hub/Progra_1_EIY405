# II Parcial 2021

Comparar dos listas enlazadas de productos.

La clase Nodo y la clase Lista ya pueden usarse. La lista guarda objetos de tipo Producto. Producto tiene dos atributos: nombreP (string) y precioP (double).

Escriba en Lista el método:

bool comparaListas(ContenedorL*)

Recibe otra lista y compara this con la lista recibida. Las listas son iguales si todo producto de una existe al menos una vez en la otra. El orden no importa y puede haber repetidos.

Si un producto se repite con el mismo nombre pero con otro precio, y ese par nombre-precio no está en la otra lista, el método retorna false.

- Escriba Producto, Nodo y ContenedorL (.h y .cpp).
- Escriba bool esIgualA(Producto&) en Producto.
- Escriba bool comparaListasIguales(ContenedorL*) en ContenedorL.
- Escriba un main que pruebe esos métodos.
