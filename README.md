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
    #(Yes I do put a ; at the end of every line)
    word.slice(2,4)
    #returns "ll"
    
####Defining a 'block' of code

In Ruby:

    Proc.new { |n| n * n }
    
In JavaScript:

    function(n) {
      return n * n
    };
    
####Defining and calling a named method/function

In Ruby:

    #define it
    def the_name(n)
      n * n
    end
    
    #call it
    the_name(12)
    
In JavaScript:

    #define it    
    var the_name = function(n) {
      return n * n
    };
    
    #OR
    function the_name(n) {
      return n * n
    };
    
    
    #call it
    the_name(12);
    
