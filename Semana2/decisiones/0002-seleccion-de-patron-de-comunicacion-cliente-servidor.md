# Seleccion-De-Patron-De-Comunicacion-Cliente-Servidor

* Status: accepted
* Deciders: Sergio, Miguel
* Date: 2024-02-16

## Context and Problem Statement

En el contexto de nuestro proyecto de desarrollo de software se pide realizar la comunicación entre el módulo cliente y modulo servidor a través de un componente Gateway. Por esto, se abordan distintas soluciones. El módulo cliente se compone de una interfaz móvil (APP Móvil) y una interfaz web (APP Web), mientras que el módulo de servidor se compone de los 4 módulos siguientes: Clientes, Pedidos, Estadísticas y Reparto y rutas. Se utilizará un Gateway API Rest implementado por Amazon Web Services.

## Decision Drivers

* RF-03.1: Acceso mediante un componente Gateway

## Considered Options

* 0002-1-API Gateway sin load balancer
* 0002-2-API Gateway con load balancer
* 0002-3-Facade

## Decision Outcome

Chosen option: "0002-1-API Gateway sin load balancer", because Al no tener load balancer permite un mayor rendimiento del software ya que puede enviarse la solicitud directamente al servidor.

### Positive Consequences

* Mayor rendimiento de la aplicación
* Escalabilidad sencilla
* Se puede mejorar y añadir load balancer si se necesita

### Negative Consequences

* Se limita a un número de solicitudes a la vez.

## Pros and Cons of the Options

### 0002-1-API Gateway sin load balancer

El patrón API Gateway nos permite proporcionar un único punto de acceso para toda el API, lo que nos permite realizar una comunicación entre los módulos cliente-servidor y podemos aprovechar para agregar la seguridad que sea necesaria.

* Good, because Realiza una comunicación eficiente entre los módulos
* Good, because Añade seguridad al tener un sólo camino de comunicación
* Bad, because Puede llegar a causar tráfico con solicitudes simultáneas

### 0002-2-API Gateway con load balancer

A diferencia del patrón API Gateway sin load balancer, este se encarga de asegurar que un balanceador de carga distribuya la solicitud.

* Good, because Más seguridad en el servidor al no haber carga excesiva
* Good, because Más escalabilidad
* Bad, because Solo es eficiente si se va a trabajar con múltiples solicitudes durante mucho tiempo
* Bad, because Rendimiento más bajo al tener que pasar por un balanceador

### 0002-3-Facade

El patrón Facade es similar al patrón API Gateway, donde ambos actuan como intermediarios y facilitan la comunicación entre los módulos.

* Good, because Simplifica el subsistema.
* Bad, because Facade se centra en la arquitectura interna de un sistema más que en sistemas distribuidos
* Bad, because La escalabilidad es muy limitada
* Bad, because El rendimiento no llega al del patrón API Gateway

## Links

* https://www.adictosaltrabajo.com/2020/05/27/introduccion-al-api-gateway-pattern/
* https://reactiveprogramming.io/blog/es/patrones-arquitectonicos/api-gateway
* https://refactoring.guru/es/design-patterns/facade
