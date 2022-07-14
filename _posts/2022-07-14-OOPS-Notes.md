---
layout: post
title: OOPS Notes
category: Core Subjects
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/07/14/OOPS-Notes/
---

In this blog post I will be sharing all the important topics of required to have a good understanding of OOPS Concept for Technical Interview.

### What is OOPS?

Object-oriented programming is a methodology or paradigm to design a program using classes and objects. It simplifies the software development and maintenance by providing some concepts:

#### Class

Class is user-defined data type which defines its properties and its functions. Class is the logical representation of the data. The class does not occupy any memory space till the time an object is instantiated.

#### Object

When a class is defined no memory is allocated but when it is instantiated, memory is allocated.
- Object is a tun-time entity. An object can operate on both data members and member functions.

*Note* When an object is created **using** *new* keyword, then the space is allocated for the variable in a heap, and the starting address is stored in the stack memory. When an object is created **without** *new* keyword, then space is not allocated in the heap memory, and the object contains the null value in the stack.

### Inheritance

Inheritance is a process in which one object acquires all the properties and behaviors of its parent object automatically. In such a way, you can reuse, extend or modify the attributes and behaviors which are defined in other classes.

In C++, the class which inherits the members of another class is called derived class and the class whose members are inherited is called base class.

Types of Inheritance:
1. Single Inheritance: When one class inherits another class, it is known as single level inheritance.
2. Multiple Inheritance: Multiple inheritance is the process of deriving a new class that inherits the attributes from two or more classes.
3. Multilevel Inheritance: Multilevel inheritance is a process of deriving a class from another derived class.
4. Hierarchical Inheritance: Hierarchical inheritance is defined as the process of deriving more than one class from a base class.
5. Hybrid Inheritance: Hybrid Inheritance is a combination of simple, multiple inheritance and hierarchical Inheritance.

### Encapsulation

Encapsulation is the process of combining data and functions into a single unit called class. In Encapsulation, the data is not accessed directly; it is accessed through the functions present inside the class. In simpler words, attributes of the class are kept private and public getter and setter methods
are provided to manipulate these attributes. Thus, encapsulation makes the concept of data hiding possible.

### Abstraction

Abstraction means displayinng only essential information and hiding the details.
- Abstraction using classes.
- Abstraction using header files.


*Dynamic Binding*: In Dynamic Binding, the code to be executed in response to function call is decided at run time.

### Polymorphism

Polymorphism is defined as the ability of a message to be displayed in more than one form.

#### Types of Polymorphism
1.  Compile Time Polymorphism(Static): The polymorphism which is implemented at the compile time is known as compile-time polymorphism. Example- Method Overloading.

*Method Overloading*: : Method overloading is a technique which allows you to have more than one function with the same function name but with different functionality. Method overloading can be possible on the following basis:
1. The return type of the overloaded function.
2. The type of the parameters passed to the function.
3. The number of parameters passed to the function.

2. Runtime Polymorphism(Dynamic): Runtime polymorphism is also known as dynamic polymorphism. Function overriding is an example of runtime polymorphism. Function overriding means when the child class contains the method which is already present in the parent class. Hence, the child class overrides the method of the parent class. In case of function overriding, parent and child classes both contain the same function with a different definition. The call to the function is determined at runtime is
known as runtime polymorphism.

### Constructor

Constructor is a method which is invoked automatically at the time of object creation. It is used to initialize the data members of new object generally.
It has the same name as the class itself. They do not have any return type.

#### Types of Constructor

1. Default constructor: Aconstructor which has no argument is known as default constructor. It is invoked at the time of creating an object.
2. Parameterized constructor: Constructor which has parameters is called a parameterized constructor. It is used to provide
different values to distinct objects.
3. Copy Constructor: A Copy constructor is an overloaded
constructor used to declare and initialize an object from another object. It is of two types - default copy constructor and user defined copy constructor.

### Destructor

Adestructor works opposite to constructor; it destructs the
objects of classes. It can be defined only once in a class.
A derived class destructor will be invoked first, the the base class destructor will be invoked.

*'this' Ponter*: **this** s is a keyword that refers to the current instance of the class. There can be 3 main uses of 'this' keyword:
1. It can be used to pass the current object as a parameter to
another method
2. It can be used to refer to the current class instance variable.
3. It can be used to declare indexers.

### Acess Modifier

1. Public: Can be accessed by any class.
2. Private: Can be accessed only by a function in a class(inaccessible outside the class).
3. Protected: It is also inaccessible outside the function but can be accessed by subclass or that class.

### Friend Function

Friend function acts as a friend of the class. It can access
the private and protected members of the class. The friend function is not a member of the class, but it must be listed in the class definition. The
non-member function cannot access the private data of the class.
Sometimes, it is necessary for the non-member function to access the data. The friend function is a non-member function and has the ability to access the private data of the class.
*Note*:
1. Afriend function cannot access the private members directly, it has
to use an object name and dot operator with each member name.
2. Friend function uses objects as arguments.

### Aggregation

It is a process in which one class defines another class as any entity reference. It is another way to reuse the class. It is a form of association that represents the HAS-A relationship.

### Virtual Function *imp*

A virtual function is a memeber function which is declared within a base class and redefined(overridden) by derived class. Functions are declared with virtual keyword in base class. When we use the same function name in both base and derived class, the function in base class is declared with a keyword virtual.

When the function is made virtual, then C++ determines at run-time which function is to be called based on the type of the object pointed by the base class pointer. Thus, by making the base class pointer to point to different objects, we can execute different versions of the virtual functions.

1. Virtual functions cannot be static.
2. Aclass may have a virtual destructor but it cannot have a virtual constructor.

### Pure Virtual Function

1. A pure virtual function is not used for performing any task. It only serves as a placeholder.
2. A pure virtual function is a function declared in the base class that has no definition relative to the base class.
3. Aclass containing the pure virtual function cannot be used to declare the objects of its own, such classes are known as abstract base classes.
4. The main objective of the base class is to provide the traits to the derived classes and to create the base pointer used for achieving the runtime polymorphism.

### Inline Function

Inline is a request not command. It is a function that is expanded in line when it is called. When the inline fuction is called, whole code gets inserted pr substituted at the point of in function call.

*Function Overloading*: It is a feature in C++ where two or more functions can have same name but different parameters.

### Abstract Class

In C++ class is made abstract by declaring at least one of
its functions as a pure virtual function. A pure virtual function is specified by placing "= 0" in its declaration. Its implementation must be provided by derived classes.

### Acess Specifier *imp*

The access specifiers are used to define how functions
and variables can be accessed outside the class. 
There are three types of access specifiers:
1. Private: Functions and variables declared as private can be accessed only within the same class, and they cannot be accessed outside the class they are declared.
2. Public: Functions and variables declared under public can be accessed from anywhere.
3. Protected: Functions and variables declared as protected cannot be accessed outside the class except a child class. This specifier is generally used in inheritance.
