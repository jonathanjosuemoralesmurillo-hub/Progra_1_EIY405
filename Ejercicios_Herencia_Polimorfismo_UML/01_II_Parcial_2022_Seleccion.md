# II Parcial 2022

Selección sobre composición, agregación, asociación, dependencia, herencia y clases abstractas.

1. Para el sistema de un banco se desea establecer la relación entre Cliente y Cuenta Bancaria. La relación entre clases es de:

a) Composición
b) Dependencia
c) Asociación
d) Agregación

2. Cuando se elimina un objeto de una clase derivada, sucede que:

a) El destructor del padre y del hijo se ejecutan automáticamente al mismo tiempo.
b) Solo el destructor de la clase derivada se ejecuta.
c) Se ejecuta primero el destructor de la clase base y luego el destructor de la clase derivada.
d) Se ejecuta primero el destructor de la clase derivada y luego el destructor de la clase base.

3. En cuanto a herencia, cuando se instancia un objeto de una clase derivada:

a) Siempre se ejecuta primero el constructor del padre y luego el constructor del hijo.
b) Solo se ejecuta el constructor de la clase derivada.
c) Se ejecuta primero el constructor de la clase derivada y luego el del padre.
d) Se ejecuta solo el constructor de la clase hijo.

4. En herencia es cierto que:

a) Las clases derivadas únicamente heredan los atributos declarados como protected en el padre.
b) Las clases derivadas únicamente heredan los atributos declarados como public en el padre.
c) Las clases derivadas únicamente heredan los atributos declarados como private en el padre.
d) Las clases derivadas heredan todos los atributos del padre, pero no tienen acceso directo a aquellos que fueron declarados como privados.

5. En la relación de composición es totalmente cierto y requerido que:

a) Cuando se crea el todo deben crearse TODAS las partes.
b) Las partes no pueden formar parte de otros todos.
c) Cuando se elimina una parte se debe eliminar el todo.
d) La multiplicidad puede ser de uno a muchos en cualquiera de ambos extremos.

6. En una relación de composición es estrictamente requerido que:

a) La multiplicidad del lado del todo siempre debe ser 1.
b) Se recibe la referencia del (los) componente(s).
c) Los componentes o partes pueden ser compartidos por dos o más compuestos o todos.
d) El compuesto no es el responsable de liberar el espacio de memoria de los componentes.

7. En la relación de agregación es totalmente cierto y requerido que:

a) Cuando se crea el todo deben crearse TODAS las partes.
b) Las partes no pueden formar parte de otros todos.
c) Cuando se elimina una parte se debe eliminar el todo.
d) La multiplicidad puede ser de uno a muchos en cualquiera de ambos extremos.

8. Para que una clase base sea abstracta es estrictamente necesario que:

a) Todos sus métodos sean virtuales puros.
b) Posea al menos un método virtual puro.
c) No posea atributos y todos sus métodos son virtuales puros.
d) Solo posea .h y no .cpp.

9. Es cierto que una clase abstracta:

a) No es instanciable.
b) Sí es instanciable.
c) Exige la instanciación de todos sus hijos.
d) Exige que sus hijos no se puedan instanciar.

10. La clase Juego se relaciona con la clase Dado, esto con el fin de obtener un puntaje aleatorio dado de la clase Dado. ¿Qué nombre recibe la relación entre Juego y Dado?

a) Herencia
b) Composición
c) Agregación
d) Dependencia

11. La clase Lista se relaciona con la clase Nodo. Cada objeto Nodo solo podrá formar parte de una única Lista. ¿Qué nombre recibe la relación?

a) Asociación
b) Composición
c) Agregación
d) Dependencia

12. La clase Lista se relaciona con la clase Nodo. Cada objeto Nodo podrá formar parte de otras Listas. ¿Qué nombre recibe la relación?

a) Asociación
b) Composición
c) Agregación
d) Dependencia

13. En una universidad existe la clase Estudiante y EstudianteBecado. EstudianteBecado cuenta con los mismos métodos y atributos que un Estudiante, y además con tipo de beca y porcentaje de exoneración. ¿Qué nombre recibe la relación?

a) Herencia
b) Composición
c) Agregación
d) Dependencia

14. De la siguiente manera se declara un método virtual puro:

a) virtual string toString() = 0;
b) virtual string toString();
c) String toString() = 0;
d) virtual string toString() {}

15. Suponiendo que Estudiante hereda de Persona y según el siguiente código:

```cpp
estudiante::estudiante(string nom, float p) : persona(nom)
	this->promedio = p;
```

a) En este código nunca se llama al constructor del padre.
b) Se llama en forma explícita al constructor con parámetros del padre.
c) Se llama en forma implícita al constructor con parámetros del padre.
d) Se llama en forma implícita al constructor sin parámetros del padre.
