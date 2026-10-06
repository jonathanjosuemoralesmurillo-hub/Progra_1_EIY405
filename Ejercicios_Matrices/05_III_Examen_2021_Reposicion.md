# III Examen 2021 (reposición)

Matriz dinámica de citas.

Una clínica tiene n médicos. Cada médico maneja su agenda semanal de citas en una matriz dinámica. Solo se asignan citas a pacientes ya registrados en una lista general.

La agenda se muestra así:

```text
Agenda semanal
Medico: Pablo Blanco

Hora   Lunes            Martes           Miercoles          Jueves            Viernes
8:00   Cita Juan Perez  Disponible       Disponible         Cita Anita Rojas  Disponible
9:00   Disponible       Disponible       Disponible         Disponible        Disponible
10:00  Disponible       Disponible       Disponible         Disponible        Disponible
11:00  Disponible       Disponible       Disponible         Disponible        Disponible
12:00  Disponible       Cita Maria Lopez Cita Ruben Gonzalez Disponible       Disponible
13:00  Disponible       Disponible       Disponible         Disponible        Disponible
14:00  Disponible       Disponible       Disponible         Disponible        Disponible
15:00  Disponible       Disponible       Disponible         Disponible        Disponible
16:00  Disponible       Disponible       Disponible         Disponible        Disponible
```

- Agende citas según el médico (búsqueda por cédula) y según el espacio disponible en su matriz.
- Muestre la agenda semanal de un médico buscado por cédula. El nombre del paciente se obtiene por la relación entre la cita y el paciente.
- Al mostrar las citas de un paciente, incluya nombre, id, nombre del doctor, especialidad, fecha y hora.
