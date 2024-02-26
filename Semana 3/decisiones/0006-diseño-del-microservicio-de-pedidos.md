# Diseño-Del-Microservicio-De-Pedidos

* Status: accepted
* Deciders: Sergio
* Date: 2024-02-22

## Context and Problem Statement

Para abordar el problema de diseñar el microservicio pedido se deben tomar en cuenta el número de intentos necesarios y poder realizar el pago. Para ello, se creará una clase GestorPedidos, que indicará el microservicio, clase Pedido y clase Producto, que serviran como bases para conocer la lista de productos y productos que existen respectivamente. La clase GestorCompra contiene las funcionalidades necesarias para realizar un pedido y comprobar el número de intentos, asi como poder comunicarse con el componente "Amazon Pay Checkout v2" para realizar el pago.

## Decision Drivers

* RF-05: Procedimiento de realización de pedido con pago incluido.

## Considered Options

* 0006-1-Clase GestorPedidos como microservicio

## Decision Outcome

Chosen option: "0006-1-Clase GestorPedidos como microservicio", because Es una respuesta sencilla para el problema que se plantea, pero realiza las funciones necesarias y de manera eficiente ademas de segura.

### Positive Consequences

* Mayor seguridad con los pagos
* Mejora la legibilidad externa
* Mantenimiento menos costoso

### Negative Consequences

* Gran dependencia del componente externo de pago

## Pros and Cons of the Options

### 0006-1-Clase GestorPedidos como microservicio

La clase GestorPedidos actua como microservicio, que estará conectada a la clase Pedido, la cual se organiza en los productos que decida añadir a este pedido. Ademas, la clase Producto esta conectada con la clase Pedido, esta clase sera la informacion del producto que se añadirá al pedido. Finalmente para realizar el pago, el microservicio GestorPedidos estará conectado al componente "Amazon Pay Checkout v2" para procesar el pago.

* Good, because La arquitectura es sencilla de entender
* Good, because Un componente externo como pago brinda seguridad
* Bad, because Si el componente falla, es necesario esperar la reparacion del servicio por Amazon.
