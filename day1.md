---
layout: page
title: Week 1 - Day 1
---
##Introduction
Geekwise PHP is an introductory course that teaches the basics of the PHP language and implementing functional Web Applications. Although not required, basic knowledge of HTML/CSS is good to have as PHP blends these technologies together to create a functional application. For the first few weeks, each student will study the PHP language while participating in practical application of course material learned in each session. Using the material learned from the first few weeks, the last few weeks will be used to design a function Web Application. 

##What is expected?
There is no homework assigned throughout the course. All work will be hands-on and will be covered in each session. Each practical application of a topic(s) will be covered after discussing the topic(s). Each topic(s), whether directly or indirectly, will be used to provide building blocks to create the final Web Application. Because there is no homework, it is encouraged that you follow along with the material and ask questions. We all are learning and this is probably one of the more important traits to possess as a software developer in the industry. So please ask questions and we will work through it. But most importantly, have fun!

Although notes may help, it is encouraged to follow along and grasp material covered in class. If you can't make it to a class, all material covered will be uploaded so that you can catch up.

##Goals
* Learn the basics of PHP
* Learn industry/production quality tools & practices
* Build a working Web Application

##Session Outline

### What is PHP?
* [PHP](http://en.wikipedia.org/wiki/PHP) was developed by Rasmus Lerdoff in 1995.
* Used all over the web to power dynamic websites.
* Backend Language
* Popular websites - Facebook, Yahoo, Wikipedia, Wordpress
* Where in the stack? browser (rendered html) -> server (Apache, NGINX, etc) -> PHP
* Loosely typed
* Interpreted, not compiled

## Let's get started?
{% highlight php %}
{% endhighlight %}

###Tools
[Codepad](http://codepad.org) - A way to run PHP snippets.

### PHP syntax and files
* PHP syntax starts with `<?php` and ends with `?>`.
* The file extension for a php file is `.php`.
* Can be embedded in HTML.
* Statements are terminated with a `;`.

### Print statements
`echo` and `print` statements provides a way to output strings. The `echo` statement can print one or more strings, while the `print` statement prints one string.
####[Example](http://codepad.org/Xps2b08s)
{% highlight php %}
<?php
echo "hello", " world!";
?>
{% endhighlight %}

### Comments
Comments can be added to PHP code to let others understand your code.
####[Example](http://codepad.org/Tqn0Dmd7)
{% highlight php %}
<?php
// i'm a single comment!
#  me too!
/*
i'm a multi line comment!
*/
?>
{% endhighlight %}

### Variables
Variables are a way to store data - think of a container that stores your data.

* Created when you assign it a value.
* Start with a `$` followed by the name. ex. `$foobar`.
* Three different types of scopes - local, global, and static.
	- A variable declared **inside** of a function is local and thus can only be accessed within the function.
	- A variable declared **outside** of a function is global and thus can only be accessed outside the function.
	- A variable declared as static will remain after function executes. Normally local variables are destroyed.

####[Example](http://codepad.org/aBihQWZl)
{% highlight php %}
<?php
$foo = 'foo'; // global to printFoobar function

function printFoobar() {
  $bar = 'bar'; // local to printFoobar function

  // doesn't know about $foo
  echo "Inside printFoo. foo = $foo, bar = $bar\n"; 
}

printFoobar();

// doesn't "know" about $bar
echo "Outside of printFoo. foo = $foo, bar = $bar\n"; 
?>
{% endhighlight %}

####[Example](http://codepad.org/GkJCRPOV)
{% highlight php %}
<?php
function printFoo() {
	static $foo = 'foo';
	echo "$foo\n";
	$foo = "$foo$foo";
}

printFoo();
printFoo();
printFoo();

function printBar() {
	$bar = 'bar';
	echo "$bar\n";
	$bar = "$bar$bar";
}

printBar();
printBar();
printBar();
?>
{% endhighlight %}


### Case Sensitivity
All functions, classes, and keywords are **not** case-sensitive. While all variables **are** case-sensitive.
####[Example](http://codepad.org/hWqOdvQG)
{% highlight php %}
<?php
$helloworld = "Hello World!";
$helloWorld = "HELLO WORLD!";

Echo $helloworld;
ECHO $helloWorld;
?>
{% endhighlight %}

### Functions
You can define blocks of code known as functions.

* Useful when embedding PHP on a page and you don't want to run a function when the page is loaded.
* Useful to create a block of statements to be used later. 

#### Anatomy of a function 
{% highlight php %}
<?php
function foo($arg1, $arg2, $arg3=50) {
  /*
  	executes the statements inside of this block

  	The function is named `foo`. It has 3 arguments named - $arg1, $arg2, and $arg3.
  	$arg3 has a default value of 50. Which means that if $arg3 is not passed in the function $arg3 will equal 50.
  */
  return $arg1 // The value of $arg1 is returned
}

foo();
?>
{% endhighlight %}

### Exercise

1. Create a function that prints a name. The function takes two arguments, the first name and last name.


### Data Types
A data type is an abstraction or classification of various types of data.

* String
* Integer
* Floating point numbers (decimals)
* Boolean
* Array
* Object
* NULL

#### String
A string is a sequence of characters.

{% highlight php %}
<?php
echo 'a string';
echo "also a string";
$foo = 'interpolation';
echo "I'm string $foo" // $foo is placed in the string
?>
{% endhighlight %}

#### [Integer](https://php.net/manual/en/language.types.integer.php)
An integer is a number that is without decimals.

{% highlight php %}
<?php
$x = 5;
$y = 6;
?>
{% endhighlight %}

#### [Floating point number](https://php.net/manual/en/language.types.float.php)
A floating point number is a number with a decimal or a number in exponential form.

{% highlight php %}
<?php
$x = 3.14
$y = 1.024e3 // 1024
$z = 1e-2    // .01 
?>
{% endhighlight %}

#### [Boolean](https://php.net/manual/en/language.types.boolean.php)
A Boolean is either TRUE or FALSE. Useful for conditional testing.

{% highlight php %}
<?php
$x = true;
$y = false;
?>
{% endhighlight %}

#### [Array](https://php.net/manual/en/language.types.array.php)
An array is a container that stores multiple values in one container.

{% highlight php %}
<?php
$fruits = array("Apple", "Orange", "Cherry");
?>
{% endhighlight %}

#### [Object](https://php.net/manual/en/language.types.object.php)
An Object is a data type that contains data about an object and defines how it is used.

{% highlight php %}
<?php
class Bicycle {
	var $color;
	var $brand;
	var $speed;

	function Bicycle($color, $brand, $speed=0) {
		$this->brand = $brand;
		$this->color = $color;
		$this->speed = $speed;
	}

	function getPaintJob($color) {
		$this->color = $color;
	}

	function increaseSpeed($by) {
		$this->speed = $this->speed + $by;
	}
}
?>
{% endhighlight %}

#### [NULL](https://php.net/manual/en/language.types.null.php)
NULL is a special variable the represents no value.

{% highlight php %}
<?php
$nothing = null;
?>
{% endhighlight %}

