# I Examen 2021

Asociación entre paciente y vacuna.

Una regional de salud registra pacientes. De cada paciente: nombre, id, peso, género, año de nacimiento y estatura. Capacidad máxima: 5000.

Al registrarse, el paciente queda sin vacunar. Al vacunarse, queda vinculado con su vacuna.

De cada vacuna: casa comercial, número de lote, número de serie, fecha de vencimiento y fecha de aplicación. Cada vacuna es única.

Menú:

- Registrar pacientes. No se permiten repetidos.
- Visualizar todos: nombre, id y si está vacunado.
- Buscar por cédula y mostrar el detalle, incluida la vacuna si ya fue vacunado.
- Vacunar un paciente. Hay que buscarlo antes. No se vacuna a quien no esté en el sistema ni a quien ya esté vacunado.
- Mostrar vacunados por género: primero mujeres y luego hombres. De cada uno, solo id y nombre.
- Porcentaje de vacunados y de no vacunados.
- Vacunados de una casa comercial indicada por el usuario. Solo nombre y cédula.
- Liberar la memoria.
