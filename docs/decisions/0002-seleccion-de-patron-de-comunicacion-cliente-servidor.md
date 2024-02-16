# Seleccion-De-Patron-De-Comunicacion-Cliente-Servidor

* Status: proposed
* Deciders: Sergio
* Date: 2024-02-16

## Context and Problem Statement

En el contexto de nuestro proyecto de desarrollo de software se pide realizar la comunicacion entre el modulo cliente y modulo servidor a traves de un componente Gateway. Por esto, se abordan distinas soluciones. El modulo cliente se compone de una interfaz movil (APP Movil) y una interfaz web (APP Web), mientras que el modulo de servidor se compone de los 4 modulos siguientes: Clientes, Pedidos, Estadistica y Reparto y rutas. Se utilizará una API Rest implementada con AWS.

## Decision Drivers

* RF-03.1: Acceso mediante un componente Gateway

## Considered Options

* 0002-1-API Gateway sin load balancer
* 0002-2-API Gateway con load balancer
* 0002-3-Facade

## Decision Outcome

Chosen option: "0002-1-API Gateway sin load balancer", because Al no tener load balancer permite un mayor rendimiento del software ya que puede enviarse la solicitud directamente al servidor.

### Positive Consequences

* Mayor rendimiento de la aplicacion
* Escalabilidad sencilla
* Se puede mejorar y añadir load balancer si se necesita

### Negative Consequences

* Se limita a un numero de solicitudes a la vez.

## Pros and Cons of the Options

### 0002-1-API Gateway sin load balancer

El patron API Gateway nos permite proporcionar un único punto de acceso para toda el API, lo que nos permite realizar una comunicacion entre los modulos cliente-servidor y podemos aprovechar para agregar la seguridad que sea necesaria. Se considera la

* Good, because Realiza una comunicacion eficiente entre los modulos
* Good, because Añade seguridad al tener un solo camino de comunicacion
* Bad, because Puede llegar a causar trafico con solicitudes simultaneas

### 0002-2-API Gateway con load balancer

A diferencia del patron API Gateway sin load balancer, este se encarga de asegurar que un balanceador de carga distribuya la solicitud.

* Good, because Mas seguridad en el servidor al no haber carga excesiva
* Good, because Mas esalabilidad
* Bad, because Solo es eficiente si se va a trabajar con multiples solicitudes durante mucho tiempo
* Bad, because Rendimiento mas bajo al tener que pasar por un balanceador

### 0002-3-Facade

El patron Facade es similar al patron API Gateway, donde ambos actuan como intermediarios y facilitan la comunicacion entre los modulos.

* Good, because Simplifica el subsistema.
* Bad, because Facade se centra en la arquitectura interna de un sistema mas que en sistemas distribuidos
* Bad, because La escalabilidad es muy limitada
* Bad, because El rendimiento no llega al del patron API Gateway

## Links

* https://www.adictosaltrabajo.com/2020/05/27/introduccion-al-api-gateway-pattern/
* https://reactiveprogramming.io/blog/es/patrones-arquitectonicos/api-gateway
* https://refactoring.guru/es/design-patterns/facade
