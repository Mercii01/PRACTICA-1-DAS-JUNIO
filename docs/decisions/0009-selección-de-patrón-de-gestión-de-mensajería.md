# Selección-De-Patrón-De-Gestión-De-Mensajería

* Status: proposed
* Deciders: Sergio
* Date: 2024-02-29

## Context and Problem Statement

Se deben reportar las incidencias en el reparto. Las incidencias pueden ser de tres tipos: camión averiado, demora, no entrega de pedido. Por otra parte, pensando en futuras ampliaciones, se pretende que el elemento reparto y rutas pueda notificar a los clientes el estado de su pedido vía mensajes al teléfono móvil y otros posibles canales de comunicación como Instagram

## Decision Drivers

* RF-6.2: Sistema de reporte de incidencias.
* RF-8: Sistema de notificación a los clientes sobre el estado de su pedido.

## Considered Options

* 0009-1-Uso de patron Publish-Suscribe

## Decision Outcome

Chosen option: "0009-1-Uso de patron Publish-Suscribe", because Realiza el envio de notificaciones que el cliente pide. Ademas, consigue agrupar a un solo patron para ambos tipos de envios.

### Positive Consequences

* Se hace un envio de notifiaciones correcto a los remitentes
* Se permite escoger el remitente

### Negative Consequences

* Requiere de una gestión adecuada para evitar colapsos operacionales.

## Pros and Cons of the Options

### 0009-1-Uso de patron Publish-Suscribe

Se utilizara el patron Publish-Suscribe para enviar notifiaciones a los remitentes necesarios dependiendo de la notificacion, ya sea una averia de camion o hasta un menasje a los clientes. Se utilizara una clase Publisher que se encarga de las operaciones necearias para realizar el envio de mensajeria y comunicacion de remitenes, que estara conectada a la interfaz Suscriber. Esta interfaz sera el intermediario para conocer que usuario es el remitente.

* Good, because Mayor escalabilidad
* Good, because Menos complejidad
* Bad, because Es necesaria una buean gestion ya que se pueden crear problemas de eficiencia en caso contrario.

## Links

* https://keepcoding.io/blog/desventaja-de-pubsub/#Cual_es_la_desventaja_de_PubSub
