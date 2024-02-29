# Selección-De-Patrón-De-Gestión-De-Algoritmos-De-Rutas

* Status: proposed
* Date: 2024-02-29

## Context and Problem Statement

Las funcionalidades de RepartoYRutas son varias, por lo que se debera utilizar un modulo para acoplar estas funcionalidades. Entre estas funcionalidaes, se encuentra la gestion de algoritmos, la gestión cuenta con 2 algoritmos de optimización que se seleccionan en función de la demora del camión con un límite de 30 minutos.

## Decision Drivers

* RF-6: Logística y gestión de reparto.
* RF-6.1:	Gestión de los algoritmos de optimización.

## Considered Options

* 0008-1-Uso de patron de diseño Strategy
* 0008-1-Uso de patron de diseño State
* 0008-1-Uso de patron de diseño Template Method

## Decision Outcome

Chosen option: "0008-1-Uso de patron de diseño Strategy", because El patron Strategy soluciona los problemas que se pueden encontrar en la eleccion de algortimo de manera mas optima y menos compleja.

### Positive Consequences

* Permite una eleccion sencilla de algoritmos segun la información dada.
* Añade posibilidad de cambiar de algoritmos durante la ejecucion del programa.
* Se puede modificar la informacion de manera sencilla para la eleccion de algoritmos.

### Negative Consequences

* Si se utiliza un solo algoritmo una mayor cantidad de veces, el patron hace que se complique demasiado el modulo.

## Pros and Cons of the Options

### 0008-1-Uso de patron de diseño Strategy

En nuestro sistema software, habrán dos tipos de algoritmos de optimizacion que se seleccionaran en función de la demora del camión. Para ello decidimos añadir el patrón Strategy en el módulo de rutas donde se escogerá el algoritmo necesario en base a las necesidades. Dentro del módulo de rutas, se tiene una clase GestorAlgoritmos que recibe las solicitudes del módulo EventChannels y llama a la clase Context para elegir que algoritmo a ejecutar. La clase Context guarda el estado del tráfico en tiempo real y calcula cuál de los dos algoritmos se debería ejecutar en cada momento. Existe una interfaz Strategy, que contiene un método execute que utiliza los dos tipos de algoritmos. También, se creará una clase AlgoritmoRutaA y AlgoritmoRutaB que contienen los métodos de optimización e implementarán la interfaz Strategy.

* Good, because El patron Strategy soluciona los problemas que se pueden encontrar en la eleccion de algortimo.
* Good, because Elige correctamente según el contexto de la situación
* Good, because En nuestro caso, es el patrón mas óptimo
* Bad, because Es necesario realizar correctamente la implementación de eleccion de algortimos para que funcione correctamente.

### 0008-1-Uso de patron de diseño State

El uso del patron de diseño State es similar al patron Strategy. Segun el contexto dado se creara una clase que se hereda de la interfaz State, esto hace que se pueda escoger un algoritmo segun el contexto en tiempo real como pide el cliente.

* Good, because Escoge algoritmos correctamente
* Bad, because Es menos eficiente que el patrón Strategy

### 0008-1-Uso de patron de diseño Template Method

El patron de diseño Template Method es distinta a las anteriores comentadas, pero se puede utilizar en nuestro sistema software para escoger la rutas. Este patron ira descomponiendo el algoritmo en metodos y dependiendo del contexto que se da puede ir siguiendo unos pasos u otros para obtener la ruta mas optima.

* Good, because Consigue la ruta mas optima
* Bad, because Es un patron mas dificil de implementar en este contexto.
* Bad, because Depende completamente de una buena implementacion de logica del algoritmo.
* Bad, because Es mas complejo.

## Links

* https://refactoring.guru/design-patterns/strategy
* https://refactoring.guru/design-patterns/state
* https://refactoring.guru/design-patterns/template-method
* https://www.baeldung.com/cs/design-state-pattern-vs-strategy-pattern
