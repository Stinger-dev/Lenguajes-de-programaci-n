# Clasificacion de lenguajes de programacion

Para empezar podriamos definir lo que es un lenguaje de programacion, si buscamos en internet, uno de los primeros resultados que nos salta es el siguiente:

  _Un **lenguaje de programación** es un lenguaje **formal** que le proporciona a una persona, en este caso el programador, la capacidad de escribir una serie de **instrucciones o secuencias de órdenes** en forma de algoritmos con el fin de **controlar** el comportamiento físico o lógico de un sistema informático_

Podriamos entenderlo como una serie de **comandos preestablecidos** con los que controlamos de manera interna un ordenador

## Clasificaciones

A la hora de clasificar los lenguajes podriamos usar la siguiente divison

 - [**Nivel de abstracción**](#nivel-de-abstracción)
 - [**Forman de ejecución**](#forma-de-ejecución)
 - [**Paradigma**](#paradigma)
 
Estas tres caracteristicas son los principales puntos que diferencian y clasican a los lenguajes haciendolos mas o menos aptos para cada tipo de aplicacion

  ### Nivel de abstracción
 
Para comunicarnos con ordenador usamos **lenguaje máquina**, que es una **secuencia de 0 y 1** con lo que controlamos los pulsos **eléctricos** que se usan para transmitir el mensaje y las órdenes

Como este sistema es muy **complicados** cuando intentamos hacer programas más complejos, usamos **abstracciones para asemejarse al lenguaje natural**

Según el nivel de abstracción es más cercano al lenguaje de máquina.

 - [**Bajo nivel**](#bajo-nivel)
 - [**Medio nivel**](#medio-nivel)
 - [**Alto nivel**](#alto-nivel)

#### Bajo nivel
Estos fueron los primeros en salir, ya que son los mas cercanos a lenguaje maquina
El mas conocido con diferencia es ensamblador, tiene un set de instrucciones muy pequeño, pero con el que tecnicamente se puede hacer cualquier cosa, ya que es [**Turing completo**](https://es.wikipedia.org/wiki/Turing_completo) 

#### Medio nivel
Sucesores de los de bajo nivel, son una abstaccion mas cercana a lenguaje natural pero manteniendo la libertad que aporta estar cerca de esamblador
La muchos de estos lenguajes estan basados en ensamblador, es decir, usando instrucciones ya existentes en esamblador crean nuevas instrucciones como convinaciones de las anteriores, facilitando el uso y mejorando los tiempos de desarrollo

![](https://github.com/Stinger-dev/Lenguajes-de-programaci-n/blob/main/Assets/rust.png)

[**Rust**](https://www.rust-lang.org) es uno de ellos y ademas el lenguaje mas amados segun una [encuesta](https://insights.stackoverflow.com/survey/2021) realizada por StackOverflow, surge como un sucesor del mitico C++ pero sulucionando los problemas relacionados con el acceso a memoria.
Es uno de los lenguajes con mayor proyeccion cuando hablamos de codigo que es necesario que se ejecute lo mas rapido posible
Asi seria el mitico 'hola mundo' en este lenguaje 

```rust
fn main() {
    println!("Hello World");
}
```

#### Alto nivel
Son los mas cercanos al lenguaje natural y al igual que los de medio nivel se basan en los de bajo nivel, estos se basan en los lenguajes de medio nivel para general un set de instrucciones que facilita el uso y los tiempos de desarrollos sacrificando la flexibilidad de estos


### Forma de ejecución

Una vez ya tenemos la abstracción ahora tenemos que traducir el código a lenguaje máquina, y según cómo lo hagamos tenemos los siguientes modos:

- Compilados:
	Se traduce el código una vez y siempre que se use el programa se recurre al archivo binario.
	Rust
- Interpretados: 
	En vez de traducirse una vez, se traduce cada vez que se usa.
	PHP

_La diferencia entre un lenguaje interpretado y uno compilado es como la diferencia entre leer un libro traducido y un libro que está en el lenguaje original pero lo vas traduciendo mientras lo lees_

- Virtuales: 
  Son lenguajes más portables que los lenguajes compilados puesto que el código que se genera tras la compilación es un código intermedio o bytecode. Este código puede   ser a su vez interpretado por una máquina virtual instalada en cualquier equipo.
  Java


### Paradigma

Una vez ya tenemos el lenguaje y cómo lo traducimos, ahora tenemos que especificar cómo queremos estructurar el código, a esta manera de estructurar el código se le llama paradigma

- Imperativos:
	Basic
- Declarativos:
	Haskell
- Procedimentales:
	Erlang
- Orientados a objetos:
	Kotlin
- Funcionales:
	Miranda
- Lógicos:	
	Prolog


