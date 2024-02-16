# Seleccion-De-Patron-De-Conexion-De-Bases-De-Datos

* Status: proposed
* Deciders: Sergio
* Date: 2024-02-16

## Context and Problem Statement

Nuestro sistema software debera poder acceder a dos bases de datos, una donde se almacena los datos de los clientes y pagos llamada Clientes y otra donde se almacenan los datos restantes llamada Pedidos. La conexion entre los servicios y los servicios se realizara a traves de el driver "Microsoft JDBC Driver Version 12.6 para SQL Server"

## Decision Drivers

* RF-03: Conexión a los datos alojados en la BBDD mediante un componente Driver

## Considered Options

* 0003-1-Shared-database-per-service pattern
* 0003-2-Database-per-service pattern

## Decision Outcome

Chosen option: "0003-1-Shared-database-per-service pattern", because Permite una mejor comunicacion con las bases de datos con los servicios.

### Positive Consequences

* Mayor rendimiento de la aplicacion
* Implementacion mas sencilla
* Facilidad la migración desde arquitecturas monolíticas

### Negative Consequences

* Hay que tener mantenimiento constante para evitar un fallo que provoque caida de todos los servicios.

## Pros and Cons of the Options

### 0003-1-Shared-database-per-service pattern

Este patron realiza una sola conexion donde todos los servicios acceden a esta.

* Good, because Es mas sencillo acceder a las bases de datos.
* Good, because Mayor esacalabilidad.
* Good, because Mayor eficiencia en la base de datos.
* Bad, because Si llega a haber fallos en la base de datos, se afectan todos los servicios.

### 0003-2-Database-per-service pattern

Este patron realizara una conexion de base de datos por servicio, lo cual indica que habra el mismo numero de servicios que se añadan, habra el mismo numero de bases de datos que acceder.

* Good, because Mayor seguridad al no depender de otras bases de datos
* Bad, because Menos rendimiento del software
* Bad, because Mayor complejidad
* Bad, because Necesita mayor mantenimiento constante

## Links

* https://docs.aws.amazon.com/prescriptive-guidance/latest/modernization-data-persistence/database-per-service.html
* https://docs.aws.amazon.com/prescriptive-guidance/latest/modernization-data-persistence/shared-database.html
