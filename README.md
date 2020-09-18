# 100 Days Of Code - Log

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
