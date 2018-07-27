---
title: 'Day 4 - Class methods, instance methods and static methods'
date: 2018-07-26
permalink: /posts/2018/07/coding-challenge-day-4/
tags:
  - python
  - coding
  - object_orientation
  - class_methods
  - instance_methods
  - static_methods
---

Today, I added two new classes to the Harry Potter universe - one for creating professors, the other for creating ghosts. Also, I implemented a few **class methods** to use them as alternative constructors.

### Types of methods
A class can have three types of methods: instance methods, class methods and static methods.
   
**Instance methods** are the most common type of method. They take at least the parameter *self* as an input. This parameter points towards an instance of the class when the method is called. An instance method can modify both *object state* and *class state* (the latter can be modified through ```self.__class_```_)
   
**Class methods** take at least the parameter *cls* as an input. *cls* points towards the *class* - not a particular object instance - when the method is called. Therefore, a class method can only modify *class state* but not *object state*. Still, changing the class state will still affect all instances of the class. 
   
**Static methods** take neither a *self* nor *cls* parameter as an input. Therefore, they cannot modify neither object state nor class state. Although they are related to the class, they are independent of the other class or instance methods and can only access the data they are provided with.
   
Class and static methods allow a developer to communicate what intention she/he had in mind when implementing the method. For example, using a static method expresses that the method is independent from everything else around it. Also, class methods can be used as **alternative constructors **.   
   
### Class methods as alternative constructors   
   
- In Python a class can only have one constructor (the ```self.__init__()``` method)
- However, we can use ```@classmethod``` to create factory functions
- These factory functions allow us to create class objects that are configured exactly the way we want them
- In this way, they act like additional constructors
   
For example, we probably want to create the main characters of the Harry Potter world. Typing all the names and other attributes every time would be very slow. Adding a few class methods allows us to speed up the process. We can create a Harry constructor as follows:
   
```
@classmethod
def harry(cls):
    return cls('Harry James Potter', 1980, 'male', 'Griffindor', start_year=1991, pet=('Hedwig', 'owl'))
```
