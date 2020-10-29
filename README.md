
Open Source Project: https://codegym.cc/groups/posts/383-top-8-open-source-github-projects-to-level-up-your-coding?utm_source=eSputnik-$email-digest-36&utm_medium=email&utm_campaign=$email-digest-36&utm_content=868856112

Interpreter (line by line but slow) vs Compiler (everything to machine code, faster but uncaught)  (READ UP!)

Important dates: 
1) Git concepts: on Day 11, September 26, 2020. 
2) To do when have time https://codegym.cc/quests/lectures/questcore.level05.lecture12 - Request parser
- https://codegym.cc/quests/lectures/questcore.level07.lecture10 - List implementation 
3) Java execution process:
- Source code (file.java) -> Java compiler (javac) -> Byte code (file.class) -> in (JVM now) Class loader -> Byte verifier -> (JRE now) Interpreter or JIT compiler -> Convert to Machine code.
Terminology:
4) Interesting problem about UncaughtExceptionHandler: https://codegym.cc/quests/lectures/questcore.level06.lecture13 (Last exercise) + https://medium.com/@yosimizrachi/advanced-exception-handling-thread-uncaughtexceptionhandler-c72e013da092 - Look at October 12 for some explanation
5) Volatile vs Synchronized https://stackoverflow.com/questions/3519664/difference-between-volatile-and-synchronized-in-java
 - Thread safe => i) Memory visibility and ii) execution control
6) Static block only runs once when it is loaded by ClassLoader. Read this for information on locking the Class so that it only initialized once! https://codegym.cc/help/1314#discussion
7) Computer has memory that stores data and codes. The PROCESSOR (CPU or central processing unit) is the one that executes these codes, grab data from memory to read and write it back to memory. To spreap up computation, the process uses cache or CPU cache where it stores most of its most used variables.  https://codegym.cc/quests/lectures/questcore.level07.lecture05
8) Object-level lock and Class-level lock:
=> 1) Object level lock: So remember that each object has a **LOCK** or **MUTEX**, if the thread wants to access this object, it needs to obtain the lock of that object.  
=> 2) Class level lock: If a thread wants to execute **STATIC** method, it needs to acquire CLASS LEVEL LOCK. But once thread acquires the class level block, it can execute **ANY** static SYNCHRONIZED methods 
https://www.tutorialspoint.com/object-level-lock-vs-class-level-lock-in-java#:~:text=Every%20class%20in%20Java%20has,synchronized%20method%20of%20that%20class.
9) How does computer work under the hood ? (Signal from mouth click -> I/O sub system -> CPU -> Fetch instruction from memory -> Execute) https://codegym.cc/quests/lectures/questcore.level07.lecture09
10) Why is HashMap **NOT** thread-safe? Remember, HashMap uses a dynamic array under the hood and uses hash function given the key to find the index inside that dynamic array that stores the value. Whenever a new item is added (put) onto the hashmap, the internal array may call `array.resize()`. But if there are multiple threads accessing the same hash map, the array may be under going **resizing**, so the new array is practically EMPTY and so calling get() will return null => **THREAD UNSAFE**

----------
- Multithreading:
- Deadlock
- Early bindng vs Late binding: Early binding guarantees function can be executed at compile time (i.e: Overloadded function call, static block calls ?), Late binding executes at run-time.
------------
Patterns learned so far:
- Singleton - To return the same object, you can do a null check => If the only Instance is null, then you can initialized it and return, but if not, then just return that only instance that has already been initialized. 
- Template 
- Factory 
------------------------------------------------------------------------------------------------------------------------------------------------------------------------

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

**Today's Progress**: More CSS and learning about Git concepts.

**Thoughts:** My git knowledge is getting stronger wohahaha

------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Day 11: September 26, 2020

**Today's Progress**: Review some Git Concept
- Git rebase: when you checkout a branch and rebase another branch (`git checkout khoi, git rebase master`), this means you are putting all changes from `master` onto `khoi` in a linear manner. Then you `git checkout master, git rebase khoi` , this will again updates master up-to-date with khoi.

- HEAD: A HEAD points to a most recent commit. You can checkout a commit `git checkout commit1` or a branch `git checkout branch-khoi`. Detaching head basically means putting head at a different location (most likely a previous commit or branch)

- Relative refs and `^` operator: When you want to reference a commit, you refer to it with a hash `fed12390218309128390` , very long but Git can accept `fed12` as a hash also (Smart guy!)
** You can move up a COMMIT by `^` 
** You can move up **SEVERAL** commits by `~<num>`

For instance, `git checkout master^` => ** This comment is to find the parent of the master branch, BASICALLY GO BACK A COMMIT from the current commit ** 
or more specifically `git checkout HEAD^` => Go back to one commit BEFORE HEAD! ( A PREVIOUS COMMIT BEFORE THE **CURRENT COMMIT (HEAD)** WE ARE ONE)

You can also do this `git checkout (COMMIT HASH)^` => This will go to that commit using the hash and jump backward by one commit! 

- The `~` operator: Like `^` but instead of go backward by one commit, you can go back by several commits :) 

Exercise: Guess what does this do : `git branch -f master HEAD~4` ? => Answer: Force master branch to go back to 4 commits before current commit (HEAD). 

- `git reset` vs `git revert`: Mostly similar for REWRITING HISTORY, but RESET works for local branch where as REVERT works for remote branch.

** `git reset (Commit)^ or ~` **: So `git reset HEAD~4` meaning on your CURRENT BRANCH, it will go all the way back to 4 commits before HEAD. Remember, once you reset, the commits will that you made so far will ** BEGONE ** => VERY DANGEROUS (git reset (commit hash)~2 is going back to 2 commits before that commit with that hash 

** `git revert HEAD` ** : This commands mean that on the current **REMOTE* branch, Git revert also takes a specified commit, however, `git revert` does not move ref pointers to this commit. A revert operation will take the specified commit, inverse the changes from that commit, and create a new "revert commit. Instead of deleting or orphaning commits in the commit history, a revert will create a new commit that inverses the changes specified. Git revert is a safer alternative to git reset in regards to losing work

- `git cherry-pick <CommitHash1> <commithash2> ...`: This is quite similar to rebase (a SELECTIVE rebase so to speak), but few differences:
=> You are perfomring cherry picking from your current branch (meaning `git cherry-pick C1 C2` and you are on `khoi` branch, then C1 and C2 (commits) will be rebased (linearly added) onto khoi branch whereas rebase will be performed from another branch that you want to rebase onto (`git checkout master, git rebase khoi` => Adding master changes into khoi.

- ** Interactive rebase ** - `git rebase -i master`: CherryPicking works pretty well **IF YOU KNOW THE COMMIT HASHES TO ADD ONTO THE BRANCH**, but without the, we need INTERACTIVE REBASE. 
=> When performing interactive rebase, a UI will open in code editor to showcase the list of commit messages and hashes that are about to be copied onto the target branch.
** IMPORTANT **: Remember that when choosing which commits to rebase, you can also CHOOSE THE ORDER THAT EACH COMMITS WILL BE PLACED ON THE BRANCH AND WHICH COMMITS TO OMIT.

- `git tag <Tagname> <Commit hash>` : This applies a tag name to a specific commit

- `git describe <ref>` : Ref is anything can be resolved into a commit. If left blank it will defualt to HEAD. By applying this command, the output is `<tag>_<numbCommit>_g<hash>
=> Where`tag` is the closest ancestor tag in history, `numCommits` is how many commits away that tag is, and `hash` is the hash of the commit being described.

- Some shortcuts for pulling  => `git pull --rebase` => This will fetch the remote of that branch, and rebase our local branch on top of that remote branch (so basically you rebase origion/<local_branch> :) => So technically merge/rebase technically updates **THE CURRENT BRANCH THAT YOU ARE ON** with the changes of the branch you are combining with !!! 

- `git branch -u  o/master(remote branch) <localName>` : This commands set the **EXISTING Local Branch** to track remote master branch (SO WHENEVER YOU PUSH FROM LOCAL, you will push to remote master on that Local Branch

- `git checkout -b <local_Branch> origin/master`: This commands is same as the above but it will create a branch and set its remote tracking to origin/master

- `git push origin <source>:<destination>`: Push from the local branch to another remote branch in origin. `git push origin khoi:demi` => Push changes from khoi branch to demi remote branch. 

Note: `git push origin :foo` => This will delete the remote foo... be careful though
`git fetch origin :foo` => This will create another LOCAL branch called "foo" @@  

- `git fetch origin <remote_source>:<local_branch>`: Fetch and combine changes from a remote branch to a local branch (if not existed). **NOTE** THIS DOES NOTT AFFECT THE CURRENTLY CHECKED OUT BRANCH.

- `git pull origin master:demi`: So say if you are on `khoi` and you run that command. THe commands will fetch all the commits from master REMOTE and put it onto a branch `demi`. and then `merge` with `khoi`.  => Like this `git fetch origin master:demi -> git merge demi` WITH KHOI! So now Khoi has a NEW commit that combines the current HEAD from khoi and all changes associated with demi, pulled from remote master. 

Link: https://learngitbranching.js.org/ => Try to do mixed bag questions again! Quite interesting. 

**Thoughts:**: These exercises took me from Level 1 git to Level 3 git user... 
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Day 12: September 27, 2020

**Today's Progress**: Learned about React Lazy loading and loadable components. Failed to provide lazy solution for slow image rendering, although successful in term of providing a facade that covers up the main problem... 

Learning more about Java interface and how to implement interface
=> When a CLASS implements an interface, all inherited methods must be DECLARED "PUBLIC" otherwise will throw an ERROR of weaker access priviledge. 

When writing LARGE APPLICATION, developers will
1) Identify all abilities/roles.
2) Define the interaction between these roles.
3) Then simply assign roles to all the classes.

What is a Stream in Java? A `stream` is an Entity for exchanging data. These are TWO MAIN STREAM INTERFACES.
-> 1) InputStream: To read data
-> 2) OutputStream: To write data
Classes that extend these are FileInput/OutputStream, 

Link: https://codegym.cc/quests/lectures/questcore.level03.lecture07

**Thoughts:**: Another day of happy Java coding :) Learned a lot about Stream writer, how to close it

### Day 13: September 28, 2020

Using FileInputStream and BufferedReader: https://codegym.cc/quests/lectures/questcore.level03.lecture11

**Today's Progress**: More java and input and output stream (I/O)

**Thoughts:**: Good day, a bit of headache, cannot do much..

### Day 14: September 29, 2020

**Today's Progress**: Reviewed narrowing and widening of reference type. When you widen (up to Object, up to chain), you would not need to do type casting, but if you narrow (go down the chain to child class, you will have to specify type). 

`public static void main(String[] args){
  Object obj = new Tiger();
  Animal animal = (Animal) obj;
  Cat cat = (Cat) obj;
  Tiger tiger = (Tiger) animal;
  Tiger tiger2 = (Tiger) cat;
}`

- This should be important (ChildClass obj).methodCall(); => When in a switch of if statement if the method passed in `obj` with a parent class 

Link: https://codegym.cc/quests/lectures/questcore.level04.lecture03

**Thoughts:**: More Java, More happiness :)

### Day 15: October 1, 2020

**Today's Progress**: Did an exercise on Singleton! Very interesting Design Pattern in which you only create **ONE** instance of it via getInstance() and **declare private constructor** so people won't be able to create a Singleton.

4 types of access modifier **BY LEVEL**:
1) Public: This variable or method can be used by anything in the program (no restrictions)
2) Protected: A bit better than package private (or default). Basically same as default, but **OUTSIDE PACKAGE CHILDREN CLASSES** can access this field. 
3) Default (or package private): This variable or method can only be used where it is defined **IN ITS OWN PACKAGE** => Meaning other classes AND **OUtSIDE PACKAGE CHILDREN CLASS** **CANNOT** use it.
4) Private: This variable or method can be used only within the class (LOWEST FLEXIBILITY)

**Thoughts:**: :)

# 100 Days Of Code - Log

### Day 16: October 3, 2020

**Today's Progress**: Learned more about Method Overloading. Parameter will ALWAYS widen (expand) to the top of chain. 
So if print((short) 1) and method is print(double i) => It will still print :) 

- When a class is loaded, it is loaded from top to bottom. from fields -> CONSTRUCTOR -> methods. What will this code block gives? 

`
class Cat
{
 public int a = getSum();
 public int b = getSum() - a;
 public int c = getSum() - a - b;

 public getSum()
 {
  return a + b + c;
 }
}`

=> It would return 0 0 0 because getSum() has not been declared when constructor is called (automatically). **ALSO BECAUSE a b c default's values are 0**

- Also, learn about **STATIC BLOCK**, a static block is loaded => Basically, everything in static block is ran first when executing.
` 
    public static int A;
    public static int B;
    public static int MIN;
    
    static {
        try {
        BufferedReader b = new BufferedReader(new InputStreamReader(System.in));
        A = Integer.parseInt(b.readLine());
        B = Integer.parseInt(b.readLine());
        MIN = min(A, B); // return min of 2 number 
        b.close();
        } catch(IOException e){
            System.out.println(e);
        }
    }
`

- Also , **NON STATIC BLOCK OR INSTANCE INITIALIZATION BLOCK** will execute **BEFORE EVERY TIME A CONSTRUCTOR FUNCTION IS CALLED** 
`{
 // These codes in here will execute before constructor functions are called 
}`

1) Only once in memory 
2) before any constructor calls (or whenever an object is initialized) .

Link, good reminder that if you don't declare a constructor, it will declare one for you by default and when you inherit the class, the child class will call the parent constructor **AND** parent's variable first  (if used super()) => ** BASICALLY `extends` is the keyword to also automatically call super() in the child class if constructor function not defined **

Link: https://codegym.cc/quests/lectures/questcore.level05.lecture05
https://codegym.cc/quests/lectures/questcore.level05.lecture08

**Thoughts:**: :)

### Day 17: October 4, 2020

**Today's Progress**: Learned about the basic of `Template Pattern`. A template pattern allows us to override parts of an algorithm while following pre-created structure. For instance, a base class has an algorithm that would have 2 methods assess() and build(). But when different class extends this base class will have the flexility to override its own assess() and build() methods while following the required structure of the original algorithm (usually `final`).

To store a very big number, use java.math.BigInteger or java.math.BigDecimal

Life cycle of object creation
1) Static variables of parent class initialized
2) Static variables of child class initialized
3) Non static variables of parent initialized
4) Constructor of parent class invoked 
5) Non static variables of child initialized
6) Constructor of child class
**Lesson learned** => Static variables go first! Then non-static varilables of parent, then non-static variable of child then constructor of parent and child. 
Static > Non static var > constructor https://codegym.cc/groups/posts/249-sequence-of-actions-during-object-creation

**Thoughts:**: :)

### Day 18: October 5, 2020

**Today's Progress**: What is a thread? A program can spawn little robots to execute some codes and commands. If we want the program to execute some other commands **IN PARALLEL** to the current robot (thread), the program will spin off another robot (thread) and asks it to do those tasks. These are **MULTITHREADING** (MULTITASKING?). In term of computer science, the computer only has **ONE** processor, and the processor will switch between threads (probably can think of threads like a **PATH** that the computer takes to finish a certain task. 

How to start a thread
1) Create a thread object
2) Wrap the task you want to run inside that object
3) run this.start() on it 
`
class Printer implements Runnable
{
public void run()
{
System.out.println("I’m printer");
}
}

public static void main(String[] args)
{
Printer printer = new Printer();
Thread childThread = new Thread(printer);
childThread.start();
}`

In a program, Java has one thread called the "MAIN THREAD". The main thread runs the main() methods and ends, whereas child thread like the one above will run once its called and then end. 

** IMPORTANT REGARDING THREAD ** : To tell a Thread what method to execute, the class must implement the `Runnable` interface. For the Thread object, it has the constructor

1) Your class must implement Runnable tinterface `Thread(Runnable runnable)` => runnable is an object that implements Runnable interface that has run(). And within run() method, you can write whatever you want in there
`public static void main(String[] args)
{
Printer printer = new Printer("Natasha");

Thread thread1 = new Thread(printer);
thread1.start();

Thread thread2 = new Thread(printer);
thread2.start();

Thread thread3 = new Thread(printer);
thread3.start();
}` => Multithread running

2) Your class must extends Thread class `YourClass extends Thread` => All you have to do is overwrite the run() method in your class and create object of your class and runs start() on it. => Shortcoming for extending a Thread is that you cannot have another parent class AND you **CANNOT** have multiple threads created from one object. 

`YourClass extends Thread {
  public void run(){ //something} 
}

public static void main(String[] args)
{
Printer printer = new Printer("Jack");
printer.start();

Printer printer2 = new Printer("Jack");
printer2.start();

}
`

**THE START() method executes run() method once called** 

- Thread stopping: For instance, in the main method, you create a child thread and call childThread.**join()** => This says that the **MAIN THREAD** will stop execution and wait until childThread finishes executing! 


**Thoughts:**:

### Day 19: October 6, 2020

**Today's Progress**: Making stuff responsive with pure CSS 

**Thoughts:**: Crazy 3 hours filled with CSS..

### Day 20: October 7, 2020

**Today's Progress**: 
- Learned more about join() => If you call join() on a child thread, then the parent thread will stop execution until that particular child thread finishes execution.
- getName() is a method 
- Volatile keyword **: This is a keyword that says a variable will be shared between different threads, therefore it will be stored in the MAIN MEMORY INSTEAD OF a CPU CACHE**. This keyword makes a variable CPU safe. Think about if there are several threads writing and reading one single variables, we cannot ensure that all threads will read and write the most updated variable :)
- Thread.sleep(): Make the program sleeps :) When is it used best? It is used best in a child thread when it `doesn't need` to run something regularly NON-STOP.
- setPriority(MAX_PRIORITY): the parameter is an int to represent what is the priority of the thread. setPriority is just a method to set the priority of each thread.

** YOU CANNOT STOP A THREAD!! IT CAN STOP ITSELF ** BY SETTING A BOOLEAN AND WAIT AFTER A WHILE IT WILL STOP THE THREAD


(OFFICIAL): STOP THREAD USING isInterrupted() and interrupt(): https://codegym.cc/quests/lectures/questcore.level06.lecture09
(UNOFFICIAL) LINK TO READ MORE ABOUT IT: https://codegym.cc/quests/lectures/questcore.level06.lecture08

### Day 21: October 8 , 2020

**Today's Progress**: 

- More about threadInterruption
-> threadObject.interrupt() => To interrupt a thread
-> threadObject.isInterrupted() => Return boolean whether it is interrupted or not

Benefit of Multithreading:
1) Paralelism/ Simultaneous Execution - https://codegym.cc/groups/posts/108-multithreading-in-java-what-it-is-its-benefits-and-common-pitfalls
-> Heavy calculation on one thread, draw or do something else in another thread.

Bad of Multithreading:
1) Programmer CANNOT control order of thread execution! Parallel DOES NOT MEAN Sequential
2) **Deadlock**: When threads are waiting for objects that are hold in other thread... So its like a vicious cycle that thread one waits for thread two but thread two is also waiting for thread one... => You need experience to get a job but how can you get experience if you don't have a job? 
3) **Race Condition**: Basically you write a program that requires sequential execution but instead you do them in parallel (no sequential order!). 

**Thoughts:**: Good stuff!

### Day 22: October 9, 2020

**Today's Progress**: Join() method is FINAL!  

**Thoughts:**: Dammit lots of practice lulz


### Day 23: October 10, 2020

**Today's Progress**: stop() is deprecated, use interrupt() and isInterrupted(). 

- Learned about UncaughtExceptionHandler interface
=> Explanation on how to implement: **Problem** We don't have time to wrap try catch block around every block of code... So we need to handle those uncaught exceptions somehow right? 
**Solution**: We have an interface called `Thread.UncaughtExceptionHandler` that belongs to the Thread class. The Thread class belongs to a ThreadGroup. If one Thread is terminated, before it does, it will terminate and call its own UncaughExceptionHandler. If it does not have one, it will use ThreadGroup's handler. If ThreadGroup does not have one, it will use the default UncaughtExceptionHandler. 

- More on `synchronized` keyword. Like `synchronized(this){ // some codes}`. This essentially says that when the thread enters this block of code, Java Virtual Machine will lock the mutex of this object (inside the parenthesis). As soon as the code block finishes execution, the mutex is unlocked, the old thread leaves and the new thread comes in. This is like a restroom sign (restroom sign = mutex, an indication). `this` is the object that this method is being called on, but another parameter can be passed in, and that parameter becomes the "MONITOR". 

- A static block also contains synchronized keyword already but you can also put different "guard" 

- Computer has memory that stores data and codes. The PROCESSOR (CPU or central processing unit) is the one that executes these codes, grab data from memory to read and write it back to memory. To speed up computation, the process uses cache or CPU cache where it stores most of its most used variables. 

**Thoughts:**: 

### Day 24: October 11,2020

**Today's Progress**
- String Buffer vs String Builder: Always use StringBuffer because String Builder is **NOT** thread-safe but String Builder is.
- Encoding: Is basically transforming data into another form. But encoding IS NOT 100% SAFE. Because program can be created to decode it! (ie: URL encode, Base64, Unicode)
- Encrytion: Is a form of data protecting. The process will also contain another **SECRET KEY** that only the creator knows about. 
- Hashing: Give an input, go through an algorithm, provide an output. But one input will only have one unique output. This CANNOT be reversed (Output -> Input). 

Encryption vs Hashing
- Encryption is TWO-WAY conversion. You can use the same SECRET KEY to convert, whereas Hasing is a ONE-WAY conversion, one input = one unique output. 

- Object-level lock and Class-level lock:
=> 1) Object level lock: So remember that each object has a **LOCK** or **MUTEX**, if the thread wants to access this object, it needs to obtain the lock of that object.  
=> 2) Class level lock: If a thread wants to execute **STATIC** method, it needs to acquire CLASS LEVEL LOCK. But once thread acquires the class level block, it can execute **ANY** static SYNCHRONIZED methods 
https://www.tutorialspoint.com/object-level-lock-vs-class-level-lock-in-java#:~:text=Every%20class%20in%20Java%20has,synchronized%20method%20of%20that%20class.
https://codegym.cc/groups/posts/110-thread-synchronization-the-synchronized-operator

- yield(): We know that processor switches threads to execute code. Quantum = processor's time. So each thread gets some quantum (processor's time). Thread.yield() means to give up the thread's quantum early... And allows processor to switches to another thread faster... 

**Thoughts:**:

### Day 25: October 12, 2020

**Today's Progress**: 
- Read and write to all primitive types except of LONG and Double are **ATOMIC**. Meaning that if there are 2 threads, one writes the int value, and the second read the int value. The second thread may read the old OR new value, no in between... But this does NOT apply to `long` and `double`.
- Comparable interface contains only ONE method => compareTo(Object o), returns a positive number (or 1) if this.props > o.props, negative (-1) if this.props < o.props and 0 if this.props == o.props. 
- Why is HashMap **NOT** thread-safe? Remember, HashMap uses a dynamic array under the hood and uses hash function given the key to find the index inside that dynamic array that stores the value. Whenever a new item is added (put) onto the hashmap, the internal array may call `array.resize()`. But if there are multiple threads accessing the same hash map, the array may be under going **resizing**, so the new array is practically EMPTY and so calling get() will return null => **THREAD UNSAFE**

**Thoughts:**:

**Day 26**: October 16, 2020

Today's Progress: CRUD operation! 
- To set command line argument (or use String[] args) => 1) Run 2) Edit Configs 3) Program argument 4) Seperate eacn with a space and string is wrapped within " " 
(i.e: c Washington m "04 15 1990")
- For CRUD operation, the variables should be volatiled if there are multiple threads changes it. Also, each thread should only be able to do one operation inside a synchronized block. 

Thoughts: Some practice with Crud

### Day 27: October 19, 2020

**Today's Progress**: More CSS. Finished task assigned in 2 hours. Pretty good

**Thoughts:**: CSS skill has improved!

### Day 28: October 20, 2020

**Today's Progress**: Switched gear to React Native 
- Fixed some CSS bug
- Get started with React Native. Finished setting up project and development environment.
- Container in React Native = View
- Wrapping ScrollView around a list allows it to scroll, but if you use FlatList Component (preferred), then it will automatically allow the list to be scrollable and **SUPPORT A FEATURE SIMILAR TO LAZY LOADING (If scroll then loads if not then no).

<FlatList >
  data={data}
 renderItem={({ item }) => ( <Text ...props></Text> )
 </FlatList>
 
 - TouchableComponents -> You can wrap a button or something around this for it to be touchable
 - Alert -> Alert.alert(`TITLE`, `TEXT to display`, {} ) => Third is an object with different keys like text, onPress(), ... 
 - TouchableWithouFeedback + Keyboard.dismiss() -> Wrap this around a big child so whenever you click away from that child, the keyboard is dismissed. 
 **FLEX BOX**: https://www.youtube.com/watch?v=R2eqAgR_KlU&list=PL4cUxeGkcC9ixPU-QkScoRBVxtPPzVjrQ&index=14
 const style = StyleSheet.create({
   containerClass: {
     flex: 1, -> This class allows the component to be flexible and flex its height for entire screen! 
     
     flexDirection: 'column' or 'row' (column means child items are stacked on top of each other whereas row is next to each other side by side)
     // Basically column makes main axis as Y axis and row makes main axis as X axis.
     
     justifyContent: : center or flex end or flex start(default) or space-around (even left and right space for leftward and rightward item) or space-between (only left and right space for other items except for leftward and rightward item) -> Determine how spreads things out on MAIN AXIS
     
     alignItems: center (around cross axis) or flex start, flex end -> Determine how spreads things out on CROSS AXIS (opposite of main axis) ,so if flexDirection is row then cross axis is column
       
   }
 })
 - Screens: Just like a page in term of mobile! 
 - Using custom font: import * as Font from 'expo-font'. Font
 => const getFonts = Font.loadAsync({
   font1: require('../assets/font);
 });
 
 => Can also tell the component whether the font has finished loaded and THEN render by `import { Apploading} from 'expo'` => <AppLoading startAsync={getFonts} onFinish={() => setComponenToRenderFromUseState(true) />, => This will reload the component and show it 
 => Once the component is rendered then that component can use those custom font loaded in StyleSheet.create(); 

**Thoughts:**:

### Day 29: October 21, 2020

**Today's Progress**: Did React Native. Debounce function can be used with Async as well :)

**Thoughts:**: Getting started with React Native! A rough start without much guidance tho.

### Day 30: October 22, 2020

**Today's Progress**: Did React Native. 

**Thoughts:**: More learning with React Native and Flex Box!

### Day 31: October 23, 2020

**Today's Progress**: Typecasting from char -> numeric value like (int) will convert the char (letter) to its ASCII value. 

**Thoughts:**:

### Day 32: October 24, 2020

**Today's Progress**: React Native, useFocusEffect, allowing android to access camera by adding to AndroidManifest.xml

**Thoughts:**: Did some bug fix and useFocusEffect :) 
