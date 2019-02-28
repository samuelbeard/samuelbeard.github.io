---
title: "Five CSS Buttons with Cool Hover Effects"
published: true
---

I was playing around with CSS transitions and put together these five experimental buttons that I thought looked pretty cool. The effects aren't over the top and can be used in a project quite nicely.

First of all, here is the CSS that is in the <code>button</code> element and, therefore, in all of these buttons.

```
button {
 margin:30px;
 color:#252525;
 font-family: 'Roboto Slab', serif;
 font-size:20px;
 cursor:pointer;
 transition:0.3s;
 }
```

## Button 1

<iframe width="100%" height="250" src="http://jsfiddle.net/TrueVineCS/t5j5hor0/embedded/result" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

```
#btn1 {
  padding:20px 50px;
  border:3px solid #252525;
  background:transparent;
}

#btn1:hover {
  background:#252525;
  color:white;
}
```

## Button 2

<iframe width="100%" height="250" src="http://jsfiddle.net/TrueVineCS/ayvgfek5/embedded/result" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

```
#btn2 {
  padding:20px 50px;
  border:3px solid #252525;
  background:transparent;
}

#btn2:hover {
  border-radius:20px;
}
```

## Button 3

<iframe width="100%" height="250" src="http://jsfiddle.net/TrueVineCS/9w2fefpn/embedded/result" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

```
#btn3 {
  padding:20px 50px;
  border:3px solid #252525;
  background:transparent;
}

#btn3:hover {
  box-shadow: inset 0 0 0 4px #252525;
}
```

## Button 4

<iframe width="100%" height="250" src="http://jsfiddle.net/TrueVineCS/x0ys65yy/embedded/result" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

```
#btn4 {
  padding:20px 50px;
  border:3px solid #252525;
  background:transparent;
}

#btn4:hover {
  -webkit-transform: rotateZ(-10deg);
  -ms-transform: rotateZ(-10deg);
  transform: rotateZ(-10deg);
}
```

## Button 5

This one is my favorite. It is just a mix of all of the other buttons.

<iframe width="100%" height="250" src="http://jsfiddle.net/TrueVineCS/5ppbbsp5/embedded/result" allowfullscreen="allowfullscreen" frameborder="0"></iframe>

```
#btn5 {
  padding:20px 50px;
  border:3px solid #252525;
  background:transparent;
}

#btn5:hover {
  background:#252525;
  color:white;
  border-radius:20px;
  -webkit-transform: rotateZ(10deg);
  -ms-transform: rotateZ(10deg);
  transform: rotateZ(10deg);     
}
```

You can see all the buttons together on CodePen here: [http://codepen.io/samuelbeard/details/nsboi](http://codepen.io/samuelbeard/details/nsboi)

If you want to show of any stylized buttons you have made or if you have improved on mine, link them in the comments or on Twitter @_SamuelBeard.
