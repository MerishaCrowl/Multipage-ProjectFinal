# MultiPageProject

GOOGLE FONTS
To include a google font, choose the one you want to use on the website, and follow the instructions to:

1. Link the font into the <head> tags of your website
<head>
    <link href="https://fonts.googleapis.com/css?family=Proza+Libre" rel="stylesheet">
</head>

2. Specify when to use it in your CSS sheet

.google-font-text {
    font-family: 'Proza Libre', sans-serif;
}


DROPDOWN MENUS
<!--HTML within body tag-->
<ul>
  <li><a class="active" href="#home">Home</a></li>
  <li><a href="#blog">Blog</a></li>
  <li class="dropdown">
    <a href="#" class="dropbtn">Dropdown</a>
    <div class="dropdown-content">
      <a href="#">Link 1</a>
      <a href="#">Link 2</a>
      <a href="#">Link 3</a>
    </div>
  </li>
</ul>


/*=====CSS for Dropdown Menus=====*/

ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #333;
}

li {
    float: left;
}

li a, .dropbtn {
    display: inline-block;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
}

li a:hover, .dropdown:hover .dropbtn {
    background-color: #0088ce;
}

li.dropdown {
    display: inline-block;
}

.dropdown-content {
    display: none;
    position: absolute;
    background-color: #f9f9f9;
    min-width: 160px;
    box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
}

.dropdown-content a {
    color: black;
    padding: 12px 16px;
    text-decoration: none;
    display: block;
    text-align: left;
}

.dropdown-content a:hover {background-color: #f1f1f1}

.dropdown:hover .dropdown-content {
    display: block;
}

RESPONSIVE WEB DESIGN

When deciding how to design for different devices, 
keep 3 things in mind:

Device (CSS) width x height
Pixel Ratio
Physical (pixel) width x height 
 
Device (CSS) Width x Pixel Ratio = Physical (Pixel) Width

common device resolution ranges
https://www.mydevice.io/

This meta tag will set the viewport of your page, which will give the browser instructions on how to control the page's dimensions and scaling.
<meta name="viewport" content="width=device-width, initial-scale=1.0">

CSS @media rule
@media is used to determine the browser resolution. 

Stay up to date!
http://cssmediaqueries.com/


@media only screen and (max-width: 767px) { /*Make the text green on small devices*/
    .mytext{
        color: green;
    }
}

@media only screen and (min-width: 768px) { /*Make the text red on large devices*/
    .mytext{
        color: red;
    }
}
open your page in Chrome. Use inspect to see how your page looks on different devices.

/*CSS styles for mobile*/
@media only screen and (max-width: 480px) { 
    .boxes{
        width: 100%;
        height: 200px;
        background-color: red;
        text-align: center;
        color: white;
    }
}

/*CSS styles for tablets*/
@media only screen and (min-width: 480px) and (max-width: 768px) { 
    .boxes{
        width: 50%;
        height: 200px;
        background-color: yellow;
        display: inline-block;
        float: left;
        border: 4px solid white;
        box-sizing: border-box;
        text-align: center;
    }
}

/*CSS styles for large screens*/
@media only screen and (min-width: 769px) { 
    .boxes{
        width: 25%;
        height: 200px;
        background-color: green;
        display: inline-block;
        float: left;
        border: 4px solid white;
        box-sizing: border-box;
        color: white;
        text-align: center;
    }
}


First, build a header and navigation for the top of your website.

<header>
 <a href="#" id="logo"></a>
   <nav>
     <a href="#" id="menu-icon"></a>
     <ul>
       <li><a href="#" class="current">Home</a></li>
       <li><a href="#">About</a></li>
       <li><a href="#">Work</a></li>
       <li><a href="#">Blog</a></li>
       <li><a href="#">Contact</a></li>
     </ul>
  </nav>
</header>

Now let's style it. Note: you will need to comment out any previous nav or header selectors

header {
	position: fixed;
	background: #fff;
	top: 0;
	left: 0;
	z-index: 100;
	width: 100%;
	height: 60px;
	border-bottom: 4px solid green;
}

nav {
	float: right;
	padding: 5px;	
}

More styling. Look at the properties and values and see if there is anything you want to change for YOUR site. 

nav ul {
	list-style: none;
	padding: 0;
}

nav ul li {
	display: inline-block;
	float: left;
	padding: 10px;
	box-sizing: border-box;
}

nav ul li a {
	text-decoration: none;
	color: black;
}

#menu-icon {
	display: hidden;
	width: 40px;
	height: 40px;
	background: url(https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcTk7z6qSJdV8wmm0xwR4nrK5OPwhOfXJPqzrIG3ynOlOoGHyc4PSyrvpQ) center;
	background-size: contain;
}

Additional @media code and style. Again, you can and should customize the properties and values to fit your site! 

/*MEDIA QUERY*/
@media only screen and (max-width : 768px) {
	header {
		position: absolute;
		border-bottom: 4px solid red;
	}
	a, a:active, a:visited {
		color: white;
	}

	#menu-icon {
		display:inline-block;
	}

	nav ul, nav:active ul { 
		display: none;
		position: absolute;
		background: #fff;
		right: 0;		
		border: 5px solid #000;
		width: 100%;
	}

	nav li:last-of-type {
		border-bottom: 0px;
	}

	nav ul li {
		text-align: center;
		width: 100%;
		margin: 0;
		padding: 20px 0 20px 0;
		background-color: red;
		border-bottom: 1px solid #fff;
	}

	/*This makes sure the nav menu opens up */
	nav:hover ul {
		display: block;
	}
}

Absolute Units

cm - centimeters

mm - millimeters

in - inches

px - pixels (1px = 1/96th of 1in)

pt - points (1pt = 1/72 of 1in)

pc - picas (1pc = 12 pt)

Relative Units

em - relative to the font-size of the element

rem - relative to the font-size of the root element

vw - relative to 1% width of the viewport

vh - relative to 1% height of the viewport

vmin - relative to 1% of the smaller dimension: either height or width

vmax - relative to 1% of the larger dimension: either height or width

% - percentage

TYPES OF GRAPHICS
LOSSY - image formats that do not store a perfect copy of the original image and thus have smaller file sizes

LOSSLESS - stores an exact pixel-by-pixel representation of the image, but in doing so, require more space.

RASTER (.PNG)
Just about everything you see on the web is a raster image file.  It is made up of a bunch of little square pixels.
Raster files lose quality if you resize them to be larger.

Photoshop, MS Paint, Canva, Pixlr

VECTOR (.SVG)
Logos, simple graphics, and 'cartoon' style images are often created in Vector format. These do NOT lose quality when resized, and are great for logos.

Illustrator, CorelDraw, Vectr

FLEXBOX

Flexible Box Layout (Flexbox) makes it easier to design a responsive layout structure without using positioning.

A container becomes flexible by setting the display property to flex.

FLEXBOX HTML
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>

FLEXBOX CSS
.flex-container {
  display: flex;
}

FLEXBOX PROPERTIES
flex-direction

flex-wrap

flex-flow

justify-content

align-items

align-content

The properties of flexible containers allow us to easily arrange blocks of content on our page while keeping the layout responsive.

HTML
<div class="flex-container">
  <div>1</div>
  <div>2</div>
  <div>3</div>
</div>

CSS
.flex-container {
  display: flex;
  background-color: DodgerBlue;
}

.flex-container > div {
  background-color: #f1f1f1;
  margin: 10px;
  padding: 20px;
  font-size: 30px;
}# Multipage-ProjectFinal
