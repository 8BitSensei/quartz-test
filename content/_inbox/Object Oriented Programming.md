2023-12-05
Tags: #programming #OOP

In modern OOP thinking there are considered to be four main pillars

**Abstraction**
Most of the time, are objects in OOP represent real-world objects, this is an inheritance of it's history as a paradigm to bring the way we code closer to the way we think about the world (e.g. sketchpad using objects as shapes, all smalltalk and constructionist learning). But, we never represent eh original object with 100% accuracy, this would be pointless, we abstract it to make it more useful to us, we only model the attributes and behaviours we need for the given context.

In fact we can probably categorise objects by their origins, either as real objects or irreal objects, that is we have real objects, which are abstractions of *real things* in the material world e.g. user, airplane, coffee, and we have irreal objects which do not represent anything in the material world, or maybe I should say anything outside of the code world e.g. HttpClient, AuthenticationRequest, JsonElement. It's fair to say that these latter objects are not abstracted at all.

**Encapsulation**
Encapsulation is the practice of *hiding* the details of an objects inner workings away from anything communicating with or using the object, exposing only a limited interface to the rest of the program. In most languages there are levels of encapsulation, e.g. in c# we have the accessibility modifiers `protected internal`, `protected`, `internal`, `private protected`, and `private`, all of which offer some degree of encapsulation.
![[Pasted image 20231207165634.png]]
The benefits of encapsulation is first, that the simplify code for the programmer, you are not forced to know the inner workings of every object you use, and in fact, by working with an interface we can change the implementation behind the scenes without forcing calling code to change.

**Polymorphism**
Polymorphism, loosely, is the ability to modify inherited methods. In c# we can allow this by adding the `virtual` keyword to a method in a parent class, and then in a child class declaring the same method signature with the `override` key word, this means that the method in the child class will be called, instead of defaulting to the parent method.  

We can go further and declare an `abstract` method in the parent class, this means that we don't have to declare a method body, but any child classes *have to* declare a unique body. Adding the `abstract` keyword to a class means that it cannot be instantiated as an object, only be used as a parent.

At this point, an abstract class and an interface are very similar, what's the point in using one over the other? Well, if you use an abstract class, you can *also add concrete methods*, if you want to force your child objects to implement their own methods you can, if you have some code that can be shared, you can do that too, and save yourself some time! The down-side is that a class can only ever have one parent class, but can have many interfaces, but an interface can't declare a concrete method, so it's a trade off depending on how you intend to structure your objects.

The reason C# doesn't allow multiple inheritance, is because we might hit ambiguous calls e.g if two parent classes have methods with the same name; however, C# deals with this in other scenarios such as libraries, or even interfaces, so this doesn't really hold up, it could have been a bigger deal back in the day? But instead now we have to manage interfaces as well as inheritance, adding complexity. 

**Inheritance**
Inheritance is the ability to build a class on top of an existing class in a parent child type relationship, the child class inherits all properties and methods from the parent, and thus has at least the same interface as their parent class. This allows us to save time by duplicating code across objects, and with polymorphism, these methods can be modified for their new context while preserving the interface.

Usually, there can only be one parent class for a child.
#### History

>“Object-Oriented Programming” (OOP) was coined by Alan Kay circa 1966 or 1967 while he was at grad school. [^1]

Ivan Sutherland's sketchpad thesis has 'masters' which represent an early form of inheritance, it's also part of an early attempt at graphical communication with computers, rather than through semantic commands.

Produced several facilities:
- sub-picture - including arbitrary symbols on a drawing
- constraints - for relating the parts of a drawing in a commutable way
- definition copying - for building complex relationships from combinations of atomic restraints

> the Sketchpad drawing itself is entirely different from the trail of carbon left on a piece of paper. Information about how the drawing is tied together is stored in the computer as well as the information which gives the drawing its particular appearance. 

> For Highly Repetitive Drawings: 
> The ability of the computer to reproduce any drawn symbol anywhere at the press of a button, and to recursively include subpictures within subpictures makes it easy to produce drawings which are composed of huge numbers of parts all similar in shape. Great interest in doing this comes from people in such fields as memory development and micro logic where vast numbers of elements are to be generated at once through photographic processes. Master drawings of the repetitive patterns necessary can be easily drawn. Here again, the ability to change the individual element of the repetitive structure and have the change at once brought into all sub-elements makes it possible to change the elements of an array without redrawing the entire array.

> If the master hexagon is changed, the entire appearance of the hexagonal pattern will be changed. 

[[Simula programming language]] one of the first true OOP languages, before the term was coined, was designed for simulating systems

Alan Kay coined the term OOP in 1966 or 67. The idea was to encapsulate 'objects' in software which could then communicate by passing messages around rather than direct data sharing, Simula 67, created around the same time included objects, classes, inheritance, subclasses, and virtual procedures; meaning these features are at the core of OOP.

![[Pasted image 20231205205943.png]]

> “The basic principal of recursive design is to make the parts have the same power as the whole.” ~ Bob Barton

Alan Kay, among others created the language Smalltalk, another one of the early OOP languages (which amazingly enough didn't include sub-classes until 1976). Smalltalk is sometimes considered the platonic form of OOP, Kay never lied out a definition of OOP, and given that he is considered the 'father of OOP', Smalltalk is what all OOP languages are compared to.

Smalltalk was actually created as an educational tool for a method called [[Construtionist learning]], which along with Sketchpad, pushes the idea that OOP is kind of a naturally occurring paradigm when we're trying to bring the model of our code closer to the model of the world they're trying to represent.

> **Constructionist learning** is the creation by learners of [mental models](https://en.wikipedia.org/wiki/Mental_model "Mental model") to understand the world around them. Constructionism advocates student-centered, [discovery learning](https://en.wikipedia.org/wiki/Discovery_learning "Discovery learning") where students use what they already know, to acquire more knowledge.

Alan Kay thinks the industry focuses too much on inheritance, the main idea of OOP is encapsulation and messaging between objects

> OOP to me means only messaging, local retention and protection and hiding of state-process, and extreme late-binding of all things. [^3]

According to Alan Kay the original conception had the following parts:
- Objects are like cells, in that they are **encapsulated** and only able to communicate by **messaging** each other
- To get rid of data, the whole cell metaphor would get rid of data (I don't follow this)
- Generic behaviour, each object could have several *algebras*, and there could be families of this (the term polymorphism for this comes about later, coined by Peter Wegener)
- Kay didn't like inheritance in Simula, so this was to be left out until he understood it better

Obviously Kay isn't the God of OOP, inheritance would go on to be a defining feature, and most OOP languages today are not not pure OOP, they often have many functional features.

[^1]: https://medium.com/javascript-scene/the-forgotten-history-of-oop-88d71b9b2d9f
[^2]: https://dspace.mit.edu/handle/1721.1/14979
[^3]: https://userpage.fu-berlin.de/~ram/pub/pub_jf47ht81Ht/doc_kay_oop_en