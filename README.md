js-notes
========

##Ruby to JavaScript

Here are some key differences between our beloved Ruby and it's best friend, JavaScript.

| Concepts   | in Ruby  | in JavaScript |
| ---------- | -------- | ------------- |
| Is everything an object? |  you have Strings, Numbers, booleans, etc., and **they are all objects**        | strings, numbers, booleans, 'undefined' and 'null' **are primitives**, not objects |
| Truthy and Falsy | Only 'nil' and 'false' are falsy | 'undefined', 'null', 'NaN' ("not a number"), 0, and '' are **all falsy values** in JS |
| Functions/Methods| Methods | Functions |
| Local vs. Global Variables | Globals require special '$' sign  | Globals happen when you forget 'var' |
| Referencing current instance | 'self' is current instance anywhere within the class and it's methods | 'this' refers to the thing that the method was called on. |

###Syntax for similar operations:

####String Slicing

In Ruby:

    word = "Hello World."
    word[2..3]
    # OR
    word[2, 2]
    #returns "ll"
    
In JavaScript:

    var word = "Hello World.";
    //(Yes I do put a ; at the end of every line)
    word.slice(2,4)
    //returns "ll"
    
####Defining a 'block' of code

In Ruby:

    Proc.new { |n| n * n }
    
In JavaScript:

    function(n) {
      return n * n;
    };
    
####Defining and calling a named method/function

In Ruby:

    #define it
    def the_name(n)
      n * n
    end
    
    #call it
    the_name(12);
    
In JavaScript:

    //define it    
    var the_name = function(n) {
      return n * n;
    };
    
    //OR
    function the_name(n) {
      return n * n;
    };
    
    
    //call it
    the_name(12);
    
####Print statements for debugging

In Ruby:
    
    puts "Help!"
    #prints to the terminal or (in RoR) the session log
    
In JavaScript:

    console.log("Help!");
    //prints to the console in the browser; use devtools to see it.
    
###The semicolon

Use it to end every statement in JavaScript.  What qualifies as a statement in Javascript?
If you would put it on a newline in Ruby, OR if it is the end of a 'block' of code then it should probably end with a semicolon.

"In some cases, JavaScript allows you to omit the semicolon at the end of a statement. In other cases, it has to be there or strange things will happen. The rules for when it can be safely omitted are complex and weird. In this book, I won't leave out any semicolons, and I strongly urge you to do the same in your own programs."
-[EloquentJS, ch. 2](http://eloquentjavascript.net/chapter2.html#p751953db)
    
