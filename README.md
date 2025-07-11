# General Syntax: 
<?php
echo “Ram”;
?>

Note: there should be no space between ? and php at first line of syntax


# Comment 
#,// are use for single line comment
/*  */ used for multi line comment

# Concat
. is used to concat two strings 

E.g.
	<?php
		echo “Ram is coming at” . 4;
?>

# Variables
As like other standard same naming regulation is here
A variable can be started with an alphabet or underscore.
A variable can’t be started with a number.
Variable are case sensitive i.e. $x and $X  both are different variables

## Note: $ is used to declare variable in php


 # Output 

echo is used to show output 
E.g. 
	<?php
		echo “Ram is coming at” . 4;
?>

# PHP is a loosely typed language 
We do not need to declare variable type, here. Php will make it sense.

Note: in php7 , type declaration added, this gives the option to define data type at function making to avoid fatal error due to misunderstanding of data type.
	

# PHP supports the following data types:
String
Integer
Float (floating point numbers - also called double)
Boolean
Array
Object
NULL
Resource

# Get the type
We use var_dump() to identify the data type of a variable.

Eg 
	$x = 5;
	var_dump($x);

Assigning string to variable

$x = 5;
echo $x;

# Assigning string to multiple variable

$x = $X = $y = 5;
echo $x . $X . $y;

# Scope of variable 

Variables can be declared anywhere in script. Scope of variable is the part of that script where variable can be accessed for further use or other action.

As previous, there are three types of scope 

## Local
## Global
## Static

### Global Variable
A variable declared outside a function has global scope and can only be accessed outside of the function.


$x = 5;  // global scope
function myTest(){
	// using x inside the function will generate error as it is global 
	echo “<p> Variable x inside function is : $x </p>
}

myTest();

echo “<p> Variable x outside of function is: $x </p>”;

#### How to access global variable inside a function if needs ?? Use of Global keyword
The global keyword is used to access the global variable inside a function 

e.g.
 	$x = 5; $y = 10;
  	function myTest(){
   	global $x, $y;
    	$y = $x + $y;
   }
   myTest();
   echo $y; 		// output will be 15

#### Notes: PHP also stores all variable in an array called $GLOBALS[index]
index hold the name of variable . This array can also be access inside function and directly can update the value of global variable.


e.g.
$x = 5;
$y = 10;
function myTest(){
$GLOBALS['y'] = $GLOBALS['x'] + $GLOBALS['y'];
}
myTest();
echo $y; 	// result will be 15



### Local Variable 

Variables defined under a function is referred to local scope and it can’t be accessed outside of function.

function myTest(){
	$x = 5 ; 		// local variable
 	echo "<p> Variable x inside function is : $x </p>";
  }
  myTest();

  // using x outside of function will give error
echo "<p> Variable x outside the function is : $x </p>";

### Static Keyword
Generally, after execution of a function, variables get auto deleted but some we want to preserve specific variables 
For this purpose we use static keyword

function myTest(){
static $x = 0;
echo $x;
$x++;
}

myTest();
myTest();
myTest();

Then, each time the function is called, that variable will still have the information it contained from the last time the function was called.

#### Note: The variable is still local to the function

