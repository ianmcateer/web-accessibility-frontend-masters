# Visual Considerations

## Color COntrast and Visual Impairments

color contrast comes up in a number of ways

lot of different impairmenets can make it difficult 

really difficult just to tell by looking at colors 

cool tools to help with this

lighthouse audit will tell you if any contrast issues

webaim contrast picker is good for designphase

tell if pass for aa compliance or aaa compliance 

https://webaim.org/resources/contrastchecker/ 

chrome dev tools also have built in accessibility color checker

oftne do fe validation on forms and if they fial they will make the border red

but proble is people with disabilities wont k

color is not the only way users can tell if there is an error, consider adding an icon or an error label

Visual Impairmenets

nocoffee for firefox simulates visual impairmenets

can understand how people visualise website 

## Set Language and Fixing Markup

WCAIG does need ot identify the language of the page

your html tag takes a lang property - this will flag in a lighthouse audit

recommend you find and fix and parsing errors 

w3 has a nice validator 

## Prefers Reduced Motion

at a high level all these apis in web now which start with prefers

give you access to specific os information 

eg if reduced motion is selected can now know on the web 

nice animation but if reduced motion do this instead - can do this in css

no page content flashes more than 3 times per second 

## Prefers Coloe Scheme and Visuals Excercise

alot of os these days including apple can set your color scheme 

no whave ability to read into this setting 

but some sites also have their own dark light toggle 

## Visuals Excercise 

https://learn-a11y.netlify.app/exercises/5.html 