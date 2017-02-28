# Part 1: Anatomy of a Web Page

## How websites work
[https://projects.propublica.org/graphics/images/data-institute/presentations/how-websites-work.pdf](https://projects.propublica.org/graphics/images/data-institute/presentations/how-websites-work.pdf)

## Git and GitHub
A quick aside: [github.md](github.md)

## HTML, CSS, & JavaScript

* [HTML](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics)
* [CSS](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)
* [JavaScript](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
	* Quick aside: this is a great JavaScript tutorial for newcomers, it will only take 2 hours or so. http://jsforcats.com/

Simple website example: [https://dmil.github.io/simple-website/](https://dmil.github.io/simple-website/)

Simple website code: [https://github.com/dmil/simple-website](https://github.com/dmil/simple-website)

## A Simple Website

### Fork my simple website

1. Fork the simple website github repo
https://github.com/dmil/simple-website

2. Turn on github pages in your repository so that it can serve up the webpage. In your fork of this repository on github, there is a "settings" tab. Click that tab and under "github pages" set the "source" to the master branch.

4. Make sure its being served in github pages by navigating to the URL of the new site.

3. Clone your fork onto your desktop with the github desktop app.


### Inspect Element

1. Lets navigate to your website and explore the chrome developer tools for this simple website. How is it being put together?

### Manipulating the Site

Lets explore together what happens when we comment out different parts of the code (HTML, CSS, and JavaScript)

1. Open the folder containing this code in sublime text.
2. Find the folder where the code is and double click on `index.html` to open.
3. Watch on-screen, don't worry about making the changes yourself, we will have have some time shortly for you to try it yourself.

### Try It
1. Change the text of the headline
2. Change the image on the page to an image of your choice
3. Make the headline green
4. Change the behavior on the page. Right now when you click the image it says "Ouch, that hurt! Don't Poke Me" in an alert box. Instead make it so that when you click the headline, it says "Hey! You clicked the headline"

**Bonus**

5. When you're done with these things - discuss conceptually what you think is going on with your partner. 
6. Go bananas - have some fun modifying the website.


### Push your changes back to github

1. Open the github desktop app and add the files you modified to the "staging area"
2. Give the files a descriptive commit message and commit them to your local git repository.
3. Push the new commit back up to the remote repository by using the github desktop app to sync your local repository with your remote repository. 
4. View the changed website online. (changes will show up instantly on github, could take a minute or two to render on your website which is hosted by "github pages".

## CSS Selectors

CSS Selectors can be used among other things to:

- style the webpage
- select an element using javascript assign behavior to it
- select an element using javascript to manipulate it
- select an element on a page to scrape its data

CSS Selector Reference
[https://www.w3schools.com/cssref/css_selectors.asp]

### Types of Selectors

* element selector- https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Simple_selectors#Type_selectors_aka_element_selectors
* id selector - https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Simple_selectors#ID_selectors
* class selector - https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Simple_selectors#Class_selectors
* There are others, like attribute selectors

#### Try It
1. Navigate to my simple website: https://dmil.github.io/simple-website/
2. Click on the the "SelectorGadget" chrome extension
3. See if you can figure out selectors for the following
 - select the image on the page
 - select all quotes
 - select only the mainquote
 - select all paragraph elements
 - select only paragraph elements next to the image
 - select only paragraph elements that are not quotes

### Using selectors to manipulate the DOM (Document Object Model)

Open up the "console" window in chrome. This is a console where you can write javascript code. This snippet of javascript for example uses the `#profilepic` selector to grab the image on the page, and applies logic to make it disappear.

```
$$('#profilepic')[0].style.display = "none";
```

The following will loop through

```
for (var x of $$('p')) { 
    x.textContent="potato potato"
}
```

#### Try it
1. Make the first and second paragraphs disappear

#### Try It
Lets see if you can make potato google news

1. modify all the headlines
2. modify all the images
3. modify only the weather images
4. Modify the name of the publication, in my case I replaced the publication name with "The potato tribune"
![](https://www.evernote.com/shard/s150/sh/bf61354e-2416-4136-9cb1-8906ecc7bfd0/eabe485c7df04e41/res/b9c2acac-3fcf-4a14-aae4-627c23d4a09f/skitch.png?resizeSmall&width=832)

## Additional Resources
* Mozilla tutorials - whatever you want to learn about basic web dev, first check if there is a mozilla tutorial
* https://jsfiddle.net/ - for playing around with HTML/CSS/Javascript snippets
 