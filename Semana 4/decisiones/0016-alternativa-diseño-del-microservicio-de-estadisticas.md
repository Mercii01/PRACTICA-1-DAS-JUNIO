# Alternativa-Diseño-Del-Microservicio-De-Estadisticas

* Status: accepted
* Deciders: Sergio, Miguel
* Date: 2024-03-01

## Context and Problem Statement

El sistema cuenta con un módulo de estadísticas que proporciona información valiosa sobre el estado de los pedidos y la situación en tiempo real de los camiones. Las estadísticas también proporcionan información de clientes.

## Decision Drivers

* RF-07: Control sobre el estado de los pedidos y la situación en tiempo real de los camiones.

## Considered Options

* 0016-1-Creación del microservicio Estadisticas.

## Decision Outcome

Chosen option: "0016-1-Creación del microservicio Estadisticas.", because Este microservicio realiza de manera correcta todas las funciones pedidas, incluso con más eficiencia.

### Positive Consequences

* El microservicio puede seguir ejecutando las funciones que no intervengan con el componente
* Es mas fácil de mantener
* Escalabilidad independiente
* Reducción del acoplamiento

### Negative Consequences

* Dependencia para una función en un componente externo.
* Dificultad en la depuración de problemas o errores.

## Pros and Cons of the Options

### 0016-1-Creación del microservicio Estadisticas.

Nombrar a Estadisticas como microservicio y se añadan las funciones y atributos necesarios para consultar informacion sobre el estado de los pedidos. Ademas, para solicitar la situacion en tiempo real de los camiones, se añadira un driver GPS que será "GPS Receiver Driver V1.10.03.22" de Windows.

* Good, because Permite realizar todas las funciones que se describen
* Good, because La eficiencia depende de nuestro sistema
* Good, because Sencillez del sistema
* Good, because El microservicio puede seguir ejecutando las funciones que no intervengan con el componente
* Bad, because La situacion en tiempo real de los camiones depende de un componente externo

## Links

* https://www.driverscape.com/download/gps-receiver
