https://learn-a11y.netlify.app/aria/index.html

# Aria

Earlier, we learned about the <label> tag in HTML and how it can be used to label certain form elements.

The ARIA spec provides us with great tools for labelling and describing any element we want. They are:

aria-label
aria-labelledby
aria-describedby

label only works for labellable elements

aria provides us with three different tools for all this added context

aria and aria-labelled by do the same thing - they ad a label to something, the label is inline, the labelledby can pass it an id

described by gets into the more complex situations

the label is the essential information about the button

A label provides essential information about an object, while a description provides extended information that the user might need.

another part of aria is roles, states and properties

eg role = "button"

ARIA also provides roles which can be applied to any element. Examples include:

button
checkbox
tree
banner
aria-autocomplete
aria-haspopup

sometimes folks rebuilt checkboxes, but often lose alot of accessibility that comes with it
role="checkbox"

https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques

aria also supports state- bit more complicated

roles and labels pretty easy
but state and proeprties tricker bc they rely on application state

can use them in css selctors as well

```css
.dropdown[aria-expanded="false"] .icon::after {
  content: "▶";
}
.dropdown[aria-expanded="true"] .icon::after {
  content: "▼";
}
```

# Live Regios and ARIA Excercise

alot of apps are very dynamic

what about applications where something updates and need to catch attention of user eg sidebar loads in, somebody leaves comment on your post


Think of using the Uber app to hail a ride. At first your status will be "waiting for a ride" but at an undetermined time it will change to "drive en route". For this we could:

```html
 <div aria-live="assertive">Waiting for a ride</div>
```

whenever the inside content of that html chanegs it will read it alout to the user

One of my favorite APIs, the value that you pass in to aria-live is a politeness setting. You can pass in:

assertive - will interrupt whatever it's doing to announce.
polite - will announce the live region update when it next idles.
off - will not read the update.

example: https://learn-a11y.netlify.app/exercises/3.html 

# Aria Solution
