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

### <i class="icon-star"></i> Phase 3 - *Interaction Design*
![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/new-palette.gif?raw=true)
#### Intro to JavaScript
#### Working with JQuery 
> ![enter image description here](https://github.com/lydiaguarino/emberitas-images/blob/master/basic-nav.gif?raw=true)

### <i class="icon-star"></i> Phase 4 - *Building the Application Code*
#### The anatomy of the web
#### Bootstrapping a new Ember application
#### The Ember Router
#### Ember Routes

### <i class="icon-star"></i> Phase 5 - *Building a CRUD application using MVC Pattern*
#### Working with Records
#### Intro to Model View Controller (MVC) Pattern - or in our case, M *T* C
#### Templates
#### Models
#### Controllers

### <i class="icon-star"></i> Phase 6 - *Persistence*
#### Understanding "front-end" vs "back-end"
#### Intro to Ember Data
#### Intro to working with APIs (Firebase)

### <i class="icon-star"></i> Phase 7 - *Deployment - Making the application available to users*
#### Understanding DNS and hosting
#### Intro to Pagefront

