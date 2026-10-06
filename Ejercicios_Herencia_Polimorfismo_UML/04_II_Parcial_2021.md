# II Parcial 2021

Dependencia de la ruta de buses y herencia abstracta de personas universitarias.

## 1. Relación de dependencia

La empresa de buses "Viajes Costa Rica".

Implemente AViaje con atributos, todos string: nombrEmpresa, ceduJuridica, teleCelular.

AViaje depende de la clase de servicio Ruta, que solo tiene métodos. Con el código del viaje se obtiene la información de esa ruta.

AViaje tiene void infoDelViaje(int). Según el código, genera toda la información de la ruta.

Escriba un main que use la relación con al menos dos códigos.

- Tres métodos de Ruta.
- infoDelViaje(int).
- Un main que ejemplifique la relación.

## 2. Herencia

Jerarquía de personas universitarias: estudiantes, profesores y administrativos.

Persona es abstracta. Tiene al menos:

virtual string toString() = 0;

Las líneas punteadas significan realización: se hereda de una clase abstracta. Persona y Trabajador son abstractas porque su toString() es virtual puro.

- Escriba las clases de la herencia (.h y .cpp).
- En el main cree tres objetos dinámicos: Estudiante, ProfUniversitario y AdmUniversitario. Los atributos, y las edades de los hijos en el caso de los trabajadores, se llenan desde el teclado.
- Imprima toda la información con toString().
