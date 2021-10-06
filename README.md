# Inheritance-Polymorphism-and-Interfaces-String-Handling

Object-Oriented Programming or OOPs refers to languages that uses objects in programming. Object-oriented programming aims to implement real-world entities like inheritance, hiding, polymorphism etc in programming. The main aim of OOP is to bind together the data and the functions that operate on them so that no other part of the code can access this data except that function. 

• Inheritance in Java
Inheritance in java is one of the core concepts of Object-Oriented Programming. Java Inheritance is used when we have is-a relationship between objects. Inheritance in Java is implemented using extends keyword.

Java Inheritance Test Program
Let’s write a simple test class to create a Cat object and use some of its methods.

package com.journaldev.inheritance;

public class AnimalInheritanceTest {

	public static void main(String[] args) {
		Cat cat = new Cat(false, "milk", 4, "black");

		System.out.println("Cat is Vegetarian?" + cat.isVegetarian());
		System.out.println("Cat eats " + cat.getEats());
		System.out.println("Cat has " + cat.getNoOfLegs() + " legs.");
		System.out.println("Cat color is " + cat.getColor());
	}

}

Output:►
Cat is Vegetarian?false
Cat eats milk
Cat has 4 legs.
Cat color is black


►Important Points
Code reuse is the most important benefit of inheritance because subclasses inherits the variables and methods of superclass. 

Private members of superclass are not directly accessible to subclass. As in this example, Animal variable noOfLegs is not accessible to Cat class but it can be indirectly accessible via getter and setter methods.

Superclass members with default access is accessible to subclass ONLY if they are in same package.

Superclass constructors are not inherited by subclass.

If superclass doesn’t have default constructor, then subclass also needs to have an explicit constructor defined. Else it will throw compile time exception. In the subclass constructor, call to superclass constructor is mandatory in this case and it should be the first statement in the subclass constructor.

Java doesn’t support multiple inheritance, a subclass can extends only one class. Animal class is implicitly extending Object class and Cat is extending Animal class but due to java inheritance transitive nature, Cat class also extends Object class.

• Polymorphism in Java
The word polymorphism means having many forms. In simple words, we can define polymorphism as the ability of a message to be displayed in more than one form.

Real life example of polymorphism: A person at the same time can have different characteristic. Like a man at the same time is a father, a husband, an employee. So the same person posses different behavior in different situations. This is called polymorphism.

Polymorphism is considered one of the important features of Object-Oriented Programming. Polymorphism allows us to perform a single action in different ways. In other words, polymorphism allows you to define one interface and have multiple implementations. The word “poly” means many and “morphs” means forms, So it means many forms.
It refers to the ability of OOPs programming languages to differentiate between entities with the same name efficiently. This is done by Java with the help of the signature and declaration of these entities. 

In Java polymorphism is mainly divided into two types:

►Compile time Polymorphism
►Runtime Polymorphism

1. Compile-time polymorphism: It is also known as static polymorphism. This type of polymorphism is achieved by function overloading or operator overloading. But Java doesn’t support the Operator Overloading.

Method Overloading: When there are multiple functions with same name but different parameters then these functions are said to be overloaded. Functions can be overloaded by change in number of arguments or/and change in type of arguments.
Example: By using different types of arguments.

2. Runtime polymorphism: It is also known as Dynamic Method Dispatch. It is a process in which a function call to the overridden method is resolved at Runtime. This type of polymorphism is achieved by Method Overriding.

Method overriding, on the other hand, occurs when a derived class has a definition for one of the member functions of the base class. That base function is said to be overridden.

• Interface in Java
Interface in java provide a way to achieve abstraction. Java interface is also used to define the contract for the subclasses to implement.

For example, let’s say we want to create a drawing consists of multiple shapes. Here we can create an interface Shape and define all the methods that different types of Shape objects will implement. For simplicity purpose, we can keep only two methods – draw() to draw the shape and getArea() that will return the area of the shape.

Interface provides absolute abstraction, in last post we learned about abstract classes in java to provide abstraction but abstract classes can have method implementations but interface can’t.

Interfaces can’t have constructors because we can’t instantiate them and interfaces can’t have a method with body.

By default any attribute of interface is public, static and final, so we don’t need to provide access modifiers to the attributes but if we do, compiler doesn’t complain about it either.

By default interface methods are implicitly abstract and public, it makes total sense because the method don’t have body and so that subclasses can provide the method implementation.

An interface can’t extend any class but it can extend another interface. public interface Shape extends Cloneable{} is an example of an interface extending another interface. Actually java provides multiple inheritance in interfaces, what is means is that an interface can extend multiple interfaces.

• Strings in Java
Strings in Java are Objects that are backed internally by a char array. Since arrays are immutable(cannot grow), Strings are immutable as well. Whenever a change to a String is made, an entirely new String is created. 

Syntax:  

<String_Type> <string_variable> = "<sequence_of_string>"; 

Memory allotment of String

Whenever a String Object is created as a literal, the object will be created in String constant pool. This allows JVM to optimize the initialization of String literal.

For example: 

String str = "Anywhere";
The string can also be declared using new operator i.e. dynamically allocated. In case of String are dynamically allocated they are assigned a new memory location in heap. This string will not be added to String constant pool.

For example: 

String str = new String("Anywhere");

Interfaces and Classes in Strings in Java

►CharBuffer: This class implements the CharSequence interface. This class is used to allow character buffers to be used in place of CharSequences. An example of such usage is the regular-expression package java.util.regex.
 
►String: String is a sequence of characters. In java, objects of String are immutable which means a constant and cannot be changed once created.

►StringBuffer: 
StringBuffer is a peer class of String that provides much of the functionality of strings. The string represents fixed-length, immutable character sequences while StringBuffer represents growable and writable character sequences.
Syntax:
StringBuffer s = new StringBuffer("Anywhere");

►StringBuilder: 
The StringBuilder in Java represents a mutable sequence of characters. Since the String Class in Java creates an immutable sequence of characters, the StringBuilder class provides an alternate to String Class, as it creates a mutable sequence of characters.
Syntax:
StringBuilder str = new StringBuilder();
str.append("GFG");

►StringTokenizer: 
StringTokenizer class in Java is used to break a string into tokens. 

►StringJoiner: 
StringJoiner is a class in java.util package which is used to construct a sequence of characters(strings) separated by a delimiter and optionally starting with a supplied prefix and ending with a supplied suffix. Though this can also be with the help of StringBuilder class to append delimiter after each string, StringJoiner provides an easy way to do that without much code to write.
