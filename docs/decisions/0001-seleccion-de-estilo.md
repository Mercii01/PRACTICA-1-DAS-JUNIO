# Seleccion-De-Estilo

* Status: proposed
* Deciders: Sergio,Miguel
* Date: 2024-02-09

## Context and Problem Statement

En el contexto de nuestro proyecto de desarrollo de software, hemos decidido adoptar una arquitectura cliente-servidor para mejorar la modularidad y la escabilidad de nuestro sistema.

## Decision Drivers

* RF-01: Migrar la arquitectura a una basada en microservicios.
* RF-02: Acceso por parte de clientes mediante protocolos HTTP/REST.

## Considered Options

* 0001-1-Arquitectura cliente-servidor
* 0001-2-Arquitectura orientada a servicios

## Decision Outcome

Chosen option: "0001-1-Arquitectura cliente-servidor", because permite una implementacion completa y sencilla de las tareas que se piden en la aplicacion.

### Positive Consequences

* Pueden realizarse los demas requisitos
* Permite el uso de la aplicacion por parte de varios clientes a la vez

### Negative Consequences

* Hay que mantener mucha seguridad para evitar fallos de servidor

## Pros and Cons of the Options

### 0001-1-Arquitectura cliente-servidor

El modelo cliente-servidor accede a datos de las bases de datos y recibe peticiones asincronas y respuestas de eventos.

* Good, because Sigue un protocolo HTTP/REST con un componente Gateway
* Good, because Es una arquitectura escalable.
* Good, because Los clientes pueden acceder a datos y aplicaciones en el servidor
* Bad, because Al ser basada en el servidor, crea gran inseguridad en un fallo de este.

### 0001-2-Arquitectura orientada a servicios

La arquitectura orientada a servicios fomenta la creacion de servicios para la integracion de aplicaciones.

* Good, because Es sencillo implementar los servicios que se piden.
* Bad, because Es similar a la arquitectura basada en microservicios ya que son procesos que se comunican con otros a traves de una red para conseguir un objetivo.
