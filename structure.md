### data and action

Algo que siempre vas a tener que tener en cuenta. Cuando estás programando es la división entre datos y acciones? Cómo vas a organizar la relación entre los datos y las acciones?

### once you divide into pieces the interface is key

Los programas más complejos suelen ser más que una tarea en 50 líneas de código. Eso implica que tienes algo que resolver que puedes dividir en subtareas y que además te interesa que esté clara esa clasificación esa división para poder reusar cada una de las subtareas y para que si trabajas en equipo distintos equipos distintos miembros del equipo puedan dedicarse a resolver cada una de las sub tareas e incluso para que puedas comprobar mediante test que cada una de las partes funciona adecuadamente

The interface is the contract.


## procedural

scope y sobre cómo las variables de dentro de la función no se pueden usar fuera y las variables globales no se pueden modificar dentro de la función

Si se usa global. Proceed at your own risk. Dragons ahead. Let's hope that you really know what your doing. Think it twice, youre probably wrong

Most simple than object oriented and functional, so if you are starting in programming, procedural might be easier.

A procedure is a sequence of instructions grouped under a single name, which can be called to execute a specific task. Procedures enable breaking down a program into smaller, more manageable modules. They can be invoked in various parts of the program, including within other procedures, which facilitates code reuse and enhances readability and error correction.
Code errors are more easily corrected: By isolating specific tasks in procedures, developers can test and debug each part of the program independently. In case of an error in a program organized with procedures, a developer can locate and correct the error more quickly than in poorly organized code, leading to significant time and efficiency savings.

Implementation becames secondary, interface is more relevant because if you change the implementation of a procedure without changing its interface the rest of the program won't be required to be modified.

The code is reusable: One of the primary benefits of procedural programming is the ability to reuse code in different parts of the program without needing to rewrite it
DRY
encourage reusability and enables code sharing

The code is clearer: Breaking down a program into procedures makes the code clearer and easier to understand. Each procedure has a specific role, assisting developers in following their program more easily and effectively.

scope. only part of the data is managed by different functions, this allows for easier debugging.
Scoping keeps procedures modularized by preventing one from accessing non-local variables from other procedures without explicit clearance.

Procedural code is simple and often the most appropriate given a simple use case. If it's organized well into modular functions with good code re-use

## interface

- function name
- arguments
- return types
- are arguments modified

## python es dinámico

en python no se puede enforce lo que se devuelve, pero, en general, no es buena idea que la función pueda devolver distintas cosas dependiendo de los argumentos que se le pasen o del estado del programa.

aunque la interfaz de la función puede indicarse con type hints (que, al menos por el momento no son enforced)

## by reference, by value, mutable and inmutable

Un problema gordo en programación es que hay una parte de la interfaz de las funciones que no es explícita, el hecho de si modifica o no los objetos/valores que le pasas. Si los argumentos se pasan por valor no hay problema porque se copian tienes la garantía de que tus valores/objetos originales no se van a modificar, pero si los pasas por referencia y son objetos mutables no tienes esa garantía y eso en python no es explícito

Lo malo es no poder indicar en la interfaz que estás modificando los argumentos. Una forma de indicarlo es que la función no devuelva nada, así el que llama sabe que lo que hace la función no es devolver algo nuevo. Eso pasa, por ejemplo, con el método Sort en Python. Mientras que la función sorted sí copia, no modifica, y devuelve
Nunca escribas una función que pueda devolver dos cosas distintas dependiendo de los parámetros que le pases
Esto es ampliable a nunca escribas una función que no quede muy claro si modifica o no modifica los parámetros que le has pasado
En principio si vas a modificar algo molaría que lo indicases en la interfaz y la forma de hacerlo. Un Python es no devolviendo nada en la función


si pasas por valor te aseguras de que los argumentos no serán cambiados, pero en python no se puede pasar por valor, sólo por referencia.

El problema de pasar por valor es el coste en memoria y tiempo de la copia.

no hay problema si los objetos son inmutables porque aunque los pases por referencia la función nunca podrá cambiarlos.
El problema es cuando se pasa por referencia un objeto mutable.

It would be ideal to never alter a value passed to a function. Pass by value enforces that, but in Python that is not possible and you rely in the writer of the function to do it.
Argument modification is part of the interface, but not an obvious part.

Immutability may cost significant resources since every value counts for a new space in memory.

un método que no devuelve nada no implica que vaya a modificar los argumentos que se le pasan.
pero sí que molaría que si cambias un objeto, que no lo devuelvas.

este es uno de los motivos por los que en python hay objetos mutables e inmutables, si quieres estar seguro de que no se modifica el objeto, usa uno inmutable.

si queda claro no veo problema porque el usuario podría enviar una copia si quiere conservar el original

## you can test every procedure and make sure that it complies with its interface/contract

Una forma de comprobar que la interfaz el contrato funciona es hacer test y es una manera muy recomendable. Si no tienes test no sabes si la característica es tan implementando realmente funciona o no, sobre todo si luego la cambias la implementación

## Ejemplo cadena de texto

Crea funciones para trabajar con un texto inmutable: upper, lower, print. La estructura de datos debe ser una secuencia de caracteres individuales.

## modules

Use functions for encapsulation and bundle functionality and interfaces into modules to be exported and used as necessary when dealing with procedural level code blocks in your application.

Las clases agrupan todos los métodos que tienen que ver con una estructura de datos en un mismo lugar

## object oriented

Object-Oriented Programming (OOP) and Procedural Programming are two of the most common programming paradigms used today.

The main building block of OOP are objects
code and data in one unit

The main idea behind OOP is to communicate with objects through their public attributes.

Extensible codebase: With the right design, Object-Oriented programs are made to scale. 

## class and object

## encapsulation

Encapsulation: One of the key concepts of OOP is encapsulation, which allows data to be hidden and protected from unauthorized access.
una clase User puede tener una propiedad privada password y un método público verify_password.
encapsulation. This is the bundling of data, and the methods that operate on these data, into a single unit called an object. This means that the data is not accessible to the outside world and only those functions, 
hiding details about an object's implementation and exposing only the necessary interface

Encapsulation. Encapsulation can be defined as wrapping the code or methods (properties) and the related fields or variables together as a single unit.

If a change is required, you can simply modify the code of a specific object, without affecting other parts of the program. This is particularly useful in large projects where changes are inevitable. In contrast, in procedural programming, a change in one part of the program may require changes in several other parts, making it more complex and time-consuming

A class contains both data and functions.

encapsulation improves modularity. Objects are self-contained, and each bit of functionality does its own thing while leaving the other bits alone,

## state is natural

## Beneficio de la herencia

Inheritance. It refers to a concept where a subclass, also known as a child class or derived class, is the class that inherits the properties and behaviors of another class known as the superclass.

Inheritance: In OOP, classes can inherit properties and methods from other classes, reducing the amount of code that needs to be written. This helps to reduce code duplication and improve code readability.

cuadrado se convierte en rectangulo, pero no hay que cambiar el código que trabajaba con rectángulos. en el caso de las funciones también puede hacerse, haciendo que calc_area_cuadrado llame a calc_area_reactangulo, pero si la función era calc_area queda un poco peor poruqe hay que crear una nueva calc_area_cuadrado
Con la herencia es muy natural y no cambia la interfaz antigua en absoluto.

while less useful for code-reuse than first believed, it is still a good technique to model similar code

## polymorphism

polymorphism es un término confuso distintas personas lo usan de distinto modo.

Because a single function can shape-shift to adapt to whichever class it’s in, you could create one function in the parent Car class called “drive” — not “driveCar” or “driveRaceCar,” but just “drive.” 

Compile-time polymorphism (Overloading) - allows a function to have multiple implementations based on function signature.

## desventajas de OOP

Una desventaja de la programación orientada a objetos es que, para un principiante, es más compleja que la procedural y otra es que suele ser más verbose.

## lists comprenhesions

No sé puede explicar todo esto sin explicar list comprehension. No tiene sentido pedagógico
Debe haber una sección sobre cómo crear generadores con listo con pre expansión yiejd


## idea programación funcional

Paradigma alternativo orientada a objetos o la procedural, sino que simplemente trata de solventar una cuestión que es si tenemos muchos cálculos para realizar y esos cálculos que se pueden realizar mediante funciones puras que garantizan su independencia. Tal vez la parte del algoritmo que hace el bucle, podríamos separarla de manera que podamos crear esa parte de una manera muchísimo más eficiente y que además no debemos de implementarla cada vez que queremos hacer un cálculo con la misma característica

 Para análisis de grandes cantidades de datos es ideal

Menos memoria y fácil paralelización

a purely functional program always yields the same value for an input, and the order of evaluation is not well-defined

Ideal for concurrent and parallel programming: In Concurrent programming, multiple tasks are executed concurrently (not necessarily simultaneously), while in parallel programming, multiple tasks are executed parallelly (simultaneously).

The classic use case is data processing

Usually it is harder to think in functional terms.

hay gente que piensa que lo más importante en la programación funcional es que los argumentos pasados a las funciones no se modifican (¿será eso un cambio de estado y por lo tanto la función no será pura?)

## pure function

functions, and prevents them from affecting other elements — that is, no side effects.

Side effect - Refers to the act of modifying non-local attributes inside a function. Programming languages that allow side effects are known as impure functional languages.

## inmutable variables

The most important tenet of Functional Programming is immutable variables -- the inability to reassign a value to an already instantiated variable.

Immutable variables make it easier to understand the value behind each variable in code at any one of its references.

## functions are first class citizens

functions are treated like any other variable. For example, in such a language, a function can be passed as an argument to other functions, can be returned by another function, and can be assigned as a value to a variable

Higher-order functions: These functions take functions as arguments or functions that return functions. This is possible because functions and data are the same.

Pure Function: A function that returns a value and does not alter the state of a non-local attribute.

Referential transparency: A mechanism that does not permit one to change the value of a variable once defined. This mechanism guarantees functional programs to be referentially transparent i.e., if a == b, then f(a) == f(b). This property of purely functional languages makes programs easier to reason and optimize.

Immutability may cost significant resources since every value counts for a new space in memory.

## lambdas

## map, reduce, filter

map: It applies a function to each element in the collection, returning a new collection with the transformed elements.
filter: Returns a new collection that only contains the elements that match the condition specified (called a predicate).
reduce: Combines the elements of a collection using a binary function to produce a single value.


### sequence and iterator


### generators low memory and pipeline lazy execution

la computación e incluso con la caché del procesador

## functools