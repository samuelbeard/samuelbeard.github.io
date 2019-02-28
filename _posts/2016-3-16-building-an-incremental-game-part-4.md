---
title: "Building an Incremental Game | Part 4"
published: true
---

![](https://github.com/samuelbeard/samuelbeard.github.io/blob/master/images/Untitled-1.jpg?raw=true)

Welcome to part 4 of this blog series. If this is your first visit here, you might want to check out [part 1](http://samuelbeard.github.io/building-an-incremental-game-part-1/), [part 2](http://samuelbeard.github.io/building-an-incremental-game-part-2/) and [part 3](http://samuelbeard.github.io/building-an-incremental-game-part-3/) first.

Today we are going to learn about upgrades. In the past tutorials, we made sure to keep everything in variables so that we can alter it if we wanted to down the road.

There is one thing that we are going to give the ability to upgrade but we didn’t make it a variable of it. The amount of clicks you gain every time you click. So let’s change this.

<p data-height="268" data-theme-id="22779" data-slug-hash="RaozeR" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/RaozeR/">Building an Incremental Game | Part 4.1</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

As you can see, the variable `clickIncrement` was added so, if we wanted, we can make it so you gain 100 clicks every time you click on the ‘CLICK ME’ button.

Also, a part of the ‘Click to Increment’ function has changed. We used to add 1 to `totalClicks` with the expression `totalClicks++;` but this could not be changed to add a different amount at any time. So the expression is changed to `totalClicks += clickIncrement;`.

## Styling
Before we make stuff do stuff, we need to add the buttons to the game. I have added two upgrades: ‘TWO CLICKS PER CLICK’ and ‘TWO CLICKS PER AUTO CLICK’. I’m sure it is pretty obvious that they are going to do.

<p data-height="268" data-theme-id="22779" data-slug-hash="QNGXzQ" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/QNGXzQ/">Building an Incremental Game | Part 4.2</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

## Upgrades
For now, we will make both of the upgrades cost 20 clicks each. We are going to make the upgrades do what they say they are going to do, take 20 clicks away from the total clicks and disappear once bought.

<p data-height="268" data-theme-id="22779" data-slug-hash="GZNbzr" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/GZNbzr/">Building an Incremental Game | Part 4.3</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

We have added two new functions that initiate when their respective button has been clicked. Let’s look at the ‘Two Clicks Per Click’ function line by line.

`if (totalClicks >= 20) {` Checks if we have enough clicks to spend.

`totalClicks -= 20;` Takes the clicks away as they have been spent.

`clickIncrement = 2;` Changes the variable clickIncrement to 2.

`$(this).addClass('hidden');` Adds the class ‘hidden’ to the button we clicked making it disappear.

Easy as that. Now every time you click, your total clicks goes up by 2. The ‘Two Clicks Per Autoclicker’ function is pretty much the same as the other new function. The only difference is the variable that is changed.

For those of you who were wondering, when you see `(this)` we are referring to the element that was clicked to start the function.

## Next Tier Upgrade
What if we wanted to add tiers to our upgrades. For example, when you by the ‘Two Clicks Per Click’ upgrade, you then have the option to buy ‘Five Clicks Per Click’ at a higher cost. Let’s do this now.

<p data-height="268" data-theme-id="22779" data-slug-hash="BKQgbd" data-default-tab="result" data-user="samuelbeard" class="codepen">See the Pen <a href="http://codepen.io/samuelbeard/pen/BKQgbd/">Building an Incremental Game | Part 4.4</a> by Samuel Beard (<a href="http://codepen.io/samuelbeard">@samuelbeard</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Three things have been added.

### 1.
A new upgrade button in the HTML that has the class ‘hidden’ so it is not visible at the start of the game.

### 2.
In the ‘Two Clicks Per Click’ function, the line `$('#upgradeFiveClicks').removeClass('hidden');` is inserted. When the ‘Two Clicks Per Click’ upgrade is bought, it will remove the ‘hidden’ class from the next upgrade making it visible.

### 3.
The ‘Five Clicks Per Click’ function was added. It is exactly the same as the Two Clicks function except it costs 100 clicks and change the `clickIncrement` variable to 5.

---

**Note**: The class ‘hidden’ is part of the bootstrap framework. If you are not using the bootstrap framework this won’t work. You can create your own ‘hidden’ class like this in your css:

```
.hidden {
 display:none;
 }
 ```

**Another Note**: Changing a class to ‘hidden’ is not the best way of removing elements but it is very easy for tutorial purposes. Look into [.remove()](http://api.jquery.com/remove/) for a better way.
