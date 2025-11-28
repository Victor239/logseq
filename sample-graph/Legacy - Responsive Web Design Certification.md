- (Legacy) [Responsive Web Design Certification](https://www.freecodecamp.org/learn/responsive-web-design) (300 hours) (HTML + CSS)
  id:: 62b5cc20-5561-4d6b-aee4-727626c9fb06
  collapsed:: true
	- #card #A006 Flashcard template
	  card-last-interval:: 4
	  card-repeats:: 2
	  card-ease-factor:: 2.46
	  card-next-schedule:: 2022-08-17T11:56:37.076Z
	  card-last-reviewed:: 2022-08-13T11:56:37.076Z
	  card-last-score:: 3
		- Answer
	- _Courses_
		- Basic HTML and HTML5
		  id:: 62d4474f-c829-4d54-9066-1d511a3b718e
		  collapsed:: true
			- _Elements_
				- `<h>` heading element
				  collapsed:: true
					- `<h1>` is generally used for main headings, and `<h2>` for subheadings
					- Example
					  collapsed:: true
						- ```html
						  <h1>Hello World</h1>
						  <h2>CatPhotoApp</h2>
						  ```
					- #card #A006 Create a heading and subheading below it in HTML, with only the aforementioned elements
					  collapsed:: true
						- ```html
						  <h1>Hello World</h1>
						  <h2>CatPhotoApp</h2>
						  ```
				- `<p>`paragraph element
				  collapsed:: true
					- Used for paragraph text
					- Example
					  collapsed:: true
						- ```html
						  <p>I'm a p tag!</p>
						  ```
					- #card #A006 Insert sentence with a paragraph element
					  collapsed:: true
						- ```html
						  <p>I'm a p tag!</p>
						  ```
				- `<!--` `-->` HTML code comments
				  collapsed:: true
				  id:: 6302598d-9b1d-4cc3-92e0-855feedb6b71
					- Example
					  collapsed:: true
						- ```html
						  <!-- This is a comment -->
						  
						  <!--
						  <h1>Hello World</h1>
						  -->
						  ```
					- #card #A006 Insert a single line HTML code comment
					  collapsed:: true
						- ```html
						  <!--- Hello -->
						  ```
					- #card #A006 Insert a multi-line HTML code comment
					  collapsed:: true
						- ```html
						  <!--- 
						  Hello 
						  -->
						  ```
					- Related: ((6302598d-7891-4955-a727-b51abdc2fed1))
				- _HTML5 elements_
				  collapsed:: true
					- HTML5 introduces more descriptive HTML tags. These include  `main` ,  `header` ,  `footer` ,  `nav` ,  `video` ,  `article` ,  `section`  and others.
					- These tags give a descriptive structure to your HTML, make your HTML easier to read, and help with Search Engine Optimization (SEO) and accessibility. The  `main`  HTML5 tag helps search engines and other developers find the main content of your page.
					- Example usage, a  `main`  element with two child elements nested inside it:
					  collapsed:: true
						- ```html
						  <main> 
						  <h1>Hello World</h1>
						  <p>Hello Paragraph</p>
						  </main>
						  ```
					- #card #A006 HTML5 introduces more descriptive HTML tags like `main` ,  `header` ,  `footer` ,  `nav` ,  `video` ,  `article` ,  `section`  and others. Name 2 benefits to using these
					  collapsed:: true
						- Makes HTML easier to read
						- Helps with SEO
						- Helps with accessibility
						- Helps other software more easily process webpages
					- #card #A006 Write out an example using the `<main>` element along with a paragraph
					  collapsed:: true
						- ```html
						  <main> 
						  <p>Hello Paragraph</p>
						  </main>
						  ```
				- `<img>` Image element
				  collapsed:: true
				  id:: 632092fc-bec5-4603-965c-be0f6a847289
					- You can add images to your website by using the  `img`  element, and point to a specific image's URL using the  `src`  attribute.
					- Example - basic1
						- ```html
						  <img src="https://www.freecatphotoapp.com/your-image.jpg">
						  ```
					- Note that  `img`  elements are self-closing.
					- All  `img`  elements **must** have an  `alt`  attribute. The text inside an  `alt`  attribute is used for screen readers to improve accessibility and is displayed if the image fails to load.
					- **Note:** If the image is purely decorative, using an empty  `alt`  attribute is a best practice.
					- Example - basic2 with `alt` attribute
					  collapsed:: true
						- ```html
						  <img src="https://www.freecatphotoapp.com/your-image.jpg" alt="freeCodeCamp logo">
						  ```
					- #card #A006 Create a HTML image element which points to a made-up URL
					  collapsed:: true
						- ```html
						  <img src="https://www.freecatphotoapp.com/your-image.jpg" alt="freeCodeCamp logo">
						  ```
				- `a` Anchor element
				  collapsed:: true
					- You can use these in several ways:
					  collapsed:: true
						- 1) to link to content outside of your web page.
						  collapsed:: true
							- `a`  elements need a destination see the ((62b73dad-0ea2-482f-a2a5-aa92b6a30d3c))
							- They also need **anchor text**, which goes between the `<a>` tags
							- Example
							  collapsed:: true
								- collapsed:: true
								  ```html
								  <a href="https://www.freecodecamp.org">this links to freecodecamp.org</a>
								  ```
									- Displays as:
									  collapsed:: true
										- <a href="https://www.freecodecamp.org">this links to freecodecamp.org</a>
							- #card #A006 Create a hyperlink to an external webpage
							  collapsed:: true
								- ```html
								  <a href="https://www.freecodecamp.org">this links to freecodecamp.org</a>
								  ```
							- #card #A006 Which part of this is the anchor text?
							  collapsed:: true
							  
							  ```html
							  <a href="https://www.freecodecamp.org">this links to freecodecamp.org</a>
							  ```
								- `this links to freecodecamp.org`
						- 2) You can also use these to create internal links to jump to different sections within a webpage.
						  collapsed:: true
							- To create an internal link, you assign a link's  `href`  attribute to a hash symbol  `#`  plus the value of the  `id`  attribute for the element that you want to internally link to, usually further down the page.
							- You then need to add the same  `id`  attribute to the element you are linking to. An  `id`  is an attribute that uniquely describes an element.
							- Example
							  collapsed:: true
								- ```html
								  <a href="#contacts-header">Contacts</a>
								  ...
								  <h2 id="contacts-header">Contacts</h2>
								  ```
							- #card #A006 Create a HTML hyperlink to this heading:
							  collapsed:: true
							  ```html
							  <h2 id="contacts-header">Contacts</h2>
							  ```
								- ```html
								  <a href="#contacts-header">Contacts</a>
								  ```
						- Advanced
						  collapsed:: true
							- Nested anchor elements
							  collapsed:: true
								- You can nest links within other text elements such as `<p>`
								  collapsed:: true
									- ```html
									  <p>
									  Here's a <a target="_blank" href="https://www.freecodecamp.org"> link to www.freecodecamp.org</a> for you to follow.
									  </p>
									  ```
								- #card #A006 Nest the following in a paragraph element
								  collapsed:: true
								  
								  ```html
								  Here's a <a target="_blank" href="https://www.freecodecamp.org"> link to www.freecodecamp.org</a> for you to follow.
								  ```
									- ```html
									  <p>
									  Here's a <a target="_blank" href="https://www.freecodecamp.org"> link to www.freecodecamp.org</a> for you to follow.
									  </p>
									  ```
							- Dead links by using `href="#"`
							  id:: 62c05873-c506-436a-a70a-792ecade7081
							  collapsed:: true
								- Sometimes you want to add  `a`  elements to your website before you know where they will link.
								- This is also handy when you're changing the behavior of a link using  `JavaScript` , which we'll learn about later.
								- Example
								  collapsed:: true
									- ```html
									  <a href="#" target="_blank">cat photos</a>
									  ```
								- #card #A006 Create a dead link (a link which doesn't go anywhere currently) with it's best template
								  collapsed:: true
									- ```html
									  <a href="#" target="_blank">cat photos</a>
									  ```
							- Hyperlinked images
							  collapsed:: true
								- Nest image within the `<a>` element
								- Example
								  collapsed:: true
									- ```html
									  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="Three kittens running towards the camera."></a>
									  ```
								- Make sure to also ((62c05873-c506-436a-a70a-792ecade7081))
								- #card #A006 Create a hyperlinked image (difficulty 2/2)
								  collapsed:: true
									- ```html
									  <a href="#"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="Three kittens running towards the camera."></a>
									  ```
								- #card #A006 Create a hyperlinked image, using the following image (difficulty 1/2)
								  ```html
								  <img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="Three kittens running towards the camera.">
								  ```
					- Attributes
					  collapsed:: true
						- `target` attribute
						  collapsed:: true
							- It specifies where to open the link. The value  `_blank`  specifies to open the link in a new tab.
							- Example
							  id:: 62b73d76-f4d6-4770-9a9c-6d7461a9d19e
							  collapsed:: true
								- ```html
								  <a href="https://www.freecodecamp.org" target="_blank"> ... </a>
								  ```
							- #card #A006 This is the typical attributes used for an `<a>` element, what does each do?
							  collapsed:: true
							  
							  ```html
							  <a href="https://www.freecodecamp.org" target="_blank"> ... </a>
							  ```
								- `href` specifies what internal position or external link should be opened, whereas `target` specifies where to open the link e.g. `_blank` is in a new tab
							- #card #A006 What does `target="_blank"` do here?
							  collapsed:: true
							  
							  ```html
							  <a href="https://www.freecodecamp.org" target="_blank"> ... </a>
							  ```
								- It opens the link in a new tab
							- #card #A006 What does the attribute `target` do in a `<a>` element?
							  collapsed:: true
								- It specifies where to open the link, e.g. the below opens the link in a new tab
								  
								  ```html
								  <a href="https://www.freecodecamp.org" target="_blank"> ... </a>
								  ```
						- `href` attribute
						  id:: 62b73dad-0ea2-482f-a2a5-aa92b6a30d3c
						  collapsed:: true
							- Contains the URL address of the link or internal address {{embed ((62b73d76-f4d6-4770-9a9c-6d7461a9d19e))}}
							- {{embed ((62c05873-c506-436a-a70a-792ecade7081))}}
				- _List elements_
					- `<ul>` bulleted unordered list
					  collapsed:: true
						- Unordered lists start and end with `<ul>`
						- Start and end each item within the list with`<li>`
						- Example
						  collapsed:: true
							- ```html 
							  <ul>
							    <li>milk</li>
							    <li>cheese</li>
							  </ul>
							  ```
						- #card #A006 Create an unordered list with two items in HTML
						  collapsed:: true
							- ```html 
							  <ul>
							    <li>milk</li>
							    <li>cheese</li>
							  </ul>
							  ```
					- `<ol>` ordered list
					  collapsed:: true
						- Ordered lists start and end with `<ol>`
						- Start and end each item within the list with`<li>`
						- Example
						  collapsed:: true
							- ```html 
							  <ol>
							    <li>Garfield</li>
							    <li>Sylvester</li>
							  </ol>
							  ```
						- #card #A006 Create an ordered list in HTML with two items
						  collapsed:: true
							- ```html 
							  <ol>
							    <li>Garfield</li>
							    <li>Sylvester</li>
							  </ol>
							  ```
				- `<input>` element
				  id:: 62d4474f-e569-4707-a416-4764f25d958a
				  collapsed:: true
					- Convenient way to get input from user
					- Self-closing (no need for a closing tag)
					- Example
						- ```html
						  <input type="text">
						  ```
					- Attributes
						- `type` attribute
						  id:: 62d4474f-08f5-402b-863f-b04bcb57c15f
						  collapsed:: true
							- Possible values
								- `text` = text field
								- `radio` = radio buttons
								  id:: 62c43088-06f1-4f35-8287-b2014daa8d39
								  collapsed:: true
									- You can use radio buttons for questions where you want the user to only give you one answer out of multiple options.
									- Best practice to 
									  id:: 62d6c2a3-be5b-4ffe-9e6b-ef96713e4a17
										- set the ((62d6c178-8f23-40f0-9a4f-f258aafb0270)), and match it to the ((62d6c148-9f62-43e8-adec-e6bc378615d2)) of the ((62c430b2-b9df-4c9e-b8ae-18936ee0679b)). See ((62d6c178-8f23-40f0-9a4f-f258aafb0270)) for more info
										  id:: 630287fb-44ff-4a09-908b-a54713bd6c24
											- ```html
											  <label for='test1' > // lookup 'name' attribute
											  	<input type='radio' id='test1' />
											  </label>
											  ```
										- Usually paired with ((62c430b2-b9df-4c9e-b8ae-18936ee0679b))
											- By wrapping an  `input`  element inside of a  `label`  element it will automatically associate the radio button input with the label element surrounding it.
										- All related radio buttons should have the same ((62d6c0d5-47ba-4e9d-ba28-2c2d8f30b3f7))  to create a radio button group
											- By creating a radio group, because ((6302598d-0262-49a6-81b8-99e9b820ab91))
									- Examples
										- collapsed:: true
										  ```html
										  <label for="indoor"> 
										    <input id="indoor" type="radio" name="indoor-outdoor">Indoor 
										  </label>
										  ```
											- Best practice because it includes ((630287fb-44ff-4a09-908b-a54713bd6c24))
											- Alternative one-line formatting:
											  collapsed:: true
												- ```html
												  <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor">Indoor</label>
												  ```
											- Extended example with two radio button choices:
											  collapsed:: true
												- ```html
												  <label for="indoor">
												  <input id="indoor" type="radio" name="radio">Indoor
												  </label>
												  <p>
												  <label for="outdoor">
												  <input id="outdoor" type="radio" name="radio">Outdoor
												  </label>
												  ```
										- collapsed:: true
										  ```html
										  <input id="indoor" type="radio" name="indoor-outdoor">
										  <label for="indoor">Indoor</label>
										  ```
											- Decent version since it has ((62d6c2a3-be5b-4ffe-9e6b-ef96713e4a17)), however nesting the `<input>` inside the `<label>` is neater and easier to read
									- #card #A006 Given the following input type, add the best practices
									  id:: 630282e5-5538-449c-a5e9-d49d71e48881
									  
									  ```html
									  <input type="radio">
									  ```
										- ```html
										  <label for="indoor"> 
										    <input id="indoor" type="radio" name="indoor-outdoor">Indoor 
										  </label>
										  ```
										  
										  
										  ((62d6c2a3-be5b-4ffe-9e6b-ef96713e4a17))
										  {{embed ((62d6c2a3-be5b-4ffe-9e6b-ef96713e4a17))}}
								- `checkbox` = checkboxes
								  id:: 62d6c6c2-5b6a-4475-8521-060a0ed14d85
								  collapsed:: true
									- Used when a form may have more than one answer (unlike ((62c43088-06f1-4f35-8287-b2014daa8d39)))
									- Same as ((62c43088-06f1-4f35-8287-b2014daa8d39)), best practice is to:
									  collapsed:: true
										- Nest each ((62d4474f-e569-4707-a416-4764f25d958a)) in it's own ((62c430b2-b9df-4c9e-b8ae-18936ee0679b)), which will automatically associate the ((62d4474f-e569-4707-a416-4764f25d958a)) with the ((62c430b2-b9df-4c9e-b8ae-18936ee0679b)) surrounding it.
										- Each ((62d4474f-e569-4707-a416-4764f25d958a)) should have the same ((62d6c0d5-47ba-4e9d-ba28-2c2d8f30b3f7))
										- Explicitly define the relationship between each ((62d4474f-e569-4707-a416-4764f25d958a)) and it's corresponding ((62c430b2-b9df-4c9e-b8ae-18936ee0679b)) by setting the ((62d6c178-8f23-40f0-9a4f-f258aafb0270)) of the ((62d4474f-e569-4707-a416-4764f25d958a)), and match it to the ((62d6c148-9f62-43e8-adec-e6bc378615d2)) of the ((62c430b2-b9df-4c9e-b8ae-18936ee0679b)). See ((62d6c178-8f23-40f0-9a4f-f258aafb0270)) for more info
									- Example
									  collapsed:: true
										- ```html
										  <label for="loving"><input id="loving" type="checkbox" name="personality">Loving</label>
										  <label for="stern"><input id="stern" type="checkbox" name="personality">Stern</label>
										  ```
								- `number` = numbers
								- #card #A006 Give three examples of input element types
								  collapsed:: true
									- ```html
									  <input type="text">
									  <input type="radio">
									  <input type="checkbox">
									  ```
						- `placeholder` attribute
						  collapsed:: true
							- Placeholder text is what is displayed in your  `input`  element before your user has inputted anything.
							- Example
							  collapsed:: true
								- ```html
								  <input type="text" placeholder="this is placeholder text">
								  ```
						- `required` attribute
						  collapsed:: true
							- You can require specific form fields so that your user will not be able to submit your form until he or she has filled them out.
							- Example
							  collapsed:: true
								- ```html
								  <input type="text" required>
								  ```
						- `name` attribute
						  id:: 62d6c0d5-47ba-4e9d-ba28-2c2d8f30b3f7
						  collapsed:: true
							- Paired with ((62d4474f-08f5-402b-863f-b04bcb57c15f)) = ((62c43088-06f1-4f35-8287-b2014daa8d39)) it ensures that only one radio button can be selected by the user
							  id:: 6302598d-0262-49a6-81b8-99e9b820ab91
							- #card #A006 What does the name attribute in input elements do?
								- When using `type="radio"` as well, it ensures that only one radio button can be selected if all input elements are using the same `name`
						- `value` attribute
						  id:: 62d6cef8-76ab-41c9-a810-50ad3683a6dc
						  collapsed:: true
							- When a form gets submitted, ((62c43088-06f1-4f35-8287-b2014daa8d39)) and ((62d6c6c2-5b6a-4475-8521-060a0ed14d85)) report the data to send to the server as what is in the ((62d6c0d5-47ba-4e9d-ba28-2c2d8f30b3f7)) + ((62d6cef8-76ab-41c9-a810-50ad3683a6dc))
							- The default ((62d6cef8-76ab-41c9-a810-50ad3683a6dc)) is `on` if not specifically changed. This is obviously not useful if there is more than one choice available.
							- Example
							   collapsed:: true
							  collapsed:: true
								- collapsed:: true
								  ```html
								  <label for="indoor">
								    <input id="indoor" value="indoor" type="radio" name="indoor-outdoor">Indoor
								  </label>
								  <label for="outdoor">
								    <input id="outdoor" value="outdoor" type="radio" name="indoor-outdoor">Outdoor
								  </label>
								  ```
									- Submitting a form with the `indoor` option selected will submit to the server `indoor-outdoor=indoor` AKA `name`+`value`
								- #card #A006 What is the default for the `value` attribute in input elements?
								  collapsed:: true
									- `on`
						- `checked` attribute
						  collapsed:: true
							- This can be used to set a ((62c43088-06f1-4f35-8287-b2014daa8d39)) or ((62d6c6c2-5b6a-4475-8521-060a0ed14d85)) to be checked by default
							- Example
							  collapsed:: true
								- ```html
								  <input type="radio" name="test-name" checked>
								  ```
						- Flashcards
						  collapsed:: true
							- #card #A006 Give an example input element
							  collapsed:: true
							  card-last-interval:: -1
							  card-repeats:: 1
							  card-ease-factor:: 2.5
							  card-next-schedule:: 2022-09-15T23:00:00.000Z
							  card-last-reviewed:: 2022-09-15T11:49:35.765Z
							  card-last-score:: 1
								- `<input type="text">`
							- #card #A006 Create an example input element which uses the following attributes: type, placeholder, required, name, value, checked
							  collapsed:: true
								- ```html
								  	  <input type="text" placeholder="this is placeholder text" required name="test" value="yes" checked>
								  	  ```
							- #card #A006 Name at least 3 attributes for input elements
							  collapsed:: true
								- type, placeholder, required, name, value, checked
							- #card #A006 When input elements are submitted in a form, which attribute data is also sent?
							  collapsed:: true
								- name + attribute
				- `<form>` element
				  collapsed:: true
					- Allows building web forms that actually submit data to a server just through pure HTML, as long as there is an ((62c42ec3-1f47-4aa5-acc7-7ceecaad1b22))
					- Example
						- ```html
						  <form action="https://url-where-you-want-to-submit-form-data.com">
						    <input>
						  </form>
						  ```
					- Attributes
						- `action` attribute
						  id:: 62c42ec3-1f47-4aa5-acc7-7ceecaad1b22
						- #card #A006 Create an example form element to go with the example input element below, including best practice
						  
						  ```html
						  <input>
						  ```
							- ```html
							  <form action="https://url-where-you-want-to-submit-form-data.com">
							    <input>
							  </form>
							  ```
				- `<button>` element
				  collapsed:: true
					- Example
						- ```html
						  <button type="submit">this button submits the form</button>
						  ```
					- Attributes
						- `type` attribute
					- #card #A006 Create a HTML element that is a submission button with "Submit" as the label
						- ```html
						  <button type="submit">this button submits the form</button>
						  ```
				- `<label>` element
				  id:: 62c430b2-b9df-4c9e-b8ae-18936ee0679b
				  collapsed:: true
					- Usually paired with ((62d4474f-e569-4707-a416-4764f25d958a)) with ((62d4474f-08f5-402b-863f-b04bcb57c15f)) for ((62c43088-06f1-4f35-8287-b2014daa8d39))
					- Example
					  id:: 632092fb-93d9-4bf2-a910-4b98c9afaac6
						- ```html
						  <label for="test"> 
						    <input id="test" type="radio" name="indoor-outdoor">Indoor 
						  </label>
						  ```
					- Attributes
						- `for` attribute
						  id:: 62d6c148-9f62-43e8-adec-e6bc378615d2
							- Best practice to match this to the ((62d6c178-8f23-40f0-9a4f-f258aafb0270)) of the ((62d4474f-e569-4707-a416-4764f25d958a))
							- Example
								- ```html
								  <label for="indoor">
								    <input id="indoor" type="radio" name="indoor-outdoor">Indoor
								  </label>
								  ```
					- #card #A006 `<label>` elements are commonly used with `<input>` elements that have `type="radio"`. Give an example of this, using best practices
					  collapsed:: true
						- ```html
						  <label for="indoor"> 
						  <input id="indoor" type="radio" name="indoor-outdoor">Indoor 
						  </label>
						  ```
						  
						  ((62d6c2a3-be5b-4ffe-9e6b-ef96713e4a17))
						  {{embed ((62d6c2a3-be5b-4ffe-9e6b-ef96713e4a17))}}
				- `<div>` division element
				  collapsed:: true
					- It's a general purpose container for other elements and probably the most commonly used element
					- It's not self-closing, so should have a closing tag
					- #card #A006 Create an example `<div>` element with some text
						- ```html
						  <div>text</div>
						  ```
			- _HTML Global Attributes_
				- `id` attribute
				  id:: 62d6c178-8f23-40f0-9a4f-f258aafb0270
				  collapsed:: true
					- Example
						- ```html
						  <h2 id="cat-photo-app">
						  ```
					- Best practices
						- Make it unique per element
						- If using ((62d4474f-e569-4707-a416-4764f25d958a)) with ((62c43088-06f1-4f35-8287-b2014daa8d39)) or ((62d6c6c2-5b6a-4475-8521-060a0ed14d85)), then it's best practice to match it's `id` attribute to the ((62d6c148-9f62-43e8-adec-e6bc378615d2)) of the ((62c430b2-b9df-4c9e-b8ae-18936ee0679b)) which surrounds the ((62d4474f-e569-4707-a416-4764f25d958a))
						  id:: 6302598d-8be0-4073-be20-d6a08adf47ad
					- #card #A006 Show two HTML examples using the `id` attribute
						- ```html
						  <h2 id="cat-photo-app">
						  <h2 id="cat-photo-app2">
						  ```
						  
						  i.e. it's unique per element
					- #card #A006 `id` attribute best practice is to match it to what?
						- ((6302598d-8be0-4073-be20-d6a08adf47ad))
				- ((62d6eecc-0c95-4d73-9c99-908e9d0cc195))
				  collapsed:: true
					- #card #A006 Show two HTML examples using the `class` attribute
					  collapsed:: true
						- ```html
						  <h2 class="cats">
						  <h2 class="cats">
						  ```
						  
						  i.e. it's non-unique
					- #card #A006 Give an example using two `class` attributes
					  collapsed:: true
						- ```css
						  <img class="smaller-image thick-green-border">
						  ```
				- [Others](https://www.w3schools.com/tags/ref_standardattributes.asp) (not encountered on this course)
				  id:: 63037876-af3b-4cd4-bcb6-ff6b689071b1
				  collapsed:: true
					- `accesskey` attribute
					- `contenteditable` attribute
					- `data-*` attribute
					- `dir` attribute
					- `draggable` attribute
					- `hidden` attribute
					- `lang` attribute
					- `spellcheck` attribute
					- `style` attribute
					- `tabindex` attribute
					- `title` attribute
					- `translate` attribute
				- #card #A006 Name two or more HTML global attributes
				  collapsed:: true
					- id, class, [others](((63037876-af3b-4cd4-bcb6-ff6b689071b1)))
			- Declare the doctype of a HTML document
			  collapsed:: true
				- Example
					- ```html
					  <!DOCTYPE html>
					  <html>
					  
					  </html>
					  ```
			- Define the Head and Body of an HTML Document
			  collapsed:: true
				- Metadata elements, such as  `link` ,  `meta` ,  `title` , and  `style` , typically go inside the  `head`  element.
				- Example
					- ```html
					  <!DOCTYPE html>
					  <html>
					    <head>
					      <meta charset="utf-8">
					      <title>Example title</title>
					    </head>
					    <body>
					      <div>
					      </div>
					    </body>
					  </html>
					  ```
				- #card #A006 Give an example HTML doc template, including the 4 most important elements
					- ```html
					  <!DOCTYPE html>
					  <html>
					    <head>
					    </head>
					    <body>
					    </body>
					  </html>
					  ```
			- ((62f67eaf-d7f3-4d8f-8f67-3d6e2753aaff))
			  id:: 6302598d-f144-47ee-88a0-a1a73184b1e9
			- Related: ((62d44751-a4e4-4230-8a2f-3bdb28b7c1f1))
		- Basic CSS
		  id:: 62d4474f-9b9d-4ba9-abdb-dd54a279991c
		  collapsed:: true
			- Introduction
			  collapsed:: true
				- Allows you to control:
				  collapsed:: true
					- color
					- fonts
					- positioning
					- spacing
					- sizing
					- decorations
					- transitions
				- 3 main ways to apply CSS styling
				  id:: 62d7c01f-4565-4e14-aaf3-4abe0957e79a
					- Apply inline styles directly to HTML elements with the `style` attribute
					  id:: 62d7c01f-ca4c-423e-a889-e645cc801b03
						- Note that it is a good practice to end inline  `style`  declarations with a  `;`
							- Example
								- ```html
								  <h2 style="color: blue;">CatPhotoApp</h2>
								  ```
						- #card #A006 Give an example of CSS using inline styling
							- ```html
							  <h2 style="color: blue;">CatPhotoApp</h2>
							  ```
					- Place CSS rules within `style` element in an HTML document
						- ((62d44751-2e76-4f8b-be80-13efd0c96abc))
						  collapsed:: true
							- {{embed ((62d44751-2e76-4f8b-be80-13efd0c96abc))}}
						- #card #A006 Give an example of CSS using `style` element
						  collapsed:: true
							- Example
							  ```html
							  <head>
							    <title>Quiz - Hello, world!</title>
							    <style>
							      .red-text {
							        color: red;
							        font-family: monospace;
							      }
							  - p {
							        font-size: 16px;
							      }
							    </style>
							  </head>
							  ```
					- Write CSS rules in an external style sheet, then reference that file in the HTML document
					  id:: 6302598d-87a1-4306-8ddf-9c7cf8dbee95
						- Pros/Cons
						  collapsed:: true
							- Pros
							  collapsed:: true
								- Nicer organisation if there are lots of styles that makes the HTML file too big
								- Allows sharing a single CSS file across multiple pages
								- Even though the first two options have their use cases, most developers prefer external style sheets because they keep the styles separate from the HTML elements. This improves the readability and reusability of your code.
						- Example
						  collapsed:: true
							- ```html
							  <head>
							    <link href="/my-styles.css" rel="stylesheet">
							  </head>
							  ```
							- id:: 63045a99-467a-4956-a722-e5b23bf6a378
							  ```html
							  <html>
							    <head>
							      <link href="example.css" rel="stylesheet" type="text/css" media=”screen” />
							    </head>
							  <html>
							  ```
						- _Attributes_
						  id:: 6302598d-6f83-4ef4-b084-36dce59096ed
						  collapsed:: true
							- `href` – specifies the location of the CSS file you want to link to the HTML. If both HTML and CSS files are in the same folder, enter only the file name. Otherwise, include the folder name in which you store the CSS file.
							  collapsed:: true
								- This can also be used to link to external webpages if you're trying to ((62d7010b-fe3c-43f1-9d68-00d6ab86626e))
								  collapsed:: true
									- {{embed ((63045a99-c249-4bc9-bc79-b598216ee09e))}}
							- `rel` – defines the relationship between the linked document and the current one. Use the rel attribute only when the href attribute is present.
							- `type` – determines the content of the linked file or document between the <style> and </style> tags. It has a text or css as the default value.
							- `media` – describes the type of media the CSS styles are optimized for. In this example, we put screen as the attribute value to imply its use for computer screens. To apply the CSS rules to printed pages, set the value to print.
						- #card #A006 Give an example of CSS external style sheet being referenced
						  collapsed:: true
							- ```html
							  <html>
							    <head>
							      <link rel="stylesheet" type="text/css" href="example.css" media=”screen” />
							    </head>
							  <html>
							  ```
						- #card #A006 Below is a typical CSS external style sheet being referenced, what does each attribute do?
						  collapsed:: true
						  
						  ```html
						  <html>
						    <head>
						      <link rel="stylesheet" type="text/css" href="example.css" media=”screen” />
						    </head>
						  <html>
						  ```
							- ((6302598d-6f83-4ef4-b084-36dce59096ed))
							  
							  {{embed ((6302598d-6f83-4ef4-b084-36dce59096ed))}}
				- #card #A006 What are the 3 main ways to apply CSS styling?
				  collapsed:: true
					- 1) ((62d7c01f-ca4c-423e-a889-e645cc801b03)) e.g. `<h2 style="color: blue;">CatPhotoApp</h2>`
					  
					  1) ((62d44751-2e76-4f8b-be80-13efd0c96abc)) e.g. 
					  ```html
					  <head>
					    <style>
					      .red-text {
					        color: red;
					        font-family: monospace;
					      }
					    </style>
					  </head>
					  ```
					  
					  2) ((6302598d-87a1-4306-8ddf-9c7cf8dbee95))
					  
					  ```html
					  <head>
					     <link rel="stylesheet" type="text/css" href="example.css" media=”screen” />
					  </head>
					  ```
				- #card #A006 Give an example HTML element for using an external style sheet, plus the element(s) it would be embedded in
				  collapsed:: true
				  card-last-interval:: 4
				  card-repeats:: 1
				  card-ease-factor:: 2.6
				  card-next-schedule:: 2022-11-20T12:27:30.939Z
				  card-last-reviewed:: 2022-11-16T12:27:30.942Z
				  card-last-score:: 5
					- ```html
					  <html>
					    <head>
					      <link rel="stylesheet" type="text/css" href="example.css" media=”screen” />
					    </head>
					  <html>
					  ```
				- The idea behind CSS is that you can use a selector to target an HTML element in the DOM (Document Object Model) and then apply a variety of attributes to that element to change the way it is displayed on the page.
			- `/*` `*/` CSS comments
			  id:: 6302598d-7891-4955-a727-b51abdc2fed1
			  collapsed:: true
				- Example
					- ```css
					  color: #000000; /* hexadecimal number for black */
					  ```
				- #card #A006 Comment out this CSS code 
				  
				  ```css
				  color: #000000;
				  ```
					- ```css
					  /* color: #000000; */
					  ```
				- Related: ((6302598d-9b1d-4cc3-92e0-855feedb6b71))
			- _Style properties_
				- _Meta_
				  collapsed:: true
					- These all use ((35bbc920-4ed2-4fe5-ae32-c53baf26746e))
					- #card #A006 What case style does CSS use, and give an example 4 word phrase using that case style
						- ((35bbc920-4ed2-4fe5-ae32-c53baf26746e))
						  
						  e.g. this-is-kebab-case
						  font-family
				- `color` style property
				  collapsed:: true
				  id:: 62d7c01f-9de3-4527-80fe-2493e4a191a7
					- Example
						- ```css
						  color: blue;
						  color: #0000FF /* hex code for blue */
						  color: rgb(0, 0, 255) /* RGB value for blue */
						  ```
					- Ways to denote colour
						- Name
						- Hex code
						  collapsed:: true
							- Example
								- ```css
								  color: #000000; /* hexadecimal code for black */
								  ```
							- Example - abbreviated hex code
								- ```css
								  color: #000; /* abbreviated hexadecimal cod for black */
								  ```
						- `RGB` values
						  collapsed:: true
							- Example
								- ```css
								  rgb(0, 0, 0); /* hexadecimal code for white */
								  rgb(255, 255, 255); /* hexadecimal code for black */
								  ```
						- Colors are specified using predefined color names, or RGB, HEX, HSL, RGBA, HSLA values.
						- Related:
							- ((62d7c01f-9de3-4527-80fe-2493e4a191a7))
							- ((62d7c01f-7ee6-4f4f-985e-e1ea1410fbc8))
					- #card #A006 For the `color` CSS style property, give 3 examples using 3 different ways of defining colour (doesn't matter if the values aren't correct, correct formatting is what is being looked for)
						- ```css
						  color: blue;
						  color: #0000FF /* hex code for blue */
						  color: rgb(0, 0, 255) /* RGB value for blue */
						  ```
						  
						  Related:
						  ((62d7c01f-9de3-4527-80fe-2493e4a191a7))
				- `font-size` style property
				  collapsed:: true
					- Example
						- ```css
						  font-size: 30px; /* <length> values */
						  font-size: 0.8em; /* <length> values */
						  font-size: 80%; /* <percentage> values */
						  font-size: large; /* <absolute-size> values */
						  ```
					- ((63045a99-a305-4fa2-a171-762107505acd))
						- {{embed ((63045a99-a305-4fa2-a171-762107505acd))}}
					- #card #A006 Create 3 different examples using CSS `font-size` using different ways of defining it's value
					  
					  ```css
					  font-size: 
					  font-size: 
					  font-size: 
					  ```
						- ```css
						  font-size: 30px; /* <length> values */
						  font-size: 0.8em; /* <length> values */
						  font-size: 80%; /* <percentage> values */
						  font-size: large; /* <absolute-size> values */
						  ```
					- [Learning Resources]
						- https://developer.mozilla.org/en-US/docs/Web/CSS/font-size
				- `font-family` style property
				  id:: 62d7005b-cbc2-42db-9709-c65acec2267c
				  collapsed:: true
					- Example
					  collapsed:: true
						- ```css
						  font-family: sans-serif;
						  ```
					- Format for importing web fonts
					  id:: 62d70250-c816-49e1-852c-3882f1962e77
					  collapsed:: true
						- ```css
						  font-family: FAMILY_NAME, GENERIC_NAME;
						  ```
						- The GENERIC_NAME is optional, and is a fallback font in case the other specified font is not available. This is covered in the next challenge.
						- Family names are case-sensitive and need to be wrapped in quotes if there is a space in the name. For example, you need quotes to use the  `"Open Sans"`  font, but not to use the  `Lobster`  font.
						- Related: ((62d7010b-fe3c-43f1-9d68-00d6ab86626e))
						- Example
						  collapsed:: true
							- ```css
							  font-family: "Courier New", monospace;
							  ```
					- #card #A006 Create an example CSS snippet using `Courier New` as the primary font as `Monospace` as the fallback
					- ```css
					  	font-family: "Courier New", monospace;
					  ```
				- `width` style property
				  collapsed:: true
					- Example
					  collapsed:: true
						- ```css
						  width: 500px;
						  ```
				- `background-color` style property
				  collapsed:: true
				  id:: 62d7c01f-7ee6-4f4f-985e-e1ea1410fbc8
					- Example
					  collapsed:: true
						- ```css
						  background-color: green;
						  ```
					- Commonly used with `<div>`
					- #card #A006 Add a HTML element + CSS to make the background colour for this `black`
					  
					  ```html
					  <h2 style="color: white;">Random</h2>
					  ```
						- ```html
						  <div style="background-color: black;">
						    <h2 style="color: white;">Random</h2>
						  </div>
						  ```
				- _Surrounding space style properties_
				  collapsed:: true
					- _Padding style properties_
					  collapsed:: true
						- `padding` style property
						  collapsed:: true
							- Example
							  collapsed:: true
								- ```css
								  padding: 10px;
								  ```
							- Example - clockwise notation can be used instead of specifying each padding side individually:
							  id:: 62d7cf8c-beb1-4572-b767-fbe49c979a10
							  collapsed:: true
								- collapsed:: true
								  ```css
								  padding: 10px 20px 10px 20px;
								  ```
									- Can be used instead of:
									  collapsed:: true
										- ```css
										  padding-top: 10px;
										  padding-right: 20px;
										  padding-bottom: 10px;
										  padding-left: 20px;
										  ```
							- #card #A006 What does each of these respond to?
							  collapsed:: true
							  
							  ```css
							  padding: 10px 20px 10px 20px;
							  ```
								- ```css
								  padding-top: 10px;
								  padding-right: 20px;
								  padding-bottom: 10px;
								  padding-left: 20px;
								  ```
							- #card #A006 Give an example of CSS using clockwise notation and say what it all means
							  collapsed:: true
								- ```css
								  padding: 10px 20px 10px 20px;
								  ```
								  It means:
								  ```css
								  padding-top: 10px;
								  padding-right: 20px;
								  padding-bottom: 10px;
								  padding-left: 20px;
								  ```
								  
								  Or `margin`
						- _Directional padding style properties_
						  collapsed:: true
							- `padding-top` style property
							  collapsed:: true
								- Example
								  collapsed:: true
									- ```css
									  padding-top: 10px;
									  ```
								- Note: ((62d7cf8c-beb1-4572-b767-fbe49c979a10))
							- `padding-right` style property
							  collapsed:: true
								- Example
								  collapsed:: true
									- ```css
									  padding-right: 20px;
									  ```
								- Note: ((62d7cf8c-beb1-4572-b767-fbe49c979a10))
							- `padding-bottom` style property
							  collapsed:: true
								- Example
								  collapsed:: true
									- ```css
									  padding-bottom: 10px;
									  ```
								- Note: ((62d7cf8c-beb1-4572-b767-fbe49c979a10))
							- `padding-left` style property
							  collapsed:: true
								- Example
								  collapsed:: true
									- ```css
									  padding-left: 20px;
									  ```
								- Note: ((62d7cf8c-beb1-4572-b767-fbe49c979a10))
					- _Margin style properties_
					  collapsed:: true
						- `margin` style property
						  collapsed:: true
							- Controls the amount of space between an element's `border` and surrounding elements
							- Examples
							  collapsed:: true
								- ```css
								  margin: 20px;
								  ```
								- ```css
								  margin: -15px;
								  ```
							- Example - clockwise notation can be used instead of specifying each margin side individually:
							  id:: 62d7d176-3b4a-49f2-bf70-f0ff29974a95
							  collapsed:: true
								- collapsed:: true
								  ```css
								  margin: 10px 20px 10px 20px;
								  ```
									- Can be used instead of:
									  collapsed:: true
										- ```css
										  margin-top: 10px;
										  margin-right: 20px;
										  margin-bottom: 10px;
										  margin-left: 20px;
										  ```
						- _Directional margin style properties_
						  collapsed:: true
							- Note: ((62d7d176-3b4a-49f2-bf70-f0ff29974a95))
							- `margin-top` style property
							- `margin-right` style property
							- `margin-bottom` style property
							- `margin-left` style property
					- _Border style properties_
					  collapsed:: true
						- `border` style property?
						- `border-color` style property
						  collapsed:: true
							- ```css
							  border-color: red;
							  ```
						- `border-width` style property
						  collapsed:: true
							- ```css
							  border-width: 5px;
							  ```
						- `border-style` style property
						  collapsed:: true
							- ```css
							  border-style: solid;
							  ```
						- `border-radius`style property
						  collapsed:: true
							- Examples
							  collapsed:: true
								- ```css
								  border-radius: 10px;
								  ```
								- ```css
								  border-radius: 50%;
								  ```
			- How to style groups of elements
			  collapsed:: true
				- First decide which one of ((62d7c01f-4565-4e14-aaf3-4abe0957e79a))
				- Next, choose a selector:
				  id:: 63045a99-14de-4b65-af5e-a97b557dc8da
					- Note: [these next exercises on the legacy course is buggy and won't accept a correct solution despite displaying correctly in the HTML preview column](https://forum.freecodecamp.org/t/freecodecamp-challenge-guide-use-css-selectors-to-style-elements/18349/9)
					- *Types of selectors*
					  id:: 632b5d57-e64c-44df-af35-e6a745c2ba0c
						- Type selector
						  id:: 63045a99-a9d7-434c-ad2c-213c9670bf4f
						  collapsed:: true
							- Inside a `<style>` block you can create CSS selector which will affect all HTML elements of a type
							  collapsed:: true
								- Example
								  collapsed:: true
									- ```css
									  <style>
									    h2 {
									      color: red;
									    }
									  </style>
									  ```
							- #card #A006 Create a CSS selector which will make all `h2` element the `color` `red`
								- ```css
								  <style>
								    h2 {
								      color: red;
								    }
								  </style>
								  ```
						- `class` selector (`.`)
						  id:: 62d7c01f-2b9d-44f3-8ae7-6d635349e6e4
						  collapsed:: true
							- ((62d6eecc-0c95-4d73-9c99-908e9d0cc195)) can be used to style multiple elements at once
							- Classes are reusable styles that can be added to HTML elements
							- They're denoted by having a `.` prefix within the CSS `style` element, but not within the HTML element ((62d6eecc-0c95-4d73-9c99-908e9d0cc195))
							- Here's an example CSS class declaration called `blue-text`:
								- collapsed:: true
								  ```css
								  <style>
								      .blue-text {
								          color: blue;
								      }
								  </style>
								  ```
									- This allows applying any HTML element with the corresponding ((62d6eecc-0c95-4d73-9c99-908e9d0cc195))
							- `class` attribute
							  id:: 62d6eecc-0c95-4d73-9c99-908e9d0cc195
								- Specifies one or more classnames for an element (refers to a class in a style sheet)
								- Example
									- ```html
									  <h2 class="blue-text">CatPhotoApp</h2>
									  ```
									- Example - applying several classes to one element
									  collapsed:: true
										- ```css
										  <img class="smaller-image thick-green-border">
										  ```
							- `:root` pseudo-class selector
							  id:: 62d7fcee-0e65-45ff-b77c-ac7c98dbff73
							  collapsed:: true
								- ((62d7fcb8-c213-44b6-a59b-f3c4ac877205))
								- To make use of inheritance, ((62d7eac8-9f24-453c-a5e6-42b487e2ceb4)) are often defined in the `:root` element.
								  id:: 63045a99-8ea6-4f4a-a100-abeba61b7872
								- `:root`  is a pseudo-class selector that matches the root element of the document, usually the  `html`  element. By creating your variables in  `:root` , they will be available globally and can be accessed from any other selector in the style sheet.
							- Flashcards
							  collapsed:: true
								- #card #A006 Create a CSS selector that will affect all elements on a webpage, regardless of the attributes it uses, and will give it `color: pink`
								  collapsed:: true
									- ```css
									  :root {
									    color: pink;
									  }
									  ```
								- #card #A006 Create a CSS selector that will affect all elements in the `<body>` element, regardless of the attributes it uses, and will give it `color: pink`
								  collapsed:: true
									- ```css
									  body {
									    color: pink;
									  }
									  ```
								- #card #A006 Create a CSS selector which will make all of the `hello` class the `color` `red`
								  collapsed:: true
								  id:: 632092fb-ef8a-4ad9-b51e-1245b10d5232
									- ```css
									  <style>
									      .hello {
									          color: red;
									      }
									  </style>
									  ```
								- #card #A006 Given the following CSS, create a HTML element which will be affected by this selector
								  collapsed:: true
								  
								  ```css
								  <style>
								      .hello {
								          color: red;
								      }
								  </style>
								  ```
									- ```html
									  <h2 class="hello">CatPhotoApp</h2>
									  ```
								- #card #A006 Given the following CSS, create a HTML element which will be affected by both these selectors
								  collapsed:: true
								  
								  ```css
								  <style>
								      .a-selector {
								          color: red;
								      }
								      .b-selector {
								          font-size: 12px;
								      }
								  </style>
								  ```
									- ```html
									  <h2 class="a-selector b-selector">CatPhotoApp</h2>
									  ```
						- `id` selector (`#`)
						  id:: 62d7c13f-3994-4362-8322-dfec8aedc3c3
						  collapsed:: true
							- ((62d6c178-8f23-40f0-9a4f-f258aafb0270)) can be used to style specific single elements. It's prefixed with `#` when it's in a `<style>` element
							- Should only be used with one element, unlike [CSS classes](((62d7c01f-2b9d-44f3-8ae7-6d635349e6e4))) which is meant for multiple elements
							- Example
								- ```html
								  <style>
								    #cat-photo {
								      background-color: green;
								    }
								  </style>
								  
								  <h2 id="cat-photo">Hello</h2>
								  ```
							- #card #A006 Given the following element, modify it as well as create a CSS selector which will only give that element `background-color` of `green`, regardless of another element of the same type is added later
							  collapsed:: true
								- ```html
								  <style>
								  #cat-photo {
								    background-color: green;
								  }
								  </style>
								  - <h2 id="cat-photo">Hello</h2>
								  ```
						- `[attr=value]`  attribute selector
						  collapsed:: true
						  id:: 63045a99-cbba-486e-8dce-3af6b8793596
							- This selector matches and styles elements with a specific attribute value.
							- Example - For example,  changes the margins of all elements with the attribute  `type`  and a corresponding value of  `radio` :
							  collapsed:: true
								- ```css
								  [type='radio'] {
								    margin: 20px 0px 20px 0px;
								  }
								  ```
							- #card #A006 Create an example CSS using the CSS attribute selector (assume a corresponding HTML element already exists)
								- ```css
								  [type='radio'] {
								    margin: 20px 0px 20px 0px;
								  }
								  ```
						- Related: ((63317807-bd1e-430c-bf63-985d824439f1))
					- Flashcards
					  collapsed:: true
						- #card #A006 Match these descriptions to the correct CSS selector:
						  
						  A) Can be used to style single elements with the corresponding attribute
						  B) Can be used to style multiple elements with the corresponding attribute
						  C) Can be used to style multiple elements of the same type
						  D) Can be used to style multiple elements with the corresponding attribute value
						  E) Can be used to style all elements on the page
							- A) ((62d7c13f-3994-4362-8322-dfec8aedc3c3))
							  B) ((62d7c01f-2b9d-44f3-8ae7-6d635349e6e4))
							  C) ((63045a99-a9d7-434c-ad2c-213c9670bf4f))
							  D) ((63045a99-cbba-486e-8dce-3af6b8793596))
							  E) ((62d7fcee-0e65-45ff-b77c-ac7c98dbff73))
					- Related: ((62d44751-6141-4c5b-8fd5-93b32359e4d3))
			- Importing web fonts
			  id:: 62d7010b-fe3c-43f1-9d68-00d6ab86626e
			  collapsed:: true
				- Steps
				  collapsed:: true
					- 1) Add a `<link>` element with a similar format above the `<style>` element
					  collapsed:: true
						- Example
						  collapsed:: true
						  id:: 63045a99-c249-4bc9-bc79-b598216ee09e
							- ```html
							  <head>
							    <link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
							    <style></style>
							  </head>
							  ```
						- Related: A different use of `<link>` ((6302598d-87a1-4306-8ddf-9c7cf8dbee95))
							- {{embed ((63045a99-467a-4956-a722-e5b23bf6a378))}}
						- #card #A006 Write an example element which would allow importing web fonts, and the parent element it would be embedded in
							- ```html
							  <head>
							    <link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
							    <style></style>
							  </head>
							  ```
					- 2) Within the `<style>` element add a ((62d7005b-cbc2-42db-9709-c65acec2267c)) with the following properties
					  collapsed:: true
						- See ((62d7005b-cbc2-42db-9709-c65acec2267c)) -> ((62d70250-c816-49e1-852c-3882f1962e77))
						- Example
						  collapsed:: true
							- ```html
							  <head>
							    <link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
							    <style>
							      h2 {
							        font-family: Lobster;
							      }
							    </style>
							  </head>
							  ```
						- #card #A006 Write an example CSS selector and appropriate style property that would allow using this web font (already assuming there's a HTML element with some text)
						  
						  ```html
						  <head>
						    <link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
						    <style></style>
						  </head>
						  ```
							- ```html
							  <head>
							    <link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
							    <style>
							      h2 {
							        font-family: Lobster;
							      }
							    </style>
							  </head>
							  ```
			- Specifying how fonts should degrade
			  collapsed:: true
				- There are several default fonts that are available in all browsers. These generic font families include  `monospace` ,  `serif`  and  `sans-serif` .
				- When one font isn't available, you can tell the browser to "degrade" to another font.
				- Example - use `Helvetica` ideally, but downgrade to `sans-serif` otherwise
				  collapsed:: true
					- ```css
					  p {
					    font-family: Helvetica, sans-serif;
					  }
					  ```
				- Generic font family names are not case-sensitive. Also, they do not need quotes because they are CSS keywords.
				- #card #A006 Given the following element, create a CSS selector which will use `Helvetica` as the `font-family` ideally, but will downgrade to a default font family
				  
				  `<h2>Test</h2>`
					- ```css
					  h2 {
					    font-family: Helvetica, sans-serif;
					  }
					  ```
			- Absolute vs Relative units
			  collapsed:: true
			  id:: 63045a99-a305-4fa2-a171-762107505acd
				- Absolute = `px` (pixels)
				  collapsed:: true
					- Example
					  collapsed:: true
						- ```css
						  font-size: 30px;
						  ```
				- Relative = `em` (based on size of an element's font)
				  collapsed:: true
					- Example
					  collapsed:: true
						- collapsed:: true
						  ```css
						  padding: 1.5em;
						  ```
							- Note: `font-size: 1em;` would be relative to the parent's `font-size`
					- Often related to the size of the viewport
			- Inheritance
			  id:: 62d7df67-0966-44bc-a65d-9418081f327e
			  collapsed:: true
				- _Order of priority, from lowest to highest_
				  id:: 62d7e225-d36f-4d4d-b6dd-6c994fb0959e
				  collapsed:: true
					- [`body` element](((62d7db38-a010-4d08-b5c1-4f01ca815d41)))
					  id:: 63045a99-b485-4f7c-bcd2-1feddb3db37d
					- ((62d7c01f-2b9d-44f3-8ae7-6d635349e6e4))
					  id:: 63045a99-5ebf-4916-a585-5e1ba95e16e8
					- ((62d7c13f-3994-4362-8322-dfec8aedc3c3))
					  id:: 63045a99-2871-47e0-8d4d-f1fa86989333
					- [Inline styles](((62d7c01f-ca4c-423e-a889-e645cc801b03)))
					  id:: 63045a99-5a97-422f-82bf-fc3cf93b2d4a
					- `!important` CSS keyword
					  id:: 62d7e44c-a4f5-432f-9bb8-35b72b28136e
					  collapsed:: true
						- Example
						  collapsed:: true
							- ```css
							  color: red !important;
							  ```
				- `body` element can be styled
				  id:: 62d7db38-a010-4d08-b5c1-4f01ca815d41
				  collapsed:: true
					- Styling the `body` element is useful so that all other elements will inherent it's styles
					- Example
					  collapsed:: true
						- ```css
						  body {
						    background-color: black;
						  }
						  ```
				- ((62d7c01f-2b9d-44f3-8ae7-6d635349e6e4)) will override `body` element CSS declaration
				  collapsed:: true
					- Example - h1 text will be pink
					  collapsed:: true
						- ```css
						  <style>
						    body {
						      color: green;
						    }
						    .pink-text {
						      color: pink;
						    }
						  </style>
						  <h1 class="pink-text">Hello World!</h1>
						  ```
				- The later declarations will take precedence over the earlier ones if both are ((62d7c01f-2b9d-44f3-8ae7-6d635349e6e4))
				  collapsed:: true
					- Example - h1 text will be blue
					  collapsed:: true
						- ```css
						  <style>
						    .pink-text {
						      color: pink;
						    }
						  
						    .blue-text {
						      color: blue;
						    }
						  </style>
						  <h1 class="pink-text blue-text">Hello World!</h1>
						  ```
				- ((62d7c13f-3994-4362-8322-dfec8aedc3c3)) declarations will override ((62d7c01f-2b9d-44f3-8ae7-6d635349e6e4)) declarations
				  collapsed:: true
				  id:: 63045a99-ec1d-443c-8bea-6cf7098e9a52
					- Example - h1 text will be orange
					  collapsed:: true
						- ```css
						  <style>
						    #orange-text {
						      color: orange;
						    }
						    .pink-text {
						      color: pink;
						    }
						  </style>
						  <h1 id="orange-text" class="pink-text">Hello World!</h1>
						  ```
				- [Inline styles](((62d7c01f-ca4c-423e-a889-e645cc801b03))) will override ((62d7c13f-3994-4362-8322-dfec8aedc3c3)) declarations
				  collapsed:: true
					- Example - h1 text will be white
					  collapsed:: true
						- ```css
						  <style>
						    body {
						      background-color: black;
						      font-family: monospace;
						      color: green;
						    }
						    #orange-text {
						      color: orange;
						    }
						  
						    .blue-text {
						      color: blue;
						    }
						  </style>
						  <h1 id="orange-text" class="blue-text" style="color: white">Hello World!</h1>
						  ```
				- ((62d7e44c-a4f5-432f-9bb8-35b72b28136e)) will override ((62d7c01f-ca4c-423e-a889-e645cc801b03)) declarations
				  collapsed:: true
					- Example - h1 text will be pink
					  collapsed:: true
						- ```css
						  <style>
						    body {
						      background-color: black;
						      font-family: monospace;
						      color: green;
						    }
						    #orange-text {
						      color: orange;
						    }
						    .pink-text {
						      color: pink !important;
						    }
						    .blue-text {
						      color: blue;
						    }
						  </style>
						  <h1 id="orange-text" class="pink-text blue-text" style="color: white">Hello World!</h1>
						  ```
				- Flashcards
				  collapsed:: true
					- #card #A006 Give an example which uses the CSS `!important`
					  collapsed:: true
						- ```css
						  color: red !important;
						  ```
					- #card #A006 Given the following, what colour will the text be?
					  collapsed:: true
					  
					  ```css
					  <style>
					    #orange-text {
					      color: orange;
					    }
					    .pink-text {
					      color: pink;
					    }
					  </style>
					  <h1 id="orange-text" class="pink-text">Hello World!</h1>
					  ```
						- Orange, because ((63045a99-ec1d-443c-8bea-6cf7098e9a52))
					- #card #A006 Given the following, what colour would the text be of an element that matches both selectors?
					- collapsed:: true
					  ```css
					  <style>
					  #orange-text {
					    color: orange;
					  }
					  .pink-text {
					    color: pink;
					  }
					  </style>
					  ```
						- Orange, because ((63045a99-ec1d-443c-8bea-6cf7098e9a52))
					- #card #A006 Order these selectors, in terms of priority from lowest to highest for inheritance 
					  collapsed:: true
					  
					  A) ((63045a99-5a97-422f-82bf-fc3cf93b2d4a))
					  B) ((63045a99-5ebf-4916-a585-5e1ba95e16e8))
					  C) ((62d7e44c-a4f5-432f-9bb8-35b72b28136e))
					  D) ((63045a99-b485-4f7c-bcd2-1feddb3db37d))
					  E) ((63045a99-2871-47e0-8d4d-f1fa86989333))
						- D) ((63045a99-b485-4f7c-bcd2-1feddb3db37d))
						  B) ((63045a99-5ebf-4916-a585-5e1ba95e16e8))
						  E) ((63045a99-2871-47e0-8d4d-f1fa86989333))
						  A) ((63045a99-5a97-422f-82bf-fc3cf93b2d4a))
						  C) ((62d7e44c-a4f5-432f-9bb8-35b72b28136e))
						  
						  {{embed ((62d7e225-d36f-4d4d-b6dd-6c994fb0959e))}}
					- #card #A006 Give a CSS selector example which will make the `background-color` of as much as possible of the below HTML `orange`
					  collapsed:: true
					  
					  ```html
					  <body>
					    <div>
					    <h2>Hello</h2>
					    </div>
					  </body>
					  ```
						- ```css
						  body {
						    background-color: orange;
						  }
						  ```
					- #card #A006 Given the following, what colour will the `h1` be?
					  collapsed:: true
					  card-last-interval:: 4
					  card-repeats:: 1
					  card-ease-factor:: 2.36
					  card-next-schedule:: 2022-09-19T11:49:26.350Z
					  card-last-reviewed:: 2022-09-15T11:49:26.351Z
					  card-last-score:: 3
					  
					  ```css
					  <style>
					    .pink-text {
					      color: pink;
					    }
					    .blue-text {
					      color: blue;
					    }
					  </style>
					  <h1 class="pink-text blue-text">Hello World!</h1>
					  ```
						- Blue
			- `--` CSS Variables
			  id:: 62d7eac8-9f24-453c-a5e6-42b487e2ceb4
			  collapsed:: true
			  AKA Custom Properties
				- Note: Microsoft's Internet Explorer doesn't support these
				- This can be used to change the values for multiple style properties at once
				  id:: 63061248-a264-4ba1-8823-78eef03517a0
				- Example
				  collapsed:: true
					- ```css
					  :root {
					    --penguin-skin: gray;
					  }
					  
					  .class1 {
					    background: var(--penguin-skin);
					  }
					  
					  .class2 {
					    background: var(--penguin-skin);
					  }
					  ```
				- Fallback values can be added that your browser will revert to if a given variable is invalid
				  collapsed:: true
					- Example - this will set your background to `black` if the variable `--penguin-skin` wasn't set
						- ```css
						  :root {
						    --penguin-skin: gray;
						  }
						  .class2 {
						    background: var(--penguin-skin, black);
						  }
						  
						  ```
				- Improving browser compatibility with fallback values
				  collapsed:: true
					- Example - put at the bottom the CSS declaration that is more likely to fail, that way at least the earlier CSS will load:
					  collapsed:: true
						- ```css
						    .red-box {
						      background: red;
						      background: var(--red-color);
						  ```
				- Inherit CSS variables
				  id:: 62d7fcb8-c213-44b6-a59b-f3c4ac877205
				  collapsed:: true
					- ((62d7fcee-0e65-45ff-b77c-ac7c98dbff73))
					- Example
					  collapsed:: true
						- ```css
						    :root {
						      --penguin-belly: pink;
						    }
						  
						    body {
						      background: var(--penguin-belly);
						    }
						  ```
					- Note: following ((62d7df67-0966-44bc-a65d-9418081f327e)) -> ((62d7e225-d36f-4d4d-b6dd-6c994fb0959e)), variables in `:root` can be overridden
					  collapsed:: true
						- Example
						  collapsed:: true
							- ```css
							  :root {
							    --penguin-belly: pink;
							  }
							  
							  body {
							    background: var(--penguin-belly);
							  }
							  
							  .penguin {
							      --penguin-belly: white;
							  }
							  ```
					- ((63045a99-8ea6-4f4a-a100-abeba61b7872))
				- Media queries can be used to change variables
				  collapsed:: true
					- Example - this will change the value of the variale when the screen is smaller or larger than the media query breakpoint
					  collapsed:: true
						- ```css
						    :root {
						      --penguin-size: 300px;
						      --penguin-skin: gray;
						    }
						  
						    @media (max-width: 350px) {
						      :root {
						        --penguin-size: 200px;
						        --penguin-skin: black;
						      }
						    }
						  
						    .penguin {
						      width: var(--penguin-size, 300px);
						      height: var(--penguin-size, 300px);
						    }
						  ```
				- Flashcards
					- #card #A006 Give an example of a CSS variable (custom property), as well as it being used in another CSS selector
					  collapsed:: true
						- ```css
						  :root {
						    --penguin-skin: gray;
						  }
						  
						  .class2 {
						    background-color: var(--penguin-skin);
						  }
						  ```
					- #card #A006 In what element are CSS variables (custom properties) usually embedded?
					  collapsed:: true
						- `:root` pseudo-class so it can be used when needed throughout the whole document
					- #card #A006 What CSS do CSS variables (custom properties) replace when declared, and what when embedded?
					  collapsed:: true
						- CSS style property, and style property value
					- #card #A006 Given the following CSS variable (custom property), use it in another CSS selector and also add a fallback value in that selector
					  collapsed:: true
					  card-last-interval:: -1
					  card-repeats:: 1
					  card-ease-factor:: 2.5
					  card-next-schedule:: 2022-09-14T23:00:00.000Z
					  card-last-reviewed:: 2022-09-14T18:20:40.697Z
					  card-last-score:: 1
					  
					  ```css
					  :root {
					    --penguin-skin: gray;
					  }
					  ```
						- ```css
						  .class1 {
						    background-color: var(--penguin-skin, black);
						  }
						  ```
						  or
						  ```css
						  .class1 {
						    color: black;
						    color: var(--penguin-skin);
						  }
						  ```
					- #card #A006 Given the following CSS variable (custom property), use it in another CSS selector and also add a fallback value in that selector
					  collapsed:: true
					  
					  ```css
					  :root {
					    --penguin-skin: gray;
					  }
					  ```
						- ```css
						    .class2 {
						      background: red;
						      background: var(--penguin-skin);
						  ```
					- #card #A006 Given the following CSS variable (custom property), override it with another selector of a higher priority inheritance that won't affect the `body` selector
					  collapsed:: true
					  
					  ```css
					  :root {
					    --penguin-belly: pink;
					  }
					  
					  body {
					    background: var(--penguin-belly);
					  }
					  ```
						- ```css
						  .penguin {
						    --penguin-belly: white;
						  }
						  ```
					- #card #A006 Given the following, add a media query which will override these CSS variables when the `max-width` is `350px`
					  collapsed:: true
					  
					  ```css
					    :root {
					      --penguin-size: 300px;
					      --penguin-skin: gray;
					    }
					  ```
						- ```css
						  :root {
						    --penguin-size: 300px;
						    --penguin-skin: gray;
						  }
						  @media (max-width: 350px) {
						    :root {
						      --penguin-size: 200px;
						      --penguin-skin: black;
						    }
						  }
						  ```
			- ((62f67eaf-d7f3-4d8f-8f67-3d6e2753aaff))
			- Related: [[CSS]]
		- Applied Visual Design
		- Applied Accessibility
		- Responsive Web Design Principles
		- CSS Flexbox
		  id:: 634bc17f-8b60-47b9-8b17-b001e69c1abd
		- CSS Grid
		- Responsive Web Design Projects