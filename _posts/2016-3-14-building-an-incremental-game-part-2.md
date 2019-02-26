---
layout: post
title: "Building an Incremental Game | Part 2"
published: true
tags: [tutorial]
image:
        feature: incremental-game.png
---

Welcome back to this blog series where we are learning about how to make an incremental game. If you missed part 1, you can see it [HERE](http://samuelbeard.github.io/building-an-incremental-game-part-1/).

Today, we shall dive into Variables and Objects. We defined a variable in part one (var totalClicks = 0;) and that is pretty much all there is to it. But preparing variables in the beginning of a project the correct way will save you so much time in the long run. An object works the same way as a variable but goes deeper. We will get to them in a moment.


Here is an example of why objects work better than variables in a scenario like this:

_You build a game where you build houses. A house costs 100 wood so you write the code:_
```
houses++;
wood = wood - 100;
```

The first line adds one house to the amount of houses you have and the next line takes 100 wood away from your current amount of wood.

But what if you wanted to add an upgrade later on in the game that makes the cost of houses cheaper. You can’t change the ’100′ in the function because it is written in stone. It is not a variable. Instead, we need to define an object and put all the information about a house in it. Here is an example:

```
var house = {
    name = 'House',
    maxResidents = '4',
    cost: {
        wood: 75,
        stone: 25
    } // This is an object inside an object.
}
```

We have created the variable ‘house’ and added any information that may change throughout the game. So if you wanted an upgrade that made 5 residents live in one house instead of 4, you would write: `house.residents = 5;`. You have now changed that variable to 5. (I will get into upgrades and things like that at a later stage but it is good practice to prepare as soon as possible.)

Take a look at this example of an incremental game. You can create lumberjacks, miners and hunters to gather resources for you. At a later stage in the game, you may want to make them gather more resources per worker so we defined their increment as 1 and we can change that when ever we want.

<p data-height="268" data-theme-id="22779" data-slug-hash="PNbmKM" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/PNbmKM/">Building an Incremental Game - Part 2</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Feel free to fork this code and use it as you will. There is more code there than we have gone through so far so don’t worry if you don’t know what is going on. Have a fiddle with it and see if you can figure some of it out; it it a good way of learning.

The main gist of objects in an incremental game like this is to add everything that can possibly change. It is possible so go back and add objects later to things you have already made but it’s a pain to do so. Especially if you have a lot of stuff in your game.

Thank you for following part 2 of this tutorial. Part three will be along soon. In the mean time, if you are just starting out with Javascript and JQuery, I highly suggest doing the courses on [Code Academy](http://www.codecademy.com/). It will help you get to know the basics and you won’t get lost following these tutorials.

Feel free to show me your works based on this blog in the comments or send them to me on Twitter [@_SamuelBeard](https://twitter.com/_SamuelBeard).
