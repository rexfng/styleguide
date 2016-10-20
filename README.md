#STYLEGUIDE SCSS BOLIERPLATE
Description - This boilerplate uses Compass SCSS framework with a few helpful mixins such as custom column grid (any columns you want for each screen sizes), media query helpers, and flexbox shortcuts. This boilerplate also includes an index.html file as a style guide. 
## Folder Structure
| — sass
	 | —  \_variables.scss_
	 | —  \_global.scss_
	 | —  \_mixins.scss_
	 | —  app.scss_
| —  app.css
| — config.rb
| — index.html_
## Folder Structure Explained
1. \_global.scss - Includes all lower level css that affects the entire projects. i.e. blockquotes, h1, p 
2. \_mixins.scss - Includes all custom mixins css helpers that are used in the project. For this boilerplate, grid, breakpoints(media query), and flexbox mixins are located here.
3.  \_variables.scss - Defines all your global variables here including colors, fonts, grid & media query settings.
4. app.scss - This file stores all the layout and specific css codes for all the pages. It is recommended to use css comment to separate codes from different pages.
5. app.css - You should never have to touch this file as it is a compiled file.
6. config.rb - Stores all SCSS settings.
7. index.html - Contains html codes to help show off the current styles being implemented in this project. 

##Variables
You can customize it for every screen size below by changing the grid size value.  ie. ('xxl', 2560px, $gridSize/ 2). Unfortunately due to sass’s limitation, if you wish to add more than 5 breakpoints, you will have to adjust grid and mediaQuery mixins accordingly.

$fontStyles variable has the following properties: 
$fontstyles : (tag, font-family, font-weight, font-size, color, line-height, letter-spacing, margin, padding)

$gridSize : 12 ; 
$breakpoints : (
	('xxl', 2560px, $gridSize),
	('xl', 1440px, $gridSize),
	('l', 1024px, $gridSize),
	('m', 768px, $gridSize),
	('s', 425px, $gridSize)
);
$border-box-mode - “true” to  gives box-sizing: border-box to all grid properties.


##Mixins
**flex($justify-content, $align-items, $flex-direction, $flex-wrap)**
	pass in values for the css properties.
**grid($xxl, $xl, $l, $m, $s)**
	depending on your grid setup, pass in the column number for each screen sizes. ie. in a 12 column grid
	@include grid(6,6,3,3,1); 
	=> output  
		@extend .xxl-6; =>  => width:16.5% in xx-large screen size;
		@extend .xl-6; => width:16.5% in x-large screen size;
		@extend .l-3; => width:33% in large screen size;
		@extend .m-3; => width:33% in medium screen size;
		@extend .s-1; => width:100% in small screen size;
**mediaQuery($xxl, $xl, $l, $m, $s)**
	to target a specific screen size, give the variable a value of 
	1 = true, 0 = false.
	ie. to create media query for only medium and small screen size:
	mediaQuery(0,0,0,1,1)\{
		// Your Code;
	\}
	=> output
		@media (max-width: 425px) { 
		  	// Your Code;
		}	
