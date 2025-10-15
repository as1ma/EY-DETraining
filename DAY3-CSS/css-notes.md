# FrontEnd Masters - Intro to Web Dev
## CSS Course Notes

 CSS is really powerful and can accomplish a wide variety of things: colors, sizes, order, positioning, hiding, showing, animation, etc.

 Like HTML, CSS is not a programming language. It's a list of rules that you give the browser. You'll provide rules to the browser like "all h1s will be colored red." 

 
<table><tr><td>

### Style
The most apparent way to use CSS is to effect visual changes on your HTML.

For example:
`<h1>This is an h1</h1>`

If we wanted to style it to be red:
```
h1{ 
    color:red;
}
```

<ul>
    <li>h1 — This is what we'd call the selector. Anything that matches this selector is going to have everything inside the { } applied to it. These selectors can be a wide variety of things but for now we're just selecting every h1 on the page. That's important to keep in mind too: it'll apply the changes to everything that matches that selector.</li>
    <li>color: – This is called the property. There are about ~350 properties that you can use but to be honest you'll never use all of them. The color property affects the color of the font (as well as some other things, but for now just assume it means font color.)</li> 
    <li>red – This is the value. This identifies what the value of the property is going to be. In this case, we're telling the color to be red. There are variety of ways to define color in CSS. This is called using "named color", of which there are about 150 different colors that CSS understands. CSS also understands hex values like #ff0000, rgb values like rgb(255, 0, 0), and hsl values like hsl(0, 100%, 50%). All those values I gave in the previous sentence are the same color as red. You don't actually need to understand how these values work to understand web programming or CSS and I would assert most web developers don't. If you need to understand, here's a great article on it from CSS Tricks.</li>
    <li>; – Every property-value pair will end in a semicolon. Think of it like a period/full-stop to end of a sentence. This is how the computer knows you're done with that property and moving on.</li>
</ul>

Links:
<a href="https://meiert.com/indices/css-properties/">CSS Properties</a>
<a href="https://css-tricks.com/nerds-guide-color-web/">CSS Tricks</a>


</td></tr></table>

<table><tr><td>

### Selectors and Cascade
Classes allow us to style the same tags (e.g. p, div, span, etc) differently because we can select the class instead of the tag. 

For example:

```
<style>
  .branding {
    color: red;
  }

  .blog-post-title {
    color: limegreen;
  }
</style>
<h1 class="branding">My Super Cool Brand</h1>
<h1 class="blog-post-title">My Cool Blog Post</h1>

```
Classes have a . (full stop) before the class name, and IDs use #. This is how you differntiate between a tag name, a class name, and identifier. 

Classes are the best way to style web pages. 

The **cacscade** defines rules for resolving conflicts between CSS rules, determining which styles take precedence when multiple rules apply to the same element. 

If we have two rules with the same class, the one that comes last applies. 

One tag can have multiple classes, and that can be useful. In the eyes of CSS, those two selectors are equal since they both have the same specificity. They both specific one class which makes them equal. So in this case, since .title comes last in the CSS, it wins. The color will be green. What about the border? Since .title doesn't conflict, it'll have a black border too. So keep in mind that each of these "conflicts" is resolved on a property-by-property basis. So the end result in an h1 that has a black border and green font.

```
<style>
  .main-brand-3.title-3 {
    color: red;
  }
​
  .title-3 {
    color: green;
  }
</style>
<h1 class="title-3 main-brand-3">Branding here</h1>
```
This how you add two classes to one selector. Notice there's no space between the two class names (that means something else.) The selector .main-brand.title will only match a tag that has both classes. If has only one of the two, it will not match. As you may imagine, since it has two classes, it's more specific, and therefore it wins.

A class is considered more specific than a tag. So a class selector "overpowers" a tag selector. It's more specific. ID selectors overpower class selectors.

</td></tr></table>


<table><tr><td>

### Pseudo-classes

Some times we want to change how elements look based on certain events that happen in the DOM. One of the most common ones is we want to change an element when someone hovers their mouse over it. Like this box:

The CSS we used for this is this:

<style>
  .hover-example {
    width: 100px;
    height: 100px;
    background-color: limegreen;
    color: white;
  }
  .hover-example:hover {
    background-color: crimson;
    width: 150px;
    height: 150px;
  }
</style>
<div class="hover-example">Hover your mouse over me</div>

```

<style>
  .hover-example {
    width: 100px;
    height: 100px;
    background-color: limegreen;
    color: white;
  }
  .hover-example:hover {
    background-color: crimson;
    width: 150px;
    height: 150px;
  }
</style>
<div class="hover-example">Hover your mouse over me</div>
```

The :hover part selects that element only when that condition is true. There are are many CSS pseudo classes: <a href="https://css-tricks.com/pseudo-class-selectors/"> pseudoclass selectors</a>

Pseudoelements:

Every element has a ::before and an ::after. You can use these pseudoelements to insert things there like we did with the fleuron.

```
<div class="chapter">This is a chapter of my book.</div>

<div class="chapter">This is a second chapter of my book.</div>

<style>
  .chapter {
    margin: 0;
  }
  .chapter::after {
    content: "❦";
    font-size: 50px;
    text-align: center;
    display: block;
  }
</style>
```
<div class="chapter">This is a chapter of my book.</div>

<div class="chapter">This is a second chapter of my book.</div>

<style>
  .chapter {
    margin: 0;
  }
  .chapter::after {
    content: "❦";
    font-size: 50px;
    text-align: center;
    display: block;
  }
</style>

</td></tr></table>

<table><tr><td>

## CSS Box Model

<h3>Display</h3>
Every tag in CSS has a display property associated with it by default. In fact, CSS has a lot of hidden defaults, just like by-default all text's color is black. With display, it varies by what type of tag we're talking about. divs are display: block; by default while spans are display: inline; and this makes sense given their functions. However, being that we have access to CSS, we can manipulate a span to act like a div and vice-versa (though usually you'd just use the appropriate tag.) We'll list out a few of the options here of what display can be.

<ul>
    <li>inline – Like it sounds, it makes whatever the tag is behave like text. If you want to style some text inline, this is how to do. The key here is the browser will determine all the height, width, padding, margins, etc. for you and will not let you change it. This is a common pitfall for those learning. If you have something and you're trying to set the width or height and it's not respecting it, it's probably the wrong display type.</li>
    <li>block – divs and ps by default are display: block;. This give you control over the height, width, padding, margins, etc. of something. By default, something that is block takes the whole line to itself.</li> 
    <li>inline-block – A hybrid of the previous two. This will make browser try to place the tag inline, but will still allow you to control the height, width, padding, and margins. </li>
    <li>flex and inline-flex – Similar to block in that it affects the tags around it like block does, however it gains some new super power on how its interior tags are layed out. There's a section where we'll talk about flex.</li>
    <li>grid and inline-grid – More advance display mode that allow you more power to layout tags inside of them. We'll have a section just on this too.</li>
    <li>table – Make something act like a table. In general, use the `< table>< /table>` tag instead of using CSS to make things act like tables.</li>
</ul>


### Height,Width, Border, Margin, Padding
<ul>
    <li>margin – This is the space outside of the element between it and other elements. It is outside of the border. If you give something a background-color, it will not color in the margin space. This is used to space elements out from other elements.</li>
    <li>border – Next is the border. If your element has a border, it comes next (not everything has or needs a border.)</li>
    <li>padding – Inside the border is the padding. This is the spacing inside the element. If you give something a background-color, you will color the padding space. In our diagram above, you can see the space between the red, solid border and the green, dashed border. This is the padding of the element.</li>
</ul>
    
Height can only be in pixels.


The wild card selector which is the one exception you should use:


```
* {
    box-sizing: border-box;
}
```

This will make everything use the border-box sizing instead of the default one (which is called content-box but you'll never have to know that.) This is the first thing I put in every project I start. You'll need it once in one file. This will make everything by-default be border-box and thus be easier to work with. 

### Floats
The old, bullet-proof way of laying things is using a property called float. The idea behind float is you'll tell an element to push itself as far left or right as possible, and once it's out of space, go to the next line.

</td></tr></table>

<table><tr><td>

## Flexbox

`display: flex` is a display mode for CSS. It's to note that when you stick display: flex, it allows you to change the layout inside the tag. It allows you to change the layout of its children. Externally, it acts just like block. Likewise there is a inline-flex which acts just like display: inline-block externally.

`flex-direction` 
`justify-content`
`align-items`
`flex-grow` determines the proportional size of flex items relative to each other. A flex-grow value of 5 will make an item 5 times larger than an item with a flex-grow value of 1.

</td></tr></table>


<table><tr><td>

## CSS Grid

`display: grid`
The latest-and-greatest way to do layouts with CSS. Grid shares a bit of similarities with flex but it's more oriented to making grids layouts as opposed to flex which is more flexible in terms of what you can get it to do. In short, grid is more useful for laying out a page (which are frequently grid-like) whereas flex is more flexible (if a bit more complicated) and is more useful when you have more unique layouts to achieve.

`row-gap and column-gap` are how you do gutters in grid i.e. the space between items in the grid 
`grid-template-column` allows you to set up how the grid is constructed. You can do it in percentages, pixels, or fr which stands for fractions. With two 1fr we made it so each piece will take 50% of the space minus the gutters which it will calculate for you. If we did 1fr 2fr 1fr the first column would take 25%, the second 50%, the third 25%. The math works like flex-grow.
Just like block and flex, there is an `inline-grid` too.


`grid-area` allows you to name a section and refer to it later as that. It doesn't need to match the class name (but it can, they have nothing to do with each other.)
`grid-template-areas` allows you to do a similar thing but to refer to the columns by name. As you can see here, it also allows us to have columns that reach across rows. Pretty neat.
The .  just refers to an empty cell.


</td></tr></table>


<table><tr><td>

## CSS Animations

CSS animations are a deep pool of knowledge and we're just going to look at a few of the techniques. You can achieve some truly amazing things with just CSS animations. You can also use JavaScript with CSS to make anything you can imagine.

Keyframes are reusable animations defined in CSS that allow you to specify different stages of animation using percentages or `from` and `to` keywords, enabling control over how an element transforms or changes during an animation.

CSS animation easing functions include: `linear` (constant speed). `ease` (starts and ends slowly), `ease-in` (slow start), `ease-out` (slow end), and `cubic-bezier` (custom animation curve that allows precise control over the animation's timing).

You can set the animation duration using seconds (e.g. 1.5s, 0.5s)  and the iteraction count using a number or `infinite`.

CSS Keyframes can animate multiple properties including rotation (`transform: rotate()`), position (translate), color, and many other visual characteristics of an element.

To write a basic CSS keyframe animation, use the `@keyframes` rule to define the animation stages, then apply the animation using the animation propertyt, specifying the name, duration, uteration count, and optional timing function.

```
<style>
  @keyframes spin {
    to {
      transform: rotate(360deg);
    }
  }
  .spinny-boi {
    animation: spin 0.5s infinite linear;
    display: inline-block;
    font-size: 30px;
  }
</style>
<div class="spinny-boi">🤢</div>
```

<style>
  @keyframes spin {
    to {
      transform: rotate(360deg);
    }
  }
  .spinny-boi {
    animation: spin 0.5s infinite linear;
    display: inline-block;
    font-size: 30px;
  }
</style>
<div class="spinny-boi">🤢</div>


The `@keyframes` part allows you to define a reusable animation. We could throw spin on anything now.
We just definte to which is what you want the end state of your animation state to be. We could define from too which is where you want your animation to start from. Implicitly if you don't define a from, your animation starts from where it is already. In this case, the spinny-boi isn't rotated at all, or transform: rotate(0deg). So it will rotate from 0 t0 360, or a full revolution. Feel free to play with it.
animation is the property to use a defined keyframe. Here we just say "do what spin defines, the whole animation should take a half second, do it infinitely (aka never stop), and do it in a linear fashion (so there's no speed-up or speed-down in the animation). This is a short hand. You can define the properties separately. See the MDN here.
Easing
Animation implies some sort of change over time. You're going from 0 to 1 in some capacity. The rate of change can be manipulated to achieve some cool effects. In the previous example you saw a linear function (these effects are called functions) where it's just a smooth line between 0 and 1. Let's check out the other possibilities.


```
<style>
  @keyframes move {
    to {
      translate: 50px;
    }
  }
  .dancer {
    display: inline-block;
    font-size: 30px;
    position: absolute;
    right: 0;
​
    /*
    this is the long way of doing:
    animation: move 1s infinite alternate;
    */
    animation-name: move;
    animation-duration: 1s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
  }
​
  .dancers-list {
    width: 100%;
    max-width: 300px;
    position: relative;
  }
​
  .linear {
    animation-timing-function: linear;
  }
  .ease {
    animation-timing-function: ease;
  }
  .ease-in-out {
    animation-timing-function: ease-in-out;
  }
  .ease-in {
    animation-timing-function: ease-in;
  }
  .ease-out {
    animation-timing-function: ease-out;
  }
  .cubic-bezier {
    animation-timing-function: cubic-bezier(0,1,.5,1);
  }
</style>
​
<ul class="dancers-list">
  <li>linear: <span class="dancer linear">💃</li>
  <li>ease: <span class="dancer ease">💃</li>
  <li>ease-in-out: <span class="dancer ease-in-out">💃</li>
  <li>ease-in: <span class="dancer ease-in">💃</li>
  <li>ease-out: <span class="dancer ease-out">💃</li>
  <li>cubic-bezier: <span class="dancer cubic-bezier">💃</li>
</ul>

```

  

### Beyond Positioning 
I've been showing you how to do this with positioning since it's the easiest to visualize. Many CSS properties are able to be animated so let's see one example here.

```
<style>
  @keyframes rainbow {
    100%,
    0% {
      color: rgb(255, 0, 0);
    }
    8% {
      color: rgb(255, 127, 0);
    }
    16% {
      color: rgb(255, 255, 0);
    }
    25% {
      color: rgb(127, 255, 0);
    }
    33% {
      color: rgb(0, 255, 0);
    }
    41% {
      color: rgb(0, 255, 127);
    }
    50% {
      color: rgb(0, 255, 255);
    }
    58% {
      color: rgb(0, 127, 255);
    }
    66% {
      color: rgb(0, 0, 255);
    }
    75% {
      color: rgb(127, 0, 255);
    }
    83% {
      color: rgb(255, 0, 255);
    }
    91% {
      color: rgb(255, 0, 127);
    }
  }
  .rainbow-boi {
    animation: rainbow 4s infinite linear;
    font-size: 30px;
  }
</style>
<div class="rainbow-boi">Rainbow</div>
```

<style>
  @keyframes rainbow {
    100%,
    0% {
      color: rgb(255, 0, 0);
    }
    8% {
      color: rgb(255, 127, 0);
    }
    16% {
      color: rgb(255, 255, 0);
    }
    25% {
      color: rgb(127, 255, 0);
    }
    33% {
      color: rgb(0, 255, 0);
    }
    41% {
      color: rgb(0, 255, 127);
    }
    50% {
      color: rgb(0, 255, 255);
    }
    58% {
      color: rgb(0, 127, 255);
    }
    66% {
      color: rgb(0, 0, 255);
    }
    75% {
      color: rgb(127, 0, 255);
    }
    83% {
      color: rgb(255, 0, 255);
    }
    91% {
      color: rgb(255, 0, 127);
    }
  }
  .rainbow-boi {
    animation: rainbow 4s infinite linear;
    font-size: 30px;
  }
</style>
<div class="rainbow-boi">Rainbow</div>


</td></tr></table>