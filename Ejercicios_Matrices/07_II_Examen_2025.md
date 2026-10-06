# II Examen 2025

Matriz de los mejores corredores.

```text
Corredor
  - string nombre
  - string id
  - float tiempo
```

Una colección administra una matriz de 6 x 5 corredores.

Cada fila es un año, de 2020 a 2025. La fila 0 es 2020, la fila 1 es 2021, y así hasta la fila 5, que es 2025.

En cada fila van los 5 mejores corredores de ese año, ordenados por tiempo de menor a mayor. La columna 0 es el primer lugar (mejor tiempo) y la columna 4 es el quinto lugar.

```text
        1er lugar   2do lugar   3er lugar   4to lugar   5to lugar
2020
2021
2022
2023
2024
2025
```

Implemente una colección que administre la matriz dinámica de punteros a Corredor:

- Atributos.
- Constructor sin parámetros.
- vecesCampion: recibe el id de un corredor y retorna cuántas veces estuvo en primer lugar entre los 6 años.
- revisionTiempo: recibe un año (por ejemplo 2021) y retorna verdadero si los corredores de ese año están ordenados de menor a mayor tiempo. Si no, retorna falso.
- mejorTiempo: retorna el nombre del corredor con el menor tiempo de todos los años.
