- AKA Cascading Style Sheets
- Documentation
	- Cheatsheet
	  collapsed:: true
		- `min-height: 100vh;`
		- max-width: 100vw; - it
		- When trying to try resizing certain elements you can give it a coloured border to see it more easily when trying to resize it
			- ```css
			  border: 1px solid cyan;
			  ```
		-
	- Learning resource sorted by priority
		- ((636fd068-a9de-47a1-b024-3a4865517bc2))
		- ((62b5cc20-5561-4d6b-aee4-727626c9fb06))
		- [[Design_spark-joy]] : ((636f8b66-90ac-483e-acab-4b4e26aa5f0b))
		- [MDN References: CSS](((6343d97b-97e3-40e0-abdc-65c61d7c9348)))
		- ((634710b7-9f3a-4533-bb0a-fdc1635bd8c5))
		- [CSSBattle](https://cssbattle.dev/)
	- Completed learning resources (references)
		- ((62b5cc20-5561-4d6b-aee4-727626c9fb06)) : ((62d4474f-9b9d-4ba9-abdb-dd54a279991c))
		- Udacity: Intro to HTML and CSS (CSS)
		  id:: 629ccb26-8b37-482c-ad2c-50d1ca57c944
		  collapsed:: true
			- CSS transforms every webpage to it's nice design. HTML = what elements, CSS = how they look
				- https://i.imgur.com/2FMFSdX.png
			- Rulesets (structure of CSS)
				- Ruleset example
				  ```css
				  div {
				   text-align: right;
				  }
				  ```
				- _Made up of two parts:_
					- 1) Selector (what element/id/class you're referring to)
					  `div`
					- 2) Declaration block (everything within { } )
					  ```css
					   {
					   text-align: right;
					  }
					  ```
				- Example2:
				  ```css
				       .kitten-image {
				              border: thick dashed #fa8072;
				              cursor: pointer;
				              box-shadow: 4px 4px 4px -2px rgba(0,0,0,0.75);
				       }
				  ```
			- CSS is placed within a [`<style>`]([[CSS]]) HTML element
			  id:: 62d44751-2e76-4f8b-be80-13efd0c96abc
				- Example
				  ```html
				  <head>
				    <title>Quiz - Hello, world!</title>
				    <style>
				      .red-text {
				        color: red;
				        font-family: monospace;
				      }
				  
				      p {
				        font-size: 16px;
				      }
				    </style>
				  </head>
				  ```
				- Place it in the `<head>` area, it'll also apply to the `<body>` area
			- Types of Selectors of doing it
			  id:: 62d44751-6141-4c5b-8fd5-93b32359e4d3
				- 3 main types:
					- **Tag Selectors** - `p` they just use the element name and it applies to all instances of that element
					  [code]
						- Example
						  `xml
						   <style>
						  h1 {
						    color: green;
						  }
						   </style>
						  `
					- **`class` Attribute Selectors** - `.example` Can use multiple classes on each element, and can be applied to multiple elements
					  [code]
						- Example
							- `<style>` tag
							  `xml
							   <style>
							  .book-summary {
							   color: green;
							  }
							   </style>
							  `
							- Within element
							  `xml
							  <p class="book-summary">random text</p>
							  `
						- Example2 (multiple classes
						  `xml
						  <p class="book-summary highlight table">random text</p>
						  `
					- **`id` Attribute Selectors** - `#test` they have to be unique per webpage and blank spaces aren't allowed
					  [code]
						- Example
							- `<style>` tag
							  `xml
							   <style>
							  #site-description {
							   color: green;
							  }
							   </style>
							  `
							- Within element
							  `xml
							  <p id="site-description">random text</p>
							  `
				- More
					- https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors
					- https://css-tricks.com/how-css-selectors-work/
				- Related: ((63045a99-14de-4b65-af5e-a97b557dc8da))
			- CSS code comments
			  [code]
				- Eg
				  `css
				  p {
				      color: blue;
				  }        
				  /* add CSS here */
				  h1 {
				      color: red;
				  }
				  `
			- Common CSS properties
				- CSS references
					- Mozilla
					  https://developer.mozilla.org/en-US/docs/Web/CSS/Reference
					- CSS Almanac
					  https://css-tricks.com/almanac/
				- _Formatting_
					- Italicise
					  `font-style`
					- Underline
					  `text-decoration: underline`
					- Uppercase
					  `text-transform: uppercase`
					- Bold
					  `font-weight: bold`
					- Size
					  `font-size`
					- Alignment
					  `text-align: center`
				- _Div resizing_
					- `width`
						- `width: 150px;`
					- `height`
					- `margin`
					- `font-size: 2em;`
					- box-shadow
						- [box-shadow generator](http://www.cssmatic.com/box-shadow)
					- `color` - text colour
				- Borders
					- https://developer.mozilla.org/en-US/docs/Web/CSS/border
					- `border-color`
					- `border-radius` - rounded corners
						- `border-radius: 25px;`
				- ((67376798-2bfa-4918-93d8-87bf84a18881))
				- Fonts
					- Web-safe fonts
					  http://www.cssfontstack.com/
					- Custom web fonts
					  https://www.google.com/fonts
					- `font-family` - define a family instead of a single font face
						- Useful because often a user's OS won't always have access to a specific font. It'll attempt to use the font starting with the first
						- tSo, specifying multiple, similar fonts ensures users have a consistent experience regardless of the operating system they are using.
						- Example
						  `css
						  body {
						      font-family: Arial, Helvetica, sans-serif;
						  }
						  `
				- Adding images
					- https://www.w3schools.com/cssref/pr_background-image.asp
					- `background-image: url(profile-placeholder.svg);`
				- CSS colours
					- Examples for `blue`
						- Named colours `color: blue;`
						- RGB `color: rgb(0, 0, 255);`
						- Shorthand Hex `color: #00f;`
					- _Either do it in:_
						- RGB
							- RGB - each 0-255
							- Example
							  `background-colour: rgb(255, 0, 255);`
						- Hexadecimal
							- RGB = 0-FF
							- Example
							  `background-colour: #ff00ff;`
							- https://en.wikipedia.org/wiki/Hexadecimal
							- Hex to RGB Converter (type in either)
							  http://hex.colorrrs.com/
						- References
							- Named Colours and Hex Equivalents
							  https://css-tricks.com/snippets/css/named-colors-and-hex-equivalents/
							- CSS Shorthand Properties
							  https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties
							- CSS Shorthand Hexadecimal form
							  https://en.wikipedia.org/wiki/Web_colors#Shorthand_hexadecimal_form
			- Example code snippets
				- Modified text
					- eg1
					  `css
					       .udacity-text {
					              font-family: Helvetica, Arial, sans-serif;
					              font-size: 60px;
					              color: #8001ff;
					              font-weight: bold;
					              text-decoration: underline;
					              text-transform: uppercase;
					              text-align: center;
					       }
					  `
				- A to-do list
				  [code]
					- Example
					  `css
					  <!DOCTYPE html>
					  <!-- Instructions: Using the provided HTML and CSS, add the correct attributes to the HTML to replicate solution provided on the previous page. 
					  
					  If you need to click back over - don't worry! Your workspace will be saved for you.
					  -->
					  <html>
					  <head>
					   <meta charset="utf-8">
					   <title>Using Attributes Quiz</title>
					   <style>
					          body {
					              font-family: Arial; 
					          }
					          #to-do-list {
					              width: 400px;
					              background: #2d304c;
					              padding: 10px 20px;
					          }
					          .title {
					              color: #fff;
					          }
					          .underline {
					              text-decoration: underline;
					          } 
					          .list {
					              list-style-type: circle;
					              text-align: left;
					              font-size: 16px;
					              color: #1fba58;
					              line-height: 24px;
					          }
					          .finished {
					              color: #f4442f;
					              text-decoration: line-through;
					          }
					   </style>
					  </head>
					  <body>
					   <div id="to-do-list">
					    <h1 class="title underline">My To-Do List</h1>
					    <h2 class="title">Chores</h2>
					    <ul class="list">
					     <li>load the diswasher</li>
					     <li>vacuum living room</li>
					     <li>take out garbage</li>
					     <li class="finished">sweep the garage</li>
					    </ul>
					    <h2 class="title">Homework</h2>
					    <ul class="list">
					     <li class="finished">brainstorm ideas for Science project</li>
					     <li class="finished">finish Calculus 2 problems</li>
					     <li>study for Programming midterm :P</li>
					              <li>finish Project 0 on Udacity FEND</li>
					     <li class="finished">find sources for Biology research paper</li>
					     <li>read first two chapters of The Art of War</li>
					    </ul>
					          <h2 class="title">Party</h2>
					          <ul class="list">
					              <li class="finished">send out invitations</li>
					              <li>reserve party room at restaurant</li>
					              <li>order the cake!</li>
					          </ul>
					   </div>
					  </body>
					  </html>
					  `
			- Developer Tools
				- `Ctrl + Shift + i`
				- Firefox Developer Tools
					- https://developer.mozilla.org/en-US/docs/Tools
				- Google Chrome DevTools
					- https://developers.google.com/web/tools/chrome-devtools/
			- Absolute or Relative CSS Units
				- Absolute = `px`, `mm`, `in`, `cm`
				- Relative = `%`, `em`, `vw`, `vh`
			- CSS Stylesheets
				- Used to apply the same CSS to multiple pages
				- _How to_
					- Create a file called `styles.css`
					- Instead of a `<styles>` element use `<link href="path-to-stylesheet/stylesheet.css" rel="stylesheet">` in each `<head>` of a HTML file
			- Multiple classes
				- <p class="highlight module right"></p>
			- {Archive}
				- Udacity: Intro to HTML and CSS
				  https://eu.udacity.com/course/html-and-css-syntax--ud001
		- ((63317807-bd1e-430c-bf63-985d824439f1))
	- Assorted topics
	  collapsed:: true
		- Flexbox
		  id:: 634d8f7c-e565-4a7a-9a3e-31c22a40c819
		  collapsed:: true
			- ((634d7722-3ccd-4b97-b5d7-4ecfd9148a92))
			- ((62b5cc20-5561-4d6b-aee4-727626c9fb06)) : ((634bc17f-8b60-47b9-8b17-b001e69c1abd))
			- How to use ((634d8f7c-e565-4a7a-9a3e-31c22a40c819)) together with Grid
			  id:: 6370c3c3-cbd0-422d-b38d-fcce43135140
			  collapsed:: true
				- They are meant to be used together. You can at the very least use CSS grid for your overall app layout and flexbox for aligning items
					- You can completely change a layout via media query.
				- The name grid should give you a hint - generally it's most useful when you need an actual grid. Flexbox is useful for a lot of other positioning techniques (like aligning arbitrary numbers of items or such)
				- Our general rule is for one directional layout, use Flexbox. For two directional, use Grid
				  collapsed:: true
					- One dimension: think of items in a top navbar
						- these items are *always* in a row, even on mobile, we probably don't want them in a column
						- we might want to space these items out with  `justify-content: space-between`
						- we might want to align them with  `align-items: center`
						- but we're never (or rarely) wrapping them, all our considerations are always in one dimension - the 'row' of the navbar
					- Two dimensions: think of 30 'card' components
						- we're almost definitely going to wrap these, so that we fit 1-5 cards in a row (based on the screen width), and then we have as many rows as we need
						- while we definitely could space these cards out with flexbox, it can be a pain, with grid, we just do  `grid-gap: 16px`  and it takes care of everything for us
					- Grid obviously has more uses than just wrapping some content and spacing it, but I wanted to stick to a very basic example that stresses when I'd reach for each.
			- [Learning Resources]
				- [An Interactive Guide to Flexbox in CSS](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/)
				- [CSS Flexbox Layout Guide | CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
				-
				- Games
				  id:: 6370bcd8-3734-47c7-bf74-8cec6b27c705
					- *Beginner*
						- [Flexbox Froggy - A game for learning CSS flexbox](https://flexboxfroggy.com)
						- [Flexbox Defense](http://www.flexboxdefense.com/)
					- *Beginner to Intermediate*
						- [Flexbox Zombies](https://mastery.games/flexboxzombies/)
						  id:: 636fc3bd-86d0-420c-95b7-7f3dc388c976
						  collapsed:: true
							- *Meta*
								- ```css
								  crossbow {
								    display: flex;
								  }
								  ```
								- Stick to an order:
								  collapsed:: true
									- ```css
									  crossbow {
									    display: flex;
									    flex-direction: row-reverse;
									    justify-content: center;
									    align-items: center;
									  }
									  ```
								- How to centre a div
								  id:: 67376778-11fb-487a-9cfb-6b8ade08e11d
								  collapsed:: true
									- ```css
									  display: flex;
									  flex-direction: row;
									  justify-content: center;
									  align-items: center;
									  ```
							- `flex-direction`
							  id:: 636fe415-7ffa-4d4c-84ac-18e3230fab81
							  collapsed:: true
							  Direction of box
								- ```css
								  /* This is the hidden default */
								  flex-direction: row; /* West-to-East */
								  
								  /* Alternate choices */
								  flex-direction: row-reverse; /* East-to-West */
								  flex-direction: column; /* North-to-South */
								  flex-direction: column-reverse; /* South-to-North */
								  ```
							- `justify-content`
							  id:: 636fe669-d6e6-4e89-9230-04789a11c47e
							  collapsed:: true
							  Centering of box
								- ```css
								  /* This is the hidden default */
								  justify-content: flex-start; /* Horizontally near from where your direction starts */
								  
								  /* Alternate choices */
								  justify-content: flex-end; /* Horizontally far from where your direction starts */
								  justify-content: center; /* Horizontally middle from where your direction starts */
								  justify-content: space-between; /* Multiple columns evenly spaced only between eachother, but not around their sides */
								  justify-content: space-around; /* Multiple columns evenly spaced between eachother plus half of that space at their sides */
								  justify-content: space-evenly; /* Multiple columns evenly spaced between eachother plus even space at their sides */
								  ```
							- `align-items`
							  id:: 636feb2e-8de3-4ed4-9283-f557d4150b4a
							  collapsed:: true
							  Positioning on other axis to ((636fe415-7ffa-4d4c-84ac-18e3230fab81)). Based on reading direction
								- ```css
								  /* This is the hidden default */
								   /* Aligned vertically if flex-direction is row/row-reverse */
								  /* Stretched vertically */
								  align-items: stretch;
								  
								   /* Aligned to the top if flex-direction is row/row-reverse */
								   /* Aligned to the left if flex-direction is column/column-reverse */
								  align-items: flex-start;
								  
								   /* Aligned to the bottom if flex-direction is row/row-reverse */
								   /* Aligned to the right if flex-direction is column/column-reverse */
								  align-items: flex-end;
								  
								   /* Aligned vertically if flex-direction is row/row-reverse */
								  /* Squished to center vertically */
								  align-items: center;
								  ```
							- `align-self`
							  collapsed:: true
							  Overrides ((636feb2e-8de3-4ed4-9283-f557d4150b4a)), used for different child elements rather than parent that you have `align-items` for
								- Second column is assigned differently
								  ```css
								  crossbow {
								    display: flex;
								    justify-content: flex-end;
								    align-items: center;
								  }
								  
								  .target:nth-of-type(2) {
								    align-self: flex-start;
								  }
								  
								  /* Has all the possible settings of align-items */
								  align-items: stretch;
								  align-items: flex-start;
								  align-items: flex-end;
								  align-items: center;
								  ```
							- `flex-grow`
							  id:: 636ff093-1e71-444b-869c-0f3339f6af8c
							  collapsed:: true
							  If box grows to fill available space. Overrides ((636fe669-d6e6-4e89-9230-04789a11c47e))?
								- Works in ratios. Having two items set to `1` makes them both grow to fill the available space at the same rate
								- Works horizontally/vertically, follows `flex-direction`
								- ```css
								  /* This is the hidden default */
								  /* Won't grow to fill the available space */
								  flex-grow: 0;
								  
								  /* Whenever free space is available grow to fill the available space */
								  flex-grow: 1;
								  
								  /* Makes the 2nd item grow at 2x ratio of the 1st item */
								  .target:nth-of-type(1) {
								    flex-grow: 1;  
								  }
								  
								  .target:nth-of-type(2) {
								    flex-grow: 2;
								  }
								  ```
							- `flex-shrink`
							  id:: 636ff098-0dac-4aa2-86fd-7068927419a7
							  collapsed:: true
							  If box shrinks when there's not enough space for it
								- Works in ratios also
								- ```css
								  /* This is the hidden default */
								  flex-shrink: 1;
								  
								  /* Force box to never shrink */
								  flex-shrink: 0;
								  
								  /* 2nd and 3rd element shrinks at 2x the speed */
								  .target:nth-of-type(2), .target:nth-of-type(3) {
								    flex-shrink: 2;
								  }
								  ```
							- `flex-basis`
							  collapsed:: true
							  Overrides `width` and `height`, better version of it basically (target size)
								- It's a starting point / ideal / hypothetical size before any growing or shrinking happens
								- Overriden by
								  collapsed:: true
									- `min-width` and `max-width`
									- `min-height` and `max-height`
									- The size of the container it's in / other elements it's influenced by
									- ((636ff093-1e71-444b-869c-0f3339f6af8c)) and ((636ff098-0dac-4aa2-86fd-7068927419a7))
								- It follows ((636fe415-7ffa-4d4c-84ac-18e3230fab81)) (i.e. if using `row`, then it'll influence width)
								- ```css
								  /* This is the hidden default. It'll fall back on `width` value */
								  flex-basis: auto;
								  
								  /* Make slime target bigger than usual  */
								  flex-basis: 200%;
								  
								  /* Make slime target smaller than usual  */
								  flex-basis: 80px;
								  ```
							- `order`
							  collapsed:: true
							  In ascending order defines which the order of the flexboxes
								- Has no effect on ((636d5ee0-2b8b-4794-99e9-d68cf1fc26c6))
								- Starts from ((636fe415-7ffa-4d4c-84ac-18e3230fab81))
								- ```css
								  /* This is the hidden default */
								  order: 0;
								  
								  /* Force the targeted element to be the furthest away, if everything else uses the default */
								  order: 1;
								  
								  /* Force the targeted element to be the second flexbox */
								  order: 2;
								  
								  /* Force the targeted element to be the closest one, if everything else uses the default */
								  order: -1;
								  
								  /* The higher the order, the farther it moves away from you? */
								  
								  /* The lower the number, the farther it is from you */
								  
								  ```
							- `flex-wrap`
							  id:: 63715d59-200c-4485-9113-aedd733d348c
							  collapsed:: true
								- ((636ff093-1e71-444b-869c-0f3339f6af8c)) means it'll grow to fill out the new line
								- ((636ff098-0dac-4aa2-86fd-7068927419a7)) happens **after** items get wrapped onto separate lines
								- ((636fe669-d6e6-4e89-9230-04789a11c47e)) influences items on new lines
								- ```css
								  /* This is the hidden default */
								  flex-wrap: nowrap;
								  
								  /* This wraps boxes so they'll fit on multiple lines */
								  /* If `flex-direction: row` then it'll appear as multiple rows */
								  flex-wrap: wrap;
								  
								  /* Creates the new line instead above the old line */
								  /* Also reverses the align-items settings */
								  flex-wrap: wrap-reverse;
								  ```
							- `align-content`
							  collapsed:: true
								- Only matters if ((63715d59-200c-4485-9113-aedd733d348c)) is enabled
								- Similar to ((636feb2e-8de3-4ed4-9283-f557d4150b4a)) except it controls the wrapped **lines** rather than the individual elements
								- ```css
								  /* This is the hidden default */
								  align-content: stretch;
								  
								  /* Wrapped lines will act similarly to `align-items` settings */
								  align-content: flex-start;
								  
								  align-content: flex-end;
								  align-content: center;
								  
								  /* Wrapped lines will act similarly to `justify-content` settings */
								  align-content: space-around;
								  align-content: space-between;
								  ```
							- flex shorthand
								- `flex`
								  collapsed:: true
									- ```css
									  /* Shortcut for flex-grow, flex-shrink, flex-basis */
									  flex: number number size;
									  /* Shortcut for flex-grow: 1, flex-shrink: 1, flex-basis: 300px */
									  flex: 1 1 300px;
									  /* Shortcut for flex-grow: 1, flex-shrink: 0, flex-basis: auto */
									  flex: 1 0 auto;
									  
									  /* Shortcut for flex-grow: 1, flex-shrink: 0, flex-basis: 0px (default only when called via `flex`)
									    Normally `flex-basis` defaults to `auto`, but in the `flex` shorthand it becomes 0px */
									  flex: 1 0;
									  /* Shortcut for flex-grow: 0 (default), flex-shrink: 1 (default), flex-basis: 300px */
									  flex: 0 300px;
									  /* Shortcut for flex-grow: 1, flex-shrink: 1 (default), flex-basis: 0px */
									  flex: 1;
									  
									  /* Shortcut for flex-grow: 1, flex-shrink: 1 (default), flex-basis: auto */
									  flex: auto;
									  /* Shortcut for flex-grow: 0 (default), flex-shrink: 0, flex-basis: auto */
									  flex: none;
									  ```
								- `flex-flow`
								  collapsed:: true
									- ```css
									  /* Sets both the flex-direction: column and flex-wrap: wrap simultaneously */
									  flex-flow: column wrap;
									  ```
					- [Flex Box Adventure](https://codingfantasy.com/games/flexboxadventure)
			- Related:
				- ((63bae0b8-d0c9-4372-be3c-15058f74bc75))
				- ((636fc3bd-f438-46b6-be13-5c2ccce742be))
		- Grid
		  id:: 636fc3bd-f438-46b6-be13-5c2ccce742be
		  collapsed:: true
			- Tailwind version
				- `grid-cols-[3fr 2fr]` equivalent is...
			- Games
			  id:: 6370bbc6-4a50-4d1e-98f7-c885b7e7cc63
				- [Grid Critters](https://mastery.games/gridcritters/)
				  id:: 6370bbd9-31d4-447b-857c-6d1bf6bda5c7
				  collapsed:: true
					- How to play
					  collapsed:: true
						- ![image.png](../assets/image_1668418649143_0.png)
							- Thick dashes is the target grid
							- The arrows and dotted lines point towards the current
						- Related: ((63715cdb-3cff-4992-b122-a437728aee02))
					- Chapters
						- `display: grid`, `grid-template-columns`, `grid-template-rows`
							- `display: grid`
							  Enables CSS Grid
								- ((63717e44-c215-45c5-9f9f-40a1bcd57112)) is the default
							- *Tracks*
							  A horizontal or vertical slice of the gris which can be sized and filled with items
								- `grid-template-rows`
								  id:: 63717e44-c215-45c5-9f9f-40a1bcd57112
									- ```css
									  /* This is the hidden default */
									  grid-template-rows: 1fr 1fr 1fr;
									  
									  /* Create two stacked rows, each with 100px height */
									  grid-template-rows: 100px 100px;
									  ```
								- `grid-template-columns`
									- ```css
									  /* Create three colums, with the first being 1 fraction of the available space, 2nd being 2, and 3rd being 1 */
									  grid-template-columns: 1fr 2fr 1fr;
									  
									  /* Create two columns, with the first being 100px wide and the rest taking up the remaining space */
									  grid-template-columns: 100px 1fr;
									  ```
								- Stuff that applices to both tracks
									- Can be combined with ((63717e44-c215-45c5-9f9f-40a1bcd57112))
									  ```css
									  planet {
									    display: grid;
									    grid-template-columns: 100px 25% 1fr;
									    grid-template-rows: 1fr 100px 25%;
									  }
									  ```
									- `repeat` allows for tracks to be easily repeated
									  id:: 637210b8-917e-4919-8cb2-4789a902f766
										- ```css
										  /* This line below */
										  grid-template-columns: 100px 100px 100px 100px;
										  
										  /* Is equivalent to */
										  grid-template-columns: repeat(4, 100px);
										  
										  /* Can't repeat with fr? */
										  ```
										- Related: ((6373edf0-86a9-45c1-a946-ade0cef54e60))
									- Can easily repeat patterns
									  ```css
									  /* This line below */
									  grid-template-columns: 50px 100px 50px 100px 50px 100px;
									  
									  /* Is equivalent to */
									  grid-template-columns: repeat(3, 50px 100px);
									  ```
									- Types of measurement units
										- `px` pixels
										- `fr` fractions
										  collapsed:: true
											- ```css
											  grid-template-columns: 1fr 100px 1fr;
											  ```
										- `vh` and `vw`units
										  collapsed:: true
											- They're like percents but relative to the viewport's height/width rather than the Grid element's height/width
											- ```css
											  grid-template-columns: 1fr 20vw;
											  grid-template-rows: 20vh 1fr 20vh;
											  ```
										- `%` is relative to the height of the Grid
						- `grid-gap`
						  collapsed:: true
							- Can't be specified with `fr`, but can with `vw, vh, %, px, rem,` etc
							- `grid-gap`
							  Sets gap between both columns and rows, like a `+`
								- ```css
								  grid-template-columns: 1fr 1fr;
								  grid-template-rows: 1fr 1fr;
								  
								  /* Sets both to the same */
								  grid-gap: 100px;
								  
								  /* Sets rows to 200, columns to 50 */
								  grid-gap: 200px 50px;
								  ```
							- `grid-row-gap`
							  Gap between each row
							  ```css
							  grid-template-rows: 1fr 1fr 1fr;
							  grid-row-gap: 70px;
							  ```
							- `grid-column-gap`
							  Gap between each column
							  ```css
							  grid-template-column: 1fr 1fr 1fr;
							  grid-column-gap: 70px;
							  ```
							- Should prefer to use `fr` for sizing the tracks if using `gap`, because `%` in contrast may be forced to make a grid greater than 100%
						- `grid-row-start`, `grid-row-end`, `grid-column-start`, `grid-column-end`
						  collapsed:: true
							- It goes by lines, not tracks. So 3 rows creates 4 lines
							- `grid-row-start`
							  id:: 63734dfc-6cbf-46b9-8621-180c7e932e0a
								- Create a track starting at row 3 (down to 4)
								  ```css
								  planet { 
								    display: grid; 
								    grid-template-rows: repeat(3, ifr);
								  
								  rocky {
								    grid-row-start: 3;
								  }
								  ```
							- `grid-row-end`
							  id:: 6373d039-fe4e-42ca-bcff-004220dd5d58
							- `grid-column-start`
							  id:: 6373d020-048e-47ac-a6a1-5641661fe158
							- `grid-column-end`
							  id:: 6373d03d-ee39-46bd-a611-2c6412469e3e
							- These can be combined to create subgrids
								- ```css
								  planet {
								    display: grid;
								    grid-template-rows: 200px 1fr 1fr 100px;
								    grid-template-columns: 200px 1fr 1fr 100px;
								  }
								  
								  rocky {
								    grid-column-start: 2;
								    grid-column-end: 5;
								    grid-row-start: 2;
								    grid-row-end: 4
								  }
								  ```
							- Negative numbers means it counts from the opposite direction
								- ```css
								  planet {
								    display: grid;
								    grid-template-columns: 15% 1fr 1fr 15%;
								    grid-template-rows: 15% 1fr 1fr 15%;
								  }
								  
								  grass {
								    grid-column-start: 1;
								    grid-column-end: -1; /* the ending line */
								    grid-row-end: -2 /* one line away from the ending line */
								  }
								  ```
							- `span`
							  collapsed:: true
							  This is how many tracks you want your grid to take up. This keeps it at a fixed size
								- It has the same effect whether you use it with `end` or `start`. If both are set however, then `start` wins
									- You can make it flow in reverse with: ((6373d9e3-532e-4074-a3c7-63098d7fc3af))
								- You can now set the items’ ending line with a span instead of a fixed line number. So to position these dunes you'd just set `grid-row-end: span 3`;
								- Example
									- ```css
									  planet {
									    display: grid;
									    grid-template-columns: repeat(2, 1fr);
									    grid-template-rows: repeat(4, 1fr);
									  }
									  
									  dunes {
									    grid-row-end: span 1;
									  }
									  ```
								- Using a `start` span and a normal end however can make items span in the opposite direction of the flow of the Grid
								  id:: 6373d9e3-532e-4074-a3c7-63098d7fc3af
									- ```css
									  ```
							- `grid-row`
								- Lets you set ((63734dfc-6cbf-46b9-8621-180c7e932e0a)) and ((6373d039-fe4e-42ca-bcff-004220dd5d58)) simultaneously
								- ```css
								  grid-row: 2 / 5;
								  /* 
								  That is the equivalent of setting it to: 
								  	grid-row-start: 2; 
								  	grid-row-end: 5;
								  */
								  ```
								- End value is optional
							- `grid-column`
								- Lets you set ((6373d020-048e-47ac-a6a1-5641661fe158)) and ((6373d03d-ee39-46bd-a611-2c6412469e3e)) simultaneously
							- The lines created by `grid-template` can be named with `[]`
								- ```css
								  /* Hidden permanent default */ 
								  grid-template-columns: [1] 1fr [2] 1fr [3] 1fr [4] 1fr [5];
								  
								  /* Example custom names */
								  grid-template-columns: [one] 1fr [two] 1fr [three] 1fr [four] 1fr [five];
								  grid-template-columns: [start] 1fr 1fr [center] 1fr 1fr [end];
								  grid-template-columns: 1fr [middle center] 1fr; /* either alias can then be used later */
								  grid-template-rows: 1fr [neat-line awesome-line] 1fr; /* either alias can then be used later */
								  
								  /* Utilising custom names in other properties or elements  */
								  grid-column-start: center
								  grid-column-end: five;
								  grid-row: top / bottom;
								  grid-column: start / center;
								  ```
								- Can set multiple lines to the same name in a ((637210b8-917e-4919-8cb2-4789a902f766))
								  id:: 6373edf0-86a9-45c1-a946-ade0cef54e60
									- ```css
									  planet {
									    display: grid;
									    grid-template-columns: 1fr repeat(5, 50px) 1fr;
									  }
									  
									  grass {
									    grid-template-columns: 1fr repeat(5, [grass] 50px) 1fr;
									    /* 
									    Note: this won't the final line 7 as grass. Need to add that name before the final 1fr
									    e.g. 
									    grid-template-columns: 1fr repeat(5, [grass] 50px) [grass] 1fr;
									    */
									  }
									  ```
									- Can then easily set items to start at your whatever repeat item
										- ```css
										  grid-column: grass 2 / span 5;
										  ```
					- Sandbox
						- ```css
						  d
						  ```
				- [Grid Garden](https://cssgridgarden.com/)
				  collapsed:: true
					- [Grid Garden - A game for learning CSS grid](https://codepip.com/games/grid-garden/)
				- [Grid Attack](https://codingfantasy.com/games/css-grid-attack)
			- ((6370c3c3-cbd0-422d-b38d-fcce43135140))
			- ((642714a2-3be7-4880-8f78-16d96a90eb9c))
			- [Learning Resources]
				- https://mastery.games/post/new-grid-site/
				- [CSS Grid — Learn all about CSS Grid with Wes Bos in this free video series!](https://cssgrid.io/)
				- https://css-tricks.com/snippets/css/complete-guide-grid/
				- [Oxbow UI - Tailwind CSS Grid Generator](https://oxbowui.com/free-tools/tailwind-css-grid-generator)
			- Related: ((634d8f7c-e565-4a7a-9a3e-31c22a40c819))
		- Selectors
		  collapsed:: true
			- Games
				- ((63317807-bd1e-430c-bf63-985d824439f1))
				- [CSS Scoops](https://codepip.com/games/css-scoops/)
				  id:: 6370c9d9-b570-4c6d-b852-2de53a531b63
				- [Nth Cart](https://codepip.com/games/nth-cart/)
				  id:: 6370c9e7-380e-42a2-b8eb-7fd915c4876b
					- Recommended to play ((6370c9d9-b570-4c6d-b852-2de53a531b63)) first
				- [Selector Showdown](https://codepip.com/games/selector-showdown/)
					- Recommended to play ((6370c9e7-380e-42a2-b8eb-7fd915c4876b)) first
		- Animations
		  id:: 6370be0c-c604-441e-97f8-613d701cf0e5
		  collapsed:: true
			- Games
				- [Unfold](https://rupl.github.io/unfold)
				  collapsed:: true
					- [CSS 3D Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
					- Contributions: [https://github.com/rupl/unfold](https://github.com/rupl/unfold)
					- Creator: [Chris Ruppel](https://chrisruppel.com)
				- [Roadmap](http://victordarras.fr/cssgame)
				  collapsed:: true
					- Skill and speed are required to solve this little game, only made with 
					  CSS and HTML. It is not directly teaching CSS, but looking into the 
					  source code teaches a lot about  `clip-path` ,  `transform`  and  `animation`  with  `@keyframes` !
					  Drop a comment how many attempts you needed to win - I needed 8!
				- Carnival
				  collapsed:: true
					- Game: [[404 on CodePen](https://codepen.io/una/pen/NxZaNr](https://codepen.io/una/pen/NxZaNr))
					- Creator: [Una Kravets](https://github.com/una)
				- Tic-Tac-Toe
				  collapsed:: true
					- Game: [[404 on CodePen](https://codepen.io/alvaromontoro/pen/BexWOw](https://codepen.io/alvaromontoro/pen/BexWOw))
					- Creator: [Alvaro Montoro](https://github.com/alvaromontoro)
			- [Character Animation](https://mastery.games/post/character-animation/)
			- Related: ((63fdff47-1079-4514-b26e-b47f3f21218d))
		- Buttons
		  collapsed:: true
			- ((63904f42-bdaf-4e4c-b124-5500a593053b))
			- [Copy & Paste CSS - Buttons Design](https://copy-paste-css.com/)
		- How to centre a div
		  collapsed:: true
			- ```
			  display: block
			  align-content: center
			  ```
				- property in 2024
			- ((67376778-11fb-487a-9cfb-6b8ade08e11d))
		- [CSS just changed forever… plus 7 new features you don't know about](https://youtu.be/A89FMtIkWKc)
			- `@property at-rule` in CSS houdini
				- You can use types e.g. specify `color` as a string, which allows you to use it in animations
				- ```css
				  @property --pink {
				    syntax: '<color>';
				    inherits: false;
				    initial-value: hotpink;
				  }
				  ```
			- `@starting-style`
				- Useful when you have a dialog or popover or anything with `display: none`
				- ```css
				  @starting-style {
				    dialog[open] {
				      translate: 0 100vh;
				    }
				  }
				  
				  dialog[open] {
				    translate: 0 0;
				    transition: translate 0.7s, display 0.7s allow-discrete;
				  }
				  ```
			- `round()`, `rem()`, `mod()` - programming concepts
				- `rem()` + `mod()` work like ((646349af-f069-46fb-868a-d3057dbbb2a7))
				- `round()` can be used for floor, ceiling and truncate
			- light-dark function for light or dark themes
				- ```css
				  :root {
				    color-scheme: light dark;
				  }
				  
				  .omni-theme {
				    background: light-dark(white, black);
				    color: light-dark(black, white);
				  }
				  ```
			- `:user-valid pseudo class` for form validation triggering *after* the user has interacted with a form
			- CSS container queries
			- Subgrid
			- `:has()`
				- `interpolate-size`
					- `allow-keywords` value allows you
- # Ecosystem
	- Meta
		- [The Best Of CSS - Tailwind vs MUI vs Bootstrap vs Chakra vs... - YouTube](https://youtu.be/CQuTF-bkOgc)
		  collapsed:: true
			- {{video https://youtu.be/CQuTF-bkOgc}}
				- {{youtube-timestamp 106}} UI Libraries venn diagram
					- 3 main categories
						- CSS++
						  id:: 63dd9959-c9b9-4f25-bde5-b4f28dceeaa8
							- Extensions of CSS
							- ((6377eced-09db-4b3b-84c8-2924fc9190a8))
							- ((63c5817b-580c-4641-aa19-db7b4117f4cf))
							- ((63dd9bb7-d0cc-4d66-a7a7-7b421381b319))
						- Behaviour libraries
						  id:: 63dd9963-f7c8-48e7-a95f-c7bfe15c91f6
							- i.e. they're JavaScript e.g. dropdown behaviour
							- ((63baa37f-b2c9-4d39-96df-8fb2b1e182c1))
							- ((63c5817c-2322-4bf9-97e6-0f92dfb6a96a))
							- ((63dd9c8e-27a7-4fcb-8357-2ebba73d4d4f))
							- [GitHub - atlassian/pragmatic-drag-and-drop: Fast drag and drop for any experience on any tech stack](https://github.com/atlassian/pragmatic-drag-and-drop)
							-
						- Style systems
						  id:: 63dd997d-0505-410d-8954-07d16d56335c
							- i.e. they're CSS
							- ((63c5817c-8e31-4b9b-99aa-3a7ad54f0efb))
								- {{youtube-timestamp 326}} It gives opinionated components made up of dozens of lines of CSS. Customising these is a chore
						- Hybrid
							- ((63dd9959-c9b9-4f25-bde5-b4f28dceeaa8)) + ((63dd997d-0505-410d-8954-07d16d56335c))
							  id:: 63dd9d0e-d424-4357-855b-d08dc9ca39cb
								- ((63baa37f-5920-45d5-a914-c8c491d3d931))
								- ((e3e2d944-cadc-4941-b3a0-46b66807c2dc))
								- ((63dda882-b2fb-45f7-a0ae-60589403fbeb))
							- "Component Libraries" ((63dd9963-f7c8-48e7-a95f-c7bfe15c91f6)) + ((63dd997d-0505-410d-8954-07d16d56335c))
							  id:: 63dd9ce3-153e-497c-bd52-16054b615328
								- ((63cd2be7-ac29-4b73-82da-c24c850cf6d9))
								- ((63baa37f-9ef7-4ad3-89b4-316054f5d71b))
							- All 3 - ((63baa37f-e0e1-4804-b17e-ca989b9a367f))
						- **Most interesting to look into**
							- ((6377eced-09db-4b3b-84c8-2924fc9190a8)) : ((639c8102-0945-4034-bed7-e5935aa033ef))
								- e.g. ((63baa37f-5920-45d5-a914-c8c491d3d931)), ((e3e2d944-cadc-4941-b3a0-46b66807c2dc))
							- ((63dd9963-f7c8-48e7-a95f-c7bfe15c91f6))
								- {{embed ((63dd9963-f7c8-48e7-a95f-c7bfe15c91f6))}}
				- {{youtube-timestamp 770}} Ugly - Beautiful diagram
				  collapsed:: true
					- ![image.png](../assets/image_1675468526057_0.png)
					-
				- {{youtube-timestamp 1102}} Spectrum of syntax being different to CSS diagram
				  collapsed:: true
					- 0 - "It's some weird shit"
						- ((63baa37f-e0e1-4804-b17e-ca989b9a367f))
							- {{youtube-timestamp 1181}} It looks complex af
						- ((63cd2be7-ac29-4b73-82da-c24c850cf6d9))
					- 6
						- ((63c5817c-8e31-4b9b-99aa-3a7ad54f0efb))
					- 9
						- ((6377eced-09db-4b3b-84c8-2924fc9190a8))
					- 10 - [[CSS]]
				- {{youtube-timestamp 1308}} Styled Components - was a revolutionary feature at the time
					- Like Storybook, is only good at that
				- ![image.png](../assets/image_1673527017069_0.png)
	- Frameworks
		- CSS frameworks
		  id:: 629ccb26-0f8b-4a06-a8bb-6e57ecbfc824
		  collapsed:: true
			- Pros/Cons
			  collapsed:: true
				- Cons
					- CSS-in-JS is the new thing, and especially suited to those who focus on JS frameworks
					- Old school HTML/CSS developers lament the lack of jobs for their skills compared to React or other JS developers
					  https://css-tricks.com/the-great-divide/
			- *Examples*
				- [Tailwind](https://tailwindcss.com)
				  id:: 6377eced-09db-4b3b-84c8-2924fc9190a8
				  collapsed:: true
					- Pros/Cons
					  collapsed:: true
						- Pros
							- More concise than writing CSS e.g. 1/3rd less characters?
							  collapsed:: true
								- It combines CSS properties and selectors
							- Lots of ((639c8102-0945-4034-bed7-e5935aa033ef))
							- It has a coherent design system
							  collapsed:: true
								- e.g. `bg-red-100`
								- Elaborated on in ((63bfff73-6f35-40ba-b6bf-c3c538b13aaf))
							- Fewer class names
							  collapsed:: true
								- You end up creating arbitrarily named classes otherwise which don't make sense after a while, having classes that make sense works better
							- Media queries, hover effects and dark mode are very easy
							  id:: 6385cc53-f1f2-4695-b752-e4d1c43bc3ac
							  collapsed:: true
								- Also it has built in media query support. so for example you can set specific elements to change how they display at different screensizes
								  and you can specify these sizes in the config (they have defaults dont worry)
								  super easy mate
								  <div className="p-10 md:p-20 lg:p-40">
								  this would mean at default size padding is 10 on medium screen its 20 and large its 40
							- Alternative to CSS modules (i.e. scoping CSS to a component)
							  collapsed:: true
								- A handy, low-effort feature supported by Create React App, which allows you to scope CSS rules to just a component: [Adding a CSS Modules Stylesheet | Create React App](https://create-react-app.dev/docs/adding-a-css-modules-stylesheet/) This is a good idea, as it ensures that one component's CSS rules don't affect another, even if they happen to use the same class names
						- Cons
							- Ugly ass HTML with many classes
							- Learning curve
							- Requires tooling
								- Works best with component systems like React because then you can just apply Tailwind to parent components in order to have them apply to children
							- Tailwind critique [Don't use Tailwind for a design system (2021) | Hacker News](https://news.ycombinator.com/item?id=34336576)
							- [Feature creep (2022)](https://news.ycombinator.com/item?id=33298806)
							  collapsed:: true
								- Because Tailwind wants to stay relevant and popular, lots of features get added regularly. This makes it more difficult to utilise the framework (especially beginners) when it's supposed to be a time-saving solution compared to CSS
								- Counters
									- You don't have to use the additional features
									- Tailwind stylesheets are always going to be much smaller than normal CSS for any decently-sized app.
									- You no longer have to think about class names - The point of Tailwind is to give everyone a common vernacular of CSS phrases so that I can bust out something like "p-2 m-2 border-red" super fast and still be writing code which is immediately comprehensible to everyone else on my team
									- I
							- https://news.ycombinator.com/item?id=33787218
							-
						- {Archive}
							- [Tailwind CSS is the worst… - YouTube](https://youtu.be/lHZwlzOUOZ4)
					- Documentation
						- [Tailwind CSS Cheat Sheet](https://tailwindcomponents.com/cheatsheet/)
						- Setup
							- [Install Tailwind CSS with Next.js - Tailwind CSS](https://tailwindcss.com/docs/guides/nextjs)
							  collapsed:: true
								- `npm install -D tailwindcss postcss autoprefixer`
								- `npx tailwindcss init -p`
								- Update `tailwind.config.js`
									- Change `content` property
									  ```js
									    content: [
									      "./app/**/*.{js,ts,jsx,tsx}",
									      "./pages/**/*.{js,ts,jsx,tsx}",
									      "./components/**/*.{js,ts,jsx,tsx}",
									   
									      // Or if using `src` directory:
									      "./src/**/*.{js,ts,jsx,tsx}",
									    ],
									  ```
								- Update `globals.css`
									- ```css
									  @tailwind base;
									  @tailwind components;
									  @tailwind utilities;
									  ```
							- [Install Tailwind CSS with Create React App - Tailwind CSS](https://tailwindcss.com/docs/guides/create-react-app)
							  collapsed:: true
								- `npx tailwindcss init -p`
							- Plugins
								- Official [Prettier plugin for Tailwind CSS](https://github.com/tailwindlabs/prettier-plugin-tailwindcss)
								  collapsed:: true
									- Pros
										- Easy to see if there's conflicting classes
										- Code review is easier because there's a standardised order for classes
									- `npm install -D prettier prettier-plugin-tailwindcss`
						- Cheatsheet
							- Make a coloured border around elements to make it more visible for editing e.g. `border-4 border-yellow-500`, `bg-green-300`, etc
							- How I imagine the pitch for this idea went: "What if we could use `class=` exactly the same way we use `style=`?!"
								- That’s the point… it’s hyper descriptive and actually cascades nicely instead of inline styles. It’s best with components so that when you actually dig down you can read exactly how something should render and then abstract a layer up into UserCardIcon or whatever for the actual purpose
						- Learnings from SoC project
							- You can use interpolated variables and functions as Tailwind classes
							  collapsed:: true
								- `https://github.com/ajvsol/FoodBankNetwork/blob/main/pages/find/index.tsx`
									- ```tsx
									  className={` overflow-auto ${selectedCardCheck(index)} space-y-1 ${tailwindMobileList} `}
									  ```
								- Alternative: tailwind-merge
							- Refresh the page - sometimes it doesn't immediately apply
						- [Custom styles](https://tailwindcss.com/docs/adding-custom-styles)
						- [Arbitrary values](https://tailwindcss.com/docs/adding-custom-styles#using-arbitrary-values) (escape hatch)
						- [Avoid `@apply`](https://youtu.be/QBajvZaWLXs?t=260)
					- UI component libraries
					  id:: 639c8102-0945-4034-bed7-e5935aa033ef
						- *My favourites*
							- ((38a466b9-69e8-4dfe-abb0-c7a6caf840e3))
						- [Flowbite](https://flowbite.com)
						  id:: 4835154b-ee19-4ffb-9430-384808c2ff9e
						  collapsed:: true
							- [Flowbite React](https://flowbite-react.com/)
							  id:: 38a466b9-69e8-4dfe-abb0-c7a6caf840e3
							- [GitHub - themesberg/flowbite-react: Official React components built for Flowbite and Tailwind CSS](https://github.com/themesberg/flowbite-react)
						- [Konsta UI](https://konstaui.com/)
						  collapsed:: true
							-
						- [Tailwind UI](https://tailwindui.com) (£120)
						  id:: e3e2d944-cadc-4941-b3a0-46b66807c2dc
						- [Tailwind Elements](https://tailwind-elements.com)
						- [Tailwind Components](http://tailwindcomponents.com/)
						- [Sailboat UI](https://sailboatui.com/)
						- [Headless UI](https://headlessui.com)
						  id:: 63c5817c-2322-4bf9-97e6-0f92dfb6a96a
							- [Combobox (Autocomplete) - Headless UI](https://headlessui.com/react/combobox)
								- Basically a dropdown menu with text field for searching
						- [DaisyUI](https://daisyui.com/)
						  id:: 63baa37f-5920-45d5-a914-c8c491d3d931
						  collapsed:: true
							- [GitHub - saadeghi/daisyui: ⭐️ ⭐️ ⭐️ ⭐️ ⭐️  The most popular, free and open-source Tailwind CSS component library](https://github.com/saadeghi/daisyui)
							- How to install
								- You need ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) and Tailwind CSS installed.
								- `npm i daisyui` = install daisyUI
								- Update `tailwind.config.js`
									- ```js
									  module.exports = {
									    //...
									    plugins: [require("daisyui")],
									  }
									  ```
						- [https://github.com/thedevdojo/tails](https://github.com/thedevdojo/tails)
						- [https://merakiui.com/](https://merakiui.com/)
						- [[Loading...](https://www.gustui.com/](https://www.gustui.com/))
						- [https://mertjf.github.io/tailblocks/](https://mertjf.github.io/tailblocks/)
						- [[404: This page could not be found](https://www.hyperui.dev/](https://www.hyperui.dev/))
						- Tailwind visual builder
						  collapsed:: true
							- [https://devdojo.com/tails](https://devdojo.com/tails)
							- [https://shuffle.dev/](https://shuffle.dev/)
						- [[404: This page could not be found](https://www.tailwind-kit.com/](https://www.tailwind-kit.com/))
						- [Horizon UI](https://horizon-ui.com/horizon-tailwind-react/) (made for an admin dashboard template)
						  id:: 63fddd5a-0281-48d1-8635-f9f409d5706d
						  collapsed:: true
							- [GitHub - horizon-ui/horizon-tailwind-react: ❇️ Horizon UI Tailwind CSS React | The most trendiest & innovative Open Source Admin Dashboard Template for Tailwind CSS & React!](https://github.com/horizon-ui/horizon-tailwind-react)
							- [Horizon UI Components | Best Chakra UI, Tailwind CSS & React Components](https://horizon-ui.com/components/?ref=readme-horizon-tailwind-react)
					- Ecosystem
						- [Tailwind colour palette generator](https://www.tints.dev/brand/2522FC)
						- [Tailscan - Browser inspector for Tailwind CSS](https://tailscan.com)
						-
					- [Learning Resources]
						- [Reusing Styles - Tailwind CSS](https://tailwindcss.com/docs/reusing-styles)
						- [Refactoring UI](https://refactoringui.com)
						  id:: 63bfff73-6f35-40ba-b6bf-c3c538b13aaf
							- Book recommended by Theo t3.gg
							-
				- [Bootstrap](https://getbootstrap.com)
				  collapsed:: true
				  id:: 63c5817c-8e31-4b9b-99aa-3a7ad54f0efb
					- Cons
					  collapsed:: true
						- UX monotony:
						  collapsed:: true
							- The very fact that Bootstrap has such a large collection of built-ins results in websites that look all-too-familiar, and quite honestly, dull. You only need to head over to the official examples to see just how much of an eyesore the defaults are.  Just search for “all bootstrap websites look the same,” and you’ll know what I mean.
							  https://getbootstrap.com/docs/4.1/examples/
						- Styling woes:
						  collapsed:: true
							- is what might be considered an opinionated framework. In other words, it has ideas about layouts, and it makes you work extra hard if you want it to look/behave differently. Consider the default CSS breakpoints for screen widths: a medium-sized screen for Bootstrap is one that starts at a device width of 768px. And what if you want to target, say, the limit of 600px? Well, good luck with that! It’s the same with almost every other component in bootstrap: rows and containers have their default padding, buttons have colors and borders that are very tricky to override without a lot of work, and so on.
					- Bootstrap is an open source toolkit for developing with HTML, CSS, and JS. Quickly prototype your ideas or build your entire app with our Sass variables and mixins, responsive grid system, extensive prebuilt components, and powerful plugins built on jQuery.
					- Bootstrap is a free and open-source front-end Web framework. It contains HTML and CSS-based design templates for typography, forms, buttons, navigation and other interface components, as well as optional JavaScript extensions. Unlike many earlier web frameworks, it concerns itself with front-end development only.
					- out of the box, almost all the UI components you’re ever likely to need. Navigation, forms, cards, modals, buttons, badges, progress bars, alerts
					- LESS and SASS support: Among the massively popular CSS frameworks, Bootstrap is the only one that supports both LESS and SASS. Yes, I know, you don’t use LESS (as no self-respecting developer should, right?), but hey, there are massive projects out there that rely on LESS. Of course, you can choose neither and write out your plain CSS files.
				- [Foundation](https://get.foundation/sites/docs/)
				  collapsed:: true
					- https://foundation.zurb.com/
				- [Blaze UI](https://www.blazeui.com/)
				- [UIKit](https://www.patternfly.org/v4/documentation/core/components/aboutmodalbox)
				- *Utility CSS*
					- [Bonsai CSS](https://www.bonsaicss.com/)
				- *Web Components*
					- [Weightless](https://weightless.dev/elements/checkbox)
					- [Shoelace](https://shoelace.style/)
				- [Bulma](https://bulma.io/)
				- [Master](https://master.co/)
				  id:: 63dda882-b2fb-45f7-a0ae-60589403fbeb
			- [Learning Resources]
			  collapsed:: true
				- https://geekflare.com/best-css-frameworks/
		- [CSS-in-JS libraries](((629ccb26-23a1-4361-8de0-d8e3d34c8ce1)))
		- Frameworks for CSS
		  collapsed:: true
			- [Charts.css: CSS data visualization framework](http://chartscss.org/)
			- Related: ((629ccb26-0f8b-4a06-a8bb-6e57ecbfc824))
	- UI Component libraries
	  id:: 63cd2ade-32a8-4e07-951a-bad6d9a022f4
	  AKA component library
		- Journal
		  collapsed:: true
			- Week 16 project [[Jan 22nd, 2023]] - Removing ((63baa37f-3362-4080-82d6-c1521af1ed2f)) cards because they have poor ((6377eced-09db-4b3b-84c8-2924fc9190a8)) support (e.g. for hover, dark mode). Already have ((4835154b-ee19-4ffb-9430-384808c2ff9e)) navbar, so using their cards also
		- Options
			- ((63dd9963-f7c8-48e7-a95f-c7bfe15c91f6))
				- {{embed ((63dd9963-f7c8-48e7-a95f-c7bfe15c91f6))}}
			- Supports multiple frameworks
			  collapsed:: true
				- [UK Intelligence Community Design System](https://design.sis.gov.uk/)
				  id:: 661ce09e-32e4-46f5-a5cb-d0b4747c9a69
				  Supports ((629ccb26-62cc-426a-9616-4d8969f32580)), Angular, Vue, Svelte, Web Components
			- Built for ((6377eced-09db-4b3b-84c8-2924fc9190a8))
			  collapsed:: true
				- {{embed ((639c8102-0945-4034-bed7-e5935aa033ef))}}
			- Built for ((635fba79-b85e-4821-810a-ce45a268a6ad))
			  collapsed:: true
				- [Precedent](https://precedent.dev/)
				  collapsed:: true
					- [GitHub - steven-tey/precedent: An opinionated collection of components, hooks, and utilities for your Next.js project.](https://github.com/steven-tey/precedent)
			- Built for ((629ccb26-62cc-426a-9616-4d8969f32580))
			  id:: 636f80b0-9945-4922-850d-aaeceb3a0b2f
			  collapsed:: true
				- *MUI Core libraries*
				  id:: 663a578a-8bbf-4695-a133-0b4739988a47
					- [Material UI](https://mui.com/) (styled with [Material Design](https://m3.material.io/))
					  id:: 63cd2be7-ac29-4b73-82da-c24c850cf6d9
					  collapsed:: true
						- [GitHub - mui/material-ui: MUI Core: Ready-to-use foundational React components, free forever. It includes Material UI, which implements Google's Material Design.](https://github.com/mui/material-ui)
						-
					- [Joy UI](https://mui.com/joy-ui/getting-started/overview/) (styled with in-house design principles)
					- [MUI Base](https://mui.com/base/react-button/) (unstyled)
						- [How to combine with Tailwind](https://mui.com/base/guides/working-with-tailwind-css/)
				- [Fluent UI](https://developer.microsoft.com/en-us/fluentui#/controls) by Microsoft
				  collapsed:: true
					- Their [Stack](https://developer.microsoft.com/en-us/fluentui#/controls/web/stack) component abstracts flexbox
				- [Chakra UI](https://chakra-ui.com/)
				  id:: 63baa37f-e0e1-4804-b17e-ca989b9a367f
				  collapsed:: true
					- [GitHub - chakra-ui/chakra-ui: ⚡️ Simple, Modular & Accessible UI Components for your React Applications](https://github.com/chakra-ui/chakra-ui)
				- [NextUI](https://nextui.org/)
				  id:: 63baa37f-3362-4080-82d6-c1521af1ed2f
				  collapsed:: true
					- uses Stitches, includes light and dark UI components out-of-the-box along with a default color palette that might be good for quickly building landing pages or other content that’s not initially tied to any branding.
				- ((38a466b9-69e8-4dfe-abb0-c7a6caf840e3))
				- [https://www.tremor.so/](https://www.tremor.so/)
				  collapsed:: true
					- Simple and modular components to build dashboards in a breeze. Fully open-source, made by data scientists and software engineers with a sweet spot for design.
				- [Radix UI](https://www.radix-ui.com/)
				  id:: 63baa37f-b2c9-4d39-96df-8fb2b1e182c1
				  collapsed:: true
					- Unstyled, accessible components for building high‑quality design systems and web apps in React.
				- [Mantine](https://mantine.dev/) 
				  id:: 63baa37f-9ef7-4ad3-89b4-316054f5d71b
				  collapsed:: true
					- More than 120 customizable components and hooks to cover you in any situation.
				- [https://akaspanion.github.io/ui-neumorphism/](https://akaspanion.github.io/ui-neumorphism/)
				- [https://component.gallery/](https://component.gallery/)
				- [https://ui.supabase.io/](https://ui.supabase.io/)
				- [React Aria](https://react-spectrum.adobe.com/react-aria/)
				  id:: 63dd9c8e-27a7-4fcb-8357-2ebba73d4d4f
				  collapsed:: true
					-
				- ((661ce09e-32e4-46f5-a5cb-d0b4747c9a69))
	- Other categories
		- CSS Preprocessors
		  id:: 632092ff-369f-4201-b8a9-dd8284401c31
		  collapsed:: true
			- [SASS](https://sass-lang.com/)
			  id:: 63c5817b-580c-4641-aa19-db7b4117f4cf
			  collapsed:: true
				- [Sass cheatsheet](https://devhints.io/sass)
			- [LESS](https://lesscss.org/)
			  id:: 63dd9bb7-d0cc-4d66-a7a7-7b421381b319
			- ((634bc1c4-9288-4b6c-bd1d-a9859612f93f))
		- Modern CSS
		  collapsed:: true
			- ((629ccb26-2f37-4f04-8f15-647f47c825c8))
			- CSS Modules
			  collapsed:: true
				- CSS files in which all class names and animation names are scoped locally by default.
				- [Official WebsiteProject GitHub Repository](https://github.com/css-modules/css-modules)
				- [ReadUsing CSS Modules In React App](https://medium.com/@ralph1786/using-css-modules-in-react-app-c2079eadbb87)
				- [WatchCSS Modules: Why are they great?](https://www.youtube.com/watch?v=pKMWU9OrA2s)
			- Styled JSX
			  collapsed:: true
				- is a CSS-in-JS library that 
				  allows you to write encapsulated and scoped CSS to style your 
				  components. The styles you introduce for one component won't affect 
				  other components, allowing you to add, change and delete styles without 
				  worrying about unintended side effects.
				- [Official DocsGetting started](https://github.com/vercel/styled-jsx)
				- [WatchStyled JSX in Next.js: Master Next.js](https://www.youtube.com/watch?v=SM5uVbfgfdo)
			- Emotion
			  collapsed:: true
				- is a library designed for writing 
				  css styles with JavaScript. It provides powerful and predictable style 
				  composition in addition to a great developer experience with features 
				  such as source maps, labels, and testing utilities. Both string and 
				  object styles are supported.
				- [ReadOfficial Website and Docs](https://emotion.sh/docs/introduction)
				- [WatchStyled components using emotion in React](https://www.youtube.com/watch?v=yO3JU2bMLGA)
		- Modular CSS
		  collapsed:: true
			- Pros/Cons
				- https://spaceninja.com/2018/09/17/what-is-modular-css/
			- Modular Rules
				- When writing styles in a modular system, follow these rules:
					- Don’t use IDs
					- Don’t nest CSS deeper than one level
					- Add classes to child elements
					- Follow a naming convention
					- Prefix class names
			- BEM
				- http://getbem.com/
				- https://en.bem.info/methodology/
			- ((629ccb26-2f37-4f04-8f15-647f47c825c8))
		- Animations
			- [Surprising things that CSS can animate (2020)](https://codersblock.com/blog/the-surprising-things-that-css-can-animate/)
				- https://news.ycombinator.com/item?id=34451002
	- Tools
		- [CSS Pro | A re-imagined Devtools for web design](https://csspro.com/)
- [Learning Resources]
  collapsed:: true
	- # Examples
		- [How to Monetize a Blog](https://modem.io/blog/blog-monetization/)
		  [AB] http://localhost:8193/archive/1729250910.028041/index.html
			- [How to Write a Blog Post About How to Monetize a Blog](https://modem.io/blog/blog-monetization-making-of/)
			  [AB] http://localhost:8193/archive/1729250992.229419/index.html
			-
	- Games
		- Flexbox Froggy - Learn the basics of CSS Flexbox through a fun, interactive game.
		  [[Page not found · GitHub Pages](https://flexboxfroggy.com/](https://flexboxfroggy.com/)Grid) Garden - Master the CSS Grid layout with this interactive game.
		  [[Page not found · GitHub Pages](https://cssgridgarden.com/](https://cssgridgarden.com/)CSS) Diner - A fun way to learn CSS selectors. (SOC week 1 ![:smiley:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/1f603@2x.png))
		  [[CSS Diner - Where we feast on CSS Selectors!](https://lnkd.in/e2DKqUiE](https://lnkd.in/e2DKqUiE)Flexbox) zombies - The game features zombie characters and challenges that require players to use the Flexbox layout to defeat the zombies and save humanity.
		  [[Flexbox Zombies](https://lnkd.in/ek4fWYgu](https://lnkd.in/ek4fWYgu)CSS) Battle - A multiplayer game that helps you practice CSS skills with others.
		  [https://cssbattle.dev/](https://cssbattle.dev/)
	- SVG Background generator
		- [BGJar | Free svg background image generator for your websites](https://bgjar.com/)
	- [Copy & Paste CSS - Buttons Design](https://copy-paste-css.com/)
	- [CSS Gradient — Generator, Maker, and Background](https://cssgradient.io/)
	- Learning how to combine CSS with React
		- Example of cards repo
		  `/home/boss/Documents/WORK/Programming/School-of-Code/1DRAFT-REPOS/week-7/bc13_w7d2_workshop_react-components-aaron-and-ben-room-40`
	- 11hr [Learn HTML5 and CSS3 From Scratch video course by John Smilga](https://youtu.be/mU6anWqZJcc) - [recommended by freeCodeCamp](https://www.freecodecamp.org/news/html-css-11-hour-course/) to do after their ((62b5cc20-5561-4d6b-aee4-727626c9fb06)) course
	- Recommended by School of Code
	  id:: 62d8037f-3497-4842-8349-1260efc89325
		- https://marksheet.io/
		- https://scrimba.com/learn/design
		- Semantic HTML articles
		  collapsed:: true
			- Semantic HTML is a vital part of the modern web,
			  and learning how to use the right HTML tag for the job is key
			  (which HTML more meaning that just using div tags
			  everywhere).
			- https://www.codecademy.com/learn/learn-html/modules/learn-semantic-html/cheatsheet
			- https://css-tricks.com/why-how-and-when-to-use-semantic-html-and-aria/
			- https://webflow.com/blog/html5-semantic-elements-and-webflow-the-essential-guide
	- ((636f80af-44c2-4f60-9f92-43ebd860c66c))
	- http://www.csszengarden.com/
	- CSS3: The Missing Manual
	  Saved to ATHENAEUM and Calibre
	  collapsed:: true
	  id:: 629ccb26-11e7-4183-bc26-3a72de4fcae6
		- After I became comfortable with basic html/css syntax from online tutorials, this book was invaluable in helping me understand the design principles necessary to create robust and attractive page layouts.
	- Defensive CSS
	  collapsed:: true
		- https://news.ycombinator.com/item?id=31984951
	- [You Might Not Need JavaScript](http://youmightnotneedjs.com/)
		- Cons
			- It might be possible, but it may work worse than JavaScript and not have any performance benefit
	- [[Design_spark-joy]]
	- State of CSS 2022
	  collapsed:: true
		- [State of CSS | Hacker News](https://news.ycombinator.com/item?id=33287471)
			-
		- [Article](https://web.dev/state-of-css-2022/)
			- | **Fresh in 2022** | **2022 and beyond** |
			  | [2022 Browser compatibility](https://web.dev/state-of-css-2022/#browser-compatibility) | [@scope](https://web.dev/state-of-css-2022/#scoping-styles-is-really-hard) |
			  | [@layer](https://web.dev/state-of-css-2022/#cascade-layers) | [@nest](https://web.dev/state-of-css-2022/#nesting-selectors-is-so-nice) |
			  | [subgrid](https://web.dev/state-of-css-2022/#subgrid) | [@media (prefers-reduced-data)](https://web.dev/state-of-css-2022/#css-cant-help-users-reduce-data) |
			  | [@container](https://web.dev/state-of-css-2022/#container-queries) | [@custom-media](https://web.dev/state-of-css-2022/#no-media-query-variables) |
			  | [hwb()](https://web.dev/state-of-css-2022/#hwb) | [Media query ranges](https://web.dev/state-of-css-2022/#was-in-min-width-or-max-width) |
			  | [lch, oklch, lab, oklab, display-p3, etc](https://web.dev/state-of-css-2022/#color-spaces) | [@property](https://web.dev/state-of-css-2022/#loosely-typed-custom-properties) |
			  | [color-mix()](https://web.dev/state-of-css-2022/#color-mix) | [scroll-start](https://web.dev/state-of-css-2022/#scroll-start) |
			  | [color-contrast()](https://web.dev/state-of-css-2022/#color-contrast) | [:snap-target](https://web.dev/state-of-css-2022/#snap-target) |
			  | [Relative color syntax](https://web.dev/state-of-css-2022/#relative-color-syntax) | [snapChanging() and snapChanged()](https://web.dev/state-of-css-2022/#snapchanging) |
			  | [Gradient color spaces](https://web.dev/state-of-css-2022/#gradient-color-spaces) | [toggle()](https://web.dev/state-of-css-2022/#cycling-between-known-states) |
			  | [accent-color](https://web.dev/state-of-css-2022/#accent-color) | [anchor()](https://web.dev/state-of-css-2022/#anchoring-an-element-to-another) |
			  | [inert](https://web.dev/state-of-css-2022/#inert) | [<selectmenu>](https://web.dev/state-of-css-2022/#customizing-select-elements) |
			  | [Color fonts v1](https://web.dev/state-of-css-2022/#colrv1-fonts) |  |
			  | [Viewport unit variants](https://web.dev/state-of-css-2022/#viewport-units) |  |
			  | [:has()](https://web.dev/state-of-css-2022/#has) |
			- Much more info in article about 2021 features etc
		- Video form: [State of CSS - YouTube](https://www.youtube.com/watch?v=Xy9ZXRRgpLk)
		  collapsed:: true
			- YouTube captions
			- [MUSIC PLAYING]  ADAM ARGYLE: Curious about
			  the state of CSS in 2022? I'm Adam Argyle, and I'm super
			  stoked to break that down with y'all. Spoiler though-- it's
			  hot, it's rapidly changing in all the right ways. And designers, tune in, because
			  there are rad goodies in here for y'all as well. But first, a surprise,
			  because we know it's hard when you get
			  new toys but you can't use them because of
			  cross-browser compatibility. Well, last year,
			  five style features were focused on and made
			  incredibly more stable-- Sticky Positioning,
			  aspect-ratio, Flexbox, Grid, and Transforms. A team listened, and they heard
			  compatibility was a pain point when developing for the web. So they hacked on it. Well, that team in
			  2022 went next level. This year, the major
			  browser engines agreed together on
			  what to focus on. I know. It's huge. And not only is the
			  list here amazing. Their collective goal
			  is to complete them by the end of the year. Just look at this list-- @layer,
			  color spaces and functions, containment, the dialog element,
			  form compatibility, scrolling, subgrid, typography,
			  viewport units, and even more web compatibility. Staple features,
			  browsers hacking on them together, life is
			  good for the web.dev. That's the surprise. So let's get nerdy and dig
			  into what's fresh in 2022. Recently stable
			  and first up, see the browser icons with
			  green underlines there? It is cascade layers,
			  also known as @layer. It allows you to customize,
			  control, and orchestrate the cascade. A CSS language feature for
			  wrangling asynchronous loading and third party styles,
			  styles can load late into page lifecycle but be
			  placed into an upper layer as if they were loaded first
			  or second to begin with. So no more meticulously
			  hand-managed CSS loading. (SINGING) Just let it load,
			  let it load, whenever it wants. Assign it to one of your
			  predefined layer nodes. For example here on the left,
			  before @layer, style imports are grouped and
			  meticulously managed so they override in
			  the order desired. But with @layer, you
			  can define the groups and order up front,
			  then let whatever loads layer append into a
			  controlled cascade layer. And there's even more
			  features of cascade layers. Check it out on web.dev or
			  MDN for more information. And also, don't miss
			  the DevTools, where you can see an overview
			  of all the layers, see when styles are in a layer. And layers are organized
			  just like you'd expect. Boom, Subgrid-- this one is a
			  huge win for the Web Layout. Firefox has had this
			  feature for a while. But thanks to Microsoft
			  in the Interop efforts, 2022 intends to catch up
			  in Chromium and webkit. So designers often have
			  page level grid lines that they align
			  tons of children to. Well, that's a
			  capability of Subgrid. There's a grid on the
			  body of this page, with line names like
			  fullbleed and main. The paragraphs and headlines
			  are aligned to the main. And the article
			  image is fullbleed. It's so nice. And here's the CSS for that
			  grid and those defined lines. Gutters are set to auto. And the main is set
			  to 60 characters, or 90% on smaller screens. The children of that grid
			  are given display grid 2, with their columns set
			  as their parents with, well, Subgrid. main-content assigns itself
			  to the main column grid later, like this. And fullbleed content can span
			  the whole page, like this. Wipe your hands
			  clean, and that is it. And also, the
			  DevTools for it rock. You can see which
			  grids define lines and which are adopting them. See the lines on the page with
			  their names and their sizes. Another 2022 interop effort
			  feature is container queries. Before container queries,
			  we could adjust elements to the page viewport
			  without media. And after container queries,
			  we can adjust elements to the size and
			  styles of a container. Components responding
			  to containers instead of containers adjusting
			  children, components owning more of their own styles.
			- Check out this rad demo by Una
			  Kravitz from the Chrome team. Event components, you know, like
			  you made a new event on a day, are shown adapting to their
			  container day columns space. So even though the
			  viewport is being adjusted, the components are only
			  watching their column size. Styles change based on how
			  much column width is available. The demo could change to a one
			  day view or a three day view, and the event
			  components would adapt. Speaking of which, there's
			  a demo that does just that. Watch the book component here. It adapts itself to each
			  section differently, layouts and styles
			  based on container. One component, many
			  built-in adaptions. Demo credits here
			  go to Max Bock. Rad demo, Max. OK, let's see some code. First, you need a container
			  that can be queried. Specify what kind of queries
			  it supports, and give it a name if you want. Container type excepts inline
			  size, like width, block size, like height, just
			  size, or style. Yeah, style, be able to
			  query a container's style-- interesting. But for now, let's
			  focus on size and that calendar-day container. Later, use the @container syntax
			  to query that day container and see if it's 200
			  pixels or smaller. If it's true, those
			  elements selected inside will apply those new styles,
			  just like media queries. You could change
			  from square images to rounded images,
			  card components to go vertical or horizontal,
			  all intelligently. Lots of amazing design
			  and UX possibilities here, and there's even a poly fill
			  so you could try it today. Don't miss Jessalyn [? Yin's ?]
			  Google I/O Talk on DevTools. It'll show you how to
			  debug container queries. Next up is accent-color,
			  available everywhere already, safely and easily tint
			  built-in elements. Bring your brand color to your
			  forms with one line of CSS, and the browser will
			  ensure that there's proper contrast
			  between your color and the checkboxes
			  and the tracks. You can tint everything,
			  like you see here in root, or tint contextually with
			  the targeted selector. Pro tip-- use a media query to
			  check for light or dark theme settings and adapt your
			  accent color to fit better. Kind of like this-- here,
			  I switch from hot pink to light pink for users with
			  their system in dark mode. Now my built-in elements
			  are adaptive and tinted. Color is exploding
			  with features in 2022. We have new color spaces,
			  more colors, built-in color manipulation, and auto contrast
			  functions, all of which are feature goals
			  in Interop 2022. First up is HWB, standing for
			  hue, whiteness, and blackness. And it's an intentionally
			  humanistic way of thinking about color. Here's a quick demo overview. We have five swatches, all
			  with the same hue of 200. Then I adjust the amount
			  of white or black in each. Swatch 1 has 75% white with no
			  black, giving us a light blue. Swatch number 5 has no white
			  and 90% black, a dark blue. HWB is pretty cool,
			  but there is way more. CSS color is about
			  to be unchained from SRGB, the only
			  color space that's been available for like 25 years. 10 more color spaces are coming. You can reach into these
			  color spaces for colors or mix and interpolate
			  with inside of them. Safari Tech Preview has these
			  already available to try. So currently, CSS
			  can only show colors from that inner triangle, SRGB. display-p3, one of
			  the new color spaces, can show the outer triangle. Other spaces can
			  reach even further into that color diagram
			  than display-p3. Color gamuts are
			- the amount of colors to choose from in a space. And I like to think of
			  gamuts like fruit sizes. Think of SRGB like a kiwi
			  and display-p3 like a mango. The bigger the fruit, the more
			  colors you have to choose from. And Lea Verou says, these
			  are not just any colors, but the most vivid colors
			  the screen can display. And she's right. And maybe more colors doesn't
			  sound that interesting. But you thought you were picking
			  hot pink in your color picker. But if you change the color
			  space you're picking from, look at all those brighter
			  colors, like in LAB here. Get a hotter pink. And it doesn't stop at just
			  more vibrant colors either. With new color spaces, there's
			  also new shapes to work within. The RGB cube-- maybe you've
			  seen it-- is suspiciously neat shaped. HSL and some others,
			  they're cylinders. But look at CIE LAB on the right
			  there, a new color space for us in 2022. It's kind of funky, right? It's all stretched and
			  contorted for different colors. It's because SRGB spaces are
			  math driven, where the shown CIE space is human perception
			  driven, hence the imperfect shape. CIE color spaces also
			  feature optimizations for human perception
			  of lightness called perceptually linear. This makes it awesome
			  for mixing colors. Like lighten this
			  color brand by 20%, and it will match your
			  human expectations. Gradients are massively
			  influenced by color spaces. Here's four gradients,
			  all deep pink to cyan, shown in four
			  different color spaces. SRGB in the top left travels in
			  a straight line between the two colors through its cube, going
			  through the middle of the cube and making kind of muddy colors. LAB and LCH, though,
			  on the bottom, they don't travel through
			  this color dead zone. So you thought you were getting
			  beautiful web gradients, but SRGB can only
			  do so much here. Here's some of the
			  new color syntax for accessing these new colors. I call the first
			  LCH color there UX gray because it's 50% from
			  a perceptually linear space. AKA, its 50% gray is
			  not math middle gray, it's human-centric middle gray. Then I create a
			  couple of hot pinks, picking vibrant colors with
			  the LAB and LCH functions. Then there's the color
			  function, accepting a color space and three numbers
			  for each of its channels. I use it here to grab hot pinks
			  in display-p3, LAB, and SRGB. You can progressively
			  enhance your colors too. Of course, it's CSS. The dynamic-range
			  media query lets you know if the device
			  is capable of HD colors. And the @supports
			  query checks to see if the browser understands the
			  color syntax before you use it. There's so much
			  more here to study. Watch out for web.dev
			  blog posts about it. Coming to a browser near
			  you in 2022, color-mix-- use CSS to mix colors on
			  the fly in the color space of your choice. To use it, call color-mix
			  and give it two colors, and get an equal mix of each in
			  LCH, the default color space. Or pass a percentage
			  along with the color, which specifies how dominant
			  the color is in the mix. The second example there
			  uses a brand hex base and mixes it with black to
			  create some darker alt colors. And I know I've been stoked
			  on everything so far, but this one is magic, pure
			  and incomparable magic. Let the browser pick
			  accessible colors for you. Automate good contrast. So here's four surfaces all
			  shown with the same paragraph content inside. Each is using color
			  contrast function with a range of brand hues
			  to target the ratio of AAA. Notice how the lightest
			  and darkest backgrounds get the more subtle text
			  colors and the brighter surfaces get black
			  or white text colors. I got to bake in good
			  contrast into my CSS and give it up to the browser. We let the browser manage this. This is how it works. In this first selector,
			  I created a --bg variable and assign it to the background. For the text color, I call
			  the color-contrast function and pass it the bg prop. And without any options
			  passed, color-contrast will choose black
			  or white for me. But later, in some other
			  selector, change bg, and the text color automatically
			  picks up white or black based on the new
			  background color. Wowie, wow, wow, wow, right? And it gets better. So it's cool having black
			  or white picked for you. But those are usually
			  last-resort text colors for designers. So check this out. I call color-contrast again
			  with a background variable-- in this case, a brand blue. And then I pass three
			  different text colors from a design system, plus
			  a AA target contrast ratio. I used AA here, but you can
			  also pass a custom number. Now the browser will
			  pick the color that's closest to passing the score. So you can just throw a bunch
			  of text colors at this function, and it'll ensure you pass. And if none pass, black or
			  white will be chosen for you as a fallback. Rad, right? And there's even more
			  color stuff coming too. Check out relative color syntax,
			  another color game changer. It allows you to extract new
			  colors from existing colors. Let me show you. In my career, so much of
			  the color code in my CSS has pivoted on a brand
			  color, or maybe two. And in this code sample, I
			  put a simulated brand color into a --color prompt. In the variable
			  called abs-change, short for absolute change,
			  I create a new LCH color from the variable and
			  set its lightness to 75%, keeping the chroma and the hue. I call it an absolute
			  change because I threw away the lightness from
			  the hex and gave it a new one. The var rel-change is a
			  relative change example. I, again, start a new LCH
			  color, and I keep the lightness, but I decrease
			  the chroma by 20%, keeping the blue hue
			  and the lightness. It's a relative change
			  because I adjusted it relative to the
			  source color value. I think of this
			  relative color syntax like destructuring
			  in JavaScript. You destructure the color
			  channels out of the color directly into a new
			  color, with an opportunity to manipulate each
			  channel along the way. It's so rad. It gives me the power to create
			  perceptually linear palettes with very, very little code. And here's what
			  those palettes look like that I made with
			  the relative color syntax in the LCH color space. I wrote the relative
			  color logic one time, and it takes a base color
			  and generates a palette. Then I use it for
			  all 15 palettes here. Give me a brand color,
			  and I'll give you a perceptually
			  linear palette back. And notice how smooth they
			  are too-- no hot spots thanks to LCH. That perceptually linear
			  color space is super handy. So be stoked to see CSS
			  producing these incredible colors and smooth palettes
			  in the web in 2022, y'all. But 10 new spaces mean
			  10 new gradient variants to choose from. Let's take a look. On the left are gradients simply
			  going from black to white. And on the right are gradients
			  going from blue to black. Today, you get the top gradient,
			- the SRGB interpolation result, which is generally
			  fine and consistent. In 2022, you'll get to pick
			  from any of the others below it. And you see what I mean. There's 10 new
			  gradient variants. The color space is
			  super important. The variance in just black
			  to white is intriguing. But the blue to black
			  gradients going purple or pink in the middle, what's
			  going on there? Let's see a couple
			  more examples. On the left is red to white. And some turn a bit orange. One goes pink. And some go through that
			  dead zone in the middle. On the right is blue to white. Most go purple in the
			  middle, but okLAB and LCH stay nicely within hue. Interesting, right? So I expect designers to
			  start specifying which color space they want their gradients
			  in after they get these tools. And here's the syntax
			  to linear-gradient that allows you
			  to do this, allows you to access the color space. linear-gradient,
			  you call function, say direction, to right, and
			  the space, in HSL or LCH, and then your set of colors. It's a pretty straightforward
			  change with really big results. Last in our color set
			  here is colrv1 fonts. They're are new smaller
			  color font format with embedded vectors that
			  allow gradient and blend mode customizations. It's an evolution
			  of the OTSVG fonts, but they're smaller
			  and with more options. It's great for icon
			  fonts, awesome headlines, and tons more. So before colrv1
			  fonts, we had these-- OTSVG fonts. Colorful, editable, and
			  really playful, but the styles are fixed. After colrv1 fonts,
			  like [? Plicato ?] here, customize the font with
			  @font-palette values, these let you define parameters
			  to pass into the font, very similar to variable
			  font parameter passing. You can tailor the color
			  font to meet your needs. And this could be a huge
			  win for icon fonts and more. To use them, import color
			  fonts, like any other font, with an @font-face declaration,
			  or grab them from Google Fonts with an ad import, which
			  will include those goodies. Next, create an
			  @font-palette-values block with a name. Colorized is used here. Then specify which
			  font you're targeting and pass some overrides. Later, assign the font
			  family with the color font and specify the
			  custom font palette. And that's it. Next up is inert. This allows
			  developers to specify which part of the document
			  should be inactive. Think of it like freezing
			  portions of the document. You can use it for keeping focus
			  into a certain part of the page by making other parts
			  of the page inactive. So originally started
			  by Alice Boxhall, now Igalia is carrying it
			  across the finish line in 2022. The alert JavaScript
			  function is a good example. Once that pops up, the rest
			  of the page isn't interactive. Keyboard and mouse
			  users are being guided into the area where
			  their action is required. To achieve this, let's
			  look at some HTML. Here, a modal is shown,
			  and the main element is given the inert attribute. Now mouse and keyboard
			  users have proper focus into the modal because the
			  main element is frozen, no JS or tab index
			  attribute traps required. This is a really cool
			  accessibility win. And expect a post
			  from it on web.dev. Another goal of Interop 2022 is
			  enjoy a bunch of new viewport unit variants so that
			  you can really hone in that full viewport feel. New units allow you to
			  specify smaller viewport size, as if the mobile
			  tab bar is showing, the larger viewport size,
			  as if the mobile tab bar is hidden, or
			  dynamically be both, depending on the presence
			  of that mobile tab bar. You have 20 new units to fit
			  this viewport with physical or logical values. Here's all the new physical
			  and logical viewport units. We have 100vh, 100
			  dynamic viewport height, 100 small viewport height,
			  100 large viewport height. And then there's the logical
			  direction block versions for internationally adapting
			  fullscreen layouts, then the complementary
			  width versions and the logical inline versions. But you can't forget the min
			  and max viewport units, too, each with small, large,
			  and dynamic versions, representing either the
			  smaller of the viewport height or width or the larger. Hopefully, these unblock lots
			- of folks making fullscreen app experiences. Ah, colon has selector-- this is
			  easiest described as the parent selector, but that
			  sells it short. Think of it more
			  like, I'm no longer forced to have my target element
			  at the end of a selector. I can change the subject
			  of the selector if I want. This one is being implemented
			  by Igalia, recently stable in Safari, and an
			  Interop goal in 2022. Here's a few examples. The first selects
			  the parent class if it has a child in its tree. This can be amazing
			  for a CMS or layout to know what kind of blocks
			  it needs to make space for. The second example
			  selects a section element if any of its children
			  have focus-visible. I like this example
			  because it shows how this selector will affect
			  interactivity and UI feedback. But let's look at a
			  couple more examples. The first selects anchor
			  elements wrapping images. And the second finds images
			  that are inside figures with figcaptions. So see how it's not
			  just a parent selector? This last example selects
			  images if its parent has caption elements. Right? It's amazing. So expect has to be
			  a huge game-changer. Combining it with pseudo
			  selectors and n-th match notation selectors, it's going
			  to unlock some very powerful state and style. Quite a lucky time to
			  be a web developer. Be sure to check
			  out my blog post on this talk where
			  I go into even more detail about these
			  topics and more items. Find me on Twitter,
			  web.dev, and YouTube, sharing gems and tips
			  about frontend UI and CSS. I'll see you later, y'all. Hope you're stoked now too. [MUSIC PLAYING]
	- [CSS Selectors: A Visual Guide](https://fffuel.co/css-selectors/)
		- https://news.ycombinator.com/item?id=37132754
		- ((663a58ed-ba1d-4b09-9eec-54d86a627bd6))
- Related:
	- ((634ae294-d1f4-4480-8025-ee9f80daa935))
	- ((63baa37f-f211-4019-88bc-7402eb5f15b8))
	- ((6345af5c-d51b-4caf-a098-b2dec8b30357)) e.g. ((634710b7-9f3a-4533-bb0a-fdc1635bd8c5))