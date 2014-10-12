---
layout: post
title: "Getting Started with Flixel, FlashDevelop and Actionscript 3"
date: 2012-05-22 14:00
tags: note flixel as3 gamedev
---

Prototyping Games with Flixel and FlashDevelop was a simple online workshop that
I put on with [design3](http://design3.com) on May 22, 2012 to help teach people
how to work with Flixel, AS3, and FlashDevelop to make a simple project.
This is a list of resources and references from the class.

## FlashDevelop

### What is it?

FlashDevelop is a free & open-source IDE for building projects using Flash. It's Windows only and allows users to write code with AS2, AS3, and HaXe.

### Why use it?

It's free. I mean, that's huge. It allows people to easily develop games or AIR applications on Windows at no cost. It doesn't have any of the extra features Flash CS5 or FlashBuilder has, but it's more than enough for a programming-oriented develop to use to get by.

I think that writing code in FlashDevelop is a joy, as removing a lot of the bulk and making it 100% programming and no timeline or visual editor makes the program quick and light-weight.

The code hinting in FlashDevelop is also superb. This can be a really big help for those who don't want to dig around the docs of libraries or are working with their own large codebase.

You may be thinking, "I don't have Windows. I am on Mac and love it. What about me?!" Don't fret. I understand. There's a few options, but none of them are are simple or as nice as FlashDevelop. My personal choice is to use [MXMLC](http://flashgamedojo.com/wiki/index.php?title=Hello_World_-_MXMLC_(Flixel)). It takes some terminal knowledge, but is quite simple and a lot of fun. You can just edit your code with your favorite text/code editor. If you're on OS X, a few nice ones are [TextWrangler](http://www.barebones.com/products/textwrangler/) or [TextMate](http://macromates.com/).

There's a second option, which is a realm I've never entered. That's using Eclipse (a cross-platform, versatile IDE) with a plug-in. I can't help much more than that because I sadly don't know anything more than that.

### Download FlashDevelop

[FlashDevelop Download Threads](http://www.flashdevelop.org/community/viewtopic.php?f=11&t=9729)

## ActionScript 3 Intro

Part of me cringes from even typing this, but [Wikipedia is a great resource for learning about a language](http://en.wikipedia.org/wiki/ActionScript). ActionScript 3 is the third version of the language used for programming in Flash. It is much more Object-Oriented than the previous iterations of AS.

### Variables

`var variableName:ObjectType = new ObjectType();`

There you have it! That's the process of creating and instantiating a variable. ObjectType is generic, but you'd want to replace that with whatever type of variable you want to work with. Some of the common ones are `int` and `string`, the first representing an integer and the second representing a group of characters (letters or numbers).

### Functions

	public function AddNumbers(int numberOne, int numberTwo):int
	{
			return numberOne + numberTwo;
	}

Wasn't that simple? That's a function! You're adding *function*ality to something. You're making something happen when you want it to happen. Functions are super important in any programming language (sometimes referred to as methods). In AS3 they have their own syntax and order of things, but it makes some sense.

`public`, the first part of the function, declares the scope of the function. The scope of the function is simply when and where it can be called upon. Variable scopes you should be aware of: `public`, `private`, and `protected`. Don't freak out about this right now, but just focus on `public` and `private`.

`AddNumbers` is the name of the function. Simple enough!

What's between those parentheses, you ask? Well that's a great question. Those are called *parameters*. It's what you're passing in to the function. It's what you want to mess with! WIth parameters, you declare the type of the object and then give it a dummy name (give it a useful name, not a dumb name, dummy!). `int` is type for both `numberOne` and `numberTwo`.

Lastly you see the `:int`. Seems…out of place, doesn't it? Well it's actually not needed, but it really should be there. It's the return type of the function. It helps with optimization and making your game run a little bit faster. `:int` means the function is returning an int. That's why in between the curly braces there is the line `return numberOne + numberTwo`. What this means is that the function will spit out a number, the sum of the two numbers passed in. If you don't want to return anything, then your function's return type would simply be `:void`.

You're almost running with the cool crowd now, The Functions. But there is one last thing you need to know - how to use functions.

In some other function (lot's of functions in programming), you're going to call this function, the `AddNumbers` function. Let's just pretend we are in a function and want to add two numbers.

	var sumOfTwoNumbers:int = AddNumbers(6, 10);

Wooh. That's it. The value of `sumOfTwoNumbers` is 16. Do you see how that works? 6 & 10 are passed into the function from before and returned as the sum of both.

### Best Practices

Syntax. That's a funny word. It always seems it is the funny words that are the most important. Syntax is crucial in programming. It is what helps create best practices, and you'll only learn both by reading and looking at other examples. I'll outline some of the best practices that I know of and use with AS3.

* Variables should be written in [camelCase](http://c2.com/cgi/wiki?CamelCase). `myInt`, `name`, `smokedSausageSandwich` are all examples of camel case. It's literally taking a word and squishing it together like a camel. It's lowercase for the first letter of the first word, then capital letters for the first letter of the rest of the words.

* Functions should be written in [PascalCase](http://c2.com/cgi/wiki?PascalCase), sometimes referred to as Upper Camel Case. `HelloWorld`, `PrintMoney`, `Weep` are all examples of Pascal Case. It's like camel case but the first letter of the first letter is capital, as well as the ones that follow.

* Always specify the return types of functions. This was talked about before, and I'd recommend you do it.

## Flixel

### What is it?

[Flixel](http://flixel.org/) is a super awesome library for making games in AS3. It's made by [Adam Atomic](http://www.adamatomic.com/), a pretty cool dude who made some pretty cool games. It's really powerful and has a very small learning curve.

If you want to learn a little bit more about Flixel and what it is, [read this](http://flixel.org/about.html). If Flixel isn't for you, there's another popular option - [FlashPunk](http://flashpunk.net/).

What these game libraries do is help you with a lot of the basics that all games have. Entities, score, levels, tiles, and managing states. It's enough to get you going and make sure you don't have to worry about a lot of the little stuff.

### Download and Use the Flixel Library

[Download the ZIP of the Flixel library here.](https://github.com/AdamAtomic/flixel/zipball/master)

It's that easy. Download it, unzip it, and drag the `org` folder into your project source folder.

Lastly, in your source, simply add `import org.flixel.*;` to import the library into your code for use.

### Flixel Resources

* [Flixel pages in the FlashGameDojo](http://flashgamedojo.com/wiki/index.php?title=Category:Flixel) - Definitely the best resource out there for almost any topic you can think of. 
* [Flixel Features Demos](http://flixel.org/features.html) - See what Flixel is capable of and see the source behind all of the projects.
* [PhotonStorm's Flash Game Dev Tips](http://www.photonstorm.com/topics/flash-game-dev-tips) - Really amazing resources for making games in Flixel. Some of the early tips use an earlier version of Flixel, but it's still insanely useful.
* [EZPlatformer Tutorial](http://flashgamedojo.com/wiki/index.php?title=EZPlatformer_(Flixel)) - This is what got me started with Flixel. It's extensive and super useful. Start here and then see what you can do.
