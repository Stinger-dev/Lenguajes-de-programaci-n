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
El mas conocido con diferencia es [**ensamblador**](https://www.youtube.com/watch?v=4gwYkEK0gOk), tiene un set de instrucciones muy pequeño, pero con el que tecnicamente se puede hacer cualquier cosa, ya que es [**Turing completo**](https://es.wikipedia.org/wiki/Turing_completo) 

#### Medio nivel
Sucesores de los de bajo nivel, son una abstaccion mas cercana a lenguaje natural pero manteniendo la libertad que aporta estar cerca de esamblador
La muchos de estos lenguajes estan basados en ensamblador, es decir, usando instrucciones ya existentes en esamblador crean nuevas instrucciones como convinaciones de las anteriores, facilitando el uso y mejorando los tiempos de desarrollo

![](https://github.com/Stinger-dev/Lenguajes-de-programaci-n/blob/main/Assets/rust.png)

[**Rust**](https://www.rust-lang.org) es uno de ellos y ademas el lenguaje mas amados segun una [encuesta](https://insights.stackoverflow.com/survey/2021) realizada por StackOverflow. Surge como un sucesor del mitico C++ pero sulucionando los problemas relacionados con el acceso a memoria.
Es uno de los lenguajes con mayor proyeccion cuando hablamos de codigo que es necesario que se ejecute lo mas rapido posible
Asi seria una forma de calcular la sucesion de b 

```rust
fn main() {
let mut a = 1;
let mut b = 1;
let mut c = 0;
    for x in 0..10
    {
        if x > 1
        {
            c = a+b;
            a = b;
            b = c;
            println!("{}", c);
        }
        else
        {
            println!("{}", a)
        }
    }
}
```


https://user-images.githubusercontent.com/75430027/204874572-3463ea89-61f6-42dd-b3df-e361e103e868.mp4




#### Alto nivel
Son los mas cercanos al lenguaje natural y al igual que los de medio nivel se basan en los de bajo nivel, estos se basan en los lenguajes de medio nivel para general un set de instrucciones que facilita el uso y los tiempos de desarrollos sacrificando la flexibilidad de estos, uno de los mas usados actualmente seria [**JavaScript**](https://developer.mozilla.org/es/docs/Web/JavaScript) que es una mejora sobre [Java](https://www.java.com/es/)

### Forma de ejecución

Una vez ya tenemos la abstracción ahora tenemos que traducir el código a lenguaje máquina, y según cómo lo hagamos tenemos los siguientes modos:

#### Compilados:
Fueron los primeros en aparecer, este tipo de lenguaje para poder ejecutarlo hay que 'traducirlo' (compilarlo) en su totalidad antes de poder usarlo
Una de las cosas buenas de esto es que, una vez ya se ha compilado por primera vez, ya no hay que compilarlo nunca mas, lo que lo hace mas eficiente que los lenguajes interpretados. Pero uno de los mayores inconvenientes es que cada sistema necesita unas instrucciones especificas, por lo que un programa que haya funconado en windows no funcionaria en linux a menos que lo volvamos a compilar con las instrucciones necesarias

El encargado de compilar el rograma es denominado 'compilador' y es el encargado de pasar del lenguaje de mayor nivel que usamos para programar sea correctamente transformado a lenguaje maquina

El mas conocido de estos es C++, uno de los lenguajes en los que esta programado windows

#### Interpretados: 
A diferencia de los lenguajes compilados, este no se compila solo una vez, sino que cada vez que se ejecuta se va 'compilando' en tiempo real la instruccion que sea necesaria, de esto se encarga el 'interprete' 

Usar un lenguaje interpretado permite acelerar los tiempos de desarrollo ya que cada vez que hay que probar algo se puede probar esa parte sin necesicad de compilar el resto ademas de que sabes en que linea especificamente ha dejado de funcionar como deberias

La mayor ventaja de usar un lenguaje interpretado es que una vez escribes el codigo, este puede ser ejecutado en cualquier sistema que tenga instalado el interprete necesario, lo que facilita que un software sea multiplatarma

Como nada es perfecto, los lenguajes interpretados tambien tienen un gran problema, y es la eficiencia, ya que realmente cuando ejecutas el codigo no solo se esta ejecutando el programa, sino tambien el interprete que lo traduce en tiempo real, por lo que la velocidad de uno depende del otro. Aunque cada vez estan mas optimizados, por ejemplo, en la ultima versionde Python (la 3.11), se asegura haber mejorado la eficiencia entra un 10 y un 60 por ciento, por lo que cada vez tienen tiempos de ejecuccion menores

Asi es como se escribiria un codigo que cacula los n primeros numeros de la sucesion de fibonacci

``` python
def fibonacci (k, tmp=[1,1]):   
    if len(tmp) < k:
        tmp.append(tmp[-1]+tmp[-2])
        fibonacci(k, tmp)
    return tmp
    
paraImprimir = map(str,fibonacci(10))
print("->".join(paraImprimir))
```


https://user-images.githubusercontent.com/75430027/204875300-c4532b9f-f6ad-4ed2-bfe7-e3bea697de1f.mp4



_La diferencia entre un lenguaje interpretado y uno compilado es como la diferencia entre leer un libro traducido y un libro que está en el lenguaje original pero lo vas traduciendo mientras lo lees, probablemente te sea mas rapido leerlo si no necesitas traducirlo_

#### Virtuales: 
Son lenguajes más portables que los lenguajes compilados puesto que el código que se genera tras la compilación es un código intermedio o bytecode. Este código puede ser a su vez interpretado por una máquina virtual instalada en cualquier equipo. 


### Paradigma

Una vez ya tenemos el lenguaje y cómo lo traducimos, ahora tenemos que especificar cómo queremos estructurar el código, a esta manera de estructurar el código se le llama paradigma

- Imperativos: Basic
- Declarativos: Haskell
- Procedimentales: Erlang
- Orientados a objetos: Kotlin
- Funcionales: Miranda
- Lógicos: Prolog

```java
public class Main{
	public static void main(String[] args) {
		int a = 1;
		int b = 1;
		int c = 0;
		for (int i =0 ; i < 10; i++) {
		    if (i>1){
		        c = a+b;
		        a = b;
		        b = c;
                System.out.println(c);
		    }else{
		       System.out.println(a);
		    }
        	}
	}
}
```


https://user-images.githubusercontent.com/75430027/204877563-f610b23b-f692-4d77-b81d-29ce73d70255.mp4


