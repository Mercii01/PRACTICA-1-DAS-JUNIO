# Diseño-Del-Microservicio-De-Clientes

* Status: proposed
* Deciders: Sergio
* Date: 2024-02-22

## Context and Problem Statement

Para abordar el manejo de informacion de los clientes, se decidió crear dos clases, donde una actuara como el objeto Cliente, mientras que la otra será el microservicio que gestionara las solicitudes de la informacion de clientes.

## Decision Drivers

* RF-04: Procedimiento de acceso a datos personales de clientes

## Considered Options

* 0005-1-Clase GestorClientes como microservicio.

## Decision Outcome

Chosen option: "0005-1-Clase GestorClientes como microservicio.", because Realiza los requisitos pedidos del sistema software de manera eficiente.

### Positive Consequences

* Mejor eficiencia del sistema
* Legibilidad mas facil para el mantenimiento
* Mejora la escalabilidad

### Negative Consequences

* Aumenta el coste de mantenimiento

## Pros and Cons of the Options

### 0005-1-Clase GestorClientes como microservicio.

La clase GestorClientes se conectará al componente que ejecuta los microservicios, mientras que la clase Cliente actuará como el Objeto en el que se guardará la información completa del cliente y se enviará como respuesta a la petición.

* Good, because Separar ambas clases permite mayor legibilidad
* Good, because Tener el microservicio conectado a la base de datos aumenta la eficiencia
* Bad, because Aumenta el coste de mantenimiento
