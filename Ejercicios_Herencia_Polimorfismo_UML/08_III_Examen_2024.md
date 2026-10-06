# III Examen 2024

Lista de Cliente abstracto, Fisico, Juridico y Contrato.

```text
Lista <>---- Nodo ----> Cliente <abstract> ----> Contrato
                         ^
            +------------+------------+
            |                         |
         Fisico                    Juridico

Lista:    Nodo* primero, Nodo* actual
Nodo:     Cliente* cli, Nodo* sig
Cliente:  nombre, cedula ;  string toString() = 0
Fisico:   genero (char), nacionalidad (string)
Juridico: representanteLegal (string)
Contrato: annioIncio (int), tipoServicio (int), estado (bool, activo o inactivo)
```

La lista es de la clase padre. Los objetos pueden ser físicos o jurídicos.

```cpp
bool lista::repetido(cliente* c) {
	actual = primero;
	while (actual != NULL) {
		if (actual->getCliente->getId() == c->getID()) { return true; }
		actual = actual->getSig();
	}
	return false;
}

void lista::insertarInicio(cliente* c) {
	primero = new nodo(c, primero);
}

string lista::toString() {
	actual = primero;
	stringstream s;
	fisico* fi;
	juridico* ju;
	while (actual != NULL) {
		if (fisico* aux = dynamic_cast<fisico*>(actual->getCliente())) {
			s << actual->getCliente()->toString();
			s << actual->getCliente()->getContrato()->toString();
			actual = actual->getSig();
		}
		return s.str();
	}
}
```

Implemente en Lista:

- Insertar: recibe un cliente físico o jurídico y lo inserta al inicio si no está repetido.
- toStringFisicos: solo clientes físicos, y el contrato si lo tiene. El toString de Cliente no llama al de Contrato. Nodo no tiene toString.
- inactivarContrato(): pone inactivos los contratos anteriores al año 2000.
- retornaListaEspecial(): crea y retorna una lista nueva solo con clientes físicos de contrato activo.

En el main:

- Cree una lista e inserte n físicos y n jurídicos. Pida los datos al usuario.
- Llame a retornaListaEspecial y muestre su contenido.
