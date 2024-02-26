# Diseño-Para-Calculo-De-Estadisticas

* Status: accepted
* Deciders: Sergio
* Date: 2024-02-23

## Context and Problem Statement

El calculo de estadisticas debera proporcionar información valiosa sobre el estado de los pedidos y la situación en tiempo real de los camiones, asi como información de clientes.

## Decision Drivers

* RF-07: Control sobre el estado de los pedidos y la situación en tiempo real de los camiones.

## Considered Options

* 0007-1-GestorEstadisticas con patron Mediator
* 0007-2-GestorEstadisticas como microservicio

## Decision Outcome

Chosen option: "0007-1-GestorEstadisticas con patron Mediator", because Realiza todas las funciones pedidas por el cliente de manera eficiente, ademas permite una mayor escalabilidad en nuestro sistema software.

### Positive Consequences

* Eficiencia en el sistema.
* Realiza las funciones necesarias para hacer consultas
* Realiza las consultas de forma segura

### Negative Consequences

* Si no esta bien optimizado puede generarse trafico.

## Pros and Cons of the Options

### 0007-1-GestorEstadisticas con patron Mediator

Nombrar a GestorEstadisticas como servicio permite crear otras 2 clases llamadas, "EstadisticasClientes" y "EstadisticasPedidos" que se encargaran de utilizar los datos de la base de datos para realizar operaciones de calculo de estadisticas y luego en la clase EstadisticaPedidos para conseguir la posición en tiempo real de los camiones, se utilizará un driver para GPS que monitorea a los camiones y devuelve una dirección, este driver seria "GPS Receiver Driver V1.10.03.22" de Windows.
Ademas, se utilizará un patron Mediator donde GestorEstadisticas funcionara como Mediator y los componentes seran las clases anteriormente llamadas.

* Good, because Permite realizar las funciones que el cliente desea.
* Good, because Es mas facil de modificar o mejorar en un futuro por la distribucion.
* Good, because La division de clases permite que no se dependa de una sola.
* Bad, because Gran dependencia en ambas bases de datos.

### 0007-2-GestorEstadisticas como microservicio

Nombrar a GestorEstadisticas como microservicio permite realizar las funciones que pide el cliente. Ademas se añadira un driver GPS para poder pedir la posicion en tiempo real al camion de reparto, este driver será "GPS Receiver Driver V1.10.03.22" de Windows.

* Good, because Conexion directa como microservicio
* Bad, because Las funciones seran mas limitadas
* Bad, because Gran dependencia en bases de datos
* Bad, because La seguridad puede fallar

## Links

* https://www.driverscape.com/download/gps-receiver
