js-notes
========

##Ruby to JavaScript

Here are some key differences between our beloved Ruby and it's best friend, JavaScript.

\(Note: There are more similarities than differences!  For example, they deal with scope in very similar ways.  
The 'Scope of variables' concept noted in this table is one of the only differences.\)

| Concepts   | in Ruby  | in JavaScript |
| ---------- | -------- | ------------- |
| Is everything an object? |  you have Strings, Numbers, booleans, etc., and **they are all objects**        | strings, numbers, booleans, 'undefined' and 'null' **are primitives**, not objects |
| Truthy and Falsy | Only 'nil' and 'false' are falsy | 'undefined', 'null', 'NaN' ("not a number"), 0, and '' are **all falsy values** in JS |
| Functions/Methods | Methods | Functions |
| Local vs. Global Variables | Globals require special '$' sign  | Globals happen when you forget 'var' |
| Referencing current instance | 'self' is current instance anywhere within the class and it's methods | 'this' refers to the thing that the method was called on. |
| Type comparisons | "5" == 5 returns false | "5" == 5 returns true BUT "5" !== 5 also returns true.  To strictly compare try "5" === 5 |
| Implicit return? | Without a 'return' statement, a function will return the last value listed. | Without 'return statement, a function will return 'undefined'. |
| Scope of variables | Referencing a variable that is not defined inside the method will raise an error. | You may use variables defined outside of a function without passing them in as arguments. \(a.k.a. [Lexical Scoping](http://eloquentjavascript.net/chapter3.html#p71c5c4c9)\) |
| Wrong number of Arguments | Raises an ArgumentError | Silently ignores extra arguments or gives missing arguments the value 'undefined', arguments can also be access with 'arguments' keyword. |
| Hashes | You call this a 'hash' in ruby. | Variables of type 'Object'. |
| String Interpolation | Easy string interpolation | [No string interpolation](http://stackoverflow.com/questions/4743137/anything-similar-in-javascript-to-rubys-value-string-interpolation)- you must concatenate. |


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
a.k.a. [anonymous functions](http://eloquentjavascript.net/chapter3.html#p7bad6ff)

In Ruby:

    Proc.new { |n| n * n }
    
In JavaScript:

    function (n) {
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
    
####If/Else 

In Ruby:

    if 2 + 2 == 4
      result = "Sane world."
    elsif 2 + 2 == 5
      result = "Very large values of 2."
    else
      result = "Not sane world."
    end
    
In JavaScript:

    if (2 + 2 == 4)
      var result = "Sane world.";
    else if (2 + 2 == 5)
      var result = "Very large values of 2.";
    else
      result = "Not sane world.";
    end

####String and Int conversion

In Ruby:
    
    "5".to_i
    #becomes the number 5
    
    5.to_s
    #becomes the string "5"
    
In JavaScript:

    Number("5");
    //becomes the number 5
    
    var n = 5;
    n.toString();
    //becomes the string "5"

####Push value to an array

In Ruby:

    [] << "something"
    
    #OR
    
    [].push("something")
    
In JavaScript:

    var arr = [];
    arr.push("something");
    // no "shovel" operator : (

####Default values for arguments

In Ruby:

    def add_n_or_1(x, n = 1)
      x + n
    end
    
In JavaScript:

    //you must specifically check that it is undefined
    function add_n_or_1(x, n) {
      n = typeof n != 'undefined' ? n : 1;
      return x + n;
    };
    
    //OR in some cases this works
    function add_n_or_1(x, n) {
      if (arguments.length == 1)
        n = 1;
      return x + n;
    };



####Print statements for debugging

In Ruby:
    
    puts "Help!"
    #prints to the terminal or (in RoR) the session log
    
In JavaScript:

    console.log("Help!");
    //prints to the console in the browser; use devtools to see it.
    
####The semicolon

Use it to end every statement in JavaScript.  What qualifies as a statement in Javascript?
If you would put it on a newline in Ruby, OR if it is the end of a 'block' of code then it should probably end with a semicolon.

"In some cases, JavaScript allows you to omit the semicolon at the end of a statement. 
In other cases, it has to be there or strange things will happen. 
The rules for when it can be safely omitted are complex and weird. 
In this book, I won't leave out any semicolons, and I strongly urge you to do the same in your own programs."
-[EloquentJS, ch. 2](http://eloquentjavascript.net/chapter2.html#p751953db)
    


###Cool Stuff to Think About

-JavaScript has metaprogramming too!  Check out [the factory method in this example](http://eloquentjavascript.net/chapter3.html#p2eb13e2b).
