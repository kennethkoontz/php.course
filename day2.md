---
layout: page
title: Week 1 - Day 2
---

###Arithmetic Operators
* addition `+`
* subtraction `-`
* multiplication `*`
* division `/`
* modulus `%` (remainder)

####[Example](http://codepad.org/Cn28NpyN)
{% highlight php %}
<?php
$x = 10;
$y = 5;
$z = 2;

echo $x + $y."\n";
echo $x - $y."\n";
echo $x * $y."\n";
echo $x / $y."\n";
echo $y % $z."\n";
?>
{% endhighlight %}

###Assignment Operators
* Assign variable `=`
* Addition `+=`
* Subtraction `-=`
* Multiplication `*=`
* Division `/=`
* Modulus `%=`

####[Example](http://codepad.org/lB8QvTUf)

{% highlight php %}
<?php
$x = 5;
echo $x."\n"; // 5

$x += 5;
echo $x."\n"; // 10

$x -= 5;
echo $x."\n"; // 5

$x *= 5;
echo $x."\n"; // 25

$x /= 5;
echo $x."\n"; // 5

$x %= 2;
echo $x."\n"; // 1
?>
{% endhighlight %}

###String Operators
* Concatenation `.`
* Concatenation Assignment `.=`

####[Example](http://codepad.org/6hiIDJ9H)
{% highlight php %}
<?php
$foo = "Hello";
$bar = " World!\n";
echo $foo.$bar;

$foo .= $bar;
echo $foo;
?>
{% endhighlight %}

###Increment/Decrement Operators
* Pre-increment `++$x`;
* Post-increment `$x++`;
* Pre-decrement `--$x`;
* Post-decrement `$x--`;

####Example
{% highlight php %}
<?php
$x = 5;
++$x; // increments x then returns x
$x++; // returns x then increments x
--$x; // decrements x then returns x
$x--; // returns x then increments x
?>
{% endhighlight %}

###Comparison Operators
* Equal `==`
* Identical `===`
* Not Equal `!=`, `<>`
* Not Identical `!==`
* Greater than `>`
* Less than `<`
* Greater than or equal to `>=`
* Less than or equal to `<=`

> `var_dump` will display more details about a variable or expression. It's used in this example to demonstrate the boolean returned when evaluating the expression (anything that has a value).

####[Example](http://codepad.org/JkMrqInC)
{% highlight php %}
<?php
$x = 5;
$y = 5;
$z = '5';

var_dump($x == $z); // True
var_dump($x === $y); // True
?>
{% endhighlight %}

###Logical Operators
* And `and`
* Or `or`
* Exclusive Or `xor`
* And `&&`
* Or `||`
* Not `!`

####[Example](http://codepad.org/cA8TZL6x)
{% highlight php %}
<?php
$x = true;
$y = false;

var_dump($x or $y); // True
var_dump($x and $y); // False

// Exclusive Or, `xor` is True when $x or $y is true but NOT both
var_dump($x xor $y); // True
var_dump($x xor $x); // False
?>
{% endhighlight %}

###Array Operators
* Union `+`
* Equality `==`
* Identity `===`
* Inequality `!=`
* Inequality `<>`
* Non-identity `!==`

####[Example](http://codepad.org/rUPQ1CoO)
{% highlight php %}
<?php
$ken_langs = array("python", "javascript", "php", "c");
$greg_langs = array("javascript", "python", "php", "haskell", "erlang");
$joe_langs = array("javascript", "python", "php", "haskell", "erlang");

var_dump($ken_langs + $greg_langs); // The union of languages that both ken and greg know
var_dump($ken_langs == $greg_langs); // True if both have the same values
var_dump($greg_langs === $joe_langs); // True if both have the same values and order
?>
{% endhighlight %}

Exercises
1. Create a function that adds two integers and returns the result. [solution](http://codepad.org/XUxAgx7j)
2. Create a function that compares two arrays for identity and returns the result. [solution](http://codepad.org/nYZ74DVW)
3. Create a function that returns the union between two arrays. [solution](http://codepad.org/hsK0ndRp)

###String Functions

####strlen() & strpos()
`strlen` will return the number of characters in a string. `strpos` will look for specified text within a string and return the position of the first occurance.

####[Example](http://codepad.org/zZcKlwZj)
{% highlight php %}
<?php
var_dump(strlen("PHP Rocks!")); // 10
var_dump(strpos("PHP Rocks!", "P")); // 0
?>
{% endhighlight %}

> Note that the above strpos example returns 0 and **not** 1 even though the first occurance occurs at the 1st position. This is because the first character of a string has a index/position of 0. The second character of a string has a position of 1 and so on and so forth. This means that the position of the last character in a string is always the length of the string - 1.

###Conditional Statements
Conditional statements are used to control the flow of code. They can be used to perform different actions based on conditions.

#### if/elseif/else Statements
`if`, `elseif`, `else` statements can be used together to execute blocks of code based on conditions.

> Use this when you want to execute code based on a single condition.

[Example](http://codepad.org/bLQQh5rM)
{% highlight php %}
<?php
$name = 'Harry';

if ($name == 'Harry') {
	echo 'Hello Harry!';
} 

?>
{% endhighlight %}

> Use this when you want to execute a block of code if the condition is true or execute another block of code if the condition is false.

[Example](http://codepad.org/zBJbMNUF)
{% highlight php %}
<?php
$name = 'Mark';

if ($name == 'Harry') {
	echo 'Hello Harry!';
} else {
	echo "You're not Harry. What is your name?";
}
?>
{% endhighlight %}

> Use this code if you have multiple blocks of code that you want to execute based on a condition.

[Example](http://codepad.org/5DkOt5rD)
{% highlight php %}
<?php
$name = 'Mark';

if ($name == 'Harry') {
	echo "Hello $name!";
} elseif ($name == 'Mark') {
	echo "Hello $name!";
} else {
	echo "I was expecting either Harry or Mark. What is your name?";
}
?>
{% endhighlight %}

Exercises
1. Create a function that takes a string and checks the length. If the length is larger than 4 characters echo "too large". [solution](http://codepad.org/3IeJYdA1)
2. Create a function that takes 3 integers and checks if a number is within a range. The first two integers represent a range. The last integer is the number you want to check. If the number to check is less than the range, echo "too low". If the number is within the range, echo "just right". If the number is greater than the range, echo "too high". [solution](http://codepad.org/qpgA1Pmq)

{% highlight php %}
<?php
function num_range($low, $high, $number) {
	if ($number < $low) {
		echo "too low\n";
	} elseif ($number >= $low && $number <= $high) {
		echo "just right\n";
	} elseif ($number > $high) {
		echo "too high\n";
	}
}

num_range(3, 5, 1);
num_range(3, 5, 4);
num_range(3, 5, 6);
?>
{% endhighlight %}

#### Switch Statements
Switch statements execute one or more blocks of code like if..elseif..else statements. 

[Example](http://codepad.org/LnZLBtEB)
{% highlight php %}
<?php
function select_website($website) {
	switch ($website) {
		case 'facebook':
			echo "you've selected facebook\n";
			break;
		case 'twitter':
			echo "you've selected twitter\n";
			break;
		case 'linkedin':
			echo "you've selected linkedin\n";
			break;
		default:
			echo "you didn't select facebook, twitter, or linkedin\n";
	}
}

select_website('facebook');
select_website('twitter');
select_website('linkedin');
select_website('wikipedia');
?>
{% endhighlight %}

> Note that if a `case` block is selected **and** you don't use a `break` in the selected `case` block. The code will execute in every subsequent `case` and `default` block until it exists the switch statement or encounters a `break` statement. This is known as *switch fall through*.

####[Example](http://codepad.org/zeQstQu9)
{% highlight php %}
<?php
function select_website($website) {
	switch ($website) {
		case 'facebook':
			echo "you've selected facebook\n";
		case 'twitter':
			echo "you've selected twitter\n";
		case 'linkedin':
			echo "you've selected linkedin\n";
			break;
		default:
			echo "you didn't select facebook, twitter, or linkedin\n";
	}
}

select_website('twitter');
?>
{% endhighlight %}

### Looping Statements
Looping statements provide a way rerun a block of code and iterate over data types such as an array.

#### While Statement
A `while` statement will loop a block a code until a condition is `true`.

####[Example](http://codepad.org/O5h6FHd4)
{% highlight php %}
<?php
$i = 0;

while($i < 10) {
	++$i;
	echo $i;
}
?>
{% endhighlight %}

Exercise
1. Create a function that prints n n-times. The function takes one an argument, an integer. The integer represents the number of times to print itself. [solution](http://codepad.org/JtyVhrue)
