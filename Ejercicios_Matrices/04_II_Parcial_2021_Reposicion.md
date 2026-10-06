# II Parcial 2021 (reposición)

Matriz dinámica de libros más vendidos.

Una editorial almacena en una matriz dinámica de 8 x 10 los libros más vendidos (best seller) de cada tienda. Las filas son tiendas y las columnas son años, de 2010 a 2019. Una celda puede estar en NULL.

```text
           2010  2011  2012  2013  2014  2015  2016  2017  2018  2019
Tienda 0
Tienda 1
...
Tienda 7
```

```cpp
class Libro {
private:
	string nombre;
	string autor;
	int unidadesVendidas;
	int costos;
	int ingresos;
};
```

Implemente la clase Coleccion, que administra esa matriz. Pruebe los métodos en el main con datos fijos y muestre los resultados. No hace falta un menú.

- Colección que administre una matriz dinámica de libros.
- Ingrese varios libros y muestre la matriz.
- sumarUnidadesVendidas: recibe un año y devuelve el total de unidades vendidas ese año. Convierta el año al número de columna.
- ganancias: recibe el nombre de un autor y retorna las ganancias de ese autor en todos los años y todas las tiendas. La ganancia es ingresos menos costos.
- PerdidasPorAutor: recibe el nombre de un autor y un año. Devuelve true si en algún momento ese autor representó pérdidas, y false si no. Convierta el año al número de columna.
- vecesBestSeller: recibe el nombre de un libro y retorna cuántas veces ha sido best seller. Best seller es el que más ventas tuvo en un año.
- totalGananciasSuc: recibe un número de sucursal y retorna el total de ingresos de esa sucursal en los años registrados.
