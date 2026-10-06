# II Parcial 2024

Clase derivada de poligonoRegular.

Un polígono regular tiene lados y ángulos interiores iguales. El perímetro es la longitud del lado por el número de lados.

```cpp
class poligonoRegular {
private:
	string nombre;
	float lado;
	float apotema;
public:
	poligonoRegular(string, float, float);
	virtual ~poligonoRegular();
	string getNombre();
	float getLado();
	float getApotema();
	void setNombre(string);
	void setLado(float);
	void setApotema(float);
	virtual float area();
	virtual float perimetro() = 0;
	virtual string toString() = 0;
};

poligonoRegular::poligonoRegular(string nombre, float lado, float apotema) {
	this->nombre = nombre;
	this->lado = lado;
	this->apotema = apotema;
}
poligonoRegular::~poligonoRegular() {}
string poligonoRegular::getNombre() { return nombre; }
float poligonoRegular::getLado() { return lado; }
float poligonoRegular::getApotema() { return lado; }
void poligonoRegular::setNombre(string nombre) { this->nombre = nombre; }
void poligonoRegular::setLado(float lado) { this->lado = lado; }
void poligonoRegular::setApotema(float apotema) { this->apotema = apotema; }
float poligonoRegular::area() { return (perimetro() * apotema) / 2; }
```

Defina una clase derivada para un polígono regular concreto (triángulo equilátero, cuadrado, pentágono regular, hexágono regular, octágono regular, etc.):

- Declare la herencia.
- Constructor sin parámetros y constructor con parámetros. En el de parámetros, invoque de forma explícita al constructor de la base.
- Defina los métodos que la herencia obliga a implementar.
- En main cree un objeto dinámico de la derivada y muestre atributos propios y heredados, perímetro y área.
