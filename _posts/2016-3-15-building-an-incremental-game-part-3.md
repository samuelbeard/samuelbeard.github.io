---
title: "Building an Incremental Game | Part 3"
published: true
---

![](https://github.com/samuelbeard/samuelbeard.github.io/blob/master/images/blogimg1.jpg?raw=true)

In [Part 1](http://samuelbeard.github.io/building-an-incremental-game-part-1/) we looked at clicking to make numbers go up; one of the fundamental features of incremental games. In [Part 2](http://samuelbeard.github.io/building-an-incremental-game-part-2/) we created objects and prepared ourselves for expanding the game. Now we are going to learn how to make the resources go up automatically.

## Displaying the Goods
Let us start by creating the button and numbers to create and display the Autoclickers. I have created this expansion on our game from part 1. It is still simple and, again, feel free to use it for your project.

<p data-height="268" data-theme-id="22779" data-slug-hash="ZWBKZv" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/ZWBKZv/">Building an Incremental Game | Part 3.1</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

I have placed `<!--ADDED-->` in front of the new lines so you can put them into your project if you are following along.

## The Javascript
First of all, here is what we are making:

<p data-height="268" data-theme-id="22779" data-slug-hash="MybmMO" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/MybmMO/">Building an Incremental Game | Part 3.2</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

As you can see, I have put `/ADDED/` above the part that is new. The only parts of the Javascript that aren’t new is the first variable and the ‘Click to Increment’ function at the bottom. I will go through each new part step by step.

## The Object
I have began a new object and a new variable with `var` just like the first one. There is a cleaner way of creating all of the variables with only one `var` but for ease, I will create them all individually so you can see what has been added.

Our first new variable is `autoClicker` and it has the properties of ‘amount’ and ‘cost’ which are 0 and ‘increment’, which is 1. So we start with no Autoclickers; to build our Autoclickers will cost nothing and they will click once each.

The next variable is `tick`. This will be how often the Autoclickers click. 1000 means 1000 milliseconds so 1 tick is 1 second.

## Run the Autoclicker
This function it technically a variable, hence the `var` at the beginning. But I am separating it because it includes the function that will make the Autoclickers click.

First we see `var runAutoClicker = setInterval(`. We created a variable that is equal to an interval that we are going to set. The setInterval is looking for two things inside the brackets after it. First, a function to run and then how often to run it.

So inside the brackets first we have `totalClicks += (autoClicker.increment * autoClicker.amount);`. This is a simple equation takes the amount of Autoclickers, multiplies that by the increment of clicks they do and adds that to your current number of clicks.

Then we see `$("total_clicks").html(totalClicks);`. This is just like the line from the function from part one. It updates the number on the screen of how many clicks you have.

After the curly brackets close we see `, tick)`. This makes this function repeat every tick. And we set the tick to 1 second.

## Buy Autoclickers
This function is even more simple than the last.

The `$('#autoClickerBuy').click(function(){` part waits for you to click the button with the id of ‘autoClickerBuy’ and runs the function.

`autoClicker.amount++;` adds one to the variable `autoClicker.amount`. Then the `$("#autoClickers").html(autoClicker.amount);` line updates the amount of Autoclickers on the screen so that the player can see.

## Making Autoclickers Cost Something
One last thing to do is to add a cost to the Autoclickers. They shouldn’t be cheap because they are a valuable commodity. Later, we will make it so that the Autoclickers increase in cost every time you buy one. But for now, they will cost 10 clicks.

<p data-height="268" data-theme-id="22779" data-slug-hash="MyboKQ" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/MyboKQ/">Building an Incremental Game | Part 3.3</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

In the example above, I have added to the ‘Buy Autoclickers’ function so that it looks to see if you have 10 or more clicks to spend before allowing you to buy an Autoclicker. This is shown in the `if (totalClicks >= 10){` part. Basically, this part says, ‘If the totalClicks is more than or equal to 10 then perform the part in the curly brackets.’

Also added is `totalClicks -= 10;`. This just takes ten clicks from for `totalClicks` becuase you have spent them. Then there is another `}` to close the if statement.

That is it for part three of this series. As always, take the code and mess around as you like. Send me what you have done so far and at the end of the series, I will show some of your work off.
