# Clasificacion de lenguajes de programacion

Para empezar, podríamos definir lo que es un lenguaje de programación buscando en internet. De esta manera, uno de los primeros resultados que nos aparece es el siguiente:

  _Un **lenguaje de programación** es un lenguaje **formal** que le proporciona a una persona, en este caso el programador, la capacidad de escribir una serie de **instrucciones o secuencias de órdenes** en forma de algoritmos con el fin de **controlar** el comportamiento físico o lógico de un sistema informático_

Podríamos entenderlo como una serie de **comandos preestablecidos** con los que controlamos de manera interna un ordenador

## Clasificaciones

A la hora de clasificar los lenguajes podríamos usar la siguiente jerarquía o división:

 - [**Nivel de abstracción**](#nivel-de-abstracción)
 - [**Forman de ejecución**](#forma-de-ejecución)
 - [**Paradigma**](#paradigma)
 
Estas tres características son los principales puntos que diferencian y clasican a los lenguajes haciéndolos más o menos aptos para cada tipo de aplicación

  ## Nivel de abstracción
 
Para comunicarnos con un ordenador usamos **lenguaje máquina**, que es una **secuencia de 0 y 1 (ceros y unos)** con lo que controlamos los pulsos **eléctricos** que se usan para transmitir el mensaje y las órdenes

Como este sistema es muy **complicado** cuando intentamos hacer programas más complejos, usamos **abstracciones para asemejarse al lenguaje natural**

Según el nivel de abstracción, un lenguaje tiene un nivel más bajo cuando es más cercano al lenguaje de máquina.

 - [**Bajo nivel**](#bajo-nivel)
 - [**Medio nivel**](#medio-nivel)
 - [**Alto nivel**](#alto-nivel)

### Bajo nivel
Estos fueron los primeros en salir, ya que son los mas cercanos a lenguaje máquina
El mas conocido con diferencia es [**ensamblador**](https://www.youtube.com/watch?v=4gwYkEK0gOk), tiene un set de instrucciones muy pequeño, pero con el que técnicamente se puede hacer cualquier cosa, ya que es [**Turing completo**](https://es.wikipedia.org/wiki/Turing_completo) 

### Medio nivel
Sucesores de los de bajo nivel, son una abstacción mas cercana a lenguaje natural pero manteniendo la libertad que aporta el estar cerca del esamblador
Ya muchos de estos lenguajes estan basados en ensamblador, es decir, usando instrucciones ya existentes en esamblador crean nuevas instrucciones como combinaciones de las anteriores, facilitando el uso y mejorando los tiempos de desarrollo.

![Rustacean](https://github.com/Stinger-dev/Lenguajes-de-programaci-n/blob/main/Assets/rust.png)

[**Rust**](https://www.rust-lang.org) es uno de ellos y ademas el lenguaje más aclamado según una [encuesta](https://insights.stackoverflow.com/survey/2021) realizada por StackOverflow. Surge como un sucesor del mítico C++ pero sulucionando los problemas relacionados con el acceso a memoria.
Es uno de los lenguajes con mayor proyección cuando hablamos de código que es necesario que se ejecute lo mas rápido posible.
Así sería una forma de calcular la sucesión de b 

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




### Alto nivel
Son los mas cercanos al lenguaje natural y al igual que los de medio nivel se basan en los de bajo nivel, estos se basan en los lenguajes de medio nivel para generar un set de instrucciones que facilita el uso y los tiempos de desarrollos sacrificando la flexibilidad de estos. 
Uno de los más usados actualmente sería [**JavaScript**](https://developer.mozilla.org/es/docs/Web/JavaScript) que es una mejora sobre [Java](https://www.java.com/es/)

## Forma de ejecución

Una vez ya tenemos la abstracción ahora tenemos que traducir el código a lenguaje máquina, y según cómo lo hagamos tenemos los siguientes modos:

### Compilados:
Fueron los primeros en aparecer, este tipo de lenguaje para poder ejecutarlo hay que 'traducirlo' (compilarlo) en su totalidad antes de poder usarlo
Una de las cosas buenas de esto es que, una vez ya se ha compilado por primera vez, ya no hay que compilarlo nunca mas, lo que lo hace mas eficiente que los lenguajes interpretados. Pero uno de los mayores inconvenientes es que cada sistema necesita unas instrucciones específicas, por lo que un programa que haya funcionado en windows no funcionaría en linux a menos que lo volvamos a compilar con las instrucciones necesarias.

El encargado de compilar el programa es denominado 'compilador' y es el encargado de pasar del lenguaje de mayor nivel que usamos para programar sea correctamente transformado a lenguaje máquina.

El más conocido de estos es C++, uno de los lenguajes en los que está programado windows.

### Interpretados: 
A diferencia de los lenguajes compilados, este no se compila solo una vez, sino que cada vez que se ejecuta se va 'compilando' en tiempo real la instrucción que sea necesaria, de esto se encarga el 'intérprete'.

Usar un lenguaje interpretado permite acelerar los tiempos de desarrollo ya que cada vez que hay que probar algo se puede probar esa parte sin necesidad de compilar el resto ademas de que sabes en qué línea específica ha dejado de funcionar como debería.

La mayor ventaja de usar un lenguaje interpretado es que una vez escribes el código, este puede ser ejecutado en cualquier sistema que tenga instalado el intérprete necesario, lo que facilita que un software sea multiplatarma.

Como nada es perfecto, los lenguajes interpretados también tienen un gran problema, y es la eficiencia, ya que realmente cuando ejecutas el código no solo se está ejecutando el programa, sino también el intérprete que lo traduce en tiempo real, por lo que la velocidad de uno depende del otro. Aunque cada vez están más optimizados, por ejemplo, en la última version de Python (la 3.11), se asegura haber mejorado la eficiencia entre un 10 y un 60 por ciento, por lo que cada vez tienen tiempos de ejecucción menores.

Así es como se escribiría un codigo que cacula los n primeros numeros de la sucesión de fibonacci en python uno de los lenguajes compilados por exelencia.

![](https://github.com/Stinger-dev/Lenguajes-de-programaci-n/blob/main/Assets/py.png)

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



_La diferencia entre un lenguaje interpretado y uno compilado es como la diferencia entre leer un libro traducido y un libro que está en el lenguaje original pero lo vas traduciendo mientras lo lees, probablemente te sea mas rápido leerlo si no necesitas traducirlo_

### Virtuales: 
Son lenguajes más portables que los lenguajes compilados puesto que el código que se genera tras la compilación es un código intermedio o bytecode. Este código puede ser a su vez interpretado por una máquina virtual instalada en cualquier equipo. 






## Paradigma

Una vez ya tenemos el lenguaje y cómo lo traducimos, ahora tenemos que especificar cómo queremos estructurar el código, a esta manera de estructurar el código se le llama paradigma.

### Imperativos
Fueron los primeros en surgir y uno de los mas simples de entender, consiste en una secuencia claramente definida de instrucciones que el ordenador sigue en el orden especificado, la mayoria de los lenguajes mas populares soportan este paaradigma. Basic y cobol son uno de los lenguajes mas antiguos con esta funcionalidad.

### Declarativo
Aquí lo importante no es el cómo se hace, sino dar la orden adecuada y este buscará el mejor algoritmo para ello, un ejemplo de programacion declarativa es cuando el python ponemos lo siguiente:
```python
'hola mundo'.upper()
```
Ya que realmente no estamos programando el algoritmo que pone todas las letras en mayúsculas, sino estamos llamando a uno escrito por otra persona.

Este paradigma suele hacer el código más fácil de leer y fácil de hacer programas simples, un lenguaje declarativo, si nos vamos al significado más amplio, sería SQL, ya que realemnte no nos encargamos de hacer casi ninguno de los algoritmos que suceden.

### Procedimentales
Este paradigma se basa en agrupar muchas instrucciones más pequeñas en una especie de grupos llamados procesos.
Un ejemplo seria imprimir la tabla de multiplicar del 5, pero en vez de usar un bucle, usamos un print para cada uno de los valores.
Un ejemplo de lenguajes que aplican este paradigma es Erlang.

### Orientados a objetos
Es probablemente el paradigma más importante hasta la fecha y el más usado.
Se basa en crear estructuras de datos funcionales (llamadas clases) que son una especie de planos para un objeto, que es una iteración de la clase que una vez formada tiene 'vida propia'.
En las clases no solo se almacenan datos sino que también código que trabaja de manera privada o pública con esa información, manteniendo una encapsulación de datos que mejora la privacidad.
Es decir, podríamos tener una clase llamada proyectil, que tenga como variables la posición y la velocidad, y como métodos el qué hacer en caso de que colisione.
Así cada vez que queramos generar una bala, en vez de tener que escribir un código único para cada una, invocamos a un objeto que sea de clase bala. 
Muchos de los lenguajes mas usados actualmente implementan orientación a objetos de manera nativa, algunos incluso son puramente orientados a objetos, como java, pero el primer lenguaje que impelementó el concepto de clase fue [Simula](https://es.wikipedia.org/wiki/Simula) 
Actualmente la orientación a objetos es aun más compleja con los conceptos de herencia y polimorfísmo.

![](https://github.com/Stinger-dev/Lenguajes-de-programaci-n/blob/main/Assets/Java.png)

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

### Funcionales
Realmente podría estar dento de lenguajes declarativos, ya que son un tipo de ellos pero con la característica de que estos usan puramente funciones matemáticas, este tipo de lenguajes se usa principalmente para manejar información, ya que no pueden contener variables.
[Lisp](https://en.wikipedia.org/wiki/Lisp_(programming_language)) o [Miranda](https://en.wikipedia.org/wiki/Miranda_(programming_language)) son ejemplos de lenguajes que usan el paradigma funcional como paradigma principal.


### Lógicos
El paradigma se basa en la descomposición de un programa en sus componentes lógicos y elementos de control.
Este paradigma es muy poco utilizado, ya que es uno de los mas difíciles de interpretar por un humano cuando se ve el código, pero lejos de ser una desventaja, se suele usar a su favor en aplicaciones en las que es beneficioso aislar los cálculos, como en la demostración de teoremas.
El lenguaje lógico por excelencia es Prolog.


Realmente casi ningún lenguaje es puramente de un paradigma, ya que normalmente son una combinación de diferentes tipos de código.


