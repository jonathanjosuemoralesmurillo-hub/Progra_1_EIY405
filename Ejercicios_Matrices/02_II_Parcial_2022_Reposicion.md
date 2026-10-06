# II Parcial 2022 (reposición)

Matriz de declaraciones de renta.

El Ministerio de Hacienda pide a las empresas la declaración anual de renta. Cada declaración incluye ingresos, egresos y el monto a pagar por impuesto de renta. La clase Declaracion ya existe: solo debe utilizarla.

Las declaraciones se almacenan en una matriz de tamaño n x m. Cada fila es una empresa y cada columna un año, desde 2010. La matriz contiene punteros a declaraciones, o NULL si en ese año la empresa no declaró.

Ejemplo de contenido (ptr es un puntero a Declaracion):

```text
           2010  2011  2012  2013  2014  2015  2016  2017  2018
Empresa 0  NULL  NULL  ptr   ptr   NULL  ptr   NULL  ptr   NULL
Empresa 1  NULL  NULL  NULL  NULL  ptr   ptr   ptr   ptr   ptr
Empresa 2  NULL  NULL  ptr   ptr   ptr   ptr   NULL  NULL  NULL
Empresa 3  NULL  ptr   ptr   ptr   ptr   ptr   ptr   ptr   ptr
Empresa 4  NULL  ptr   ptr   ptr   ptr   ptr   NULL  NULL  NULL
Empresa 5  NULL  NULL  NULL  NULL  NULL  NULL  NULL  NULL  NULL
Empresa 6  ptr   ptr   ptr   ptr   ptr   ptr   ptr   NULL  NULL
```

Toda la memoria es dinámica.

Implemente la clase Coleccion:

- Atributos, incluidos los necesarios para el funcionamiento de la colección.
- Constructor: recibe el número de filas y de columnas e inicializa todos los atributos.
- totalMontoImpEmpresa: recibe un número de empresa y retorna el total que esa empresa ha pagado en impuestos durante los años de la matriz.
- sinDeclarar: recibe un número de columna y retorna cuántas empresas no declararon ese año.
- Destructor: libera la memoria que sea necesaria.
