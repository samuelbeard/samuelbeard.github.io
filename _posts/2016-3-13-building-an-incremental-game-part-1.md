---
title: "Building an Incremental Game | Part 1"
published: true
---

![Example Image for Post](https://github.com/samuelbeard/samuelbeard.github.io/blob/master/images/blogimg.jpg?raw=true)

Welcome to part one of Building an Incremental Game. In this series of blog posts I will show you the fundamentals to building your own game. I will be using Javascript and JQuery to make the magic happen and using the Twitter Bootstrap framework to make it look magic.

Throughout the series, I will try to make things as simple as possible so that anyone can get a grasp; even if you haven’t programmed before.

For those of you who don’t know what an incremental game is, it is a type of game where the goal it to get the most amount of resources as possible. First by clicking and then getting auto clickers to do it with you and upgrading everything and being economical. It sounds boring but it is amazingly addictive and really fun.

Check out [Cookie Clicker](http://orteil.dashnet.org/cookieclicker/); a very popular incremental game.

## The Play Field
How your game looks and what it’s about is entirely up to you. So just for something to work with, I’ve put together some buttons and text for teaching purposes. Feel free to copy it and change it however you want.

<p data-height="268" data-theme-id="22779" data-slug-hash="RaGYLM" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/RaGYLM/">Building an Incremental Game | Part 1 | The Play Field</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

On top of the above code, I have incorporated a Twitter Bootstrap theme.
If you are working in your browser on an app like CodePen, copy and paste this: `//netdna.bootstrapcdn.com/bootswatch/3.1.0/superhero/bootstrap.min.css` into External Resources.

Also, in order to use jQuery, we need to link it. To do this in CodePen, go to "Settings" > "JavaScript" then select jQuery from the "Quick-add" dropdown menu. (Don't select "jQuery UI")

If you are building in a text editor on your desktop then add this: `<link rel="stylesheet" type="text/css" href="//netdna.bootstrapcdn.com/bootswatch/3.1.0/superhero/bootstrap.min.css">` between your `<head></head>` tags. (For ease, I’ll be working in CodePen from now on and will refer to it when writing code.)

## Creating Variables
Variables are simply the parts of your code that are going to change. In this first part, the only variable we need is the total amount of clicks. This will then be displayed on the screen as you play (Once we tell it to).

Go ahead and type this into the Javascript section of the editor.

```
var totalClicks = 0;
```

The `var` part means we are defining a variable.
The `totalClicks` part is the name we are giving the variable.
The `= 0` part is what the variable value is. In this case, the total clicks is 0.
And the `;` is simply so the computer knows to stop reading that line.

## Click and Make the Number Go Up
The main part of, pretty much, every incremental game is to increment things (Duh). So let's make the `totalClicks` go up by one every time we click on the ‘CLICK ME’ button.

So let’s do the code.
<p data-height="268" data-theme-id="22779" data-slug-hash="RaGYLM" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/RaGYLM/">Building an Incremental Game | Part 1 | The Play Field</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

In the code we have our `totalClicks` set to `0`. Then we have a function. The first line of the function tells the computer to wait for #click to be clicked (Just like in css, # looks for an id in the HTML). Then it will perform what is in the curly brackets.

`totalClicks++;` means “Take the variable ‘totalClicks’ and add 1 to it”.
`$("#total_clicks").html(totalClicks);` means ‘Look for the element with the id ‘total_clicks’ and show the variable ‘totalClicks’ to it.
So basically, all these two lines are doing is adding 1 then showing the result every time the button is clicked.

So that is it for Part 1. I will carry on this series of tutorial for as long as it has interest. And don’t forget to post your game based on this tutorial in the comments below!
