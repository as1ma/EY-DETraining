# FrontEnd Masters - Intro to Web Dev
## HTML Course Notes

HTML stands for **hypertext markup language**. Simply put, it's the content on a webpage and the structure of that content. 

CSS stands for **cascading stylesheets**. It's the style of the website. 

JavaScript is a **programming language**. It was specifically invented for the purpose of running on webpages. It makes a webpage interactive, allowing dynamic content and user interactions. HTML and CSS are NOT programming languages. JS is the only language that can run directly inside web browsers like FireFox, Chrome and Safari.

<table><tr><td>

### Tags 
HTML's base building block is the tag. A tag is a building block. It describes what's inside it. Every tag has an opening and a closing tag (some tags open and close at the same point). Tags surround content to give it semantic meaning.  

Browsers aren't the only thing reading websites. Blind and people who can't see well will use screen readers to read web pages out loud to them; it uses things like headers to understand what information is important to read to the users. 

It's also how Google and Bing will understand the important details of your website. In other words, it's important which type of tag you use. More than just the visual aesthetic is using those tags.

Tag nesting involves placing one tag inside another, with the key rule being that the most recently opened tag must be closed first.

` <h1> This is a heading! </h1> ` Heading 1 (ranges from h1 to h6)
<h1> This is a heading! </h1>

`<div > This is a division tag </div >` Division tag - used for grouping together other things. In general, you want to group together "like" things into a containing tag (like a div) to keep them together. If you have a website with a list of blog posts that each have paragraphs, titles, images, etc. you'll group each post together in a div or other container-type tag typically.

For example: 
```<div style="width: 100px; height: 100px; background-color: red;"> a div example with style </div> ```

Would produce:

<div style="width: 100px; height: 100px; background-color: red;"> a div example with style </div>

`<p> This is a paragraph tag </p>` Paragraph tag - used to group and define blocks of text, similar to paragraphs in a chapter book.

`<a href = "">Anchor Tag</a>` Anchor tag is a link to somewhere else. 

`<span> </span>` A container for small pieces of text. If a div is like a cardboard box, a span is like a Ziploc bag. It doesn't change the styling of anything by itself but it allows you use CSS and JavaScript later to make that text different in some way. 

Example: 

```
<p>Here is some text. <span>This text is in a span</span> but it doesn't look any different.</p>

<p>This is <span style="text-decoration: underline">important</span> text</p> 
``` 
Produces:
<p>Here is some text. <span>This text is in a span</span> but it doesn't look any different.</p>

<p>This is <span style="text-decoration: underline">important</span> text</p>

ol, ul, and li – Both ol and ul represent lists. A ul is an unordered list: it's a list of things that could be shuffled and still mean the same thing.  An ol is an ordered list: what comes first matters. In either list, each item in the list is an li. 
Example: 
```
<ul>
    <li>Bob</li>
    <li>Eve</li>
    <li>Alice</li>
</ul>
```

<ul><li>Bob</li><li>Eve</li><li>Alice</li></ul>

`<button> Click me!</button> ` A button can be used by JavaScript to respond to a user clicking it.
<button>Click me</button>

`<img src = "source for image" alt="description of image for screen readers and search engine indexing>` The image tag is used to load images onto the page. CSS can also be used to bring in images but when the image is part of the content, it should be in an img tag. img tags are always self-closing tags.

`<input /> ` Input tag used for browser inputs from the user. You can also have these inputs do numbers, dates, colours, checkboxes, radio buttons, and others. 

```
<!-- these are the same, type="text" is the default -->
<input />
<input type="text" />

<input type="color" />
<input type="file" />
<input type="number" />
<input type="datetime-local" />
<input type="radio" /> #select only one option
<input type="checkbox" /> #select multiple options
```
<!-- these are the same, type="text" is the default -->
<input />
<input type="text" />
<input type="color" />
<input type="file" />
<input type="number" />
<input type="datetime-local" />
<input type="radio" /> 
<input type="checkbox" />

`<textarea></textarea>` This is similar to an input but for a lot more text. 
<textarea>example</textarea>


```
<select>
  <option value="seattle">Seattle</option>
  <option value="portland">Portland</option>
  <option value="san-francisco">San Francisco</option>
</select>
```
Limits a user to a certain group of options to select from. Select is a user-interactive input that a user can select an option from a dropdown menu. An option is one of the available options. Each option needs a value that will be sent back to the server if the user selects that option. 

Example:

<select>
  <option value="seattle">Seattle</option>
  <option value="portland">Portland</option>
  <option value="san-francisco">San Francisco</option>
</select>

```
<form>
  <input placeholder="First Name" />
  <input placeholder="Last Name" />
</form>
```
The form tag is a group of HTML tags related to gathering data from a user. You can then use this form element to send that data to your server. 

<form>
  <input placeholder="First Name" />
  <input placeholder="Last Name" />
</form>

```
<table>
  <tbody>
    <tr>
      <td>(0,0)</td>
      <td>(1,0)</td>
    </tr>
    <tr>
      <td>(0,1)</td>
      <td>(1,1)</td>
    </tr>
  </tbody>
</table>
```
table, tr, and td – Like making a table in Word or Excel. If you have a table of data, this is the best way to display it. The table is the container for the whole table, tr represents a row, and td represents one cell in the table. 
Example: <table><tr><td>(0,0)</td><td>(1,0)</td></tr><tr><td>(0,1)</td><td>(1,1)</td></tr></table>

</br>

Comments - You can leave little notes in your code that the computer won't read, it'll just ignore them. In HTML, the way you write a comment is `<!-- your comments go here -->`. Leave whatever notes you need in between the <!-- and the --> so that later you can come back to your code and remember what you were doing. 

`</br>` Linebreak tag - no longer the correct way.
</td></tr></table>

<table><tr><td>

### Attributes

Attributes allow you to modify behavior of an HTML tag. You've already seen a few of them but we'll go into a few more examples of them.

A really good example we have seen already is the href attribute of the `<a href="www.frontendmasters.com"></a>` tag. By modifying the href we're modifying what the tag does. It's contextual as well: href only works on a tags. You can't add a href to a div and expect to suddenly work as a link.

Another one we say is the type attribute on the input. By changing the type you're changing what sort of input is being shown.

There are other attributes like `class` and `id` that are universal and can be applied to (nearly) all tags. These themselves are inert; they don't do anything, but allow other things to find them later.

```
<h3 class="the-red-one">This one is red</h3>
<h3 class="the-blue-one">This one is blue</h3>

<style>
  /* don't worry about this yet, it's CSS */
  .the-red-one {
    color: red;
  }

  .the-blue-one {
    color: blue;
  }
</style>
```

</br>
<h5>Classes</h5>

Classes are more useful than IDs. You should use them 95% of the time. A class is reusable. Now I could create another tag (doesn't even have to be another h3) and that CSS style would be reapplied to it! You can also give multiple classes to one tag.

<h5>IDs</h5>
Classes are far more useful. However there are IDs that you may need occasionally. A key thing is that an ID is unique. Whereas I've already used the the-red-one class twice, you can't do with IDs. They're designed to not be reusable; they're unique to the page.

Again, in general, even if you happen to have just one of something, it's best to just use classes for everything and more-or-less pretend that IDs are not an option at all. You really only want to use IDs when something is unique and you want to make sure it stays unique. 
</td></tr></table>

<table><tr><td>

<h3>Organising HTML</h3>

`<div></div>` Generic divider
`<article></article>` A self-contained unit of information
`<section></section>` A larger macro unit or thematic grouping of content
`<nav></nav>` for navigation bar 
```
<nav>
  <ul class="nav-list">
    <li class="nav-list-item">
      <a class="nav-link" href="/">Home</a>
    </li>
    <li class="nav-list-item">
      <a class="nav-link" href="/news">Newsfeed</a>
    </li>
    <li class="nav-list-item">
      <a class="nav-link" href="/about">About</a>
    </li>
    <li class="nav-list-item">
      <a class="nav-link" href="/contact">Contact</a>
    </li>
  </ul>
</nav>
```

A leading slash in a URL path indicates navigation relative to the root domain, meaning the browser will start from the main domain and then follow the specified path.

</td></tr></table>

<table><tr><td>

<h3>Head and Meta Tags</h3>

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My Blog</title>
  </head>
  <body>
    <!-- all your content will go here -->
  </body>
</html>
```
Let's pick these tags apart one-by-one.

`<!DOCTYPE html>` - There have been several revisions of HTML. In any case, since your browser can understand several versions of HTML, put this at the top to signal to the browser that we're using the latest version.
`<html lang="en"></html>` - This tag is the absolute most root tag of an HTML document. Technically HTML is just a specific type of XML, this tag is necessary to signal to any reader this is actually an HTML doc (you never need to worry about that, just FYI.) Everything inside it will be interpreted as HTML. The lang="en" is the language you're writing your HTML in. Since this class is English, we're writing it in English. Specifically that's important to search engines so they know where to index your content. For our content we want English readers to see it.
`<head></head>` - All of your web pages are going to need important meta data. They need to tell browsers how to handle browser resizings, what character sets your page uses, what the title is, what the favicon is (the little logo on your browser tab), where the CSS is located, etc. The `<head>` tag (which is over the body tag, duh) contains all the important meta data. Nothing that gets displayed to the user (like a div or an h1) will ever be put in the head. It's just meta data.
`<meta>` - all these meta tags are giving the browser information of how to handle your documents
The `charset="UTF-8"` bit says that your document is written using the UTF-8 character set. This basically means you can use all character/letters/numbers/emojis/etc. that you expect to be able to use. Another example (that you would never use is) is ASCII (as in ASCII Art). ASCII is a much narrower set of characters that wouldn't have emojis for example. ASCII can't even do a lot of the characters you'd expect you'd be able to use like non-English accents. In other words, always include this line and never think about it. It's always UTF-8. 
`name="viewport" content="width=device-width, initial-scale=1.0"` - This is letting the browser know how specifically to handle mobile devices like phones and small tablets. If you don't put this, the browser may just output a really zoomed out view of your website and it's very hard to read. This allows you to have mobile browsers treat your content better and more like you'd expect. Always put this too.
`<title></title>` allows you to set the title that shows up on the browser tab. It will also be the title of the search result when people search for it on Google.
`<body></body>` All of your visible HTML will go here. Your divs, spans, tables, h1s, etc. all here.
This is the barebones skeleton of an HTML. You can literally just copy/paste this from project to project. Some of these things you can leave out but I don't recommend it. It makes the browser guess what you meants and that can vary how they guess from Safari to Edge to Chrome to Firefox, etc. Best to be explicit.

Let's talk about one second having multiple HTML docs in one project. Put this tag in the index.html we created.

`<a href="about.html">About</a>`
Then create a new file called about.html (must be in same directory) and put this in there:

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>About</title>
  </head>
  <body>
    <h1>About Me</h1>
    <a href="index.html">Go home</a>
  </body>
</html>
```
Now open index.html in your browser. You can either just drag the file onto your browser or you can use the CMD+O or CTRL+O shortcut to open the open dialog. Once you've done that, try clicking the links. You should it navigate between the two pages (if you put them in the same directory.) We'll take advantage of this in the project.


</td></tr></table>