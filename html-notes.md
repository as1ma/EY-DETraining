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