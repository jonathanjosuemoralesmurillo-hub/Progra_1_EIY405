# II Parcial 2021 (reposición)

Lista polimórfica de clientes físicos y jurídicos, cada uno con una cuenta.

```text
Lista <>---- n ---- Cliente <abstract>
                      |
          +-----------+-----------+
          |                       |
   ClienteFisico            ClienteJuridico

Cliente ----> Cuenta
```

Atributos:

- Cliente: nombre, id, tipo (físico, jurídico)
- ClienteFisico: estado civil, año de nacimiento
- ClienteJuridico: nombre del representante, tipo de actividad
- Cuenta: moneda, saldo, estado (activo o inactivo)

La lista guarda la clase padre. Los objetos pueden ser físicos o jurídicos.

Menú cíclico:

- Insertar clientes físicos y jurídicos con sus cuentas, y mostrarlos.
- Mostrar el detalle de todos los físicos o de todos los jurídicos, a elección del usuario, incluida la cuenta.
- desactivaCuenta(): pone inactivas las cuentas con saldo negativo o cero.
- retornaLista(): crea y retorna una lista nueva solo con clientes de cuentas inactivas. La lista original no cambia. Muéstrela en el main.
- eliminaNoActivas(): elimina de la lista original los clientes con cuentas inactivas e imprime cuántos eliminó.
