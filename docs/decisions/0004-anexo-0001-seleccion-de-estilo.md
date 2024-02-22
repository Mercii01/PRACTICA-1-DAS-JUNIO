# Anexo-0001-Seleccion-De-Estilo

* Status: proposed
* Deciders: Sergio
* Date: 2024-02-22

## Context and Problem Statement

Para la construccion de nuestro sistema software, se utilizará la arquitectura de Cliente-Servidor. Aunque hay que el numero de capas con las que se trabajará, en nuestro caso implicaremos 3 capas.

## Decision Drivers

* RF-01: Migrar la arquitectura a una basada en microservicios.
* RF-02: Acceso por parte de clientes mediante protocolos HTTP/REST.

## Considered Options

* 0004-1-Cliente Servidor de 3 capas

## Decision Outcome

Chosen option: "0004-1-Cliente Servidor de 3 capas", because Al tener 3 capas permite una mayor seguridad de peticiones y mejora el rendimiento, ademas de ser más sencilla de implementar debido a la facilidad de encajar las clases, modulos y componentes correspondientes en cada capa.

### Positive Consequences

* Más sencilla de implementar.
* Mayor potencia, logica y flexibilidad

### Negative Consequences

* Mayor complejidad frente a dos capas

## Pros and Cons of the Options

### 0004-1-Cliente Servidor de 3 capas

Esta arquitectura, a diferencia de lo habitual, se basa en 3 capas distintas. Una capa Cliente donde se realizan las peticiones, una capa Servidor, que procesa estas peticiones por los modulos (Reparto y rutas) y clases correspondientes (Estadisticas, Clientes y Pedidos) y finalmente una capa de accesso a base de datos, donde se encontrará el driver  "Microsoft JDBC Driver Version 12.6 para SQL Server" para acceder a las bases de datos.

* Good, because Permite una conexion segura
* Good, because Mayor esalabilidad y rendimiento
* Good, because Más eficiencia en el sistema
* Bad, because Añade complejidad al sistema

## Links

* https://iberasync.es/arquitectura-cliente-servidor-modelo-de-3-capas/
