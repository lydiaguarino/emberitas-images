# Color Palette Tutorial
Emberitas Track One | July 16th, 2016 | Lydia Guarino, Instructor
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/Ember-Austin-Zoey-Half-sm.png?raw=true)

## Setting the stage

 Today we'll be playing the role of Front End Web Developer. We'll learn about how developers turn ideas and designs into fully functioning applications.

 We'll be following a typical developer workflow to turn a static image into a *real*, *live* application that our friends can play with on the web.

The interactive table of contents below outlines the entire tutorial and will allow you to quickly navigate to different sections and exercises. We recommend you follow the tutorial in order by scrolling through the page.

[TOC]

## Developer Workflow

### <i class="icon-star"></i> Phase 1 - *Requirements Gathering*
The first phase of any new project is to **understand the problem you are trying to solve**. This process is called **requirements gathering**. This process generally starts with understanding who **your users** will be and what they expect the application to do. Once you understand the needs of your users, you can start to make educated decisions about the **tech** and the **visual design** you want to use.
#### User Stories
User personas and user stories are cognitive tools designers and developers use to explore application needs from the perspective of the people who will be using the product.
> ##### **Zoey's User Persona**
> ![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/Ember-Austin-Zoey-Full-sm.png?raw=true)
*Name*: Zoey Tomster
*Profession*: Web Designer
*Traits*: **Values visual aesthetics**, Knows some HTML and CSS, Often uses software on **mobile devices** as well as her desktop computer when discussing projects with clients.

> ##### **Zoey's User Story**
> Zoey spends a lot of time as a visual designer experimenting with **color palettes**. She is frustrated that she doesn't have a good reference tool to help her store and share the color palettes she creates. **She needs a tool that will allow her to create, refrence, edit, delete and share color palettes with her teammates and clients.** Since she values visual aesthetics, it is important to her that the tool be easy to use as well as pleasing to look at.

#### Application Specs
Now that we are familiar with our user and her needs, we can start to make assumptions and decisions about what we should build. 

> ##### <i class="icon-pencil"></i> Exercise 1
> Review Zoey's user persona and user story. As a group, make some lists and sketches to brainstorm how Zoey might use an application to help her manage her color palettes. Here are some ideas to get you started:
> 
> 1. What types of screens or user interfaces might we need to build?
> 2. How will Zoey navigate between different screens?
> 3. Do we need to display groups of things? If so, what types of things?
> 4. What types of actions should Zoey be able to perform with the application?
> 5. What types of forms and buttons might we need to accommodate those actions?

> Time Box It: 10min

#### Wireframes
After discussing as a development team and consulting our UX designer, we've decided to build an application that uses two types of screens - a list view and a form. We gathered all of our decisions into some simple reference sketches and notes called "wireframes".

We came up with the following specifications for each screen:
> ##### <i class="icon-pencil"></i> Exercise 2
> As a group, review and discuss the specs and wireframes outlined below.

>Time Box It: 10min
> 
> ##### **List View Specs**
> 1. The list view should be our landing page - the first page the user sees when they visit the application
> 2. The list view should have three sections: A heading, a way to navigate to the new palette form and a list of the saved palettes.
> 3. The list of palettes should be a preview of the colors and should show the RGB color value when you hover over an individual color.
> 4. Each palette preview should link you to the palette edit page.
> 5. Each palette will have up to five individual colors.
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/list-view-wireframe.jpg?raw=true)

> ##### **Form View Specs**
1. The form should have six sections: A heading, a place to specify the palette name, a palette preview, a place to edit the individual colors in the palette and a form actions section with some buttons.
2. Clicking on a color in the palette preview should populate the edit color section.
3. The edit color section should let the user input the Red, Green and Blue component values of an RGB color code with text or with a slider input.
4. Changing the RGB values should automatically update the preview to show the new color.
5. The form should be able to be used to create a new palette or to edit an existing palette.
5. There should be three actions - Cancel, Delete and Save
6. Cancel should throw away any changes on the form and return the user to the list view.
7. Delete should completely delete the palette and return the user to the list view. Delete should be disabled if the user is creating a new palette.
8. Save should create a new palette or save the changes made to an existing palette and return the user to the list view.
 ![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/form-wireframe.jpg?raw=true)

#### Comps

Now that we have our basic ideas nailed down, it's time for some aesthetic polish. Conveniently, Zoey is a talented web designer and was able to turn our wireframe sketches into some Comprehensive Layouts, or "comps" that we will use to start coding and styling our application.

> #####**Final comps for our application**
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/comps.png?raw=true)

> #####**Colors**
dark gray ```#1C1F24``` *- this is called a color hexcode*
light gray ```#586073```
red ```rgb(217,33,32)``` *- this is an RGB (red, green, blue) color code*
orange ```rgb(231,116,47)```
yellow ```rgb(223,165,58)```
lime ```rgb(177,190,78)```
green ```rgb(109,179,136)```
light blue ```rgb(70,131,193)```
dark blue ```rgb(63,78,161)```
purple ```rgb(120,28,129)```
black ```rgb(0,0,0)```
white ```rgb(238,238,238)```

> ##### **Special Fonts**
>Google Fonts - [Pacifico](https://www.google.com/fonts#UsePlace:use/Collection:Pacifico)

> ##### **Special Elements** 
> [Twitter Bootstrap Responsive Grid System](http://getbootstrap.com/2.3.2/scaffolding.html#gridSystem)
> [Twitter Bootstrap Button Groups](http://getbootstrap.com/2.3.2/components.html#buttonGroups)

### <i class="icon-star"></i> Phase 2 - *Coded Comps - HTML, CSS, Intro to Bootstrap*
#### Marking up the content - HTML
The very first step in building our application is to convert Zoey's awesome designs into code that our browser understands.

Your browser is a piece of software on your computer or mobile device that lets you access content or use applications that are shared over the internet. Chrome, Firefox and Internet Explorer are examples of web browsers. Browsers follow a set of rules or *protocols* to communicate with servers where data and information is actually stored. 

The most common of these protocols is called HTTP or *Hyper Text Transfer Protocol*.   With HTTP, information is requested by the browser or *client* when you visit a URL (like Google.com) and a server (just another computer somewhere) responds with the requested information in the form of some text. That text is then interpreted by the browser and rendered to your screen. 

Your browser knows how to interpret three main types of text returned from a server- HTML, CSS and JavaScript

A good way to think about the roles of each of these types is:
1. **HTML** - Provides the structure and semantic outline of a webpage
2. **CSS** - Works in collaboration with HTML to tell the browser how to style elements on the page
3. **JS** - Allows you to script interactions on the page like clicking a button or rotating content in a slide show

> ##### <i class="icon-pencil"></i> Exercise 3
> Web pages don't start out pretty. They start out as simple text. A web developer then gradually adds layers of markup, styling and interactions to that text to produce the rich experience you get when working with applications on the internet.
>
> The first step in this conversion is to wrap the text-based content of our page in HTML *tags* which tell the browser the purpose of that text. 
> 
> **Use the instructions below to outline the structure of our two pages using HTML.**
> 
> What you will need: 
> 1. A text editor - we recommend [Atom](https://atom.io/) or [Sublime Text](https://www.sublimetext.com/), which are both free
> 2. A browser - we recommend [Google Chrome](https://www.google.com/chrome/browser/desktop/index.html)
> 
> Time Box It:  30min

###### **Step 1 - Getting Started**
Open your text editor and create a new directory (folder) called "emberitas". 
Create the following empty files:
```
emberitas
	palettes.html
	palette.html
```

###### **Step 2 - Starter Structure**
HTML tags look something like this:
```
<tag> Content </tag>
```

Almost all HTML documents start with a similar basic structure. Copy the following starter code into each of your two new empty html files. Update the author meta tag to use your own name:
``` 
<!-- this is an HTML comment. It is invisible. -->
<!-- tell the browser this is an html document -->
<!doctype html>
<html lang="en">
	<head>
	  <!-- give the browser some info about this document -->
	  <meta charset="utf-8">
	  <!-- standard settings for mobile devices -->
	  <meta name="viewport" content="width=device-width, initial-scale=1">
	  <!-- Displayed in the browser tab header -->
	  <title>Emberitas Color Palette</title>
	  <!-- This is frequently used in search results -->
	  <meta name="description" content="Emberitas Practice App">
	  <!-- You are the author -->
	  <meta name="author" content="Lydia Guarino">
	</head>
	
	<body>
		<!-- This is where all of our code will go -->
	</body>
</html>
```
###### **Step 3 - HTML Tags**
We are now ready to add our basic layout content between our body tags. Notice how content can be wrapped in different levels of **nested** tags. There are [a ton of tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) that the browser understands. Let's focus on a few we will need for our application.

- `<h1>...</h1>`
The most important headline on your page.
usually the page title.

- `<h2>...</h2>`
A subheading or the second most important headline on your page
usually a section title.

- `<button type="button">...</button>`
A clickable button.

- `<a href="palette.html">...</a>`
An link or *anchor* tag that allows you to wrap any element on the page and make it a clickable link. The href attribute specifies where the link should take the user. In this case, we want to link to another file in our current directory (folder) - but you can also use the href attribute to link the user to any URL.

- `<form>...</form>`
A special wrapper tag for content that will be part of a form (usually input tags).

- `<input type="text" placeholder="New Palette">`
A text input field.

- `<input type="range" step=1 min=0 max=255>`
A slider or range input.

- `<input type="submit" value="Save">`
The button that controls submitting a form. The value attribute will be displayed as the button text.

- `<div>...</div>` 
The workhorse of the HTML tags. Use divs for your different site sections, sidebars, footers, etc. Divs are the primary way to group related elements together.

- `<span>...</span>`
Span tags allow you to group inline elements. Spans are useful for wrapping elements that might receive different CSS styling than their surroundings.

> **Using the tags listed above, take a first pass at building our two pages. To view your page, simply open it in your browser. They should look something like this:**

palettes.html
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/palettes-raw-html.png?raw=true)

palette.html
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/palette-raw-html.png?raw=true)

###### **Step 4 - Inline Styling**
Adding inline CSS styles is a quick and easy way to add some fancy improvements to our HTML, like color. Let's try making all of our color buttons...colorful!

You can add a *style* attribute to any HTML element. This special attribute lets you add CSS styling directly to the element. Let's try making one of our buttons red by specifying the background-color.

```
<button type="button" style="background-color:rgb(217,33,32)"> 217,33,32 </button>
```

> **Add style attributes and set the background-color on each of the buttons representing colors. They should look something like this:**
 
 palette.html
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/palette-html-only.png?raw=true)

>Take a break if you need one!

#### Working with responsive frameworks and libraries- intro to Bootstrap
HTML is awesome. Inline styles - even MORE awesome, but I bet you are starting to realize that if you had a really complex application, it would get very tedious to have to individually style every single element on the page - and what if you wanted to change the way ALL the buttons looked in your entire application? It would get completely unmanageable. **There must be a better way - and there is.**

The fastest option? Use someone else's styling! There are several libraries and responsive frameworks you can add to your project to give you a fast leg up on styling your application.

[Twitter Bootstrap](http://getbootstrap.com/2.3.2/index.html) is an incredibly popular *responsive framework*. Responsive frameworks provide advanced styling to help you to build applications that will look good on giant desktop monitors, laptop screens, tablets and smaller mobile devices, all without having to write totally different styling for each size screen.

Most of these frameworks rely on a [grid system](http://getbootstrap.com/2.3.2/scaffolding.html#gridSystem) to determine how elements should be displayed at different screen sizes. Bootstrap uses a 12 column grid. This means the main content of your page *(container)* is divided up into 12, invisible, equal-width vertical sections *(columns)*. Content is also grouped into horizontal sections using *rows*. You can then use this *grid* to specify how many columns an element should take up at various screen sizes. 

Bootstrap uses an HTML tag attribute called a **class** to apply the grid and any component styling you might like to use.

The structure looks something like this:
```
<div class='container'>
	<div class='row'>
		<div class='col-xs-12 col-sm-6 col-md-6 col-lg-4'></div>
		<div class='col-xs-12 col-sm-6 col-md-6 col-lg-4'></div>
		<div class='col-xs-12 col-sm-12 col-md-12 col-lg-4'></div>
	</div>
	<div class='row'>
		<div class='col-xs-12 col-sm-6 col-md-6 col-lg-4'></div>
		<div class='col-xs-12 col-sm-6 col-md-6 col-lg-4'></div>
		<div class='col-xs-12 col-sm-12 col-md-12 col-lg-4'></div>
	</div>
</div>
```
Bootstrap groups screen sizes into four categories: xs, sm, md, lg - representing phones, tablets, standard laptop screens and much larger screens - respectively.

In this example, each div takes up the *full width* of the screen on mobile devices, *half* the screen on tablets and laptop screens and a *third* of the screen on very large screens.

> ##### <i class="icon-pencil"></i> Exercise 4
> In this exercise, we'll be adding Twitter Bootstrap to our project and using the responsive grid and several *component classes* to pretty-up our application.
> 
> **Use the instructions below to add Bootstrap and build the styling foundation for our application.**
> 
> The Bootstrap **component** docs can be found [here](http://getbootstrap.com/2.3.2/components.html).
> The Bootstrap **grid** docs can be found [here](http://getbootstrap.com/2.3.2/scaffolding.html#gridSystem).
> 
> Time Box It:  15min

###### **Step 1 - Linking a stylesheet**
To start using Bootstrap, simply add the following link tag to the head of your html (a good spot would be after the author meta tag) on both pages:
```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
```
This special HTML tag tells your browser to request the bootstrap.min.css file from the Bootstrap servers and load it with your project when your page loads. 

If you refresh your browser window, you should already see some styling changes including a new font and some nicer-looking inputs and buttons.

###### **Step 2 - Organizing content with divs and grid classes**
Based on Zoey's designs, we want the main content of our pages to be centered and we want it to automatically adjust to an appropriate width on different screen sizes. Zoey would like the content to take up the **full width** of the page on xs devices (This is a default! Yay!), about **two-thirds** of the page on sm devices and **half** the page on md and lg devices. 

To keep the content centered at various sizes, we will need to use some offset classes to help push the content into the middle columns.

Our columns will work like this:
```
xs |------------| 12 = 12 			(use all 12 cols)
sm --|--------|-- 2 + 8 + 2 = 12 	(8 cols offset by 2)
md ---|------|--- 3 + 6 + 3 = 12 	(6 cols offset by 3)
lg ---|------|--- 3 + 6 + 3 = 12 	(6 cols offset by 3)
```

To achieve this, we simply wrap our existing page content in the following HTML div tags with some classes added that Bootstrap knows how to style:
```
<body>
	<div class='container'>
		<div class='row'>
			<div class='col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 '>
				<!-- The rest of our existing page content -->
			</div>
		</div>
	</div>
</body>
```

Once we've added these new classes, our content should be centered and we should be able to watch the content width adjust when we resize our browser window.

> <i class="icon-mobile"></i> If you want to get really fancy, you can right click anywhere in your Chrome browser window and choose "Inspect". This will open up the developer inspector tool - a tool web developers use to gain more useful insights into what the code is doing under the hood.

> Next to the "Elements" tab heading, there is a mobile device icon that will let you simulate what your page looks like on different standard device sizes.

###### **Step 3 - Adding component classes**

When reviewing Zoey's design, did you notice that she reused the same bar-like styling for all of the palette previews and for the buttons on our page?

These *bars* are an example of a Bootstrap component. Components are similar to the grid, in that they are just combinations of classes applied to our HTML elements that Bootstrap knows how to style. You can find all kinds of useful component classes that Bootstrap includes in its *kit of parts*, [here](http://getbootstrap.com/components/#btn-groups).

Reviewing the Bootstrap docs, it looks like the component we want to use is called a **button group**. We've already got our buttons added to our HTML code. Let's try refactoring (or editing) the buttons to add a wrapper div and the Bootstrap classes that will give us that nice button bar styling:

```
<div class="btn-group">
  <button class="btn" type="button" style="background-color:rgb(217,33,32)">217,33,32</button>
  <button class="btn" type="button" style="background-color:rgb(231,116,47)">231,116,47</button>
  ...
</div>
```

Another component class we'll want to use is for **styling text inputs**. Add the `form-control` class to all of the **text** inputs on our form. Once you've successfully added the btn-group, btn and form-control classes, your pages should look something like this:

![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/bootstrap-button-groups.png?raw=true)

> Take a break if you need one!

#### Styling the content - CSS

Let's take another look at Zoey's designs:

![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/comps.png?raw=true)

Bootstrap helped us position our content on the page and gave us some helpful component styling, but our pages still look pretty different from Zoey's designs. 

We already know that we could go edit the styling for each element directly in our HTML using the style attribute, but that sounds pretty inefficient and incredibly difficult to maintain.  

We learned in the last exercise that Bootstrap uses *classes* to apply styles to a bunch of elements all at once. As long as the element has the correct class, Bootstrap will correctly apply to appropriate styling. 

> How does this work?
> 
>Remember that `<link>` tag we put in the head of our HTML documents? That link tag told our browser that we wanted to load some CSS or a "Cascading Style Sheet" along with our page. 

>That CSS document is a list of *selectors*, which can be HTML tags (like `<h1>`), classes (like `btn-group`) or a third type called an `id`, which is used for identifying and styling individual elements (the special snowflakes).  CSS then uses some special syntax to list out the style attributes that should be applied to any elements that match the selector.

Structure:
```
[selector name] {
	[style attribute name] : [value];
	[style attribute name] : [value];
	[style attribute name] : [value];
}
```

Example with a tag selector:
```
h1 {
  font-family: 'Pacifico', cursive;
  font-size: 70px;
  margin-top: 50px;
  padding-bottom: 20px;
  text-align: center;
}
```

Example with a class selector (note the "." at the beginning of the class name):
```
.color-text-input {
  width: 20%;
  margin: 2%;
  display: inline-block;
}
```

Example with an id selector (note the "#" at the beginning of the class name):
```
#my-specific-element {
  background-color: #1C1F24;
  color: #586073;
}
```

> ##### <i class="icon-pencil"></i> Exercise 5
> Time to get fancy! In this exercise we'll be writing our own custom CSS to bring Zoey's designs to life.
>
> As a group, take a look at Zoey's designs. What types of elements or patterns are repeated? Could those be grouped as a class? Start to make a list of the classes you think you might need.
>
> To get you started, here is a comprehensive list of style attributes you will need to use to complete the styling for Zoey's designs:
> 
> **Colors and Outlines:**
> `background-color` `color`  `opacity` `border`    
>
> **Fonts:**
> `font-family` `font-size` `text-align`
>
> **Sizing:**
> `width` `height`
>
> **Positioning:**
> `margin-top` `margin-bottom` `padding-top` `padding-bottom` `display` `vertical-align`
> 
> **Use the instructions below to link a new stylesheet and write some custom CSS**
> 
> Time Box It:  30min

###### **Step 1 - Adding a CSS file and linking it**
Open your text editor and create a new file to your emberitas directory called "style.css" 
```
emberitas
	palettes.html
	palette.html
	style.css
```

In the head of each of your HTML files, add another link tag, this time linking our new style.css file. Note that this new link tag should be listed *beneath* the Bootstrap link tag. This will allow our custom styles to *override* any Bootstrap styles.

```
<link rel="stylesheet" href="styles.css">
```

To test it out, let's add some CSS to our new file and observe how it impacts our pages.

Add the following to your style.css file:
```
* {
	border: 1px solid magenta; 
}
```
Save the file and refresh your browser window. Every element on your page should suddenly be outlined in pink! This is a helpful trick to get a quick glimpse at how your page is currently organized. The "*" is a wildcard selector that means "all the things". 

You can also open the inspector again, by right clicking in your browser window and selecting inspect. The Elements tab will show you the HTML and also the styles being applied to items on the page. In the top left of the inspector window, there is a little arrow that will let you hover over elements on the page and view specific details about them.

When you've had enough of the pink outline, simply remove that code from your CSS file.

###### **Step 2 - Adding a Google font**

Zoey is a typography nerd. She has specified a fancy font called 'Pacifico' that she would like for us to use for the page titles. She has chosen a Google font, which we can link in our HTML head, just like our other stylesheets! 

The [Google fonts site](https://www.google.com/fonts) has wonderful documentation on how to add a font to your project. Simply search for the font you want to use and click "Add to Collection" for more instructions.
```
  <link href='https://fonts.googleapis.com/css?family=Pacifico' rel='stylesheet' type='text/css'>
```

Let's go ahead and apply our new font, along with some sizing and positioning attributes to the `h1` elements in our application:
```
h1 {
  font-family: 'Pacifico', cursive;
  font-size: 70px;
  margin-top: 50px;
  padding-bottom: 20px;
  text-align: center;
}
```

###### **Step 3 - Adding smart styling defaults**
The biggest difference between Zoey's designs and our pages is that our pages are white, while Zoey has specified a dark color scheme for the majority of the application.

CSS, or Cascading Style Sheets are particularly useful because the order in which the HTML selectors appear in your list of styles makes your styling *additive*. 

For this reason, you usually structure your CSS files from least specific to most specific selectors. This lets you create smart defaults. Elements wrapped by styled elements (child elements) will inherit from their wrapper (or parent) element.

Additionally, any styles listed further down in your CSS file will override styles specified higher up in the file. This is how we are able to override the Bootstrap styles by linking our custom CSS file after the Bootstrap file.

Let's start our smart defaults by setting the color scheme on the entire `body` element:
```
body {
  background-color: #1C1F24;
  color: #586073;
}
```
Let's also set a smart font-size default for all the `h2` tags in our application:
```
h2 {
  font-size: 18px;
}
```
Finally, we already know that our Bootstrap `.btn-group` elements are repeated throughout the app. Let's add some smart overrides to start making our application look more uniform:
```
.btn-group {
  width: 100%;
  margin-bottom: 12px;
  margin-top: 12px;
}
```

###### **Step 4 - Adding custom classes**

Things are starting to look pretty good! Let's spend some time focusing on our palette preview button groups. It looks like we basically have two representations of a color palette - One with colors, and an empty one that doesn't have any color blocks yet. Both are shaped the same, with five equally sized sections, but there are some slight differences in border styling.

Let's start by creating a new custom class called `color-palette` that we will apply to all the button groups we're using as color-palette previews.

```
<a href="palette.html" class="btn-group color-palette">
	<button ... >217,33,32</button>
	<button ...>231,116,47</button>
	<button ...>223,165,58</button>
	<button ...>177,190,78</button>
	<button ...>109,179,136</button>
</a>
```

We'll also add the color-palette class to our empty color palette, but we'll give that element an additional custom class called `.empty-palette`

```
<h2>Add a Palette</h2>
<a href="palette.html" class="btn-group color-palette empty-palette">
	<button class="btn" type="button"></button>
	<button class="btn" type="button"></button>
	<button class="btn" type="button"></button>
	<button class="btn" type="button"></button>
	<button class="btn" type="button"></button>
</a>
```

Now that we have custom classes add to our HTML, we can edit the styles that the elements will share.

```
.color-palette .btn {
  width: 20%;
  height: 50px;
  border: none;
  font-size: 10px;
  color: transparent;
}
```
Hmmmmmm. That's odd. There's a second class listed in our selector!
> CSS selectors can be chained. The notation above means "find all the elements with the `.color-palette` class and then drill down to all of the nested elements *inside* that element that have the `.btn` class and apply the following styles to those elements.
>

Let's take a look at one more example. Here, we're using the same nested selector `.color-palette .btn`, but we're adding one more layer of specificity using a *pseudo-class*, which is essentially a conditional class that gets applied when the user interacts with different elements on the page, such as hovering over an element.

```
.color-palette .btn:hover, .color-palette .btn:focus {
  color: #1C1F24;
  border: 2px solid #1C1F24;
}
```
You can apply the same style to several different selectors by separating them with a comma. Save and refresh your browser window. What happens when you hover over one of the color buttons now?

Finally, let's add the styling for our special empty-palette. Remember, order matters in your CSS file.
```
.empty-palette .btn {
  background-color: transparent;
  border: 1px solid #586073;
}

.empty-palette:hover .btn {
  border: 1px solid white;
}
```
> ##### <i class="icon-star"></i> Challenge Time!
> Use the following custom classes and style attributes to style the rest of the palette form:
> 
> **Custom classes and nested selectors**
> ```
> .palette-name-input {}
>.preview-tile {}
>.color-input-group {}
>.color-input-label {}
>.color-text-input {}
>.color-input-group .color-range-input {}
>.fom-actions .btn {}
>.form-actions .btn:hover {}
>```
>
> **Style attributes and values**
> ```
> width: 10%;
> width: 33.3%;
> width: 20%;
> width: 68%;
> width: 100%;
> height: 50px;  
> margin: 2%;
> margin-top: 12px;
> margin-top: 18px;
> margin-top: 24px;
> margin-bottom: 6px;
> margin-bottom: 18px;
> margin-bottom: 24px;  
> padding: 12px;  
> color: white;
> background-color: #586073;
> border: 1px solid #1C1F24;
> font-size: 24px;
> vertical-align: middle;
> display: inline-block;
> opacity: .8;
>```


# Color Palette Tutorial
## Part 2 - Converting to Ember
Emberitas Track One | July 16th, 2016 | Lydia Guarino, Instructor
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/Ember-Austin-Zoey-Half-sm.png?raw=true)


---------

Ember is a front-end javascript framework. Now that we have a little bit more context around what a framework is, let's learn about how to convert our *static* webpages to a *dynamic* web application with Ember.

--------

## Getting Started

To start a new ember application, open your terminal window and run the following command from within the directory where you want your project to live.

`ember new color-palette`

Do some dancing while you wait for the application dependencies to install.

----

Next, change directory (cd) into your newly created ember project directory. 

`cd color-palette`

To test that everything is working as expected, start your local server by running the following command from your command line:

`ember server`

Open your browser and navigate to the following URL, where your local server is currently running the ember application:

`http://localhost:4200`

If you see "Welcome to Ember" or a happy little Tomster hamster, congrats! You have successfully created an Ember application!


---
## How to kill your server

To avoid confusion, let's kill our server for now by pressing the `control` and `C` keys at the same time (on Mac) from within our terminal window.

You will need to remember this command to stop your server if you need to restart it because you are seeing odd errors or so that you can easily run other commands from the terminal. 

To restart your server, you'll simply run `ember server` again.

-----

## Understanding the Ember Router


>From the Ember docs:
>
>Imagine we are writing a web app for managing a blog. At any given time, we should be able to answer questions like What post are they looking at? and Are they editing it? In Ember.js, the answer to these questions is determined by the URL.

>The URL can be set in a few ways:

>The user loads the app for the first time.
The user changes the URL manually, such as by clicking the back button or by editing the address bar.
The user clicks a link within the app.
Some other event in the app causes the URL to change.

>Regardless of how the URL becomes set, the Ember router then maps the current URL to one or more route handlers. A route handler can do several things:

>It can render a template.
It can load a model that is then available to the template.
It can redirect to a new route, such as if the user isn't allowed to visit that part of the app.
It can handle actions that involve changing a model or transitioning to a new route.

------

## Routes

Since the Ember Router is the core of our application, we'll start building our application code by adding some route handlers for it to use. The routes represent the different pages in our application and will have individual URLs associated with them.

We'll need three routes for our application:
- A palettes route for our list view
- A palettes/new route for our creation form
- A palettes/edit route for our edit form

To create some routes, Ember CLI provides us with some handy terminal commands that will automatically create some files for us. Since the framework provides the file structure for our application, using these *generators* is a handy way to quickly and confidently wire up the primary parts of our application to work with the Ember Router. 

 `ember g route palettes`
```
installing route
	create app/routes/palettes.js
	create app/templates/palettes.hbs
updating router
	add route palettes
installing route-test
	create tests/unit/routes/palettes-test.js
```
`ember g route palettes/new`
```
installing route
	create app/routes/palettes/new.js
	create app/templates/palettes/new.hbs
updating router
	add route palettes/new
installing route-test
	create tests/unit/routes/palettes/new-test.js
```
`ember g route palettes/edit`
```
installing route
	create app/routes/palettes/edit.js
	create app/templates/palettes/edit.hbs
updating router
	add route palettes/edit
installing route-test
	create tests/unit/routes/palettes/edit-test.js
```


___

## Adding an application template

You can see that we automatically got some templates when we ran the generator for our routes. For our application, we need a couple of additional special templates. 

The first special template is the `application template`. This template allows us to wrap all of our other templates in some consistent context. In most applications, this is where things like your nav bar or footer might go - things that should appear on every page of your application.

We'll be using this template to wrap all of our page content in our bootstrap responsive grid.

`ember g template application`
```
installing template
	create app/templates/application.hbs
```
---

## Adding an index template


Next, we need to add a template for our list view. Out of the box, Ember assumes that you might want to build pages with *nested* content - for example, you may want a route that shows a list of blog posts on one side of the screen and also renders an individual blog post on the right side of the screen when you click one of the items.

This is a very powerful option, but not one that we will be using for our application.

Since our design doesn't need any nested templates, we can add a special template called an `index` template to render our list view without any nested content:

`ember g template palettes/index`
```
installing template
	create app/templates/palettes/index.hbs
```
---
## Adding a partial for our form

Next, we need a special type of template called a *partial*.
Partials allow you to create templates that will be reused in more than one place. Since both our new and edit pages will use exactly the same form, we can use a partial to use the same code in both places without having to have two copies of it. 

>Note that Ember provides another structure that we could use for this purpose called a "component". For simplicity purposes, we'll stick to a partial for now, but it would be a good extension to research and implement our form as a component, should you feel up to the challenge.

For now, let's go ahead and generate a partial template for our form. By convention, partial template names start with a dash.

`ember g template -palette-form`
```
installing template
	create app/templates/-palette-form.hbs
```

----------

## Adding Bootstrap

Remember adding bootstrap to our static pages by adding the `<link>` tag in our HTML head? In an Ember application, we can use a special install command to import bootstrap directly into our project, instead. There are a ton of awesome *add-ons* and libraries you can incorporate into your project, simply by running the install command with the library name.

> One of my favorite resources for researching and installing Ember Add Ons is a fantastic website called the [Ember Observer.](https://emberobserver.com/)

To install bootstrap, run the following command:

`ember install ember-bootstrap`

--------

## Copying over our HTML templates

Under the hood, Ember templates are just HTML with some special sauce that lets us dynamically swap out the content that is displayed on the page. This means that all of the HTML we wrote earlier today can be directly ported over to our new application.

>The special sauce is some templating syntax called *Handlebars* - so named for the use of double curly braces to denote dynamic content within the template. The creators thought the curly braces looked like Handlebar mustaches: `{{dynamic-content}}`
>
> The particular flavor of Handlebars that modern Ember applications use is called HTMLbars and uses the file extension `.hbs`.

Let's copy over our templates from this morning into our brand new *Handlebars* Ember templates.

---
## Using an application template

Both our list view and our form view have some duplicate context that we can consolidate into our new application template.

Ember uses a special handlebars helper to designate where any nested content will be rendered into the page. Since we want all of our pages to be rendered inside of the bootstrap grid, we can add the wrapper divs for the container, row and column around this special helper called the `{{outlet}}` helper. All of our other templates will get rendered into this special placeholder and will automatically include the wrapping content. 
```
<!-- app/templates/application.hbs -->
<div class="container">
  <div class="row">
    <div class="col-md-6 col-sm-8 col-md-offset-3 col-sm-offset-2">
      {{outlet}}
    </div>
  </div>
</div>
```
---
## Building our palettes list template

Next, we'll take the list view content that is *different* than the form view content and copy it into our palettes/index template.
```
<!-- app/templates/palettes/index.hbs -->
<h1>Color Palettes</h1>

<h2>Add a Palette</h2>
<a href="palette.html" class="btn-group color-palette empty-palette">
  <button class="btn" type="button"></button>
  <button class="btn" type="button"></button>
  <button class="btn" type="button"></button>
  <button class="btn" type="button"></button>
  <button class="btn" type="button"></button>
</a>

<h2>Tropical</h2>
<a href="palette.html" class="btn-group color-palette">
  <button class="btn" type="button" style="background-color:rgb(217,33,32)" >217,33,32</button>
  <button class="btn" type="button" style="background-color:rgb(231,116,47)">231,116,47</button>
  <button class="btn" type="button" style="background-color:rgb(223,165,58)">223,165,58</button>
  <button class="btn" type="button" style="background-color:rgb(177,190,78)">177,190,78</button>
  <button class="btn" type="button" style="background-color:rgb(109,179,136)">109,179,136</button>
</a>

<h2>Cool</h2>
<a href="palette.html" class="btn-group color-palette">
  <button class="btn" type="button" style="background-color:rgb(70,131,193)">70,131,193</button>
  <button class="btn" type="button" style="background-color:rgb(63,78,161)">63,78,161</button>
  <button class="btn" type="button" style="background-color:rgb(120,28,129)">120,28,129</button>
  <button class="btn" type="button" style="background-color:rgb(0,0,0)">0,0,0</button>
  <button class="btn" type="button" style="background-color:rgb(238,238,238)">238,238,238</button>
</a>
```
---
## Using a partial for our form

Now we'll copy over our HTML for our form into the partial template:

```
<!-- app/templates/-palette-form.hbs -->
<h1>Tropical</h1>
<form>
  <h2>Palette Name</h2>
  <input class="palette-name-input form-control" type="text" placeholder="New Palette">

  <h2>Palette Preview</h2>
  <div class="btn-group color-palette">
    <button class="btn" type="button" style="background-color:rgb(217,33,32)" >217,33,32</button>
    <button class="btn" type="button" style="background-color:rgb(231,116,47)">231,116,47</button>
    <button class="btn" type="button" style="background-color:rgb(223,165,58)">223,165,58</button>
    <button class="btn" type="button" style="background-color:rgb(177,190,78)">177,190,78</button>
    <button class="btn" type="button" style="background-color:rgb(109,179,136)">109,179,136</button>
  </div>

  <h2>Edit Color</h2>
  <div class="btn-group">
    <div class="btn preview-tile" style="background-color:rgb(217,33,32)"></div>
  </div>
  <div class="color-input-group">
    <span class="color-input-label">R</span>
    <input class="color-text-input form-control" maxlength="3" type="text">
    <input class="color-range-input pull-right" type="range" step=1 min=0 max=255>
  </div>
  <div class="color-input-group">
    <span class="color-input-label">G</span>
    <input class="color-text-input form-control" maxlength="3" type="text">
    <input class="color-range-input pull-right" type="range" step=1 min=0 max=255>
  </div>
  <div class="color-input-group">
    <span class="color-input-label">B</span>
    <input class="color-text-input form-control" maxlength="3" type="text">
    <input class="color-range-input pull-right" type="range" step=1 min=0 max=255>
  </div>

  <div class="btn-group form-actions" role="group">
    <a class="btn" href="palettes.html">Cancel</a>
    <a class="btn" href="palettes.html">Delete</a>
    <input class="btn" type="submit" value="Save">
  </div>
</form>
```

----

## Referencing our partial in our edit and new templates

We've got two different templates where we want to use our form. Partials make this painless by letting us drop in a single line of Handlebars to pull in the content from the partial.

We'll add the partial to the new and edit templates using the `{{partial}}` helper. 

Note that since there is no further nested content for these templates, we can simply remove the `{{outlet}}` helpers that were automatically added to our templates when we generated our routes.

```
<!-- app/templates/palettes/new.hbs -->
{{partial 'palette-form'}}
```

```
<!-- app/templates/palettes/edit.hbs -->
{{partial 'palette-form'}}
```
---

## Adding in our styles

Ember provides us a great place to add in our styles, right out of the box. We don't have to mess with linking up style sheets in Ember as long as we add our styles to the app.css file.

We can simply copy our styles directly into the supplied styles/app.css file.

```
/* app/styles/app.css */

body {
  background-color: #1C1F24;
  color: #586073;
}

h1 {
  font-family: 'Pacifico', cursive;
  font-size: 70px;
  margin-top: 50px;
  padding-bottom: 20px;
  text-align: center;
}

h2 {
  font-size: 18px;
}

.btn-group {
  width: 100%;
  margin-bottom: 12px;
  margin-top: 12px;
}

.color-palette .btn {
  width: 20%;
  height: 50px;
  border: none;
  font-size: 10px;
  color: transparent;
}

.color-palette .btn:hover, .color-palette .btn:focus {
  color: #1C1F24;
  border: 2px solid #1C1F24;
}

.empty-palette .btn {
  background-color: transparent;
  border: 1px solid #586073;
}

.empty-palette:hover .btn {
  border: 1px solid white;
}

.palette-name-input {
  width: 100%;
  margin-top: 24px;
  margin-bottom: 24px;
}

.preview-tile {
  width: 100%;
  height: 50px;
  margin-bottom: 18px;
}

.color-input-group {
  width: 100%;
  margin-bottom: 6px;
}

.color-input-label {
  font-size: 24px;
  width: 10%;
  vertical-align: middle;
}

.color-text-input {
  width: 20%;
  margin: 2%;
  display: inline-block;
}

.color-input-group .color-range-input {
  width: 68%;
  margin-top: 18px;
}

.form-actions .btn {
  width: 33.3%;
  padding: 12px;
  margin-top: 12px;
  background-color: #586073;
  border: 1px solid #1C1F24;
  color: white;
}

.form-actions .btn:hover {
  opacity: .8;
}

```
---

## Importing a Google Font

The last thing we linked in our HTML file was the fancy Pacifico font from Google Fonts. In our Ember application, we can *import* the font directly into our css file with some special syntax.

Add Pacifico to your css file by adding this line to the top of the file:

`@import url(https://fonts.googleapis.com/css?family=Pacifico);`

----------------------

##How are things looking?

At this point, we've successfully converted everything from our static web pages over to our new Ember application context.

Let's run our `ember server` command again from our terminal window and checkout how our application is looking!

To take a look at our palettes list page, navigate to:
`http://localhost:4200/palettes`

To checkout how the form is looking, navigate to:
`http://localhost:4200/edit`

If your application looks like the image below - congratulations! You've reached parity with our static web pages and are ready to start layering on some Ember magic.

![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/comps.png?raw=true)

---
#The Ember Magic Begins

## Wiring up our interactions

Ember creates *single-page applications*, which means that instead of the server sending us back an individual HTML page when we visit the application's URL, it actually sends us back the entire application all packaged up together. This means that things like links work a little differently than they did with our static pages. The Ember Router knows how to interpret URLs associated with each of the internal Ember Routes, but we have to use some special handlebars helpers so that it recognizes the difference between *internal* links and *external* links.

---
## Working with link-to helpers

The first thing we need to swap out to get our application to work as expected are the `<a>` tags we were previously using to link between our two views. We'll replace them with some special Handlebars helpers called `{{#link-to}}` helpers, since all of our links are currently *internal* links, meaning they will transition the user to another page within our application:

>A quick note about Handlebars helpers - many of the helpers are special replacements for standard HTML tags. The link-to helper is one such helper. This means you can add things like the class attribute inside of the opening handlebars tag, just like you would with an HTML tag.
>
>The major difference is that you will no longer have an href attribute on the link and will specify the internal route name in quotation marks instead.
>
> Here is an example of the structure of a link-to helper:
> ```
> {{#link-to 'name-of-route' class='my-class'}}
>	 Link Content
> {{/link-to}}
> ```

Replace all of the `<a>` tags in our list and form templates with the appropriate link-to helpers. Be sure to keep any classes or other attributes that were applied to the `<a>` tags.

Here is a list of the three link-tos you will need and the naming conventions for the internal routes we'll be using:
`{{#link-to 'palettes.edit'}}{{/link-to}}`
`{{#link-to 'palettes.new'}}{{/link-to}}`
`{{#link-to 'palettes'}}{{/link-to}}`


----------

##Working with dynamic content

Up to this point, we've been working with static web pages, where all the content is written directly in our HTML.

To make our application dynamic, we will need to start thinking about the items in our list and the information that is backing our form and edit views as *dynamic data*.

To start converting the items displayed in our list to dynamic data, let's take a look at how they could be represented as *JavaScript Objects*.

JavaScript Objects are a way of describing an item by its traits. Let's take a look at what some objects might look like for our palette list view.

> This is a good time to talk about two very important structures in JavaScript - Arrays and Objects.
>
>**Arrays** are ordered lists of items. They use the following syntax:
>`[ thing-one, thing-two, thing-three ]`
>
>Ordered lists, or *arrays* are incredibly useful when you want to represent a collection of things. Our list view will have a collection of palettes as its dynamic data and we'll be using an array to represent it.
>
>The second important structure is called an **Object**. Objects are data structures that allow you to describe an item by a list of traits. They are structured to include a series of key-value pairs where the key is the name of the trait.
>
>They look something like this:
>`{ name: 'Jane', age: 27, eyeColor: 'green' }`
>
>Each individual palette in our list can be represented as an object. Note that the value of a key in an object can essentially be any type of data structure, including another object or an array of objects.

Now that we know a little bit about how objects and arrays look and work, let's set the model (the dynamic data backing our template) on our palettes route to use an array of objects representing our collection of palettes.

```
/* app/routes/palettes.js */

import Ember from 'ember';

export default Ember.Route.extend({
  model() {
    return [
      {
        id: 1,
        name: 'Tropical',
        creator: 'YOUR NAME',
        colors: [
          { r: 217, g: 33, b: 32, styleString: 'background-color:rgb(217,33,32)', labelString: '217,33,32'},
          { r: 231, g: 116, b: 47, styleString: 'background-color:rgb(231,116,47)', labelString: '231,116,47'},
          { r: 223, g: 165, b: 58, styleString: 'background-color:rgb(223,165,58)', labelString: '223,165,58'},
          { r: 177, g: 190, b: 78, styleString: 'background-color:rgb(177,190,78)', labelString: '177,190,78'},
          { r: 109, g: 179, b: 136, styleString: 'background-color:rgb(109,179,136)', labelString: '109,179,136'}
        ]
      },
      {
        id: 2,
        name: 'Cool',
        creator: 'YOUR NAME',
        colors: [
          { r: 70, g: 131, b: 193, styleString: 'background-color:rgb(70,131,193)', labelString: '70,131,193'},
          { r: 63, g: 78, b: 161, styleString: 'background-color:rgb(63,78,161)', labelString: '63,78,161'},
          { r: 120, g: 28, b: 129, styleString: 'background-color:rgb(120,28,129)', labelString: '120,28,129'},
          { r: 0, g: 0, b: 0, styleString: 'background-color:rgb(0,0,0)', labelString: '0, 0, 0'},
          { r: 238, g: 238, b: 238, styleString: 'background-color:rgb(238,238,238)', labelString: '238,238,238'}
        ]
      }
    ];
  }
});

```
The models for our edit and new routes will be a single object -representing a single item in our palettes collection. Let's update the model hook for these two routes to return a single palette object.

```
/* app/routes/palettes/edit.js and app/routes/palettes/new.js */
import Ember from 'ember';

export default Ember.Route.extend({
  model() {
    return {
      id: 1,
      name: 'Tropical',
      creator: 'YOUR NAME',
      colors: [
        { r: 217, g: 33, b: 32, styleString: 'background-color:rgb(217,33,32)', labelString: '217,33,32'},
        { r: 231, g: 116, b: 47, styleString: 'background-color:rgb(231,116,47)', labelString: '231,116,47'},
        { r: 223, g: 165, b: 58, styleString: 'background-color:rgb(223,165,58)', labelString: '223,165,58'},
        { r: 177, g: 190, b: 78, styleString: 'background-color:rgb(177,190,78)', labelString: '177,190,78'},
        { r: 109, g: 179, b: 136, styleString: 'background-color:rgb(109,179,136)', labelString: '109,179,136'}
      ]
    };
  }
});
```

----------

## Adding dynamic placeholders to our templates

Now that we have some dynamic data to back our templates, we need to update our templates to use dynamic placeholders. You can think of these as the blanks in a madlibs document.

First, let's update our palettes list view to dynamically display each item in our list of palettes, instead of hard-coding our two example palettes.

We'll do this with another special Handlebars helper called an `{{#each}}` helper.

Each helpers can be used with any collection of data that is stored as an array. The each helper *loops* over the array and performs the same action for each item in the array. This gives us a streamlined way to add a list elements to our HTML for each item in the array.

The structure is pretty straight-forward, but the syntax can be a little confusing when you first look at it.

Here's how the syntax works:

```
{{#each [array to loop over] as |item in array|}}
	<div>Repeated content for each {{item}}</div>
{{/each}}
```

>The "|" characters in the opening each tag are called *pipes* - I like to think of them as creating a little chute that drops the variable name you want to use for an individual item into the nested block - kind of like one of the portal pipes in Super Mario. For the individual items, you can use whatever name you'd like, as long as you pass it into the nested block via the pipes.

For our list of palettes view, we have TWO each loops we need to make - one for the collection of palettes, and one for the collection of colors within a palette.

Let's take a look:

```
<!-- app/templates/palettes/index.hbs -->
...
{{#each model as |palette|}}
  <h2>{{palette.name}}</h2>
  {{#link-to 'palettes.edit' class="btn-group color-palette"}}
    {{#each palette.colors as |color|}}
      <button class="btn" type="button" style={{color.styleString}} >{{color.labelString}}</button>
    {{/each}}
  {{/link-to}}
{{/each}}
```

Here, we're looping over all the palettes in our model and displaying the palette name. We're then looping over each color in the palette and adding one of our buttons with the style attribute dynamically set to match the styleString property of the color.

Now, we'll do the same to dynamically display the colors in the palette preview of our form:

```
<!-- app/templates/-palette-form.hbs -->

<h1>{{model.name}}</h1>
<form>
  <h2>Palette Name</h2>
  <input class="palette-name-input form-control" type="text" placeholder="New Palette">

  <h2>Palette Preview</h2>
  <div class="btn-group color-palette">
    {{#each model.colors as |color|}}
      <button class="btn" type="button" style={{color.styleString}}>{{color.labelString}}</button>
    {{/each}}
  </div>
  ...

```
----------

#Working with Controllers

Controllers and actions

`ember g controller palettes/edit`
```
installing controller
  create app/controllers/palettes/edit.js
installing controller-test
  create tests/unit/controllers/palettes/edit-test.js
```

`ember g controller palettes/new`
```
installing controller
  create app/controllers/palettes/new.js
installing controller-test
  create tests/unit/controllers/palettes/new-test.js
```

Controller:
```
/* app/controllers/palettes/new.js and app/controllers/palettes/edit.js */
import Ember from 'ember';

export default Ember.Controller.extend({
  focusColor: null,
  actions: {
    setFocusColor(color) {
      this.set('focusColor', color);
    }
  }
});
```

connect actions and dynamic controller properties
```
<!-- app/templates/-palette-form.hbs -->
...
<h2>Palette Preview</h2>
  <div class="btn-group color-palette">
    {{#each model.colors as |color|}}
      <button class="btn" type="button" style={{color.styleString}} {{action 'setFocusColor' color}}>{{color.labelString}}</button>
    {{/each}}
  </div>

  <h2>Edit Color</h2>
  <div class="btn-group">
    <div class="btn preview-tile" style={{focusColor.styleString}}></div>
  </div>
  
...
```
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/set-focus-color.gif?raw=true)

----------

Input helpers - bound properties
```
<h2>Palette Name</h2>
  {{input value=model.name class="palette-name-input form-control" type="text" placeholder="New Palette"}}

  <h2>Palette Preview</h2>
  <div class="btn-group color-palette">
    {{#each model.colors as |color|}}
      <button class="btn" type="button" style={{color.styleString}} {{action 'setFocusColor' color}}>{{color.labelString}}</button>
    {{/each}}
  </div>

  <h2>Edit Color</h2>
  <div class="btn-group">
    <div class="btn preview-tile" style={{focusColor.styleString}}></div>
  </div>
  <div class="color-input-group">
    <span class="color-input-label">R</span>
    {{input value=focusColor.r class="color-text-input form-control" maxlength="3" type="text"}}
    {{input value=focusColor.r class="color-range-input pull-right" type="range" step=1 min=0 max=255}}
  </div>
  <div class="color-input-group">
    <span class="color-input-label">G</span>
    {{input value=focusColor.g class="color-text-input form-control" maxlength="3" type="text"}}
    {{input value=focusColor.g class="color-range-input pull-right" type="range" step=1 min=0 max=255}}
  </div>
  <div class="color-input-group">
    <span class="color-input-label">B</span>
    {{input value=focusColor.b class="color-text-input form-control" maxlength="3" type="text"}}
    {{input value=focusColor.b class="color-range-input pull-right" type="range" step=1 min=0 max=255}}
  </div>
```

![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/bound-properties.gif?raw=true)

---------

Computed properties
```
...
focusColorStyleString: Ember.computed('focusColor.r', 'focusColor.g', 'focusColor.b', function() {
    var r = this.get('focusColor.r');
    var g = this.get('focusColor.g');
    var b = this.get('focusColor.b');
    if (r || g || b) {
      return Ember.String.htmlSafe(`background-color:rgb(${r}, ${g}, ${b})`);
    } else {
      return Ember.String.htmlSafe('background-color:transparent; border:1px solid #586073');
    }
  })
  ...
```

![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/computed-property.gif?raw=true)

----------
`ember install emberfire`

Add keys to config/environment.js
```
// config/environment.js

module.exports = function(environment) {
	var ENV = {
		firebase: {
		   apiKey: "AIzaSyBvdiz729ZWt5XUHQhsaEeR1MrO53Q_FyA",
		   authDomain: "emberitas-color-palette.firebaseapp.com",
		   databaseURL: "https://emberitas-color-palette.firebaseio.com",
		   storageBucket: "emberitas-color-palette.appspot.com"
		 },
		 ...
```
-------------
Generate models
`ember g model palette`

```
installing model
  create app/models/palette.js
installing model-test
  create tests/unit/models/palette-test.js
```

`ember g model color`

```
installing model
  create app/models/color.js
installing model-test
  create tests/unit/models/color-test.js
```

combine computed properties and fixture structure. Has many, belongs to
MAKE SURE THEY CHANGE THE CREATOR DEFAULT TO THEIR OWN NAME
```
import Model from 'ember-data/model';
import attr from 'ember-data/attr';
import { hasMany } from 'ember-data/relationships';

export default Model.extend({
  name: attr({ defaultValue: 'New Palette' }),
  creator: attr({ defaultValue: 'YOUR NAME' }),
  colors: hasMany('color', {async: false})
});
```

```
import Model from 'ember-data/model';
import attr from 'ember-data/attr';
import Ember from 'ember';
import { belongsTo } from 'ember-data/relationships';

export default Model.extend({
  palette: belongsTo('palette', { async: false }),
  r: attr({ defaultValue: 0 }),
  g: attr({ defaultValue: 0 }),
  b: attr({ defaultValue: 0 }),
  styleString: Ember.computed('r', 'g', 'b', function() {
    var r = this.get('r');
    var g = this.get('g');
    var b = this.get('b');
    if (r || g || b) {
      return Ember.String.htmlSafe(`background-color:rgb(${r}, ${g}, ${b})`);
    } else {
      return Ember.String.htmlSafe('background-color:transparent; border:1px solid #586073');
    }
  }),
  labelString: Ember.computed('r', 'g', 'b', function() {
    var r = this.get('r');
    var g = this.get('g');
    var b = this.get('b');
    if (r || g || b) {
      return Ember.String.htmlSafe(`${this.get('r')}, ${this.get('g')}, ${this.get('b')}`);
    } else {
      return '';
    }
  }),
});
```

----

rigging up real models to routes
Replace palettes route model hook with real data! Note special syntax JUST for firebase
```
model: function() {
   return this.store.query('palette', {
     orderBy: 'creator',
     equalTo: 'Fixture'
   });
 }
```
BROKEN!
Need a serializer
`ember g serializer palette`

```
import FirebaseSerializer from 'emberfire/serializers/firebase';
export default FirebaseSerializer.extend({
  attrs: {
    colors: {embedded: 'always'}
  }
});
```

YAY! RECORDS FROM THE SERVER!
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/fixture-endpoint.png?raw=true)

SWAP OUT THE FILTER FOR YOUR OWN NAME AGAIN
```
model: function() {
   return this.store.query('palette', {
     orderBy: 'creator',
     equalTo: 'YOUR NAME'
   });
 }
```

-----------
Create model:
```
import Ember from 'ember';

export default Ember.Route.extend({
  model() {
    // add a new palette to our local store
    var newPalette = this.store.createRecord('palette', {});
    // isolate the colors property of our new palette
    var colors = newPalette.get('colors');
    // add five empty color records to the palette
    for (var i=0; i<5; i++) {
      colors.addObject(this.store.createRecord('color', {}));
    }
    return newPalette;
  },
  afterModel(model) {
    // select the first color and make that the active color for editing
    this.controllerFor('palettes.new').set('focusColor', model.get('colors.firstObject'));
  }
});
```

Add create action to form

```
actions: {
    setFocusColor(color) {
      this.set('focusColor', color);
    },
    savePalette() {
      var palette = this.get('model');
      palette.save().then(() => {this.transitionToRoute('palettes.index');}, (err) => {console.log(err);});
    }
  }
```

`<form {{action 'savePalette' on='submit'}}>`

YAY! We can create REAL records!

Now, for edit:
Dynamic segments - and while we're at it - setting the index route:

update router.js
```
Router.map(function() {
  this.route('palettes', { path: '/'},  function() {
    this.route('new');
    this.route('edit', { path: '/palettes/:palette_id' });
  });
});
```
Restart your server!

swap out the model for something real:
```
export default Ember.Route.extend({
  model(params) {
    return this.get('store').findRecord('palette', params.palette_id);
  },
  afterModel(model) {
    this.controllerFor('palettes.edit').set('focusColor', model.get('colors.firstObject'));
  }
});
```
Fix links to use dynamic segment!
`{{#link-to 'palettes.edit' palette.id class="btn-group color-palette"}}`

Add save, delete and cancel actions
```
savePalette() {
      var palette = this.get('model');
      palette.save().then(() => {this.transitionToRoute('palettes.index');}, (err) => {Ember.Logger.log(err);});
 },
 cancel() {
   var palette = this.get('model');
   palette.rollbackAttributes();
   var colors = palette.get('colors');
   colors.forEach((color)=>{
     color.rollbackAttributes();
   });
   this.transitionToRoute('palettes');
 },
 deletePalette() {
   var palette = this.get('model');
   palette.destroyRecord();
   this.transitionToRoute('palettes');
 }
```

Add actions to new view buttons
```
cancel() {
   this.transitionToRoute('palettes');
 },
 deletePalette() {
   this.transitionToRoute('palettes');
 }
```

Add new actions to form buttons:
```
<button class="btn" {{action 'cancel'}}>Cancel</button>
<button class="btn" {{action 'deletePalette'}}>Delete</button>
<input class="btn" type="submit" value="Save">
```

YAY!!!!!!! ALL THE THINGS WORK!!!!!

Deploying to page front - 
`ember install ember-pagefront --app=YOUR_APP_NAME`
`ember deploy production`

