# III Examen 2025

Lista enlazada polimórfica de personas.

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

1. En cout << listaPersonas->toString(), ¿cuántas veces corre Estudiante::toString()?

a) 3
b) 7
c) 4
d) Ninguna

2. ¿Cuántas veces corre Profesor::toString()?

a) 4
b) Ninguna
c) 7
d) 3

3. "Vinculación dinámica" significa que:

a) El método que se invoca es el de la clase declarada en el tipo del puntero.
b) El método depende del tipo real del objeto, más que del tipo declarado del puntero.
c) El término no se relaciona con polimorfismo.
d) Ninguna de las otras.

4. La Condición-1 correcta es:

a) Persona* pE = dynamic_cast<Estudiante*>(actual->getPersona())
b) Estudiante* pE = dynamic_cast<Estudiante*>(actual)
c) dynamic_cast<Estudiante*>(actual->getPersona())
d) Estudiante* pE = dynamic_cast<Estudiante*>(actual->getPersona())

5. La Condición-2 correcta es:

a) Profesor* pP = dynamic_cast Profesor*(actual->getPersona())
b) Profesor* pP = dynamic_cast<Profesor*> actual->getPersona()
c) Profesor* pP = dynamic_cast<Profesor*>(actual->getPersona())
d) Persona* pP = dynamic_cast<Profesor*>(actual->getPersona())

6. Si se escribiera actual->getPersona()->incrementarSalario();

a) Se ejecuta solo para los profesores de la lista.
b) No se ejecuta para los estudiantes.
c) Error porque incrementarSalario no está declarado virtual.
d) Error porque incrementarSalario no es accesible con un puntero a Persona.

7. Es falso que:

a) Estudiante::incrementarPromedio() solo puede invocarse con una referencia a Estudiante.
b) Profesor::incrementarSalario() solo puede invocarse con una referencia a Profesor.
c) Profesor::toString() no puede accederse mediante lo que devuelve Persona* Nodo::getPersona().
d) Estudiante::toString() puede accederse mediante lo que devuelve Persona* Nodo::getPersona().

8. La lista:

a) Puede contener referencias a Estudiante mediante un Estudiante*.
b) No puede contener profesores con punteros a Persona.
c) Solo puede contener estudiantes.
d) Solo puede contener profesores.
