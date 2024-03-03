# Alternativa-Diseño-De-Clase-Clientes

* Status: accepted
* Deciders: Sergio
* Date: 2024-03-01

## Context and Problem Statement

El módulo de clientes permite acceder a los datos personales de los clientes consistentes en identificador de cliente, nombre, apellidos, email y teléfono móvil.

## Decision Drivers

* RF-04: Procedimiento de acceso a datos personales de clientes

## Considered Options

* 0014-1-Creación de la clase Cliente

## Decision Outcome

Chosen option: "0014-1-Creación de la clase Cliente", because Realiza correctamente los requisitos del cliente de manera sencilla y eficaz.

### Positive Consequences

* Facilidad de mantener
* El sistema es mas sencillo de leer

### Negative Consequences

* Fragilidad en una sola clase

## Pros and Cons of the Options

### 0014-1-Creación de la clase Cliente

Para gestionar la informacion de los clientes se hara a traves de la clase Cliente que realizará las operacion CRUD (Crear, Leer, Actualizar y Borrar) y sera el respondable de obtener la informacion de estos de la base de datos.

* Good, because Mayor facilidad de legibilidad
* Good, because Facil de mantener
* Good, because Mayor sencillez de sistema
* Bad, because La obtencion de clases depende completamente de una clase y una conexion intacta con la base de datos.
