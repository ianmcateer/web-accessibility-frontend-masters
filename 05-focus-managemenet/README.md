# Focus Management

https://learn-a11y.netlify.app/focus-management/index.html

we talked about different devices, screen readers, accessible html, wriitng either semantic html or how to use aria to update it

more advanced stuff now- we know what device fols use how do we think about building great accessible sites

focus management is for like keyboard only users eg if tab through site do i have some idea where i am through the site 

eg do i have that blue focus ring that comes with default on links and buttons, some way knowing where i am

to be compliant with webaim to be compliant whenever an elemenet receives focus it cant change the page dramatically, focus can be called when a user tabs to an element, and when input finromation it also doesnt change the page

we need a visual or screen reader safe indicator that the itema has focus html has .focus property 

also be careful dont change too much 

they keyboard will call focus itself 

# Keyboard Shortcuts

sites like tiwtter and facebook offor shortcuts for so mant actions

definitely more advanced,event listeners for js is whats required

# Skip Links

advaced technique as well 

skip links help users skip over large headers and navigation and jump right into the "main" content of your site

How to make a skip link
Create an anchor with the body "Skip to content"
Prepend it to the body of your website
Make it visually hidden
Give it a focus state which makes it visible

most sites have a nav, should have something to help user skip through it 

# Focus Management Q and A

chrome dev tools- lighthouse accessibility audit, then turning those into tickets and working on them, setup a linter for that 
react and angular have accessibility plugins 

basic linter and manually do a lighthouse run- dont d gingantic refactor 

really good resources that do accessibility audits for you 

# Tab Navigation 

advanced techniques involving js and css- keybor donly users will tab through the website

all page functionality is available through the keyboard

figure out what kinf ot hings will be tabbable? achros, buttons slects text areas and iframes

mostly its the interactive elements

can use tabindex attribute to make it tabbable

Tabindex values
a negative value means that the element should be focusable, but should not be reachable via sequential keyboard navigation;
0 means that the element should be focusable and reachable via sequential keyboard navigation, but its relative order is defined by the platform convention;
a positive value means should be focusable and reachable via sequential keyboard navigation; its relative order is defined by the value of the attribute: the sequential follow the increasing number of the tabindex. If several elements share the same tabindex, their relative order follows their relative position in the document.

complicated example eg navigation but one of those items is a ... and when click on it brings up a dropdown because the dropdown is a list of children the expected behaviour 

for most part- top level elements should be tabbable and then lists of chldren should be arrow keyable 

just something to keep in mind 

# Active Element

this will return the currently active element 

# Tab Trapping 

imagine have button makes modal

click on button and a modal opens up - the modal has a form to fill in 

tab trapping- grab first tabbable element and last tabbel element , listen for keyboard tab on the last element, if tab, then tab them back to the start

could get all focusable items, get first and last of array

and then add event listener for keydown 

test esc key to make sure can close the modal

## Skip Links Excercise 

making a skip link in this excercise

https://learn-a11y.netlify.app/exercises/4.html 