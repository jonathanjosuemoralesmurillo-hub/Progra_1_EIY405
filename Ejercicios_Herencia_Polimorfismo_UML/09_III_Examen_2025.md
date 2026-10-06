# III Examen 2025

Selección de polimorfismo, dynamic_cast y lista de Persona.
Los formularios A y B usan el mismo código y las mismas preguntas.

## Parte 1. Polimorfismo

```cpp
#include <iostream>
#include <cmath>
#include <sstream>
using namespace std;

class poligonoRegular {
protected:
	string nombre;
	float lado;
	float apotema;
public:
	poligonoRegular(float, float);
	virtual ~poligonoRegular();
	string getNombre();
	float getLado();
	virtual float perimetro() = 0;
	float area();
	virtual string toString() = 0;
};

poligonoRegular::poligonoRegular(float lado, float apotema) {
	this->lado = lado;
	this->apotema = apotema;
}
poligonoRegular::~poligonoRegular() {}
float poligonoRegular::area() {
	return (perimetro() * apotema) / 2;
}

class cuadrado : public poligonoRegular {
private:
	int numeroLados;
public:
	cuadrado(float);
	float perimetro();
	float diagonal();
	string toString();
};

cuadrado::cuadrado(float lado) : poligonoRegular(lado, lado / 2) {
	nombre = "Cuadrado";
	numeroLados = 4;
}
float cuadrado::perimetro() { return lado * numeroLados; }
float cuadrado::diagonal() { return sqrt(pow(lado, 2) + pow(lado, 2)); }
string cuadrado::toString() {
	stringstream s;
	s << nombre << endl << numeroLados << endl << lado << endl << apotema << endl;
	return s.str();
}

int main(int argc, char *argv[]) {
	cuadrado* c = new cuadrado(5);
	cout << c->toString();
	cout << c->perimetro() << endl;
	cout << c->area() << endl << endl;

	poligonoRegular* pr = new cuadrado(5);
	cout << pr->toString() << endl;
	cout << "Perímetro\t:\t" << pr->perimetro() << endl;
	cout << "Area\t\t:\t" << pr->area() << endl;

	cuadrado* pc = dynamic_cast<cuadrado*>(pr);
	cout << "Diagonal\t:\t" << pc->diagonal() << endl;

	delete c;
	delete pr;
	return 0;
}
```

1. Con cuadrado* c = new cuadrado(5);

a) Se asigna cero a los atributos numéricos de poligonoRegular.
b) Los atributos numéricos de poligonoRegular quedan sin valor.
c) Se asigna 5 a lado y 2.5 a apotema.
d) Se asigna 5 a lado y 2 a apotema.

2. En poligonoRegular:

a) Se debe implementar perimetro().
b) perimetro() devuelve cero para objetos de la clase.
c) La declaración de perimetro() impide sobreescribirlo en cuadrado.
d) La declaración de perimetro() impide instanciar objetos de la clase.

3. poligonoRegular* pr = new cuadrado(5);

a) Crea un objeto de poligonoRegular.
b) Crea un objeto de cuadrado referido como poligonoRegular.
c) Tiene error porque poligonoRegular es abstracta.
d) Hace que el tipo de pr sea puntero a cuadrado.

4. float poligonoRegular::area():

a) Solo se puede ejecutar para objetos de poligonoRegular.
b) Es obligatorio redefinirlo en cuadrado.
c) Se hereda para objetos de cuadrado.
d) No puede invocar perimetro().

5. El método string toString(); obligatoriamente:

a) Se tiene que implementar en cuadrado.
b) Se debe declarar virtual en cuadrado.
c) Se tiene que implementar en poligonoRegular.
d) Solo se puede invocar mediante un cuadrado*.

6. float diagonal();

a) Puede invocarse mediante una referencia a poligonoRegular.
b) Debe ser virtual puro en la base.
c) Tiene que implementarse también en la base.
d) Solo puede invocarse por medio de una referencia a cuadrado.

7. Con cout << pr->area() << endl; (el que imprime "Area"):

a) Se usa perimetro() de poligonoRegular.
b) Se usa perimetro() de cuadrado.
c) Se ejecuta area() de cuadrado.
d) Se ejecuta el método virtual area().

8. Con cout << c->area() << endl;

a) Se ejecuta area() de cuadrado.
b) Se usa perimetro() de poligonoRegular.
c) Se ejecuta area() de poligonoRegular.
d) Se utiliza el cero que devuelve virtual float perimetro() = 0.

9. cuadrado* pc = dynamic_cast<cuadrado*>(pr);

a) Devuelve un cuadrado* aunque pr no apunte a un cuadrado.
b) Asigna dinámicamente la referencia de pc a pr.
c) Convierte de cuadrado* a poligonoRegular*.
d) Convierte de poligonoRegular* a cuadrado*.

10. Con cout << pc->diagonal() << endl;

a) Se invoca diagonal() con un poligonoRegular*.
b) Se invoca diagonal() con un cuadrado*.
c) pc es un cuadrado* actuando como poligonoRegular*.
d) pc es un poligonoRegular* actuando como cuadrado*.

11. Si existiera hexagono, análoga a cuadrado:

poligonoRegular* pr = new cuadrado(5);
hexagono* ph = dynamic_cast<hexagono*>(pr);

a) La conversión se hace y ph apunta a un hexágono.
b) ph apunta a un poligonoRegular.
c) Generan un error de conversión de tipo.
d) Ninguna de las otras opciones.

12. Si virtual string toString() = 0; se cambia por virtual string toString(); y se implementa devolviendo "toString() de poligonoRegular", entonces cout << c->toString() << endl;

a) Usa el toString() de poligonoRegular.
b) Usa el toString() de cuadrado.
c) Ninguna de las otras.
d) Muestra algo distinto que cout << pr->toString() << endl;

13. Cuando se definen métodos virtuales puros en el padre:

a) Se pueden instanciar el padre y las hijas.
b) Se pueden crear punteros a las hijas apuntando a objetos del padre.
c) Las hijas deben implementar todos los métodos del padre.
d) Las hijas deben implementar los métodos declarados virtuales puros en el padre.

14. Si perimetro() deja de ser virtual puro, se declara float perimetro(); y retorna 0, ¿qué muestra cout << c->area() << endl?

a) El área del cuadrado creado con new cuadrado(5).
b) El valor de (20 * apotema) / 2.
c) Cero.
d) Un valor distinto a los anteriores.

## Parte 2. Lista polimórfica

Persona es abstracta porque toString() es virtual puro. Profesor tiene incrementarSalario(). Estudiante tiene incrementarPromedio().

```cpp
class Persona {
private:
	/* atributos de la clase */
public:
	virtual string toSring() = 0;
};

class Nodo {
private:
	Persona* persona;
	Nodo* siguiente;
public:
	Nodo(Persona*, Nodo*);
	~Nodo();
	Persona* getPersona();
	Nodo* getSiguiente();
	void setSiguiente(Nodo*);
};

string Estudiante::toString() { return "toString() de Estudiante\n"; }
string Profesor::toString() { return "toString() de Profesor\n"; }

class Lista {
protected:
	Nodo* primero;
	Nodo* actual;
public:
	Lista();
	void agregar(Persona*);
	string toString();
	void actualizarPersonas();
};

string Lista::toString() {
	stringstream s;
	actual = primero;
	while (actual != nullptr) {
		s << actual->getPersona()->toString();
		actual = actual->getSiguiente();
	}
	return s.str();
}

void Lista::actualizarPersonas() {
	actual = primero;
	while (actual != nullptr) {
		if ( /* Condición-1 */ )
			pE->incrementarPromedio();
		if ( /* Condición-2 */ )
			pP->incrementaSalario();
		actual = actual->getSiguiente();
	}
}

void main() {
	Lista* listaPersonas = new Lista;
	listaPersonas->agregar(new Estudiante("Luis", "10101", 1990, 70));
	listaPersonas->agregar(new Profesor("Jorge", "10102", 1990, 68000));
	listaPersonas->agregar(new Estudiante("Carlos", "10156", 2000, 89));
	listaPersonas->agregar(new Profesor("Miguel", "10103", 1998, 69000));
	listaPersonas->agregar(new Estudiante("Maria", "10133", 2001, 56));
	listaPersonas->agregar(new Profesor("Rosa", "10104", 1999, 97000));
	listaPersonas->agregar(new Estudiante("Jose", "10123", 1980, 56));
	cout << listaPersonas->toString() << endl;
	listaPersonas->actualizarPersonas();
	delete listaPersonas;
}
```

15. En cout << listaPersonas->toString(), ¿cuántas veces corre Estudiante::toString()?

a) 3
b) 7
c) 4
d) Ninguna

16. ¿Cuántas veces corre Profesor::toString()?

a) 4
b) Ninguna
c) 7
d) 3

17. "Vinculación dinámica" significa que:

a) El método que se invoca es el de la clase declarada en el tipo del puntero.
b) El método depende del tipo real del objeto, más que del tipo declarado del puntero.
c) El término no se relaciona con polimorfismo.
d) Ninguna de las otras.

18. La Condición-1 correcta es:

a) Persona* pE = dynamic_cast<Estudiante*>(actual->getPersona())
b) Estudiante* pE = dynamic_cast<Estudiante*>(actual)
c) dynamic_cast<Estudiante*>(actual->getPersona())
d) Estudiante* pE = dynamic_cast<Estudiante*>(actual->getPersona())

19. La Condición-2 correcta es:

a) Profesor* pP = dynamic_cast Profesor*(actual->getPersona())
b) Profesor* pP = dynamic_cast<Profesor*> actual->getPersona()
c) Profesor* pP = dynamic_cast<Profesor*>(actual->getPersona())
d) Persona* pP = dynamic_cast<Profesor*>(actual->getPersona())

20. Si se escribiera actual->getPersona()->incrementarSalario();

a) Se ejecuta solo para los profesores de la lista.
b) No se ejecuta para los estudiantes.
c) Error porque incrementarSalario no está declarado virtual.
d) Error porque incrementarSalario no es accesible con un puntero a Persona.

21. Es falso que:

a) Estudiante::incrementarPromedio() solo puede invocarse con una referencia a Estudiante.
b) Profesor::incrementarSalario() solo puede invocarse con una referencia a Profesor.
c) Profesor::toString() no puede accederse mediante lo que devuelve Persona* Nodo::getPersona().
d) Estudiante::toString() puede accederse mediante lo que devuelve Persona* Nodo::getPersona().

22. La lista:

a) Puede contener referencias a Estudiante mediante un Estudiante*.
b) No puede contener profesores con punteros a Persona.
c) Solo puede contener estudiantes.
d) Solo puede contener profesores.
