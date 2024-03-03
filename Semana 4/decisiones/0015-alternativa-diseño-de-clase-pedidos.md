# Alternativa-Diseño-De-Clase-Pedidos

* Status: accepted
* Deciders: Sergio
* Date: 2024-03-01

## Context and Problem Statement

El módulo de pedidos contiene todo lo necesario para la realización de los productos a la empresa, incluido el proceso de pago. Cada cliente cuenta con 3 intentos para realizar el mismo pedido.

## Decision Drivers

* RF-05: Procedimiento de realización de pedido con pago incluido.

## Considered Options

* 0015-1-Creación de la clase Pedidos

## Decision Outcome

Chosen option: "0015-1-Creación de la clase Pedidos", because Realiza de manera correcta y eficiente las funcionalidades que se describieron en los requisitos.

### Positive Consequences

* Sencillo y legible para el sistema
* Facil mantenimiento

### Negative Consequences

* Dependencia de componentes externos.

## Pros and Cons of the Options

### 0015-1-Creación de la clase Pedidos

Se crea la clase Pedidos que contiene las funcionalidades y atributos necesarias para realizar un pedido y comprobar el número de intentos, asi como poder comunicarse con el componente "Amazon Pay Checkout v2" para realizar el pago.

* Good, because Es una idea sencilla que realiza los requisitos del cliente
* Good, because Eficiente ya que esta conectada a la base de datos
* Good, because Facil legibilidad del sistema
* Bad, because La funcionalidad de Pedidos depende de un componente que si falla, se tiene que detener completamente.

## Links

* https://pay.amazon.es/checkoutv2
