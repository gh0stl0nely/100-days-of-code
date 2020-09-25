# 100 Days Of Code - Log

### Day : , 2020

**Today's Progress**: 

**Thoughts:**:

### Day 1: September 14, 2020

**Today's Progress**: Created a git workflow guide on the Github repo for our website for Git Best Practice. Worked on some more React, Material UI and SVG for Civic Tech Toronto Website. Practiced splitting code into folders for better organization and maintainence.

**Thoughts:** Knowing Git is a must for every developer. Just by creating a git workflow by typing it into a list of steps got me thinking hard about what each step of the workflow will do and what to watch out for. Although I am not a fan of writing CSS, I forced myself to polish my CSS and React skill using Material UI to guarantee mobile responsiveness. I also reorganized the folders to make sure all files are well-organized and clean.

### Day 2: September 15, 2020

**Today's Progress**: More and more CSS and React!

**Thoughts:** Never know whether or not I will get over the fear of CSS... It's nightmarish to think of CSS, but you gotta do what you gotta do! Go, Khoi!

### Day 3: September 16, 2020

**Today's Progress**: More intense CSS, a bit of git (read up about `git rebase`). Basically rebasing is quite similar to merge. Rebasing puts all the commit history of a source branch onto a "target" branch and "linearize the entire commit history".. Right now I don't have practical knowledge of what rebasing does yet, but it seems the biggest benefit is to have one linear commit history, which is pretty neat :) as opposed to merge. One thing to keep in mind is ONLY to perform rebase on a private branch that no one but you use.

**Thoughts:** CSS is another monster in of itself... enuff said. Hopefully one day I can get to fully grasph the concept of rebase. 

### Day 4: September 17, 2020

**Today's Progress**: Switched over to Java for a bit. Learned about type narrowing and widening, 'char' type representing unicode value (char 'i' => unicode value is 49). FINAL keyword 
`final` => Final class cannot be inherited, final variable cannot be reassigned, final method cannot be overriden. ** final ** does not need to be initialized (if it is pointing to null, you can still reassign it) => `final int thisIsNull;` => `thisIsNull = 3` => `Correct`

1) Another important thing to note is when passed to a method, primitive is passed by VALUE. That means that if you do this
` static void add(int x) {
  x++;
}` 
`main(){
  int x = 10;
  add(x) => This will log out 10 still because you are only passing a COPY of x and not X itself => This is passed by VALUE
}`

Passed by reference is the opposite. Passing an Object into a method will pass the the `REFERENCE` of that object to a method. Therefore changing its property within the method is gucci. 

=> Lesson: Passing primitive data type to method => You get a copy. Passing reference object to a method, you get that exact reference of that object. 

2) Enum type => This basically create a "static" `list` of static FINAL field. 
`public enum DayOfWeek {
  Sunday, Monday, etc... Saturday
}` 
=> You can use DayOfWeek.Saturday :) Read more details here https://codegym.cc/groups/posts/154-how-to-use-the-enum-class

3) Wrapper class => A class that stores primitive INTERNALLY (i.e: Integer, Float, Long). Remember, primitive don't have method but wrapper class does 
=> Integer.toString() YES , int.toString() => NOPE

4) Autoboxing vs Unboxing
int a = 10;
Integer b = 1;
a = b  => unboxing // Basically b is a wrapper class that contains primitive 1, but we assign it to a which is already a primitive. Unboxing is like opening a wrapper and assign. 
b = a * 10; => autoboxing //  
=> a wrapper variable can be assigned a primitive value. This process is called AUTOBOXING. => Cuz it already knows int is primitive type represented by Integer class
=> Similarly, a primitive variable can be assigned a wrapper object. This process is called UNBOXING.
Read more: https://codegym.cc/groups/posts/32-wrappers-unboxing-and-boxing

**Thoughts:** Learned a whole lot about Java syntax! But its just a beginning!

### Day 5: September 18, 2020

**Today's Progress**: More practicing with type conversion, initializing variables, throwing and handling exception in Java.
 
**Thoughts:** Coding in both Javascript and Java makes you appreciate Javascript more as it is a weakly typed language. Java is strongly typed, thus safer. In term of best practice, Java certainly takes the upper hand. 

### Day 6: September 19, 2020

**Today's Progress**: Refreshed myself with 4 core concepts of OOP
1) Abstraction: Splits the program into smaller parts. We should not have one giant monolithic application because that is not maintainable. 

2) Encapsulation: Interaction between 2 classes should be made using methods. One class should NOT be able to access private data of other class WIHOUT a valid method. Simple speaking, we HIDE our own data from the outside world and they can only interact with our data using specific allowed methods. 

3) Inheritance: This allows for code useability. 10 `similar` child classes can extends/ inherits from a parent class without having to rewrite all the code and method. This can be done via class extension.  

4) Polymorphism: Connected to inheritance in a way that two different child classes that extend one same parent class can have their own implementation of methods. For example
`public class Shape {
  calculateArea(){}
}
 public class Square extends Shape {
  @override 
  calculateArea(int side{
    return side * side;
  }
  
  public class Rectangle extends Shape {
  @override 
  calculateArea(int left, int right){
    return left * right;
  }
 }
` 
In addition to 4 pillars of OOP, I was introduced to the idea of `Aggregation and Composition`. 
=> Aggregation is when two objects have NOT AS STRICT relationship (i.e: Car and Passenger => Car does not Passenger to function. The Passenger class can interact with other object)
=> Composition is when two objects have STRICT relationship (i.e: Car and Engine => Car OWNS and NEEDS an Engine to work. The Engine cannot interact with other things but Car, meaning Car only has ONE ENGINE) 

**Link**: This is a link for Type Casting for class https://codegym.cc/quests/lectures/questcore.level02.lecture01

**Thoughts:** Another day of learning Java. I love it! OOP is definitely a concept that every developer should know to become a better programmer. Mastering such concept will not only allow one to write cleaner code, but also let one to think about how to design great softwares. 

### Day 7: September 20, 2020

**Today's Progress**: Learned about early binding and late binding
1) Early binding: Example of this is static method. Static method is defined at `COMPILED TIME`
2) Late binding: Example of this is instance (non-static) method. When you override a NON-STATIC method, it will be ran at `RUN TIME`. 
An advantage of late binding is that at run-time a method can be used on different type of objects, but it will be SLOWER because it is executed at RUN-TIME.

- Additional lesson is learned on the topic of objec narrowing/widening
=> Animal pet = new Pet(); => This is WIDENING. 
=> WildAnimal wildAnimal = new Coyote();
  Coyote coyote = (Coyote) wildAnimal; // This is Narrowing (from WildAnimal to Coyote)
=> Pet pet = new Animal(); // Error! // This is Error! Because Animal is a parent class but you reference it using a child class that parent class DOES NOT know about
`Make sure WE DON'T confuse between type casting VS wrongly reference (Object of parent class being referenced by a child class)`

- In addition, we learned about `ABSTRACT CLASS`. There are fews characteristics of an ABSTRACT class.
`public abstract class ObjectA{
  Object A = new ObjectA(); => ERRORRRR!!!! 3)

  public static abstract void getA(){
    // NO IMPLEMENTATION !!!  1) and 2)
  }
}`

1) Marked with word `abstract`
2) Declare method WITHOUT implementing it
3) Cannot create an object out of ABSTRACT class
4) ALL METHODS that are inherited from a ABSTRACT CLASS **MUST BE** implemented. Otherwise, the child class must also be considered as **ABSTRACT** class. These are good restrictions though :) We don't want every child class to just extends the parent class without any restriction. 

- Jumping ahead! I got a headstart with Interface today. Interface is like Abstract class.

`interface Drawable {
  void draw();
}`
1) Interface can only EXTENDS **MULTIPLE** Interfaces
2) Classes can IMPLEMENTS **MULTIPLE** interfaces

Some important advantages of Interface:
1) Multiple inheritance (with interface)
2) Separate method definition vs method implementation (interface does not implement any methods but its child class that implements it will do it.

Interface represents more of ABILITIES (in term of method) than the object itself. You don't really say `Car as a class but Drivable as a Interface`

** Links**: https://codegym.cc/groups/posts/106-widening-and-narrowing-of-reference-types

https://codegym.cc/quests/lectures/questcore.level02.lecture08 - Thinking about Interface

**Thoughts:** Making more progress with Java! Happy :)

### Day 8: September 23, 2020

**Today's Progress**: More CSS.

**Thoughts:**: Just tweaking things. My CSS skill is getting a bit better?

### Day 9: September 24, 2020

**Today's Progress**: Completed my tasks assigned by the volunteer group.Took 2 hours on CSS, learned about breakpoints in Material UI to manipulate responsiveness. Shifted gear back to Java to learn more about the difference Interface, Abstract Class and normal classes.
- Interface provides `LOOSE COUPLING CODE`. 
- Interface does NOT have `STATE` but ONLY BEHAVOIUR while Abstract Classes `DO BOTH`
- Interface describes BEHAVIOUR so many **UNRELATED CLASSES** can implement it. Abstract Classes are like a blueprint and only a parent of **RELATED CLASSES**
- Multiple inheritance only apply to interface not classes.

*** WHEN INHERTING A PARENT CLASS, THE SUBCLASS CAN ACCESS THE FIELDS DIRECTLY!! ***

**Thoughts:**: Not a bad day, actually spend more time than I expected on CSS. 

### Day 10: September 25, 2020

**Today's Progress**: 

**Thoughts:**:
