---
layout: page
title: Week 2 - Day 4
---

### Looping statements (cont)
#### do...while loops
A do...while loop will execute the block code once then check the condition. If the condition is true the block will repeat itself

####[Example](http://codepad.org/m80zEo6O)
{% highlight php %}
<?php
$i = 0;
do {
	echo ++$i;
} while ($i < 10);
?>
{% endhighlight %}

> It is important to note that a do...while statement will execute at least once, even if the condition fails the first time.

####[Example](http://codepad.org/T8bo1Rsk)
{% highlight php %}
<?php
$i = 20;

do {
	echo "I'm in a block\n";
} while ($i < 10);
?>
{% endhighlight %}

#### for loop
A for loop will execute a block of code until the counter evaluates to false.

####[Example](http://codepad.org/MLmF6aAN)
{% highlight php %}
<?php
for ($i=0; $i<=10; $i++) {
	echo "$i\n";
}
?>
{% endhighlight %}

#### foreach loop
A foreach loop will loop through an array.

####[Example](http://codepad.org/PV5KXbFG)
{% highlight php %}
<?php
$games = array("Halo", "Last of Us", "Madden", "Destiny", "Final Fantasy");

foreach ($games as $value) {
	echo "$value\n";
}
?>
{% endhighlight %}

####[Example](http://codepad.org/7TIDqYv1)
{% highlight php %}
<?php
$games = array("xbox" => array("Halo", "Madden", "Destiny", "Final Fantasy"), "playstation" => array("Last of Us", "Madden", "Destiny", "Final Fantasy"));

foreach ($games as $key => $value) {
	echo "key: $key, value: $value\n";
}
?>
{% endhighlight %}

####Exercises
1. Using a do...while statement, create a function that counts to 10. [solution](http://codepad.org/AGLTjjce)
2. Using a for loop, create a function that counts to 10. [solution](http://codepad.org/T1NdUltR)
3. Using a foreach loop, create a function that iterates through an array and prints its contents. [solution](http://codepad.org/CoYkewmz)

### Functions revisited
There are many functions that are built-in to php. [Function References](http://php.net/manual/en/funcref.php)

* Function names are **not** case-sensitive
* `{` represent the beginning of a function
* `}` represent the end of a function
* to invoke or call a function, use `()` ex. `function_name()`
* Functions take 0 or more arguments.
* Arguments have the `$`, just like variables do
* To set a default value for an argument, use `=`. Example `$start=5`
* To return a value use the return statement

Examine php's [strlen](http://php.net/manual/en/function.strlen.php) function.

####Exercise
1. Examine a few functions from the php.net function reference [documentation](http://php.net/manual/en/funcref.php)

### Arrays revisited
Arrays store multiple values in a single variable. If you have a group of values that you want to store, why not use an array?

Example
{% highlight php %}
<?php
	$carMake1 = "Chrysler";
	$carMake2 = "Honda";
	$carMake3 = "Toyota";

	// What if you wanted to loop through all of the carMake variables and what if there were many of them, say 25? Put them in an array.
	$cars = array("Chrysler", "Honda", "Toyota");
	
	$foreach($cars as $value) {
		echo $value;
	}	
?>
{% endhighlight %}

There are three types of arrays.

* Indexed
* Associative
* Multidimensional

_Indexed_, arrays that have numeric indexes  
Example
{% highlight php %}
<?php
$cars = array("Chrysler", "Honda", "Toyota");
?>
{% endhighlight %}

You can access an element in an indexed array by specifying it's index.  
Example
{% highlight php %}
<?php
$cars = array("Chrysler", "Honda", "Toyota");
$toyota = $cars[2]; // "Toyota"
?>
{% endhighlight %}

_Associative_, arrays that have named keys  
Example
{% highlight php %}
<?php
$person = array("first_name" => "John", "last_name" => "Doe");
?>
{% endhighlight %}

You can access an element in an Associative array by specifying it's key.  
Example
{% highlight php %}
<?php
$person = array("first_name" => "John", "last_name" => "Doe");
$first_name = $person['first_name']; // "John"
?>
{% endhighlight %}


_Multidimensional_, arrays that contain one or more arrays  
Example
{% highlight php %}
<?php
	$person = array(
		"first_name" => "John",
		"last_name" => "Doe",
		"cars_owned" => array("honda pilot", "honda accord")
	);
?>
{% endhighlight %}

Like a string, you can get the length of an array too.
[Example](http://codepad.org/fZZMRSGF)
{% highlight php %}
<?php
$cities = array("Fresno", "Boston", "London");
var_dump(count($cities));
?>
{% endhighlight %}

####Exercise
1) Create an a function that takes three arguments - `first_name`, `last_name`, `phone_number`. The function will take the arguments and return an array that has each key and values passed in. [solution](http://codepad.org/kFXB7Mjg)

###Sorting an Array
There are several functions available to sort arrays.

* sort, ascending
* rsort, descending
* asort, sort associative arrays in ascending, by value
* ksort, sort associative arrays in ascending, by key
* arsort, sort associative arrays in descending, by value
* krsort, sort associative arrays in descending, by key

{% highlight php %}
<?php
$letters = array("x", "a", "k");
$person = array("fname"=>"ken", "lname"=>"koontz");

sort($letters);
?>
{% endhighlight %}

###Objects
An object is a datatype that contains information and methods that interact with itself.

###Creating a class
[Example](http://codepad.org/1KADExmM)
{% highlight php %}
<?php
class Person {
}

$ken = new Person;
var_dump($ken);
?>
{% endhighlight %}

###Class properties
To add data to a class, you can use class properties. These properties are like variable except that they are bound to the class only.  
[Example](http://codepad.org/245mZYMN)
{% highlight php %}
<?php
class Person {
	public $first_name = "first_name";
}

$ken = new Person;
var_dump($ken->first_name);
?>
{% endhighlight %}

The `public` keyword is used to define the visibility of a property.

###Class methods
Class methods are class-specific methods. Unlike properties, that store data, methods are functions that can be used to manipulate data. Like class properties, methods are bound to the class only.  
[Example](http://codepad.org/IhjcK6tT)
{% highlight php %}
<?php
class Person {
	public $first_name = '';
	public $last_name = '';
	public function set_first_name($name) {
		$this->first_name = $name;
	}
	public function set_last_name($name) {
		$this->last_name = $name;
	}
}

$ken = new Person;
$ken->set_first_name('ken');
$ken->set_last_name('koontz');
var_dump($ken);
?>
{% endhighlight %}

The `$this` variable can be used inside of a function to reference itself.

###Multiple instances
Object Oriented programming allows you to create multiple instances of a class by only defining one class. This is a powerful.  
[Example](http://codepad.org/lyM3KbzD)
{% highlight php %}
<?php
class Person {
	public $first_name = '';
	public $last_name = '';
	public function set_name($first, $last) {
		$this->first_name = $first;
		$this->last_name = $last;
	}
}

$ken = new Person;
$ken->set_name('ken', 'koontz');
$jeff = new Person;
$jeff->set_name('jeff', 'jones');
var_dump($ken);
var_dump($jeff);
?>
{% endhighlight %}

###Constructors
You can define a function that gets called when an object is created. This is called a constructor.  
[Example](http://codepad.org/hFUN6VuE)
{% highlight php %}
<?php
class Person {
	public $first_name = '';
	public $last_name = '';
	public function __construct($first, $last) {
		echo "I'm creating a class\n";
		$this->first_name = $first;
		$this->last_name = $last;
	}
}

$ken = new Person('ken', 'koontz');
var_dump($ken);
?>
{% endhighlight %}

###Destructors
You can define a function that gets called when an object is destroyed. This is called a Destructor.  
[Example](http://codepad.org/1BU2xEvV)
{% highlight php %}
<?php
class Person {
	public $first_name = '';
	public $last_name = '';
	public function __destruct() {
		echo "I'm destroying ", __CLASS__, "!!!\n";
	}
}

function foo() {
	echo "I'm inside of foo.\n";
	$ken = new Person;
}

foo();
echo "I've exitted foo";
?>
{% endhighlight %}