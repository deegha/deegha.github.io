---
layout: post
title:  hositing and javascript basics
description: Explaning hosting along with javascript basics
date:   2022-03-24 15:01:35 +0300
image:  'https://res.cloudinary.com/duqpgdc9v/image/upload/v1648148638/deegha/Hositing_Execution_context.png'
tags:   [tech. javaScripts]
---


When I first started writing javascript I learned things by trial and error. With time and experience I learned a lot of things. But when I learned javascript basics, I understood why things is happening in certain ways. So in this post I am trying to explain such a small principle. That is hoisting. 


> Let's take a small javascript example 

{% highlight js %}
console.log("this will print a name next line")

function getName () {
	var name = "Jakan hagar"
	return name
}

var theName =  getName()

console.log(theName) 
{% endhighlight %}


When we execute this program the first thing that is happening is, the Javascript engine creates something called the Execution context. This execution content is created in the call stack of the browser. Every time javascript executes a function it creates an execution context for that function. 

To execute this execution context there are two phases. The first phase is memory allocation and the second phase is code execution. 

In the memory allocation process javascript runs through this code and allocates memory for its variables and functions. 

For variables it allocates memory and assign a value called “undefined” (this part is so important to remember)
For a function it allocates memory and assign the whole function inside that memory location. 

> So lets execute our function

### Phase 1: Memory allocation 

we have a function, so the memory will be allocated for that and assign that function itself into that memory location.

And the next thing javascript will be looking at the next variable. That is the “theName” variable. So javascript will be allocating memory for that variable and assign undefined  

### Phase 2: Code execution 

So now javascript will be running line by line. 
1. finds a console log, and it executes that line
2. finds a function invocation {% highlight js %} getName() {% endhighlight %}. So it brings up the function in the memory and executes it. A very important thing here is that every time javascript invokes a function it creates a new execution context for that particular context. Then it will start allocating memory for varibales inside that context (again 1st phase for this execution context). until that point those varibles have no memory location.
3. 
