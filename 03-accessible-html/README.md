# Contents

https://learn-a11y.netlify.app/accessible-html/index.html

## Accessible HTML

alot of this stuff is just about using the tools that html already gives us

can do alot just by using the proper semantic elements

one patter see alot is fols will use divs for everything

while some of them provide semantics alot of them have alof of functionality built in

Some elements have semantic meaning but no special functionality. Examples are:

<aside>
<footer>
<header>

these might help SEO score but they dont really do anything, not going to add any extra utility to screen readers,
not going to add anythng like that

Other's provide a lot of built-in functionality such as:

<button>
<input>
<textarea>

if turn screen reader on

opt + ctrl + u can look at all the articles, can go to links to read all links on page
can go to headings and arrow through all the headings

use appriorate h1s

use text labels for input labels

## Accessibility Form Field Labels

labels are easy but big impact

form fields have accessiiblity issues all the time

```html
<form>
  <p>First Name</p>
  <input type="text" />
  <p>Last Name</p>
  <input type="text" />
  <p>Password</p>
  <input type="password" />
  <input type="submit" value="Submit" />
</form>
```

problem with this is screen reader will say "edit text blank"

becomes difficult if not impossible to use

html provides these label tags which will fix the problem

```html
<form>
  <label for="first">First Name</label>
  <input id="first" type="text" />
  <label for="last">Last Name</label>
  <input id="last" type="text" />
  <label for="password">Password</label>
  <input id="password" type="password" />
  <input type="submit" value="Submit" />
</form>
```

or..

```html
<form>
  <label>
    First Name
    <input id="first" type="text" />
  </label>
  <label>
    Last Name
    <input id="last" type="text" />
  </label>
  <label>
    Password
    <input id="password" type="password" />
  </label>
  <input type="submit" value="Submit" />
</form>
```

exception...

only certain elements which can be labelled

The label tag can only works with "labelable" elements. Those include:

<button>
<input>
<keygen>
<meter>
<output>
<progress>
<select>
<textarea>

If you ever need to label an element not on that list, use aria-label instead.

```html
<div aria-label="Interactive div">Hello</div>
```

should a label exist if there is no reason to see it? absolutely yes, give class visually hidden

when are aria labelled elements read by screen readers? if you take an element and add ability for it to be focused

when its focusable thats when add label to it

### Screen reader only content

Sometimes you'll want to communicate with a screen reader directly! One cool example is announcing to screen reader users that you offer accessibility features! In that case you can make some HTML and wrap it in a visually hidden class.

```css
.visuallyhidden {
  position: absolute;
  left: 0;
  top: -500px;
  width: 1px;
  height: 1px;
  overflow: hidden;
}
```

twitter- took a div , keybord shortcut, js to prepend that div to entire document , first thting screen reader seen

## Buttons

made a button here

```html
<button onclick="alert('hello')">Click me!</button>
```

an use a div as a button as well

could give the div a role of button

```js
<div role="button" onclick="alert('hello')">
  Click me!
</div>
```

issue with form fields and buttons is you can tab to them, can focus to them

so atm the iv wont be able to focus- can fix this by tab index

This will allow keyboard only users to tab to it.

```js
<div tabindex="0" role="button" onclick="alert('hello')">
  Click me!
</div>
```

but if keyboard only user cant click on the button, buttons also work if you enter on them , have to add an onkeyup

```js
<div
  tabindex="0"
  role="button"
  onclick="alert('hello')"
  onkeyup="alert('hello')"
>
  Click me!
</div>
```

but also dont forget about screen reader users either

```js
<div
  aria-label="Alert the word hello"
  tabindex="0"
  role="button"
  onclick="alert('hello')"
  onkeyup="alert('hello')"
>
  Click me!
</div>
```

hilights how much these semantic html elements do for us

## Accessibility Problems Excercise

https://learn-a11y.netlify.app/exercises/2.html 

fix the issues in this document

1. turn on screen reader to get a feel for the site and tab through a bit 

fixes:
- wrap the input in a label instead of using p element 
- use a button instead of a div
- add alt text to images
- add aria-label ot links so it has more context to it than what the link is

two different ways screenr eaders interact with site
1. read whole web page
2. if using links on the web rotor

great to add labels to those links 

role, tab index, mouse down, keydown make sure do all those on the div

is it better to use nav tag with anchors v ul with lis?

nav does provide some semantic meaning for sure

anything that takes you to new page is anchor 

prefer to use nav

if have buttons take you to new pages that is bad

what about if has form with submit button and submit button sends somewhere else, how do we tell the user?

within aria there are roles that can add to thngs eg hastransition, haspopup 

