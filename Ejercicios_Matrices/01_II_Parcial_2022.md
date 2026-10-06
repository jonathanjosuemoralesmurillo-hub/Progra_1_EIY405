# II Parcial 2022

Selección y desarrollo sobre matrices dinámicas.

## Selección

1. Si en una clase Contenedora deseamos declarar una matriz dinámica de punteros a objetos tipo Autor, el atributo de la clase que define esta matriz es:

a) Autor*** m
b) Autor** m
c) Autor* m[tam][tam]
d) Autor** m[tam][tam]

2. Si en una clase Contenedora deseamos declarar una matriz dinámica de objetos automáticos tipo Autor, el atributo de la clase que define esta matriz es:

a) Autor*** m
b) Autor** m
c) Autor* m[tam][tam]
d) Autor** m[tam][tam]

3. Según el siguiente código, ¿cuántas personas han sido instanciadas?

```cpp
Persona*** m;
m = new Persona**[3];

for (int i = 0; i < fil; i++) {
	m[i] = new Persona*[3];
}
```

a) 3
b) 6
c) 0
d) 9

4. Según la siguiente línea de código, ¿cuántas personas han sido instanciadas?

```cpp
Persona m[5][6];
```

a) 5
b) 6
c) 0
d) 30

5. Suponiendo una matriz dinámica (4 x 3) de objetos automáticos tipo auto, ¿cuál es la instrucción correcta para la liberación de memoria?

a) No hay memoria que liberar, pues el contenido es automático.

b)

```cpp
for (int i = 0; i < 4; i++) {
	delete[] m[i];
}
delete[] m;
```

c)

```cpp
for (int i = 0; i < 3; i++) {
	delete[] m[i];
}
delete[] m;
```

d) `delete[] m;`

## Desarrollo

1. Suponga una clase Contenedora tipo matriz que administra una matriz dinámica (M x M) de personas dinámicas. Existe composición entre la Contenedora y las personas. Implemente el constructor y el destructor.

2. Suponga una clase Contenedora tipo matriz que administra una matriz dinámica de personas dinámicas. Implemente un método que reciba una persona dinámica y una posición f, c, inserte la persona en esa posición y realice el corrimiento.
