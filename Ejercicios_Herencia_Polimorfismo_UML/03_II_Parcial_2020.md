# II Parcial 2020

Herencia de motores, composición de pacientes y dependencia Moneda / TipoCambio.

## 1. Herencia de motores

Herencia de motores, con clase abstracta.

- Programe la herencia con clase abstracta.
- En el main cree tres objetos: MElectrico, MCGasolina y MCDiesel. Insértelos en un vector polimórfico de tres campos.
- Imprima el toString() de cada objeto del vector.
- Cambie del objeto MElectrico el amperaje a 1.5, del MCGasolina el octanaje a 90 y del MCDiesel la potencia a 180. Muestre de nuevo los valores.

## 2. Composición y asociación

Composición de pacientes contagiados con Covid-19. Cada paciente está asociado a una fecha.

Implemente una contenedora tipo lista. Atributos del paciente: nombre, cédula, teléfono y número de comorbilidades. A cada paciente se le asocia una fecha de ingreso en la UCI, si es del caso.

En el main:

1. Ingresar un paciente al inicio de la lista y mostrarlo.
2. Eliminar los pacientes con n comorbilidades (n se recibe por parámetro) y mostrar la lista.
3. Ordenar los pacientes por fecha, de menor a mayor, y mostrar la lista.

## 3. Herencia y dependencia

Moneda es la clase base de Dolar y Colon.

La aplicación convierte dólares a colones y colones a dólares. Si la persona tiene dólares, se crea un Dolar con esa cantidad. Si tiene colones, se crea un Colon.

La conversión depende de la clase de servicio TipoCambio:

double obtenerValorDeCambio(string, double)

Recibe el tipo de moneda y la cantidad, y devuelve el valor en la otra moneda. El dólar está fijo a 601 colones.

Un objeto Dolar o Colon usa un TipoCambio* que llega por parámetro.

string tipo = typeid(*ptr).name();

Eso deja "class Dolar" o "class Colon".

- Escriba .h y .cpp de Moneda, Dolar, Colon y TipoCambio.
- Declare y defina double obtenerValorDeCambio(string, double).
- Declare y defina double conversion(TipoCambio* TC).

En el main:

- Crear un Dolar con una cantidad leída por teclado.
- Crear un TipoCambio.
- Llamar a conversion() e imprimir los colones.
- Repetir el proceso de colones a dólares.
