# Seleccion-De-Middleware-Para-Ejecutar-Microservicios

* Status: proposed
* Deciders: Sergio
* Date: 2024-03-01

## Context and Problem Statement

Es necesario añadir un middleware que nos permita ejecutar los microservicios que hemos añadido. Por ello, como equipo hemos investigado sobre el caso y finalmente hemos encontrado varios servicios que podrian resolver el problema.

## Decision Drivers

* RF-9: Especificaciones de la Arquitectura de Microservicios

## Considered Options

* 0010-1-Amazon Lambda
* 0010-2-Docker Container

## Decision Outcome

Chosen option: "0010-1-Amazon Lambda", because Permitiría una ejecucion mas segura y eficiente, aunque a mayor coste. Las ventajas son mejores que las desventajas y ayudaria a brindar mas seguridad a nuestro sistema software

### Positive Consequences

* Eficiencia del sistema
* Mayor seguridad
* Mayor facilidad de implementacion

### Negative Consequences

* Los costes del sistema seran mayor
* Limitaciones por parte de Amazon

## Pros and Cons of the Options

### 0010-1-Amazon Lambda

AWS Lambda permite ejecutar el código en respuesta a los eventos y administra los recursos informáticos. Por tanto, se encargaria de ejecutar nuestros microservicios de manera segura.

* Good, because Alta escalabilidad
* Good, because Un servicio muy eficiente
* Good, because Facilidad de implementar
* Bad, because El costo puede variar dependiendo de los servicios que se ejecutaran
* Bad, because Las limitaciones como el tamaño del codigo que impone Amazon pueden traer problemas en un futuro.

### 0010-2-Docker Container

Docker Container permite creacion e implementacion de aplicaciones. Este servicio incluye lo necesario para ejecutar el codigo, ya sea las bibliotecas, herramientas y tiempo de ejecucion.

* Good, because Permite la automatizacion de la ejecución
* Good, because Control de versiones incluido
* Bad, because Menos seguridad que Amazon Lambda
* Bad, because Son mas lentos en la velocidad de ejecucion.

## Links

* https://www.docker.com/resources/what-container/
* https://aws.amazon.com/es/lambda/
