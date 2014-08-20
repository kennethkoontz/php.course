---
layout: page
title: Week 3 - Day 5
---
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

####Exercises
1. [Laravel QuickStart](http://laravel.com/docs/quick#routing)  
