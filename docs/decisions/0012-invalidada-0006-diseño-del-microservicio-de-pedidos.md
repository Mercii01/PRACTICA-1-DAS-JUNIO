# Invalidada-0006-Diseño-Del-Microservicio-De-Pedidos

* Status: accepted
* Deciders: Sergio
* Date: 2024-03-01

## Context and Problem Statement

Para abordar el problema de diseñar el microservicio pedido se deben tomar en cuenta el número de intentos necesarios y poder realizar el pago. Para ello, se creará una clase GestorPedidos, que indicará el microservicio, clase Pedido y clase Producto, que serviran como bases para conocer la lista de productos y productos que existen respectivamente. La clase GestorCompra contiene las funcionalidades necesarias para realizar un pedido y comprobar el número de intentos, asi como poder comunicarse con el componente "Amazon Pay Checkout v2" para realizar el pago.

## Decision Drivers

* RF-05: Procedimiento de realización de pedido con pago incluido.

## Considered Options

* 0012-1-Invalidar decision

## Decision Outcome

Chosen option: "0012-1-Invalidar decision", because Al invalidar la decision, podremos crearla nuevamente de manera correcta.

## Pros and Cons of the Options

### 0012-1-Invalidar decision

Es necesario invalidar la decision debido a los fallos en esta.
