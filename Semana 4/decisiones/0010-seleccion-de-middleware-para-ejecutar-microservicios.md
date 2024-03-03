# Seleccion-De-Middleware-Para-Ejecutar-Microservicios

* Status: accepted
* Deciders: Sergio, Miguel
* Date: 2024-03-01

## Context and Problem Statement

Es necesario añadir un middleware que nos permita ejecutar los microservicios que hemos añadido. Por ello, como equipo hemos investigado sobre el caso y finalmente hemos encontrado varios servicios que podrian resolver el problema. Para añadirlo, se creará una capa de menor nivel llamada "Capa de Servicios" que se utilizará por la capa de negocio y la capa de clientes.

## Decision Drivers

* RF-9: Especificaciones de la Arquitectura de Microservicios

## Considered Options

* 0010-1-Amazon Lambda
* 0010-2-Docker Container

## Decision Outcome

Chosen option: "0010-1-Amazon Lambda", because Permitiría una ejecución más segura y eficiente, aunque a mayor coste. Las ventajas son mejores que las desventajas y ayudaría a brindar más seguridad a nuestro sistema software

### Positive Consequences

* Eficiencia del sistema
* Mayor seguridad
* Mayor facilidad de implementación
* Alta disponibilidad y tolerancia a fallos
* Escalabilidad automática según la cantidad de peticiones

### Negative Consequences

* Los costes del sistema serán mayores
* Limitaciones por parte de Amazon

## Pros and Cons of the Options

### 0010-1-Amazon Lambda

AWS Lambda permite ejecutar el código en respuesta a los eventos y administra los recursos informáticos. Por tanto, se encargaria de ejecutar nuestros microservicios de manera segura. Este se añadira en la Capa de Servicios para poder ser utilizado.

* Good, because Alta escalabilidad
* Good, because Un servicio muy eficiente
* Good, because Facilidad de implementar
* Bad, because El costo puede variar dependiendo de los servicios que se ejecutaran
* Bad, because Las limitaciones como el tamaño del codigo que impone Amazon pueden traer problemas en un futuro.

### 0010-2-Docker Container

Docker Container permite creacion e implementacion de aplicaciones. Este servicio incluye lo necesario para ejecutar el codigo, ya sea las bibliotecas, herramientas y tiempo de ejecucion. Este se añadirá en la Capa de Servicios para poder ser utilizado.

* Good, because Permite la automatización de la ejecución
* Good, because Control de versiones incluido
* Bad, because Menos seguridad que Amazon Lambda
* Bad, because Son más lentos en la velocidad de ejecución.
* Bad, because Problemas con la compatibilidad del hardware
* Bad, because Docker se encuentra en constante evolución, puede llevar a cambios frecuentes en la infraestructura

## Links

* https://www.docker.com/resources/what-container/
* https://aws.amazon.com/es/lambda/
