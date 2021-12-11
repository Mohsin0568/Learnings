# Design Patterns


## Creational:
Creational design patterns relate to how objects are constructed from classes. New-ing up objects may sound trivial but unthoughtfully littering code with object instance creations can lead to headaches down the road. The creational design pattern come with powerful suggestions on how best to encapsulate the object creation process in a program.

## Structural:
Structural patterns are concerned with the composition of classes, i.e. how the classes are made up or constructed.

## Behavioural:
Behavioural design patterns dictate the interaction of classes and objects amongst each other and the delegation of responsibility. 


## Builder Pattern:

As the name implies, a builder pattern is used to build objects. Sometimes, the objects we create can be complex, made up of several sub-objects or require an elaborate construction process. The exercise of creating complex types can be simplified by using the builder pattern. A composite or an aggregate object is what a builder generally builds.

Formally, a builder pattern encapsulates or hides the process of building a complex object and separates the representation of the object and its construction. The separation allows us to construct different representations using the same construction process. In Java speak, different representations implies creating objects of different classes that may share the same construction process.

Suppose that you have a class with a handful of instance attributes, such as the Employee class shown below. In this class, some of the instance attributes are required while the rest are optional. What kind of constructors should you write for such a class? A first option would be to have a constructor that only takes the required attributes as parameters, one that takes all the required attributes plus the first optional one, another one that takes two optional attributes, and so on ( this is called telescoping constructor pattern).

As developers, we offer a solution for clients to construct objects from the Employee class. But, clients may return with a bunch of questions for us, including:
* Which constructor should I invoke? The one with four parameters or the one with five or six?
* What is the default value for those optional parameters if I don’t pass a value for each?
* If I want to pass values only for mail and phone but not for address, how can I fulfill this requirement?
* What will happen if I mistakenly pass the value intended for the address to mail (compile may not complain about it because they have the same type)?

You might be thinking that the JavaBean pattern could be the second alternative solution to the above questions. In the JavaBeans pattern, we call a no-arg constructor to create an object and then call the setter method on this object to set each required parameter value and each optional parameter of your interest (as shown below). It is no surprise that the JavaBean pattern increases the readability of code and the flexibility of object construction. But, this solution has two big disadvantages: the first one is that the object state will be inconsistent unless all the attributes are set explicitly; the second one is that the JavaBean pattern makes a class mutable and requires extra efforts of developers to ensure thread safety.

https://github.com/Mohsin0568/Algorithms/blob/master/Algorithms/src/com/systa/algo/builder/creational/BuilderPatternDemo.java

## Singleton Pattern:

Singleton pattern as the name suggests is used to create one and only instance of a class. There are several examples where only a single instance of a class should exist and the constraint be enforced. Caches, thread pools, registries are examples of objects that should only have a single instance.

Its trivial to new-up an object of a class but how do we ensure that only one object ever gets created? The answer is to make the constructor private of the class we intend to define as singleton. That way, only the members of the class can access the private constructor and no one else.

Formally the Singleton pattern is defined as ensuring that only a single instance of a class exists and a global point of access to it exists.

https://github.com/Mohsin0568/Algorithms/blob/master/Algorithms/src/com/systa/algo/builder/creational/SingletonPatternDemo.java

## Factory Method Pattern:

A factory produces goods, and a software factory produces objects.

SomeClass someClassObject = new SomeClass();

The problem with the above approach is that the code using the SomeClass's object, suddenly now becomes dependent on the concrete implementation of SomeClass. There's nothing wrong with using new to create objects but it comes with the baggage of tightly coupling our code to the concrete implementation class, which is a violation of code to an interface and not to an implementation.

Formally, the factory method is defined as providing an interface for object creation but delegating the actual instantiation of objects to subclasses.

https://github.com/Mohsin0568/Algorithms/blob/master/Algorithms/src/com/systa/algo/builder/creational/FactoryMethodPatternDemo.java

## Adapter Pattern:

When two heads of states who don't speak a common language meet, usually a language interpreter sits between the two and translates the conversation, thus enabling communication. The Adapter pattern is similar in that it sits between two incompatible classes that otherwise can't work with eachother and lets them work together. Another example to consider is when one buys electronics from USA and tries to use them in India. The two countries have different power voltages being distributed to consumers and using an electronic appliance from one country in another requires a physical adapter which steps up or down the voltage appropriately. The concept of the software adapter pattern is similar.

Formally, the adapter pattern is defined as allowing incompatible classes to work together by converting the interface of one class into another expected by the clients

The Adapter pattern is pretty common in Java code. It’s very often used in systems based on some legacy code. In such cases, Adapters make legacy code work with modern classes.

## Decorator Pattern:

A decoration is added to something to make it more attractive, in the same spirit, the decorator pattern adds new functionality to objects without modifying their defining classes.

The decorator pattern can be thought of as a wrapper or more formally a way to enhance or extend the behavior of an object dynamically. The pattern provides an alternative to subclassing when new functionality is desired.

The strategy is to wrap the existing object within a decorator object that usually implements the same interface as the wrapped object. This allows the decorator to invoke the methods on the wrapped object and then add any additional behavior. Usually, the decorator adds behavior to the existing functionality of the wrapped object i.e. the decorator takes action either before or after invoking some method on the wrapped object.

https://github.com/Mohsin0568/Algorithms/blob/master/Algorithms/src/com/systa/algo/builder/structural/DecoratorPatternDemo.java

## Facade Pattern:

A facade literally means the front of a building or an outward appearance to hide a less pleasant reality. The facade pattern essentially does the same job as the definition of the word facade. Its purpose is to hide the complexity of an interface or a subsystem.

If you take a look around the amenities of current life, almost everything is a facade. When you press a button to turn on the room lights. The button is a facade that hides from you the complexities of electric power generation and distribution and magically lights up your room. The facade makes complex systems easier to use.

Formally the facade pattern is defined as a single user interface to one or more subsystems or interfaces intending to make use of the subsystems easier.

## Proxy Pattern:

The literal definition of proxy is the authority to represent someone else. In a proxy pattern setup, a proxy is responsible for representing another object called the subject in front of clients. The real subject is shielded from interacting directly with the clients. There could be several reasons why one would want to front a subject with a proxy, some are listed below:

* To access remote objects over the internet, running in another JVM or another address space
* To protect a subject from clients not authorized to access it
* To stand in place of an object that may be expensive to create and delay the object's creation till it is accessed
* To cache queries or results from subject for clients
* There are a number of other use cases such as the firewall proxy, synchronization proxy etc.

Formally, the pattern is defined as a mechanism to provide a surrogate or placeholder for another object to control access to it.

* When we want a simplified version of a complex or heavy object. In this case, we may represent it with a skeleton object which loads the original object on demand, also called as lazy initialization. This is known as the Virtual Proxy

* When the original object is present in different address space, and we want to represent it locally. We can create a proxy which does all the necessary boilerplate stuff like creating and maintaining the connection, encoding, decoding, etc., while the client accesses it as it was present in their local address space. This is called the Remote Proxy

* When we want to add a layer of security to the original underlying object to provide controlled access based on access rights of the client. This is called Protection Proxy

https://github.com/Mohsin0568/Algorithms/blob/master/Algorithms/src/com/systa/algo/builder/structural/ProxyPatternDemo.java

## Observer Pattern:

Social media helps us immensely in understanding the observer pattern. If you are registered on Twitter then whenever you follow someone, you are essentially asking Twitter to send you (the observer) tweet updates of the person (the subject) you followed. The pattern consists of two actors, the observer who is interested in the updates and the subject who generates the updates.

A subject can have many observers and is a one to many relationship. However, an observer is free to subscribe to updates from other subjects too. You can subscribe to news feed from a Facebook page, which would be the subject and whenever the page has a new post, the subscriber would see the new post.

The pattern is formally defined as a one to many dependency between objects so that when one object changes state all the dependents are notified.

https://github.com/Mohsin0568/Algorithms/blob/master/Algorithms/src/com/systa/algo/designPatterns/behavioral/ObserverPatternDemo.java

## Iterator Pattern:

Iterate literally means to perform repeatedly. A for loop iterates over an array i.e. it accesses the array repeatedly.

The iterator allows a consumer to go over the elements of a collection without knowing how the collection is implemented. A collection can be a list, array, arraylist, hashmap or any other fancy datastructure. A collection signifies a bunch of objects. It doesn't specify any ordering or properties about the objects it holds. An iterator is formally defined as a pattern that allows traversing the elements of an aggregate or a collection sequentially without exposing the underlying implementation.

The iterator pattern extracts out the responsibility of traversing over an aggregate out of the aggregate's interface and encapsulates it in the iterator class, thereby simplifying the aggregate's interface.

https://github.com/Mohsin0568/Algorithms/blob/master/Algorithms/src/com/systa/algo/designPatterns/behavioral/IteratorPatternDemo.java


