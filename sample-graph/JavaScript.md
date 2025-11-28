- Pros/Cons
  collapsed:: true
	- Pros
		- is hot in 2017 - use React Native for mobile and something for web apps
		- Web is more free a platform than mobile
		  collapsed:: true
			- Google is forcing new Android apps to use Android App Bundles - which means developers have to give Google their private signing keys
			- Microsoft are circumventing Apple's restrictions on hosting game stores on iOS by making their Xbox Cloud Gaming available as a Progressive Web App
				- Apple has restrictions on Progressive Web Apps to apparently but I'm not sure to what extent
		- Scales well in 3 of 4 ways
		  collapsed:: true
			- ![image.png](../assets/image_1673556369339_0.png)
	- Cons
		- Third-party package issues
		  collapsed:: true
			- Traditional JS is actually among the safest environments ever created. Every day, billions of devices run untrusted JS code, and no other platform has seen sandboxed execution at such scale. And in nearly three decades, there have been very few incidents of large successful attacks on browser engines. That makes the JS engine derived from browsers the perfect tool to build a server side framework out of.
				- However, processes and practices around NodeJS and npm are in dire need of a security overhaul. When the bad actor's target is a developer's server rather than a browser user, then they're easy to compromise thanks to little oversight into new updates to npm packages
			- Javascript doesn't have a standard library, until it does the 170 million weekly downloads of packages like [UUID](https://www.npmjs.com/package/uuid) will continue. You can't expect people to re-write everything over and over.
			- The solution is not to go back to vanilla JS, it's for people to form a foundation and build a more complete utilities library for JS that doesn't have 1000 different dependencies, and can be trusted. Something like Boost for C++, or Apache Commons for Java.
				- Python and Rust both have decent std lib, but it is just a matter of time before this happens in thoae ecosystems. There is nothing unique about this specific attack that could only happen in JavaScript.
		- What’s Wrong with JavaScript?
		  collapsed:: true
			- https://whydoesitsuck.com/why-does-javascript-suck/
				- Instance inheritance
				- Scoping: Cannot avoid global variables and have to create closures to have any kind of data hiding
				- Falsy
		- [WebAssembly](((629ccb26-a02e-4939-ac4f-f7fc22c05a97))) might replace JavaScript
		  id:: 629ccb26-5148-4b1f-86a8-055fdf669f27
		- Dart/Flutter might replace JavaScript
		  collapsed:: true
			- Why
				- It's highly cross platform on mobile and desktop, just not web yet
				- It will be the primary framework on Fuchsia, and that's almost certainly going to replace Android's Linux kernel
- # Documentation
  #A002 `~/Documents/MUSEUM/Programming/Anki1.ods`
	- ## Cheatsheet
	  id:: 635593b2-818d-4d6c-a00c-cfa7f4cd850a
	  collapsed:: true
		- # Categories
			- [[JavaScript]] / ((629ccb26-1eab-4686-a7b8-f9433a871440)) cheatsheet
			  collapsed:: true
				- Quick links
					- ((66ba22e0-f894-4d28-80c2-98ae6feb4171))
				- **To ingrain**
				  id:: 6408d44e-1000-4594-ab4b-8e5a18543479
					- ((64024e3f-d75a-46c3-98e3-e4679ebc4b50)) manipulation
					  collapsed:: true
						- ((63484525-06f3-4d0d-a0cc-2c93b0f6be60))
						- ((63fdd9d7-2555-4f15-8f94-798587be6b3c))
						- To get last character of a string use either `String[String.length-1]` or `String.slice(-1)`
						- Inline ternary operator is can be useful for some functions like conditional string concatenation
						  collapsed:: true
							- Example: ((63f33e7b-1a4b-413e-b00d-efe1a87c0a8a))
								- {{embed ((d6066a95-9e02-45c9-8d0c-6a3db80390be))}}
						- ((63470fd1-1f37-4428-9546-d674c323d5d1)) : ((63baa388-24f2-42ae-913a-d2efcaf9f4bf))
						  collapsed:: true
							- Example: ((db967743-4408-46dc-a72c-7a0efcc2f248))
								- {{embed ((db967743-4408-46dc-a72c-7a0efcc2f248))}}
						- ((63f33e7c-dd58-4555-93f9-15a02fe35376)) is useful during string concatenation
						- ((63470fd1-de4c-4705-9fb1-e734bf59cdd7)) : ((63f29925-f6ae-4cd6-96ad-e6c66a96f1cb))
						- ((63904f3d-d998-45d3-9f94-c97030425ec2)) : ((63f215db-3662-4702-823a-59316716ef34))
						- ((63470fd1-1f37-4428-9546-d674c323d5d1)) : ((63baa388-24f2-42ae-913a-d2efcaf9f4bf))
						  id:: 6347b91e-ec78-403e-a18d-de40ff54f345
						- ((63470fd1-5259-4cdb-a208-b49d213b679b)) : ((63baa388-4fe1-416f-a1b2-6e3755f6aede))
						  id:: 6347b43d-34fb-4d29-85b1-934bc0212c36
						- ((63470fd1-332b-4ebf-965d-7073b319c11b)) : ((63f297c1-a028-4e79-a600-e12e670fbca2))
						- ((6345ae08-f477-4d93-8a9e-e1825a4dbf30)) : ((63baa388-00f3-4cf9-9e71-e74211713820))
						- ((63470fd1-d1aa-49cd-95ec-4a5a0cf2ef74)) : ((63f298d8-e92e-4e36-bfa2-37818da7cf4d))
						- ((63470fd1-335a-43ad-be82-547be1c10d07)) : ((63f2995e-3c1d-4961-8d40-38ed8cd83373))
					- ((64024e3f-2a66-4456-816f-f0b00cfd0c4e)) manipulation
					  collapsed:: true
						- ((63679853-bf0c-44a1-9fba-087790dbcc45)) : ((63fdd9d7-f6c7-4b7b-8eda-521c5d014922))
						- ((63679853-27fd-40a4-bd44-b836c61f4394)) : ((64024d45-68f1-4b21-8fe3-af5d7a8489a3))
						- ((63679853-46c2-4992-ab73-5c27acc7ce2e)) :
							- ((64010eac-b5f5-404e-851f-6eca86550049))
							- ((640234da-c807-43bd-a52e-b122082e86d4))
						- To empty an array set `arr.length = 0`
						  id:: 6350374c-0936-4de6-a686-4e1b2329412c
						- ((d0a968a6-4f22-48e4-ae07-45629e7372db))
						  id:: 63470fd1-76d3-45ab-89f6-95d278c0dabe
						- ((634bc0c2-38ee-4fdb-b785-2b19b9d2a6e1))
						- ((635eb08f-48a4-41e1-9112-9f62670ddec2))
						- ((63679853-7115-4961-bd6b-0b224f149a11)) is superb for FizzBuzz and other times you need to replace items in an array
						  collapsed:: true
							- Example: ((63ef9163-b156-414c-ba00-27c352c96685))
						- ((63470fd1-ed0f-45f6-9b63-2ee67c3c152f)) : ((63f2aa4d-31c4-4f62-817c-a1bfae893094))
						- ((6350374d-3846-414b-a27e-7d32b86eec86)) : ((63f239d8-2241-4838-9121-3b0ccc43dee7))
						- ((63642a10-4e86-4101-961a-8311efb8ae4f)) : ((63f294fd-f0e1-453a-afc4-17a340b58e16))
						- ((63679853-1c98-454a-8932-e67322c119d9)) : ((63f2952f-86d7-4fdd-aafa-51bf4fa40dfb))
						- ((63906cf1-ee3b-481e-9b7e-08ad98c55c5d))
						  collapsed:: true
							- {{embed ((63906cf1-ee3b-481e-9b7e-08ad98c55c5d))}}
						- ((63470fd1-5c6c-4c4d-aea0-9d111a003975)) : ((63f2965f-e63c-44c2-89f3-ecd6f644632f))
						- ((63470fd1-ed0f-45f6-9b63-2ee67c3c152f)) : ((63f2976f-4508-41b5-9d84-47dd345a0990))
						- ((63f903ec-e5f7-44e5-9bd6-7aa607d0b969))
						- How can I check if a JavaScript array includes a specific value?
						  collapsed:: true
							- Primitive values - use `Array.prototype.includes()`
							- Objects - Use `Array.prototype.some()` to check if any object matches the shape of another object. Array.prototype.includes() can't be used due to objects being reference types (see object comparison https://www.30secondsofcode.org/articles/s/javascript-object-comparison)
								- ```js
								  const array = [{ a: 1 }, { a: 2 }, { a: 3 }];
								  
								  const equals = (a, b) => Object.keys(a).every(key => a[key] === b[key]);
								  
								  array.some(item => equals(item, { a: 2 })); 
								  array.some(item => equals(item, { a: 4 })); 
								  ```
					- ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1)) manipulation
					  collapsed:: true
						- ((6377ece4-b9b9-413a-8195-15de9b9c5ec2)) : ((6408bfe1-6ca4-4ba1-8f6a-1d72eb69ffce))
						- ((6408649f-1747-45ba-95c1-5bf5984a32a6))
						- ((64084faa-6068-42d4-a193-2263c4b4d039))
						- ((64024e3f-549b-4656-8bac-049e1eb3580b)) : ((766969c0-49a0-4a07-9b69-02351708da55))
					- ### Type conversion
						- ### From String
							- ((638f4569-62ae-4ff5-bcd8-05d9e9794183)) : ((63f90cc1-edf9-4d69-8bf3-2f444910e465))
							- How to convert a string to a boolean
							  collapsed:: true
								- Any non-empty string is considered truthy in JavaScript, so it's a good idea to use a couple of transformations, namely String.prototype.toLowerCase() and String.prototype.trim(), to make the string representation of the value more consistent
									- [String.prototype.trim()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim)
										- Removes whitespace from both ends of the string and returns the new string. Immutable method as it doesn't modify the original string
										- Related:
											- [trimStart()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trimStart)
											- [trimEnd](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trimEnd)
								- an array of acceptable values might make it easier to perform the conversion in certain cases, which is why that's one of the parameters (`truthyValues`)
									- [Array.prototype.includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)
										- determines whether an array includes a certain value among its entries, returning true or false as appropriate
								- ```javascript
								  const toBoolean = (value, truthyValues = ['true']) => {
								  const normalizedValue = String(value).toLowerCase().trim();
								  return truthyValues.includes(normalizedValue);
								  };
								  
								  toBoolean('true'); 
								  toBoolean('TRUE'); 
								  toBoolean('True'); 
								  toBoolean('tRue '); 
								  toBoolean('false'); 
								  toBoolean('FALSE'); 
								  toBoolean('False'); 
								  toBoolean('fAlse '); 
								  toBoolean('YES', ['yes']); 
								  toBoolean('no', ['yes']);
								  ```
							- ((63642a10-4e86-4101-961a-8311efb8ae4f)) : ((6400dd4b-2309-4368-a90e-564bc9f5cbb0))
							- ((63470fd1-c937-4cd7-9301-de009d1fb7e0)) : ((63f29878-1bf7-47ea-9b60-6a90394d0c12))
						- ((66ba4356-1666-4c14-ae60-2c17993d8c76)) : ((66ba4367-68bf-41d1-bf05-f86a6ae43825))
						- ((63470fd1-de4c-4705-9fb1-e734bf59cdd7)) : ((63f219c9-6008-4f84-beba-7db15dd52f76))
						- ((638f490f-1505-4a98-9399-94834d07c5b6)) : ((63f90c9d-a27c-454b-8848-98c6627b7905))
						- ((6488932a-5cd5-4e35-9412-bdaeff5fb153)) : ((64889457-d7d5-4fe8-bbf5-538be01ddd56))
						- ((6351322c-6b12-4902-b961-9ad79f67c9dc))
						  collapsed:: true
							- {{embed ((6351322c-6b12-4902-b961-9ad79f67c9dc))}}
						- ((63513279-b287-4afa-89fd-764214eba393))
						- ((507dc5b1-e753-4ada-9eee-5acd64ec1f7d)) : ((6408c102-0f97-4a12-820b-ce707252c952))
						- ((64024e3f-dbb1-4d5c-9b49-76009df56467)) : ((64024e3f-ab8d-4776-964c-79c44a5c8c1f))
						- Convert decimal number to hexadecimal
						  collapsed:: true
							- Number.prototype.toString(16)
							- ```js
							  const decimalToHex = dec => dec.toString(16);
							  
							  decimalToHex(0); 
							  decimalToHex(255); 
							  ```
							- To do the reverse (string to a number in a given base)
							- ```js
							  const hexToDecimal = hex => parseInt(hex, 16);
							  
							  hexToDecimal('0'); 
							  hexToDecimal('ff'); 
							  ```
					- ((64024e3f-184c-440e-b9e6-c2e0abf1a2a3)) manipulation
						- ((0257c452-a8cc-40b2-b47a-235d81f263ce)) : ((63f90e8f-6ac5-4eff-ad9f-4aa51f3a52a1))
						- ((63fd16e2-0108-4579-b85a-717d83927648)) is great for getting the sum of a sequence of integers
					- *Binary and other base manipulation*
						- ((63470fd1-de4c-4705-9fb1-e734bf59cdd7)) : ((63f219c9-6008-4f84-beba-7db15dd52f76))
					- *Assorted*
						- ((66bce5d1-babc-4aa9-b668-2fd3dd5b45be))
						- ((66bcfc84-1397-497c-a788-d7c396e82de8))
						- For `if` statements (and more?) curly brackets `{ }` are not actually necessary if the expression is on a single line
						  collapsed:: true
							- `if` statements
								- Examples
								  collapsed:: true
									- ((63cf9164-5abf-48eb-b525-6356c001e05f))
										- {{embed ((63f8fe4c-e392-47d9-8aa9-fb166942f2c0))}}
									- ((63cf8ec4-f24a-4619-83be-737562d558e6))
										- {{embed ((63f90938-2ffa-431b-8137-172d6187dc67))}}
									- ((63cf8c8e-16ef-4c89-8d92-69f6e63c6f47))
										-
							- `for` loops
								- Examples
								  collapsed:: true
									- ((63cf8ec4-f24a-4619-83be-737562d558e6))
										- {{embed ((63f90938-2ffa-431b-8137-172d6187dc67))}}
						- If a function is supposed to return a boolean, can just use a `return` with an equality operator, instead of a conditional
						  collapsed:: true
							- Example: ((63f33e7b-8d10-4739-8c49-2dfefc8d2c1e))
								- {{embed ((5aee7c7d-c7f5-4201-936b-8e496e51e5dc))}}
						- It's possible to add new methods to prototypes, allowing their use similar to native methods
						  collapsed:: true
							- Examples
								- `String.prototype.toJadenCase = function () { }` in ((63f66f5b-a9f1-4c41-9489-9e5c904781c0))
								  collapsed:: true
									- This line of JavaScript code is adding a new method to the `String` prototype called `toJadenCase`.
									- `String.prototype` is the prototype object for all string instances in JavaScript. By adding a new method to the `String` prototype, we can use this method on any string object in our code.
						- ((63e40d8b-b5b5-4124-a386-e28fb962d7e1)) : useful for ((63f33e83-b36c-46b9-b411-2886cc6f9d53))
						- ((636d5df2-5117-4f9e-8113-83bbb5eff6c1)) : ((63f33e7b-8224-497b-ad76-70ab74cdfa1e))
						- ((63f33581-f747-4705-b965-a7371bc28f77))
						- ((63baa388-27f4-48ce-9808-643b128297a7)) : ((63f29ee4-1022-4275-a0ec-1dc01640e128))
						  id:: 63baa387-43de-492a-be69-95132a6e47b5
						- ((635593b3-9619-4902-8342-f7649f68f90c)) : ((64024e3f-d5e7-43db-9093-a6a28044ff60))
						- ((635593b3-9619-4902-8342-f7649f68f90c)) : ((6400db4c-de72-46ec-98f5-c79d918326c6))
						- ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1)) : ((63f8fedc-7c7f-4902-abd1-b925c86c93ce))
						  collapsed:: true
							- {{embed ((63f8fedc-7c7f-4902-abd1-b925c86c93ce))}}
						- Other
							- ((6343d976-fbe8-45fe-bc74-1fe1b5309a59)) can be ((63fcf532-1fe3-44e0-8423-d49da84a864e))
							- `parseInt(n.toString().split('').sort().reverse().join(''))` to sort a number
							  collapsed:: true
								- Related: ((6364185a-26c2-4213-9783-0dc15ec30342))
							- `return dt === 10 && dx === 0 && dy === 0` is a more concise way than writing `if` all of these, return true
							  collapsed:: true
								- Related: ((6391b172-3c6f-47b6-9b37-f49aa9a2edf0))
									- {{embed ((6391b186-4fc6-47cd-a1ad-d06df9799a79))}}
							- ((63f8fe4d-795b-436e-9fc4-1c0cb402cbda))
						- Multiple takeaways from one example: ((63d18142-3084-4ee3-af2a-1e3187a3705f))
							- {{embed ((63f8d6e9-0f6e-4b56-ab8a-04626cbb3244))}}
					-
				- {Archive} - *Probably ingrained now*
				  collapsed:: true
					- ((63470fd1-b8ce-43b2-ab22-5ba17988fc3e)) : ((63f29a8b-25b6-4d4a-a671-068a6eff4ca9))
					- ((63470fd1-5ac6-4b0c-a9ee-f54e0c50692f)) : ((63f29a65-5fa1-4742-b615-5b45a1bfac86))
					- ((63470fd1-ff2c-4b9a-b116-136a41a52b94)) : ((63f29a46-c5f9-4702-9615-3e231e17ffd2))
					- ((6363f60d-5a9d-48a8-a1d9-996e21bd4858))
					  id:: 634bc0c2-1dad-4964-ae4a-39d0b670b534
			- ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) : ((660d69d8-2984-48b1-8ddd-19e4605d1188))
			- ((629ccb26-62cc-426a-9616-4d8969f32580)) : ((6408d4c2-ff21-45ef-af97-e8bd60dbbcfb))
			  collapsed:: true
				- {{embed ((6408d4c2-ff21-45ef-af97-e8bd60dbbcfb))}}
		- # Unsorted
			- Improve these notes
				- If doing Two Sum algorithm or similar where you loop over an array twice, then have the second loop start from `let j = i + 1` rather than `let j = 0` so that it always is 1 above the previous
					- [source] [Page not found · GitHub · GitHub](https://github.com/PercaysoRecruitment/pe1-soc-cohort13-ajvsol)
				- ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) : ((63679852-8d12-4f83-994e-52e0dcbd642f))
				- ((629ccb26-aed8-440e-92ad-39ed84c0651f))
				- ((6377ece3-fcd7-4478-bf93-a27d3a9eac32)) : ((64024e3f-d36c-4958-be87-5d90de5e50c5))
				- ((6377ece3-44b2-4063-961a-dfdb67fa6ac6))
				- ((63679853-e408-4028-a2c0-eefdd34febd3))
				- ((63904f3d-b287-478d-9e3a-106f8528a920))
				- ((638d0621-0b12-4e67-b88a-3ed069b90233))
				- ((64024e3f-159e-41ab-800d-5a5bf7e98bda))
				- ((64024e3f-dada-457c-af41-eb8557bcff5c))
				- ((635eb08f-d0ba-48f3-aeae-1b2d10f55c84)) : ((6408a8c5-f56e-4a9a-86b5-6a1fabc26812))
			- Stuff to use more often
				- ((63679853-c651-4513-ae6a-b293b5290bd8))
				- ((63a9bb68-a490-44d5-a4db-57db695b5146))
				- ((63470fd1-ff2c-4b9a-b116-136a41a52b94)) : ((64084faa-6068-42d4-a193-2263c4b4d039))
				- ((63e40d8b-b5b5-4124-a386-e28fb962d7e1))
			- ((636d1397-3729-49ea-bdd0-7f5745334aa8))
			- ((2e08cf60-c991-45bb-b23d-a34699a9d300))
			- ((634d55c2-c0e5-4126-b819-8be4151dbd5f)) / ((63642a2b-028e-460f-aed5-9d6bf0113e1e))
			- ((636d5df2-5117-4f9e-8113-83bbb5eff6c1))
			- ## Code snippets
			  id:: 6341c12f-21ed-489f-bb16-1734abd32b1f
			  collapsed:: true
				- By topic
				  id:: 6343d976-3539-4362-a57f-0b267a7fe4fa
					- ((63679853-975f-4456-b131-53731a001078))
					- `removeChild()`
					  collapsed:: true
						- How to remove an element without specifying it's parent element
						  id:: 63430fd1-9771-4a61-9095-091e4cb7c952
							- ```javascript
							  let elem = document.getElementById('dummy');
							  elem.parentNode.removeChild(elem);
							  ```
							- Related: [((63430fd1-9771-4a61-9095-091e4cb7c952))](((63431477-5948-4b94-8790-2179c4b7a5fa)))
						- Removing all `X` elements
						  id:: 63431477-5948-4b94-8790-2179c4b7a5fa
							- ```javascript
							  // basically loop for the number of elements that exist, and then use querySelector to select the first questionCard detected each time on the page, then parentNode.removeChild it
							  
							  
							  for (var i = 0; i < importantThings.length; i++) {
							    let li = document.querySelector('li');
							    li.parentNode.removeChild(li);
							  ```
							- Related: ((63430fd1-9771-4a61-9095-091e4cb7c952))
				- By source
					- Others'
						- Useful snippets
						  https://github.com/Chalarangelo/30-seconds-of-code
					- Coding test answers
						- [Coding1](https://www.reddit.com/r/javascript/comments/3f7rx5/been_interviewing_with_a_lot_of_tech_startups_as/)
						  id:: 629ccb26-e681-4b75-8aac-44d41708e661
						  collapsed:: true
							- The first few the employer stole from You Can't JavaScript Under Pressure :)
							- Write a function that takes an integer and returns it doubled
							  ```javascript
							  function doubleInteger(i) {
							      //your code here
							      
							  }
							  ```
							- Write a function that takes a number and returns true if it's even and false if not
							  ```javascript
							  function isNumberEven(i) {
							      // i will be an integer. Return true if it's even, and false if it isn't.
							  }
							  ```
							- Write a function that returns a file extension
							  ```javascript
							  function getFileExtension(i) {
							      
							      // i will be a string, but it may not have a file extension.
							      // return the file extension (with no period) if it has one, otherwise false
							      
							  }
							  ```
							- What will be printed to the console? Why?
							  ```javascript
							  (function() {
							     var a = b = 5;
							  })();
							  console.log(b);
							  ```
							- Define a repeatify function on the String object. The function accepts an integer that specifies how many times the string has to be repeated. The function returns the string repeated the number of times specified.
							- For example:
							  ```javascript
							  console.log('hello'.repeatify(3));
							  //Should print hellohellohello.
							  ```
							- What will log out here?
							  ```javascript
							  function test() {
							     console.log(a); 
							     console.log(foo());
							      
							     var a = 1;
							     function foo() {
							        return 2;
							     }
							  }
							  test();
							  ```
							- What will log out here
							  var fullname = 'John Doe';
							  var obj = {
							     fullname: 'Colin Ihrig',
							     prop: {
							        fullname: 'Aurelio De Rosa',
							        getFullname: function() {
							           return this.fullname;
							        }
							     }
							  };
							  
							  console.log(obj.prop.getFullname()); 
							   
							  var test = obj.prop.getFullname; 
							   
							  console.log(test());
							- Fix the previous question’s issue so that the last console.log() prints Aurelio De Rosa.
							- The following recursive code will cause a stack overflow if the array list is too large. How can you fix this and still retain the recursive pattern?
							  var list = readHugeList();
							  
							  var nextListItem = function() {
							      var item = list.pop();
							  
							      if (item) {
							          // process the list item...
							          nextListItem();
							      }
							  };
							- What will alert out here
							  var a = 'value';
							  
							  (function() {
							    alert(a); 
							    var a = 'value2';
							  })();
							- The following code will output "my name is rex, Woof!" and then "my name is, Woof!" one second later, fix it so prints correctly the second time
							  var Dog = function (name) {
							    this.name = name;
							  };
							  
							  Dog.prototype.bark = function () {
							    console.log('my name is '+ this.name + ', Woof!');
							  }
							  
							  var rex = new Dog('rex');
							  
							  rex.bark();
							  
							  setTimeout(rex.bark, 1000);
							- The following code outputs 100, a hundred times, fix it so it outputs every number with a 100ms delay between each
							  for (var i = 0; i < 100; ++i) {
							    setTimeout(function() {
							      console.log(i);
							    }, 100);
							  }
							- The following code is outputting the array but it's filled with every number, we just want the even numbers, what's gone wrong?
							  var evenNumbers = []
							  
							  var findEvenNumbers = function (i) {
							    if (i % 2 === 0)
							      console.log(i, 'is an even number, adding to array!');
							      evenNumbers.push(i);
							  }
							  
							  for (var i = 0; i < 10; i++) {
							    findEvenNumbers(i);
							  }
							  
							  console.log(evenNumbers);
							  //outputs:
							  //0 "is an even number, adding to array!"
							  //2 "is an even number, adding to array!"
							  //4 "is an even number, adding to array!"
							  //6 "is an even number, adding to array!"
							  //8 "is an even number, adding to array!"
							  //[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
							- The following is outputting 0, but if 42 = 16 and 22 = 4 then the result should be 12
							  var square = function (number) {
							    result = number * number;
							    return result;
							  }
							  
							  result = square(4);
							  result2 = square(2);
							  difference = result - result2;
							  
							  console.log(difference);
							- Write a function that when passed an array of numbers it gives you the max difference between the largest and smallest number ONLY if the small number is in front of the large number, not behind it, so for example: [3,4,8,1] = 5, notice how the biggest difference is between 8 and 1, but because the 1 is after the 8 in the array it shouldn't count, so really the biggest gap is the 3 and the 8.
							- fizzbuzz (lol)
							- I was presented with a html element with a border, and asked to animate it left to right full width of browser
							- I was presented with another html box and asked to centre it both horizontally and vertically
			- ((63721cd2-b29c-49d6-8cdc-e568df1dff6a))
			- ((6367b609-cc62-4567-92f9-93038f30fdd4))
		- Related:
			- ((6364c41b-0024-4b36-a6e3-adc75e044ac8))
			- [[CodeWars - JavaScript]]
	- ## My Notes
		- Modern Node.js patterns
		  collapsed:: true
			- Meta
				- Node has built in test support now: looks like I can drop jest!
				- Node has built in watch support now: looks like I can drop nodemon!
			- Module system
			  logseq.order-list-type:: number
			  collapsed:: true
				- ES modules imports
				  collapsed:: true
					- ```js
					  // math.js
					  export function add(a, b) {
					    return a + b;
					  }
					  
					  // app.js
					  import { add } from './math.js';
					  import { readFile } from 'node:fs/promises';  // Modern `node:` prefix
					  import { createServer } from 'node:http';
					  
					  console.log(add(2, 3));
					  ```
				- Top-level `await`
				  collapsed:: true
					- No more wrapping your entire application in an async function just to use await at the module level:
					- ```js
					  // app.js - Clean initialization without wrapper functions
					  import { readFile } from 'node:fs/promises';
					  
					  const config = JSON.parse(await readFile('config.json', 'utf8'));
					  const server = createServer(/* ... */);
					  
					  console.log('App started with config:', config.appName);
					  ```
					- This eliminates the common pattern of immediately-invoked async function expressions (IIFE) that we used to see everywhere. Your code becomes more linear and easier to reason about.
			- Built-in web APIs
			  logseq.order-list-type:: number
			  collapsed:: true
				- Fetch API included
				  collapsed:: true
					- ```js
					  const response = await fetch('https://api.example.com/data');
					  const data = await response.json();
					  
					  // You get sophisticated timeout and cancellation support built-in:
					  async function fetchData(url) {
					    try {
					      const response = await fetch(url, {
					        signal: AbortSignal.timeout(5000) // Built-in timeout support
					      });
					  
					      if (!response.ok) {
					        throw new Error(`HTTP ${response.status}: ${response.statusText}`);
					      }
					  
					      return await response.json();
					    } catch (error) {
					      if (error.name === 'TimeoutError') {
					        throw new Error('Request timed out');
					      }
					      throw error;
					    }
					  }
					  ```
					- The `AbortSignal.timeout()` method is particularly elegant—it creates a signal that automatically aborts after the specified time.
				- AbortController: Graceful Operation Cancellation
				  collapsed:: true
					- Modern applications need to handle cancellation gracefully, whether it’s user-initiated or due to timeouts. AbortController provides a standardized way to cancel operations:
					- ```js
					  // Cancel long-running operations cleanly
					  const controller = new AbortController();
					  
					  // Set up automatic cancellation
					  setTimeout(() => controller.abort(), 10000);
					  
					  try {
					    const data = await fetch('https://slow-api.com/data', {
					      signal: controller.signal
					    });
					    console.log('Data received:', data);
					  } catch (error) {
					    if (error.name === 'AbortError') {
					      console.log('Request was cancelled - this is expected behavior');
					    } else {
					      console.error('Unexpected error:', error);
					    }
					  }
					  ```
					- This pattern works across many Node.js APIs, not just fetch. You can use the same AbortController with file operations, database queries, and any async operation that supports cancellation.
				-
			- Built-in test runner
			  logseq.order-list-type:: number
			  collapsed:: true
				- ```js
				  // test/math.test.js
				  import { test, describe } from 'node:test';
				  import assert from 'node:assert';
				  import { add, multiply } from '../math.js';
				  
				  describe('Math functions', () => {
				    test('adds numbers correctly', () => {
				      assert.strictEqual(add(2, 3), 5);
				    });
				  
				    test('handles async operations', async () => {
				      const result = await multiply(2, 3);
				      assert.strictEqual(result, 6);
				    });
				  
				    test('throws on invalid input', () => {
				      assert.throws(() => add('a', 'b'), /Invalid input/);
				    });
				  });
				  ```
				- How to use with Node.js
				  collapsed:: true
					- ```bash
					  # Run all tests with built-in runner
					  node --test
					  
					  # Watch mode for development
					  node --test --watch
					  
					  # Coverage reporting (Node.js 20+)
					  node --test --experimental-test-coverage
					  ```
			- Sophisticated asynchronous patterns
			  logseq.order-list-type:: number
			  collapsed:: true
				- Async/Await with Enhanced Error Handling and parallel execution
				  collapsed:: true
					- ```js
					  import { readFile, writeFile } from 'node:fs/promises';
					  
					  async function processData() {
					    try {
					      // Parallel execution of independent operations
					      const [config, userData] = await Promise.all([
					        readFile('config.json', 'utf8'),
					        fetch('/api/user').then(r => r.json())
					      ]);
					  
					      const processed = processUserData(userData, JSON.parse(config));
					      await writeFile('output.json', JSON.stringify(processed, null, 2));
					  
					      return processed;
					    } catch (error) {
					      // Structured error logging with context
					      console.error('Processing failed:', {
					        error: error.message,
					        stack: error.stack,
					        timestamp: new Date().toISOString()
					      });
					      throw error;
					    }
					  }
					  ```
					- The Promise.all() ensures that independent operations run concurrently, while the try/catch provides a single point for error handling with rich context.
				- Modern Event Handling with AsyncIterators
				  collapsed:: true
					- For handling streams of events
					  collapsed:: true
						- ```js
						  import { EventEmitter, once } from 'node:events';
						  
						  class DataProcessor extends EventEmitter {
						    async *processStream() {
						      for (let i = 0; i < 10; i++) {
						        this.emit('data', `chunk-${i}`);
						        yield `processed-${i}`;
						        // Simulate async processing time
						        await new Promise(resolve => setTimeout(resolve, 100));
						      }
						      this.emit('end');
						    }
						  }
						  
						  // Consume events as an async iterator
						  const processor = new DataProcessor();
						  for await (const result of processor.processStream()) {
						    console.log('Processed:', result);
						  }
						  ```
			- Advanced Streams with Web Standards Integration
			  logseq.order-list-type:: number
			  collapsed:: true
				- Modern Stream Processing
				  collapsed:: true
					- ```js
					  import { Readable, Transform } from 'node:stream';
					  import { pipeline } from 'node:stream/promises';
					  import { createReadStream, createWriteStream } from 'node:fs';
					  
					  // Create transform streams with clean, focused logic
					  const upperCaseTransform = new Transform({
					    objectMode: true,
					    transform(chunk, encoding, callback) {
					      this.push(chunk.toString().toUpperCase());
					      callback();
					    }
					  });
					  
					  // Process files with robust error handling
					  async function processFile(inputFile, outputFile) {
					    try {
					      await pipeline(
					        createReadStream(inputFile),
					        upperCaseTransform,
					        createWriteStream(outputFile)
					      );
					      console.log('File processed successfully');
					    } catch (error) {
					      console.error('Pipeline failed:', error);
					      throw error;
					    }
					  }
					  ```
					- The pipeline function with promises provides automatic cleanup and error handling, eliminating many of the traditional pain points with stream processing.
				- Web Streams Interoperability
				  collapsed:: true
					- ```js
					  // Create a Web Stream (compatible with browsers)
					  const webReadable = new ReadableStream({
					    start(controller) {
					      controller.enqueue('Hello ');
					      controller.enqueue('World!');
					      controller.close();
					    }
					  });
					  
					  // Convert between Web Streams and Node.js streams
					  const nodeStream = Readable.fromWeb(webReadable);
					  const backToWeb = Readable.toWeb(nodeStream);
					  ```
			- Worker Threads: True Parallelism for CPU-Intensive Tasks
			  logseq.order-list-type:: number
			  collapsed:: true
				- JavaScript’s single-threaded nature isn’t always ideal for CPU-intensive work. Worker threads provide a way to leverage multiple cores effectively while maintaining the simplicity of JavaScript.
				- Background Processing Without Blocking
				  collapsed:: true
					- Worker threads are perfect for computationally expensive tasks that would otherwise block the main event loop:
					- ```js
					  // worker.js - Isolated computation environment
					  import { parentPort, workerData } from 'node:worker_threads';
					  
					  function fibonacci(n) {
					    if (n < 2) return n;
					    return fibonacci(n - 1) + fibonacci(n - 2);
					  }
					  
					  const result = fibonacci(workerData.number);
					  parentPort.postMessage(result);
					  ```
				- The main application can delegate heavy computations without blocking other operations:
				  collapsed:: true
					- ```js
					  // main.js - Non-blocking delegation
					  import { Worker } from 'node:worker_threads';
					  import { fileURLToPath } from 'node:url';
					  
					  async function calculateFibonacci(number) {
					    return new Promise((resolve, reject) => {
					      const worker = new Worker(
					        fileURLToPath(new URL('./worker.js', import.meta.url)),
					        { workerData: { number } }
					      );
					  
					      worker.on('message', resolve);
					      worker.on('error', reject);
					      worker.on('exit', (code) => {
					        if (code !== 0) {
					          reject(new Error(`Worker stopped with exit code ${code}`));
					        }
					      });
					    });
					  }
					  
					  // Your main application remains responsive
					  console.log('Starting calculation...');
					  const result = await calculateFibonacci(40);
					  console.log('Fibonacci result:', result);
					  console.log('Application remained responsive throughout!');
					  ```
					- This pattern allows your application to utilize multiple CPU cores while keeping the familiar async/await programming model.
			- Enhanced Development Experience
			  logseq.order-list-type:: number
			  collapsed:: true
				- Watch Mode and Environment Management
				  collapsed:: true
					- Development workflow has been significantly streamlined with built-in watch mode and environment file support:
					- ```json
					  {
					    "name": "modern-node-app",
					    "type": "module",
					    "engines": {
					      "node": ">=20.0.0"
					    },
					    "scripts": {
					      "dev": "node --watch --env-file=.env app.js",
					      "test": "node --test --watch",
					      "start": "node app.js"
					    }
					  }
					  ```
					- The --watch flag eliminates the need for nodemon, while --env-file removes the dependency on dotenv. Your development environment becomes simpler and faster:
					- ```js
					  // .env file automatically loaded with --env-file
					  // DATABASE_URL=postgres://localhost:5432/mydb
					  // API_KEY=secret123
					  
					  // app.js - Environment variables available immediately
					  console.log('Connecting to:', process.env.DATABASE_URL);
					  console.log('API Key loaded:', process.env.API_KEY ? 'Yes' : 'No');
					  ```
			- Modern Security and Performance Monitoring
			  logseq.order-list-type:: number
			  collapsed:: true
				- Permission Model for Enhanced Security
				  collapsed:: true
					- The experimental permission model allows you to restrict what your application can access, following the principle of least privilege:
					- ```bash
					  # Run with restricted file system access
					  node --experimental-permission --allow-fs-read=./data --allow-fs-write=./logs app.js
					  
					  # Network restrictions 
					  node --experimental-permission --allow-net=api.example.com app.js
					  # Above allow-net feature not avaiable yet, PR merged in node.js repo, will be available in future release
					  ```
					- This is particularly valuable for applications that process untrusted code or need to demonstrate security compliance.
				- Built-in Performance Monitoring
				  collapsed:: true
					- Performance monitoring is now built into the platform, eliminating the need for external APM tools for basic monitoring:
					- ```js
					  import { PerformanceObserver, performance } from 'node:perf_hooks';
					  
					  // Set up automatic performance monitoring
					  const obs = new PerformanceObserver((list) => {
					    for (const entry of list.getEntries()) {
					      if (entry.duration > 100) { // Log slow operations
					        console.log(`Slow operation detected: ${entry.name} took ${entry.duration}ms`);
					      }
					    }
					  });
					  obs.observe({ entryTypes: ['function', 'http', 'dns'] });
					  
					  // Instrument your own operations
					  async function processLargeDataset(data) {
					    performance.mark('processing-start');
					  
					    const result = await heavyProcessing(data);
					  
					    performance.mark('processing-end');
					    performance.measure('data-processing', 'processing-start', 'processing-end');
					  
					    return result;
					  }
					  ```
					- This provides visibility into application performance without external dependencies, helping you identify bottlenecks early in development.
				-
			- Single Executable Applications for distribution and deployment
			  logseq.order-list-type:: number
			  collapsed:: true
				- ```sh
				  # Create a self-contained executable
				  node --experimental-sea-config sea-config.json
				  ```
				- The configuration file defines how your application gets bundled:
				- ```json
				  {
				    "main": "app.js",
				    "output": "my-app-bundle.blob",
				    "disableExperimentalSEAWarning": true
				  }
				  ```
				- This is particularly valuable for CLI tools, desktop applications, or any scenario where you want to distribute your application without requiring users to install Node.js separately.
			- Modern Error Handling and Diagnostics
			  logseq.order-list-type:: number
			  collapsed:: true
				- Structured Error Handling
				  collapsed:: true
					- Modern applications benefit from structured, contextual error handling that provides better debugging information:
					- ```js
					  class AppError extends Error {
					    constructor(message, code, statusCode = 500, context = {}) {
					      super(message);
					      this.name = 'AppError';
					      this.code = code;
					      this.statusCode = statusCode;
					      this.context = context;
					      this.timestamp = new Date().toISOString();
					    }
					  
					    toJSON() {
					      return {
					        name: this.name,
					        message: this.message,
					        code: this.code,
					        statusCode: this.statusCode,
					        context: this.context,
					        timestamp: this.timestamp,
					        stack: this.stack
					      };
					    }
					  }
					  
					  // Usage with rich context
					  throw new AppError(
					    'Database connection failed',
					    'DB_CONNECTION_ERROR',
					    503,
					    { host: 'localhost', port: 5432, retryAttempt: 3 }
					  );
					  ```
				- Advanced Diagnostics
				  collapsed:: true
					- Node.js includes sophisticated diagnostic capabilities that help you understand what’s happening inside your application:
					- ```js
					  import diagnostics_channel from 'node:diagnostics_channel';
					  
					  // Create custom diagnostic channels
					  const dbChannel = diagnostics_channel.channel('app:database');
					  const httpChannel = diagnostics_channel.channel('app:http');
					  
					  // Subscribe to diagnostic events
					  dbChannel.subscribe((message) => {
					    console.log('Database operation:', {
					      operation: message.operation,
					      duration: message.duration,
					      query: message.query
					    });
					  });
					  
					  // Publish diagnostic information
					  async function queryDatabase(sql, params) {
					    const start = performance.now();
					  
					    try {
					      const result = await db.query(sql, params);
					  
					      dbChannel.publish({
					        operation: 'query',
					        sql,
					        params,
					        duration: performance.now() - start,
					        success: true
					      });
					  
					      return result;
					    } catch (error) {
					      dbChannel.publish({
					        operation: 'query',
					        sql,
					        params,
					        duration: performance.now() - start,
					        success: false,
					        error: error.message
					      });
					      throw error;
					    }
					  }
					  ```
			- Modern Package Management and Module Resolution
			  logseq.order-list-type:: number
			  collapsed:: true
				- Package management and module resolution have become more sophisticated, with better support for monorepos, internal packages, and flexible module resolution.
				- Import Maps and Internal Package Resolution
				  collapsed:: true
					- Modern Node.js supports import maps, allowing you to create clean internal module references:
					- ```json
					  {
					    "imports": {
					      "#config": "./src/config/index.js",
					      "#utils/*": "./src/utils/*.js",
					      "#db": "./src/database/connection.js"
					    }
					  }
					  ```
					- This creates a clean, stable interface for internal modules:
					- ```js
					  // Clean internal imports that don't break when you reorganize
					  import config from '#config';
					  import { logger, validator } from '#utils/common';
					  import db from '#db';
					  ```
					- These internal imports make refactoring easier and provide a clear distinction between internal and external dependencies.
				- Dynamic Imports for Flexible Loading
				  collapsed:: true
					- Dynamic imports enable sophisticated loading patterns, including conditional loading and code splitting:
					- ```js
					  // Load features based on configuration or environment
					  async function loadDatabaseAdapter() {
					    const dbType = process.env.DATABASE_TYPE || 'sqlite';
					  
					    try {
					      const adapter = await import(`#db/adapters/${dbType}`);
					      return adapter.default;
					    } catch (error) {
					      console.warn(`Database adapter ${dbType} not available, falling back to sqlite`);
					      const fallback = await import('#db/adapters/sqlite');
					      return fallback.default;
					    }
					  }
					  
					  // Conditional feature loading
					  async function loadOptionalFeatures() {
					    const features = [];
					  
					    if (process.env.ENABLE_ANALYTICS === 'true') {
					      const analytics = await import('#features/analytics');
					      features.push(analytics.default);
					    }
					  
					    if (process.env.ENABLE_MONITORING === 'true') {
					      const monitoring = await import('#features/monitoring');
					      features.push(monitoring.default);
					    }
					  
					    return features;
					  }
					  ```
			- {Archive}
			  collapsed:: true
				- [Modern Node.js Patterns | Hacker News](https://news.ycombinator.com/item?id=44778936)
				- logseq.order-list-type:: number
		- [How can I group and count values in a JavaScript array?](https://www.30secondsofcode.org/js/s/count-grouped-elements/)
		  collapsed:: true
			- Counting occurrences
				- ```js
				  const frequencies = arr =>
				    arr.reduce((a, v) => {
				      a[v] = (a[v] ?? 0) + 1;
				      return a;
				    }, {});
				  
				  frequencies(['a', 'b', 'a', 'c', 'a', 'a', 'b']);
				  // { a: 4, b: 2, c: 1 }
				  frequencies([...'ball']);
				  // { b: 1, a: 1, l: 2 }
				  ```
			- Group elements of an array based on a function
				- ```js
				  const countBy = (arr, fn) =>
				    arr
				      .map(typeof fn === 'function' ? fn : val => val[fn])
				      .reduce((acc, val) => {
				        acc[val] = (acc[val] || 0) + 1;
				        return acc;
				      }, {});
				  
				  countBy([6.1, 4.2, 6.3], Math.floor);
				  // {4: 1, 6: 2}
				  countBy(['one', 'two', 'three'], 'length');
				  // {3: 2, 5: 1}
				  countBy([{ count: 5 }, { count: 10 }, { count: 5 }], x => x.count);
				  // {5: 2, 10: 1}
				  ```
			- Using a `Map` instead of an object
				- Both of the previous examples use objects to store the frequencies of the values. However, you can also use a Map to store the frequencies. This can be useful if you need to keep the insertion order of the keys or if you need to iterate over the keys in the order they were inserted. It's also more efficient when you need to delete keys or check for the existence of a key.
				- ```js
				  const frequenciesMap = arr =>
				    arr.reduce((a, v) => a.set(v, (a.get(v) ?? 0) + 1), new Map());
				  
				  frequenciesMap(['a', 'b', 'a', 'c', 'a', 'a', 'b']);
				  // Map(3) { 'a' => 4, 'b' => 2, 'c' => 1 }
				  
				  const countByMap = (arr, fn) =>
				    arr
				      .map(typeof fn === 'function' ? fn : val => val[fn])
				      .reduce((acc, val) => {
				        acc.set(val, (acc.get(val) || 0) + 1);
				        return acc;
				      }, new Map());
				  
				  countByMap([6.1, 4.2, 6.3], Math.floor);
				  // Map(2) { 6 => 2, 4 => 1 }
				  countByMap(['one', 'two', 'three'], 'length');
				  // Map(2) { 3 => 2, 5 => 1 }
				  countByMap([{ count: 5 }, { count: 10 }, { count: 5 }], x => x.count);
				  // Map(2) { 5 => 2, 10 => 1 }
				  ```
			- Implement a frequency map data structure
				- When dealing with data that changes often, you may need to recalculate frequencies as needed. This can become tedious and inefficient, especially if you only need to keep track of the frequencies and have no need for the original array.
				- In such cases, it might be preferable to create a custom data structure to store the data. This data structure will be able to keep track of the frequencies of the values it contains and update them as needed.
				- Moreover, you may want to be able to check the frequency of any value, even if it doesn't exist in the data structure. This also comes in handy if you want to easily increment or decrement the frequency of a value. Let's take a look at how you can implement such a data structure:
				- ```js
				  class FrequencyMap extends Map {
				    constructor(iterable) {
				      super();
				      iterable.forEach(value => this.increment(value));
				    }
				  
				    get(value) {
				      return super.get(value) ?? 0;
				    }
				  
				    has(value) {
				      return super.get(value) > 0;
				    }
				  
				    increment(value) {
				      super.set(value, this.get(value) + 1);
				      return this;
				    }
				  
				    decrement(value) {
				      super.set(value, Math.max(this.get(value) - 1, 0));
				      return this;
				    }
				  
				    toSortedArray(ascending = true) {
				      if (ascending)
				        return [...this].sort((a, b) => a[1] - b[1]).map(v => v[0]);
				      else return [...this].sort((a, b) => b[1] - (1)[1]).map(v => v[0]);
				    }
				  }
				  
				  const fMap = new FrequencyMap(['a', 'b', 'c', 'a', 'a', 'b']);
				  
				  fMap.decrement('c');
				  fMap.increment('d');
				  
				  console.log(fMap.toSortedArray(false)); // [ 'a', 'b' , 'd' ]
				  ```
		- Common RegExp
		  collapsed:: true
			- ### Exact string match
				- Use the `^` and `$` anchors to match the start and end of the string, respectively.
				- Add the string you want to match in-between the two anchors.
				- ```js
				  const regexp = /^abc$/;
				  // Where 'abc' is the exact string you want to match
				  ```
			- ### Match empty string
				- Use the `^` and `$` anchors to match the start and end of the string, respectively.
				- Do not add any characters in-between to match an empty string.
				- ```js
				  const regexp = /^$/;
				  ```
			- ### Match whitespace sequences
				- Use the `\s` meta-sequence to match any whitespace character, including spaces, tabs, newlines, etc.
				- Use the `+` quantifier to match one or more occurrences of the previous character.
				- Add the global flag (`g`) to match all occurrences of the pattern in the string.
				- ```js
				  const regexp = /\s+/g;
				  ```
			- ### Match line breaks
				- Depending on the environment, line breaks can be represented in different ways.
				- Use the `\r` character to match carriage returns, the `\n` character to match newlines, and the `\r\n` sequence to match carriage returns followed by newlines.
				- Add the global (`g`) and multiline (`m`) flags to match all occurrences of the pattern in the string.
				- ```js
				  const regexp = /\r|\n|\r\n/gm;
				  ```
			- ### Match non-word characters
				- Use negation (`^`) to match any character that is not a word character (`\w`) or a whitespace character (`\s`).
				- Add the global flag (`g`) to match all occurrences of the pattern in the string.
				- Add the ignore case flag (`i`) to match both uppercase and lowercase characters.
				- ```js
				  const regexp = /[^\w\s]/gi;
				  ```
			- ### Match alphanumeric, dashes and hyphens
				- Use the `^` and `$` anchors to match the start and end of the string, respectively.
				- Use the `a-zA-Z0-9-` pattern to match any alphanumeric character, dashes and hyphens.
				- Use the `+` quantifier to match one or more occurrences of the previous character.
				- Particularly useful when matching URL slugs.
				- ```js
				  const regexp = /^[a-zA-Z0-9-_]+$/;
				  ```
			- ### Match letters and whitespaces
				- Use the `^` and `$` anchors to match the start and end of the string, respectively.
				- Use the `a-zA-Z\s` pattern to match any letter and whitespace character.
				- Use the `+` quantifier to match one or more occurrences of the previous pattern.
				- ```js
				  const regexp = /^[A-Za-z\s]+$/;
				  ```
			- ### Pattern not included
				- Use the `^` and `$` anchors to match the start and end of the string, respectively.
				- Use a negative lookahead (`?!`) to match any character that is not followed by the pattern you want to exclude.
				- Add the global flag (`g`) to match all occurrences of the pattern in the string.
				- To ensure more than one pattern is not included, use the `|` character to separate them.
				- ```js
				  const regexp = /^((?!(abc|bcd)).)*$/;
				  ```
			- ### Text inside brackets
				- Use the `\(` and `\)` characters to match the opening and closing brackets, respectively.
				- Use a capturing group between the two and exclude the closing parenthesis character.
				- Use the `+` quantifier to match one or more characters, as needed.
				- Add the global flag (`g`) to match all occurrences of the pattern in the string.
				- Replace `\(` and `\)` with `\[` and `\]` to match square brackets and with `\{` and `\}` to match curly brackets.
				- ```js
				  const regexp = /\(([^)]+)\)/g;
				  ```
			- ### Validate GUID/UUID
				- Use the `^` and `$` anchors to match the start and end of the string, respectively.
				- Validate each segment of the GUID/UUID separately using numeric character ranges and quantifiers.
				- ```js
				  const regexp = /^(0?[1-9]|[12][0-9]|3[01])[\/\-](0?[1-9]|1[012])[\/\-]\d{4}$/;
				  ```
			- ###  Validate date format (DD/MM/YYYY)
				- Use the `^` and `$` anchors to match the start and end of the string, respectively.
				- Validate each segment of the date separately using numeric character ranges and quantifiers.
				- Alter the order of the segments and separators to match different formats.
				- ```js
				  const regexp = /^(0?[1-9]|[12][0-9]|3[01])[\/\-](0?[1-9]|1[012])[\/\-]\d{4}$/;
				  ```
			- ### Chunk string into n-size chunks
				- Use the `.{1,n}` quantifier to match any character between `1` and `n` times.
				- Add the global flag (`g`) to match all occurrences of the pattern in the string.
				- ```js
				  const regexp = /.{1,2}/g;
				  ```
		- Typechecking JavaScript arrays with `Array.isArray`
		  collapsed:: true
			- To determine if a JavaScript object is an array, you can either use Array.isArray()
			- ```js
			  var iframeEl = document.createElement('iframe');
			  document.body.appendChild(iframeEl);
			  iframeArray = window.frames[window.frames.length - 1].Array;
			  
			  var array1 = new Array(1,1,1,1);
			  var array2 = new iframeArray(1,1,1,1);
			  
			  console.log(array1 instanceof Array);   
			  console.log(Array.isArray(array1));     
			  
			  console.log(array2 instanceof Array);   
			  console.log(Array.isArray(array2));     
			  ```
				- As illustrated in the previous example, `instanceof` breaks when working with an `iframe`. However, [`Array.isArray()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray) produces the correct result regardless of the way the array was instantiated.
		- Checking if a value is blank using `isBlank` custom method
		  collapsed:: true
			- ```js
			  const isFalsy = value => !value;
			  const isWhitespaceString = value =>
			    typeof value === 'string' && /^\s*$/.test(value);
			  const isEmptyCollection = value =>
			    (Array.isArray(value) || value === Object(value)) &&
			    !Object.keys(value).length;
			  const isInvalidDate = value =>
			    value instanceof Date && Number.isNaN(value.getTime());
			  const isEmptySet = value => value instanceof Set && value.size === 0;
			  const isEmptyMap = value => value instanceof Map && value.size === 0;
			  
			  const isBlank = value => {
			    if (isFalsy(value)) return true;
			    if (isWhitespaceString(value)) return true;
			    if (isEmptyCollection(value)) return true;
			    if (isInvalidDate(value)) return true;
			    if (isEmptySet(value)) return true;
			    if (isEmptyMap(value)) return true;
			    return false;
			  };
			  
			  isBlank(null); 
			  isBlank(undefined); 
			  isBlank(0); 
			  isBlank(false); 
			  isBlank(''); 
			  isBlank(' \r\n '); 
			  isBlank(NaN); 
			  isBlank([]); 
			  isBlank({}); 
			  isBlank(new Date('hello')); 
			  isBlank(new Set()); 
			  isBlank(new Map()); 
			  ```
				- Why
					- First of all, any falsy values should be considered blank. These include `null`, `undefined`, `0`, `false`, `''`, and `NaN`.
						- ```js
						  const isFalsy = value => !value;
						  
						  isFalsy(null); 
						  isFalsy(undefined); 
						  isFalsy(0); 
						  isFalsy(false); 
						  isFalsy(''); 
						  isFalsy(NaN); 
						  ```
					- Secondly, empty arrays and objects should also be considered blank. This can be easily checked by using [`Object.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys) for both types of values.
						- ```js
						  const isEmptyCollection = value =>
						    (Array.isArray(value) || value === Object(value)) &&
						    !Object.keys(value).length;
						  
						  isEmptyCollection([]); 
						  isEmptyCollection({}); 
						  ```
					- In addition to the empty string (`''`), whitespace-only strings should be considered blank, too. A regular expression can be used to check for this.
						- ```js
						  const isWhitespaceString = value =>
						    typeof value === 'string' && /^\s*$/.test(value);
						  
						  isWhitespaceString(' '); 
						  isWhitespaceString('\t\n\r'); 
						  ```
					- Finally, we can check for some commonly-used built-in objects. Invalid [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) instances, as well as empty [`Set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) and [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) instances should all be considered blank.
						- ```js
						  const isInvalidDate = value =>
						    value instanceof Date && Number.isNaN(value.getTime());
						  const isEmptySet = value => value instanceof Set && value.size === 0;
						  const isEmptyMap = value => value instanceof Map && value.size === 0;
						  
						  isInvalidDate(new Date('hello')); 
						  isEmptySet(new Set()); 
						  isEmptyMap(new Map()); 
						  ```
		- Replacing If Statements with ternary operators when assigning an object
		  collapsed:: true
			- Improved version
				- ```js
				  object = {
				    property1: 1
				    property2: property1 == property3 ? "hi" : "bye"
				    property3: 3
				  };
				  ```
			- Original
				- ```js
				  if (property1 !== property3) {
				    object = {
				      property1: 1
				      property2: "hi"
				    	property3: 3
				    };
				  } else {
				    object = {
				      property1: 1
				      property2: "bye"
				    	property3: 1
				    };
				  }
				  ```
		- [Animations on the Web](https://animations.dev/)
		  collapsed:: true
		- Sleep timer function
		  collapsed:: true
			- ```typescript
			  const oneSecond = 1000;
			  await new Promise((resolve) => setTimeout(resolve, oneSecond));
			  ```
		- ### Object-Oriented Programming
		  collapsed:: true
			- `_` prefix used in addition to `private` variables
			  id:: 68d3eb85-cbd4-4105-b72d-07d2c0202607
			  collapsed:: true
				- This is a convention used as a visual clue in TypeScript codebases
				- ### Why use   `_`   prefix if you already have   `private` ?
					- **Visual clue:** In many codebases, the underscore is used to quickly distinguish private fields from public ones, improving readability especially in larger classes or when mixing public and private members.
					- **Historical and cross-language convention:** In languages without built-in privacy keywords (like early JavaScript or Python), `_` was the only way to denote private or internal fields. Many developers carry that style over into TypeScript.
					- **Backward compatibility and tooling:** Some IDEs and teams prefer `_` to easily identify private fields during development or for consistency with legacy code.
					- Some large projects and style guides allow or even enforce leading underscores in private names for extra clarity, especially when using accessors (getters/setters) to distinguish backing fields from public properties
						- Example
							- ```typescript
							  private _value: number;
							  
							  get value(): number {
							    return this._value;
							  }
							  
							  set value(newValue: number) {
							    this._value = newValue;
							  }
							  ```
			-
		- ## Assorted topics
		  collapsed:: true
			- ((f16a5715-3945-4df4-88e5-598969dec550)) in JavaScript
			  id:: 629ccb26-33a2-445c-859c-adeaa91e4f27
			  collapsed:: true
				- ((63fe5472-f72c-4a29-9067-7d7edc128d06)) features
				  id:: 67376787-8e8c-4977-974d-34b619380f7c
					- How to use `super()` in subclass constructor
					  collapsed:: true
						- ```typescript
						  class Animal {
						  	name: string;
						  	age: number;
						  
						  	constructor(name: string, age: number) {
						        this.name = name;
						        this.age = age;
						        console.log(`Animal constructor: ${this.name}, age ${this.age}`);
						  	}
						  
						  	move(distance: number) {
						  		console.log(`${this.name} moved ${distance}m.`);
						  	}
						  }
						  
						  class Dog extends Animal {
						  	breed: string;
						  
						  	constructor(name: string, age: number, breed: string) {
						        super(name, age); // Calls Animal's constructor with name and age
						        this.breed = breed;
						        console.log(`Dog constructor: breed ${this.breed}`);
						  	}
						  
						  	bark() {
						  		console.log(`${this.name} barks.`);
						  	}
						  }
						  
						  // Usage example:
						  const rover = new Dog("Rover", 5, "Golden Retriever");
						  rover.bark();             // Output: Rover barks.
						  rover.move(10);           // Output: Rover moved 10m.
						  ```
					- Implements and Extends
					  collapsed:: true
						- implements: A class can implements an interface, ensuring it contains all properties and methods from that interface. However, the class can also define additional properties or methods that are not present in the interface—this is entirely valid and supported.
							- ```ts
							  interface IAnimal {
							  	name: string;
							  }
							  
							  class Dog implements IAnimal {
							    name: string;
							    breed: string; // additional property not in IAnimal
							  
							    constructor(name: string, breed: string) {
							      this.name = name;
							      this.breed = breed;
							    }
							  }
							  ```
						- extends: A class uses extends only to inherit from another class (not interface). This copies all members from the base class into the derived class, so you can extend/override or add new members.
						- Interfaces use `extends`: Interfaces can use extends to inherit from other interfaces—this lets you compose multiple structures for type-checking. But classes don’t use extends for interfaces.
							- ```ts
							  interface IAnimal {
							  	name: string;
							  }
							  
							  interface IDog extends IAnimal {
							  	breed: string;
							  }
							  
							  class Dog implements IDog {
							    name: string;
							    breed: string;
							  
							    constructor(name: string, breed: string) {
							      this.name = name;
							      this.breed = breed;
							    }
							  }
							  ```
					- Protected vs private
					  collapsed:: true
						- In a TypeScript class, protected and private are access modifiers that control the visibility of class members (properties and methods):
						- `private`
						  Members marked as private are accessible only within the class where they are defined.
						  They cannot be accessed from outside the class or from any subclass (derived class).
						  This ensures encapsulation by hiding implementation details strictly within the containing class.
						- `protected`
						  Members marked as protected are accessible within the class where they are defined and in all subclasses ("derived" classes).
						  They cannot be accessed from outside the class hierarchy, but any class extending the base class can use them.
						- ```ts
						  class Base {
						  private onlyBaseVisible: number;
						  protected baseAndSubVisible: number;
						  
						  constructor() {
						  this.onlyBaseVisible = 1;
						  this.baseAndSubVisible = 2;
						  }
						  }
						  
						  class Sub extends Base {
						  constructor() {
						  super();
						  // this.onlyBaseVisible; // ❌ Error: private, not accessible
						  this.baseAndSubVisible; // ✅ OK: protected, accessible in subclass
						  }
						  }
						  
						  const test = new Sub();
						  // test.baseAndSubVisible; // ❌ Error: protected, not accessible outside the class or subclasses
						  ```
						- Modifier	Accessible in Class	Accessible in Subclasses	Accessible Outside
							- private	Yes	No	No
							  protected	Yes	Yes	No
						- Use private for information that should be strictly hidden within the class itself, and protected for details that subclasses are allowed to use, but still hidden from external code.
					- Factory methods
					  collapsed:: true
						- A factory method is a method (often static) that creates and returns instances of a class — acting as a centralized “factory” for building objects.
						- Instead of calling the class constructor directly with new, you call the factory method, which may:
							- Hide complex creation logic
							- Return a specific subclass or cached instance
							- Apply certain configuration
							- Improve code readability
						- Factory methods in classes
							- Constructors are quite relevant when using factory methods, as it allows you to copy local variables in your factory method into the class instance as properties
						- Using a class with a factory method (to create instances) and another method to remove instances
						  collapsed:: true
							- ```typescript
							  class ExampleClass {
							    value: string;
							    private disposed: boolean = false;
							  
							    private constructor(value: string) {
							     this.value = value;
							    }
							    
							      // Factory method
							    static create(value: string): ExampleClass {
							     return new ExampleClass(value);
							    }
							  
							    // Dispose method to cleanup the instance
							    dispose(): void {
							       if (!this.disposed) {
							         console.log(`Disposing instance with value: ${this.value}`);
							         // Perform any cleanup logic here
							  
							         // Mark as disposed
							         this.disposed = true;
							         // Optionally clear properties
							         this.value = '';
							     	 }
							    }
							  
							    // Static helper to clear an instance and set it to undefined
							    static clearInstance(instance: ExampleClass | undefined): undefined {
							      instance?.dispose(); // call dispose if instance exists
							      return undefined;    // clear reference
							    }
							  }
							  
							  // Usage example:
							  let obj = ExampleClass.create('hello');
							  obj = ExampleClass.clearInstance(obj); // obj is now undefined and disposed
							  ```
						- ```ts
						  class User {
						  constructor(
						  public username: string,
						  public role: string
						  ) {}
						  
						  // Factory method
						  static createAdmin(username: string): User {
						  return new User(username, "admin");
						  }
						  
						  static createGuest(): User {
						  return new User("Guest", "guest");
						  }
						  }
						  
						  // Using the factory methods:
						  const admin = User.createAdmin("Alice");
						  const guest = User.createGuest();
						  
						  console.log(admin); // User { username: 'Alice', role: 'admin' }
						  console.log(guest); // User { username: 'Guest', role: 'guest' }
						  ```
						- My example and utilisation
							- ```ts
							  class Tunnel {
							    connection: number | undefined;
							  
							    constructor(connection: number | undefined) {
							   	 this.connection = connection;
							    }
							  
							    static async connect(adb: Type1, options: Type2) {
							      const connecto = adb++;
							     	 return new Tunnel(connecto);
							    }
							  }
							  
							  let TUNNEL: Tunnel | undefined
							  
							  class Thingy {
							    static async start(adb: Type1, options: Type2) {
							      if (!TUNNEL) {
							        TUNNEL = await Tunnel.connect(adb, options)
							      }
							    }
							  }
							  ```
					- Using `this` or `ClassName` to prefix usage of static properties and methods [Perplexity](https://www.perplexity.ai/search/why-doesn-t-git-branch-d-have-fwJT3hVORlKt8ET4phXvMQ#70)
					- Abstract functions
						- `abstract consume(param1: String): T;`
							- You don't need to specify any function body
					- Constructor
					  collapsed:: true
						- Avoid async commands in a class constructor - this keeps classes instantiating quickly
							- Instead use factory method pattern dedicated to instantiating classes and run async operations inside it
						- Constructor can be used to handle parameters passed during class instantiation
						  collapsed:: true
							- ```typescript
							  class FetchWithProgress {
							    constructor(url: string) {
							    	// rest of implementation..
							    }
							  
							    function fetchServer() {
							      if (!cachedValue) {
							     		cachedValue = new FetchWithProgress(BIN)
							    }
							  }
							  ```
						- `constructor()` method
							- ```typescript
							  class User {
							    name: string;
							  
							    constructor() {
							      console.log("Constructor called!");
							      this.name = "Default User";
							    }
							  }
							  
							  const user = new User(); // "Constructor called!" is printed
							  ```
							- ```typescript
							  class User {
							    name: string;
							    age: number;
							  
							    constructor(name: string, age: number) {
							      this.name = name;
							      this.age = age;
							    }
							  }
							  
							  const user = new User("Alice", 25);
							  ```
						-
					- Property scoping
					  collapsed:: true
						- Need prefix `this.` for each use of a class property within the class
							- ```typescript
							  class Something {
							  process: Type1 | undefined;
							  
							  async start() { // instance method
							  this.process = await something2(); // ✅ Works
							  }
							  }
							  ```
						- Remember to prefix properties and methods with `static` you intend for class instances to always use the class values instead of the instance's
							- ```ts
							  class Something {
							  static process: Type1 | undefined;
							  
							  static async start() {
							  this.process = await something2(); // ✅ Works
							  }
							  }
							  ```
					- How to pass multiple arguments to a class, and run specific methods only if specific strings are passed
					  collapsed:: true
						- ```typescript
						  class TestClass {
						  promise: Promise<Uint8Array | File>;
						  
						  constructor(url: string | URL, type: 'buffer' | 'file') {
						  if (type === 'buffer') {
						  	this.promise = this.fetchBuffer(url);
						  } else if (type === 'file') {
						  	this.promise = this.fetchFile(url);
						  } else {
						  	throw new Error("Invalid type provided. Use 'buffer' or 'file' instead.");
						  }
						  }
						  
						  private async fetchBuffer(url: string | URL): Promise<Uint8Array> {
						  // rest of method
						  return buffer;
						  }
						  
						  private async fetchFile(url: string | URL): Promise<File> {
						  // rest of method
						  const file = new File([blob], "reverse.bin", { type: blob.type });
						  return file;
						  }
						  }
						  
						  // Example usage:
						  const bufferFetch = new TestClass('https://example.com/file.mp4', 'buffer');
						  const fileFetch = new TestClass('https://example.com/file.mp4', 'file');
						  ```
							- It can alternately be done with two variables but that then means you have to specify that one or the other can be undefined, because if that string isn't used as an argument then it'll be undefined
								- ```ts
								  promiseBuffer: Promise<Uint8Array>; // two variables used within the constructor
								  promiseFile: Promise<File>
								  
								  constructor(url: string | URL, type: 'buffer' | 'file') {
								  if (type === 'buffer') {
								  this.promiseBuffer = this.fetchBuffer(url);
								  } else if (type === 'file') {
								  this.promiseFile = this.fetchFile(url);
								  } else {
								  throw new Error("Invalid type provided. Use 'buffer' or 'file' instead.");
								  }
								  }
								  
								  // methods
								  ```
							- The typical pattern to call and cache these values:
								- ```ts
								  export let cachedBuffer: TestClass | undefined;
								  
								  export function fetchBuffer() {
								  if (!cachedBuffer) {
								  cachedBuffer = new TestClass(BIN, "buffer");
								  cachedBuffer.promise.catch(() => {
								  	cachedBuffer = undefined;
								  });
								  }
								  return cachedBuffer.promise;
								  }
								  
								  export let cachedFile: TestClass | undefined;
								  
								  export function fetchFile() {
								  // etc
								  }
								  ```
							- **Had to update my code to make it simpler and work:**
								- ```typescript
								  class TestClass {
								  promise: Promise<File>;
								  
								  public constructor(url: string | URL) {
								  this.promise = this.fetchFile(url);
								  }
								  
								  private async fetchFile(url: string | URL): Promise<File> {
								  // rest of method
								  const file = new File([blob], "reverse.bin", { type: blob.type });
								  return file;
								  }
								  }
								  
								  let cachedInstance: TestClass | undefined;
								  
								  export function fetchBinary() {
								  if (!cachedInstance) {
								  cachedInstance = new TestClass(BIN);
								  }
								  return cachedInstance.promise
								  }
								  
								  // To obtain a variable with a type of File instead of Promise<File:
								  const file = await fetchBinary();
								  
								  // e.g.
								  class OtherClass {
								  install = async() => {
								  const file = await fetchBinary();
								  // etc
								  }
								  ```
					- If in an abstract class you create a variable e.g. `tunnelForward = false` then to change that to `true` in a class that extends it you need to override it e.g. `override tunnelForward = true`
					- `#` prefix for class methods makes it truly private
					  collapsed:: true
						- In TypeScript (and modern JavaScript), a function, method, or property whose name is prefixed with # (such as #createVideoStream) is a private class member. This syntax is part of the ECMAScript standard: the # symbol makes the member truly private, so it can only be accessed from within that class and not from subclasses, external code, or even via bracket notation.
						- *# prefixed members are private: They are only accessible from within the class body that declares them; it's a runtime/private field, not just a TypeScript compile-time check.
						  Stronger than TypeScript's private: The `private` keyword in TypeScript is enforced only by the TypeScript compiler and not at runtime; in contrast, #-prefixed fields/methods are private at runtime as well.
						  Applies to methods too: You can use this with functions/methods (e.g., `async #createVideoStream() { ... }`), not just with properties.
						- ```typescript
						  class Example {
						  #privateMethod() {
						  console.log("This is private!");
						  }
						  
						  async callPrivate() {
						  await this.#privateMethod();
						  }
						  }
						  
						  const ex = new Example();
						  ex.callPrivate(); // OK
						  // ex.#privateMethod(); // Error: not accessible
						  ```
					- common prefixes and modifiers used in TypeScript class methods and properties
					- Here's how to create a static defaults property that inherits all class properties:
					  collapsed:: true
						- ```typescript
						  export class GOptionsLatest {
						  value?: SomethingOptionsInit;
						  testVar = 'hello';
						  
						  static defaults = new GOptionsLatest();
						  
						  static createConnection(adb: Adb, options: OptionsOne) {
						  if (tunnelForward) {
						   return true;
						  }
						  }
						  }
						  ```
						- Inherit all defaults and override specific properties:
							- ```typescript
							  const options = new GOptionsLatest({
							  ...GOptionsLatest.defaults,
							  testVar: 'custom value'  // Override only testVar, keep other defaults
							  });
							  ```
					- How to ensure that a class instance populates with all the default properties and methods of it's superclass (whilst still allowing them to be overridden)
					  collapsed:: true
						- Constructor with defaults
							- ```typescript
							  export class GOptionsLatest {
							  value?: SomethingOptionsInit;
							  testVar = 'hello';
							  
							  constructor(overrides: Partial<GOptionsLatest> = {}) {
							  Object.assign(this, overrides);
							  }
							  
							  static createConnection(adb: Adb, options: OptionsOne) {
							  if (tunnelForward) {
							   return true;
							  }
							  }
							  }
							  
							  // Usage
							  const options = new GOptionsLatest({
							  testVar: 'custom value'
							  });
							  ```
						- Use `Object.assign` to set properties on an instance right after creation
							- ```typescript
							  const instance2 = Object.assign(new MyClass(), { prop1: "custom value", prop2: 100, prop3: false });
							  console.log(instance2.describe());
							  ```
					- [Learning Resources]
						- ```typescript
						  constructor(base: ScOpti<T>) {
						  	super(base, base.value);
						  }
						  ```
							- constructor(...): This is the special method that's called when you create a new instance of a class.
							- base: ScOpti<T>: This specifies the constructor takes an argument named base, whose type is ScOpti<T>.
							- ScOpti is likely a generic class or interface, and T is a type parameter, so this allows the constructor to accept a base object of any type T.
							- super(...):
							- This calls the parent (superclass) constructor.
							- In TypeScript (and JavaScript ES6+), if your class extends another class, you must call super(...) in your constructor before accessing this.
							- Here, two arguments are passed: base and base.value.
							- The parent class is expected to have a constructor that matches this signature, e.g.:
							- ```typescript
							  constructor(base: ScOpti<T>, value: T) {}
							  ```
						- [Object-oriented JavaScript for beginners - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)
						- [JavaScript OOP in 4 steps](http://exploringjs.com/impatient-js/ch_single-objects.html)
					- Related: ((629ccb26-1eab-4686-a7b8-f9433a871440)) : ((68fcecf0-9d11-49c8-87a5-b44e13304cd3))
				- Functional Programming in JavaScript
				  id:: 629ccb26-05a4-476c-93b3-c50de3455318
					- https://github.com/stoeffel/awesome-fp-js
					- https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0
					- https://codeburst.io/functional-programming-in-javascript-e57e7e28c0e5
					- https://www.udemy.com/master-functional-js/
					- https://jrsinclair.com/articles/2016/gentle-introduction-to-functional-javascript-intro/
					- Fun Fun Function
					  https://www.youtube.com/playlist?list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84
					- JavaScript Allonge. It's a free book on Lean Pub.
					- Recommended to learn a pure functional language like Haskell, then take the ideas back to mixed paradigm languages
					- https://github.com/stefanlesser/recurse/blob/master/resources/functional-programming.md
					- https://drboolean.gitbooks.io/mostly-adequate-guide/content/
			- Asynchronous programming
			  id:: 68fcf9e9-4ed7-40cb-b0f3-41a1f01bfdc3
			  collapsed:: true
				- Asynchronous programming: JavaScript is often used in asynchronous programming, where code is executed out of order. You should understand how to use callbacks, promises, and async/await to write asynchronous code.
				- Old async code: `.catch` and `.then` are methods on a Promise type - instead prefix these values with `await` then you can use normal `try...catch` blocks
				- ((typescript))
					- `async` methods should always try to return something of the type `Promise<>`
			- ECMAScript versions
			  collapsed:: true
				- Learn newer EMCA because old stuff like var isn't as good
				  collapsed:: true
					- Now we have ES7, ES8 and ES9 on the way.
					  
					  Why would you learn callbacks and promises when async/await is a much better paradigm? Why learning the weirdness of \`var\` instead of using \`const\` and \`let\`? Why using regular functions when arrow functions are better in most cases? You'll need to unlearn lots of stuff, which you don't need to if you start with modern JS in the first place.
					  
					  Don't worry about scale or speed, it's fast enough for almost everyone.
					  
					  Personal opinion here, everyone will tell you different things: go with React or Vue, use VSCode.
					  
					  https://reddit.com/comments/8x7d39/comment/e21vokb?context=3
				- Learn ES6 to ES5 compatibility procedure [ECMAScript 6 compatibility table](https://kangax.github.io/compat-table/es6/)
				- [Javascript ES6 — You don’t really need to learn Generators](https://medium.com/@_bengarrison/javascript-es6-you-dont-really-need-to-learn-generators-96aa2e9114fa)
			- 7 Data Types : `number`, `string`, `boolean`, `undefined`, `null`, `object`, `symbol` (ES2015)
			  id:: 629ccb26-0412-44d5-8c9b-22f20cc7e773
			- ((634ae294-d1f4-4480-8025-ee9f80daa935))
			- Styling
				- [Clean Code Guide - Styling and Formatting Your Code](https://schoolofcode.notion.site/Clean-Code-Guide-Styling-and-Formatting-Your-Code-a8825609ed314f04a712db42d5a354a0)
				  id:: 634af998-c719-4249-8107-74d7fd9146f5
				  collapsed:: true
					- Table of Contents
						- Introduction
						  collapsed:: true
							- In this introductory guide, we will look at why coding practices are important, why formatting your code is important, and how you can achieve well formatted, easy to understand code.
							- Code doesn't need to look good or read well to work. So why bother? Let's take a look at the following code.
							- ```javascript
							  function a(b,c){return(b/c\*100)}const x=1;const y=2;const b = a(x,y);
							  ```
							- 🤮 - this works. But the code is not easy to work with as a programmer. Formatting and code style practices are almost always solely to make it easier for code to be quickly read and understood. Here's the same code as above but with a few minor tweaks in style (the functionality is exactly the same);
							- ```javascript
							  function calculatePercentage(amount, total) { 
							    return (amount / total) \* 100; 
							  } 
							  const numMentors = 1; 
							  const numPeople = 2; 
							  
							  const percentageOfPeopleWhoAreMentors = calculatePercentage(numMentors, numPeople);
							  ```
							- Easy to read code is good news not just for you, but any other developers who will look at the code in the future. Well structured, well formatted, and well written code can also help make errors in your code more obvious.
							- Let's look at some of the techniques and ideas of how we can achieve code that doesn't make us cry when we look at it ![😢](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)
						- Indentation and Spacing
						- Brackets
						- Comments
					- Naming Conventions
					  collapsed:: true
						- Using good, descriptive names for your functions and variables can reveal the intention of the code at a glance. This means it reduces the effort and time needed to read that code and understand what it is doing. This means that you are likely to understand the code better, quicker, which means less mistakes and more holidays !
						- Remember to always use meaningful names so your code speaks for itself.
						- Function Names
							- Bad:
							  ```javascript
							  function find(name) {}
							  ```
							- Good:
							  ```javascript
							  function findBooksByAuthor(author) {}
							  ```
						- Variables Names
							- Bad
							  ```javascript
							  let someStuff = ["Bananas", "Bread", "Cheese", "Crisps", "Milk"];
							  ```
							- Good:
							  ```javascript
							  let shoppingList = ["Bananas", "Bread", "Cheese", "Crisps", "Milk"];
							  ```
						- You can think of indentation as the distance from the page edge. Indentation is the leading whitespace before the code. Indentation has no meaning in JavaScript - the computer will ignore it completely. However, although your code will run without it, good indentation helps improve code readability.
					- Indentation and Spacing
					  collapsed:: true
						- Indentation
						  collapsed:: true
							- You can think of indentation as the distance from the page edge. Indentation is the leading whitespace before the code. Indentation has no meaning in JavaScript - the computer will ignore it completely. However, although your code will run without it, good indentation helps improve code readability.
							- Statement with the same indentation level(whitespace) should be treated as a single code block.
							- Examples
								- Indentation can help us see the relationships in code.
								- ```html
								  <body>
								    <h1>Hello</h1>
								    <h2>There</h2>
								  </body>
								  ```
							- In the HTML code above, we can see from the indentation that body has some children, and the h1 and h2 "belong" to the body and are at the same level.
							- The same approach can be useful in JavaScript.
							- ```javascript
							  let myName = "Kazeem"; 
							  if (myName === "Kazeem") { 
							    console.log(myName); //this is indented because it's treated as a separate code block. 
							  } 
							  myName = "Ade";
							  ```
							- Above, we can see that the indented code belongs to the if statement. This tells us at a glance that the code will only run if the condition evaluates to true.
							- ```javascript
							  const names = \["kazeem", "chris", "Liz"\]; 
							  for (let i = 0; i < names.length; i++) { 
							    console.log(names\[i\]); //this is indented because it's treated as separate code block. 
							  }
							  ```
							- In the for loop example, we can quickly see that the indented code is what will be repeated by the loop. Although brackets are important, it can be fiddly to see which brackets line up with which. The indentation here makes is speedy and easy to see what code belongs where, and when it will run. That's amazing ![🤯](data:image/gif;base64,R0lGODlhAQABAIAAAP///wAAACH5BAEAAAAALAAAAAABAAEAAAICRAEAOw==)
						- White Space
						  collapsed:: true
							- White space is mostly irrelevant to JavaScript (unless it separates key words, or is in a string). This means that most white space gives us the opportunity to make our code more readable.
							- Bad:
							  ```javascript
							  const names=["kazeem","chris","Liz"]; 
							  const favouriteLanguage="Python";
							  ```
							- Good:
							  ```javascript
							  const names = ["kazeem", "chris", "Liz"]; 
							  const favouriteLanguage = "Python";
							  ```
							- Although some of this is opinionated, it's widely thought that space allows our eyes to scan and identify items of interest more easily that clutter. Hopefully you'll agree, and space things out where possible.
						- Line Space
						  collapsed:: true
							- If white space is the space between things on the same line, line space is the space between those lines. As always, it's important to be consistent when spacing so that you can get used to understanding your code at a glance.
							- Bad:
							  ```javascript
							  function(num1,num2){ 
							  console.log(num1\*num2) 
							  } 
							  function(firstName){
							  console.log(firstName) 
							  }
							  function(food){
							  console.log(food) }
							  ```
							- Good:
							  ```javascript
							  function(num1,num2){ 
							    console.log(num1\*num2) 
							  } 
							  function(firstName){ 
							    console.log(firstName) 
							  } 
							  function(food){ 
							    console.log(food) 
							  }
							  ```
					- Brackets
					  collapsed:: true
						- There are three main types of brackets in JavaScript. They are parenthesis `()` (or smoothies as we say at School of Code !🥤, square brackets `[]` (squaries? 🧐, and curly brackets `{}` (or as we call them, *squiggs* 🥴). This section shows what they do and how you can use them.
						- Parenthesis ()
						  collapsed:: true
							- You can think of smoothies as the collectors. They can show things being collected together for evaluation.
								- ```javascript
								  const answer = 4 \* (2 + 3);
								  ```
							- They can collect together the parameters of a function as they are defined.
								- ```javascript
								  function yourFavoriteStuffOnScreen(movie, tv) {}
								  ```
							- In the same way, they can be used to collect the condition of an if, else, for loop, while loop, etc.
							- ```javascript
							  for (let i = 0; i < array.length; i++) { 
							    console.log(i); 
							  }
							  ```
							- They can be used to call a function and collect the arguments to pass through to it.
							- ```javascript
							  yourFavoriteStuffOnScreen("The Avengers", "The Simpsons");
							  ```
						- Square Brackets []
						  collapsed:: true
							- Square brackets are mainly used for either:
								- Defining an array
								- Accessing items in an array
								- Accessing properties in an object
							- Defining an array
								- ```javascript
								  const positiveNumbers = [1, 2, 3, 45, 6, 77];
								  ```
							- Accessing items in an array
								- ```javascript
								  const positiveNumbers = [1, 2, 3, 45, 6, 77]; 
								  positiveNumbers[0]; // gets 1 from the array 
								  positiveNumbers[2]; // gets 3 from the array
								  ```
						- Accessing items in an object
						  collapsed:: true
							- Square brackets can be used to get the value of a key in an object. This does the same thing as using dot(.) notation to get the values.
							- ```javascript
							  const coachesRunningSpeed = { 
							    kazeem: 15, 
							    jordan: 18, 
							    arshi: 17 
							  }; 
							  
							  coachesAge\["kazeem"\]; // gets the value of kazeem from the object (15) 
							  coachesAge.kazeem; // gets the value of kazeem from the object (15)
							  ```
						- Curly Brackets {}
						  collapsed:: true
							- Curly brackets are used to open and close code blocks. Code blocks are present in things like loops, if/else statements, and functions. They define statements to be executed together.
							- Curly brackets also relate to objects. They allow us to define an object, or to destructure properties from an object.
							- Below, the code in the curly bracket runs if the condition in the parenthesis is met.
							- ```javascript
							  const yourName = "Kazeem";
							  if (yourName === "Kazeem") { 
							    console.log(yourName); 
							  }
							  ```
							- ```javascript
							  const scores = { 
							    kazeem: 12, 
							    jordan: 15 }; 
							  
							  const { kazeem } = scores; // makes a new variable called kazeem, with a value of 12 because the object has a property of kazeem with that value
							  ```
					- Comments
					  collapsed:: true
						- How to leave comments like a pro
							- Comments save time, help other developers navigate through your code, and help your future self understand what you had written.
							- This is especially true when you are learning. When you hit real-world projects, often the preference is to have code that explains itself. If your code needs comments to explain it, it might be too complicated.
							- In JavaScript you create a single-line comment with // and multi-line comments using /\* and \*/.
						- As you can see from the examples below, comment overkill can be overwhelming and take to long to read through and understand.
						- Bad:
						  ```javascript
						  function printMessage() { 
						    //calls a function 
						    const comment = document.getElementbyID("comments").value; // declares a variable 
						    if (comment !== null && comment !== "") { 
						      //starts an if statement if there's a comment 
						      return console.log("What a meaningful comment"); //prints a string to the console 
						    } 
						  }
						  ```
						- Good:
						  ```javascript
						  //checks to see if there's a comment. If so, returns a message.
						  function printMessage() { 
						    const comment = document.getElementbyID("comments").value; 
						    if (comment !== null && comment !== "") { 
						      return console.log("What a meaningful comment"); 
						    } 
						  }
						  ```
					- ((63dbe268-004a-42e8-ad9f-c31ff0a05f90))
					  id:: 634b2b38-9907-4c36-a9ce-cfdf7bb8db2f
					  collapsed:: true
			- Template literals
			  collapsed:: true
			  id:: 629ccb26-f5bb-4afa-b828-e7c5c0b92539
				- [source] https://classroom.udacity.com/courses/ud356/lessons/42383e89-ac6a-491a-b7d0-198851287bbe/concepts/df4360db-645e-428c-a6bd-3650eab1a13d
				- See ((63356c8e-baa4-4742-820f-dd86833f2c01))
			- callbacks, promises and async/await
			  collapsed:: true
				- http://callbackhell.com/
				- Promises
				- https://frontarm.com/courses/async-javascript/promises/why-async/
				- * Philip Roberts's What the heck is the event loop anyway? - [https://www.youtube.com/watch?v=8aGhZQkoFbQ](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
				- * The Story of Asynchronous JavaScript - [https://www.youtube.com/watch?v=rivBfgaEyWQ](https://www.youtube.com/watch?v=rivBfgaEyWQ)
				- * JavaScript Callbacks, Promises, and Async / Await Explained - [https://www.youtube.com/watch?v=JRNToFh3hxU](https://www.youtube.com/watch?v=JRNToFh3hxU)
				- * Async Javascript Tutorial For Beginners (Callbacks, Promises, Async Await). - [https://www.youtube.com/watch?v=_8gHHBlbziw](https://www.youtube.com/watch?v=_8gHHBlbziw)
				- * Jake Archibald: In The Loop - setTimeout, micro tasks, requestAnimationFrame, requestIdleCallback, - [https://www.youtube.com/watch?v=cCOL7MC4Pl0](https://www.youtube.com/watch?v=cCOL7MC4Pl0)
				- Edit...
					- I've been rewatching these videos, reading the MDN docs, the Eloquent
				- JavaScript book, javascript.info, blogs about the subject, etc. This
				- further proves you shouldn't limit yourself to a single resource, and
				- instead fill up the laguna with water from different sources if you
				- will.
			- Progressive Web Apps (PWA)
			  collapsed:: true
				- What
					- Native app-like experiences but with a web app
					- e.g. offline-capable; fast
					- What is this Service Worker thing?
						- Service workers are scripts the browser runs in the background, separate from a web page, that allow us to implement features such as push notifications, background sync, dynamic caching of assets and more!
				- _Frameworks_
					- Ionic
						- https://ionicframework.com/pwa
						- https://ionicframework.com/docs/publishing/progressive-web-app/
				- [Learning Resources]
					- https://web.dev/learn/pwa/ - [discussion](https://news.ycombinator.com/item?id=32675791)
			- https://alexnisnevich.github.io/untrusted/
			- Syntax
			  Understanding the basic syntax of JavaScript is essential. This includes knowing how to write variables, functions, control structures, and objects.
				- Control structures = conditionals, loops
			- Data types
			  id:: afddb9fb-9d0f-456f-b505-32fee333e255
			  collapsed:: true
			  AKA data structures
				- *Built-in data types*
					- Strings
					  id:: 663a5793-11c7-42e9-82c2-a9341fb2b742
					- Numbers
					  id:: 663a5793-dcbb-420e-bcfc-76e30f010ce5
					- Booleans
					- Arrays
						- Two-dimensional arrays
						  collapsed:: true
							- e.g. `inputs: Float32Array[][]`
							- In TypeScript (and JavaScript), the syntax inputs: Float32Array[][] means that the variable inputs is a two-dimensional array (an array of arrays) of Float32Array objects.
								- Breaking it down:
									- Float32Array:
									- This is a typed array representing an array of 32-bit floating-point numbers. It is used for efficient storage and manipulation of binary floating-point numeric data, common in audio processing, graphics, and numeric computations.
									- Float32Array[]:
									- An array where each element is a Float32Array. For example, this might represent a list of vectors or signal buffers.
									- Float32Array[][]:
									- An array where each element is itself an array of Float32Array objects. This is effectively a 2D array of typed arrays.
					- Objects
					- **Maps**
					  collapsed:: true
					  Maps are similar to objects, but they allow you to use any data type as the key, not just strings. Maps also maintain the order of keys, which can be useful in some cases.
						- Examples
							- ```js
							  let myMap = new Map();
							  myMap.set("key1", "value1");
							  myMap.set("key2", "value2");
							  myMap.set("key3", "value3");
							  console.log(myMap.get("key2")); // Output: "value2"
							  myMap.delete("key3"); // Remove an entry from the map
							  console.log(myMap); // Output: Map(2) {"key1" => "value1", "key2" => "value2"}
							  ```
					- **Sets**
					  collapsed:: true
					  Sets are used to store a collection of unique values of any data type. Sets automatically remove any duplicate values.
						- Examples
							- ```js
							  let mySet = new Set();
							  mySet.add(1);
							  mySet.add(2);
							  mySet.add(3);
							  mySet.add(3); // Adding a duplicate value has no effect
							  console.log(mySet.has(2)); // Output: true
							  mySet.delete(3); // Remove an element from the set
							  console.log(mySet); // Output: Set(2) {1, 2}
							  ```
					- Null
					- Undefined
					- BigInt
					- Symbol
					- Date
				- *Not built-in:*
					- **Stacks**
					  collapsed:: true
					  Stacks are a collection of elements that can be inserted or removed only from one end of the collection, called the top. Stacks follow the Last In, First Out (LIFO) principle, which means the most recently added element is the first one to be removed.
						- Examples
							- ```js
							  let myStack = [];
							  myStack.push(1);
							  myStack.push(2);
							  myStack.push(3);
							  console.log(myStack.pop()); // Output: 3
							  console.log(myStack); // Output: [1, 2]
							  ```
					- **Queues**
					  collapsed:: true
					  Queues are a collection of elements that can be inserted at one end and removed from the other end of the collection. Queues follow the First In, First Out (FIFO) principle, which means the first element added to the queue is the first one to be removed.
						- Examples
							- ```js
							  let myQueue = [];
							  myQueue.push(1);
							  myQueue.push(2);
							  myQueue.push(3);
							  console.log(myQueue.shift()); // Output: 1
							  console.log(myQueue); // Output: [2, 3]
							  ```
					- **Trees**
					  collapsed:: true
					  Trees are hierarchical data structures consisting of nodes connected by edges. Each node can have zero or more child nodes, and there is only one root node in a tree. Trees are often used to represent hierarchical relationships, such as family trees or organization charts.
						- Examples
							- ```js
							  class TreeNode {
							    constructor(value) {
							      this.value = value;
							      this.children = [];
							    }
							    addChild(node) {
							      this.children.push(node);
							    }
							  }
							  
							  let rootNode = new TreeNode(1);
							  let childNode1 = new TreeNode(2);
							  let childNode2 = new TreeNode(3);
							  rootNode.addChild(childNode1);
							  rootNode.addChild(childNode2);
							  console.log(rootNode.value); // Output: 1
							  console.log(rootNode.children.length); // Output: 2
							  ```
					- **Graphs**
					  collapsed:: true
					  Graphs are a collection of vertices (also called nodes) and edges connecting them. Graphs can be directed or undirected, and they are often used to represent relationships between entities in a network, such as social networks or computer networks.
						- Examples
							- ```js
							  class Graph {
							    constructor() {
							      this.vertices = new Set();
							      this.edges = new Map();
							    }
							    addVertex(vertex) {
							      this.vertices.add(vertex);
							      this.edges.set(vertex, new Set());
							    }
							    addEdge(vertex1, vertex2) {
							      this.edges.get(vertex1).add(vertex2);
							      this.edges.get(vertex2).add(vertex1);
							    }
							  }
							  
							  let myGraph = new Graph();
							  myGraph.addVertex(1);
							  myGraph.addVertex(2);
							  myGraph.addVertex(3);
							  myGraph.addEdge(1, 2);
							  myGraph.addEdge(2, 3);
							  console.log(myGraph.vertices.size); // Output: 3
							  console.log(myGraph.edges.get(2).size); // Output: 2
							  ```
					- **Hash tables**
					  collapsed:: true
					  Hash tables are used to store key-value pairs, but they use a hashing function to map keys to indexes in an array. This allows for efficient lookup and insertion of key-value pairs.
						- Examples
							- ```js
							  let myHashTable = {};
							  myHashTable["key1"] = "value1";
							  myHashTable["key2"] = "value2";
							  myHashTable["key3"] = "value3";
							  console.log(myHashTable["key2"]); // Output: "value2"
							  delete myHashTable["key3"]; // Remove an entry from the hash table
							  console.log(myHashTable); // Output: {key1: "value1", key2: "value2"}
							  ```
				- Mutability
				  id:: 66bce5d1-babc-4aa9-b668-2fd3dd5b45be
				  collapsed:: true
					- Immutable basically means something that cannot be changed.
					- Primitives (e.g. ((663a5793-11c7-42e9-82c2-a9341fb2b742)), ((663a5793-dcbb-420e-bcfc-76e30f010ce5)) ) are immutable by default
						- Appending text creates a new string and assigns it to the greet variable.
						  collapsed:: true
							- ![image.png](../assets/image_1723655781351_0.png)
					- Arrays and objects are mutable by default
						- We can modify it "in place", adding, removing, or changing elements.
					- [Learning Resources]
						- [Immutability in JavaScript – Explained with Examples](https://www.freecodecamp.org/news/immutability-in-javascript-with-examples/)
					- Related: [[Programming Languages]] : ((66bce803-2305-4c9c-83b5-582478a0c376))
			- DOM manipulation: JavaScript is often used to manipulate the Document Object Model (DOM) of a web page. You should understand how to use JavaScript to add, remove, and modify elements on a web page.
			- Functions: Functions are a core concept in JavaScript. You should understand how to write functions, how to use them as first-class citizens, and how to use them to create higher-order functions.
			- Events: JavaScript is often used to handle events, such as user interactions with a web page. You should understand how to use event listeners to handle these events.
			- ES6 features: ECMAScript 6 (ES6) is a major update to the JavaScript language that introduced several new features, including arrow functions, let and const variables, classes, and modules. You should understand how to use these features to write more modern and efficient code.
			- How to have a non-blocking forever loop
			  collapsed:: true
				- Suppose you have an `async function runStream(ws)` which loops forever, e.g.:
					- ```js
					  async function runStream(ws) {
					    while (true) {
					      // process data from the stream (for example, reading and writing)
					      await ws.processSomeData();
					    }
					  }
					  ```
					- And you want to call this in another async function but not block further execution.
					  Simply call the function but do not await it:
					- ```js
					  async function doThings() {
					  runStream(ws); // starts infinite loop in background, does not block
					  // The next line will execute immediately
					  doOtherStuff();
					  }
					  ```
			- Function overloading
			  collapsed:: true
				- ```typescript
				  function pickFile( options: { multiple: true } & PickFileOptions, ): Promise<FileList>;
				  function pickFile( options: { multiple?: false } & PickFileOptions, ): Promise<File | null>;
				  function pickFile( options: { multiple?: boolean } & PickFileOptions, ): Promise<FileList | File | null>;
				  ```
				- i.e. many ways to call the function depending on the arguments passed in
	- ## Completed learning resources (references)
		- [MDN References: JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
		  id:: 6343d066-e388-4d88-808d-94ce2960681d
		  collapsed:: true
			- Meta
				- Quick links
					- ((663a5794-417e-4e60-b0ea-2fdf18fd5342)) : Notable data types
					  id:: 66ba22e0-f894-4d28-80c2-98ae6feb4171
						- ((64024e3f-d75a-46c3-98e3-e4679ebc4b50))
						- ((63904f3d-8308-421c-b0a0-c1bb897f5b31))
						- ((64024e3f-2a66-4456-816f-f0b00cfd0c4e))
						- ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1))
					- ((64024e3f-971a-4fae-8c9e-ec2415404127)) : notable
						- ((64024e3f-ef30-4e8e-bc0f-aedb5a95a08c))
						- ((63679853-6e6e-4fce-87bc-93f106c2e05d))
						- ((6350374d-2dff-4f93-bacc-6480a9f1aca0))
					- ((663a5793-2531-4a6e-a2de-6aae0ad0ec69))
						- ((63679853-e408-4028-a2c0-eefdd34febd3))
						- ((63642a10-4e86-4101-961a-8311efb8ae4f))
						- ((63679853-46c2-4992-ab73-5c27acc7ce2e))
						-
			- [Built-ins](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects)
			  id:: 663a5794-417e-4e60-b0ea-2fdf18fd5342
			  collapsed:: true
				- Value properties
					- [`globalThis`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/globalThis)
					- [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity)
					- [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN)
					- [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)
				- Function properties
					- [`eval()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval)
					- [`isFinite()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isFinite)
					- [`isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/isNaN)
					- [`parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)
					- [`parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
					  id:: 63470fd1-de4c-4705-9fb1-e734bf59cdd7
					  collapsed:: true
					  ((63f29925-f6ae-4cd6-96ad-e6c66a96f1cb)) | Inverse of ((638f490f-1505-4a98-9399-94834d07c5b6)) or ((638d0621-ae57-4cbc-b873-1bbcffc158dd)) | Alternative to ((63904f3d-d57b-4667-94cf-29d887d54afc)) or ((638f4569-62ae-4ff5-bcd8-05d9e9794183))
						- Can convert a string to a number
						  id:: 63f29925-f6ae-4cd6-96ad-e6c66a96f1cb
						- Syntax
							- `parseInt(string)`
						- Example
							- ```javascript
							  parseInt("10");
							  // returns: 10
							  ```
							- Can convert a binary string (base-2) to normal numbers (base-10)
							  id:: 63f219c9-6008-4f84-beba-7db15dd52f76
								- ((63f21a59-5cd9-4daa-beeb-34f9df8f5296))
									- {{embed ((63f21a60-f0de-40b4-9674-dc3f8beb880d))}}
								- Related: The inverse = ((638d0621-ae57-4cbc-b873-1bbcffc158dd)) : ((63f2175c-19f9-4a8e-8c4a-7443cf99d71e))
						- Related:
							- ((6391c00f-9fcf-4c2a-a121-ad8bfbc09cff))
					- [`decodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURI)
					- [`decodeURIComponent()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/decodeURIComponent)
					- [`encodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI)
					- [`encodeURIComponent()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent)
				- Fundamental objects
					- [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
					  id:: 63f33e7c-e71b-4d14-b352-7b9fe2d600b1
					  collapsed:: true
						- Meta
							- ((66044236-7c13-489c-90d8-c596c760179a))
							- Features
								- Collections of key-value pairs
								- Mutable, meaning their state can be updated
								- Can store various data types e.g. strings, numbers, arrays, functions
							- ((63679853-975f-4456-b131-53731a001078)) : ((646349b1-7599-465f-978d-a5b10b88a004))
							- Dot notation vs Bracket notation
							  id:: 63f8fedc-7c7f-4902-abd1-b925c86c93ce
							  collapsed:: true
								- AKA ((64024e3f-e59e-42a6-9fba-1c86518b4b19))
								- ((63f8d8cf-e3ec-47f7-b296-7e8e026a0d45))
								- Need to use bracket notation instead of dot notation if using ((6350374d-fdba-4eb4-b17a-f80e5e5a3fcb)) to update an object (adding new key/value pairs or updating the existing) otherwise `element` will be read as a string
								- To access an object in an array whose name is defined by a var
									- ```js
									  sentPacks[i][packSizes[i]]
									  ```
								- Related:
									- ((63679853-975f-4456-b131-53731a001078)) : ((646349b1-7599-465f-978d-a5b10b88a004))
									- [Introducing JavaScript objects - Learn web development | MDN](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects)
							- ((507dc5b1-e753-4ada-9eee-5acd64ec1f7d)) : ((6408c102-0f97-4a12-820b-ce707252c952))
						- Properties
							- [`Object.prototype.constructor`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/constructor)
							- {Archive} ^^Deprecated^^
							  collapsed:: true
								- [`Object.prototype.__proto__`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/proto)
								  id:: 646349b1-801a-47e3-a73e-de2360725a07
						- Methods
							- [`Object.assign()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)
							  collapsed:: true
							  ((6408c21b-fe9b-4417-b6a1-d9442a257977))
								- It copies all [enumerable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/propertyIsEnumerable) [own properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwn) from one or more *source objects* to a *target object*. It returns the modified target object.
								  id:: 6408c21b-fe9b-4417-b6a1-d9442a257977
								- Meta
									- #+BEGIN_WARNING
									  This is a **shallow copy**. Use ((507dc5b1-e753-4ada-9eee-5acd64ec1f7d)) and ((634eb27a-5613-4a08-8634-3fe0a916e99e)) to do a deep copy.
									  #+END_WARNING
								- Examples
									- ```js
									  const target = { a: 1, b: 2 };
									  const source = { b: 4, c: 5 };
									  
									  const returnedTarget = Object.assign(target, source);
									  
									  console.log(target);
									  // Expected output: Object { a: 1, b: 4, c: 5 }
									  
									  console.log(returnedTarget === target);
									  // Expected output: true
									  ```
							- [`Object.create()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create)
							  collapsed:: true
								- It creates a new object, using an existing object as the prototype of the newly created object.
								- Examples
									- ```js
									  const person = {
									    isHuman: false,
									    printIntroduction: function() {
									      console.log(`My name is ${this.name}. Am I human? ${this.isHuman}`);
									    }
									  };
									  
									  const me = Object.create(person);
									  
									  me.name = 'Matthew'; // "name" is a property set on "me", but not on "person"
									  me.isHuman = true; // Inherited properties can be overwritten
									  
									  me.printIntroduction();
									  // Expected output: "My name is Matthew. Am I human? true"
									  ```
							- [`Object.defineProperties()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperties)
							- [`Object.defineProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)
							  id:: 63679853-849e-4274-8f95-b5178cb66a6c
							  collapsed:: true
								- [How to hide object properties from console logs and iteration #shorts - YouTube](https://youtu.be/51S1hevmQd0)
								  id:: 6367a0ff-8d8b-4d0d-b757-9219291e7ed8
									- ```javascript
									  const obj = {
									    name: 'hello',
									  }
									  Object.defineProperty(obj,
									    'secret', {
									      enumerable: false,
									      value: 'what is up',
									    }
									  )
									  console.log(obj);
									  // expected output: { name: 'hello' }
									  ```
									- Limited usecases since it still can be called directly. Better to use environment variables for secrets
							- [`Object.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/entries)
							  id:: 6377ece4-3a89-4765-b6d0-8c1620f49c11
							  collapsed:: true
							  ((6367a177-676f-4518-ad91-4fad0759ab49))
								- It returns an array of a given object's own enumerable string-keyed property names and values.
								  id:: 6367a177-676f-4518-ad91-4fad0759ab49
									- Opposite of ((6367a146-06fc-4e50-b64f-a112da9ad635))
									- ```javascript
									  const obj = {
									    name: "bob",
									    age: 20
									  };
									  console.log(Object.entries(obj));
									  // expected output: [ ['name', 'bob'], ['age', 20] ]
									  ```
								- Related:
									- ((6377ece4-b9b9-413a-8195-15de9b9c5ec2)) for the keys
									- ((6377ece4-268b-452d-b61a-2237d410c507)) for the values
									- ((64024e42-a0ab-4278-9c5b-4cc98409efd8)) for checking non-object data structures
							- [`Object.freeze()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze)
							  id:: 64024e3f-2814-4615-b4f0-a2b49b57e78f
							  collapsed:: true
							  ((6408c51c-ad3a-4c43-b4b1-9cd9fee3d51b))
								- This *freezes* an object
								  id:: 6408c51c-ad3a-4c43-b4b1-9cd9fee3d51b
									- Freezing an object [prevents extensions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/preventExtensions) and makes existing properties non-writable and non-configurable. A frozen object can no longer be changed: new properties cannot be added, existing properties cannot be removed, their enumerability, configurability, writability, or value cannot be changed, and the object's prototype cannot be re-assigned. `freeze()` returns the same object that was passed in.
									- Freezing an object is the highest integrity level that JavaScript provides.
								- Examples
									- ```js
									  const obj = {
									    prop: 42
									  };
									  
									  Object.freeze(obj);
									  
									  obj.prop = 33;
									  // Throws an error in strict mode
									  
									  console.log(obj.prop);
									  // Expected output: 42
									  ```
								- Related: ((64024e3f-ac91-4d7c-a821-0002462bb14d))
							- [`Object.fromEntries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/fromEntries)
							  id:: 64024e3f-dbb1-4d5c-9b49-76009df56467
							  collapsed:: true
							  ((64024e3f-ab8d-4776-964c-79c44a5c8c1f))
								- It transforms a list of key-value pairs (e.g. an array) into an object.
								  id:: 64024e3f-ab8d-4776-964c-79c44a5c8c1f
								- Example
									- ```javascript
									  const entries = new Map([
									    ['foo', 'bar'],
									    ['baz', 42]
									  ]);
									  
									  const obj = Object.fromEntries(entries);
									  
									  console.log(obj);
									  // expected output: Object { foo: "bar", baz: 42 }
									  ```
								- [How to use Object.fromEntries to convert arrays to objects #shorts - YouTube](https://youtu.be/9Vn4q_zy3ls)
								  id:: 6367a146-06fc-4e50-b64f-a112da9ad635
									- Opposite of ((6367a177-676f-4518-ad91-4fad0759ab49))
									- ```javascript
									  const objAsArray = [
									    ['name', 'bob'],
									    ['age', 20]
									  ]
									  const obj = Object.fromEntries(objAsArray)
									  console.log(obj);
									  // expected output: { name: "bob", age: 20 }
									  ```
							- [`Object.getOwnPropertyDescriptor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor)
							- [`Object.getOwnPropertyDescriptors()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptors)
							- [`Object.getOwnPropertyNames()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyNames)
							- [`Object.getOwnPropertySymbols()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertySymbols)
							- [`Object.getPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf)
							  id:: 646349b0-c2cf-4be8-8ad1-b93767059a94
							  collapsed:: true
							  Returns the prototype (i.e. the value of the internal [[Prototype]] property) of the specified object.
								-
							- [`Object.groupBy`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/groupBy)
							  id:: 6579fe15-797f-4976-a9a1-2f7a4d0995a7
							  collapsed:: true
								- allows you to organise all the objects in an array by a specific value e.g. sort ages into two groups
							- [`Object.hasOwn()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwn)
							  id:: 64024e3f-34f6-4295-8f37-be8258ca0c9e
							  collapsed:: true
							  ((640866c5-5fd1-4955-b2c3-4393598adecc)) | Intended to replace ((646349b0-11fb-44f1-a715-ee5bd59d8f1c))
								- It returns `true` if the specified object has the indicated property as its *own* property.  If the property is inherited, or does not exist, the method returns `false`.
								  id:: 640866c5-5fd1-4955-b2c3-4393598adecc
								- Syntax
									- ```js
									  Object.hasOwn(obj, prop)
									  ```
										- Parameters
											- [`obj`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwn#obj) : The JavaScript object instance to test.
											- [`prop`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwn#prop) : The [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) name or [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) of the property to test.
										- Return value
											- `true` if the specified object has directly defined the specified property. Otherwise `false`
								- Examples
									- Using hasOwn to test for a property's existence
									  ```js
									  const example = {};
									  Object.hasOwn(example, "prop"); // false - 'prop' has not been defined
									  
									  example.prop = "exists";
									  Object.hasOwn(example, "prop"); // true - 'prop' has been defined
									  
									  example.prop = null;
									  Object.hasOwn(example, "prop"); // true - own property exists with value of null
									  
									  example.prop = undefined;
									  Object.hasOwn(example, "prop"); // true - own property exists with value of undefined
									  ```
							- [`Object.prototype.hasOwnProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)
							  id:: 646349b0-11fb-44f1-a715-ee5bd59d8f1c
							  collapsed:: true
							  Being replaced by ((64024e3f-34f6-4295-8f37-be8258ca0c9e))
								- Returns a boolean indicating whether this object has the specified property as its own property (as opposed to inheriting it).
								- Syntax
									- ```js
									  hasOwnProperty(prop)
									  ```
										- Parameters
											- [`prop`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty#prop) : The [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) name or [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) of the property to test.
										- Return value
											- Returns `true` if the object has the specified property as own property; `false` otherwise.
								- Examples
									- ```js
									  const fruits = ["Apple", "Banana", "Watermelon", "Orange"];
									  fruits.hasOwnProperty(3); // true ('Orange')
									  fruits.hasOwnProperty(4); // false - not defined
									  ```
									- id:: 65539093-0042-4124-8394-bb0f4b8ecd9d
									  ```js
									  let Person = {
									    firstName: '',
									    lastName: '',
									    age: 18
									  }
									  
									  let jim = { firstName: 'Jim', lastName: 'Cooper' }
									  Object.setPrototypeOf(jim, Person);
									  
									  jim.hasOwnProperty('firstName'); // true
									  jim.hasOwnProperty('age'); // false
									  ```
							- [`Object.is()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is)
							  collapsed:: true
							  ((6408c5ad-72f9-4e3d-b81d-e991970e1fd3))
								- It determines whether two values are [the same value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#same-value_equality_using_object.is).
								  id:: 6408c5ad-72f9-4e3d-b81d-e991970e1fd3
								- Examples
									- ```js
									  console.log(Object.is('1', 1));
									  // Expected output: false
									  
									  console.log(Object.is(NaN, NaN));
									  // Expected output: true
									  
									  console.log(Object.is(-0, 0));
									  // Expected output: false
									  
									  const obj = {};
									  console.log(Object.is(obj, {}));
									  // Expected output: false
									  ```
							- [`Object.isExtensible()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isExtensible)
							- [`Object.isFrozen()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isFrozen)
							- [`Object.prototype.isPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isPrototypeOf)
							- [`Object.isSealed()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isSealed)
							- [`Object.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/keys)
							  id:: 6377ece4-b9b9-413a-8195-15de9b9c5ec2
							  collapsed:: true
							  ((6408bfe1-6ca4-4ba1-8f6a-1d72eb69ffce))
								- It returns an array of a given object's own enumerable string-keyed property names.
								  id:: 6408bfe1-6ca4-4ba1-8f6a-1d72eb69ffce
								- Meta
									- `Object.keys(myObj).length` can be used to get an object's length
									  id:: 6408649f-1747-45ba-95c1-5bf5984a32a6
								- Example
									- ```javascript
									  const object1 = {
									    a: 'somestring',
									    b: 42,
									    c: false
									  };
									  
									  console.log(Object.keys(object1));
									  // expected output: Array ["a", "b", "c"]
									  
									  ```
								- Related:
									- ((6377ece4-268b-452d-b61a-2237d410c507)) for the values
									- ((6377ece4-3a89-4765-b6d0-8c1620f49c11)) for the keys and values
							- [`Object.preventExtensions()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/preventExtensions)
							- [`Object.prototype.propertyIsEnumerable()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/propertyIsEnumerable)
							- [`Object.seal()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/seal)
							  id:: 64024e3f-ac91-4d7c-a821-0002462bb14d
							  collapsed:: true
							  ((6408c777-a52c-47e7-b0fc-f11ed609ce1f))
								- It *seals* an object, preventing adding new properties but still allowing existing properties to be changed.
								  id:: 6408c777-a52c-47e7-b0fc-f11ed609ce1f
									- Sealing an object [prevents extensions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/preventExtensions) and makes existing properties non-configurable. A sealed object has a fixed set of properties: new properties cannot be added, existing properties cannot be removed, their enumerability and configurability cannot be changed, and its prototype cannot be re-assigned. Values of existing properties can still be changed as long as they are writable. `seal()` returns the same object that was passed in.
								- Related: ((64024e3f-2814-4615-b4f0-a2b49b57e78f))
							- [`Object.setPrototypeOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/setPrototypeOf)
							  id:: 646349b0-93d7-4477-add9-481d59e062c3
							  collapsed:: true
							  Sets the prototype (i.e., the internal `[[Prototype]]` property) of a specified object to another object or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null).
								- Syntax
									- ```js
									  Object.setPrototypeOf(obj, prototype)
									  ```
									- Parameters
										- [`obj`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/setPrototypeOf#obj) : The object which is to have its prototype set.
										- [`prototype`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/setPrototypeOf#prototype) : The object's new prototype (an object or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null)). Naming convention it that it should be ((b2c095a3-5b8c-49e3-a10d-877a42e8cb78)) ?
									- Return value
										- The specified object.
								- Examples
									- id:: 6550d30d-a061-4ad7-9a2b-5732508af02f
									  ```js
									  let Person = {
									    firstName: '',
									    lastname: '',
									    age: 0
									  }
									  
									  let jim = {};
									  Object.setPrototypeOf(jim, Person);
									  ```
									- Creating multiple levels of inheritance (prototype chain)
									  id:: 655392b4-1e44-4721-ad10-c6f13b7055fd
									  ```js
									  let Person = {
									    firstName: '',
									    lastname: '',
									    age: 0
									  }
									  
									  let Student = {
									    enrolledCourses = [],
									    yearOfGraduation = 2015
									  }
									  
									  Object.setPrototypeOf(Student, Person);
									  
									  let jim = {};
									  Object.setPrototypeOf(jim, Student);
									  ```
							- [`Object.prototype.toLocaleString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toLocaleString)
							- [`Object.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/toString)
							  id:: 64024e3f-cc84-4091-bb07-e55be6c3abdb
							  collapsed:: true
							  ((6408c62a-82f4-428e-929a-3194dc6790f2))
								- This returns a string representing the object. This method is meant to be overridden by derived objects for custom [type conversion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#type_coercion) logic.
								  id:: 6408c62a-82f4-428e-929a-3194dc6790f2
								- Meta
									- `Object.prototype.toString.call(arr)` to identify arrays
									  id:: 64085108-7822-43fd-93e3-9c5e514101f0
										- ```js
										  const arr = [1, 2, 3];
										  
										  arr.toString(); // "1,2,3"
										  Object.prototype.toString.call(arr); // "[object Array]"
										  
										  ```
										- Related: ((63470fd1-ff2c-4b9a-b116-136a41a52b94))
							- [`Object.prototype.valueOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/valueOf)
							- [`Object.values()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/values)
							  id:: 6377ece4-268b-452d-b61a-2237d410c507
							  collapsed:: true
							  ((64024e3f-a154-4ef3-807a-8dd85e3f34dc))
								- It returns an array of a given object's own enumerable string-keyed property values.
								  id:: 64024e3f-a154-4ef3-807a-8dd85e3f34dc
								- Example
									- ```javascript
									  const object1 = {
									    a: 'somestring',
									    b: 42,
									    c: false
									  };
									  
									  console.log(Object.values(object1));
									  // expected output: Array ["somestring", 42, false]
									  ```
								- Related:
									- ((6377ece4-b9b9-413a-8195-15de9b9c5ec2)) for the keys
									- ((6377ece4-3a89-4765-b6d0-8c1620f49c11)) for the keys and values
							- {Archive} ^^Deprecated^^
								- [`Object.prototype.__defineGetter__()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineGetter__)
								- [`Object.prototype.__defineSetter__()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__defineSetter__)
								- [`Object.prototype.__lookupGetter__()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__lookupGetter__)
								- [`Object.prototype.__lookupSetter__()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/__lookupSetter__)
						- Related: ((64024e3f-2a66-4456-816f-f0b00cfd0c4e))
					- [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function)
					  collapsed:: true
						- Properties
							- Non-standard + Deprecated [`Function.prototype.arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/arguments)
							- Non-standard + Deprecated [`Function.prototype.caller`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/caller)
							- Non-standard [`Function.prototype.displayName`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/displayName)
							- [`Function.prototype.length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/length)
							- [`Function.prototype.name`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/name)
							- [`Function.prototype.prototype`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/prototype)
							  id:: 646349b0-04f1-4f6c-a7ad-c0bb87216141
						- Methods
							- [`Function.prototype.apply()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)
							  id:: 63f8fe4d-795b-436e-9fc4-1c0cb402cbda
								- Calls the specified function with a given `this` value, and `arguments` provided as an array (or an [array-like object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#working_with_array-like_objects)).
								- Syntax
									- ```javascript
									  apply(thisArg)
									  apply(thisArg, argsArray)
									  ```
										- Parameters
											- `thisArg` : The value of `this` provided for the call to `func`. If the function is not in [strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode), [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null) and [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) will be replaced with the global object, and primitive values will be converted to objects.
											- `argsArray` : An array-like object, specifying the arguments with which `func` should be called, or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null) or [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) if no arguments should be provided to the function.
										- Return value
											- The result of calling the function with the specified `this` value and arguments.
								- Description
									- This function is almost identical to [`call()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call), except that `call()` accepts an **argument list**, while `apply()` accepts a **single array of arguments** — for example, `func.apply(this, ['eat', 'bananas'])` vs. `func.call(this, 'eat', 'bananas')`.
								- Examples
									- ```javascript
									  const numbers = [5, 6, 2, 3, 7];
									  
									  const max = Math.max.apply(null, numbers);
									  
									  console.log(max);
									  // Expected output: 7
									  
									  const min = Math.min.apply(null, numbers);
									  
									  console.log(min);
									  // Expected output: 2
									  ```
									- ((63f8a449-3ee5-4ca1-9c55-1ac8dc03ec0a))
										- {{embed ((63f8fe4c-b210-4d07-b282-4fb0d47a4d9e))}}
							- [`Function.prototype.bind()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)
							- [`Function.prototype.call()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call)
							- [`Function.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/toString)
					- [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)
					  collapsed:: true
						- Methods
							- [`Boolean.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/toString)
							- [`Boolean.prototype.valueOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/valueOf)
					- [`Symbol`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)
					  id:: 63470fd1-c27c-424a-bb5b-5e554f9571ec
					  collapsed:: true
						- Properties
							- [`Symbol.asyncIterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/asyncIterator)
							- [`Symbol.prototype.description`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/description)
							- [`Symbol.hasInstance`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/hasInstance)
							- [`Symbol.isConcatSpreadable`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/isConcatSpreadable)
							- [`Symbol.iterator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/iterator)
							  collapsed:: true
								- [obj[Symbol.iterator] can be used to overwrite default iteration behaviour](https://youtu.be/wuw7bk2v6bw)
								  id:: 6367a82c-cc3e-4f05-bb71-fe01e8558ebe
									- ```javascript
									  const obj = {
									    name: 'bob',
									    age:  20
									  }
									  obj[Symbol.iterator] = function () {
									    yield 'a'
									    yield 'b'
									    yield 'c'
									    yield 'd'
									  }
									  for (let key of obj) {
									    console.log(key)
									  }
									  // expected output: 
									  // a
									  // b
									  // c
									  // d
									  
									  // outputs your custom logic rather than what is actually in the object
									  ```
							- [`Symbol.match`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/match)
							- [`Symbol.matchAll`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/matchAll)
							- [`Symbol.replace`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/replace)
							  id:: ad29df8c-e612-449e-b366-2eeaa53b0c1e
							- [`Symbol.search`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/search)
							- [`Symbol.species`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/species)
							- [`Symbol.split`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/split)
							- [`Symbol.toPrimitive`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toPrimitive)
							- [`Symbol.toStringTag`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toStringTag)
							- [`Symbol.unscopables`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables)
						- Methods
							- [`Symbol.prototype[@@toPrimitive]`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/@@toPrimitive)
							- [`Symbol.for()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/for)
							- [`Symbol.keyFor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/keyFor)
							- [`Symbol.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/toString)
							- [`Symbol.prototype.valueOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/valueOf)
				- Error objects
					- [`Error`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error)
					- [`EvalError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError)
					- [`RangeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError)
					- [`ReferenceError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError)
					- [`SyntaxError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError)
					- [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)
					- [`URIError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/URIError)
					- [`AggregateError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError)
				- Numbers & dates
					- [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number)
					  id:: 63904f3d-8308-421c-b0a0-c1bb897f5b31
					  collapsed:: true
						- Meta
							- ((6351322c-6b12-4902-b961-9ad79f67c9dc))
						- Constructor
							- [`Number() constructor`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/Number)
							  id:: 66ba4356-1666-4c14-ae60-2c17993d8c76
							  collapsed:: true
							  ((66ba4367-68bf-41d1-bf05-f86a6ae43825)) | Inverse of ((638f490f-1505-4a98-9399-94834d07c5b6)) or ((638d0621-ae57-4cbc-b873-1bbcffc158dd)) | Alternative to ((638f4569-62ae-4ff5-bcd8-05d9e9794183)) or ((63904f3d-d57b-4667-94cf-29d887d54afc))
								- Can convert any type(?) to a number
								  id:: 66ba4367-68bf-41d1-bf05-f86a6ae43825
								- Examples
									- ```js
									  str = '1234'
									  Number(str) // 1234
									  ```
									- ((6351322c-6b12-4902-b961-9ad79f67c9dc))
										- {{embed ((6351322c-6b12-4902-b961-9ad79f67c9dc))}}
						- Properties
							- [`Number.EPSILON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/EPSILON)
							- [`Number.MAX_SAFE_INTEGER`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_SAFE_INTEGER)
							- [`Number.MAX_VALUE`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_VALUE)
							- [`Number.MIN_SAFE_INTEGER`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_SAFE_INTEGER)
							- [`Number.MIN_VALUE`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_VALUE)
							- [`Number.NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN)
							- [`Number.NEGATIVE_INFINITY`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/NEGATIVE_INFINITY)
							- [`Number.POSITIVE_INFINITY`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/POSITIVE_INFINITY)
						- Methods
							- [`Number.isFinite()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isFinite)
							- [`Number.isInteger()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger)
							  id:: 63baa388-27f4-48ce-9808-643b128297a7
							  collapsed:: true
								- Can be used to check whether the passed value is an integer
								- Examples
									- ```javascript
									  Number.isInteger(0); // true
									  Number.isInteger(1); // true
									  Number.isInteger(5.0); // true
									  Number.isInteger(-100000); // true
									  Number.isInteger(99999999999999999999999); // true
									  
									  Number.isInteger(0.1); // false
									  Number.isInteger(5.01); // false
									  ```
									- Can be combined with ((63baa388-e728-4ca8-b999-71ccffc091b4)) in order to identify if a value is a square number
									  id:: 63f29ee4-1022-4275-a0ec-1dc01640e128
										- ```javascript
										  Number.isInteger(Math.sqrt(n))
										  ```
							- [`Number.isNaN()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN)
							- [`Number.isSafeInteger()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/isSafeInteger)
							- [`Number.parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseFloat)
							- [`Number.parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt)
							  id:: 63904f3d-d57b-4667-94cf-29d887d54afc
							  collapsed:: true
							  Converts a string to a number | Inverse of ((638f490f-1505-4a98-9399-94834d07c5b6)) or ((638d0621-ae57-4cbc-b873-1bbcffc158dd)) | Alternative to ((63470fd1-de4c-4705-9fb1-e734bf59cdd7)) or ((638f4569-62ae-4ff5-bcd8-05d9e9794183)) or ((66ba4356-1666-4c14-ae60-2c17993d8c76))
								- Example
									- ```javascript
									  function roughScale(x, base) {
									    const parsed = Number.parseInt(x, base);
									    if (Number.isNaN(parsed)) {
									      return 0;
									    }
									    return parsed * 100;
									  }
									  
									  console.log(roughScale(' 0xF', 16));
									  // expected output: 1500
									  
									  console.log(roughScale('321', 2));
									  // expected output: 0
									  
									  ```
								- Related: ((63470fd1-de4c-4705-9fb1-e734bf59cdd7))
							- [`Number.prototype.toExponential()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toExponential)
							- [`Number.prototype.toFixed()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
							  Round decimals to a particular number of decimal places
							- [`Number.prototype.toLocaleString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString)
							- [`Number.prototype.toPrecision()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toPrecision)
							- [`Number.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString)
							  id:: 638d0621-ae57-4cbc-b873-1bbcffc158dd
							  collapsed:: true
							  Converts number to string | Inverse of ((638f4569-62ae-4ff5-bcd8-05d9e9794183)) or ((63470fd1-de4c-4705-9fb1-e734bf59cdd7)) or ((63904f3d-d57b-4667-94cf-29d887d54afc)) | Alternative to ((638f490f-1505-4a98-9399-94834d07c5b6))
								- Example
									- ```javascript
									  const count = 10;
									  console.log(count.toString()); // "10"
									  
									  console.log((17).toString()); // "17"
									  console.log((17.2).toString()); // "17.2"
									  ```
									- Can convert normal (base-10) numbers to binary (base-2), hexadecimal (base-16), etc
									  id:: 63f2175c-19f9-4a8e-8c4a-7443cf99d71e
										- ```javascript
										  (255).toString(); // "255" (default is radix 10)
										  (255).toString(2); // "11111111" (radix 2, i.e. binary)
										  (255).toString(16); // "ff" (radix 16, i.e. hexadecimal)
										  ```
											- Binary (base-2) = 8 numbers
											- Hexadecimal (base-16) = `0`-`9`, then`A`-`F`
										- Related: The inverse = ((63470fd1-de4c-4705-9fb1-e734bf59cdd7)) : ((63f219c9-6008-4f84-beba-7db15dd52f76))
								- Related: ((63470fd1-b8ce-43b2-ab22-5ba17988fc3e))
							- [`Number.prototype.valueOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/valueOf)
					- [`BigInt`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt)
					- [`Math`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
					  collapsed:: true
					  id:: 64024e3f-184c-440e-b9e6-c2e0abf1a2a3
						- Properties
							- [`Math.E`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/E)
							- [`Math.LN10`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/LN10)
							- [`Math.LN2`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/LN2)
							- [`Math.LOG10E`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/LOG10E)
							- [`Math.LOG2E`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/LOG2E)
							- [`Math.PI`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/PI)
							- [`Math.SQRT1_2`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/SQRT1_2)
							- [`Math.SQRT2`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/SQRT2)
						- Methods
							- [`Math.abs()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/abs)
							  id:: 635130dc-3425-423b-9311-3819c0f7039f
							  collapsed:: true
								- Can return the absolute value of a number
								- `Math.abs(number)` can be used to convert numbers between positive and negative
								  id:: 63513279-b287-4afa-89fd-764214eba393
									- `Math.abs(number)` can be used to convert a negative number to a positive number
									- `-Math.abs(number)` can be used to convert a positive number to a negative number
									- Related: ((6350374c-70ca-4bef-a2e8-567973e8a603))
							- [`Math.acos()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/acos)
							- [`Math.acosh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh)
							- [`Math.asin()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/asin)
							- [`Math.asinh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/asinh)
							- [`Math.atan()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atan)
							- [`Math.atan2()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atan2)
							- [`Math.atanh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/atanh)
							- [`Math.cbrt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cbrt)
							- [`Math.ceil()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil)
							  id:: 63904f3d-1750-45b8-8d71-64b745cbf61f
							  collapsed:: true
							  Inverse of ((63904f3d-8ecf-4c85-b7c3-9c1b19778762))
								- The **`Math.ceil()`** function always rounds up and returns the smaller integer greater than or equal to a given number.
								- Examples
									- ```javascript
									  console.log(Math.ceil(.95));
									  // expected output: 1
									  
									  console.log(Math.ceil(4));
									  // expected output: 4
									  
									  console.log(Math.ceil(7.004));
									  // expected output: 8
									  
									  console.log(Math.ceil(-7.004));
									  // expected output: -7
									  ```
								- Related: ((63904f3d-8ecf-4c85-b7c3-9c1b19778762))
							- [`Math.clz32()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/clz32)
							- [`Math.cos()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cos)
							- [`Math.cosh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/cosh)
							- [`Math.exp()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/exp)
							- [`Math.expm1()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/expm1)
							- [`Math.floor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor)
							  id:: 63904f3d-8ecf-4c85-b7c3-9c1b19778762
							  collapsed:: true
							  Inverse of ((63904f3d-1750-45b8-8d71-64b745cbf61f))
								- The **`Math.floor()`** function always rounds down and returns the largest integer less than or equal to a given number.
								- Examples
									- ```javascript
									  console.log(Math.floor(5.95));
									  // expected output: 5
									  
									  console.log(Math.floor(5.05));
									  // expected output: 5
									  
									  console.log(Math.floor(5));
									  // expected output: 5
									  
									  console.log(Math.floor(-5.05));
									  // expected output: -6
									  
									  ```
							- [`Math.fround()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/fround)
							- [`Math.hypot()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot)
							- [`Math.imul()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/imul)
							- [`Math.log()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log)
							- [`Math.log10()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log10)
							- [`Math.log1p()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log1p)
							- [`Math.log2()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/log2)
							- [`Math.max()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/max)
							  id:: 5c654b22-085e-4bd2-9d05-6e4692cf0929
							  collapsed:: true
								- Meta
									- ((63f2965f-e63c-44c2-89f3-ecd6f644632f))
							- [`Math.min()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/min)
							  id:: 0257c452-a8cc-40b2-b47a-235d81f263ce
							  collapsed:: true
							  ((63f90e8f-6ac5-4eff-ad9f-4aa51f3a52a1))
								- Returns the smallest of the numbers given as input parameters.
								  id:: 63f90e8f-6ac5-4eff-ad9f-4aa51f3a52a1
								- Syntax
									- collapsed:: true
									  ```javascript
									  Math.min()
									  Math.min(value0)
									  Math.min(value0, value1)
									  Math.min(value0, value1, /* … ,*/ valueN)
									  ```
										- Parameters
											- `value1`, …, `valueN` : Zero or more numbers among which the lowest value will be selected and returned.
										- Return value
											- The smallest of the given numbers. Returns [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN) if any of the parameters is or is converted into `NaN`. Returns [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity) if no parameters are provided.
								- Meta
									- ((63f2965f-e63c-44c2-89f3-ecd6f644632f))
									  id:: 63fd17fd-f540-463e-8b0e-a6bb94bacff9
								- Examples
									- ```javascript
									  console.log(Math.min(2, 3, 1));
									  // Expected output: 1
									  
									  console.log(Math.min(-2, -3, -1));
									  // Expected output: -3
									  
									  const array1 = [2, 3, 1];
									  
									  console.log(Math.min(...array1));
									  // Expected output: 1
									  ```
									- ((63f8a449-3ee5-4ca1-9c55-1ac8dc03ec0a))
										- {{embed ((63f8fe4c-b210-4d07-b282-4fb0d47a4d9e))}}
									- ((63f8a449-3ee5-4ca1-9c55-1ac8dc03ec0a))
										- {{embed ((63f8fe4c-40d8-4b0a-ab4e-2a9bc13c179a))}}
							- [`Math.pow()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/pow)
							  id:: 663a5793-5383-439e-bf6e-f7b2edc6dca1
							  collapsed:: true
							  Inverse of ((63baa388-e728-4ca8-b999-71ccffc091b4))
								- The **`Math.pow()`** static method returns the value of a base raised to a power. That is ` 𝙼𝚊𝚝𝚑.𝚙𝚘𝚠 ( 𝚡 , 𝚢 ) = x y `
								- Syntax
									- ```js
									  Math.pow(base, exponent)
									  ```
								- Examples
									- ```js
									  console.log(Math.pow(7, 3));
									  // Expected output: 343
									  
									  console.log(Math.pow(4, 0.5));
									  // Expected output: 2
									  
									  console.log(Math.pow(7, -2));
									  // Expected output: 0.02040816326530612
									  //                  (1/49)
									  
									  console.log(Math.pow(-7, 0.5));
									  // Expected output: NaN
									  ```
									- [Sum of odd numbers | Codewars](https://www.codewars.com/kata/55fd2d567d94ac3bc9000064/javascript)
									  ```js
									  function rowSumOddNumbers(n) {
									    return Math.pow(n, 3);
									  }
									  ```
									- [Find the next perfect square! | Codewars](https://www.codewars.com/kata/56269eb78ad2e4ced1000013/javascript)
									  ```js
									  function findNextSquare(sq) {
									    var number = Math.sqrt(sq);
									    if(Math.round(number) === number) {
									      return Math.pow(++number, 2)
									    }
									    return -1;
									  }
									  ```
							- [`Math.random()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random)
							- [`Math.round()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round)
							- [`Math.sign()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sign)
							- [`Math.sin()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sin)
							- [`Math.sinh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sinh)
							- [`Math.sqrt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt)
							  id:: 63baa388-e728-4ca8-b999-71ccffc091b4
							  collapsed:: true
							  Inverse of ((663a5793-5383-439e-bf6e-f7b2edc6dca1))
								- Examples
									- ((63baa388-27f4-48ce-9808-643b128297a7)) : ((63f29ee4-1022-4275-a0ec-1dc01640e128))
										- {{embed ((63f29ee4-1022-4275-a0ec-1dc01640e128))}}
							- [`Math.tan()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/tan)
							- [`Math.tanh()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/tanh)
							- [`Math.trunc()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/trunc)
					- [`Date`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
				- Text processing
					- [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
					  id:: 64024e3f-d75a-46c3-98e3-e4679ebc4b50
					  collapsed:: true
						- Documentation
							- String methods cheatsheet
							  id:: 63484525-06f3-4d0d-a0cc-2c93b0f6be60
							  collapsed:: true
								- ```javascript
								  "Hello".charAt(4) 				// o
								  "Hello".concat("", "world")		// Hello world
								  "Hello".startsWith("H")			// true
								  "Hello".endsWith("o")			// true
								  "Hello".includes("x")			// false
								  "Hello".indexOf("I")			// 2
								  "Hello".lastIndexOf("I")		// 3
								  "Hello".match(/[A-Z]/g)			// ['H']
								  "Hello".padStart(6, "?")		// ?Hello
								  "Hello".padEnd(6, "?")			// Hello?
								  "Hello".repeat(3)				// HelloHelloHello
								  "Hello".replace("llo", "y")		// Hey
								  "Hello".search('e')				// 1
								  "Hello".slice(l, 3)				// el
								  "Hello".split("")				// ['H', 'E', 'L', 'L', 'O']
								  "Hello".substring(2, 4)			// ll
								  "Hello".toLowerCase()			// hello
								  "Hello".toUpperCase()			// HELLO
								  " Hello ".trim()				// Hello
								  " Hello ".trimStart()			// "Hello "
								  " Hello ".timEnd()				// " Hello"
								  ```
						- Constructor
							- [`String() constructor`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/String)
							  id:: 6488932a-5cd5-4e35-9412-bdaeff5fb153
							  collapsed:: true
								- The **`String()`** constructor creates [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) objects. When called as a function, it returns primitive values of type String.
								- Syntax
									- ```js
									  new String(thing)
									  String(thing)
									  ```
										- Parameters
											- `thing` = Anything to be converted to a string.
										- Return value
											- When `String` is called as a constructor (with `new`), it creates a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) object, which is **not** a primitive.
											- When `String` is called as a function, it coerces the parameter to a string primitive. [Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol) values would be converted to `"Symbol(description)"`, where `description` is the [description](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/description) of the Symbol, instead of throwing.
								- Examples
									- Can convert any data type to a string
									  id:: 64889457-d7d5-4fe8-bbf5-538be01ddd56
										- ```js
										  let number = 234;
										  console.log(String(number));
										  // "234"
										  ```
								- Related: ((638d0621-ae57-4cbc-b873-1bbcffc158dd))
						- Properties
							- [`String length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
							  id:: 67376787-9f90-44a8-af46-e7c126b61f00
						- Methods
							- [`String.prototype[@@iterator]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/@@iterator)
							- [`String.prototype.at()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/at)
							- [`String.prototype.lastIndexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf)
							- [`String.prototype.charAt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt)
							  id:: 6345ae08-f477-4d93-8a9e-e1825a4dbf30
							  collapsed:: true
							  ((63baa388-00f3-4cf9-9e71-e74211713820))
								- Can be used instead of bracket notation (e.g. `String[index]`) to return the character at the specified offset. It's recommended as it's more accurate in edge cases
								  id:: 63baa388-00f3-4cf9-9e71-e74211713820
								  collapsed:: true
									- NOTE:  `charAt`  is preferable than using  `[ ]`  ([bracket notation](http://forum.freecodecamp.com/t/javascript-string-prototype-touppercase/15950)) as  `str.charAt(0)`  returns an empty string (`''`) for  `str = ''`  instead of  `undefined`  in case of  `''[0]` .
									- ```javascript
									  var string = "freeCodecamp";
									  
									  string.charAt(0); // Returns "f"
									  ```
							- [`String.prototype.charCodeAt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt)
							  id:: 63904f3d-d998-45d3-9f94-c97030425ec2
							  collapsed:: true
							  ((63f215db-3662-4702-823a-59316716ef34))
								- Can return an integer between `0` and `65535` representing the UTF-16 code  unit at the given index e.g. to identify the type of character, alphabetical order, etc
								  id:: 63f215db-3662-4702-823a-59316716ef34
								- Syntax = `charCodeAt(index)`
									- Parameters
									  collapsed:: true
										- `index`: An integer greater than or equal to `0` and less than the `length` of the string. If `index` is not a number, it defaults to `0`.
										- Return value = A number representing the UTF-16 code unit value of the character at the given `index`. If `index` is out of range, `charCodeAt()` returns [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN)
								- Meta
									- If just checking for letters, you can use greater or less than operators instead
										- e.g. `if (character > "m")` to check for letters that start with `n` or after
								- Examples
									- ((63736445-7ccf-467e-a7ca-877a38cfd6a5))
										- {{embed ((63736445-7ccf-467e-a7ca-877a38cfd6a5))}}
								- charCodeAt uses `utf-16`
									- [UTF-16 table](https://asecuritysite.com/coding/asc2)
									- ![ASCII table.pdf](../assets/ASCII_table_1677780764579_0.pdf)
									  id:: 646349b0-26df-4b6d-9ae4-46abda612f2f
										- Related: ((64634976-9fee-489a-b73a-2349e05c35ee))
								- Related: ((63470fd1-b8ce-43b2-ab22-5ba17988fc3e)) : ((63f2175c-19f9-4a8e-8c4a-7443cf99d71e))
							- [`String.prototype.codePointAt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/codePointAt)
							- [`String.prototype.concat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat)
							- [`String.prototype.endsWith()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith)
							  id:: 63fdd9d7-2555-4f15-8f94-798587be6b3c
							  collapsed:: true
								-
							- [`String.fromCharCode()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCharCode)
							- [`String.fromCodePoint()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fromCodePoint)
							- [`String.prototype.includes()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes)
							  id:: adf5843f-68dc-4059-9634-3059f69a6635
							  collapsed:: true
								- The `includes()` method performs a case-sensitive search to determine whether one string may be found within another string, returning  `true`  or  `false`  as appropriate.
								- Syntax
									- ```javascript
									  includes(searchString)
									  includes(searchString, position)
									  ```
										- `searchString` = A string to be searched for within str. Cannot be a regex.
										- `position` (Optional) = The position within the string at which to begin searching for searchString. (Defaults to `0`)
								- Example
									- ```javascript
									  const sentence = 'The quick brown fox jumps over the lazy dog.';
									  
									  const word = 'fox';
									  
									  console.log(`The word "${word}" ${sentence.includes(word) ? 'is' : 'is not'} in the sentence`);
									  // expected output: "The word "fox" is in the sentence"
									  ```
								- Related: ((d0a968a6-4f22-48e4-ae07-45629e7372db))
							- [`String.prototype.indexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)
							  id:: 63470fd1-d1aa-49cd-95ec-4a5a0cf2ef74
							  collapsed:: true
								- Can return the first index at which a given character can be found, or `-1` if it is not present.
								  id:: 63f298d8-e92e-4e36-bfa2-37818da7cf4d
								- Examples
								  id:: 6363f739-1d16-4b36-80d0-a39fba2e06a3
								  collapsed:: true
									- `name.indexOf('$')` can find a specific character (`$`) in the `name` string
								- Related: ((63679853-7115-4961-bd6b-0b224f149a11))
							- [`String.prototype.localeCompare()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/localeCompare)
							- [`String.prototype.match()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match)
							  id:: 63470fd1-1f37-4428-9546-d674c323d5d1
							  collapsed:: true
								- Can check for how many times characters appear in a given string. Creates an array with each item being the characters matched.
								  id:: 63baa388-24f2-42ae-913a-d2efcaf9f4bf
								- Return value
									- An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) whose contents depend on the presence or absence of the global ( `g` ) flag, or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null) if no matches are found.
									  collapsed:: true
										- If the  `g`  flag is used, all results matching the complete regular expression will be returned, but capturing groups are not included.
										- If the  `g`  flag is not used, only the first complete match and its related capturing groups are returned. In this case,  `match()`  will return the same result as [`RegExp.prototype.exec()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec) (an array with some extra properties).
								- Example
									- ((6347b540-6c5c-4871-b4b7-cbebe82269ec))
										- {{embed ((6347b54a-7668-432a-bc12-16c412332310))}}
									- ((6359001a-4d38-47e3-95bd-5a3b8a18050c))
										- {{embed ((63904f3d-9b31-4b9f-9ab7-ae0c533a0abd))}}
									- ((63ecd217-58e0-4ebf-add2-fadb54b6ed59))
										- {{embed ((db967743-4408-46dc-a72c-7a0efcc2f248))}}
								- Related: ((6345ae08-b3a7-40fb-bd6a-35c0918159e5))
							- [`String.prototype.matchAll()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/matchAll)
							  id:: 663a5793-2dc7-4416-87b6-5dc83940108c
							- [`String.prototype.normalize()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/normalize)
							- [`String.prototype.padEnd()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padEnd)
							- [`String.prototype.padStart()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padStart)
							- [`String.raw()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/raw)
							- [`String.prototype.repeat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/repeat)
							  id:: 63f33e7c-dd58-4555-93f9-15a02fe35376
							  collapsed:: true
							  Constructs and returns a new string which contains the specified number of copies of the string on which it was called, concatenated together.
								- Example
									- ```javascript
									  const mood = 'Happy! ';
									  
									  console.log(`I feel ${mood.repeat(3)}`);
									  // Expected output: "I feel Happy! Happy! Happy! "
									  ```
									- ((63f8aa8f-f4e4-4d1a-816a-df61b5e19dcc))
									  collapsed:: true
										- {{embed ((63f8aaa0-96f7-487f-ac99-d752662f0a56))}}
							- [`String.prototype.replace()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
							  id:: 63470fd1-5259-4cdb-a208-b49d213b679b
							  collapsed:: true
							  ((63baa388-4fe1-416f-a1b2-6e3755f6aede))
								- Can replace one or more characters in a string using RegExp
								  id:: 63baa388-4fe1-416f-a1b2-6e3755f6aede
									- Related: ((6347b429-ccfa-48c2-9891-da957cb3f19a))
									- Related: ((634da2ed-17ad-4770-98b1-6e36134ee107))
								- Syntax
								  id:: 6347bb76-7433-4187-a62d-eb89f1835d14
									- ```javascript
									  replace(pattern, replacement)
									  ```
										- `pattern`
											- Can be a string or an object with a ((ad29df8c-e612-449e-b366-2eeaa53b0c1e)) method — the typical example being a ((6345ae08-b3a7-40fb-bd6a-35c0918159e5)). Any value that doesn't have the  ((ad29df8c-e612-449e-b366-2eeaa53b0c1e))  method will be coerced to a string.
										- `replacement`
											- Can be a string or a function.
											- If it's a string, it will replace the substring matched by  `pattern` . A number of special replacement patterns are supported; see the [Specifying a string as the replacement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace#specifying_a_string_as_the_replacement) ( ((ad29df8c-e612-449e-b366-2eeaa53b0c1e)) )section below.
											- If it's a function, it will be invoked for every match and its return value is used as the replacement text. The arguments supplied to  this function are described in the [Specifying a function as the replacement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace#specifying_a_function_as_the_replacement) section below.
								- Examples
									- ```javascript
									  const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';
									  
									  console.log(p.replace('dog', 'monkey'));
									  // expected output: "The quick brown fox jumps over the lazy monkey. If the dog reacted, was it really lazy?"
									  ```
									- Can also replace using regex instead
									  ```javascript
									  const regex = /Dog/i;
									  console.log(p.replace(regex, 'ferret'));
									  // expected output: "The quick brown fox jumps over the lazy ferret. If the dog reacted, was it really lazy?"
									  ```
									- ((63904f3d-b859-416a-af40-5ddf0b9b30ab))
										- {{embed ((63904f3d-b859-416a-af40-5ddf0b9b30ab))}}
									- ((84ff6676-f0d0-41f1-9e1a-1418ee207d16))
										- {{embed ((84ff6676-f0d0-41f1-9e1a-1418ee207d16))}}
									- ((639aedfe-27f9-4fd6-bb60-e207723da798))
										- {{embed ((63baa387-5558-4306-bd11-22353a8b4d6d))}}
								- Related: ((63470fd1-332b-4ebf-965d-7073b319c11b))
							- [`String.prototype.replaceAll()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replaceAll)
							  id:: 63470fd1-78ae-41e3-a0b5-43bf0527755d
							  collapsed:: true
								- Newer method, not available in all environments. Alternatively use ((63470fd1-5259-4cdb-a208-b49d213b679b)) with regex using g (global) modifier
								- Examples
									- ```js
									  const paragraph = "I think Ruth's dog is cuter than your dog!";
									  
									  console.log(paragraph.replaceAll('dog', 'monkey'));
									  // Expected output: "I think Ruth's monkey is cuter than your monkey!"
									  
									  // Global flag required when calling replaceAll with regex
									  const regex = /Dog/gi;
									  console.log(paragraph.replaceAll(regex, 'ferret'));
									  // Expected output: "I think Ruth's ferret is cuter than your ferret!"
									  ```
									- ((66bcd59d-2f68-46bb-a8f3-fa69662a2550))
								- Related: ((63470fd1-332b-4ebf-965d-7073b319c11b))
							- [`String.prototype.search()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search)
							  id:: 663a5793-fa23-43c4-812a-2c149e261114
							  collapsed:: true
								-
							- [`String.prototype.slice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice)
							  id:: 63470fd1-335a-43ad-be82-547be1c10d07
							  collapsed:: true
							  ((63f2995e-3c1d-4961-8d40-38ed8cd83373))
								- Can be used to remove characters from a string
								  id:: 63f2995e-3c1d-4961-8d40-38ed8cd83373
								- To remove the last character from a string in JavaScript, you should use the  `slice()`  method. It takes two arguments: the start index and the end index.  `slice()`  supports negative indexing, which means that  `slice(0, -1)`  is equivalent to  `slice(0, str.length - 1)` .
								- Related: ((634bc0c2-0b68-4da7-83b6-5abefa297cac))
							- [`String.prototype.split()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
							  id:: 63470fd1-c937-4cd7-9301-de009d1fb7e0
							  collapsed:: true
							  Inverse of ((635eb08f-cba9-45d7-a72b-d207d55081db)) | ((63f29878-1bf7-47ea-9b60-6a90394d0c12))
								- Can create a new array by dividing a string into substrings based on a given character or pattern
								  id:: 63f29878-1bf7-47ea-9b60-6a90394d0c12
								- Examples
									- ```javascript
									  const str = 'The quick brown fox jumps over the lazy dog.';
									  
									  const words = str.split(' ');
									  console.log(words);
									  // expected output: ['The', 'quick', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog.']
									  console.log(words[3]);
									  // expected output: "fox"
									  ```
									- ```javascript
									  const number = 123456;
									  let newWords = str.toString().split('');
									  console.log(newWords);
									  //expected output: [ "1", "2", "3", "4", "5", "6" ]
									  ```
							- [`String.prototype.startsWith()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith)
							- [`String.prototype.substring()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring)
							  collapsed:: true
								-
							- [`String.prototype.toLocaleLowerCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLocaleLowerCase)
							- [`String.prototype.toLocaleUpperCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLocaleUpperCase)
							- [`String.prototype.toLowerCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)
							- [`String.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toString)
							  id:: 63470fd1-b8ce-43b2-ab22-5ba17988fc3e
							  collapsed:: true
							  ((63f29a8b-25b6-4d4a-a671-068a6eff4ca9))
								- Can convert a number to a string
								  id:: 63f29a8b-25b6-4d4a-a671-068a6eff4ca9
								- Example
								  collapsed:: true
									- `num.toString()` converts a number to a string
								- Related: ((638d0621-ae57-4cbc-b873-1bbcffc158dd)) : ((63f2175c-19f9-4a8e-8c4a-7443cf99d71e))
							- [`String.prototype.toUpperCase()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase)
							  id:: 63470fd1-5ac6-4b0c-a9ee-f54e0c50692f
							  collapsed:: true
							  ((63f29a65-5fa1-4742-b615-5b45a1bfac86))
								- Can convert a string to uppercase
								  id:: 63f29a65-5fa1-4742-b615-5b45a1bfac86
								- Example
								  collapsed:: true
									- ```javascript
									  let text = "Hello World!";
									  let result = text.toUpperCase();
									  ```
							- [`String.prototype.trim()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/Trim)
							- [`String.prototype.trimEnd()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trimEnd)
							- [`String.prototype.trimStart()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trimStart)
							- [`String.prototype.valueOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf)
							- *Deprecated*
							  collapsed:: true
								- [`String.prototype.anchor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/anchor) (Deprecated)
								- [`String.prototype.italics()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/italics) (Deprecated)
								- [`String.prototype.big()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/big) (Deprecated)
								- [`String.prototype.blink()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/blink) (Deprecated)
								- [`String.prototype.small()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/small) (Deprecated)
								- [`String.prototype.sup()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/sup) (Deprecated)
								- [`String.prototype.strike()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/strike) (Deprecated)
								- [`String.prototype.sub()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/sub) (Deprecated)
								- [`String.prototype.substr()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr) (Deprecated)
								- [`String.prototype.bold()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/bold) (Deprecated)
								- [`String.prototype.link()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/link) (Deprecated)
								- [`String.prototype.fixed()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fixed) (Deprecated)
								- [`String.prototype.fontcolor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fontcolor) (Deprecated)
								- [`String.prototype.fontsize()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/fontsize) (Deprecated)
					- [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)
					  id:: 6345ae08-b3a7-40fb-bd6a-35c0918159e5
					  collapsed:: true
					  AKA Regular Expressions
						- # Syntax
							- ```javascript
							  new RegExp(pattern)
							  new RegExp(pattern, flags)
							  RegExp(pattern)
							  RegExp(pattern, flags)
							  ```
							- `pattern` = The text of the regular expression. This can also be another  `RegExp`  object.
								- Examples
									- `/``something``/` = what's between the `/` signifies what text to look for
									  id:: 66bcda69-ebaa-46cb-8ac6-3b4797a2b46a
									- `[abcd]` = look for each of these characters
									  id:: 66bcdaa8-499c-4e30-8ae8-1807ae820ef7
									- `[a-z]` = look for a character between and including a-z
									  id:: 6367aa0a-f0bf-42da-890e-15afa26b796b
									- `+` = 1 or more characters
									  id:: 6367aa1c-ddf7-4f96-97ec-269a578030a2
									- `\d` = followed by the character `d`
									  id:: 6367aaaa-01a0-4f99-a6a5-ed0224007f9a
							- `flags`  Optional
							  collapsed:: true
								- If specified,  `flags`  is a string that contains the flags to add. Alternatively, if a  `RegExp`  object is supplied for the  `pattern` , the  `flags`  string will replace any of that object's flags (and  `lastIndex`  will be reset to  `0` ).
								- `flags`  may contain any combination of the following characters:
									- [`g`  (global)](((63470fd1-b26f-45d0-967a-1c746f835cfc))) : Find all matches rather than stopping after the first match.
									  id:: 63679853-5edb-4076-9cc2-53971f791893
										- ((63a3afae-a986-4d53-acfa-a72c13b9fc86))
											- ((63a48de6-a0bd-4ca1-8e6f-c84109bcaf43))
									- [`i`  (ignore case)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/ignoreCase) : When matching, casing differences are ignored.
									  id:: 663a5793-a50a-4b0f-8c7e-6fdfd3a0a9b3
									- [`d`  (indices)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/hasIndices) : Generate indices for substring matches.
									- [`m`  (multiline)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/multiline) : Treat beginning and end assertions ( `^`  and  `$` ) as working over multiple lines. In other words, match the beginning or end of *each* line (delimited by  `\n`  or  `\r` ), not only the very beginning or end of the whole input string.
									- [`s`  (dotAll)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/dotAll) : Allows  `.`  to match newlines.
									- [`u`  (unicode)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/unicode) : Treat  `pattern`  as a sequence of Unicode code points.
									- [`y`  (sticky)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/sticky) : Matches only from the index indicated by the  `lastIndex`  property of this regular expression in the target string. Does not attempt to match from any later indexes.
						- # Examples
							- id:: 6367a9d1-bce9-4bfe-8864-3948c102e007
							  ```javascript
							  const text = 'the dog5 jumped high';
							  const re = /[a-z]+\d/g
							  console.log(re.text(text));
							  // expected output: true
							  ```
								- ((6367aa0a-f0bf-42da-890e-15afa26b796b))
								- ((6367aa1c-ddf7-4f96-97ec-269a578030a2))
								- ((6367aaaa-01a0-4f99-a6a5-ed0224007f9a))
								- ((63679853-5edb-4076-9cc2-53971f791893))
							- `/([^])\1+/`
								- `[^]` matches any character, including newline
								- `\1` matches the same text as most recently matched by the 1st capturing group
								- `+` matches the previous token between one and unlimited times, as many times as possible, giving back as needed (greedy)
							- ((63a3afb0-f24c-4e0f-9c9a-00caeffabb6b))
							- ((63f2a18f-1978-40f0-b4b6-815da6b62041))
							- ((66bcd59d-2f68-46bb-a8f3-fa69662a2550))
								- {{embed ((3a79d84c-5151-4266-92d2-0bff4950d7cf))}}
						- # Properties
							- [`get RegExp[@@species]`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@species)
							- [`RegExp.prototype.dotAll`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/dotAll)
							- [`RegExp.prototype.flags`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/flags)
							- [`RegExp.prototype.global`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/global)
							  id:: 63470fd1-b26f-45d0-967a-1c746f835cfc
							  collapsed:: true
							  AKA `g` flag
								- The `global` accessor property indicates whether or not the g flag is used with the regular expression.
								- Example
									- ```javascript
									  const regex1 = new RegExp('foo', 'g');
									  
									  console.log(regex1.global);
									  // expected output: true
									  
									  const regex2 = new RegExp('bar', 'i');
									  
									  console.log(regex2.global);
									  // expected output: false
									  
									  ```
								- How to use the `g` flag
									- Example
										- ```javascript
										  mystring = mystring.replace(/test/g, mystring);
										  ```
										- ```javascript
										  var mystring = "hello world test world";
										  var find = "world";
										  var regex = new RegExp(find, "g");
										  alert(mystring.replace(regex, "yay")); // alerts "hello yay test yay"
										  ```
											- As a function
											  ```javascript
											  replaceGlobally(original, searchTxt, replaceTxt) {
											      const regex = new RegExp(searchTxt, 'g');
											      return original.replace(regex, replaceTxt) ;
											  }
											  ```
							- [`RegExp.prototype.hasIndices`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/hasIndices)
							- [`RegExp.prototype.ignoreCase`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/ignoreCase)
							  id:: 63470fd1-ffa6-4c1f-9d5b-88dd4374c543
							  AKA `i` flag
							- [`RegExp.input ($_)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/input) (Non-standard)
							- [`RegExp: lastIndex`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/lastIndex)
							- [`RegExp.lastMatch ($&)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/lastMatch) (Non-standard)
							- [`RegExp.lastParen ($+)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/lastParen) (Non-standard)
							- [`RegExp.leftContext ($`)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/leftContext) (Non-standard)
							- [`RegExp.prototype.multiline`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/multiline)
							- [`RegExp.$1-$9`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/n)
							- [`RegExp.rightContext ($')`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/rightContext) (Non-standard)
							- [`RegExp.prototype.source`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/source)
							  collapsed:: true
								- Read-only property
							- [`RegExp.prototype.sticky`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/sticky)
							- [`RegExp.prototype.unicode`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/unicode)
						- # Methods
						  id:: 63470fd1-c9a9-4a92-a92a-7c9fafdac157
							- [`RegExp.prototype[@@match]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@match)
							  id:: 63470fd1-6951-493e-9e6b-6151b68269a1
							  collapsed:: true
							  Returns an array containing all of the matches, including capturing groups, or  `null`  if no match is found.
								- The **`[@@match]()`** method of a regular expression specifies how [`String.prototype.match()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match) should behave. In addition, its presence (or absence) can influence whether an object is regarded as a regular expression.
								- Example
									- ```javascript
									  class RegExp1 extends RegExp {
									    [Symbol.match](str) {
									      const result = RegExp.prototype[Symbol.match].call(this, str);
									      if (result) {
									        return 'VALID';
									      }
									      return 'INVALID';
									    }
									  }
									  
									  console.log('2012-07-02'.match(new RegExp1('([0-9]+)-([0-9]+)-([0-9]+)')));
									  // expected output: "VALID"
									  ```
									- [String ends with?](https://www.codewars.com/kata/51f2d1cafc9c0f745c00037d)
										- ```javascript
										  function solution(str, ending){
										    var l = ending.length;
										    var str = str.slice(-l);
										    return str.match(ending) ? true : false;
										  }
										  ```
									- ((6401f353-f6bc-44da-9e8e-6128381908c8))
										- {{embed ((5ea4d18a-04f9-49d8-8ea9-5343e80b2316))}}
								- Related: ((63470fd1-76ac-435d-abf4-bca22c9baf5c))
							- [`RegExp.prototype[@@matchAll]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@matchAll)
							  id:: 63470fd1-76ac-435d-abf4-bca22c9baf5c
							  collapsed:: true
							  Returns an iterator containing all of the matches, including capturing groups.
								- Related: ((63470fd1-6951-493e-9e6b-6151b68269a1))
							- [`RegExp.prototype[@@replace]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@replace)
							  id:: 63470fd1-332b-4ebf-965d-7073b319c11b
							  collapsed:: true
							  Executes a search for a match in a string, and replaces the matched substring with a replacement substring.
								- ((63470fd1-78ae-41e3-a0b5-43bf0527755d)) = Executes a search for all matches in a string, and replaces the matched substrings with a replacement substring.
								- Can replace all given characters in a string with the `g` flag
								  id:: 63f297c1-a028-4e79-a600-e12e670fbca2
								- Examples
									- Given a string, this will remove the vowels from it
									  ```javascript
									  function disemvowel(str) {
									    return str.replace(/[aeiou]/gi, ''); // g + i flags
									  }
									  ```
									- ((6348574a-5ac4-4df9-99f1-1806bc0025f1))
										- {{embed ((63904f3d-760d-4bcb-993f-bfcfb5e2cce0))}}
										- Can replace all given characters in a string with the `g` flag
							- [`RegExp.prototype[@@search]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@search)
							  id:: 63470fd1-89fb-4e50-8ef8-14e05d96a727
							  Tests for a match in a string. It returns the index of the match, or  `-1`  if the search fails.
							- [`RegExp.prototype[@@split]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/@@split)
							  id:: 63470fd1-8016-47b5-ad4c-dd2015ad5be9
							  Uses a regular expression or a fixed string to break a string into an array of substrings.
							- [`RegExp.prototype.exec()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/exec)
							  id:: 63470fd1-44ff-442e-89fc-2acc67948977
							  Executes a search for a match in a string. It returns an array of information or  `null`  on a mismatch.
							- [`RegExp.prototype.test()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/test)
							  id:: 85fecdc2-4e32-4a5d-a102-51e4adb6069c
							  collapsed:: true
							  Executes a search for a match between a  regular expression and a specified string. Returns `true` or  `false`.
								- Examples
							- [`RegExp.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/toString)
							  Returns a string representing the regular expression.
							- (Deprecated) [`RegExp.prototype.compile()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp/compile)
							- ((64024e3f-d75a-46c3-98e3-e4679ebc4b50))
								- ((63470fd1-1f37-4428-9546-d674c323d5d1))
								- ((63470fd1-1f37-4428-9546-d674c323d5d1))
								- ((63470fd1-5259-4cdb-a208-b49d213b679b))
								- ((63470fd1-78ae-41e3-a0b5-43bf0527755d))
								- ((663a5793-fa23-43c4-812a-2c149e261114))
								- ((63470fd1-c937-4cd7-9301-de009d1fb7e0))
						- [Learning Resources]
							- RegEx builder
								- [regex101: build, test, and debug regex](https://regex101.com/)
								- [RegExr: Learn, Build, & Test RegEx](https://regexr.com/)
							- Documentation
							  id:: 63470fd1-0426-4360-b9d4-b98c8ca7217f
								- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
								  collapsed:: true
									- Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects.
									- You construct a regular expression in one of two ways:
									  collapsed:: true
										- Using a regular expression literal
										  collapsed:: true
											- consists of a pattern enclosed between slashes
											- ```javascript
											  const re = /ab+c/;
											  ```
											- They provide compilation of the regular expression when the script is loaded. If the regular expression remains constant, using this can improve performance.
										- Or calling the constructor function of the RegExp object, as follows:
										  collapsed:: true
											- ```javascript
											  const re = new RegExp('ab+c');
											  ```
											- Using the constructor function provides runtime compilation of the regular expression. Use the constructor function when you know the regular expression pattern will be changing, or you don't know the pattern and are getting it from another source, such as user input.
									-
								- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Cheatsheet
								  collapsed:: true
									- Aggregates parts of the individual special characters articles also
								- https://regex101.com/
								- https://regexcrossword.com/
								- [Regular-Expressions.info - Regex Tutorial, Examples and Reference - Regexp Patterns](https://www.regular-expressions.info)
						- Related: ((63470fd1-1f37-4428-9546-d674c323d5d1))
				- Indexed Collections
					- [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
					  id:: 64024e3f-2a66-4456-816f-f0b00cfd0c4e
					  collapsed:: true
						- Properties
							- [`get Array[@@species]`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@species)
							- [`Array.prototype[@@unscopables]`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@unscopables)
							- [`Array.prototype.length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length)
						- Methods
						  id:: 63baa387-bb13-4434-80c9-78e3d6f14485
							- Meta
								- Image of various methods
								  collapsed:: true
									- ![image.png](../assets/image_1667948247803_0.png)
										- Two small issues:
											- Order of arguments:  `.fill(value, start)`
											- The method names are  `.findIndex()`  and  `.indexOf()` .
								- Immutable vs Mutable Array Methods
								  collapsed:: true
								  id:: 636d1397-3729-49ea-bdd0-7f5745334aa8
									- Some mutable array methods i.e. they alter the original array
										- ((63679853-27fd-40a4-bd44-b836c61f4394))
										- ((63679853-975f-4456-b131-53731a001078))
										- ((63679853-dcb7-4c52-a93f-2ba70da4b082))
										- ((63679853-f388-4ef7-98f4-ccfcebf4cd89))
										- ((635eb08f-bc21-4a5c-baa9-813d9170753a))
										- ((63470fd1-5c6c-4c4d-aea0-9d111a003975))
										- ((634bc0c2-38ee-4fdb-b785-2b19b9d2a6e1))
									- Some immutable array methods i.e. doesn't alter the original array
										- ((635eb08f-48a4-41e1-9112-9f62670ddec2))
										- ((63679853-a37a-4046-8ccc-7841dfaa48a9))
										- ((63470fd1-ed0f-45f6-9b63-2ee67c3c152f)) -
										- ((63679853-bf0c-44a1-9fba-087790dbcc45))
										- ((63679853-9c2f-4df7-859c-e2278dbebdb7))
										- ((6350374d-fdba-4eb4-b17a-f80e5e5a3fcb)) - creates a new array which we can then run code on
										- ((63679853-1c98-454a-8932-e67322c119d9))
										- ((634bc0c2-0b68-4da7-83b6-5abefa297cac))
									- ((63642a10-4e86-4101-961a-8311efb8ae4f)) is often used as an alternative
										- Immutable alternative to ((63679853-975f-4456-b131-53731a001078))
											- ```javascript
											  const push = (array, value) => [...array, value];
											  ```
									- Use array method that don’t mutate the original array with React, because mutating arrays in React can lead to issues because it might be comparing that in a virtual dom
									- [Learning Resources]
										- [Immutable Array Methods: Write Cleaner JavaScript Code - SitePoint](https://www.sitepoint.com/immutable-array-methods-javascript/)
									- Related:
										- [[School of Code bootcamp]] : ((636a77ab-9100-4564-b0f6-324cd53f42b9))
										- ((636cce43-e74d-482c-ab56-df86054a8e43))
							- [`Array.prototype[@@iterator]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/@@iterator)
							- [`Array.prototype.at()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/at)
							- [`Array.prototype.concat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)
							  id:: 635eb08f-48a4-41e1-9112-9f62670ddec2
							  collapsed:: true
								- Used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.
								- Immutable method
								- Example
									- ```javascript
									  const array1 = ['a', 'b', 'c'];
									  const array2 = ['d', 'e', 'f'];
									  const array3 = array1.concat(array2);
									  
									  console.log(array3);
									  // expected output: Array ["a", "b", "c", "d", "e", "f"]
									  ```
							- [`Array.prototype.copyWithin()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/copyWithin)
							- [`Array.prototype.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/entries)
							- [`Array.prototype.every()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
							  id:: 63679853-a37a-4046-8ccc-7841dfaa48a9
							  collapsed:: true
							  Check whether every element in the array passes the function's test || Unlike ((63679853-1c98-454a-8932-e67322c119d9)) which requires this for only one elements
								- Tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value
								- Syntax
									- ```javascript
									  // Arrow function
									  every((element) => { /* … */ } )
									  every((element, index) => { /* … */ } )
									  every((element, index, array) => { /* … */ } )
									  
									  // Callback function
									  every(callbackFn)
									  every(callbackFn, thisArg)
									  
									  // Inline callback function
									  every(function(element) { /* … */ })
									  every(function(element, index) { /* … */ })
									  every(function(element, index, array){ /* … */ })
									  every(function(element, index, array) { /* … */ }, thisArg)
									  ```
										- Parameters
											- callbackFn = A function to test for each element.
											- The function is called with the following arguments:
												- element = The current element being processed in the array.
												- index = The index of the current element being processed in the array.
												- array = The array every was called upon.
											- thisArg Optional
											- A value to use as this when executing callbackFn.
										- Return value = `true` if the `callbackFn` function returns a truthy value for every array element. Otherwise, `false`.
								- Meta
									- Make sure to include `return` keyword
								- Examples
									- Check if every number in an array is a multiple of 7 (or 77)
									  ```javascript
									  const sevenTimesTable = [7, 14, 21, 28, 35, 42, 49, 56, 63, 70];
									  
									  const seventySevenTimesTable = [77, 154, 231, 308, 385, 461, 538, 616, 693, 770];
									  
									  // check that every number in the sevenTimesTable array is a multiple of 7.
									  const checkSeven = sevenTimesTable.every((item) => {
									    if (item % 7 === 0) {
									      return item;
									    }
									  })
									  
									  // Check if every number in the seventySevenTimesTable array is a multiple of 77
									  const checkSeventySevens = seventySevenTimesTable.every((item) => {
									    if (item % 77 === 0) {
									      return item;
									    }
									  })
									  // expected output: false - there's one number here which is false
									  ```
									- ```javascript
									  const array1 = [1, 30, 39, 29, 10, 13];
									  
									  const isBelowThreshold = (currentValue) => currentValue < 40;
									  
									  console.log(array1.every(isBelowThreshold));
									  // expected output: true
									  ```
								- Related: ((63679853-bf0c-44a1-9fba-087790dbcc45)) + ((63679853-9c2f-4df7-859c-e2278dbebdb7)) can locate which item fails the `every()` test
							- [`Array.prototype.fill()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)
							- [`Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
							  id:: 63470fd1-ed0f-45f6-9b63-2ee67c3c152f
							  collapsed:: true
							  ((63f2976f-4508-41b5-9d84-47dd345a0990))
								- Can be used to remove anything from an array, such as values that are strings
								  id:: 63f2976f-4508-41b5-9d84-47dd345a0990
								- Syntax
									- collapsed:: true
									  ```javascript
									  // Arrow function
									  filter((element) => { /* … */ } )
									  filter((element, index) => { /* … */ } )
									  filter((element, index, array) => { /* … */ } )
									  
									  // Callback function
									  filter(callbackFn)
									  filter(callbackFn, thisArg)
									  
									  // Inline callback function
									  filter(function(element) { /* … */ })
									  filter(function(element, index) { /* … */ })
									  filter(function(element, index, array){ /* … */ })
									  filter(function(element, index, array) { /* … */ }, thisArg)
									  ```
										- Parameters
											- `callbackFn` = Function is a predicate, to test each element of the array. Return a value that coerces to  `true`  to keep the element, or to  `false`  otherwise.
											- The function is called with the following arguments:
												- `element` = The current element being processed in the array.
												- `index` = The index of the current element being processed in the array.
												- `array` = The array on which  `filter()`  was called.
											- `thisArg` (Optional)  = Value to use as  `this`  when executing  `callbackFn` .
								- Example
									- Using it with an anonymous function
									  ```javascript
									  const ages = [32, 33, 16, 40]; 
									  const result = ages.filter((person) => {
									    return person >= 18;
									  }
									  ```
									- Using with a named function
									  ```javascript
									  const ages = [32, 33, 16, 40]; 
									  const result = ages.filter(checkAdult);
									  
									  function checkAdult(age) { 
									    return age >= 18;
									  }
									  ```
									- Return only animals which start with the letter 'b'
									  ```javascript
									  let animals = [
									      "baboon",
									      "kangaroo",
									      "rhino",
									      "frog",
									      "beaver",
									      "horse",
									      "basalisk",
									    ];
									    
									  let bListAnimals = animals.filter((animal) => {
									    if (animal[0] === "b") {
									      return animal
									    }
									  })
									  ```
									- [[CodeWars - JavaScript]]
									  id:: 63679853-4efd-4035-a2d7-1a23b5d9e3f0
										- ((634fe2de-cb29-41bd-a324-de28e866f009))
											- {{embed ((63679853-8500-48d4-8458-ac65c6842951))}}
										- ((63485e7f-a73d-4dff-aae6-57fe42e82542))
										  id:: 63679853-2a34-4fbe-973b-464a2dd07046
											- {{embed ((63679853-07b8-47a1-bcf7-9a26648c0d5c))}}
										- ((636a274c-f69f-44b4-87a8-b554dd9f09ba))
											- {{embed ((636a2774-a8be-47fb-b610-fc3f4093f239))}}
										- ((63f1fb9a-00ac-4c2f-80d9-92012054b0ed))
											- {{embed ((ae73d48d-e24a-4646-914d-339e2c649502))}}
										- Moving a specific character type within an array to the end of the array, preserving the order otherwise
										  id:: 63f2aa4d-31c4-4f62-817c-a1bfae893094
											- {{embed ((63baa387-1e08-4360-8992-cf71d823a78e))}}
							- [`Array.prototype.find()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
							  id:: 63679853-bf0c-44a1-9fba-087790dbcc45
							  collapsed:: true
							  ((63fdd9d7-f6c7-4b7b-8eda-521c5d014922))
								- Returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, [`undefined`](https://devdocs.io/javascript/global_objects/undefined) is returned.
								  id:: 63fdd9d7-f6c7-4b7b-8eda-521c5d014922
								- Syntax
								  collapsed:: true
									- ```javascript
									  // Arrow function
									  find((element) => { /* … */ } )
									  find((element, index) => { /* … */ } )
									  find((element, index, array) => { /* … */ } )
									  
									  // Callback function
									  find(callbackFn)
									  find(callbackFn, thisArg)
									  
									  // Inline callback function
									  find(function(element) { /* … */ })
									  find(function(element, index) { /* … */ })
									  find(function(element, index, array){ /* … */ })
									  find(function(element, index, array) { /* … */ }, thisArg)
									  ```
									- Parameters
										- `callbackFn`  :Function to execute on each value in the array.
										- The function is called with the following arguments:
											- `element`  :The current element in the array.
											- `index`  :The index (position) of the current element in the array.
											- `array`  :The array that  `find`  was called on.
										- The callback must return a [truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy) value to indicate a matching element has been found.
										- `thisArg`  Optional : Object to use as [ `this` ](https://devdocs.io/javascript/operators/this) inside  `callbackFn` .
									- Return value
										- The first element in the array that satisfies the provided testing function. Otherwise, [ `undefined` ](https://devdocs.io/javascript/global_objects/undefined) is returned.
								- Example
									- ```javascript
									  const array1 = [5, 12, 8, 130, 44];
									  
									  const found = array1.find(element => element > 10);
									  
									  console.log(found);
									  // expected output: 12
									  ```
									- Find an object in an array by one of its properties
									  ```javascript
									  const inventory = [
									    {name: 'apples', quantity: 2},
									    {name: 'bananas', quantity: 0},
									    {name: 'cherries', quantity: 5}
									  ];
									  
									  function isCherries(fruit) {
									    return fruit.name === 'cherries';
									  }
									  
									  console.log(inventory.find(isCherries));
									  // { name: 'cherries', quantity: 5 }
									  ```
									- Using arrow function and destructuring
									  id:: 636ac4ee-356d-4f2d-be6f-00f0343addd9
									  ```javascript
									  const inventory = [
									    {name: 'apples', quantity: 2},
									    {name: 'bananas', quantity: 0},
									    {name: 'cherries', quantity: 5}
									  ];
									  
									  const result = inventory.find(({ name }) => name === 'cherries');
									  
									  console.log(result) // { name: 'cherries', quantity: 5 }
									  ```
									- Chech which number in table is not a multiple of 77
									  ```javascript
									  const seventySevenTimesTable = [77, 154, 231, 308, 385, 461, 538, 616, 693, 770];
									  
									  const result = seventySevenTimesTable.find((number) => {
									    if (number % 77 !== 0) {
									      return number;
									    }
									  // expected output: 461
									  ```
								- e
									- Example - also uses fat arrows
										- ```javascript
										  function marieDavid2ndFriend() {
										    let people = SOCBook.data.people; // this is an array that contains separate objects for each person
										    let marieDavid = people.find(o => o.name === 'Marie David');
										    return marieDavid.name;
										  }
										  ```
										- Can alternatively be written:
										  ```javascript
										  function marieDavid2ndFriend() {
										    let people = SOCBook.data.people; // this is an array that contains separate objects for each person
										    let marieDavid = people.find(o) { // native find() locate object for the person
										    	o.name === 'Marie David');
										    }
										    return marieDavid.name;
										  }
										  ```
									- https://stackoverflow.com/questions/12462318/find-a-value-in-an-array-of-objects-in-javascript
									- `o` is the parameter (which is `obj`)
									- ```javascript
									  function testName(o) {
									  	o.name === 'Marie David'
									  }
									  ```
									- ```javascript
									  () => {}
									  ```
								- Related:
									- If you need the **index** of the found element in the array, use ((63679853-9c2f-4df7-859c-e2278dbebdb7))
									- If you need to find the **index of a value**, use [ `indexOf()` ](https://devdocs.io/javascript/global_objects/array/indexof). (It's similar to [ `findIndex()` ](https://devdocs.io/javascript/global_objects/array/findindex), but checks each element for equality with the value instead of using a testing function.)
									- If you need to find if a value **exists** in an array, use [ `includes()` ](https://devdocs.io/javascript/global_objects/array/includes). Again, it checks each element for equality with the value instead of using a testing function.
									- If you need to find if any element satisfies the provided testing function, use [ `some()` ](https://devdocs.io/javascript/global_objects/array/some).
							- [`Array.prototype.findIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
							  id:: 63679853-9c2f-4df7-859c-e2278dbebdb7
							  collapsed:: true
								- Returns the index of the first element in an array that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned.
								- Syntax
								  collapsed:: true
									- ```javascript
									  // Arrow function
									  findIndex((element) => { /* … */ } )
									  findIndex((element, index) => { /* … */ } )
									  findIndex((element, index, array) => { /* … */ } )
									  
									  // Callback function
									  findIndex(callbackFn)
									  findIndex(callbackFn, thisArg)
									  
									  // Inline callback function
									  findIndex(function(element) { /* … */ })
									  findIndex(function(element, index) { /* … */ })
									  findIndex(function(element, index, array){ /* … */ })
									  findIndex(function(element, index, array) { /* … */ }, thisArg)
									  ```
								- Examples
									- Item '461' isn't a multiple of 77. Find it's index
									  ```javascript
									  const seventySevenTimesTable = [77, 154, 231, 308, 385, 461, 538, 616, 693, 770];
									  
									  const result = seventySevenTimesTable.findIndex((number) => {
									    return number === 461
									  })
									  // expected output: 5
									  ```
									- ```javascript
									  const array1 = [5, 12, 8, 130, 44];
									  
									  const isLargeNumber = (element) => element > 13;
									  
									  console.log(array1.findIndex(isLargeNumber));
									  // expected output: 3
									  
									  ```
								- Related:
									- ((63679853-bf0c-44a1-9fba-087790dbcc45)), which returns the first element that satisfies the testing function (rather than its index)
									- ((63679853-7115-4961-bd6b-0b224f149a11))
							- [`Array.prototype.findLast()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLast)
							  id:: 646349b0-29c2-4fc3-9beb-1582086c806c
							- [`Array.prototype.findLastIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLastIndex)
							  id:: 646349b0-1bfd-4201-a31e-3882ac88972b
							- [`Array.prototype.flat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat)
							- [`Array.prototype.flatMap()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flatMap)
							- [`Array.prototype.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
							  id:: 635eb08f-9a44-4545-88c0-b7064e94f590
							  collapsed:: true
								- Easily run a statement for every item of an array
								- Syntax
									- ```javascript
									  // Arrow function
									  forEach((element) => { /* … */ })
									  forEach((element, index) => { /* … */ })
									  forEach((element, index, array) => { /* … */ })
									  
									  // Callback function
									  forEach(callbackFn)
									  forEach(callbackFn, thisArg)
									  
									  // Inline callback function
									  forEach(function (element) { /* … */ })
									  forEach(function (element, index) { /* … */ })
									  forEach(function (element, index, array) { /* … */ })
									  forEach(function (element, index, array) { /* … */ }, thisArg)
									  ```
									- Parameters
										- `callbackFn`: A function to execute for each element in the array. Its return value is discarded.
											- The function is called with the following arguments:
												- `element`: The current element being processed in the array.
												- `index`: The index of the current element being processed in the array.
												- `array`: The array `forEach()` was called upon.
								- Example
								  id:: 63679459-5a45-446d-a126-f9de8ebb188d
									- ```javascript
									  const user = {
									    name: 'bob', 
									    subscription: {
									      date: '01/01/2022'
									    },
									    hobbies: [
									      'running',
									      'jumping',
									    ],
									  }
									  user.hobbies.forEach(console.log)
									  // expected output:
									  // running 0 [ 'running', 'jumping' ]
									  // running 1 [ 'running', 'jumping' ]
									  ```
									- It's a better way to loop over arrays
									  id:: 6367af82-3703-4412-acb1-e47347b5b08f
										- ```javascript
										  const numbers = [1, 2, 3, 4, 5];
										  numbers.forEach(number => {
										    console.log(`My number: ${number}`);
										  })
										  // expected output:
										  // My number: 1
										  // My number: 2
										  // My number: 3
										  // My number: 4
										  // My number: 5
										  ```
								- [When should you use forEach vs map in Javascript #shorts - YouTube](https://youtu.be/Lv7bojecZ9k)
								  id:: 6367b145-82f1-491d-955a-cee03dc77894
									- Map is when you want to take an array and return it with new elements inside of it. If you just want to run the logic and not make an additional new array, then stick with forEach
									- ```javascript
									  const numbers = [1, 2, 3];
									  // map
									  const newArray = numbers.map(
									    (number) => number * 2
									  );
									  // forEach
									  numbers.forEach(
									    (number) => number * 2
									  );
									  ```
								- Related:
									- ((63679853-c651-4513-ae6a-b293b5290bd8))
									- ((63baa387-c3bf-4f09-8aea-264508378625))
							- [`Array.from()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/from)
							- [`Array.prototype.group()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/group) (Experimental)
							  id:: db03f080-1780-42f1-a473-b02f04ac499a
							- [`Array.prototype.groupToMap()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/groupToMap) (Experimental)
							- [`Array.prototype.includes()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)
							  id:: d0a968a6-4f22-48e4-ae07-45629e7372db
							  collapsed:: true
								- The `includes()` method determines whether an array includes a certain value among its entries, returning `true` or `false` as appropriate.
								- Example
									- ```javascript
									  const pets = ['cat', 'dog', 'bat'];
									  
									  console.log(pets.includes('cat'));
									  // expected output: true
									  
									  console.log(pets.includes('at'));
									  // expected output: false
									  ```
								- Related: ((adf5843f-68dc-4059-9634-3059f69a6635))
							- [`Array.prototype.indexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
							  id:: 63679853-7115-4961-bd6b-0b224f149a11
							  collapsed:: true
								- Can returns the first index at which a given element can be found in the array, or `-1` if it is not present.
								  id:: 63baa387-9c40-4889-908d-e992436eaa72
								- Syntax
									- collapsed:: true
									  ```javascript
									  indexOf(searchElement)
									  indexOf(searchElement, fromIndex)
									  ```
										- Parameters
											- `searchElement` : Element to locate in the array.
											- `fromIndex`  (Optional) : The index to start the search at. If the index is greater than or equal to the array's length, -1 is returned, which means the array will not be searched. If the provided index value is a negative number, it is taken as the offset from the end of the array. Note: if the provided index is negative, the array is still searched from front to back. If the provided index is 0, then the whole array will be searched. Default: 0 (entire array is searched).
										- Return value
											- The first index of the element in the array; **-1** if not found.
										- `indexOf()`  compares  `searchElement`  to elements of the Array using [strict equality](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality) (the same method used by the  `===`  or triple-equals operator).
								- Example
									- ```javascript
									  const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];
									  
									  console.log(beasts.indexOf('bison'));
									  // expected output: 1
									  
									  // start from index 2
									  console.log(beasts.indexOf('bison', 2));
									  // expected output: 4
									  
									  console.log(beasts.indexOf('giraffe'));
									  // expected output: -1
									  ```
									- ((63906cf1-ee3b-481e-9b7e-08ad98c55c5d))
										- {{embed ((63906cf1-ee3b-481e-9b7e-08ad98c55c5d))}}
									- `indexOf` returns `-1` if the given character is not in the string
									  id:: 63f2a699-9092-4fd9-8351-9b303f53f6c4
										- {{embed ((63baa387-5a93-4ed4-a40d-971eadeabbb0))}}
									- ((63ef9163-b156-414c-ba00-27c352c96685)) - finding the multiple that Fizz or Buzz is using can be found by just using it's indexOf
									  id:: 63ef9482-c618-42df-8a29-9c810e3d33f4
										- {{embed ((4234dc95-ef8e-467a-b203-1ea773498b9b))}}
								- Related:
									- ((63679853-9c2f-4df7-859c-e2278dbebdb7))
									- ((63470fd1-d1aa-49cd-95ec-4a5a0cf2ef74))
							- [`Array.isArray()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)
							  id:: 64024e3f-ad1c-4953-807a-ebedd4878008
							  collapsed:: true
								- Related: ((63470fd1-ff2c-4b9a-b116-136a41a52b94)) : ((64084faa-6068-42d4-a193-2263c4b4d039))
							- [`Array.prototype.join()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
							  id:: 635eb08f-cba9-45d7-a72b-d207d55081db
							  collapsed:: true
							  Inverse of ((63470fd1-c937-4cd7-9301-de009d1fb7e0)) | ((63f8a9e5-6b7b-4a44-9416-cdad29be9831))
								- Can create a new string by concatenating all elements of an array or array-like object
								  id:: 63f8a9e5-6b7b-4a44-9416-cdad29be9831
								- Examples
									- ```javascript
									  const elements = ['Fire', 'Air', 'Water'];
									  
									  console.log(elements.join());
									  // expected output: "Fire,Air,Water"
									  
									  console.log(elements.join(''));
									  // expected output: "FireAirWater"
									  
									  console.log(elements.join('-'));
									  // expected output: "Fire-Air-Water"
									  
									  ```
									- ((63f33e7b-3df6-4ff4-81c3-4307a8468e78))
										- {{embed ((63f33e7b-3df6-4ff4-81c3-4307a8468e78))}}
							- [`Array.prototype.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/keys)
							- [`Array.prototype.lastIndexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf)
							  id:: 63904f3d-72c4-40d5-9738-0ae25c6b0e81
							  collapsed:: true
								- It returns the last index at which a given element can be found in the array, or -1 if it is not present. The array is searched backwards, starting at `fromIndex`.
								- Parameters
									- `searchElement`:  Element to locate in the array.
									- `fromIndex` (Optional) : Zero-based index at which to start searching backwards, [converted to an integer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#integer_conversion).
										- Negative index counts back from the end of the array — if `fromIndex < 0`, `fromIndex + array.length` is used.
										- If `fromIndex < -array.length`, the array is not searched and `-1`
										   is returned. You can think of it conceptually as starting at a 
										  nonexistent position before the beginning of the array and going 
										  backwards from there. There are no array elements on the way, so `searchElement` is never found.
										- If `fromIndex >= array.length` or `fromIndex` is omitted, `array.length - 1`
										   is used, causing the entire array to be searched. You can think of it 
										  conceptually as starting at a nonexistent position beyond the end of the
										   array and going backwards from there. It eventually reaches the real 
										  end position of the array, at which point it starts searching backwards 
										  through the actual array elements.
								- **Return value:** The last index of the element in the array; **-1** if not found.
								- Examples
									- Comparing ((63904f3d-72c4-40d5-9738-0ae25c6b0e81)) and ((63679853-7115-4961-bd6b-0b224f149a11)) can be used to easily check for duplicates
									  id:: 63906cf1-ee3b-481e-9b7e-08ad98c55c5d
										- Related: ((639061fa-373b-46c3-9f9f-10e94045b532))
											- {{embed ((63906226-8908-4e27-b387-7012d73337f5))}}
							- [`Array.prototype.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
							  id:: 6350374d-fdba-4eb4-b17a-f80e5e5a3fcb
							  collapsed:: true
								- Can be used to create a new array populated with the results of calling a provided function on every element in the calling array.
								- ((6377ece3-fcd7-4478-bf93-a27d3a9eac32))
								- Meta
									- This returns an array item for each corresponding element. If you want to instead skip certain items, use ((63470fd1-ed0f-45f6-9b63-2ee67c3c152f))
								- Syntax
									- collapsed:: true
									  ```javascript
									  // Arrow function
									  map((element) => { /* … */ })
									  map((element, index) => { /* … */ })
									  map((element, index, array) => { /* … */ })
									  
									  // Callback function
									  map(callbackFn)
									  map(callbackFn, thisArg)
									  
									  // Inline callback function
									  map(function(element) { /* … */ })
									  map(function(element, index) { /* … */ })
									  map(function(element, index, array){ /* … */ })
									  map(function(element, index, array) { /* … */ }, thisArg)
									  ```
										- Parameters
											- `callbackFn` = Function that is called for every element of arr. Each time callbackFn executes, the returned value is added to newArray.
											- The function is called with the following arguments:
												- `element` = The current element being processed in the array.
												- `index` = The index of the current element being processed in the array.
												- `array` = The array map was called upon.
								- Example
									- ```javascript
									  const cats = ["tony", "daisy", "socks", "rockie" ];
									  
									  const capitalisedCats = cats.map((cat) => {
									      return cat.toUpperCase();
									  });
									  
									  console.log(capitalisedCats);
									  ```
									- ```javascript
									  const animals = ['cat', 'dog', 'frog', 'rhino'];
									  
									  // take in each array item
									  const pettedAnimals = animals.map(function (animal) {
									    // concatenate 'petting ' on each array item
									    const pettedAnimal = 'petting ' + animal;
									    // return the new string of the petted animal
									    return pettedAnimal;
									    // .map will eventually return a new array full of these new strings
									  })
									  
									  console.log(pettedAnimals);
									  // expected output: ['petting cat', 'petting dog', 'petting frog', 'petting rhino']
									  console.log(animals);
									  // expected output: ['cat', 'dog', 'frog', 'rhino'];
									  ```
									- Very useful for making a new array from an existing one with extra logic applied
									  ```javascript
									  const numbers = [1, 2, 3];
									  const newArray = numbers.map(
									    (number) => number * 2 
									  )
									  console.log(newArray);
									  // expected output: [2, 4, 6]
									  console.log(numbers == newArray)
									  // expected output: false
									  ```
									- `Array.map(Number)`( ((6350374d-fdba-4eb4-b17a-f80e5e5a3fcb)) + ((66ba4356-1666-4c14-ae60-2c17993d8c76)) ) can convert an array of strings into an array of numbers
									  id:: 6351322c-6b12-4902-b961-9ad79f67c9dc
										- ```javascript
										  value = value.toString()
										  array = value.split("");
										  array = array.map(Number);
										  
										  // or
										  
										  for (let i = 0; i < value; i++) {
										     array = value[i]
										  }
										  
										  ```
										- The long way of writing this out would be:
											- ```javascript
											  ...
											  arr.map(item => Number(item));
											  ```
										- Related: ((63904f3d-8308-421c-b0a0-c1bb897f5b31))
								- ((6367b145-82f1-491d-955a-cee03dc77894))
									- {{embed ((6367b145-82f1-491d-955a-cee03dc77894))}}
								- You can also destructure in maps
								  id:: 636d46f1-35c7-49b1-9692-df489b19b0d8
									- ```jsx
									  const posts = { title: 'hi', author: 'hello', highlights: 'none' }
									  
									  function Main() {
									    return <div>
									      {posts.map(
									        ({ title, date, author, highlights }) => {
									          return <Post 
									          key = {post.postId}
									          />
									        }
									      )} 
									    </div>
									  }
									  ```
								- Related: ((636d1789-e0f8-469b-97c6-4ebdbb7b3c1a))
							- [`Array.of()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/of)
							- [`Array.prototype.pop()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
							  id:: 63679853-27fd-40a4-bd44-b836c61f4394
							  collapsed:: true
							  ((64024d45-68f1-4b21-8fe3-af5d7a8489a3)) | Opposite side to ((63679853-dcb7-4c52-a93f-2ba70da4b082)) | Inverse of ((63679853-975f-4456-b131-53731a001078))
								- (Mutable) Removes the last element from an array and returns it
								  id:: 64024d45-68f1-4b21-8fe3-af5d7a8489a3
								- Gets the last item of an array
								  id:: 636a3cca-5dd4-44ff-92a8-8296b6885173
									- ```javascript
									  const animals = ['cat', 'dog', 'frog', 'rhino'];
									  animals.pop()
									  // expected output: 'rhino'
									  ```
								- Related: ((63679853-f388-4ef7-98f4-ccfcebf4cd89))
							- [`Array.prototype.push()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
							  id:: 63679853-975f-4456-b131-53731a001078
							  collapsed:: true
							  Adds to end of array | Opposite side to ((63679853-f388-4ef7-98f4-ccfcebf4cd89)) | Inverse of ((63679853-27fd-40a4-bd44-b836c61f4394))
								- Syntax
									- ```js
									  push()
									  push(element1)
									  push(element1, element2)
									  push(element1, element2, /* …, */ elementN)
									  ```
								- Examples
									- ```js
									  const animals = ['pigs', 'goats', 'sheep'];
									  
									  const count = animals.push('cows');
									  console.log(count);
									  // Expected output: 4
									  console.log(animals);
									  // Expected output: Array ["pigs", "goats", "sheep", "cows"]
									  
									  animals.push('chickens', 'cats', 'dogs');
									  console.log(animals);
									  // Expected output: Array ["pigs", "goats", "sheep", "cows", "chickens", "cats", "dogs"]
									  ```
									- Adding an object into an array
									  id:: 646349b1-7599-465f-978d-a5b10b88a004
										- ```javascript
										  const numWordPairs = [];
										  let key = 'hello'
										  let value = 3;
										  numWordPairs.push({ [key] : value })
										  
										  console.log(`numWordPairs:`, numWordPairs)
										  return JSON.stringify(numWordPairs)
										  ```
											- {{evalparent}}
											  id:: 63910f56-dc95-4d5c-a222-f623d8081b4e
										- ```javascript
										  let importantThings = [];
										  
										  function addItem(newItemText, newItemPriority) {
										      importantThings.push({
										        text: newItemText, 
										        priority: newItemPriority
										      })
										  }
										  addItem('hello', 1)
										  addItem('world', 2);
										  
										  console.log(importantThings)
										  return JSON.stringify(importantThings)
										  ```
											- {{evalparent}}
								- Related:
									- ((63679853-dcb7-4c52-a93f-2ba70da4b082))
									- ((634bc0c2-0b68-4da7-83b6-5abefa297cac)) : ((636d0fc5-9fbf-432f-8246-1f5884e5a5f6))
							- [`Array.prototype.reduce()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
							  id:: 6350374d-3846-414b-a27e-7d32b86eec86
							  collapsed:: true
							  ((63f239d8-2241-4838-9121-3b0ccc43dee7))
								- Can be used to run sequential operations on items in an array e.g. sum all elements, multiply all values together, etc
								  id:: 63f239d8-2241-4838-9121-3b0ccc43dee7
								- Intro
									- This method executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.
									- The first time that the callback is run there is no "return value of the previous calculation". If supplied, an initial value may be used in its place. Otherwise the array element at index 0 is used as the initial value and iteration starts from the next element (index 1 instead of index 0).
									- Perhaps the easiest-to-understand case for this method is to ((63924a86-8e38-4532-9625-cbc7c3bd336a))
								- Syntax
									- collapsed:: true
									  ```javascript
									  // Arrow function
									  reduce((accumulator, currentValue) => { /* … */ })
									  reduce((accumulator, currentValue, currentIndex) => { /* … */ })
									  reduce((accumulator, currentValue, currentIndex, array) => { /* … */ })
									  
									  reduce((accumulator, currentValue) => { /* … */ }, initialValue)
									  reduce((accumulator, currentValue, currentIndex) => { /* … */ }, initialValue)
									  reduce((accumulator, currentValue, currentIndex, array) => { /* … */ }, initialValue)
									  
									  // Callback function
									  reduce(callbackFn)
									  reduce(callbackFn, initialValue)
									  
									  // Inline callback function
									  reduce(function (accumulator, currentValue) { /* … */ })
									  reduce(function (accumulator, currentValue, currentIndex) { /* … */ })
									  reduce(function (accumulator, currentValue, currentIndex, array) { /* … */ })
									  
									  reduce(function (accumulator, currentValue) { /* … */ }, initialValue)
									  reduce(function (accumulator, currentValue, currentIndex) { /* … */ }, initialValue)
									  reduce(function (accumulator, currentValue, currentIndex, array) { /* … */ }, initialValue)
									  ```
										- Parameters
											- `callbackFn` = A function to execute for each element in the array. Its return value becomes the value of the `accumulator` parameter on the next invocation of `callbackFn`. For the last invocation, the return value becomes the return value of `reduce()`.
												- The function is called with the following arguments:
													- `accumulator`: The value resulting from the previous call to `callbackFn`. On first call, `initialValue` if specified, otherwise the value of `array[0]`
													- `currentValue` : The value of the current element. On first call, the value of `array[0]` if an `initialValue` was specified, otherwise the value of `array[1]`.
													- `currentIndex` : The index position of `currentValue` in the array. On first call, `0` if `initialValue` was specified, otherwise `1`.
													- `array` : The array `reduce()` was called upon.
											- `initialValue` (Optional) :
												- A value to which `accumulator` is initialized the first time the callback is called.
												- If `initialValue` is specified, that also causes `currentValue` to be initialized to the first value in the array.
												- If `initialValue` is *not* specified, `accumulator` is initialized to the first value in the array, and `currentValue` is initialized to the second value in the array.
										- Return value
											- The value that results from running the "reducer" callback function to completion over the entire array.
								- Examples
									- ((63ecfa3c-c989-4dcb-ab13-7ee56afd7282))
										- {{embed ((d65cdc60-c895-4d09-9565-5dff9abd924e))}}
									- Return the sum of all the elements in an array
									  id:: 63924a86-8e38-4532-9625-cbc7c3bd336a
										- ```javascript
										  const array1 = [1, 2, 3, 4];
										  
										  // 0 + 1 + 2 + 3 + 4
										  const initialValue = 0;
										  const sumWithInitial = array1.reduce(
										    (accumulator, currentValue) => accumulator + currentValue,
										    initialValue
										  );
										  
										  console.log(sumWithInitial);
										  // expected output: 10
										  ```
									- ((63924d3c-ff3a-4f86-a07e-337af88fa6eb))
										- {{embed ((63924d3c-ff3a-4f86-a07e-337af88fa6eb))}}
									- ((63cf8891-e99e-4e5a-9cbe-9dc1e009b37a))
										- {{embed ((9baa8144-5bc0-47ae-ad63-afdd84db3c7d))}}
									- ((63ecdf7a-481c-4647-ab53-5952c43def9e))
										- {{embed ((23369854-6e65-4923-9cf3-c14763a4eeb2))}}
									- ((63f8a449-3ee5-4ca1-9c55-1ac8dc03ec0a))
										- {{embed ((63f8fe4c-acc8-4c99-b271-3bc180f53ba7))}}
									- ((63cf8891-e99e-4e5a-9cbe-9dc1e009b37a))
										- {{embed ((9baa8144-5bc0-47ae-ad63-afdd84db3c7d))}}
									- [Square(n) Sum | Codewars](https://www.codewars.com/kata/515e271a311df0350d00000f/javascript)
										- Square each number in an array then sum them together
										- ```js
										  function squareSum(numbers){
										    return numbers.reduce((sum,num) => sum + (num * num), 0);
										  }
										  ```
								- [JavaScript Array reduce() Method](https://www.w3schools.com/jsref/jsref_reduce.asp)
							- [`Array.prototype.reduceRight()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduceRight)
							- [`Array.prototype.reverse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
							  id:: 635eb08f-bc21-4a5c-baa9-813d9170753a
							  collapsed:: true
							  Inverse of ((63470fd1-5c6c-4c4d-aea0-9d111a003975)) | Mutable of ((657a0339-beca-427d-9840-468296d19588)) | It reverses an array in-place
								- Examples
									- ```javascript
									  const array1 = ['one', 'two', 'three'];
									  console.log('array1:', array1);
									  // expected output: "array1:" Array ["one", "two", "three"]
									  
									  const reversed = array1.reverse();
									  console.log('reversed:', reversed);
									  // expected output: "reversed:" Array ["three", "two", "one"]
									  
									  // Careful: reverse is destructive -- it changes the original array.
									  console.log('array1:', array1);
									  // expected output: "array1:" Array ["three", "two", "one"]
									  ```
							- [`Array.prototype.shift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
							  id:: 63679853-dcb7-4c52-a93f-2ba70da4b082
							  collapsed:: true
							  Removes from beginning of array | Opposite side to ((63679853-27fd-40a4-bd44-b836c61f4394)) | Inverse of ((63679853-f388-4ef7-98f4-ccfcebf4cd89))
								- removes the **first** element from an array and returns that removed element. This method changes the length of the array.
								- Example
									- ```javascript
									  const array1 = [1, 2, 3];
									  
									  const firstElement = array1.shift();
									  
									  console.log(array1);
									  // expected output: Array [2, 3]
									  
									  console.log(firstElement);
									  // expected output: 1
									  ```
								- Related: ((63679853-975f-4456-b131-53731a001078))
							- [`Array.prototype.slice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
							  id:: 634bc0c2-0b68-4da7-83b6-5abefa297cac
							  collapsed:: true
							  Slice a section from an array | Immutable method, clones an array. | Immutable version of ((634bc0c2-38ee-4fdb-b785-2b19b9d2a6e1))
								- Returns a [shallow copy](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy) of a portion of an array into a new array object selected from  `start`  to  `end`  ( `end`  not included) where  `start`  and  `end`  represent the index of items in that array. The original array will not be modified.
								- #+BEGIN_IMPORTANT
								  This is an immutable method, whereas ((634bc0c2-38ee-4fdb-b785-2b19b9d2a6e1)) is a mutable method
								  #+END_IMPORTANT
								- #+BEGIN_TIP
								  `start` doesn't include that item, `end` includes that item
								  #+END_TIP
								- Syntax
									- collapsed:: true
									  ```javascript
									  slice()
									  slice(start)
									  slice(start, end)
									  ```
										- Parameters
											- `start`  (Optional)
												- Zero-based index at which to start extraction.
												- A negative index can be used, indicating an offset from the end of the sequence.  `slice(-2)`  extracts the last two elements in the sequence.
												- If  `start`  is undefined,  `slice`  starts from the index  `0` .
												- If  `start`  is greater than the index range of the sequence, an empty array is returned.
											- `end`  (Optional)
												- The index of the first element to exclude from the returned array.  `slice`  extracts up to but not including  `end` . For example,  `slice(1,4)`  extracts the second element through the fourth element (elements indexed 1, 2, and 3).
												- A negative index can be used, indicating an offset from the end of the sequence.  `slice(2,-1)`  extracts the third element through the second-to-last element in the sequence.
												- If  `end`  is omitted,  `slice`  extracts through the end of the sequence ( `arr.length` ).
												- If  `end`  is greater than the length of the sequence,  `slice`  extracts through to the end of the sequence ( `arr.length` ).
										- Return value = A new array containing the extracted elements.
								- Example
									- `slice()` by itself is useful for cloning arrays
										- ```javascript
										  const numbers = [1, 2, 3, 4];
										  const clone = numbers.slice();
										  console.log(clone);
										  // [1, 2, 3, 4];
										  ```
									- ```javascript
									  const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];
									  
									  console.log(animals.slice());
									  // expected output: Array ["ant", "bison", "camel", "duck", "elephant"]
									  
									  console.log(animals.slice(2));
									  // expected output: Array ["camel", "duck", "elephant"]
									  
									  console.log(animals.slice(0, 2));
									  // expected output: Array ["ant", "bison"]
									  
									  console.log(animals.slice(-2));
									  // expected output: Array ["duck", "elephant"]
									  
									  console.log(animals.slice(2, -1));
									  // expected output: Array ["camel", "duck"]
									  ```
									- Deleting an item from an array immutably
									  ```javascript
									  const languages = ["“JavaScript", "SQL", "cat purrs", "C#", "“Go"];
									  const accurateLanguages = [
									    ...languages.slice(0, 2),
									    
									    ...Languages.slice(3)
									  ];
									  ```
									- ```javascript
									  const languages = ["JavaScript", "SQL", "C#", "Go"];
									  const accurateLanguages = [ 
									    ...languages.slice(0, 2), // 'JavaScript', 'SQL'
									    "Java", 
									    ...languages.slice(3), // 'Go'
									  ];
									  ```
									- `slice(0, n)` is a good way of returning a slice of an array
										- {{embed ((313a98fd-dcd3-4695-bea4-a439e1d3acf4))}}
									- Can be used to insert an item at a specific position in an array
									  id:: 636d0fc5-9fbf-432f-8246-1f5884e5a5f6
									  ```javascript
									  function insertItem(array, item, index) {
									      let newArray = [...array.slice(0, index), item, ...array.slice(index)]
									      return newArray;
									  }
									  ```
								- Related:
									- Related: [[JavaScript]] : ((66bce5d1-babc-4aa9-b668-2fd3dd5b45be))
									- ((634bc0c2-38ee-4fdb-b785-2b19b9d2a6e1))
									- ((63470fd1-335a-43ad-be82-547be1c10d07))
									- ((636cce43-e74d-482c-ab56-df86054a8e43))
							- [`Array.prototype.some()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)
							  id:: 63679853-1c98-454a-8932-e67322c119d9
							  collapsed:: true
							  ((63f2952f-86d7-4fdd-aafa-51bf4fa40dfb)) || Unlike ((63679853-a37a-4046-8ccc-7841dfaa48a9)) which requires this for all elements
								- Can check whether at least one element in the array passes the function's test e.g. easily check for duplicates
								  id:: 63f2952f-86d7-4fdd-aafa-51bf4fa40dfb
								- Tests whether at least one element in the array passes the test implemented by the provided function. It returns true if, in the array, it finds an element for which the provided function returns true; otherwise it returns false. It doesn't modify the array.
								  id:: 636a54e5-a694-489b-8bfd-85030b168052
								- #+BEGIN_WARNING
								  The `typeof` each item is an `object` during this method, even if you're passing an array of strings for example
								  #+END_WARNING
								- Example
									- ```javascript
									  const array = [1, 2, 3, 4, 5];
									  
									  // checks whether an element is even
									  const even = (element) => element % 2 === 0;
									  
									  console.log(array.some(even));
									  // expected output: true
									  
									  // Alternatively written:
									  console.log(array.some((element) => {
									    element % 2 === 0
									  }));
									  ```
									- Check if any multiples of 3 exist in an array
									  ```javascript
									  const someNumbers = [4, 5, 6, 78, 2, 3, 45, 34, 2, 23, 5, 45, 6, 7, 23];
									  
									  const three = someNumbers.some((number) => {
									    if (number % 3 === 0) { 
									          return number;
									    }
									  });
									  ```
									- ((639061fa-373b-46c3-9f9f-10e94045b532)) - check if there's any duplicates in an array
										- {{embed ((63905ff4-4050-4b0e-ab42-0df243390d97))}}
							- [`Array.prototype.sort()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
							  id:: 63470fd1-5c6c-4c4d-aea0-9d111a003975
							  collapsed:: true
							  Inverse of ((635eb08f-bc21-4a5c-baa9-813d9170753a)) | Mutable version of ((657a032d-9e70-4c5a-a1da-aaae4d7d1730)) | Can be used to sort arrays, including ones with objects in them
								- Sort an array of numbers or strings. But use ((5c654b22-085e-4bd2-9d05-6e4692cf0929)) or ((0257c452-a8cc-40b2-b47a-235d81f263ce)) instead to find the highest/lowest number in an array, as it's a lot more efficient
								- `Array.sort(compareFunction)` The Compare Function
								  id:: 63642aac-c79a-4855-9c12-fae94a472481
								  collapsed:: true
								  Used to sort numbers, and values inside of objects/arrays
									- What
										- When `sort()` compares two values, it sends the values to the compare function, and sorts the values according to the returned (negative, zero, positive) value.
									- Syntax
										- ```javascript
										  function(a, b) {
										    return a - b
										  }
										  
										  array.sort(compareFunction)
										  ```
									- Examples
										- Sort numbers in ascending order
										  ```javascript
										  const points = [40, 100, 1, 5, 25, 10];
										  points.sort(function(a, b) {
										    return a-b
										  });
										  // expected output: [1, 5, 10, 25, 40, 100]
										  ```
										- Sort numbers in descending order
										  ```javascript
										  const points = [40, 100, 1, 5, 25, 10];
										  points.sort(function(a, b) {
										    return b-a
										  });
										  // expected output: [100, 40, 25, 10, 5, 1]
										  ```
										- Find the lowest value
										  ```javascript
										  const points = [40, 100, 1, 5, 25, 10];
										  
										  // Sort the numbers in ascending order
										  points.sort(function(a, b) {
										    return a-b
										  });
										  
										  let lowest = points[0];
										  ```
										- Find the highest value
										  ```javascript
										  const points = [40, 100, 1, 5, 25, 10];
										  
										  // Sort the numbers in descending order:
										  points.sort(function(a, b) {
										    return b-a
										  });
										  
										  let highest = points[0];
										  // or
										  let highest = points[points.length-1];
										  ```
									- {Archive}
										- https://www.w3schools.com/js/js_array_sort.asp
										- https://www.w3schools.com/jsref/jsref_sort.asp
								- Sorting alphabetically works well for strings ("Apple" comes before "Banana"). But, sorting numbers can produce incorrect results. "25" is bigger than "100", because "2" is bigger than "1". You can fix this by doing a ((63642aac-c79a-4855-9c12-fae94a472481))
								- Meta
									- Instead use ((5c654b22-085e-4bd2-9d05-6e4692cf0929)) or ((0257c452-a8cc-40b2-b47a-235d81f263ce)) to find the highest/lowest number in an array, as it's a lot more efficient than ((63470fd1-5c6c-4c4d-aea0-9d111a003975))
									  id:: 63f2965f-e63c-44c2-89f3-ecd6f644632f
									  collapsed:: true
										- Examples
											- [The highest profit wins!](https://www.codewars.com/kata/559590633066759614000063/javascript)
												- ```js
												  // Best practice
												  function minMax(arr){
												    return [Math.min(...arr), Math.max(...arr)];
												  }
												  
												  // Alternative
												  function minMax(arr){
												    arr.sort((a,b) => a-b);
												    return [arr[0], arr[arr.length-1]];
												  }
												  ```
											- ((66ba0d32-3ccd-4c2c-bfc1-87215eb97e3e))
											- ((63fd0a42-815d-4882-bde6-68c78297e37c))
												- {{embed ((0bf98572-621e-4fc4-a49d-548cbb22e8ae))}}
											-
								- Syntax
									- collapsed:: true
									  ```javascript
									  // Functionless
									  sort()
									  
									  // Arrow function
									  sort((a, b) => { /* … */ } )
									  
									  // Compare function
									  sort(compareFn)
									  
									  // Inline compare function
									  sort(function compareFn(a, b) { /* … */ })
									  ```
										- Parameters
											- `compareFn` (optional): Specifies a function that defines the sort order. If omitted, the array elements are converted to strings, then sorted according to each character's Unicode code point value.
											- `a` : The first element for comparison
											- `b` : The second element for comparison
										- Return value
											- The reference to the original array, now sorted. Note that the array is sorted *[in place](https://en.wikipedia.org/wiki/In-place_algorithm)*, and no copy is made.
								- Examples
									- Basic array sorting (strings, or mixed strings and numbers)
										- ```javascript
										  const foo = [9, 1, 4, 'zebroid', 'afterdeck'];
										  foo.sort(); // returns [ 1, 4, 9, 'afterdeck', 'zebroid' ]
										  ```
									- Sorting an array of numbers
										- Positive integers
											- ```javascript
											  const broomCupboard = [2, 4, 1, 3, 7, 5, 8, 6, 10, 9, 0];
											  
											  broomCupboard.sort((a, b) => {
											    return a - b
											  })
											  // expected output: [ 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ]
											  ```
												- Note: have to use a ((63642aac-c79a-4855-9c12-fae94a472481)) because otherwise it'll go `0, 1, 10, 2`
												  id:: 646349af-4cfb-460f-8e84-d3e34b0042a5
										- Mix of positive and negative integers
											- ```javascript
											  ```
									- Sort an array of objects
									  collapsed:: true
										- Sorting an array of objects of people allowed to get into a nightclub
										  collapsed:: true
											- ```javascript
											  const allowedGuests = [];
											  	const sortedArray = [];
											  
											  // Loop over the array
											  array.forEach((person) => {
											    if (person.age >= 18) {
											      allowedGuests.push(person);
											    }
											  });
											  // allowedGuests and sorting by age
											  allowedGuests
											  	.sort((a, b) => b.age - a.age) 
											  	.forEach((person) => {
											    		sortedArray.push(person.name);
											  });
											  
											  return sortedArray;
											  ```
												- ((635eb08f-9a44-4545-88c0-b7064e94f590))
										- Sort array of objects - Hogwarts potions
										  collapsed:: true
											- ```javascript
											  // Using the .sort() method and the shelf property of each potions object, rearrange the four potions in the 'potions' array so they are in DESCENDING order of their shelves, with the 'draught of living death' at index 0 and the 'pepperup potion' at index 3.
											  const potions = [
											    { name: "polyjuice potion", shelf: 2 },
											    { name: "draught of living death", shelf: 4 },
											    { name: "pepperup potion", shelf: 1 },
											    { name: "veritaserum", shelf: 3 },
											  ];
											  
											  //6b
											  potions.sort((a, b) => {
											    return b.shelf - a.shelf
											  })
											  ```
										- [Sort an array of objects](https://www.sitepoint.com/sort-an-array-of-objects-in-javascript/) with a compare function
										  collapsed:: true
											- ```javascript
											  const singers = [
											    { name: 'Steven Tyler', band: 'Aerosmith', born: 1948 },
											    { name: 'Karen Carpenter', band: 'The Carpenters', born: 1950 },
											    { name: 'Kurt Cobain', band: 'Nirvana', born: 1967 },
											    { name: 'Stevie Nicks', band: 'Fleetwood Mac', born: 1949 },
											  ];
											  
											  function compare(a, b) {
											    const bandA = a.born;
											    const bandB = b.born;
											  
											    let comparison = 0;
											    if (bandA > bandB) {
											      comparison = 1;
											    } else if (bandA < bandB) {
											      comparison = -1;
											    }
											    return comparison;
											  }
											  
											  singers.sort(compare);
											  
											  /* returns [
											    { name: 'Steven Tyler', band: 'Aerosmith',  born: 1948 },
											    { name: 'Stevie Nicks', band: 'Fleetwood Mac', born: 1949 },
											    { name: 'Karen Carpenter', band: 'The Carpenters', born: 1950 }
											    { name: 'Kurt Cobain', band: 'Nirvana', born: 1967 }
											  ] */
											  
											  ```
												- Note: if comparing strings then first convert them both uppercase as they can have wildly different values otherwise:
												  ```javascript
												    // Use toUpperCase() to ignore character casing
												    const bandA = a.band.toUpperCase();
												    const bandB = b.band.toUpperCase();
												  ```
										- [How to sort objects in Javascript using array,sort #shorts - YouTube](https://youtu.be/AGVPBhaxZbs)
										  ```javascript
										  let names = {
										    {
										  	isPaid: true,
										  	name: 'Bob'
										    },
										    {
										  	isPaid: false,
										  	name: 'Zach'
										    }
										  }
										  
										  names.sort((a, b)) => {
										    if (a.isPaid && !b.isPaid) {
										      return -1;
										    } else if (!a.isPaid && b.isPaid) {
										      return 1;
										    } else { 
										    	return 0;
										  })
										  ```
							- [`Array.prototype.splice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
							  id:: 634bc0c2-38ee-4fdb-b785-2b19b9d2a6e1
							  collapsed:: true
							  This changes the contents of an array by removing or replacing existing elements and/or adding new elements [in place](https://en.wikipedia.org/wiki/In-place_algorithm) | Mutable version of ((634bc0c2-0b68-4da7-83b6-5abefa297cac)) / ((657a032a-26ac-4c21-99ee-d33ff1fc3e78))
								- Unlike ((63679853-27fd-40a4-bd44-b836c61f4394)) and ((63679853-dcb7-4c52-a93f-2ba70da4b082)) this method removes items starting from an arbitrary index
								- #+BEGIN_WARNING
								  This is a mutable method, unlike ((634bc0c2-0b68-4da7-83b6-5abefa297cac))
								  #+END_WARNING
								- Example
									- ```javascript
									  const months = ['Jan', 'March', 'April', 'June'];
									  months.splice(1, 0, 'Feb');
									  // inserts at index 1
									  console.log(months);
									  // expected output: Array ["Jan", "Feb", "March", "April", "June"]
									  
									  months.splice(4, 1, 'May');
									  // replaces 1 element at index 4
									  console.log(months);
									  // expected output: Array ["Jan", "Feb", "March", "April", "May"]
									  ```
								- Syntax
									- ```javascript
									  const months = ['Jan', 'March', 'April', 'June'];
									  months.splice(1, 0, 'Feb');
									  // inserts at index 1
									  console.log(months);
									  // expected output: Array ["Jan", "Feb", "March", "April", "June"]
									  
									  months.splice(4, 1, 'May');
									  // replaces 1 element at index 4
									  console.log(months);
									  // expected output: Array ["Jan", "Feb", "March", "April", "May"]
									  ```
										- Parameters
											- `start` :   Zero-based index at which to start changing the array, [converted to an integer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#integer_conversion).
												- Negative index counts back from the end of the array — if `start < 0`, `start + array.length` is used.
												- If `start < -array.length` or `start` is omitted, `0` is used.
												- If `start >= array.length`, no element will be deleted, but the method will behave as an adding function, adding as many elements as provided.
											- `deleteCount` (Optional) : An integer indicating the number of elements in the array to remove from `start`.
												- If `deleteCount` is omitted, or if its value is greater than or equal to the number of elements after the position specified by `start`, then all the elements from `start` to the end of the array will be deleted. However, if you wish to pass any `itemN` parameter, you should pass `Infinity` as `deleteCount` to delete all elements after `start`, because an explicit `undefined` gets [converted](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number#integer_conversion) to `0`.
												- If `deleteCount` is `0` or negative, no elements are removed. In this case, you should specify at least one new element (see below).
											- `item1`, …, `itemN` (Optional) : The elements to add to the array, beginning from `start`.
												- If you do not specify any elements, `splice()` will only remove elements from the array.
										- Return value
											- An array containing the deleted elements.
											- If only one element is removed, an array of one element is returned.
											- If no elements are removed, an empty array is returned.
								- Related:
									- [[JavaScript]] : ((66bce5d1-babc-4aa9-b668-2fd3dd5b45be))
									- ((634bc0c2-0b68-4da7-83b6-5abefa297cac))
									- ((63470fd1-335a-43ad-be82-547be1c10d07))
									- ((63679853-27fd-40a4-bd44-b836c61f4394))
									- ((63679853-dcb7-4c52-a93f-2ba70da4b082))
							- [`Array.prototype.toLocaleString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toLocaleString)
							- [`Array.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toString)
							- [`Array.prototype.toSpliced()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toSpliced)
							  id:: 657a032a-26ac-4c21-99ee-d33ff1fc3e78
							  Immutable version of ((634bc0c2-38ee-4fdb-b785-2b19b9d2a6e1))
							- [`Array.prototype.toSorted()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toSorted)
							  id:: 657a032d-9e70-4c5a-a1da-aaae4d7d1730
							  Immutable version of ((63470fd1-5c6c-4c4d-aea0-9d111a003975))
							- [`Array.prototype.toReversed()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toReversed)
							  id:: 657a0339-beca-427d-9840-468296d19588
							  Immutable version of ((635eb08f-bc21-4a5c-baa9-813d9170753a))
							- [`Array.prototype.unshift()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
							  id:: 63679853-f388-4ef7-98f4-ccfcebf4cd89
							  collapsed:: true
							  Adds to beginning of array | Opposite side to ((63679853-975f-4456-b131-53731a001078)) | Inverse of ((63679853-dcb7-4c52-a93f-2ba70da4b082))
								- Adds one or more elements to the beginning of an array and returns the new length of the array.
								- Related:
									- ((63679853-27fd-40a4-bd44-b836c61f4394))
									- ((634bc0c2-0b68-4da7-83b6-5abefa297cac)) : ((636d0fc5-9fbf-432f-8246-1f5884e5a5f6))
							- [`Array.prototype.values()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/values)
							- [`Array.prototype.with()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/with)
							  id:: 657a04d8-14b8-4e87-9763-a68fc3215d08
							  collapsed:: true
							  [Copying](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#copying_methods_and_mutating_methods) (immutable) version of using the [bracket notation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_accessors#bracket_notation) to change the value of a given index. It returns a new array with the element at the given index replaced with the given value.
								-
						- Related: ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1))
					- [`Int8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int8Array)
					- [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array)
					- [`Uint8ClampedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray)
					- [`Int16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int16Array)
					- [`Uint16Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint16Array)
					- [`Int32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Int32Array)
					- [`Uint32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint32Array)
					- [`BigInt64Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt64Array)
					- [`BigUint64Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigUint64Array)
					- [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array)
					- [`Float64Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float64Array)
				- Keyed collections
					- [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
					  id:: 6377ece3-fcd7-4478-bf93-a27d3a9eac32
					  collapsed:: true
					  ((64024e3f-d36c-4958-be87-5d90de5e50c5))
						- This object holds key-value pairs, accepts no duplicate **keys** and remembers the original insertion order of the keys. Any value (both objects and [primitive values](https://developer.mozilla.org/en-US/docs/Glossary/Primitive)) may be used as either a key or a value.
						  id:: 64024e3f-d36c-4958-be87-5d90de5e50c5
						- Properties
							- [`get Map[@@species]`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/@@species)
							- [`Map.prototype.size`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/size)
							  Return the current element count
						- Methods
							- [`Map.prototype[@@iterator]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/@@iterator)
							- [`Map.prototype.clear()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/clear)
							  Removes everything from the Map.
							- [`Map.prototype.delete()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/delete)
							  Removes the value, accessed via the key
							- [`Map.prototype.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/entries)
							- [`Map.prototype.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/forEach)
							  id:: 63baa387-c3bf-4f09-8aea-264508378625
							  collapsed:: true
								- Related: ((635eb08f-9a44-4545-88c0-b7064e94f590))
							- [`Map.prototype.get()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/get)
							  id:: 63904f3d-6b67-461e-bf92-5f55bc24fa36
							  collapsed:: true
							  ((64024e3f-b62b-49c4-8673-8455fc16b39c))
								- It returns a specified element from a `Map` object, accessed via the key.
								  id:: 64024e3f-b62b-49c4-8673-8455fc16b39c
									- If the value that is associated to the provided key is an object, then you will get a reference to that object and any change made to that object will effectively modify it inside the `Map` object.
								- Syntax
									- ```javascript
									  myMap.get(key)
									  ```
									- Parameters
										- `key` = The key of the element to return from the Map object.
									- Return value
										- The element associated with the specified key, or `undefined` if the key can't be found in the `Map` object.
								- Examples
									- ```javascript
									  const map1 = new Map();
									  map1.set('bar', 'foo');
									  
									  console.log(map1.get('bar'));
									  // expected output: "foo"
									  
									  console.log(map1.get('baz'));
									  // expected output: undefined
									  
									  ```
									- ```javascript
									  const myMap = new Map();
									  myMap.set('bar', 'foo');
									  
									  console.log(myMap.get('bar')); // Returns "foo"
									  console.log(myMap.get('baz')); // Returns undefined
									  ```
								- Related: ((63904f3d-93d0-4f88-8826-258b6e04558a))
							- [`Map.prototype.has()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/has)
							  id:: 63904f3d-96c1-429e-af8b-4a46b1bf89c5
							  collapsed:: true
							  ((64024e3f-c4b0-4849-bce2-74663e4e35ba))
								- It returns a boolean indicating whether an element with the  specified key exists or not.
								  id:: 64024e3f-c4b0-4849-bce2-74663e4e35ba
								- Syntax
									- ```javascript
									  has(key)
									  ```
									- Parameters
										- `key` = The key of the element to test for presence in the Map object.
									- Return value
										- `true` if an element with the specified key exists in the Map object; otherwise `false`.
								- Example
									- ```javascript
									  const map1 = new Map();
									  map1.set('bar', 'foo');
									  
									  console.log(map1.has('bar'));
									  // expected output: true
									  
									  console.log(map1.has('baz'));
									  // expected output: false
									  ```
									- ```javascript
									  const myMap = new Map();
									  myMap.set("bar", "foo");
									  
									  console.log(myMap.has("bar")); // true
									  console.log(myMap.has("baz")); // false
									  ```
							- [`Map.prototype.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/keys)
							- [`Map.prototype.set()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/set)
							  id:: 63904f3d-93d0-4f88-8826-258b6e04558a
							  collapsed:: true
							  ((64024e3f-00c8-469b-b07b-29f7a416676a))
								- It adds or updates an entry in a `Map` object with a specified key and a value.
								  id:: 64024e3f-00c8-469b-b07b-29f7a416676a
								- Syntax
									- ```javascript
									  myMap.set(key, value)
									  ```
									- Parameters
										- `key` = The key of the element to add to the Map object. The key may be any [JavaScript type](((63904f3d-07c5-4adc-87cd-6cfc1c5ecdde))) (any primitive value or any type of JavaScript object).
										- `value` = The value of the element to add to the Map object. The value may be any [JavaScript type](((63904f3d-07c5-4adc-87cd-6cfc1c5ecdde))) (any primitive value or any type of JavaScript object)
								- Examples
									- ```javascript
									  const map1 = new Map();
									  map1.set('bar', 'foo');
									  
									  console.log(map1.get('bar'));
									  // expected output: "foo"
									  
									  console.log(map1.get('baz'));
									  // expected output: undefined
									  ```
									- ```javascript
									  const myMap = new Map();
									  
									  // Add new elements to the map
									  myMap.set('bar', 'foo');
									  myMap.set(1, 'foobar');
									  
									  // Update an element in the map
									  myMap.set('bar', 'baz');
									  ```
							- [`Map.prototype.values()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/values)
						- Examples
							- ```javascript
							  let mapTest = new Map();
							  
							  mapTest.set("name", "keira");
							  mapTest.set("age", 27);
							  mapTest.set("city", "london");
							  mapTest.set("name", "francesco")
							  console.log(mapTest);
							  // returns: Map(3) { name → "francesco", age → 27, city → "london" }
							  ```
							- ```javascript
							  Map {"hame" => "keira", "age" => 27, "city" => "London"}
							  ```
						- Related:
							- ((635593b3-9619-4902-8342-f7649f68f90c))
							- ((6350374d-fdba-4eb4-b17a-f80e5e5a3fcb))
					- [`Set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set)
					  id:: 635593b3-9619-4902-8342-f7649f68f90c
					  collapsed:: true
					  ((64024e3f-d5e7-43db-9093-a6a28044ff60))
						- Is an object type that accepts no duplicates (i.e. every character inside is unique). It stores unique values of any type, whether [primitive values](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) or object references. Does not store key-value pairs, unlike an ((63f33e7c-e71b-4d14-b352-7b9fe2d600b1)) or ((635593b3-9619-4902-8342-f7649f68f90c))
						  id:: 64024e3f-d5e7-43db-9093-a6a28044ff60
						- Constructor
							- [`Set() constructor`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/Set)
							  collapsed:: true
								- The **`Set` constructor** lets you  create `Set` objects that store unique values of any type, whether [primitive values](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) or object references.
								- Example
									- ```javascript
									  const set1 = new Set([1, 2, 3, 4, 5]);
									  
									  console.log(set1.has(1));
									  // Expected output: true
									  
									  console.log(set1.has(5));
									  // Expected output: true
									  
									  console.log(set1.has(6));
									  // Expected output: false
									  ```
						- Properties
							- [`get Set[@@species]`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/@@species)
							- [`Set.prototype.size`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/size)
							  id:: cdcdc58f-5478-4230-9f4b-3b09f00f725a
							  collapsed:: true
								- The **`size`** accessor property returns the number of (unique) elements in a [`Set`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set) object.
								- Example
									- ```javascript
									  const set1 = new Set();
									  const object1 = {};
									  
									  set1.add(42);
									  set1.add('forty two');
									  set1.add('forty two');
									  set1.add(object1);
									  
									  console.log(set1.size);
									  // Expected output: 3
									  ```
						- Methods
							- [`Set.prototype[@@iterator]()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/@@iterator)
							- [`Set.prototype.add()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/add)
							  id:: 63fdd9d6-f868-4e2f-9946-fd408c683a6e
							  collapsed:: true
								- Inserts a new element with a specified value in to a `Set` object, if there isn't an element with the same value already in the `Set`.
								- Examples
									- ```js
									  const set1 = new Set();
									  
									  set1.add(42);
									  set1.add(42);
									  set1.add(13);
									  
									  for (const item of set1) {
									    console.log(item);
									    // Expected output: 42
									    // Expected output: 13
									  }
									  ```
									- ```js
									  const mySet = new Set();
									  
									  mySet.add(1);
									  mySet.add(5).add("some text"); // chainable
									  
									  console.log(mySet);
									  // Set [1, 5, "some text"]
									  ```
							- [`Set.prototype.clear()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/clear)
							- [`Set.prototype.delete()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/delete)
							- [`Set.prototype.entries()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/entries)
							- [`Set.prototype.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/forEach)
							- [`Set.prototype.has()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/has)
							- [`Set.prototype.keys()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/keys)
							- [`Set.prototype.values()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/values)
						- Meta
							- To return all values in one string do `[...set].join('')`
							  id:: 6400db4c-de72-46ec-98f5-c79d918326c6
							  collapsed:: true
								- Example
									- {{embed ((8701c966-b92f-4b3b-931d-bf0d142727ed))}}
						- Example
						  id:: 6358f51d-6667-45b4-bad0-717f5b8cca4b
							- ```javascript
							  let array = ['a', 'b', 'b'];
							  let newSet = new Set(array);
							  console.log(newSet)
							  // returns: ['a', 'b'];
							  ```
							- ```javascript
							  let setTest = new Set ([1, 1, 1, 2, 2, 3, 4, 4, 4, 4, 4, 4, 5]);
							  console.log(setTest)
							  // returns: [1, 2, 3, 4, 5]
							  ```
							- ((63f66c6c-a485-474c-b2b7-3c480816fe02))
								- {{embed ((63f8fe4c-9601-4a28-bea8-a3761241253f))}}
						- Related: ((6377ece3-fcd7-4478-bf93-a27d3a9eac32))
					- [`WeakMap`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap)
					- [`WeakSet`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakSet)
				- Structured data
					- [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)
					- [`SharedArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SharedArrayBuffer)
					- [`DataView`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView)
					- [`Atomics`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics)
					- [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)
					  collapsed:: true
						- Methods
							- [`JSON.parse()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse)
							  id:: 634eb27a-5613-4a08-8634-3fe0a916e99e
							  collapsed:: true
								- It parses a JSON string, constructing the JavaScript value or object described by the string. An optional *reviver* function can be provided to perform a transformation on the resulting object before it is returned.
								- Examples
									- ```js
									  const json = '{"result":true, "count":42}';
									  const obj = JSON.parse(json);
									  
									  console.log(obj.count);
									  // Expected output: 42
									  
									  console.log(obj.result);
									  // Expected output: true
									  ```
							- [`JSON.stringify()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)
							  id:: 507dc5b1-e753-4ada-9eee-5acd64ec1f7d
							  collapsed:: true
							  ((6408c102-0f97-4a12-820b-ce707252c952))
								- It converts a JavaScript value to a JSON string (especially useful for objects). Optionally replacing values if a replacer function is specified or optionally including only the specified properties if a replacer array is specified
								  id:: 6408c102-0f97-4a12-820b-ce707252c952
								- Meta
								- Examples
									- ```js
									  let myObject = { key1: 'value1', key2: 'value2', key3: 'value3' };
									  
									  let jsonString = JSON.stringify(myObject);
									  
									  console.log(jsonString);
									  ```
									- Can ensure that JSON file keeps indentation so it remains readable
									  id:: 63528e53-2831-43a9-8463-6fb0afb8cbf0
										- ```javascript
										  stringify(myData, null, 4) // will indent with tabs of 4 size
										  ```
										- Related: ((63525cd5-d5e5-4705-835a-88eb5a163206))
								- Related: ((67e7fb30-fb89-40d9-a915-c82228bd700d))
				- Memory management
					- [`WeakRef`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakRef)
					- [`FinalizationRegistry`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/FinalizationRegistry)
				- Control abstraction
					- [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
					  collapsed:: true
						- Properties
							- [`get Promise[@@species]`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/@@species)
						- Methods
							- [`Promise.all()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)
							- [`Promise.allSettled()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/allSettled)
							- [`Promise.any()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/any)
							- [`Promise.prototype.catch()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/catch)
							- [`Promise.prototype.finally()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/finally)
							- [`Promise.race()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/race)
							- [`Promise.reject()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/reject)
							- [`Promise.resolve()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/resolve)
							- [`Promise.prototype.then()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then)
							  id:: 2e08cf60-c991-45bb-b23d-a34699a9d300
							  collapsed:: true
								-
					- [`GeneratorFunction`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/GeneratorFunction)
					- [`AsyncGeneratorFunction`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncGeneratorFunction)
					- [`Generator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Generator)
					- [`AsyncGenerator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncGenerator)
					- [`AsyncFunction`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AsyncFunction)
				- Reflection
					- [`Reflect`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect)
					- [`Proxy`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy)
				- Internationalization
					- [`Intl`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl)
					- [`Intl.Collator`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Collator)
					- [`Intl.DateTimeFormat`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DateTimeFormat)
					- [`Intl.DisplayNames`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/DisplayNames)
					- [`Intl.ListFormat`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/ListFormat)
					- [`Intl.Locale`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Locale)
					- [`Intl.NumberFormat`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/NumberFormat)
					- [`Intl.PluralRules`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/PluralRules)
					- [`Intl.RelativeTimeFormat`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/RelativeTimeFormat)
					- [`Intl.Segmenter`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter)
			- [Statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements)
			  id:: 64024e3f-971a-4fae-8c9e-ec2415404127
			  collapsed:: true
				- Control flow
				  id:: 646349af-27f7-495d-93c8-29a7f7ff45ec
					- [Block](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block)
					- [Empty statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/Empty)
					- [`break`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break)
					  id:: 63721cd2-b29c-49d6-8cdc-e568df1dff6a
					- [`continue`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue)
					- [`if...else`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else)
					  id:: 64024e3f-ef30-4e8e-bc0f-aedb5a95a08c
					  collapsed:: true
						- Related:
							- ((63f8fe4d-9e21-4df9-ac1f-0e20e98afc49))
							- ((6343d976-fbe8-45fe-bc74-1fe1b5309a59))
					- [`switch`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch)
					  id:: 6343d976-fbe8-45fe-bc74-1fe1b5309a59
					  collapsed:: true
					  AKA switch statements
						- Cons
							- Can only do equality comparison, not greater or less than
						- Syntax
							- collapsed:: true
							  ```javascript
							  switch (expression) {
							    case value1:
							      //Statements executed when the
							      //result of expression matches value1
							      break;
							    case valueN:
							      //Statements executed when the
							      //result of expression matches valueN
							      break;
							    default:
							      //Statements executed when none of
							      //the values match the value of the expression
							      break;
							  }
							  
							  ```
								- `expression` = An expression whose result is matched against each  `case`  clause.
								- `case valueN` (Optional) = A case clause used to match against expression. If the expression matches the specified valueN (which can be any expression), execution starts from the first statement after that case clause until either the end of the switch statement or the first encountered break.
								- `default` (Optional) = A default clause; if provided, this clause is executed if the value of expression doesn't match any of the case clauses. A switch statement can only have one default clause.
						- Meta
							- It's easy to make more than one case trigger a conditional e.g.
							  ```javascript
							  case 'jaguar':
							  case 'bobcat':
							  case 'cat':
							  	console.log('Cats are great')
							  ```
							- You can wrap case statements with `{ }` to limit it's scope e.g.
							  ```javascript
							  case 'Oranges': {
							      console.log('Oranges are $0.59 a pound.') 
							  }
							  ```
						- Examples
							- Concisely written
							  id:: 63fcf532-1fe3-44e0-8423-d49da84a864e
								- ((63fcf386-b599-47d6-95b3-c6f7ec41bdda))
									- {{embed ((f230a965-1bfd-4641-9f50-04837468e098))}}
								- ((6391b172-3c6f-47b6-9b37-f49aa9a2edf0))
									- {{embed ((6391b186-4fc6-47cd-a1ad-d06df9799a79))}}
							- ```javascript
							  const expr = 'Papayas';
							  switch (expr) {
							    case 'Oranges':
							      console.log('Oranges are $0.59 a pound.');
							      break;
							    case 'Mangoes':
							    case 'Papayas':
							      console.log('Mangoes and papayas are $2.79 a pound.');
							      // expected output: "Mangoes and papayas are $2.79 a pound."
							      break;
							    default:
							      console.log(`Sorry, we are out of ${expr}.`);
							  }
							  ```
								- Comparison to If Statements
									- ```javascript
									  const expr = 'Papayas';
									  if (expr === 'Oranges') {
									  	console.log('Oranges are $0.59 a pound.');
									  } else if (expr === 'Mangoes' {
									  } else if (expr === 'Papayas') {
									  	console.log('Mangoes and papayas are $2.79 a pound.');
									      // expected output: "Mangoes and papayas are $2.79 a pound."
									  } else {
									  	console.log(`Sorry, we are out of ${expr}.`);
									  }
									  ```
							- ((63f3e221-dce8-44ae-9ae5-781b54a95db1))
								- {{embed ((527e66c4-29b7-45e2-90d1-3e896452f943))}}
						- Related: ((629ccb26-b359-481c-9476-3e881f17f95d))
					- [`throw`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/throw)
					- [`try...catch`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch)
					  id:: 6377ece3-44b2-4063-961a-dfdb67fa6ac6
					  collapsed:: true
						- Useful for being able to log errors, instead of for example ad-hoc console.log statements
						- Example
							- ![image.png](../assets/image_1669908685389_0.png)
							-
				- Declarations
					- [`var`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/var)
					- [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let)
					- [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const)
				- Functions and classes
					- [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function)
					- [`function*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*)
					- ((63470fd1-387d-4bd7-ac06-0f82419968be))
					- ((63470fd1-5e15-4587-8cef-3bffdf330b5c))
					- [`return`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/return)
						- `return undefined` is generally an anti-pattern since it's equivalent to writing `return`
							- It can be useful if you're using it in a conditional that will error early and return `undefined`, but that if the conditional passes then it won't return `undefined`
					- [`class`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/class)
					  id:: 6350374d-2dff-4f93-bacc-6480a9f1aca0
					  collapsed:: true
						- https://www.digitalocean.com/community/tutorials/understanding-classes-in-javascript
						- https://www.w3schools.com/js/js_classes.asp
						- Relaetd: ((6377ece3-63be-4271-b21a-f601ef2cccd1))
				- Iterations
				  id:: 663a5793-03f8-4dad-b289-6126845e59e9
				  AKA loops
					- [`do...while`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/do...while)
					  id:: 64024e3f-a15d-4a78-a629-6d530a318a64
					  collapsed:: true
						- [Loops and iteration - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#do...while_statement)
					- [`for`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
					  id:: 63679853-6e6e-4fce-87bc-93f106c2e05d
					  collapsed:: true
						- The `for` statement creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement (usually a block statement) to be executed in the loop.
						- Syntax
							- collapsed:: true
							  ```js
							  for (initialization; condition; afterthought)
							    statement
							  ```
								- [`initialization`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for#initialization) Optional
									- An expression (including [assignment expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment)) or variable declaration evaluated once before the loop begins. 
									  Typically used to initialize a counter variable. This expression may optionally declare new variables with `var` or `let` keywords. Variables declared with `var` are not local to the loop, i.e. they are in the same scope the `for` loop is in. Variables declared with `let` are local to the statement.
									- The result of this expression is discarded.
								- [`condition`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for#condition) Optional
									- An expression to be evaluated before each loop iteration. If this expression [evaluates to true](https://developer.mozilla.org/en-US/docs/Glossary/Truthy), `statement` is executed. If the expression [evaluates to false](https://developer.mozilla.org/en-US/docs/Glossary/Falsy), execution exits the loop and goes to the first statement after the `for` construct.
									- This conditional test is optional. If omitted, the condition always evaluates to true.
								- [`afterthought`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for#afterthought) Optional
									- An expression to be evaluated at the end of each loop iteration. This occurs before the next evaluation of `condition`. Generally used to update or increment the counter variable.
								- [`statement`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for#statement):
									- A statement that is executed as long as the condition evaluates to true. You can use a [block statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block) to execute multiple statements. To execute no statement within the loop, use an [empty statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/Empty) (`;`).
						- Examples
							- ```js
							  let str = '';
							  
							  for (let i = 0; i < 9; i++) {
							    str = str + i;
							  }
							  
							  console.log(str);
							  // Expected output: "012345678"
							  ```
					- [`for...in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in)
					  id:: 635eb08f-a372-4f5b-9072-e574620dbea4
					  collapsed:: true
					  Allows you to loop over each property in an object
						- Example
						  id:: 63679853-b57b-42c6-ac11-e9aa4a00ee12
						  ```javascript
						  const object = { a: 1, b: 2, c: 3 };
						  
						  for (const property in object) {
						    console.log(`${property}: ${object[property]}`);
						  }
						  
						  // expected output:
						  // "a: 1"
						  // "b: 2"
						  // "c: 3"
						  ```
					- [`for...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)
					  id:: 63679853-c651-4513-ae6a-b293b5290bd8
					  collapsed:: true
					  More succinct way of writing a basic ((63679853-6e6e-4fce-87bc-93f106c2e05d))
						- Pros/Cons compared to ((63679853-6e6e-4fce-87bc-93f106c2e05d))
							- Pros
								- More succinct and readable for basic loops
								- It also works with async / await
							- Cons
								- Doesn't allow starting loop at arbitrary index
								- Doesn't allow decrementing instead of incrementing to loop backwards
						- More succinct way of doing a basic for loop
						  id:: 6367ac6e-5aa5-4d6a-a059-2efefda1df54
							- ```javascript
							  const numbers = [-4, -2, 0];
							  // Standard for loop
							  for (let i = 0; i < numbers.length; i++) {
							    console.log(numbers[i])
							  }
							  // expected output: -4, -2, 0
							  
							  // For Of loop
							  for (let number of numbers) {
							    console.log(number);
							  }
							  ```
						- Related: ((635eb08f-9a44-4545-88c0-b7064e94f590))
					- [`for await...of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for-await...of)
					- [`while`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/while)
					- Related: ((63f33e7c-dd58-4555-93f9-15a02fe35376))
				- Other
					- [`debugger`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/debugger)
					- [`export`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
						- ((68d1c0cb-3e12-44cf-91ef-f31a3fdc176c))
					- [`import`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
						- Export and import in Javascript using `as`
						  id:: 68d1c0cb-3e12-44cf-91ef-f31a3fdc176c
						  collapsed:: true
							- ```javascript
							  // Inside myModule.js
							  export const greet = "Hello";
							  
							  // In another file
							  import { greet as sayHello } from './myModule.js';
							  ```
						-
					- [`label`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label)
					- [`with`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/with)
			- [Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators)
			  id:: 663a5793-2531-4a6e-a2de-6aae0ad0ec69
			  collapsed:: true
				- Primary expressions
					- [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
					  id:: 64024e3f-159e-41ab-800d-5a5bf7e98bda
					- [`function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function)
					- [`class`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/class)
					  id:: 6377ece3-63be-4271-b21a-f601ef2cccd1
					  collapsed:: true
						- [Learning Resources]
							- [JavaScript Classes Tutorial - YouTube](https://youtu.be/2ZphE5HcQPQ)
							  collapsed:: true
								- {{video https://youtu.be/2ZphE5HcQPQ}}
									- It creates one or more objects
									- It's basically a function that always creates an object(s) built via that specific statement
									- Basics
									  collapsed:: true
										- ```javascript
										  // Class definition
										  class Rectangle {
										    // Constructor
										    constructor() {
										     
										    }
										  }
										  ```
										- Example1
										  ```javascript
										  class Rectangle {
										    // Setup
										    constructor() {
										      console.log('The rectangle is being created');
										      
										      this.width = 5;
										    }
										  }
										  
										  let myRectangle = new Rectangle();
										  ```
										- How to make custom things out of classes
										  ```javascript
										  class Rectangle {
										    // Setup
										    constructor(_width, _height, _color) {
										      console.log('The rectangle is being created');
										      
										      this.width = _width;
										      this.height = _height;
										      this.color = _color;
										    }
										  }
										  
										  let myRectangle = new Rectangle(3, 5, 'blue');
										  ```
										- Instance methods - basically functions related to a class
											- Method examples: `getArea` and `printDescription`
											  ```javascript
											  class Rectangle {
											    constructor(_width, _height, _color) {
											      console.log('The rectangle is being created');
											  
											      this.width = _width;
											      this.height = _height;
											      this.color = _color;
											    }
											    
											    getArea() {
											      return this.width * this.height;
											    }
											    
											    printDescription() {
											      console.log(`I am a rectangle of ${this.width} x ${this.height} and I am ${this.color}`);
											    }
											  }
											  
											  let myRectangle1 = new Rectangle(3, 5, 'blue');
											  let myRectangle2 = new Rectangle(10, 5, 'red');
											  
											  console.log(myRectangle1.getArea());
											  // returns: 15
											  console.log(myRectangle2.getArea());
											  // returns: 50
											  
											  console.log(myRectangle2.printDescription());
											  // returns: `I am a rectangle of 10 x 5 and I am red`
											  ```
									- {{youtube-timestamp 887}}
										- Getter and Setter
											- "They look like properties, but are actually methods of that class"
											- ```javascript
											  class Square { 
											    constructor (_width) { 
											      this.width = _width; 
											      this.height = _width;
											    }
											    
											    get area () {
											      return this.width = this.height
											    }
											    
											    set area (area) {
											      area
											    }
											  }
											  
											  let square1 = new Square(25);
											  console.log(square1.area);
											  
											  
											  ```
						- Related:
							- ((6350374d-2dff-4f93-bacc-6480a9f1aca0))
							- ((6377ece3-2e80-40ca-8e8b-f9f734259790))
					- [`function*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function*)
					- [`yield`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield)
					- [`yield*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield*)
					- [`async function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/async_function)
					  id:: 63470fd1-387d-4bd7-ac06-0f82419968be
					  collapsed:: true
						-
					- [`async function*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/async_function*)
					  id:: 63470fd1-5e15-4587-8cef-3bffdf330b5c
					- [`await`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await)
					- [`[]`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
					- [`{}`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer)
					- [`/ab+c/i`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp)
					- [`( )`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Grouping)
					- [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/null)
				- Left-hand-side expressions
					- [Property accessors](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Property_Accessors)
					  id:: 64024e3f-e59e-42a6-9fba-1c86518b4b19
					- [`?.`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining) 
					  id:: 63679853-e408-4028-a2c0-eefdd34febd3
					  collapsed:: true
					  AKA Optional chaining
						- Overview
						  id:: 68ce7ee1-218f-4c63-857a-35889c6392e9
							- Written as: `object?.property`
							- Purpose: Checks if the left side (object) is null or undefined before accessing further properties. If so, returns undefined instead of throwing an error.
							- Effect at compile time: No errors if the left side might be missing; the result is considered possibly undefined.
							- Effect at runtime: If the left expression is null or undefined, the expression short-circuits and yields undefined—no runtime error.
							- Use case: Use when it’s possible the value may be missing and you want safe, defensive access.
							- Example:
								- ```ts
								  const maybeCar: { brand?: string } | undefined = getCar();
								  const brand = maybeCar?.brand; // brand is string | undefined, safe even if maybeCar is undefined
								  ```
							- Usage in TypeScript
								- Syntax: obj?.property or obj?.method()
								- What it does: Checks if the value on the left is null or undefined; if so, it short-circuits and returns undefined instead of throwing an error.
								- Effect: Safe property/method access that gracefully handles potentially null/undefined values at runtime.
								- Risk: None—if the value is missing, it yields undefined and does not error out.
								- Use Case: When you want to safely access properties or call methods only if the base value is actually defined.
							- Example:
								- ```ts
								  const foo: { bar?: { baz: string } } | undefined = getValue();
								  console.log(foo?.bar?.baz); // Prints undefined if foo or bar is missing
								  ```
						- [Optional chaining can be used so that code won't run if a property doesn't exist, rather than crashing](https://youtu.be/0N2OEQQ3pNg)
						  id:: 6367a0a0-4b5c-4f7a-8212-9ec4e3007acf
							- ```javascript
							  // Below code will crash unless '?' is added
							  let user = {
							    name: 'bob', 
							    subscription: {
							      date: '01/01/2022'
							    },
							    // hobbies: 'football'
							  }
							  user.hobbies?.forEach(console.log) 
							  ```
							- Works well with ((63679853-35a3-4095-bffa-b1266212d17b)) to only assign a value if it's nullish
						- ## Comparisons
							- ((68ce7ee1-4be1-4ed6-ad49-f7d42d3c96b1)) vs ((63679853-e408-4028-a2c0-eefdd34febd3))
							  id:: 68d1c0cb-87c2-46b9-804a-6fafc7df91be
								- ((63679853-e408-4028-a2c0-eefdd34febd3)) : ((68ce7ee1-218f-4c63-857a-35889c6392e9))
								- ((68ce7ee1-4be1-4ed6-ad49-f7d42d3c96b1)) : ((68fcf7b7-1f64-4850-8008-fb27498a1bf5))
								- Summary:
									- Use `!` when you know for sure a value is present (but do not want TypeScript to complain).
									- Use `?.` when a value may be absent and you want to avoid runtime errors or repetitive null checks.
					- [`new`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new)
					  id:: 646349af-34cf-4f75-9faa-865b2c30af88
					- [`new.target`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target)
					- [`import.meta`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/import.meta)
					- [`super`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super)
					- [`...obj`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax) Spread operator
					  id:: 63642a10-4e86-4101-961a-8311efb8ae4f
					  collapsed:: true
					  ((63f294fd-f0e1-453a-afc4-17a340b58e16))
						- Can be used to easily clone an iterable, or split an iterable (e.g. string) into an array (e.g. of characters), or move items from one array or object into another
						  id:: 63f294fd-f0e1-453a-afc4-17a340b58e16
						- What
							- Allows an iterable, such as an array or string, to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected. In an object literal, the spread syntax enumerates the properties of an object and adds the key-value pairs to the object being created.
							- Spread syntax looks exactly like rest syntax. In a way, spread syntax is the opposite of rest syntax. Spread syntax "expands" an array into its elements, while rest 
							  syntax collects multiple elements and "condenses" them into a single element.
							- See ((63679853-b363-45f7-bfaa-0f44b5d29804)) and ((636cd42d-7ad8-4aff-8bbc-efd56ec59808))
							- Can be used on objects to pass all the properties of one object into another
								- Example
								  ```javascript
								  var object1 = {
								  test: 1,
								  test2: "hi"
								  }
								  
								  var object2 = {
								  ...object1,
								  test3: "bye"
								  }
								  ```
						- Meta
							- ((636d5df2-f729-4189-b518-fe60777436f7))
						- Examples
							- ```javascript
							  const numbers = [1, 2, 3, 4];
							  const clone = [...numbers];
							  console.log(clone === numbers);
							  // expected output: false
							  ```
							- ```javascript
							  const numbersOne = [1, 2, 3];
							  const numbersTwo = [4, 5, 6];
							  const numbersCombined = [...numbersOne, ...numbersTwo];
							  console.log(numberCombined)
							  // expected output: [1, 2, 3, 4, 5, 6];
							  ```
							- Adding to an array immutably
							  ```javascript
							  const oldCount = [1, 2, 3, 4, 5];
							  const uhOhCount = [oldCount, 6, 7, 8];
							  // expected output: [[1, 2, 3, 4, 5], 6, 7, 8]
							  const newCount = [...oldCount, 6, 7, 8];
							  // expected output: [1, 2, 3, 4, 5, 6, 7, 8]
							  ```
							- Basic use with objects
							  ```javascript
							  const originalNiceThingsObject = { 
							    library: "React", 
							    sound: “Tonys purrs", 
							    group: "“Bootcampers”
							  }; 
							  const sameNiceThingsObject = originalNiceThingsObject;
							  const newNiceThingsObject = {...originalNiceThingsObject};
							  originalNiceThingsObject.sound = 'rain'
							  console.log(originalNiceThingsObject.sound)
							  // expected output: 'rain'
							  console.log(sameNiceThingsObject.sound)
							  // expected output: 'rain'
							  console.log(newNiceThingsObject.sound)
							  // expected output: “Tonys purrs"
							  ```
							- Adding to objects immutably
							  ```javascript
							  const oldCount = { a: 1, b: 2 };
							  const uhOhCount = { oldCount, c: 3 };
							  // expected output: { { a: 1, b: 2 }, c: 3 };
							  const newCount = { ...oldCount, c: 3 };
							  // expected output: { a: 1, b: 2, c: 3 };
							  ```
							- Adding to objects immutably with existing properties
							  ```javascript
							  const oldCount = {a: 1, b: 2, c: 3};
							  const whatDoYouThink = {...oldCount, c: 4};
							  // expected output: {a: 1, b: 2, c: 4}  because `c: 4` overwrites `c` as the code is read left-to-right
							  const howAboutThisOne = {c: 4, ...oldCount};
							  // expected output: { c: 3, a: 1, b: 2}  because oldCount overwrites `c` as the code is read left-to-right
							  ```
							- Split a string into an array of characters
							  id:: 6400dd4b-2309-4368-a90e-564bc9f5cbb0
							  ```js
							  let string = 'hello'
							  let arr = [...string]
							  console.log(arr)
							  // returns: Array(5) [ "h", "e", "l", "l", "o" ]
							  ```
							- id:: 636d5df2-f729-4189-b518-fe60777436f7
							  #+BEGIN_CAUTION
							  Using spread on objects in objects only creates a shallow copy by default. It'll look the same, but the nested object is mutable but the parent object is immutable
							  #+END_CAUTION
								- ```javascript
								  const detective = { 
								    firstName: "Sherlock", 
								    lastName: "Jones", 
								    ability: { 
								      name: "smell", 
								      level: "slightly heightened" 
								    }
								  };
								  
								  const lessUsefulDetective = {...detective};
								  // expected output: 
								  // { firstName: "Sherlock", lastName: "Jones", 
								  //  ability: { name: "smell", level: “slightly heightened" }};
								  lessUsefulDetective.ability.name = "tapdancing";
								  console.log(detective)
								  // expected output: 
								  // { 
								  //  firstName: "Sherlock", 
								  //  lastName: "Jones", 
								  //  ability: { 
								  //    name: "tapdancing", <--- it's still mutable
								  //    level: “slightly heightened" 
								  //  }
								  // };
								  ```
								- To clone the nested object we'd have to do a nested spread operator on that nested object
								  ```javascript
								  const lessUsefulDetective = {...detective, 
								    ability: {
								      ...detective.ability
								    } 
								  };
								  ```
								- Best practice: use spreading each time rather than `lessUsefulDetective.ability.game = 'tapdancing'` because assignment is a mutable method
								  ```javascript
								  const lessUsefulDetective = {...detective,
								    ability: {
								      ...detective.ability, game: "“tapdancing"
								    }
								  };
								  ```
								- Liz doesn't know if there's a way to automatically spread on all nested objects, so recommends not making overly deep objects in APIs
								- **How to deep copy an object**
								  collapsed:: true
									- A common and popular way is to use  `JSON.stringify()`  and  `JSON.parse()` .
										- ```javascript
										  const oldObj = {a: {b: 10}, c: 2};
										  const newObj = JSON.parse(JSON.stringify(oldObj));
										  
										  oldObj.a.b = 3;
										  oldObj.c = 4;
										  
										  console.log('oldObj', oldObj);
										  console.log('newObj', newObj);
										  ```
									- Another approach is to assign the  `oldObj`  properties one by one into  `newObj` 's newly assigned properties.
										- ```javascript
										  const oldObj = {a: {b: 10}, c: 2};
										  const newObj = {a: {b: oldObj.a.b}, c: oldObj.c};
										  
										  oldObj.a.b = 3;
										  oldObj.c = 4;
										  
										  console.log('oldObj:', oldObj);
										  console.log('newObj:', newObj);
										  ```
									- There are some libraries available for deep-copy. You can use them too.
							- ((636cf3a1-5bf5-42f9-adac-ec4cae939742))
								- {{embed ((636cf3a1-5bf5-42f9-adac-ec4cae939742))}}
						- [Learning Resources]
						  collapsed:: true
							- [JS Spread Operator: How It Works & Why I Love It - YouTube](https://www.youtube.com/watch?v=pYI-UuZVtHI)
								- Basically there are three places you can use spread:
									- In function calls
									  collapsed:: true
										- Example
										  ```javascript
										  const temperatures = [12, 13, 31, 23]
										  
										  Math.min(...temperatures)
										  // expected output: 54
										  ```
										- Arrays are treated as one argument
										  ```javascript
										  const tvShows = ["Six Feet Under", "Chernobyl", "Black Mirror", "Fleabag" ]
										  //I can pass each element in tvShows as a separate argument using spread:
										  console.log(...tvShows);
										  // expected output: Six Feet Under Chernobyl Black Mirror Fleabag
										  ```
										- Strings and sets are iterables, so also works with them
										  ```javascript
										  console.log('this s£$% is bananas: ', ...'BANANAS')
										  // expected output: this s£$% is bananas: B A N A N A S
										  ```
									- In array literals
										- Example
										  ```javascript
										  const parents = ["Lorie", "Steve"];
										  const kids = ['Jake', "Annie", "Jess"];
										  
										  const fullFamily = [...parents, 'Me', ...kids];
										  //["Lorie", "Steve", "Jake", 'Me', "Annie", "Jess"]
										  ```
									- In object literals
										- Example
										  ```javascript
										  const mainColors = {brightRed: "#e55039", waterfallBlue: "#38ada9"};
										  const accentColors = {lightGrey: "#778ca3", swanWhite: "#f7f1e3"};
										  
										  const fullPalette = {...mainColors, ...accentColors};
										  //{brightRed: "#e55039", waterfallBlue: "#38ada9", lightGrey: "#778ca3", swanWhite: "#f7f1e3"}
										  ```
								- In React it's important not to mutate specific data (the state) because it can cause your app to not re-render when it should
									- Instead of `push()`, use spread
										- ```javascript
										  const todos = [
										  	{user: "Brick", completed: false, task: "Upload Video"},
										  	{user: "Lilith", completed: true, task: "Rob Bank"}
										  ]
										  
										  function addTodo(newTodo){
										    return [...todos, {...newTodo, completed: false}]
										  }
										  
										  const newTodos = addTodo({user: "Mordecai", task: "Feed Bloodwing"});
										  ```
						- Related:
							- ((636cce43-e74d-482c-ab56-df86054a8e43))
							- ((634bc0c2-0b68-4da7-83b6-5abefa297cac)) is another way to easily clone an array
				- Increment & decrement
					- [`A++`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Increment)
					- [`A--`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Decrement)
					- [`++A`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Increment)
					- [`--A`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Decrement)
				- Unary operators
					- [`delete`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete)
					  id:: 64024e3f-549b-4656-8bac-049e1eb3580b
					  collapsed:: true
						- Examples
							- Can remove a property from an object (mutating the object)
							  id:: 766969c0-49a0-4a07-9b69-02351708da55
							  ```js
							  delete myObject.regex;
							  // or,
							  delete myObject['regex'];
							  // or,
							  var prop = "regex";
							  delete myObject[prop];
							  ```
								- [source](https://stackoverflow.com/questions/208105/how-do-i-remove-a-property-from-a-javascript-object)
								- Immutable alternative is using object destructuring, or perhaps spread operator
									- Object destructuring version
									  ```js
									  const { a, ...rest } = { a: 1, b: 2, c: 3 };
									  ```
								- Advanced
									- How to delete the first property in an object
									  ```js
									  delete myObj[Object.keys(myObj)[0]]
									  ```
									- How to delete the last property in an object
									  ```js
									  delete myObj[Object.keys(myObj)[Object.keys(myObj).length-1]]
									  ```
					- [`void`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/void)
					  id:: 646349af-25d2-453c-8020-85d3e808aaa4
					  collapsed:: true
						- The **`void`** operator evaluates the given `expression` and then returns [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).
						- Examples
							- ```js
							  const output = void 1;
							  console.log(output);
							  // Expected output: undefined
							  
							  void console.log('expression evaluated');
							  // Expected output: "expression evaluated"
							  
							  void function iife() {
							    console.log('iife is executed');
							  }();
							  // Expected output: "iife is executed"
							  
							  void function test() {
							    console.log('test function executed');
							  };
							  try {
							    test();
							  } catch (e) {
							    console.log('test function is not defined');
							    // Expected output: "test function is not defined"
							  }
							  ```
					- [`typeof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/typeof)
					  id:: 63470fd1-ff2c-4b9a-b116-136a41a52b94
					  collapsed:: true
					  ((63f29a46-c5f9-4702-9615-3e231e17ffd2))
						- Can check the data type of a variable
						  id:: 63f29a46-c5f9-4702-9615-3e231e17ffd2
						- Meta
							- Arrays give the type `object`, so to differentiate them from regular objects instead use ((64024e3f-ad1c-4953-807a-ebedd4878008)) or ((64085108-7822-43fd-93e3-9c5e514101f0))
							  id:: 64084faa-6068-42d4-a193-2263c4b4d039
						- Example
						  id:: 63486044-2706-4d24-aa13-8910366bf45b
							- `typeof unknownVariable` can check the type of `unknownVariable`
							- ((63485e7f-a73d-4dff-aae6-57fe42e82542))
							  collapsed:: true
								- {{embed ((63485e7f-a73d-4dff-aae6-57fe42e82542))}}
					- [`+`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unary_plus)
					- [`-`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unary_negation)
					  collapsed:: true
					  AKA Unary negation / Unary minus
						- Example: `-Math.pow(2, 15) === -32768`
						- uses the unary minus (-) operator as a prefix to negate the number returned by Math.pow(2, 15).
						- What is happening here?
							- `Math.pow(2, 15)` computes 2 to the power of 15, which equals 32768.
							- The unary minus `-` in front negates that number, turning it into -32768.
						-
					- [`~`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_NOT)
					- [`!`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_NOT)
					  id:: 67376787-bcb3-40da-abce-f25bd389423e
					  collapsed:: true
					  AKA Logical NOT
						- Related: ((68d1c0cb-1419-4845-8545-1cb0e2fe62ac))
				- Arithmetic operators
					- [`+`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition)
					  id:: 638d0621-0b12-4e67-b88a-3ed069b90233
					  collapsed:: true
						- `+string`
						  id:: 638f4569-62ae-4ff5-bcd8-05d9e9794183
						  ((63f90cc1-edf9-4d69-8bf3-2f444910e465)) | Inverse of ((638f490f-1505-4a98-9399-94834d07c5b6)) or ((638d0621-ae57-4cbc-b873-1bbcffc158dd)) | Alternative to ((63904f3d-d57b-4667-94cf-29d887d54afc)) or ((63470fd1-de4c-4705-9fb1-e734bf59cdd7))
							- Can convert a string to a number
							  id:: 63f90cc1-edf9-4d69-8bf3-2f444910e465
							- Example
								- ```javascript
								  let string = '3';
								  
								  string = +string;
								  console.log(string)
								  // returns: 3
								  ```
						- `""+number`
						  id:: 638f490f-1505-4a98-9399-94834d07c5b6
						  ((63f90c9d-a27c-454b-8848-98c6627b7905)) | Inverse of ((638f4569-62ae-4ff5-bcd8-05d9e9794183)) or ((63470fd1-de4c-4705-9fb1-e734bf59cdd7)) or ((63904f3d-d57b-4667-94cf-29d887d54afc)) | Alternative to ((638d0621-ae57-4cbc-b873-1bbcffc158dd)) and ((6488932a-5cd5-4e35-9412-bdaeff5fb153))
							- Can convert a number to a string
							  id:: 63f90c9d-a27c-454b-8848-98c6627b7905
							- Using the [`+` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition): `"" + x` coerces its operand to a *primitive* instead of a *string*, and, for some objects, has entirely different behaviors from normal string coercion. See its [reference page](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition) for more details.
							- Example
								- ```javascript
								  let number = 3;
								  
								  number = ""+number;
								  console.log(number);
								  // returns "3"
								  ```
					- [`-`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction)
					- [`/`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Division)
					  collapsed:: true
						- Example
							- ```js
							  console.log(12 / 2);
							  // Expected output: 6
							  
							  console.log(3 / 2);
							  // Expected output: 1.5
							  
							  console.log(6 / '3');
							  // Expected output: 2
							  
							  console.log(2 / 0);
							  // Expected output: Infinity
							  ```
					- [`*`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication)
					- [`%`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder) 
					  id:: 646349af-f069-46fb-868a-d3057dbbb2a7
					  collapsed:: true
					  AKA [modulo](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators#Remainder_()) operator
						- determine if a number is even or odd. The modulo operater takes two numbers and returns the remainder when the first number is divided by the second one:
						- Note: ((663a5793-c169-485a-badb-e37653744864)) values for `1` and `0`
						  id:: 66bcfc84-1397-497c-a788-d7c396e82de8
							- ((629ccb26-9661-457c-b1b7-6c39cc955e05)) : ((663a5793-c477-406a-b3f1-39adcbe9c3ca))
							- ((663a5793-435c-40aa-b5a2-c9845cc05a92)) : ((663a5793-8ba7-499a-893e-fcbbb8598e9b))
							- Note about exit codes
							  collapsed:: true
								- ((66bcfe38-bde0-4c8b-b88f-ccc4327a3e7e))
						- Example
							- ```javascript
							  console.log(12 % 3);
							  console.log(10 % 4);
							  
							  
							  Result: 
							  0 
							  2
							  ```
								- The answer for 12 % 3 is 0 because twelve divided by three has no remainder. 10 % 4 is 2 because ten divided by 4 has a remainder of two.
							- ((66bcfb80-153b-4150-8a81-55265346843f))
								- {{embed ((63b36007-4080-4e8f-b0ab-99ab1d8f4d40))}}
					- [`**`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation)
				- Relational operators
					- [`in`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in)
					  id:: 64024e3f-dada-457c-af41-eb8557bcff5c
					- [`instanceof`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof)
						- ```javascript
						  function Car(make, model, year) {
						  this.make = make;
						  this.model = model;
						  this.year = year;
						  }
						  const auto = new Car("Honda", "Accord", 1998);
						  
						  console.log(auto instanceof Car);
						  // Expected output: true
						  
						  console.log(auto instanceof Object);
						  // Expected output: true
						  
						  console.log(auto instanceof String);
						  // Expected output: false
						  ```
					- [`<`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than)
					- [`>`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than)
					- [`<=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Less_than_or_equal)
					- [`>=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Greater_than_or_equal)
					  id:: 663a5793-7173-4ff5-afdf-a9d6b9410119
				- Equality operators
					- [`==`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality)
					- [`!=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Inequality)
					- [`===`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality)
					- [`!==`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_inequality)
				- Bitwise shift operators
					- [`<<`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Left_shift)
					- [`>>`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Right_shift)
					- [`>>>`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unsigned_right_shift)
				- Binary bitwise operators
					- [`&`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_AND)
					- [`|`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR)
					- [`^`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_XOR)
				- Binary logical operators
					- [`&&`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND)
					  collapsed:: true
						- [Use ternaries rather than && in JSX](https://kentcdodds.com/blog/use-ternaries-rather-than-and-and-in-jsx)
						  id:: 63a43279-e0c1-42db-9086-caee87fce24e
					- [`||`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR)
					  id:: 635eb08f-d0ba-48f3-aeae-1b2d10f55c84
					  collapsed:: true
					  AKA Logical OR / Logical disjunction
						- For a set of operands is true if and only if one or more of its operands is true. It is typically used with boolean (logical) values. When it is, it returns a Boolean value. However, the ((635eb08f-d0ba-48f3-aeae-1b2d10f55c84)) operator actually returns the value of one of the specified operands, so if this operator is used with non-Boolean values, it will return a non-Boolean value.
						- Examples
							- Standard use - is with `boolean` values
							  ```js
							  const a = 3;
							  const b = -2;
							  
							  console.log(a > 0 || b > 0);
							  // Expected output: true
							  ```
							- Most concise way of conditionally assigning a variable 
							  id:: 6408a8c5-f56e-4a9a-86b5-6a1fabc26812
							  collapsed:: true
							  ```js
							  let a = [1, 1, 1]
							  
							  a[2] = ++a[2] || 9;
							  console.log(a)
							  // Expected output:Array [1, 1, 2]
							  
							  a[4] = ++a[4] || 9;
							  console.log(a);
							  // Expected output: Array [1, 1, 1, undefined, 9]
							  ```
								- Explanation
									- You only have to state the variable name twice, unlike the other methods which need it 3x
									- This statement assigns `1` to `sentPacks[packSizes[packSizes.length - 2]]` if its previous value is falsy (i.e., undefined, null, 0, false, or NaN), and then increments its value by 1 using the postfix increment operator. If `sentPacks[packSizes[packSizes.length - 2]]` already has a truthy value, it increments the value by 1 without assigning 1 to it.
									- Note that the original statement uses a ternary operator to achieve the same result, but the ternary operator isn't necessary in this case because the postfix increment operator already returns the original value of `sentPacks[packSizes[packSizes.length - 2]]` before it is incremented.
								- ((63f8fe4d-9e21-4df9-ac1f-0e20e98afc49)) ternary version
								  ```js
								  let a = [1, 1, 1]
								  
								  a[2] = a[2] ? ++a[2] : 9
								  ```
								- ((64024e3f-ef30-4e8e-bc0f-aedb5a95a08c)) version
								  ```js
								  let a = [1, 1, 1]
								  
								  if (a[2]) {
								    ++a[2]
								  } else {
								    a[2] = 1
								  }
								  ```
								- Related:
									- ((64024e3f-27cd-4f58-9005-b5a7d6cdbfb7))
									- ((63679853-e408-4028-a2c0-eefdd34febd3))
					- [`??`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)
					  id:: 63904f3d-b287-478d-9e3a-106f8528a920
					  collapsed:: true
					  AKA nullish coalescing operator
						- nullish coalescing operator (`??`)
							- Purpose: Provide a default value when the expression on the left is either null or undefined.
							- Effect: Returns the right-hand side operand only if the left-hand side is null or undefined; otherwise, returns the left-hand side.
							- This is different from the logical OR (||) which treats other falsy values like 0, '', false as triggering the right side.
							- Usage example:
								- ```javascript
								  const foo = null ?? 'default';     // returns 'default'
								  const bar = undefined ?? 'default';// returns 'default'
								  const baz = 0 ?? 42;               // returns 0 (not 42)
								  const qux = '' ?? 'fallback';      // returns '' (not 'fallback')
								  ```
							- This operator is useful when you want to provide defaults only when values are truly absent (null or undefined), preserving other falsy but valid values.
				- Assignment operators
					- [`=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment)
					- [`*=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Multiplication_assignment)
					- [`**=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Exponentiation_assignment)
					- [`/=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Division_assignment)
					- [`%=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder_assignment)
					- [`+=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition_assignment)
					  id:: 635eb08f-de6e-452e-8af9-aa517a2342e1
					  collapsed:: true
						- `i += i` is the shorter way of writing `i = i + i`
						  id:: 6363f60d-5a9d-48a8-a1d9-996e21bd4858
							- Example
							  ```javascript
							  i = 'hello ';
							  i += i;
							  ```
							  returns:
							  ```javascript
							  "hello hello " 
							  ```
							- Related: ((633d4878-c36e-41df-abdc-cb1ee8e6a2e4))
					- [`-=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Subtraction_assignment)
					- [`<<=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Left_shift_assignment)
					- [`>>=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Right_shift_assignment)
					- [`>>>=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Unsigned_right_shift_assignment)
					- [`&=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_AND_assignment)
					- [`^=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_XOR_assignment)
					- [`|=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_OR_assignment)
					- [`&&=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND_assignment)
					- [`||=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR_assignment)
					  id:: 64024e3f-27cd-4f58-9005-b5a7d6cdbfb7
					  collapsed:: true
						- The **logical OR assignment (`x ||= y`)** operator only assigns if `x` is [falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy).
						- Examples
							- ```js
							  const a = { duration: 50, title: '' };
							  
							  a.duration ||= 10;
							  console.log(a.duration);
							  // Expected output: 50
							  
							  a.title ||= 'title is empty.';
							  console.log(a.title);
							  // Expected output: "title is empty"
							  ```
						- Related: ((635eb08f-d0ba-48f3-aeae-1b2d10f55c84)) : ((6408a8c5-f56e-4a9a-86b5-6a1fabc26812))
							- Shortest way of checking if a variable is falsy, and if so assigning it
							  id:: 6408694e-91e6-4452-8891-9f6c75d9e8eb
					- [`??=`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_nullish_assignment)
					  id:: 63679853-35a3-4095-bffa-b1266212d17b
					  collapsed:: true
					  AKA Nullish coalescing assignment
						- Syntax
							- ```javascript
							  x ??= y
							  // only assigns if x is nullish (null or undefined)
							  ```
						- Example
							- ```javascript
							  const a = { duration: 50 };
							  
							  a.duration ??= 10;
							  console.log(a.duration);
							  // expected output: 50
							  
							  a.speed ??= 25;
							  console.log(a.speed);
							  // expected output: 25
							  
							  ```
						-
					- [`[a, b] = arr`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) 
					  id:: 63679853-46c2-4992-ab73-5c27acc7ce2e
					  collapsed:: true
					  AKA array destructuring / destructuring assignment | ((640234da-c807-43bd-a52e-b122082e86d4))
						- Makes it possible to unpack values from arrays, or properties from objects, into distinct variables.
						  id:: 640234da-c807-43bd-a52e-b122082e86d4
						- [Destructuring assignment](https://javascript.info/destructuring-assignment#array-destructuring)
						- Rest property
						  id:: 636cd42d-7ad8-4aff-8bbc-efd56ec59808
							- Related:
								- ((63679853-b363-45f7-bfaa-0f44b5d29804))
								- ((63642a10-4e86-4101-961a-8311efb8ae4f))
						- Meta
							- Can be used instead of `element` parameter in certain methods
							  id:: 64010eac-b5f5-404e-851f-6eca86550049
								- Examples
									- {{embed ((f0479460-b90a-487a-9ec1-a856476855d5))}}
						- Examples
							- ```js
							  let arr = [1, 2, 3, 4];
							  let [a, b,,d] = arr;
							  console.log(b)
							  // returns: 2
							  console.log(d)
							  // returns: 4
							  ```
							- ((63fdda25-ba87-476a-a007-24d16ef62e64))
								- {{embed ((dc1d62b5-0302-4fcf-b0b8-3fa1df96d4fb))}}
							- ((6402327c-0104-4468-8317-98fcece06095))
								- {{embed ((640232da-375d-448e-b655-994974cdc230))}}
						- Related: ((63679853-25dd-4d52-85a8-466697c801b8))
					- [`{ a, b } = obj`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
					  id:: 63679853-25dd-4d52-85a8-466697c801b8
					  collapsed:: true
					  AKA object destructuring
						- [Destructuring assignment](https://javascript.info/destructuring-assignment#object-destructuring)
						- Destructuring for importing
							- You can export multiple functions as default as long as they're in an object
								- `App.js`
								  ```javascript
								  export default {
								    bootcampers,
								    compliments,
								  };
								  ```
								- Importing
								  collapsed:: true
									- You can import them all either in an named object
									  ```javascript
									  import bothFunctions from './bootcampers';
									  ```
									- Or import them via destructuring
									  ```javascript
									  import { bootcampers, compliments } from './bootcampers';
									  ```
									- Or you can import only one of the functions
										- `test2.js`
										  ```javascript
										  import { bootcampers } from './bootcampers';
										  ```
						- Related: ((63679853-46c2-4992-ab73-5c27acc7ce2e))
				- Other operators
					- [`(condition ? ifTrue : ifFalse)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)
					  id:: 63f8fe4d-9e21-4df9-ac1f-0e20e98afc49
					  collapsed:: true
					  AKA Conditional (ternary) operator
						- See ((63a43279-e0c1-42db-9086-caee87fce24e))
						- Examples
							- ((63fd0a42-815d-4882-bde6-68c78297e37c))
								- {{embed ((63fd0a5c-cfda-4354-8c91-418c07c23978))}}
							- ((60082e89-1d10-424a-baec-143f315a44ad))
								- {{embed ((60082e89-1d10-424a-baec-143f315a44ad))}}
							- If you want to make one condition do nothing, then ((646349af-25d2-453c-8020-85d3e808aaa4)) 0 can be used or `null`
								- ```js
								  item ? count++ : void 0;
								  item ? count++ : null;
								  ```
						- Related:
							- ((64024e3f-ef30-4e8e-bc0f-aedb5a95a08c))
							- ((6343d976-fbe8-45fe-bc74-1fe1b5309a59))
					- [`,`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comma_Operator)
					  AKA Comma operators
				- Misc
					- `!!` 
					  id:: 68d1c0cb-1419-4845-8545-1cb0e2fe62ac
					  collapsed:: true
					  AKA double logical NOT operator | ((67376787-bcb3-40da-abce-f25bd389423e)) x2 | Used to convert any value to a boolean (true or false)
						- What does !! do?
							- The first ! negates the value, converting it to a boolean and inverting it.
							- The second ! negates it again, yielding the original truthiness as a strict boolean true or false.
						- Why use it?
						- When you have a value that can be of any type and you want to express it explicitly as a boolean, !!value is a common pattern.
						- ```typescript
						  const value = "hello";
						  console.log(!!value); // true
						  
						  const emptyString = "";
						  console.log(!!emptyString); // false
						  
						  const nullValue = null;
						  console.log(!!nullValue); // false
						  
						  const numberZero = 0;
						  console.log(!!numberZero); // false
						  
						  const numberOne = 1;
						  console.log(!!numberOne); // true
						  ```
						- The !! converts values that are "truthy" or "falsy" into boolean true or false, e.g., a non-empty string is true, an empty string is false.
						- Summary:
							- !! is a quick way to cast/convert a value to a pure boolean.
							- It’s often used in conditional checks or when you need a boolean result explicitly instead of a truthy/falsy value.
							- This is not specific to TypeScript; it’s a widespread JavaScript pattern for coercing to boolean.
					- `!` non-null assertion operator
					  id:: 68ce7ee1-4be1-4ed6-ad49-f7d42d3c96b1
					  collapsed:: true
						- Overview
						  id:: 68fcf7b7-1f64-4850-8008-fb27498a1bf5
							- Purpose: Tells the TypeScript compiler “I’m certain this value is not null or undefined here.”
							- Effect at compile time: Suppresses type errors for possibly null/undefined values and lets you access properties as if the value is always present.
							- Effect at runtime: None. If your value is actually null or undefined when accessed, you'll get a runtime error (e.g., TypeError: Cannot read property 'x' of undefined).
							- Use case: Use when the developer is sure about the value's existence at that point—even if TypeScript can't prove it.
							- Example:
							  ```ts
							  const nameOrNull: string | null = possiblyNullFunc();
							  const length = nameOrNull!.length; // Compiles, but crashes at runtime if nameOrNull is null
							  ```
							- Usage in TypeScript
								- Syntax: `value!`
								- What it does: Tells TypeScript “I’m absolutely sure this is not null or undefined here, so treat it as non-optional.”
								- Effect: Removes null/undefined from the type at that position for the compiler but does not perform any runtime check.
								- Risk: If you're wrong and the value is actually null or undefined at runtime, you'll get a runtime error (e.g., "Cannot read property X of undefined").
								- Use Case: When the developer is confident the value exists at this code location, often after some manual check elsewhere.
						- ! non-null assertion (suffix after a property) https://www.perplexity.ai/search/why-doesn-t-git-branch-d-have-fwJT3hVORlKt8ET4phXvMQ#64
							- e.g. `const stream = new BufferedReadableStream(socket!.readable);` to get rid of error that `socket` might be undefined
						- (`!` suffix) non-null assertion operator
						  collapsed:: true
							- `const channel = input[channelIndex]!`
							- Certainly! The syntax:
							  ```typescript
							  const channel = input[channelIndex]!;
							  ```
							- means the following in TypeScript:
							- ### Breakdown
								- `input[channelIndex]`  
								  Accesses the element at position `channelIndex` in the array (or array-like object) `input`.
								- `!` (the exclamation mark after the expression)  
								  This is the **non-null assertion operator** in TypeScript.
							- ### What Does the Non-Null Assertion Operator `!` Do?
								- It tells the TypeScript compiler:  
								  "**I am certain that `input[channelIndex]` is not `null` or `undefined` here. Please don't complain or raise an error about possible `undefined` or `null`**."
								- Essentially, it **removes `null` and `undefined` from the type** of that expression.
								- It **does not affect the runtime behavior**; it only impacts TypeScript's static type checking.
							- ### Why Use It?
								- Sometimes TypeScript infers that `input[channelIndex]` might be `undefined`—for example, if:
									- `input` is an array but `channelIndex` could be out of range,
									- or if the array type includes optional elements (`(Type | undefined)[]`).
								- You, as the developer, know better in this context that the value is definitely present.
								- So you assert non-null with `!` to avoid TypeScript errors.
							- ### Example
								- ```typescript
								  	const input: (Float32Array | undefined)[] = [new Float32Array([1, 2]), undefined];
								  	const channelIndex = 0;
								  
								  	// TypeScript would warn if you do:
								  	// const channel = input[channelIndex]; 
								  	// because input[0] could be undefined by type definition.
								  
								  	// Using non-null assertion:
								  	const channel = input[channelIndex]!;
								  	// Now, `channel` is typed as `Float32Array` (not possibly undefined).
								  	```
							- ### Important Notes
								- This is a **compile-time only hint**; if `input[channelIndex]` is actually `undefined` or `null` at runtime, you will get a runtime error.
								- Use `!` only when you are absolutely sure something is not null/undefined.
								- Overusing `!` can defeat the purpose of TypeScript's safety checks.
							- **In short:**
								- `const channel = input[channelIndex]!` accesses an element and tells TypeScript that it definitely exists (is non-null/non-undefined), suppressing type errors about possible missing values.
						- ## Comparisons
							- ((68d1c0cb-87c2-46b9-804a-6fafc7df91be))
			- [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)
			  collapsed:: true
				- [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
				  id:: 636d5df2-5117-4f9e-8113-83bbb5eff6c1
				  collapsed:: true
				  AKA fat arrow functions
					- Pros/Cons
						- Pros
							- Concise - they allow us to omit `function` and `return` keywords, as well as curly braces
							- just one line of code
							- no `function` keyword
							- no `return` keyword
							- and no curly braces {}
							- Because of their concise syntax and handling of the [`this`](https://www.sitepoint.com/inner-workings-javascripts-this-keyword/) keyword, arrow functions quickly became a favorite feature among developers.
						- Cons
							- Harder to read
							- Hoisting doesn't work
							- Pitfalls
								- You need both `{ }` and `return`, or neither
								  id:: 63f33e7b-8224-497b-ad76-70ab74cdfa1e
								  collapsed:: true
									- Examples
										- e.g. 
										  ```javascript
										  function maps(x) {
										    return x.map(el => el * 2);
										  }
										  
										  // Or
										  function maps(x) {
										    return x.map(el => {
										      return el * 2;    
										    })
										  }
										  ```
										- ((639061fa-373b-46c3-9f9f-10e94045b532))
										  collapsed:: true
											- {{embed ((639061fa-373b-46c3-9f9f-10e94045b532))}}
						- You can declare without executing? Not sure what this refers to
					- Arrow function vs normal function syntax
					  collapsed:: true
						- ```javascript
						  function toBoolean(value, truthyValues = ['true']) {
						  const normalizedValue = String(value).toLowerCase().trim();
						  return truthyValues.includes(normalizedValue);
						  }
						  
						  const toBoolean = (value, truthyValues = ['true']) => {
						  const normalizedValue = String(value).toLowerCase().trim();
						  return truthyValues.includes(normalizedValue);
						  };
						  ```
					- Examples
						- ```javascript
						  //Normal function
						  function addNumbers(a, b) { 
						    return a + b
						  }
						  
						  //Converting this to an Arrow function 
						  let addNumbers = (a, b) => {return a + b};
						  
						  //If you're only returning one line and don't have any other syntax in the 
						  //function you can remove the curly brackets and the return key word and its implicit 
						  //that you are returning whats on the right hand side of the fat arrow
						  let addNumbers2 = (a, b) => a + b;
						  
						  //If there is only one parameter in the function we don't even need the smooth brackets 
						  let greet = (a) => “hello " + a
						  
						  //becomes 
						  let greet2 = a => "hello" + a
						  
						  //If there are no parameters in the function we do need the smooth brackets however 
						  let newFunction = () => “This is a new function”
						  ```
						- ```javascript
						  // Function expression
						  const sayHiStranger = function () {
						    return 'Hi, stranger!'
						  }
						  
						  // Fat arrow function version
						  const sayHiStranger = () => 'Hi, stranger'
						  ```
						- ```javascript
						  // Function expression
						  function greeter(greeting) {
						    return function(name) {
						      return `${greeting}, ${name}!` 
						    }
						  } 
						  
						  // Fat arrow function version
						  const greeter = greeting => name => `${greeting}, ${name}!`
						  ```
					- [Arrow functions](https://www.sitepoint.com/arrow-functions-javascript/)
					  collapsed:: true
					- Related: [[C#]] : ((661bb3c7-5ad8-4244-b3fe-96209e36c02e))
				- [Default parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters)
				  id:: 63a9bb68-a490-44d5-a4db-57db695b5146
				  collapsed:: true
				  AKA Default function parameters
					- They allow named parameters to be initialized with default values if no value or undefined is passed.
					- Examples
						- ```javascript
						  function multiply(a, b = 1) {
						    return a * b;
						  }
						  
						  console.log(multiply(5, 2));
						  // expected output: 10
						  
						  console.log(multiply(5));
						  // expected output: 5
						  ```
						- ((629ccb26-1eab-4686-a7b8-f9433a871440)) version
							- ```typescript
							  function applyDiscount(price: number, discount: number = 0.05): number {
							      return price * (1 - discount);
							  }
							  
							  console.log(applyDiscount(100)); // 95
							  ```
				- [Rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest_parameters)
				  id:: 63679853-b363-45f7-bfaa-0f44b5d29804
				  collapsed:: true
				  ((6408c704-578a-4596-8997-e6c27e827648))
					- It allows a function to accept an indefinite number of arguments as an array, providing a way to represent [variadic functions](https://en.wikipedia.org/wiki/Variadic_function) in JavaScript.
					  id:: 6408c704-578a-4596-8997-e6c27e827648
					- Examples
						- ```js
						  function sum(...theArgs) {
						    let total = 0;
						    for (const arg of theArgs) {
						      total += arg;
						    }
						    return total;
						  }
						  
						  console.log(sum(1, 2, 3));
						  // Expected output: 6
						  
						  console.log(sum(1, 2, 3, 4));
						  // Expected output: 10
						  ```
					- Related:
						- ((636cd42d-7ad8-4aff-8bbc-efd56ec59808))
						- ((63642a10-4e86-4101-961a-8311efb8ae4f))
				- [`arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)
				- [Method definitions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Method_definitions)
				- [getter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get)
				  id:: 646349af-03ff-479d-9752-1f16dd01262d
				  collapsed:: true
				  This binds an object property to a function that will be called when that property is looked up. It can also be used in ((6377ece3-2e80-40ca-8e8b-f9f734259790))
					- Examples
						- ```js
						  const obj = {
						    log: ['a', 'b', 'c'],
						    get latest() {
						      return this.log[this.log.length - 1];
						    },
						  };
						  
						  console.log(obj.latest);
						  // Expected output: "c"
						  
						  ```
				- [setter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/set)
				  id:: 646349af-6311-4d14-b0ad-1c303197741b
				- [Function declarations vs Function expressions](https://www.sitepoint.com/function-expressions-vs-declarations/)
				  collapsed:: true
					- Function declarations
						- Pros
							- It can make your code more readable. If you have a long function, giving it a name can help you keep track of what it’s doing.
							- Function declarations are hoisted, which means that they are available before they are defined in your code. This helps if you need to use the function before it is defined.
						- Example
							- ```javascript
							  // function declaration
							  function sayHiStranger() {
							    return 'Hi, stranger!'
							  }
							  
							  // call the function
							  sayHiStranger()
							  ```
					- Function expressions
						- Pros
							- They are more flexible than function declarations. You can create function expressions and assign them to different variables, which can be helpful when you need to use the same function in different places.
							- Function expressions are not hoisted, so you can’t use them before they are defined in your code. This helps if you want to make sure that a function is only used after it is defined.
						- Example
							- ```javascript
							  let sayHiStranger = function () {
							    return 'Hi, stranger!'
							  }
							  ```
						- Characteristics
							- Function can be anonymous - doesn't have a name
							- They're assigned to a variable
							- Function declarations are [hoisted](https://www.sitepoint.com/javascript-hoisting/), while function expressions are not. This means that you can call a function declaration before it is defined, but you cannot do this with a function expression.
							- With function expressions, you can use a function immediately after it is defined. With function declarations, you have to wait until the entire script has been parsed.
							- Function expressions can be used as an argument to another function, but function declarations cannot.
			- [Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
			  id:: 6377ece3-2e80-40ca-8e8b-f9f734259790
			  collapsed:: true
				- Related: ((6377ece3-63be-4271-b21a-f601ef2cccd1))
			- [Regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions)
			  collapsed:: true
				- [Overview](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions)
				- [Backreference: \1, \2](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Backreference)
				- [Capturing group: (...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Capturing_group)
				- [Character class escape: \d, \D, \w, \W, \s, \S](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_class_escape)
				- [Character class: [...], [^...]](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_class)
				- [Character escape: \n, \u{...}](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Character_escape)
				- [Disjunction: |](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Disjunction)
				- [Input boundary assertion: ^, $](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Input_boundary_assertion)
				- [Literal character: a, b](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Literal_character)
				- [Lookahead assertion: (?=...), (?!...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Lookahead_assertion)
				- [Lookbehind assertion: (?<=...), (?<!...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Lookbehind_assertion)
				- [Named backreference: \k<name>](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Named_backreference)
				- [Named capturing group: (?<name>...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Named_capturing_group)
				- [Non-capturing group: (?:...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Non-capturing_group)
				- [Quantifier: *, +, ?, {n}, {n,}, {n,m}](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Quantifier)
				- [Unicode character class escape: \p{...}, \P{...}](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Unicode_character_class_escape)
				- [Wildcard: .](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Wildcard)
				- [Word boundary assertion: \b, \B](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Word_boundary_assertion)
			- [Errors](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors)
			  collapsed:: true
				- [Error: Permission denied to access property "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Property_access_denied)
				- [InternalError: too much recursion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Too_much_recursion)
				- [RangeError: argument is not a valid code point](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_a_valid_code_point)
				- [RangeError: BigInt division by zero](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/BigInt_division_by_zero)
				- [RangeError: BigInt negative exponent](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/BigInt_negative_exponent)
				- [RangeError: invalid array length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_array_length)
				- [RangeError: invalid date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_date)
				- [RangeError: precision is out of range](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Precision_range)
				- [RangeError: radix must be an integer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_radix)
				- [RangeError: repeat count must be less than infinity](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Resulting_string_too_large)
				- [RangeError: repeat count must be non-negative](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Negative_repetition_count)
				- [RangeError: x can't be converted to BigInt because it isn't an integer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_be_converted_to_BigInt_because_it_isnt_an_integer)
				- [ReferenceError: "x" is not defined](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_defined)
				- [ReferenceError: assignment to undeclared variable "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Undeclared_var)
				- [ReferenceError: can't access lexical declaration 'X' before initialization](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_access_lexical_declaration_before_init)
				- [ReferenceError: deprecated caller or arguments usage](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_caller_or_arguments_usage)
				- [ReferenceError: reference to undefined property "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Undefined_prop)
				- [SyntaxError: "0"-prefixed octal literals and octal escape seq. are deprecated](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_octal)
				- [SyntaxError: "use strict" not allowed in function with non-simple parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Strict_non_simple_params)
				- [SyntaxError: "x" is a reserved identifier](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Reserved_identifier)
				- [SyntaxError: a declaration in the head of a for-of loop can't have an initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_for-of_initializer)
				- [SyntaxError: applying the 'delete' operator to an unqualified name is deprecated](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Delete_in_strict_mode)
				- [SyntaxError: await is only valid in async functions, async generators and modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_await)
				- [SyntaxError: cannot use `??` unparenthesized within `||` and `&&` expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_use_nullish_coalescing_unparenthesized)
				- [SyntaxError: continue must be inside loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_continue)
				- [SyntaxError: for-in loop head declarations may not have initializers](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_for-in_initializer)
				- [SyntaxError: function statement requires a name](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unnamed_function_statement)
				- [SyntaxError: getter and setter for private name #x should either be both static or non-static](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Either_be_both_static_or_non-static)
				- [SyntaxError: identifier starts immediately after numeric literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Identifier_after_number)
				- [SyntaxError: illegal character](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Illegal_character)
				- [SyntaxError: invalid assignment left-hand side](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_assignment_left-hand_side)
				- [SyntaxError: invalid BigInt syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_BigInt_syntax)
				- [SyntaxError: invalid regular expression flag "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_regexp_flag)
				- [SyntaxError: JSON.parse: bad parsing](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/JSON_bad_parse)
				- [SyntaxError: label not found](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Label_not_found)
				- [SyntaxError: missing ; before statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_semicolon_before_statement)
				- [SyntaxError: missing : after property id](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_colon_after_property_id)
				- [SyntaxError: missing ) after argument list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_parenthesis_after_argument_list)
				- [SyntaxError: missing ) after condition](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_parenthesis_after_condition)
				- [SyntaxError: missing ] after element list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_bracket_after_list)
				- [SyntaxError: missing } after function body](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_curly_after_function_body)
				- [SyntaxError: missing } after property list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_curly_after_property_list)
				- [SyntaxError: missing = in const declaration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_initializer_in_const)
				- [SyntaxError: missing formal parameter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_formal_parameter)
				- [SyntaxError: missing name after . operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Missing_name_after_dot_operator)
				- [SyntaxError: missing variable name](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_variable_name)
				- [SyntaxError: redeclaration of formal parameter "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Redeclared_parameter)
				- [SyntaxError: return not in function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_return)
				- [SyntaxError: test for equality (==) mistyped as assignment (=)?](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Equal_as_assign)
				- [SyntaxError: Unexpected '#' used outside of class body](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Hash_outside_class)
				- [SyntaxError: Unexpected token](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unexpected_token)
				- [SyntaxError: unlabeled break must be inside loop or switch](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Bad_break)
				- [SyntaxError: unparenthesized unary expression can't appear on the left-hand side of '**'](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unparenthesized_unary_expr_lhs_exponentiation)
				- [SyntaxError: unterminated string literal](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unterminated_string_literal)
				- [SyntaxError: Using //@ to indicate sourceURL pragmas is deprecated. Use //# instead](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Deprecated_source_map_pragma)
				- [TypeError: 'x' is not iterable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/is_not_iterable)
				- [TypeError: "x" has no properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_properties)
				- [TypeError: "x" is (not) "y"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Unexpected_type)
				- [TypeError: "x" is not a constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_a_constructor)
				- [TypeError: "x" is not a function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Not_a_function)
				- [TypeError: "x" is not a non-null object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/No_non-null_object)
				- [TypeError: "x" is read-only](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Read-only)
				- [TypeError: can't assign to property "x" on "y": not an object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_assign_to_property)
				- [TypeError: can't convert BigInt to number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_convert_BigInt_to_number)
				- [TypeError: can't convert x to BigInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_convert_x_to_BigInt)
				- [TypeError: can't define property "x": "obj" is not extensible](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_define_property_object_not_extensible)
				- [TypeError: can't delete non-configurable array element](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Non_configurable_array_element)
				- [TypeError: can't redefine non-configurable property "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_redefine_property)
				- [TypeError: cannot use 'in' operator to search for 'x' in 'y'](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/in_operator_no_object)
				- [TypeError: cyclic object value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cyclic_object_value)
				- [TypeError: invalid 'instanceof' operand 'x'](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/invalid_right_hand_side_instanceof_operand)
				- [TypeError: invalid Array.prototype.sort argument](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Array_sort_argument)
				- [TypeError: invalid assignment to const "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Invalid_const_assignment)
				- [TypeError: More arguments needed](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/More_arguments_needed)
				- [TypeError: property "x" is non-configurable and can't be deleted](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_delete)
				- [TypeError: Reduce of empty array with no initial value](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Reduce_of_empty_array_with_no_initial_value)
				- [TypeError: setting getter-only property "x"](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Getter_only)
				- [TypeError: X.prototype.y called on incompatible type](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Called_on_incompatible_type)
				- [URIError: malformed URI sequence](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Malformed_URI)
				- [Warning: -file- is being assigned a //# sourceMappingURL, but already has one](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Already_has_pragma)
				- [Warning: unreachable code after return statement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Stmt_after_return)
			- Misc
			  collapsed:: true
				- [JavaScript technologies overview](https://developer.mozilla.org/en-US/docs/Web/JavaScript/JavaScript_technologies_overview)
				- [Lexical grammar](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar)
				- [Iteration protocols](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
				- [Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
				- [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
				  id:: 65b39269-8f46-4d62-9ed1-bcd18e2765ba
				  collapsed:: true
				  AKA Template strings / string interpolation
					- **Template literals** are literals delimited with backtick (```) characters, allowing for [multi-line strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#multi-line_strings), [string interpolation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#string_interpolation) with embedded expressions, and special constructs called [tagged templates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#tagged_templates).
					- Template literals are sometimes informally called *template strings*, because they are used most commonly for [string interpolation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#string_interpolation) (to create strings by doing substitution of placeholders). However, a tagged template literal may not result in a string; it can be used with a custom [tag function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#tagged_templates) to perform whatever operations you want on the different parts of the template literal.
					- [Syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#syntax)
						- ```javascript
						  `string text`
						  
						  var longString = `string text line 1
						  string text line 2`
						  
						  `string text ${expression} string text`
						  
						  tagFunction`string text ${expression} string text`
						  ```
						- This allows you to avoid `let fullName = first + " " + middle + " " + last`
						- ```js
						  let fullName = `${first} ${middle} ${last}`;
						  console.log(fullName);
						  ```
						- ((642714a5-1d61-4067-a9fd-87d003c13a07)) : ((65b38f28-ea69-4c1f-a162-1f62f3aa1726))
				- [Trailing commas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Trailing_commas)
				- [Deprecated features](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features)
			- [Additional reference pages](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference#additional_reference_pages)
			  collapsed:: true
				- [Lexical grammar](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar)
				- [Data types and data structures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
				  id:: 63904f3d-07c5-4adc-87cd-6cfc1c5ecdde
					- > The value may be any [JavaScript type](((63904f3d-07c5-4adc-87cd-6cfc1c5ecdde))) (any primitive value or any type of JavaScript object)
					-
				- [Strict mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)
				- [Deprecated features](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Deprecated_and_obsolete_features)
			- Related: ((6343d58e-ff1f-4978-ab6d-22dcf81b3e51))
		- [[School of Code bootcamp]]
		- [[CodeWars - JavaScript]]
		- [[LeetCode - JavaScript]]
		- [Udacity: Intro to Javascript](https://classroom.udacity.com/courses/ud803)
		  id:: 629ccb26-2489-4137-b403-127fea25d547
		  collapsed:: true
		  #A003 `~/Documents/MUSEUM/Programming/Anki1.ods`
			- 1) Intro
			  collapsed:: true
				- JavaScript AKA ECMAScript AKA ES
				  collapsed:: true
					- ES6 / ES 2015
					- ES7 / ES 2016
					- ES8 / ES 2017
					- ES9 / ES 2018
					  9th Edition - ECMAScript 2018
				- Browser Dev Tools shortcuts
				  collapsed:: true
					- [Chrome](https://developers.google.com/web/tools/chrome-devtools/shortcuts)
					- Firefox
						- https://developer.mozilla.org/en-US/docs/Tools/Keyboard_shortcuts
						- CTRL+SHIFT+I to open
				- console.log
				  eg `console.log(awesomeMessage);`
				  collapsed:: true
					- `ctrl` + `shift` + `i` for developer tools > `console`
					  id:: 629de044-7257-40d7-a227-70e6aa67d172
					- Example1
					  `javascript
					  var thingOne = "red";
					  var thingTwo = "blue";
					  
					  console.log(thingOne + " " + thingTwo);
					  
					  Returns: red blue`
					- What is the text used to make code in a browser run?
				- Loops
				  collapsed:: true
					- Example 1
						- Runs 10 times
						  `javascript
						  for (var i = 0; i < 10; i++) {
						    console.log(i);
						  }
						  `
				- Example snippets
				  collapsed:: true
					- Example - adding cat gif to page
					  `javascript
					  document.body.addEventListener('click', function () {
					       var myParent = document.getElementById("Banner"); 
					       var myImage = document.createElement("img");
					       myImage.src = 'https://thecatapi.com/api/images/get?format=src&type=gif';
					       myParent.appendChild(myImage);
					       myImage.style.marginLeft = "160px";
					  });
					  `
			- 2) Data Types and Variables
			  collapsed:: true
				- _Main types_
					- Numbers (any integer or decimal)
					  collapsed:: true
						- Can use console like a calculator for arithmetic calculations
						- Compare numbers e.g.
						  collapsed:: true
							- 5 >= 10 (false) - greater than or equal to
							- 12 == 17 (false) - equal to
							- 1 != 0 (true) - not equal to
					- Strings (any text or number)
					  collapsed:: true
					  e.g. `'123'` `'hello'`
						- `'` preferred, except with JSON objects: double quotes `"` are required per the [JSON specification](http://www.json.org/)
						- String concatenation (adding together)
						  collapsed:: true
						  [code] e.g. `"Hello," + " New York City"`
							- Eg
							  `var haiku = "Blowing from the west" + "\nFallen leaves gather" + "\nIn the east."`
							  
							  Returns: 
							  ```
							  Blowing from the west
							  Fallen leaves gather
							  In the east.
							  ```
					- Booleans
					  collapsed:: true
						- Basic booleans
						  collapsed:: true
							- `true` and `false`
							- `1` and `0`
							- `on` and `off`
							- `yes` and `no`
					- Null, Undefined, and NaN
					  collapsed:: true
						- `null` value of nothing
						  Means you purposefully assigned `0` value
						- `undefined` absence of value
						  Means you haven't assigned a value to it
						- `NaN` stands for "Not-A-Number" nd it's often returned indicating an error with number operations
				- Implicit type coercion & Strict Equality
				  collapsed:: true
					- Implicit type coercion
					  collapsed:: true
						- JavaScript is known as a loosely typed language.
							- Basically, this means that when you’re writing JavaScript code, you do not need to specify data types. Instead, when your code is interpreted by the JavaScript engine it will automatically be converted into the "appropriate" data type.
							- DEFINITION: A strongly typed language is a programming language that is more likely to generate errors if data does not closely match an expected type. Because JavaScript is loosely typed, you don’t need to specify data types; however, this can lead to errors that are hard to diagnose due to implicit type coercion.
						- `"Hello" + 5*10` becomes `"Hello50` because it converts it to the same type first (string)
					- Strict Equality
					  Add a `=` at the end of operators i.e. `===` or `!==` | Always returns either `true` or `false`
					  AKA strict comparison
					  collapsed:: true
					  id:: 632092fe-ceb5-4fe1-800b-f661c544e0c4
						- Best practice is to use this to see if the _type_ and _value_ are identical before doing the type conversion
						- `===` Strict Equality Operator
						  id:: 63357756-dd26-4e83-8229-5176dd293241
						- `!==` Strict Inequality Operator
						- Examples
							- `"1" === 1` returns: false
							  because the string `"1"` is not the same type or value as the number `1`
							- `0 !== false` returns: true
				- Variables = persistent data
				  collapsed:: true
				  ```javascript
				  var variableName = value;
				  ```
				  collapsed:: true
					- Example
					  ```javascript
					  
					  var greeting = "Hello";  
					  # then 
					  greeting + " World!"; 
					  ```
					  returns: Hello World!
					- Reassigning a new string value
					  e.g. `greeting = "Hola"; `
					- Naming conventions
						- Use camelCase
						  e.g. `var totalAfterTax`
							- When you create a variable, you write the name of the variable using camelCase (the first word is lowercase, and all following words are uppercase)
						- Have it be succinct yet descriptive
					- [Google's JavaScript StyleGuide](https://google.github.io/styleguide/jsguide.html)
					- Note: `;` is essential
				- _Basic operations_
				  collapsed:: true
					- String Index
					  collapsed:: true
						- _Indexing_
							- You can access individual characters in a string
							  [code]
								- Example1
								  `"James"[0];` returns `"J"`
								- Eg2
								  `javascript
								  var name = "James";
								  name[0];
								  `
								  
								  Returns: `"J"`
							- `charAt()` can be used to access certain characters
								- Eg1
								  `javascript
								  var quote = "Stay awhile and listen!";
								  console.log(quote[6]);
								  ` 
								  
								  Returns: `"w"`
					- Escaping Strings
					  collapsed:: true
						- You can't put a normal quote `"` in JavaScript directly, insead you use a backslash `\`
							- Eg
							  `javascript
							  "The man whispered, \"please speak to me.\""`
						- Escaping a character ignores the character's special meaning
						- _Special characters_
							- `\\` \ (backslash)
							- `\"` '' (double quote)
							- `\'` ' (single quote)
							- `\n` newline
							  adds whitespace - line break
							- `\t` tab
							  adds whitespace - move to next tab stop
							- [More](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#Using_special_characters_in_strings)
						- Examples
						  [code]
						  collapsed:: true
							- Example using `\n`and `\t`
								- eg
								  `javascript
								  "Up up\n\tdown down"
								  `
								  
								  Returns:
								  Up up
								    down down
							- Example using a Windows filepath (need to use `\` for every `\`)
								- eg
								  `javascript
								  "The file located at \"C:\\\\Desktop\\My Documents\\Roster\\names.txt\" contains the names on the roster."
								  `
								  
								  Returns:
								  `javascript
								  "The file located at "C:\\Desktop\My Documents\Roster\names.txt" contains the names on the roster."
								  `
							- eg 2 line joke
								- eg
								  `javascript
								  var joke = "Why couldn't the shoes go out and play?\nThey were all \"tied\" up!"`
								  
								  Returns:
								  `javascript
								  Why couldn't the shoes go out and play?
								  They were all "tied" up!
								  `
					- Comparing Strings
					  collapsed:: true
						- e.g. `==`, `!=`
						- Lowercase letters have higher numerical values on the [ASCII table](http://www.ascii-code.com/)
						  [code]
							- eg1
							  `"green" > "blue"`
							- eg2
							  `"green" > "Green"`
					- Round up numbers `toFixed()`
					  collapsed:: true
						- To round total up by two decimal points use the toFixed() method. To use toFixed() pass it the number of decimal points you want to use. For example, if total equals 3.9860, then total.toFixed(2) would return 3.99.
				- Examples
				  id:: 629ccb26-730c-4476-9b94-8ae2695a9fd0
					- Printing a bill
					  collapsed:: true
						- eg - standard decimal
						  ```javascript
						  var bill = 10.25 + 3.99 + 7.15
						  var tip = bill * 0.15
						  var total = tip + bill
						  
						  console.log(total)
						  ```
						- eg - with $ and rounded up
						  ```javascript
						  var bill = 10.25 + 3.99 + 7.15
						  var tip = bill * 0.15
						  var total = tip + bill
						  
						  console.log("$" + total.toFixed(2))
						  ```
				- Related: ((afddb9fb-9d0f-456f-b505-32fee333e255))
			- 3) Conditionals
			  collapsed:: true
				- Intro concepts
				  collapsed:: true
					- Algorithms
						- The steps that your code takes to solve a problem
					- Flowcharts
						- DEFINITION: A flowchart is a visual diagram that outlines the solution to a problem through a series of logical statements. The order in which statements are evaluated and executed is called the control flow.
						- Often use yes/no boolean to visually represent what the code does
						- If everything is in a flow chart pattern, then it needs to be a series of `else if` statements
				- If...Else statements (`if else`)
				  Or just `if` statements
				  collapsed:: true
					- allow you to execute certain pieces of code based on a condition, or set of conditions, being met.
					- Example
					  [code]
					  collapsed:: true
						- template
						  `javascript
						  if (/* this expression is true */) {
						    // run this code
						  } else {
						    // run this code
						  }
						  `
						- eg a <= b
						  `javascript
						  var a = 1;
						  var b = 2;
						  
						  if (a > b) {
						    console.log("a is greater than b");
						  } else {
						    console.log("a is less than or equal to b");
						  }
						  `
						- eg check if number is even or odd
						  `javascript
						  var number = 3;
						  
						  if (number % 2 >= 1) {
						      console.log("odd");
						  } else {
						      console.log("even");
						  }
						  
						  `
						- eg `true` booleans will trigger `if` statements
						  id:: 629ccb26-543d-4ed5-924e-324ca1d4c589
						  ```javascript
						  var solved = true;
						  // doesn't print if 'false' however
						  
						  if (solved) {
						      console.log("11111111111");
						  }
						  ```
					- `if` part is mandatory, `else` is optional
					- Using `if(isGoing)` is the same as using `if(isGoing === true)`
						- Alternatively, using `if(!isGoing)` is the same as using `if(isGoing === false)`
				- Else If Statements (`else if`)
				  collapsed:: true
					- Can be used like extra `if` statements
					- The `else` statements acts as a default condition in case all the other `if` statements are false
					- Examples
						- what clothes based on weather
						  collapsed:: true
							- ```javascript
							  var weather = "sunny";
							  
							  if (weather === "snow") {
							    console.log("Bring a coat.");
							  } else if (weather === "rain") {
							    console.log("Bring a rain jacket.");
							  } else {
							    console.log("Wear what you have on.");
							  }
							  ```
						- What name of musical group depending on size
						  collapsed:: true
							- eg
							  `javascript
							  var musicians = 4;
							  
							  if (musicians <= 0)
							  {
							      console.log("not a group");
							  }
							  else if (musicians === 1)
							  {
							      console.log("solo");
							  }
							  else if (musicians === 2)
							  {
							      console.log("duet");
							  }
							  else if (musicians === 3)
							  {
							      console.log("trio");
							  }
							  else if (musicians === 4)
							  {
							      console.log("quartet");
							  }
							  else if (musicians > 4)
							  {
							      console.log("this is a large group");
							  }
							  `
						- Murder mystery game/whodunit
						  collapsed:: true
						  id:: 629ccb26-a2d8-46e3-bb60-21d87e63db60
							- https://discussions.udacity.com/t/javascript-conditional-mystery-quiz-murder-mystery-3-4/259259/9
							- eg
							  ```javascript
							  (change these 2 vars to test code)
							  var room = "dining room";
							  var suspect = "Mr. Parkes";
							  
							  var weapon = "";
							  var solved = false;
							  
							  if (room === "ballroom") {
							      weapon = "poison"; solved = suspect === "Mr. Kalehoff";
							  // 'solved' will become true because === is a strict comparison and "Mr. Kalehoff" is truthy
							  } else if (room === "gallery") {
							      weapon = "trophy"; solved = suspect === "Ms. Van Cleve";
							  } else if (room === "billiards room") {
							      weapon = "pool stick"; solved = suspect === "Mrs. Sparr";
							  } else {
							      weapon = "knife"; solved = suspect === "Mr. Parkes";
							  }
							  
							  if (solved) {
							      console.log(suspect + ' did it in the ' + room + ' with the ' + weapon + '!');
							  }
							  ```
							  
							  e.g. `Mr. Parkes did it in the dining room with the knife!`
							- Explanation
								- `if (solved)` works because [eg `true` booleans will trigger `if` statements](((629ccb26-543d-4ed5-924e-324ca1d4c589)))
							-
						- Checking your balance
						  https://i.imgur.com/PkHAtWX.png
						  collapsed:: true
							- eg
							  ```javascript
							  /*
							   * Programming Quiz - Checking Your Balance (3-5)
							   */
							  
							  // change the values of 'balance', 'checkBalance', and 'isActive' to test your code
							  var balance = 325.00;
							  var checkBalance = true;
							  var isActive = false;
							  
							  if (checkBalance === false) {
							      console.log("Thank you. Have a nice day!");
							  }
							  else if (balance > 0 && isActive === true) {
							      console.log("Your balance is $" + balance + ".");
							  }
							  else if (isActive === false) {
							      console.log("Your account is no longer active.");
							  }
							  else if (balance === 0) {
							      console.log("Your account is empty.");
							  }
							  else if (balance !== 0) {
							      console.log("Your balance is negative. Please contact bank.");
							  }
							  ```
				- Logical Operators
				  e.g. `&&`, `||` and `!`
				  collapsed:: true
					- Logical expressions
					  collapsed:: true
						- Like mathematically expressions, except they can only be either `true` or `false`
						- Mathematically expressions are similar
						  e.g. `+`, `-`, `*`,  `/` and `%`
						  collapsed:: true
							- ((646349af-f069-46fb-868a-d3057dbbb2a7))
					- `&&` Logical AND operator
					  e.g. `value1 && value2`
					  collapsed:: true
						- Returns true if both `value1` and `value2` evaluate to true.
						- Combines two logical expressions into one
						  collapsed:: true
							- If both smaller expressions are true, then the entire expression evaluates to true.
							- If either one of the smaller expressions is false, then the whole logical expression is false.
							- Another way to think about it is when the `&&` operator is placed between the two statements, the code literally reads, "if Colt is not busy AND the weather is nice, then go to the park".
							- Basically two `if` statements
						- Truth table
						  https://i.imgur.com/Q8WQY8S.png
						  collapsed:: true
							- _Table text version_
								- A | B | A&&B
								- -------------------
								- true | true | true
								- true | false | false
								- false | true | false
								- false | false | false
							- `A` is the boolean value on the left-side of the expression
							- Short-circuiting - because expressions are processed left-to-right, often `B` doesn't matter
						- Examples
						  collapsed:: true
							- Julia's weekend plans (see Colt depending on 2 factors: the weather and his plans)
							  `javascript
							  var colt = "not busy";
							  var weather = "nice";
							  
							  if (colt === "not busy" && weather === "nice") {
							    console.log("go to the park");
							  }
							  `
							- `!` means not, so look for the opposite
							  `javascript
							  !([BLANK] === 4) && "STRing" === "STRing"
							  `
							  
							  Returns: false 
							  4
								- The right side of && in the expression evaluates to true, so to make the entire expression evaluate to false, you need the left side of && to evaluate to false.
							- ((63f8fe4d-9e21-4df9-ac1f-0e20e98afc49))
							- Ice cream (uses both || and &&)
							  collapsed:: true
							  id:: 629ccb26-d63f-4904-8f83-b7efee476837
								- ```javascript
								   * Programming Quiz: Ice Cream (3-6)
								   *
								   * Write a single if statement that logs out the message:
								   * 
								   * "I'd like two scoops of __________ ice cream in a __________ with __________."
								   * 
								   * ...only if:
								   *   - flavor is "vanilla" or "chocolate"
								   *   - vessel is "cone" or "bowl"
								   *   - toppings is "sprinkles" or "peanuts"
								   *
								   * We're only testing the if statement and your boolean operators. 
								   * It's okay if the output string doesn't match exactly.
								   */
								  
								  // change the var values to test your code
								  var flavor = "vanilla";
								  var vessel = "cone";
								  var toppings = "sprinkles";
								  
								  if (flavor === "vanilla" || flavor === "chocolate") 
								  && (vessel === "cone" || vessel === "bowl")
								  && (toppings === "sprinkles" || toppings === "peanuts")) {
								      console.log("I'd like two scoops of " + flavor + " ice cream in a " + vessel + " with " + toppings + ".");
								  }
								  ```
							- Sizing chart (uses both || and &&)
							  collapsed:: true
								- Clothes sizing chart
								  ```javascript
								   * Programming Quiz: What do I Wear? (3-7)
								   *
								   * Using if/else statements, create a series of logical expressions that logs the size of a t-shirt based on the measurements of:
								   *   - shirtWidth
								   *   - shirtLength
								   *   - shirtSleeve
								   *
								   * Use the chart above to print out one of the following correct values:
								   *   - S, M, L, XL, 2XL, or 3XL
								   */
								  
								  // change the values  to test your code
								  var shirtWidth = 28;
								  var shirtLength = 34;
								  var shirtSleeve = 10.13;
								  
								  if ((shirtWidth < 20) && (shirtLength < 29) && (shirtSleeve < 8.38)) {
								      console.log("S");
								  }
								  else if ((shirtWidth < 22 && shirtWidth > 18) 
								  && (shirtLength < 30 && shirtLength > 28) 
								  && (shirtSleeve < 8.63 && shirtSleeve > 8.13)) {
								      console.log("M");
								  }
								  else if ((shirtWidth < 24 && shirtWidth > 20) 
								  && (shirtLength < 31 && shirtLength > 29) 
								  && (shirtSleeve < 8.88 && shirtSleeve > 8.38)) {
								      console.log("L");
								  }
								  else if ((shirtWidth < 26 && shirtWidth > 22) 
								  && (shirtLength < 33 && shirtLength > 30) 
								  && (shirtSleeve < 9.63 && shirtSleeve > 8.63)) {
								      console.log("XL");
								  }
								  else if ((shirtWidth < 28 && shirtWidth > 22) 
								  && (shirtLength < 34 && shirtLength > 31) 
								  && (shirtSleeve < 10.13 && shirtSleeve > 8.88)) {
								      console.log("2XL");
								  }
								  else if ((shirtWidth > 26) 
								  && (shirtLength > 33) 
								  && (shirtSleeve > 9.63)) {
								      console.log("3XL");
								  }
								  else {
								      console.log("N/A");
								  }
								  ```
								- Ternary Operator version (in progress)
								  id:: 629ccb26-d441-47f6-bd47-83290746b134
									- ```javascript
									  
									  // change the values to test your code
									  var shirtWidth = 28;
									  var shirtLength = 34;
									  var shirtSleeve = 10.13;
									  
									  var clothesSize = shirtWidth < 20 && shirtLength < 29 && shirtSleeve < 8.38 ? "S" : 
									  
									  
									  shirtWidth < 22 && shirtWidth > 18) 
									  && (shirtLength < 30 && shirtLength > 28) 
									  && (shirtSleeve < 8.63 && shirtSleeve > 8.13)) {
									   console.log("M");
									  }
									  else if ((shirtWidth < 24 && shirtWidth > 20) 
									  && (shirtLength < 31 && shirtLength > 29) 
									  && (shirtSleeve < 8.88 && shirtSleeve > 8.38)) {
									   console.log("L");
									  }
									  else if ((shirtWidth < 26 && shirtWidth > 22) 
									  && (shirtLength < 33 && shirtLength > 30) 
									  && (shirtSleeve < 9.63 && shirtSleeve > 8.63)) {
									   console.log("XL");
									  }
									  else if ((shirtWidth < 28 && shirtWidth > 22) 
									  && (shirtLength < 34 && shirtLength > 31) 
									  && (shirtSleeve < 10.13 && shirtSleeve > 8.88)) {
									   console.log("2XL");
									  }
									  else if ((shirtWidth > 26) 
									  && (shirtLength > 33) 
									  && (shirtSleeve > 9.63)) {
									   console.log("3XL");
									  }
									  else {
									   console.log("N/A");
									  }
									  ```
									- ((63f8fe4d-9e21-4df9-ac1f-0e20e98afc49))
					- `||` Logical OR operator
					  e.g. `value1 || value2`
					  collapsed:: true
						- Returns true if either value1 or value2 (or even both!) evaluates to true.
						- Truth table
						  https://i.imgur.com/itanv6y.png
							- _Table text version_
								- A | B | A||B
								- -------------------
								- true | true | true
								- true | false | true
								- false | true | true
								- false | false | false
							- `A` is the boolean value on the left-side of the expression
							- Short-circuiting - because expressions are processed left-to-right, often `B` doesn't matter
						- Examples
							- eg1
							  ```javascript
							  3 < -10 || "James" !== "james"
							  ```
							- [Ice cream](((629ccb26-d63f-4904-8f83-b7efee476837)))
							- [Sizing chart](((629ccb26-d441-47f6-bd47-83290746b134)))
					- `!` Logical NOT operator
					  e.g. `!value1`
					  collapsed:: true
						- Returns the opposite of value1. If value1 is true, then !value1 is false.
						- _Examples_
				- Advanced Conditionals
				  collapsed:: true
					- Truthy and Falsy
					  id:: 663a5793-c169-485a-badb-e37653744864
					  collapsed:: true
						- Every value in JavaScript has an inherent boolean value
							- When that value is evaluated in the context of a boolean expression, the value will be transformed into that inherent boolean value.
						- Falsy values
						  id:: 629ccb26-9661-457c-b1b7-6c39cc955e05
						  (only 6 in total)
							- the Boolean value `false`
							- the `null` type
							- the `undefined` type
							- the number `0`
							  id:: 663a5793-c477-406a-b3f1-39adcbe9c3ca
							- the empty string `""`
							  [code]
							  collapsed:: true
								- eg
								  `javascript
								  if ("") {
								      console.log("the value is truthy");
								  } else {
								      console.log("the value is falsy");
								  }
								  ` 
								  
								  Returns: "the value is falsy"
							- the odd value `NaN` (stands for "not a number", check out the [NaN MDN article](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN)
						- Truthy values
						  id:: 663a5793-435c-40aa-b5a2-c9845cc05a92
							- Examples
								- `1`
								  [code]
								  collapsed:: true
								  id:: 663a5793-8ba7-499a-893e-fcbbb8598e9b
									- Eg
									  ```javascript
									  
									  if (1) {
									      console.log("the value is truthy");
									  } else {
									      console.log("the value is falsy");
									  }
									  ```
									  
									  Returns: "the value is truthy"
								- true
								- 42
								- "pizza"
								- "0"
								- "null"
								- "undefined"
								- {}
								- []
						- id:: 66bcfe38-bde0-4c8b-b88f-ccc4327a3e7e
						  #+BEGIN_IMPORTANT
						  In ((640c8362-cdc6-44a3-b991-a338f1d05b5a)) the convention is to return `0` as the exit code for successful program execution, which is seemingly contradictory behaviour as it's falsy. This is due to earlier convention from pre-C such as Unix-like systems, where alternative codes (e.g. 1, 2, 3 etc) are used to indicate other specific failures
						  #+END_IMPORTANT
					- [**<--created Anki cards up to here-->**](((629e07ee-075d-4a72-9bd0-fd63cd35f152)))
					- Ternary Operator
					  id:: 629ccb26-aed8-440e-92ad-39ed84c0651f
						- It's a shortcut alternative for writing lengthy if...else statements
						- Basic template
						  collapsed:: true
						  ```javascript
						  conditional ? (if condition is true) : (if condition is false)
						  ```
							- To use the ternary operator, first provide a conditional statement on the left-side of the ?. Then, between the ? and : write the code that would run if the condition is true and on the right-hand side of the : write the code that would run if the condition is false.
						- Multiple choice template
						  collapsed:: true
						  ```javascript 
						  conditional1 ? (if condition1 is true) : conditional2 ? (if condition2 is true) : conditional3 ? (if condition3 is true)
						  ```
							- Example - Navigating the Food Chain
							  `javascript
							   * Use a series of ternary operator to set the category to one of the following:
							   *   - "herbivore" if an animal eats plants
							   *   - "carnivore" if an animal eats animals
							   *   - "omnivore" if an animal eats plants and animals
							   *   - undefined if an animal doesn't eat plants or animals
							   */
							  // change the values of eatsPlants and eatsAnimals to test your code
							  
							  var eatsPlants = false;
							  var eatsAnimals = true;
							  
							  var category = eatsPlants && eatsAnimals ? "omnivore" :
							                 eatsPlants ? "herbivore" :
							                 eatsAnimals ? "carnivore" : undefined;
							                 
							  console.log(category);
							  `
						- Examples
							- [Sizing chart](((629ccb26-d441-47f6-bd47-83290746b134)))
							- eg1: the variable color is being assigned to either "green" or "red" based on the value of isGoing
							  collapsed:: true
								- Long way
								  ```javascript
								  var isGoing = true;
								  var color;
								  
								  if (isGoing) {
								    color = "green";
								  } else {
								    color = "red";
								  }
								  
								  console.log(color);
								  ```
								  
								  Prints: "green"
								- Short way
								  ```javascript
								  var isGoing = true;
								  var color = isGoing ? "green" : "red";
								  console.log(color);
								  ```
							- eg2
								- code
								  ```javascript
								  var adult = true;
								  var preorder = true;
								  
								  console.log("It costs $" + (adult ? "40.00" : "20.00") + " to attend the concert. Pick up your tickets at the " + (preorder ? "will call" : "gate") + ".");
								  ```
						- Related: ((63f8fe4d-9e21-4df9-ac1f-0e20e98afc49))
					- Switch Statements
					  collapsed:: true
					  id:: 629ccb26-b359-481c-9476-3e881f17f95d
						- If you find yourself repeating `else if` statements in your code, where each condition is based on the same value (and there are no conditional statements), then it might be time to use a switch statement.
						- each else if statement (`option === [value]`) has been replaced with a `case` clause (`case: [value]`) and those clauses have been wrapped inside the switch statement.
						  collapsed:: true
							- When the switch statement first evaluates, it looks for the first `case` clause whose expression evaluates to the same value as the result of the expression passed to the switch statement. Then, it transfers control to that case clause, executing the associated statements.
						- Falling through + Break statements
						  [code]
						  collapsed:: true
							- it runs all the cases below your selected case unless you add a break statement to all cases (except the last)
							- Break Statements examples
							  collapsed:: true
								- eg1 with no break statements
								  `javascript
								  var option = 3;
								  
								  switch (option) {
								    ...
								  }
								  
								  
								  
								  Prints:
								  You selected option 3.
								  You selected option 4.
								  You selected option 5.
								  You selected option 6.
								  `
								- eg1 with break statements
								  id:: 629ccb26-0502-479b-94b3-6a83a2d76817
								  ```javascript
								  var option = 3;
								  
								  switch (option) {
								    case 1:
								      console.log("You selected option 1.");
								      break;
								    case 2:
								      console.log("You selected option 2.");
								      break;
								    case 3:
								      console.log("You selected option 3.");
								      break;
								    case 4:
								      console.log("You selected option 4.");
								      break;
								    case 5:
								      console.log("You selected option 5.");
								      break;
								    case 6:
								      console.log("You selected option 6.");
								      break; // technically, not needed
								  }
								  ```
								- eg2 - with only one var
								  `javascript
								  var month = 2;
								  
								  switch(month) {
								    case 1:
								    case 3:
								    case 5:
								    case 7:
								    case 8:
								    case 10:
								    case 12:
								      days = 31;
								      break;
								    case 4:
								    case 6:
								    case 9:
								    case 11:
								      days = 30;
								      break;
								    case 2:
								      days = 28;
								  }
								  
								  console.log("There are " + days + " days in this month.");
								  `
								  
								  Prints 28 days
								- eg3 with two vars "Salary against Education statistics
								  `javascript
								  /*
								   * Programming Quiz: Back to School (3-9)
								   *
								   * Write a switch statement to set the average salary of a person based on their type of completed education.
								   *
								   */
								  
								  // change the value of 'education' to test your code
								  var education = 'no high school diploma';
								  
								  // set the value of this based on a person's education
								  var salary = 0;
								  
								  switch (education) {
								      case 'no high school diploma':
								          salary = 25636;
								          console.log("In 2015, a person with " + education + " earned an average of $" 
								          + salary.toLocaleString("en-US") + "/year.");
								          break;
								      case 'a high school diploma':
								          salary = 35256;
								          console.log("In 2015, a person with " + education + " earned an average of $" 
								          + salary.toLocaleString("en-US") + "/year.");
								          break;
								      case 'an Associate\'s degree':
								          salary = 41496;
								          console.log("In 2015, a person with " + education + " earned an average of $" 
								          + salary.toLocaleString("en-US") + "/year.");
								          break;
								      case 'a Bachelor\'s degree':
								          salary = 59124;
								          console.log("In 2015, a person with " + education + " earned an average of $" 
								          + salary.toLocaleString("en-US") + "/year.");
								          break;
								      case 'a Master\'s degree':
								          salary = 69732;
								          console.log("In 2015, a person with " + education + " earned an average of $" 
								          + salary.toLocaleString("en-US") + "/year.");
								          break;
								      case 'a Professional degree':
								          salary = 89960;
								          console.log("In 2015, a person with " + education + " earned an average of $" 
								          + salary.toLocaleString("en-US") + "/year.");
								          break;
								      case 'a Doctoral degree':
								          salary = 84396;
								          console.log("In 2015, a person with " + education + " earned an average of $" 
								          + salary.toLocaleString("en-US") + "/year.");
								  }
								  
								  `
							- In some situations, you might want to leverage the "falling-through" behavior of switch statements to your advantage. For example, when your code follows a hierarchical-type structure.
							- Falling-Through examples
							  collapsed:: true
							  id:: 629ccb26-25c0-463e-9a6b-60239f0970d9
								- e.g. card game
								  id:: 629ccb26-1f0b-4faa-a95e-77a04cceaee9
								  ```javascript
								  var tier = "nsfw deck";
								  var output = "You’ll receive "
								  
								  switch (tier) {
								    case "deck of legends":
								      output += "a custom card, ";
								    case "collector's deck":
								      output += "a signed version of the Exploding Kittens deck, ";
								    case "nsfw deck":
								      output += "one copy of the NSFW (Not Safe for Work) Exploding Kittens card game and ";
								    default:
								      output += "one copy of the Exploding Kittens card game.";
								  }
								  
								  console.log(output);
								  ```
									- Prints: `You’ll receive one copy of the NSFW (Not Safe for Work) Exploding Kittens card game and one copy of the Exploding Kittens card game.`
								- [eg3 prizes](((629ccb26-a72d-499a-bb4c-911a4c441b1e)))
							- `default` case - it will execute when none of the values match that of the switch expression
							  collapsed:: true
								- Eg1
								  ```javascript
								  notice the default case. var tier = "none"; var output = "You’ll receive "; switch (tier) { ... default: output += "one copy of the Exploding Kittens card game."; } console.log(output); 
								  ```
								  
								  Prints: `You’ll receive one copy of the Exploding Kittens card game.`
								- [eg2 - card game](((629ccb26-1f0b-4faa-a95e-77a04cceaee9)))
								- eg3 prizes
								  id:: 629ccb26-a72d-499a-bb4c-911a4c441b1e
								  ```javascript
								  var prize = "";
								  
								  switch (winner) {
								    case 1:
								      prize += "a trip for two to the Bahamas and ";
								    case 2:
								      prize += "a four piece furniture set.";
								      break;
								    case 3:
								      prize += "a smartwatch and ";
								    default:
								      prize += "tickets to the circus.";
								  }
								  
								  console.log("You've won " + prize);
								  ```
								  
								  Prints: You've won a smartwatch and tickets to the circus.
						- Examples
							- Example1 "you selected option N"
							  id:: 629ccb26-d348-42c9-87b0-0a732acc65b2
							  collapsed:: true
								- Version with switch statement (but no break statements)
								  ```javascript
								  var option = 3;
								  
								  switch (option) {
								    case 1:
								      console.log("You selected option 1.");
								    case 2:
								      console.log("You selected option 2.");
								    case 3:
								      console.log("You selected option 3.");
								    case 4:
								      console.log("You selected option 4.");
								    case 5:
								      console.log("You selected option 5.");
								    case 6:
								      console.log("You selected option 6.");
								  }
								  ```
								- Long version without switch statement
								  ```javascript
								  var option = 3;
								  
								  if (option === 1) {
								    console.log("You selected option 1.");
								  } else if (option === 2) {
								    console.log("You selected option 2.");
								  } else if (option === 3) {
								    console.log("You selected option 3.");
								  } else if (option === 4) {
								    console.log("You selected option 4.");
								  } else if (option === 5) {
								    console.log("You selected option 5.");
								  } else if (option === 6) {
								    console.log("You selected option 6.");
								  }
								  ```
								- [eg1 with break statements](((629ccb26-0502-479b-94b3-6a83a2d76817)))
							- [Falling-Through examples](((629ccb26-25c0-463e-9a6b-60239f0970d9)))
							- [eg6 - countdown, liftoff (NASA)](((629ccb26-8bc6-4922-a1c2-d1eaf5f2f1ee)))
						- Related: ((6343d976-fbe8-45fe-bc74-1fe1b5309a59))
			- 4) Loops
			  collapsed:: true
				- What
				  collapsed:: true
					- Instead of writing the same bit of code many times for a certain task, can just turn it into a repeating loop
					- Loops let you iterate over values and repeatedly run a bit of code
				- While Loops
				  collapsed:: true
					- 3 Parts of a While Loop
					  id:: 629ccb26-2d6f-450f-9bc6-fa088571901d
						- 1) When to start
						  collapsed:: true
							- The code that sets up the loop — defining the starting value of a variable for instance.
							- Note: it has a `;` unlike normal variables (see [examples](((629ccb26-730c-4476-9b94-8ae2695a9fd0))))
								-
						- 2) When to stop:
						  collapsed:: true
							- The logical condition to test whether the loop should continue.
						- 3) How to get to the next item:
						  collapsed:: true
							- The incrementing or decrementing step — for example, `x = x * 3` or `x = x - 1`
							- Note: it always prints off the variable without addition/subtraction first
						- [eg2](((629ccb26-f6e4-40a6-ac8f-8712f979a0e0)))
					- Examples
						- Eg1 - count to mississipi
						  collapsed:: true
							- eg1- counting mississippi to 10,000
							  `javascript
							  var x = 1;
							  while (x <= 10000) {
							   console.log(x + " mississippi!");
							   x = x + 1;
							  }
							  `
						- eg2
						  collapsed:: true
						  id:: 629ccb26-f6e4-40a6-ac8f-8712f979a0e0
							- eg2
							  ```javascript
							  var start = 0; // when to start
							  while (start < 10) { // when to stop
							    console.log(start);
							    start = start + 2; // how to get to the next item
							  }
							  ```
								- Prints:
								  ```
								  0
								   2
								   4
								   6
								   8
								  ```
						- eg3 - broken, infinite loop
						  collapsed:: true
							- eg
							  `javascript
							  while (true) {
							    console.log("true is never false, so I will never stop!");
							  }
							  `
						- eg4 FizzBuzz/JuliaJames
						  collapsed:: true
							- Intro
							  collapsed:: true
								- "Fizzbuzz" is a famous interview question used in programming interviews. It goes something like this:
									- Loop through the numbers 1 to 100
									- If the number is divisible by 3, print "Fizz"
									- If the number is divisible by 5, print "Buzz"
									- If the number is divisible by both 3 and 5, print "FizzBuzz"
									- If the number is not divisible by 3 or 5, print the number
								- TIP: A number x is divisible by a number y if the answer to x / y has a remainder of 0. For example, 10 is divisible by 2 because 10 / 2 = 5 with no remainder. You can check if a number is divisible by another number by checking if `x % y === 0`
							- Answer1
							  `javascript
							  var x = 1;
							  
							  while (x <= 20) {
							      console.log((x % 3 ? "" : "Julia") + (x % 5 ? "" : "James") || x);
							      x++;
							  }
							  `
								- Explanation
									- `(x % 3 ? "" : "Julia")`
										- ((63f8fe4d-9e21-4df9-ac1f-0e20e98afc49)) for `? "" : "Julia"`
											- `""` is falsy ([Falsy values (only 6 in total)](((629ccb26-9661-457c-b1b7-6c39cc955e05))))
											- Given that x is supposed to refer to a number, `x % 3` is truthy if and only if `x % 3 !== 0` is true.
									- `x++`
										- Basically the same as `x = x + 1` (increment by 1)
										- `++` means increment
										- `--` means decrement
						- eg5 - 99 bottles of juice
						  collapsed:: true
							- Code
							  `javascript
							  var num = 99;
							  while (num > 0) {
							      console.log(num + (num === 1 ? " bottle" : " bottles") + " of juice on the wall! "+num + (num === 1 ? " bottle" : " bottles") +" of juice! Take one down, pass it around... "+(num-1)+((num-1) === 1 ? " bottle" : " bottles")+" of juice on the wall!");
							      num --;
							  }
							  `
							- Other solutons
							  collapsed:: true
								- code2
								  `javascript
								  var num = 99;
								  var bottle = "bottle";
								  
								  while (num > 0) {
								      console.log(`${num} ${bottle = (num === 1 ? "bottle" : "bottles")} of juice on the wall! ${num} ${bottle = (num === 1 ? "bottle" : "bottles")} of juice! Take one down, pass it around... ${num-1} ${bottle = ((num - 1) === 1 ? "bottle" : "bottles")} of juice on the wall!`);
								      num --;
								  }
								  `
								- code3
								  `javascript
								  var num = 99;
								  var bottles= "bottles";
								  while (num > 0) {
								    var song = "";
								    song = num + " " + bottles + " of juice on the wall! " + num 
								    + " " + bottles + " of juice! Take one down, pass it around... " 
								    + (num - 1 ) + " " + (bottles = ((num - 1)=== 1 ? "bottle" : "bottles")) 
								    + " of juice on the wall!";
								    console.log(song);
								    num--;
								  }
								  `
							- Explanation
								- `>` stands for "greater than" - can replace `>` with it?
								  source:: https://stackoverflow.com/a/5068965
						- eg6 - countdown, liftoff (NASA)
						  collapsed:: true
						  id:: 629ccb26-8bc6-4922-a1c2-d1eaf5f2f1ee
							- Code
							  ```javascript
							  var s = 60;
							  while (s >= 0) {
							      switch (s) {
							          case 50: console.log("Orbiter transfers from ground to internal power"); break;
							          case 31: console.log("Ground launch sequencer is go for auto sequence start"); break;
							          case 16: console.log("Activate launch pad sound suppression system"); break;
							          case 10: console.log("Activate main engine hydrogen burnoff system"); break;
							          case 6: console.log("Main engine start"); break;
							          case 0: console.log("Solid rocket booster ignition and liftoff!"); break;
							          default: console.log("T-"+s+" seconds");
							      }
							      s--;
							  }
							  ```
							- Explanation
								- [Switch Statements](((629ccb26-b359-481c-9476-3e881f17f95d)))
								- An alternative to `("T-"+s+" seconds")` is `((backtick)T-${s} seconds(backtick))`
									- `${s}` is a [template literal](((629ccb26-f5bb-4afa-b828-e7c5c0b92539)))
							- Other solutions
							  collapsed:: true
								- sol2
								  `javascript
								  var tasks = {
								      50: "Orbiter transfers from ground to internal power",
								      31: "Ground launch sequencer is go for auto sequence start",
								      16: "Activate launch pad sound suppression system",
								      10: "Activate main engine hydrogen burnoff system",
								      6: "Main engine start",
								      0: "Solid rocket booster ignition and liftoff!"
								  };
								  var s = 60;
								  while (s >= 0) {
								      console.log(tasks[s] || `T-${s} seconds`);
								      s--;
								  }
								  `
								- My draft solution
								  `javascript
								  var time = 60;
								  var t50 = "Orbiter transfers from ground to internal power";
								  var t31 = "Ground launch sequencer is go for auto sequence start";
								  var t16 = "Activate launch pad sound suppression system";
								  var t10 = "Activate main engine hydrogen burnoff system";
								  var t6 = "Main engine start";
								  var t0 = "Solid rocket booster ignition and liftoff!";
								  
								  while (time > -1) {
								      console.log(time === 50 ? t50 : "")
								      +(time === 31 ? t31 : "")
								      +(time === 16 ? t16 : "")
								      +(time === 10 ? t10 : "")
								      +(time === 6 ? t6 : "")
								      +(time === 0 ? t0 : "");
								      time --;
								  }
								  `
				- For Loops
				  collapsed:: true
					- They have the same 3 parts as while loops but they're more explicit about stating them and you'll get an error if any are left out i.e. `Uncaught SyntaxError: Unexpected token`
					- Template
					  `javascript
					  for ( start; stop; step ) {
					    // do this thing
					  }
					  `
					- Examples
						- See nested loop examples
						- Print out values 0 to 5
							- code
							  `javascript
							  for (var i = 0; i < 6; i = i + 1) { 
							  console.log("Printing out i = " + i); 
							  } 
							  `
							  
							  Prints:
							   Printing out i = 0
							   Printing out i = 1
							   Printing out i = 2
							   Printing out i = 3
							   Printing out i = 4
							   Printing out i = 5
						- Rewrite `while` loop to a `for` loop
						  collapsed:: true
							- While loop
							  ```javascript
							  var x = 9;
							  while (x >= 1) {
							      console.log("hello " + x);
							      x = x - 1;
							  }
							  ```
							- For loop
							  ```javascript
							  for (var x=9; x>=1; x--) {
							      console.log("hello " + x);
							  }
							  ```
						- Factorial of the number 12
							- What is a factorial
							  collapsed:: true
								- A factorial is calculated by multiplying a number by all the numbers below it. For instance, 3! or "3 factorial" is 3 * 2 * 1 = 6
									- 3!=3∗2∗1=6 3! = 3 * 2 * 1 = 6 3!=3∗2∗1=6 4!=4∗3∗2∗1=24 4! = 4 * 3 * 2 * 1 = 24 4!=4∗3∗2∗1=24 5!=5∗4∗3∗2∗1=120 5! = 5 * 4 * 3 * 2 * 1 = 120 5!=5∗4∗3∗2∗1=120
							- Code
							  `javascript
							  var solution = 1;
							  for (var i = 1; i <= 12; i++) {
							      solution *= i;
							  }
							  console.log(solution);
							  `
				- Nested Loops
				  collapsed:: true
					- Example 1
					  collapsed:: true
						- Code
						  `javascript
						  for (var x = 0; x < 5; x = x + 1) {
						    for (var y = 0; y < 3; y = y + 1) {
						      console.log(x + "," + y);
						    }
						  }
						  `
						- Prints
						  `javascript
						  Prints:
						   0, 0
						   0, 1
						   0, 2
						   1, 0
						   1, 1
						   1, 2
						   2, 0
						   2, 1
						   2, 2
						   3, 0
						   3, 1
						   3, 2
						   4, 0
						   4, 1
						   4, 2
						  `
						- Explanation
							- Notice the order that the output is being displayed.
								- For each value of x in the outer loop, the inner for loop executes completely. The outer loop starts with x = 0, and then the inner loop completes it's cycle with all values of y:
								- x = 0 and y = 0, 1, 2 // corresponds to (0, 0), (0, 1), and (0, 2)
							- Once the inner loop is done iterating over y, then the outer loop continues to the next value, x = 1, and the whole process begins again.
								- x = 0 and y = 0, 1, 2 // (0, 0) (0, 1) and (0, 2) x = 1 and y = 0, 1, 2 // (1, 0) (1, 1) and (1, 2) x = 2 and y = 0, 1, 2 // (2, 0) (2, 1) and (2, 2) etc.
					- Find my seat
						- Code
						  `javascript
						  for (var row=0; row<26; row++) {
						      for (var seat=0; seat<100; seat++) {
						          console.log(row+"-"+seat)
						      }
						  }
						  `
				- Operators
				  collapsed:: true
					- Increment
						- Increment by 1
						  `x++` or `++x` = `x=x+1`
							- `x++` will return the `x` value first, then run the whole `+1` for the second loop
							- `++x` however will show `x+1` even for the first loop
						- Increment by 3
						  `x += 3` // same as `x = x + 3`
						- Increment by multiplication
						  `x *= 2` // same as `x = x * 2`
					- Decrement
						- Decrement by 1
						  `x--` or `--x` // same as `x = x - 1`
						- Decrement by 6
						  `x -= 6` // same as `x = x - 6`
						- Decrement by division
						  `x /= 5` // same as `x = x / 5`
			- 5) Functions
			  collapsed:: true
				- Intro
				  collapsed:: true
					- A function is a like a shortcut or script which allow you to package up lines of code that you can use (and often reuse) in your programs
					- You call it like a variable
				- Function body - enclosed in curly brackets
				  `javascript
				  function add(x, y) {
				    // function body!
				  }
				  `
				- Parameters vs. Arguments
				  collapsed:: true
					- A parameter is always going to be a variable name and appears in the function declaration.
					- An argument is always going to be a value (i.e. any of the JavaScript data types - a number, a string, a boolean, etc.) and will always appear in the code when the function is called or invoked.
					- _Parameters_
					  collapsed:: true
						- Sometimes they take parameters i.e. `name` and `otherName`
						  `javascript
						  function doubleGreeting(name, otherName) {
						    // name and otherName are both parameters
						  }`
						- Or they might have none so they're just `()`
						  id:: 629ccb26-0162-482f-b359-777c83c4cb82
						  ```javascript
						  function sayHello() {
						    var message = "Hello!"
						    console.log(message);
						  }
						  ```
					- e.g. [findAverage](((629ccb26-1bf3-46d6-a25c-4847e18ba9b9))) , [add(x, y)](((629ccb26-d1f3-4ec1-9e2a-1e06a5739a58)))
				- How to run a function
				  collapsed:: true
					- Invoke or call a function using the function name, followed by parantheses with any _arguments_ passed into it
					  e.g. `add(1, 2);`
					- e.g. [sayHello](((629ccb26-9322-4fdb-95cb-82d96f9cec11)))
						- {{embed ((629ccb26-9322-4fdb-95cb-82d96f9cec11))}}
				- Examples
				  collapsed:: true
					- sayHello
					  id:: 629ccb26-9322-4fdb-95cb-82d96f9cec11
					  ```javascript
					  // declares the sayHello function
					  function sayHello() {
					    var message = "Hello!"
					    return message; // returns value instead of printing it
					  }
					  
					  // function returns "Hello!" and console.log prints the return value
					  console.log(sayHello());
					  ```
					- findAverage
					  id:: 629ccb26-1bf3-46d6-a25c-4847e18ba9b9
					  ```javascript 
					  function findAverage(x, y) {
					    var answer = (x + y) / 2;
					    return answer;
					  }
					  
					  var avg = findAverage(5, 9);
					  ```
						- x and y are parameters! They are defined in the function declaration.
						- The values 5, and 9 are passed in as function arguments.
					- add(x, y)
					  id:: 629ccb26-d1f3-4ec1-9e2a-1e06a5739a58
					  ```javascript
					  // x and y are parameters in this function declaration
					  function add(x, y) {
					    // function body
					    var sum = x + y;
					    return sum; // return statement
					  }
					  
					  // 1 and 2 are passed into the function as arguments
					  var sum = add(1, 2);
					  ```
					- LaughItOff1
					  ```javascript
					  function laugh() {
					      var message = "hahahahahahahahahaha!";
					      return message;
					  }
					  
					  console.log(laugh());
					  ```
					- Laugh It Off 2
					  collapsed:: true
						- Solution 1
						  `javascript
						  function laugh(num) {
						      return "ha".repeat(num) + "!";
						  }
						  
						  console.log(laugh(10)); // hahahahahahahahahaha!
						  console.log(laugh(3)); // hahaha!
						  console.log(laugh(2)); // haha!
						  console.log(laugh(1)); // ha!
						  console.log(laugh(0)); // !
						  `
						- Solution 2
						  `javascript
						  function laugh(num) {
						      var output = "";
						      for (var i = 0; i < num; i++) {
						          output += "ha";
						      }
						      return output + "!";
						  }
						  
						  console.log(laugh(10)); // hahahahahahahahahaha!
						  console.log(laugh(3));  // hahaha!
						  console.log(laugh(2));  // haha!
						  console.log(laugh(1));  // ha!
						  console.log(laugh(0));  // !
						  `
				- Return statements
				  collapsed:: true
					- Return statements explicitly make your function return a value
					  `return sum;`
					- More
					  collapsed:: true
						- In [Or they might have none so they're just `()`](((629ccb26-0162-482f-b359-777c83c4cb82))) a value is printed to the console with console.log, but not explicitly returned with a return statement. You can write a return statement by using the return keyword followed by the expression or value that you want to return.
						   ```javascript
						  // declares the sayHello function 
						  function sayHello() {
						   var message = "Hello!"
						   return message; // returns value instead of printing it 
						  } 
						  ```
					- Returning vs. Logging
					  collapsed:: true
						- Logging = `console.log()`
						  **Prints** a value to the JavaScript console
							- Only displays a value (that you can view for debugging purposes), but the value it displays can't really be used for anything more than that.
						- Returning = `return`
						  Stops execution of a function and **returns** a value back to the caller
							- If you don't explicitly define a return value, the function will return `undefined` by default.
							- If you enter in two or more `return` statements then only the first one will be used
					- A function's return value can be stored in a variable or reused throughout your program as a function argument.
					- Examples
					  collapsed:: true
						- Combining return values from two functions together
							- Example
							  `javascript
							  // returns the sum of two numbers
							  function add(x, y) {
							    return x + y;
							  }
							  
							  
							  // returns the value of a number divided by 2
							  function divideByTwo(num) {
							    return num / 2;
							  }
							  
							  
							  var sum = add(5, 7); // call the "add" function and store the returned value in the "sum" variable
							  var average = divideByTwo(sum); // call the "divideByTwo" function and store the returned value in the "average" variable
							  `
							- Example2 (answer = 4)
							  `javascript
							  function addTen(x) {
							    return x + 10;
							  }
							  
							  function divideByThree(y) {
							    return y / 3;
							  }
							  
							  var result = addTen(2);
							  console.log(divideByThree(result));
							  `
				- Scope, Shadowing
				  collapsed:: true
				  id:: 632092fe-f539-4562-b034-7b66bd756be5
					- Scope
					  collapsed:: true
						- Variables etc may be accessible everywhere within program or only via their specific function
						- Types of Scopes
							- See ES6 Block scope for more
							- Global Scope - identifiers which can be accessed everywhere within your program
							- Function Scope - identifiers that can be accessed everywhere inside the function it was defined in
								- It's defined within the { } of a function
						- Examples
							- Example1 - `a` is global scope
							  ```javascript
							  var a = 1;
							  function x() {
							    var b = 2;
							    function y() {
							      var c = 3;
							      function z() {
							        var d = 4;
							      }
							      z();
							    }
							    y();
							  }
							  
							  x();
							  ```
								- Where can you print out the value of variable c without resulting in an error?
								  Anywhere inside function `y()` or `z()`
					- Shadowing
					  collapsed:: true
						- Using the same variable multiple times in a program will make the results additive (if numerical) or use the last modification (if text)
						  collapsed:: true
							- Example1 - answer here is `4`
							  `javascript
							  vvar x = 1;
							  
							  function addTwo() {
							    x = x + 2;
							  }
							  
							  addTwo();
							  x = x + 1;
							  console.log(x);
							  `
						- If you give a variable a new value within a function scope by using `var`, then it won't affect the global variable result
							- Example1
							  `javascript
							  var x = 1;
							  
							  function addTwo() {
							    var x = x + 2;
							  }
							  
							  addTwo();
							  x = x + 1;
							  console.log(x);
							  `
								- Explanation
									- The global variable x is incremented by 1. Since the global variable's original value was 1, and it was incremented by 1, console.log will print out 2.
									- The variable assignment inside the function addTwo() only has function scope, so its affect is not reflected outside the function.
					- When trying to access an identifier, the JavaScript Engine will first look in the current function. If it doesn't find anything, it will continue to the next outer function to see if it can find the identifier there. It will keep doing this until it reaches the global scope.
					- Global variables aren't always the answer
						- Global identifiers are a bad idea. They can lead to bad variable names, conflicting variable names, and messy code.
						- So you might be wondering: "Why wouldn't I always use global variables? Then, I would never need to use function arguments since ALL my functions would have access to EVERYTHING!"
						- Well... Global variables might seem like a convenient idea at first, especially when you're writing small scripts and programs, but there are many reasons why you shouldn't use them unless you have to. For instance, global variables can conflict with other global variables of the same name. Once your programs get larger and larger, it'll get harder and harder to keep track and prevent this from happening.
						- There are also other reasons you'll learn more about in more advanced courses. But for now, just work on minimizing the use of global variables as much as possible.
						-
				- Hoisting
				  collapsed:: true
					- Though you should always write top-to-bottom, function arguments are "hoisted" to the top (read first by the interpreter)
					- Function and variable declarations get hoisted, but variable assignments are not hoisted (i.e. variables will exist but will be `undefined`)
					  collapsed:: true
						- Example1
						  `javascript
						  sayHi("Julia");
						  
						  function sayHi(name) {
						    console.log(greeting + " " + name);
						    var greeting = "Hello";
						  }
						  `
							- Equivalent to
							  `var greeting;
							  console.log(greeting + " " + name);
							  greeting = "Hello";
							  `
					- Always declare functions at the top of the scripts, and variables at the top of the functions, so the syntax and behavior are consistent with each other.
				- Example
			- 6) Arrays
			- 7) Objects
			- _Assorted_
				- Javascript code comments
				  id:: 646349ae-f6ad-4d1e-a2d5-8e9caa13af70
				  collapsed:: true
					- Example 1
					  ```javascript
					  // this is 
					  // a comment
					  ```
					- Eg2
					  ```javascript
					  /* 
					  this is 
					  a comment
					  */
					  ```
				- Instead of concatenating, can use `${variableName}` and keep the whole thing between two `
				  collapsed:: true
					- Example
					  console.log(`${suspect} did it in the ${room} with the ${weapon}!`);
				- Pretty confusing [Murder mystery game](((629ccb26-a2d8-46e3-bb60-21d87e63db60)))
			- [Forum](https://discussions.udacity.com/c/standalone-courses/intro-to-javascript)
	- ## Learning resource sorted by priority
	  id:: 629d4e63-367b-48ab-a942-170b827a143f
		- Sorted by priority
			- [All JavaScript and TypeScript Features of the last 3 years | by Linus Schlumberger | Better Programming](https://medium.com/@LinusSchlumberger/all-javascript-and-typescript-features-of-the-last-3-years-629c57e73e42)
		- Regularly updated
			- [ECMAScript® 2023 Language Specification](https://262.ecma-international.org)
			  id:: 6579fcc0-3004-4cdb-a9d2-59af1450fa77
			  collapsed:: true
			  See Introduction section on webpage for yearly changelog
				- Changes summary
					- ECMAScript 2023, the 14th edition, introduced the ((657a032d-9e70-4c5a-a1da-aaae4d7d1730)), ((657a0339-beca-427d-9840-468296d19588)), ((657a04d8-14b8-4e87-9763-a68fc3215d08)), ((646349b0-29c2-4fc3-9beb-1582086c806c)), and ((646349b0-1bfd-4201-a31e-3882ac88972b)) methods on `Array.prototype` and `TypedArray.prototype`, as well as the ((657a032a-26ac-4c21-99ee-d33ff1fc3e78)); added support for `#!` comments at the beginning of files to better facilitate executable ECMAScript files; and allowed the use of most Symbols as keys in weak collections.
						- Also:
							- ((6579fe15-797f-4976-a9a1-2f7a4d0995a7))
					- ECMAScript 2022, the 13th edition, introduced top-level `await`, allowing the [keyword](https://262.ecma-international.org/#sec-keywords-and-reserved-words) to be used at the top level of modules; new class elements: public and private instance fields, public and private static fields, private instance methods and accessors, and private static methods and accessors; static blocks inside classes, to perform per-class evaluation initialization; the `#x in obj` syntax, to test for presence of private fields on objects; regular expression match indices via the `/d` flag, which provides start and end indices for matched substrings; the `cause` property on `Error` objects, which can be used to record a causation chain in errors; the `at` method for Strings, Arrays, and TypedArrays, which allows relative indexing; and `Object.hasOwn`, a convenient alternative to `Object.prototype.hasOwnProperty`.
					- ECMAScript 2021, the 12th edition, introduced the `replaceAll` method for Strings; `Promise.any`, a Promise combinator that short-circuits when an input value is fulfilled; `AggregateError`, a new Error type to represent multiple errors at once; logical assignment operators (`??=`, `&&=`, `||=`); `WeakRef`, for referring to a target object without preserving it from garbage collection, and `FinalizationRegistry`, to manage registration and unregistration of cleanup operations 
					  performed when target objects are garbage collected; separators for numeric literals (`1_000`); and `Array.prototype.sort` was made more precise, reducing the amount of cases that result in an [implementation-defined](https://262.ecma-international.org/#implementation-defined) [sort order](https://262.ecma-international.org/#sort-order).
					- ECMAScript 2020, the 11th edition, introduced the `matchAll` method for Strings, to produce an iterator for all match objects generated by a global regular expression; `import()`, a syntax to asynchronously import Modules with a dynamic specifier; `BigInt`, a new number primitive for working with arbitrary precision [integers](https://262.ecma-international.org/#integer); `Promise.allSettled`, a new Promise combinator that does not short-circuit; `globalThis`, a universal way to access the global `this` value; dedicated `export * as ns from 'module'` syntax for use within modules; increased standardization of `for-in` enumeration order; `import.meta`, a [host](https://262.ecma-international.org/#host)-populated object available in Modules that may contain contextual information about the Module; as well as adding two new syntax features to improve working with “nullish” values (null or undefined): nullish coalescing, a value selection operator; and optional chaining, a property access and function invocation operator that short-circuits if the value to access/invoke is nullish.
			- [tc39/proposals: Tracking ECMAScript Proposals](https://github.com/tc39/proposals)
			  id:: 657a009b-e9e7-43e4-a2b4-1cb135d98e18
		- Sorted by difficulty
		  collapsed:: true
			- Beginner-Advanced
				- [JavaScript 2022 | Pluralsight path](https://app.pluralsight.com/paths/skills/javascript-2022)
				  id:: 65500703-75a9-4a9c-8cd6-08519600f536
				  collapsed:: true
					- Novice
						- [JavaScript: The Big Picture](https://app.pluralsight.com/library/courses/javascript-big-picture)
					- Entry-level
						- [JavaScript Fundamentals](https://app.pluralsight.com/library/courses/fundamentals-javascript)
						- [Debugging JavaScript Applications](https://app.pluralsight.com/library/courses/javascript-debugging-applications)
					- Practitioner
						- [Arrays and Objects in JavaScript](https://app.pluralsight.com/library/courses/javascript-arrays-objects)
						- Strings and Regular Expressions in JavaScript
						- Functions in JavaScript
						- Error Handling in JavaScript
						- Looping and Branching in JavaScript
						- Asynchronous Programming in JavaScript
						- Network Requests in JavaScript
						- Modules in JavaScript
						- JavaScript in the Browser
						- Package Management in JavaScript with npm and Yarn
						- JavaScript Unit Testing with Jest
						- Building a REST API in JavaScript with Express
						- Building a Web Application with JavaScript
					- Advanced
					  id:: 655007c9-5a7b-4d3b-897e-d24db018a0b7
					  collapsed:: true
						- [Object-oriented Concepts in JavaScript](https://app.pluralsight.com/library/courses/javascript-object-oriented-concepts)
						  id:: 654fdf5c-2455-4dc2-ad96-b60cd6fd1ddd
						  collapsed:: true
						  Paused this because OO is never used in JavaScript, and it's complexity makes me think I'm better off learning it in a real OO language
							- ## Course Introduction
							  collapsed:: true
								- JavaScript is a prototypes-based language instead an object-based ones
								- ### What is Object-oriented Programming
									- Object-oriented Concepts
										- Encapsulation - grouping of data or functionality e.g. a Person, Vehicle
										- Composition - composing objects from other objects e.g. Person object might also contain their own Vehicle object
										  collapsed:: true
											- Classes are typically used to create a set of objects with a consistent set of properties and functionality
											  collapsed:: true
												- ```js
												  class Person {
												    firstName = '';
												    lastName = '';
												    isAdult() { ... }
												  }
												  let jim = new Person('Jim', 'Cooper'); 
												  let kris = new Person('Kris', 'Cooper');
												  ```
										- Inheritance
										  collapsed:: true
											- Allows us to create additional types of objects that inherit properties and methods from another type of object
											- e.g. Student extends Person class
										- Polymorphism
										  collapsed:: true
											- One aspect is that an object inherits from another object can be used as if it were the parent object
											  collapsed:: true
												- e.g. if a function expects a Person object to be entered you can instead use the Student object instead there since you know it'll inherit the same methods and properties
											- Another aspect is to do with overriding methods. We can code overrides in the extended class (e.g. Student) so that it doesn't inherit, it'll instead use a different method/property
											-
								- ### JavaScript is a Loosely-typed, Prototype-based Language
									- Loosely-typed means we just use the keyword `let` and JavaScript infers the type of the variable
										- As opposed to strongly typed where we'd instead do `int age = 5`
									- JavaScript also doesn't do type checking on parameters
									- When you create new classes they're still of the data type object. As opposed to strongly-typed languages where you're actually creating a new data type e.g. Person
									- Classes-based vs Prototypes-based (objects)
									  collapsed:: true
										- ![image.png](../assets/image_1699750052006_0.png)
											- Pseudocode
											- JavaScript uses prototypes and objects, and even their "classes" still use prototypes behind-the-scenes
								- ### Using the [Stackblitz](https://stackblitz.com/) Environment
									- [StackBlitz | Instant Dev Environments | Click. Code. Done.](https://stackblitz.com/) uses an embedded ((63209272-1088-4824-a762-4ac7ded04b0a)) editor on the left and an embedded browser on the right
									- Fork this dev environment - [Object-Oriented JavaScript - StackBlitz](https://stackblitz.com/edit/oo-javascript)
									-
							- ## Understanding JavaScript Prototypes
							  collapsed:: true
								- ### How JavaScript Prototypes Work
									- ((646349b0-93d7-4477-add9-481d59e062c3)) can be used for inheritance
									- ((6550d30d-a061-4ad7-9a2b-5732508af02f))
									- ((646349b0-c2cf-4be8-8ad1-b93767059a94)) can be used to find out an object's prototype
								- ### Instance vs Prototype Properties
									- ((646349b0-11fb-44f1-a715-ee5bd59d8f1c)) is used to find out if an object inherits a property
									- ((65539093-0042-4124-8394-bb0f4b8ecd9d))
									- Child objects inherit properties and methods from their prototype
								- ### Creating Prototype Chains
									- Multiple levels of inheritance
									- All objects created in JavaScript have the prototype `Object`, and this holds all the methods such as ((64024e3f-34f6-4295-8f37-be8258ca0c9e))
									- ((646349b0-93d7-4477-add9-481d59e062c3)) can be used for this
										- ((655392b4-1e44-4721-ad10-c6f13b7055fd))
							- ## Using JavaScript Constructor Functions
								- See intro for why these are useful
								- ### Using JavaScript Constructor Functions
								  collapsed:: true
									- Classes are just syntactic sugar on top of constructor functions
									- Constructor functions are functions which are used to construct new objects
									- Constructor function compared to an object prototype
										- id:: 6553cab5-299d-4490-aa61-6f7190b83b8e
										  ```js
										  // Constructor function
										  function Person(firstName, lastName, age) {
										    // Parameter values are assigned as properties on new objects created iwth this function
										    this.firstName = firstName;
										    this.lastName = lastName;
										    this.age = age;
										    // This isn't best practice - instead see "Adding Methods to a Constructor Function's Prototype"
										    this.fullName = function() {
										    	return `${this.firstName} ${this.lastName}`; 
										    }
										  }
										  
										  // Creating a new instance
										  let jim = new Person('Jim', 'Cooper', 29);
										  ```
											- ((64024e3f-159e-41ab-800d-5a5bf7e98bda)) refers to an object in memory, which one it is depends on the context in which it's called
											- ```js
											  jim.hasOwnProperty('firstname'); // This evaluates as `true` now, since unlike object prototypes this puts properties
											  								// on the instance itself
											  ```
										- ```js
										  // Object prototype
										  let Person = {
										    firstName: '',
										    lastName: '',
										    age: 21,
										    fullName() {
										      return `${this.firstName} ${this.lastName}`;
										    }
										  }
										  
										  // Creating a new instance
										  let jim = { firstName: 'Jim', lastName: 'Cooper', age: 29 }
										  Object.setPrototypeof(jim, Student);
										  ```
											- Much more verbose to create a new instance
								- ### Understanding the ((646349af-34cf-4f75-9faa-865b2c30af88)) Keyword
								  collapsed:: true
									- Does 4 things:
										- Creates a new object in-memory
										  logseq.order-list-type:: number
										- Binds ((64024e3f-159e-41ab-800d-5a5bf7e98bda)) to the new object
										  logseq.order-list-type:: number
										- Calls the function that follows the `new` keyword
										  logseq.order-list-type:: number
										- Implicitly returns the newly created object i.e. the constructor function doesn't need a `return` statement
										  logseq.order-list-type:: number
								- ### Adding Methods to a Constructor Function's Prototype
								  id:: e101673f-b28a-40dc-af87-231d1e344dc1
								  collapsed:: true
									- Old
									  ((6553cab5-299d-4490-aa61-6f7190b83b8e))
									- Best practice
									  ```js
									  // Constructor function
									  function Person(firstName, lastName, age) {
									    // Parameter values are assigned as properties on new objects created iwth this function
									    this.firstName = firstName;
									    this.lastName = lastName;
									    this.age = age;
									  }
									  // Best practice for how to add methods onto a constructor function
									  Person.prototype.fullName = function() {
									    return `${this.firstName} ${this.lastName}`; 
									  };
									  
									  // Creating a new instance
									  let jim = new Person('Jim', 'Cooper', 29);
									  ```
									- Every function you create has a prototype object which is created once we first define the function
									- Unlike objects which require ((646349b0-c2cf-4be8-8ad1-b93767059a94)) you can instead access a function's prototype using the `.prototype` property
										- e.g.
										  ```js
										  Person.prototype;
										  ```
										- ((646349b0-04f1-4f6c-a7ad-c0bb87216141))
									- An Object's Prototype is the object instance from which the object was inherited.
									- A Function’s Prototype is the object instance that will become the prototype for all objects created using this function as a constructor
										- ```js
										  // This means as soon as you create it using this:
										  this.fullName = function() {
										    	return `${this.firstName} ${this.lastName}`; 
										    }
										  
										  // It's now stored here in-memory as method on the `prototype` property
										  // and the old `this.fullName` line can be deleted
										  Person.prototype.fullName = function() {
										    	return `${this.firstName} ${this.lastName}`; 
										    }
										  
										  // You can even test this 
										  jim.hasOwnProperty('fullName'); // returns `false`
										  jim.getPrototypeOf().hasOwnProperty('fullName'); // returns `true`
										  ```
										- This prototype object (`Person.prototype`) becomes the prototype for any new object created by this constructor function
								- ### A Graphical Overview of Constructor Functions
								  collapsed:: true
									- As soon as we declare a Person constructor function, it creates a prototype in the background
										- ```js
										  function Person(firstName, lastName, age) {
										    this.firstName = firstName;
										    this.lastName = lastName;
										    this.age 
										  }
										  ```
										- Background
									- ```js
									  Person.prototype:
									  	__proto__: Object // The prototype of Person is by default Object
									  
									  Person.prototype.fullName = function () {} // Methods can be added to the Person prototype
									  ```
									- Creating a new object using this constructor function
										- ```js
										  let jim = new Person('Jim', 'Cooper', 29);
										  ```
										- It follows the `this` keywords in the constructor function to add these as new properties to the object
											- ```js
											  // jim
											  __proto__: Person
											  firstName: 'Jim'
											  lastName: 'Cooper'
											  age: 29;
											  ```
								- ### Creating Getter and Setter Properties
								  collapsed:: true
									- ```js
									  function Person(firstName, lastName, age) {
									    this.firstName = firstName;
									    this.lastName = lastName;
									    this.age = age;
									  }
									  Person.prototype.fullName = () => `${this.firstName} ${this.lastName}`;
									  ```
									- Getter properties are basically methods which are accessed like a normal property instead of as a function
									- Using an object literal:
										- ```js
										  let kris = {
										    firstName: 'Kris',
										    lastName: 'Cooper',
										    get fullName() {
										      return `${this.firstName} ${this.lastName}`;
										    }
										  }
										  ```
										- ((646349af-03ff-479d-9752-1f16dd01262d)) allows you to use `kris.fullName` to obtain the value. Notice there's no `()` unlike calling a method
									- Note: you can't use ((646349af-03ff-479d-9752-1f16dd01262d)) inside a function e.g. the Person constructor function
									- You can use it inside the Person constructor function in one of two ways:
									  collapsed:: true
										- Simple way by adding ((646349af-03ff-479d-9752-1f16dd01262d)) and ((646349af-6311-4d14-b0ad-1c303197741b)) properties to the prototype
											- ```js
											  function Person(firstName, lastName, age) {
											    this.firstName = firstName;
											    this.lastName = lastName;
											    this.age = age;
											  }
											  
											  Person.prototype = {
											    get fullName() {
											      return `${this.firstName} ${this.lastName}`;
											    },
											    set fullName(fullName) {
											      let nameParts = fullName.split(' ');
											      this.firstName = nameParts[0];
											      this.lastName = nameParts[1];
											    }
											  }
											  ```
										- Verbose way using ((63679853-849e-4274-8f95-b5178cb66a6c)). Not used frequently unless you want to set other properties like `writeable`
											- ```js
											  function Person(firstName, lastName, age) {
											    this.firstName = firstName;
											    this.lastName = lastName;
											    // Below is equivalent to `this.age = age;``
											    // This is a lot more verbose 
											    Object.defineProperty(this, 'age', {
											      value: age
											    })
											  }
											  ```
											- How to use with ((646349af-03ff-479d-9752-1f16dd01262d)):
											  collapsed:: true
												- ```js
												  function Person(firstName, lastName, age) {
												    this.firstName = firstName;
												    this.lastName = lastName;
												    this.age = age;
												    Object.defineProperty(this, 'fullName', {
												      get: () => `${this.firstName} ${this.lastName}`;
												    })
												  }
												  ```
												- Allows you to access it like a property e.g:
												  ```js
												  let jim = new Person('Jim', 'Cooper', 29);
												  console.log(jim.fullName);
												  ```
											- How to use with ((646349af-6311-4d14-b0ad-1c303197741b)):
											  collapsed:: true
												- ((646349af-6311-4d14-b0ad-1c303197741b)) works like ((646349af-03ff-479d-9752-1f16dd01262d)) but in the opposite direction
												- ```js
												  function Person(firstName, lastName, age) {
												    this.firstName = firstName;
												    this.lastName = lastName;
												    this.age = age;
												    Object.defineProperty(this, 'fullName', {
												      get: () => `${this.firstName} ${this.lastName}`;
												      // This setter function allows you to change the 'fullName' of someone
												      set: () => {
												      	let nameParts = fullName.split(' ');
												      	this.firstName = nameParts[0];
												      	this.lastName = nameParts[1];
												    	}
												    })
												  }
												  ```
												- This then allows you to use `jim.fullName = 'John Doe';` to easily change the `fullName`
								- ### Creating Static Properties
									-
								- ### Creating Static Methods
								- ### Creating Private Properties with Closures
								- ### Creating Private Methods with Closures
							- ## Inheritance with Constructor Functions and Prototypes
							- ## Using JavaScript Classes
							- ## Inheritance with JavaScript Classes
								- ### Inheritance with JavaScript Classes
								- ### Inheritance with Class Constructors
								- ### Using the typeof and instanceof Operators
								- ### Polymorphism with JavaScript Classes
								- ### Overriding Methods in JavaScript Classes
								- ### A Word of Warning About Object-oriented Design
									- Search `what is wrong with object oriented programming`
									- Gives the example of using many classes for vehicles, cars, engine etc. But then along comes electric cars and they lack an engine and use different fuel. This results in months of refactoring if you've got a large codebase
									- Classes are still being used in modern JavaScript applications but not large inheritance chains. Instead composition is being used, and some instead go as far as using ((63fe5474-f771-4530-8f8a-58b55c71204e))
							- Related:
								- ((63fe5472-f72c-4a29-9067-7d7edc128d06))
								- ((f16a5715-3945-4df4-88e5-598969dec550))
						- [Functional Programming Concepts in JavaScript](https://app.pluralsight.com/library/courses/javascript-functional-programming-concepts)
						  id:: 654fdfa7-337d-4fa9-915b-a1ce80421fde
						- Transpiling and Polyfills for Extended JavaScript Support
					- Expert
						- Proxy Objects and Reflect in JavaScript
						- Web Assembly Interaction with JavaScript
			- _Beginner_
			  id:: 629d542c-4f95-4966-84fe-a2170d83484d
				- ((646349ac-4774-4376-b96f-863fd43d5b4d))
				  collapsed:: true
					- {{embed ((646349ac-4774-4376-b96f-863fd43d5b4d))}}
				- Watch and Code's Programming Foundations (JavaScript beginner course by Gordon Zhu)
				  #A005 ~/Documents/MUSEUM/Programming/Anki1.ods / AKA practical-javascript2
				  collapsed:: true
				  id:: 629ccb27-9bb8-46a3-8ae8-33d6da62dbcc
					- Successor to [Watch and Code's Practical JavaScript](((629ccb27-6855-4209-8a01-0e0b2afd59e8)))
						- OLD: Watch and Code's Practical JavaScript (11 hr JS course by Gordon Zhu)
						  id:: 629ccb27-6855-4209-8a01-0e0b2afd59e8
						  collapsed:: true
						  #A004
							- Highly recommended on /r/learnprogramming
							- Old data store
							  https://plnkr.co/edit/gOUroVG2g2Z16fjnJK0Q?preview
							- Note: replaced by [Watch and Code's Programming Foundations](((629ccb27-9bb8-46a3-8ae8-33d6da62dbcc)))
							- Screen setup for learning - 3 tiles via Vivaldi (Dynalist, W&C, Plunker
							  collapsed:: true
								- Vivaldi
								  https://i.imgur.com/80A1rk6.png
								- Firefox
								  https://i.imgur.com/aULh5Fr.png
								- [Plunker](((629ccb26-b915-4995-b035-f7960ee4b57e)))
							- Facebook group
							  https://www.facebook.com/groups/514043678767094/
							- _Modules_
								- Introduction
								  collapsed:: true
									- Everything is a todo list-type structure e.g. search results show you a list of data, tweet timeline is a list of tweets, chat apps are a list of messages
									-
									- The program is broken up into three stages. Each stage is drastically different because as you get better, you’ll need to do different things to improve. If you keep doing the same thing, you’ll stagnate.
									  collapsed:: true
										- The brief beginning stage (essentially Practical JavaScript) is an introduction to the mechanics of programming. This is a short but important part of Watch and Code as it sets the foundation for everything that comes next.
										- The middle stage teaches you how to read code so that you can make sense of existing programs. This is the bulk of the Watch and Code experience and the most important part by a wide margin.
										- In the later stage, you’ll learn through contributing to existing software projects. Your role will change from a consumer (someone that just reads code) to a producer (someone that writes code).
									- Office hours AMA
									  collapsed:: true
										- The best way to get help if you get stuck is to ask your question during our weekly live office hours, which occur every Monday at 6PM PST. To register for office hours, join the [Watch and Code Facebook group](https://www.facebook.com/groups/514043678767094/) and then you'll find detailed information in the events section.
										- If attending office hours is not an option, you can [submit a question using this form](https://github.com/gordonmzhu/questions/issues/new?template=Custom.md). There's a link to this form below every lesson, so it'll always be there if you get stuck.
								- Module 1: Array
									- _Requirements_
									  collapsed:: true
										- It should have a place to store to-dos
											- `var todos = ['item 1', 'item 2', 'item 3']`
												- ie brackets [ ]
											- You can then later call this variable by simply typing `todos`
										- It should have a place to display to-dos
											- console.log('My Todos:',todos)
											- _Prints: _ `My Todos: ['item 1', 'item 2', 'item 3']`
										- It should have a place to add new to-dos
											- `todos.push('item 4')`
												- ie parentheses ( )
											- Now `todos` shows `['item 1', 'item 2', 'item 3', 'item 4']`
										- It should have a place to change to-dos
											- `todos[0]` pulls `'item 1'`
											- `todos[0] = 'item 1 updated'` makes it now `'item 1 updated'`
										- It should have a place to delete to-dos
											- `todos.splice(0, 1)`
											- `0` is for what position to start deleting items
											- `1` is for how many items to delete
									- Array = list
								- Module 2: Functions
								  collapsed:: true
									- _Intro_
									  collapsed:: true
										- Functions are like recipes - A series of stored steps grouped under a single name, which is performed every time the function is called
										- They are structured like so
										  `function makeTurkeySandwch() {
										   step1;
										   step2;
										  }`
										- Call it like `makeTurkeySandwich()`
									- Customising Functions
									  collapsed:: true
										- Rather than making one function for every possibility, you can instead use the parameter `()` of your function - which can either be a variable or just a string
										- () is called a parameter when creating your function, and it's called an argument when calling your function
										- Example with variable
										  `var filling = ['mayonaise', 'ketchup']
										  
										  function makeSandwichWith(filling) {
										   step1;
										   step2 add filling;
										  }`
										  
										  Calling it with:
										  `makeSandwichWith(ketchup)`
										- Example with string
										  `function makeSandwichWith(filling) {
										   step1;
										   step2 add filling;
										  }`
										  
										  Calling it with:
										  `makeSandwichWith('ketchup')`
									- _Requirements_
										- `var todos = ['item 1', 'item 2', 'item 3'];`
										- It should have a function to display to-dos
										  collapsed:: true
											- Example
											  `var todos = ['item 1', 'item 2', item 3']
											  
											  function displayTodos() {
											   console.log('My todos:', todos);
											  }`
										- It should have a function to add new to-dos
										  collapsed:: true
											- Example
											  `function addTodo(todo) { // todo is a new variable which your function will take
											   todos.push(todo); // the parameter of the function uses the variable at this point within the function
											   displayTodos; // shows your updated todos list after
											  }`
											  
											  **Example utilisation:**
											  `addTodo('some stuff')`
										- It should have a function to change to-dos
										  collapsed:: true
											- Example
											  `function changeTodo(position, newValue) {
											   todos[position] = newValue; // choose which todo to update, then the value it should now be. Also note, position starts from 0 not 1
											   displayTodos(); // displays the todos after you update it
											  }`
											  
											  Example utilisation:
											  `changeTodo(0, 'changed')` 
											  // this changes the __first__ item to 'changed'
											  
											  Two parameters: position and newValue
										- It should have a function to delete to-dos
										  collapsed:: true
											- Example
											  `function deleteTodo(position) {
											    todos.splice(position, 1); // position and 1 for number of items to delete
											    displayTodos();
											   }
											   `
								- Interlude - Functions and variables (just discusses scope)
								- Module 3: Objects
								  collapsed:: true
									- _What is an object_
									  collapsed:: true
										- Example object - my computer
										  `var myComputer = {
										   operatingSystem: 'Linux',
										   screenSize: '13 inches',
										   purchaseYear: 2018
										  };
										  `
										- To see the properties in the object, you can use something like `myComputer.screenSize`
									- _Objects and functions_
									  collapsed:: true
										- Having a function as a property of an object is AKA a method
										- Example of an object which contains a function that can be used to reference the object itself
										  `var gordon = {
										   name: 'Gordon'
										   sayName: function() {
										    console.log(this); // 'this' is a JavaScript tool to reference the object itself 
										   }
										  }
										  `
											- To print the object, use `gordon.sayName();`
										- Example of an object which contains a function that can be used to reference an object property
										  `var gordon = {
										   name: 'Gordon'
										   sayName: function() {
										    console.log(this.name); // 'this' is a JavaScript tool to reference the object itself 
										   }
										  }
										  `
											- To print the object property, use `gordon.sayName();`
										- This function is an _anonymous function_ because it doesn't have a name, it's simply referenced by the property name
									- _Plunker_
									  collapsed:: true
										- https://plnkr.co
										- Pros/Cons vs console.log
											- Lets you type in multiple lines at once rather than entering after every line
											- You can save your work
										- OR alternative recommended by Tom and used by many: [Visual Studio Code](((629ccb26-e54b-4851-8144-32c05a7e8b5b)))
										- CTRL+/ to uncomment multiple lines
									- [online copy]
									  https://plnkr.co/edit/gOUroVG2g2Z16fjnJK0Q v3.js
									- [offline backup - 23/10/19]
									  /home/boss/Documents/MUSEUM/Programming/Practical_JavaScript_course/pjs-v3.js
									- Objects start and end like this
									  ```var todoList = {
									   something: 
									  };
									  ```
									  
									  OR if it's multiple properties: 
									  ```var todoList = {
									   something: ,
									   something2: 
									  };
									  
									  ```
									- _It should store the todos array on an object_
									  collapsed:: true
										- Example
										  `var todoList = {
										    todos: ['item 1', 'item 2', 'item 3'],
										  };`
									- _It should have a displayTodos method_
									  collapsed:: true
										- Example
										  `var todoList = {
										    todos: ['item 1', 'item 2', 'item 3'], // 1) todos array is in an object
										    displayTodos: function() {
										      console.log('My Todos', this.todos);
										    } 
										  };
										  `
									- _It should have an addTodo method_
									  collapsed:: true
										- Example
										  `var todoList = {
										    todos: ['item 1', 'item 2', 'item 3'], // 1) todos array is in an object
										    displayTodos: function() { // has a displayTodos method
										      console.log('My Todos', this.todos);
										    } 
										    addTodos: function(todo) { // has an addTodo method
										      this.todos.push(todo); // 'this' is added because you're referring the todoList object that this function is contained within
										      this.displayTodos(); 
										    }
										  };
										  `
									- _It should have a changeTodo method_
									  collapsed:: true
										- Example
										  `var todoList = {
										    todos: ['item 1', 'item 2', 'item 3'], // 1) todos array is in an object
										    displayTodos: function() { // has a displayTodos method
										      console.log('My Todos', this.todos);
										    },
										    addTodos: function(todo) { // has an addTodo method
										      this.todos.push(todo); // 'this' is added because you're referring the todoList object that this function is contained within
										      this.displayTodos(); 
										    },
										    changeTodo: function(position, newValue) { //has a changeTodo method
										      this.todos[position] = newValue;
										      this.displayTodos();
										    }
										  };
										  `
									- _It should have a deleteTodo method_
									  collapsed:: true
										- Example
										  `var todoList = {
										    todos: ['item 1', 'item 2', 'item 3'], // 1) todos array is in an object
										    displayTodos: function() { // has a displayTodos method
										      console.log('My Todos', this.todos);
										    },
										    addTodos: function(todo) { // has an addTodo method
										      this.todos.push(todo); // 'this' is added because you're referring the todoList object that this function is contained within
										      this.displayTodos(); 
										    },
										    changeTodo: function(position, newValue) { //has a changeTodo method
										      this.todos[position] = newValue;
										      this.displayTodos();
										    },
										    deleteTodo: function(position) {
										      this.todos.splice(position, 1);
										      this.displayTodos();
										    }
										  };
										  `
									- Final version
									  collapsed:: true
										- Example
										  `var todoList = {
										    todos: ['item 1', 'item 2', 'item 3'], // 1) todos array is in an object
										    displayTodos: function() { // has a displayTodos method
										      console.log('My Todos', this.todos);
										    },
										    addTodos: function(todo) { // has an addTodo method
										      this.todos.push(todo); // 'this' is added because you're referring the todoList object that this function is contained within
										      this.displayTodos(); 
										    },
										    changeTodo: function(position, newValue) { //has a changeTodo method
										      this.todos[position] = newValue;
										      this.displayTodos();
										    },
										    deleteTodo: function(position) {
										      this.todos.splice(position, 1);
										      this.displayTodos();
										    }
										  };
										  `
								- Module 4: Booleans
								  collapsed:: true
									- [online copy]
									  https://next.plnkr.co/edit/gOUroVG2g2Z16fjnJK0Q v4.js
									- [offline backup - ?/10/19]
									  /home/boss/Documents/MUSEUM/Programming/Practical_JavaScript_course/pjs-v4.js
									- _todoList.addTodo should add objects_
									  collapsed:: true
										- Example
										  `var todoList = {
										    todos: [], // removed the simple text array
										    displayTodos: function() { 
										      console.log('My Todos', this.todos);
										    },
										    addTodo: function(todoText) { // parameter changed to instead reference a new method with this existing method
										      this.todos.push({ // our todos is no longer an array, instead we’re using an object so we need an additional method for the parameter
										        todoText: todoText, // 1st one is the static property name, 2nd one is referring to the dynamic parameter for this method (i.e. the argument that you pass when using this method)
										        completed: false
										      }); 
										      this.displayTodos(); 
										    }
										  };
										  `
										- Example adding to to the list
										  `todoList.addTodo('this is an object');`
									- _todoList.changeTodo should change the todoText property_
									  collapsed:: true
										- Example
										  ```var todoList = {
										    todos: [], 
										    displayTodos: function() { 
										      console.log('My Todos', this.todos);
										    },
										    addTodos: function(todoText) { 
										      this.todos.push({ 
										        todoText: todoText,
										        completed: false
										      }); 
										      this.displayTodos(); 
										    },
										    changeTodo: function(position, todoText) { // more descriptive parameter name to use todoText than newValue
										      // this.todos[position] = newValue; // old version, new version can access the property rather than the whole object
										      this.todos[position].todoText = todoText
										      this.displayTodos();
										    },
										    deleteTodo: function(position) { 
										      this.todos.splice(position, 1);
										      this.displayTodos();
										    }
										  };
										  ```
									- _todoList.toggleCompleted should change the completed property_
									  collapsed:: true
										- bang operator e.g. !true = false (basically gives the opposite)
											- Example
											  `var gordonBoolean = true
											  gordonBoolean = !gordonBoolean; // you just made it the opposite, so now it's false
											  console.log(gordonBoolean);
											  `Output = `false`
										- Example
										  `toggleCompleted: function(position) { // parameter is position so you can identify which todo to modify
										      var todo = this.todos[position];
										      todo.completed = !todo.completed; // this will flip it to true or false, the opposite of what it is initially
										      this.displayTodos();
										    }`
									- Whole app
									  collapsed:: true
										- Code
										  var todoList = {
										    todos: [], // removed the simple text array
										    displayTodos: function() { 
										      console.log('My Todos', this.todos);
										    },
										    addTodos: function(todoText) { 
										      this.todos.push({ // 'this' is added because you're referring the todoList object that this function is contained within. Swapped todo parameter for a method
										        todoText: todoText, // 1st one is the static property name, 2nd one is referring to the dynamic parameter for this method
										        completed: false
										      }); 
										      this.displayTodos(); 
										    },
										    changeTodo: function(position, todoText) { // more descriptive parameter name to use todoText than newValue
										      // this.todos[position] = newValue; // old version, new version can access the property rather than the whole object
										      this.todos[position].todoText = todoText
										      this.displayTodos();
										    },
										    deleteTodo: function(position) { 
										      this.todos.splice(position, 1);
										      this.displayTodos();
										    },
										    toggleCompleted: function(position) { 
										      var todo = this.todos[position];
										      todo.completed = !todo.completed; // this will flip it to true or false, the opposite of what it is initially
										      this.displayTodos();
										    }
										  };
								- [**<--created Anki cards up to here-->**](((629e07ee-075d-4a72-9bd0-fd63cd35f152)))
								- **<--submitted to GitHub snippets repo up to here-->**
								- _Modules I never managed to do_
								  collapsed:: true
									- Module 5: Loops
										- For loops
										  collapsed:: true
											- Format
											  `i = 0 // Initialisation
											  Say "hey" if i < 3 // Condition
											  Increase i by 1 // Final-expression
											  
											  for (initialisation; condition; final-expression) {
											   console.log("hey");
											  }
											  
											  for (var i = 0; i <3, i = i++) {
											   console.log("hey");
											  }
											  
											  // i = i + 1
											  // i++ 
											  // both the same
											  `
										- Looping over arrays
											-
									- Module 6: Thinking in Code
									- Interlude - Data types and comparisons
									- Version 7 - HTML and the DOM
									- Interlude - Don't wonder about things the debugger can tell you
									- Version 8 - Getting data from inputs
									- Version 9 - Escape from the console
									- Interlude - Functions inside of functions
									- Version 10 - Click to delete
									- Version 11 - Destroy all for loops
									- Interlude - Understanding *this*
								- Read this multiple times, it's the most important thing
								  https://medium.com/@gordon_zhu/how-to-be-great-at-asking-questions-e37be04d0603
							- Need to watch something on Debugging, because watchandcode relying on an old version of Plunker for debugging methodology
					- My workspace
						- v0.4 workspace - different browser and outliner
						  collapsed:: true
							- _Left screen_
								- Logseq - showing course notes
								- _In background_
									- Librewolf with separate tabs
										- _Default showing tab_
											- Dynalist - course notetaking
										- _In background tabs_
											- Local HTML file `file:///home/boss/Documents/Git/1MY%20REPOS/snippets/practical-javascript2/todoList.html` + [browser console](((629de044-7257-40d7-a227-70e6aa67d172))) as [live code editor](((629ccb27-2cb7-4ac2-bc16-90c66e156174)))
											- Watch And Code (with Picture-in-Picture for video)
							- _Right screen_
								- ((63209272-1088-4824-a762-4ac7ded04b0a)) (for editing code)
									- Open folder: `/home/boss/Documents/Git/1MY REPOS/snippets/`
								- See [Watch And Code (with Picture-in-Picture for video)](((629ccb27-f103-4d50-8386-59c70fc6a955))) (top-right quarter of right screen)
								- _In background_
									- GitKraken (for committing work as accountability/progress log)
									- LibreOffice Calc (for turning course notes into Anki flashcards)
									- Pomotroid
									- Anki
							- _Right half of screen_
							  (KWin quick tile to right - meta+right)
							- _Left half of screen_
							  (KWin quick tile to left - meta+left)
						- v0.3 workspace - second monitor added
						  collapsed:: true
							- _Left screen_
								- Brave with separate tabs
									- _Default showing tab_
										- Dynalist - course notetaking
									- _In background tabs_
										- Local HTML file + browser console as live code editor
										  [Either use Visual Studio Code+browser console OR just Web Maker as live code editor](((629ccb27-2cb7-4ac2-bc16-90c66e156174)))
										- Watch And Code (with Picture-in-Picture for video)
										  id:: 629ccb27-f103-4d50-8386-59c70fc6a955
							- _Right screen_
								- ((63209272-1088-4824-a762-4ac7ded04b0a)) (for editing code)
									- Open folder: `/home/boss/Documents/Git/1MY REPOS/snippets/`
								- See [Watch And Code (with Picture-in-Picture for video)](((629ccb27-f103-4d50-8386-59c70fc6a955))) (top-right quarter)
								- _In background_
									- GitKraken (for committing work as accountability/progress log)
									- LibreOffice Calc (for turning course notes into Anki flashcards)
									- Pomotroid
									- Anki
							- _Right half of screen_
							  (KWin quick tile to right - meta+right)
							- _Left half of screen_
							  (KWin quick tile to left - meta+left)
						- v0.2 workspace
						  https://i.imgur.com/4Lm6OrI.png
						  collapsed:: true
							- _Right half of screen_
							  (KWin quick tile to right - meta+right)
								- ((63209272-1088-4824-a762-4ac7ded04b0a)) (for editing code)
									- Open folder: `/home/boss/Documents/Git/1MY REPOS/snippets/`
							- _Left half of screen_
							  (KWin quick tile to left - meta+left)
								- Ungoogled Chromium with separate tabs
									- Dynalist
									- Watch And Code (with Picture-in-Picture for video. PiP can be either right or left bottom)
										- (background tab, and having the video shown via Picture-in-Picture extension on top-left quarter of screen)
									- Local HTML file + browser console as live code editor (usually as the default showing tab)
									  [Either use Visual Studio Code+browser console OR just Web Maker as live code editor](((629ccb27-2cb7-4ac2-bc16-90c66e156174)))
						- _Other windows_
						  collapsed:: true
							- Anki (for ingraining learning)
							  collapsed:: true
								- ~/Documents/MUSEUM/Programming/Anki1.ods
								- See for more info
									- See Anki SOP - for how to add learning notes into flashcards
									  #MetaLearning https://workflowy.com/#/be1d6e89506a
									- use split-screen for AnkiDroid + Markor when reviewing flash cards
									  https://imgur.com/a/FnsSRX4
									- [<--created Anki cards up to here-->](((629ccb26-84b2-46d2-944d-7044c3629f37)))
							- GitKraken (for submitting daily work to GitHub for accountabiliy + psuedo-CV)
							- Either use ((63209272-1088-4824-a762-4ac7ded04b0a))+browser console OR just Web Maker as live code editor
							  id:: 629ccb27-2cb7-4ac2-bc16-90c66e156174
							  collapsed:: true
								- Browser console
									- Pros/Cons
										- Pros
											- More functionality than Web Maker
											- Paired with ((63209272-1088-4824-a762-4ac7ded04b0a)) has more functionality
										- Cons
											- Web Maker has a nicer UI
										- Unclear
									- Open console in a blank page or open a file to work on
										- Open `about:blank` then right-click > `Inspect` > Console tab
										- Edit a local file using File > Open File > select HTML file in a web browser
											- e.g. new tab for:
											  `file:///home/boss/Documents/Git/1MY%20REPOS/snippets/practical-javascript2/todoList.html`
									-
									- Reposition the docking under the vertical ellipsis button
									  source:: https://stackoverflow.com/questions/10023640/how-to-reposition-chrome-developer-tools
								- Web Maker
								  id:: 63470fd0-2c8b-4064-9388-fdd55a211d5c
						- {Archive}
						  collapsed:: true
							- v0.1 Vivaldi window layout
							  collapsed:: true
								- Tab stack with tab tiles:
									- Dynalist
									- Watch And Code
									- Web Maker (editing/testing code)
					- _Modules_
						- _Copy of prior similar course modules_ - see [Watch and Code's Practical JavaScript](((629ccb27-6855-4209-8a01-0e0b2afd59e8)))
						- 1) Introduction
						  collapsed:: true
							- Meta on course
							  collapsed:: true
								- The course is really difficult and you will get stuck
								- Instead of going through every type of code possibility then giving an example for each, he shows the code first and then repeated exposure teaches you the type of code it is
								- Goal: code 1-3 hours every day. Most important is consistency, not time
									- "I stop every day right at the point where I feel like I can write more. Do that, and the next day's work goes surprisingly smoothly."
							- Watch and Code vs Bootcamps
							  collapsed:: true
							  id:: 629ccb27-cec5-43e5-b1fe-b703520c919a
								- Bootcamps
									- Philosophy - teach you Breadth: popular tools, frameworks, the motions of programming
									- Goal - get first job ASAP
									- Work experience - student projects
									- Inteview prep - 1-2 weeks (low)
								- Watch and Code
									- Philosophy - teach you Depth: logic, communication, good programming habits
									- Goal - long-term career growth
									- Work experience - contributing to open-source projects. Holds more weight than showing off a small app you made
									- Inteview prep - high (instructor-led practice groups)
							- _Language considerations_
							  collapsed:: true
								- Good languages for learning are:
									- Easy to read (makes learning efficient) - Python is A, JavaScript is B
									- Compact syntax (maintains simplicity by reducing choices/methods) - Lisp is A, JavaScript is D
									- Easy setup - JavaScript is quick since it's browser-based. A+
									- Clearly useful e.g. widely adopted - JavaScript A+
							- _Get ready_
							  collapsed:: true
								- In Visual Studio Code go to Settings > Workspace settings > Tab size: 2 (2 is what JavaScript typically uses by convention)
								  id:: 629ccb27-c9e2-4419-9e39-4b026e14abd4
								  https://i.imgur.com/zKmeHKn.png
								- _HTML_
									- At the top of HTML files write `<!DOCTYPE html>` to define more clearly what the filetype is
									- Typical HTML template has
									  collapsed:: true
										- Template
										  ```html
										  <!DOCTYPE html>
										  
										  <html>
										   <head></head>
										   <body>
										   <script>
										   </script>
										   </body>
										  </html>
										  ```
									- `<title>` can be put between the `<head>` tags and it allows renaming the webpage title
										- Q: Give an example of how you give a webpage a title via HTML, and what are the components used called
											- A:
												- `<title>Practical JavaScript</title>`
												- `<title>` is an opening tag, and `</title>` is a closing tag
									- Tags usually come in pairs with an opening and closing tag
								- Choose either console or Web Maker
								  [Either use Visual Studio Code+browser console OR just Web Maker as live code editor](((629ccb27-2cb7-4ac2-bc16-90c66e156174)))
							- _On todo lists_
								- Example of a good basic todo list
								  https://todomvc.com/examples/vanillajs
						- 2) Version 1 - getting started
						  collapsed:: true
							- Five requirements
								- 2.1) It should have a place to store todos
									- Todos are stored in a list AKA **array**
										- `['Item 1', 'Item 2', 'Item 3']`
									- Pressing the up arrow in the console will paste the last used command, similar to terminals
									- The array can be saved under a `var` named `todos` in order to save it in this console session
										- `var todos = ['Item 1', 'Item 2', 'Item 3']`
									- You enter a `;` at the end of certain lines such as this var. It’s mainly done for readability, and compatibility with tooling
									- Format: `declaration = assignment`
									  id:: 629ccb27-c2d9-413c-b1ee-58b23d5f7282
										- Declaring that a variable exists
										- Assigning a value to that variable
										- _Related:_
											- [Format](((629ccb27-fbf0-4d12-ba3c-c12949ec8b0b))) of functions
								- 2.2) It should have a way to display todos
									- Just adding `todos` as a line in the script won't print the var to the console
									- But if you add `console.log(todos);` to the script then it'll print it to the console when you open this HTML file
									- `console.log()` can be used to print many kinds of data to the console when added to a script
									- If already using the console and just trying to print the var to it, `console.log()` isn't needed and just `todos;` is fine
								- 2.3) It should have a way to add a todo
								  collapsed:: true
									- `push()` can be used to add data to the end of an array
										- Example
											- `todos.push('Item 4');` will add 'Item 4' as a 4th item at the end of the array
								- 2.4) It should have a way to edit a todo
								  collapsed:: true
									- First you need to select an item
										- `todos[0];` will select the first item in the array `Item 1`
										- `todos[1];` will select the second item in the array `Item 2`
										- `todos[4];` will select the fifth item in the array, which doesn't exist so it outputs `undefined`
										- Basically structure format is `var[position];`
									- Set the item as a new value
										- `todos[0] = 'Item 1 updated';`
										- Basic structure is `= new-value;`
								- 2.5) It should have a way to remove a todo
								  collapsed:: true
									- `splice()` can be used to remove items
										- Basic format is `var.splice(position, number of items to delete);`
										- `todos.splice(0, 1);`
							- When going through a quiz/problem ideally:
							  collapsed:: true
								- Example problem
								  source:: https://watchandcode.com/courses/programming-foundations/lectures/22887997
								  collapsed:: true
									- Example
									  ```
									  var array1 = ['yo', 'hi'];
									  array1[0] = array1[1];
									  
									  var array2 = ['bye', 'later'];
									  array2.splice(1, 1);
									  
									  var array3 = [];
									  array3[0] = array1[0];
									  array3[1] = array2[0];
									  ```
								- Paste it into a new file
								- Create code comments for what you predict to happen at each stage, as well as how certain you are that you're correct
									- e.g. `// array1 = ['yo', 'hi'] => ['hi', 'hi'] 99%`
								- Add `console.log();` after each stage to double-check the values are what you expect them to be
									- Example
									  ```
									  var array1 = ['yo', 'hi']; 
									  array1[0] = array1[1];
									  console.log(array1); // array1 = ['yo', 'hi'] => ['hi', 'hi'] 99%
									  
									  var array2 = ['bye', 'later'];
									  array2.splice(1, 1);
									  console.log(array2); // array2  => ['bye'] 99%
									  
									  var array3 = [];
									  array3[0] = array1[0];
									  console.log(array3); // array3 => ['hi'] 99%
									  array3[1] = array2[0];
									  console.log(array3); // array3 => ['hi', 'bye'] 99%
									  ```
							- Semicolons
							  collapsed:: true
								- Example
								  source:: https://watchandcode.com/courses/programming-foundations/lectures/23512381
									- Example1
									  ```
									  var todos = ['Item 1', 'Item 2', 'Item 3'];
									  
									  console.log(todos);
									  
									  todos.push('Item 4');
									  
									  todos[0] = 'Item 1 updated';
									  
									  todos.splice(0, 1);
									  ```
								- Rules
									- Every line of code ends with a semicolon
									- Every ) is followed immediately by a semicolon.
						- 3) Version 2 - Functions
						  collapsed:: true
							- 3a) Functions are a series of stored steps grouped under a single name, which is performed every time the function is called
							- Function template
								- `function functionName() {}`
								- Example
								  ```
								  function add() {
								   todos.push('another item');
								   console.log(todos);
								  }
								  ```
								- To run it you can use `functionName();` e.g. `add();` (parentheses required)
							- Format
							  id:: 629ccb27-fbf0-4d12-ba3c-c12949ec8b0b
							  ```
							  function demoFunction(myData) { // Declaration
							   console.log(myData);
							  }
							  
							  demoFunction('gordon'); // Assignment
							  ```
								- Parameter = what is between the parentheses `()` in the declaration i.e. `myData`
									- Very similar to variables from the variable format example
									  [Format: `declaration = assignment`](((629ccb27-c2d9-413c-b1ee-58b23d5f7282)))
								- Argument = what is between the parentheses `()` in the assignment i.e. `'gordon'`
									- Very similar to values from the variable format example
									  [Format: `declaration = assignment`](((629ccb27-c2d9-413c-b1ee-58b23d5f7282)))
							- 3b) When you run a function, you can provide the function with data (that goes between the parentheses.)
							  collapsed:: true
								- `demoFunction(myData);`
								- Known as a parameter within the function, and an argument when calling the function
							- _Note:_ do not need semicolons`;`after curly braces lines `{` and `}` in functions
							- Questions
							  collapsed:: true
								- In this example what is `0, 1` known as
								  ```
								   var todos = ['Item 1', 'Item 2', 'Item 3']; 
								  
								   console.log(todos); 
								  
								   todos.push('Item 4');
								  
								   todos[0] = 'Item 1 updated'; 
								  
								   todos.splice(0, 1)
								  ```
									- A: Two arguments
								- In this example what is `todos[0] = 'Item 1 updated';` known as
								  ```
								   var todos = ['Item 1', 'Item 2', 'Item 3']; 
								  
								   console.log(todos); 
								  
								   todos.push('Item 4');
								  
								   todos[0] = 'Item 1 updated'; 
								  
								   todos.splice(0, 1)
								  ```
									- A: Assignment
								- In this example name a declaration
								  ```
								   var todos = ['Item 1', 'Item 2', 'Item 3']; 
								  
								   console.log(todos); 
								  
								   todos.push('Item 4');
								  
								   todos[0] = 'Item 1 updated'; 
								  
								   todos.splice(0, 1)
								  ```
									- A: `var todos`
							- 3.2) It should have a function to add a todo
							  collapsed:: true
								- First given code
								  ```
								  function add() {
								   todos.push('another item');
								   console.log(todos);
								  }
								  ```
									- Modify the code so that `add('Watch the next video in Practical JavaScript');` will add `'Watch the next video in Practical JavaScript'` as another item
								- Solution
								  ```
								  var todos = ['Item 1', 'Item 2', 'Item 3']; 
								  
								  function add(text) {
								  console.log(text); //optional, allows checking that the function is working properly throughout
								   todos.push(text);
								   console.log(todos);
								  }
								  ```
							- 3.3) It should have a function to edit a todo
							  collapsed:: true
								- First given code
								  `todos[0] = 'Item 1 updated'`
									- It should take two arguments: position of item in the array to edit, and what value to set it to e.g. `edit (1, 'second item changed');`
								- Solution
								  ```
								  function edit(position, newValue) {
								   todos[position] = newValue;
								   console.log(todos);
								  }
								  ```
							- 3.4) It should have a function to remove a todo
							  collapsed:: true
								- First given code
								  ` todos.splice(0, 1);`
									- Want it to work so you can use `remove(0);` to remove the first item
								- Solution
								  ```
								  function remove(position) {
								   todos.splice(position, 1);
								  }
								  ```
						- 4) Computer's perspective
						  collapsed:: true
							- Debugger can help you understand what your program is doing
							- _How to use the debugger_
							  collapsed:: true
								- Open debugger (CTRL + SHIFT + i)
									- Go to Sources tab (next to Console) for the debugger
									- Press the vertical ellipsis (3 dots) in the top-right to show/hide the console drawer whilst on Sources, to show them simultaneously
									- Make sure it's also docked to bottom
								- _In the Page tab (left panel/the Navigator), select your HTML doc_
									- Clicking on the line number in the margin will set a Breakpoint there (the program will stop running at this line)
									- _Running the file again, with the breakpoint_
										- Either reload the page
										- OR use CTRL+O to open the file again (more clicks after that too)
							- Step over (next function call)
							  https://i.imgur.com/vTtKroY.png This button (next to resume play/pause script execution) in the dev tools
							  collapsed:: true
								- AKA step over to next line of code _that's about to run_
								- Note: it will ignore function declarations (eg `function remove(position)`) because they're not actually run. A function call would instead be something like `remove();`
							- To exit the debugger
							  collapsed:: true
								- Either
									- "Step over" over multiple lines (more time-consuming
									- OR click the resume script execution button in the dev tools (looks like a Play button with a l to the left of it)
										- Note: Sometimes it'll go to next breakpoint instead if you have more leftover breakpoints BUT this depends on the type of breakpoints leftover
										  19/07/21 - this seems false
											- It'll stop at `console.log(todos);`
											- It'll skip past `todos.push(text);`
										- It'll skip all break points
							- Sidenote: it can be good to create code comments with your (expectation) and (outcome) for different code, to see where your knowledge gap is
							  collapsed:: true
								- e.g.
									- // todos (expectation: undefined, 100% conf) (reality: )
										- I expect using `todos` before I define the var it will output `undefined`, and I have 100% confidence that'll happen
									- Can use a breakpoint to pause the code at a certain point, and then use console at that point to run commands and check the values
							- Checking variables in the debugger
							  collapsed:: true
								- Step over to a particular breakpoint
								- Type in the variable name in console, or mouseover the variable in the code itself (within the debugger)
							- Using the step-into (next function call) button
							  collapsed:: true
								- It'll take you into the body of the function that you're calling
								- If you're already in the body, then trying to step-into further will only work for non-native functions (i.e. user-made functions) (e.g. push and console.log are built-in)
									- 3 ways to tell if a function is native or not - all by using a blank tab (about:blank) with Console dev tool open, type in a function (e.g. `console.log` or `[].push`)
									  https://i.imgur.com/oohUJ4l.png
										- The function will run
										- Trying to use the function will say "native code"
										- It will say "not defined" if it's not native
							- Ways to stop the debugger inside of a function
							  collapsed:: true
								- Either
									- Set a breakpoint within the function, then use the console to run the function
									- Use the console to run the function, then run the whole program
							- Setting breakpoints without writing to a file
							  collapsed:: true
								- Either
									- Write the `debugger;` on a separate line, and it'll stop on the `debugger;` line
										- e.g. 
										  ```javascript
										  function hello(name) {
										    let phrase = `Hello, ${name}!`;
										  
										    debugger;  // <-- the debugger stops here
										  
										    say(phrase);
										  }
										  ```
											- [source] https://javascript.info/debugging-chrome#the-command-debugger
										- Such command works only when the development tools are open, otherwise the browser ignores it.
								- If after you call a function then it'll stop on that function line 1
								- Step into will skip lines with native functions, but it'll go to the next line for custom functions
						- 5) Functions and variables
						  collapsed:: true
							- Scope
							  AKA variable visibility
							  collapsed:: true
								- Variables within functions are only accessible within the function itself. Outside the function, the variable isn't accessible
									- Example
									  ```
									  function sayName() {
									   var secret = 'watchandcode';
									  }
									  
									  console.log(secret); 
									  ```
									  console.log = secret is undefined
									- Visual example - circle all functions. Then draw arrows from whenever you call a variable to that variable itself. You can draw arrows going out of circles, but never going into them
									  https://i.imgur.com/ozvp1Sq.png
								- Other functions on the same level can't access each other's parameters
									- Example - `a` cannot access `bParam`
									  ```
									  function a() {
									    var aVar = 'a';
									  }
									  
									  function b(bParam) {
									    console.log(bParam);
									  }
									  ```
										- You can test this with something like `console.log(bParam);` within the `a` function
									- Example 2 - trying to call the function via `b();` will return `undefined`
									  ```
									  function a(aLog) {
									   var aStore = aLog;
									  }
									  
									  function b() {
									   console.log(aLog);
									  }
									  ```
						- 6) Version 3 - Objects
						  collapsed:: true
							- Booleans: true or false value for a variable
								- eg `var completed = true;`
							- Text (AKA string) is another data type that variables can be
							- Arrays within arrays
								- Allows you to have a single item with multiple arrays linked together (like a database)
								- Example
								  `var todos = [['Get groceries', true], ['Go for a run', false]];`
									- Calling this var
										- `todos[0]` would give you `['Get groceries', true]`
										- `todos[0][0]` would give you `'Get groceries'` (because you're calling the item within 2 layers of arrays
										- `todos[1]` would give you `['Go for a run', false]`
							- Objects
								- Objects use `{}` within a var
								- Example
								  ```
								  var gordon = {
								   name: 'Gordon',
								   location: 'San Francisco',
								   favoriteDessert: 'ice cream'
								  }
								  ```
									- name, location and favouriteDessert on the left are properties, each with values on the right
									- Calling the object
										- `gordon` would show the whole object with all properties and values
										- `gordon.favouriteDessert` would show only the value for the property favouriteDessert
								- How to use objects in arrays instead of arrays inside of arrays
									- Basic structure of an object within a variable is `[{}, {}];` or `[{something1: true, something2: 'hi'}, {}];`
									- Example
									  ```
									  var todos = [
									   {todoText: 'Get groceries', completed: true}, 
									   {todoText: 'Go for a run', completed: false}
									  ];
									  ```
									- Calling the object
										- `todos[0].todoText` would show `'Get groceries'`
										- `todos[1].completed` would show `false`
										- First half is the same as for an array `[todos[1]`, the `.completed` is added to access a particular property because it's an object. Arrays within arrays would instead use `todos[1][1]`
									- Pros/Cons of using objects rather than arrays
										- Pros
											- By naming the property it's more obvious what we're storing
											- Calling objects less likely to lead to errors because it's easier to see what data type it'll output (e.g. string, boolean etc)
										- Note: you can't call objects in arrays via something like `todos[0].[1]`, which would have otherwise allowed two methods of calling values within objects in arrays
							- ((63209272-1088-4824-a762-4ac7ded04b0a)) shortcut: `CTRL + /` will comment in/out multiple lines of code
							- Requirements tasks
								- 6.9) We should initialise the todos variable with objects
									- Example
									  ```
									  var todos = [
									   {todoText: 'Item 1', completed: false},
									    {todoText: 'Item 2', completed: false},
									    {todoText: 'Item 3', completed: false}
									   ];
									  ```
										- Each `{}` is an object, with two properties: `todoText` and `completed`
								- 6.11) The add function should add objects
									- Example
									  ```
									  function add(initialText) { 
									   todos.push({todoText: initialText, completed: false});
									   console.log(todos);
									   }
									  ```
								- 6.12) The edit function should edit objects
									- Example
									  ```
									  function edit(position, newTodoText) {
									   todos[position].todoText = newTodoText;
									   console.log(todos);
									   }
									  ```
							- Quiz
								- Example
								  ```
								  var myArray = [{name: 'Gordon'}];
								  
								  function exampleFunction(thing) {
								    thing.name = 'changed by exampleFunction';
								    
								    thing.thing = {name: 'new thing'};
								  }
								  
								  exampleFunction(myArray[0]);
								  exampleFunction(myArray[0].thing);
								  ```
									- Answers
										- At some point, `myArray[0].thing.name` will be equal to 'new thing'.
										- After the code runs, `myArray[0].thing.thing.name` will be equal to 'new thing'.
									- Learned
										- You can create a property which doesn't already exist for an object i.e. `myArray.myArray = {name: 'new thing'}`
										- You can create nested objects (objects within objects) i.e. makes it into `var myArray = [{name: 'Gordon', myArray: {name: 'new thing'}}];`
										- Length will always been 1 for an array with 1 top-level object in it, even if it has nested objects inside
										- Use the debugger with step-over and step-in function in order to check the value of `myArray[0].thing.name` at various points
										- Hovering over variables in the debugger will show you their current value (especially useful when using breakpoints/stepping over)
						- 7) Version 4 - Toggling
						  collapsed:: true
							- If statements
								- Basic syntax is `if () { }`
								- `if (myBoolean)` is the same as `if (myBoolean === true)`
							- It should have a function to toggle a todo
								- Example
								  ```
								  function toggle(position) {
								   if (todos[position].completed === true) {
								   todos[position].completed = false
								   }
								   else {
								   todos[position].completed = true
								   }
								   console.log(todos);
								   }
								  ```
							- When reading some code to work out what runs and what doesn't, use code comments at least. Consider highlighting where important changes happen, and bolding which lines of code actually run and ignoring that which doesn't
							  https://i.imgur.com/qEeI0LC.png
						- 8) Data types
						  collapsed:: true
						  id:: 63baa387-dafd-46a6-a6a3-6f92662d10f0
							- JavaScript data types
							  id:: 63f33e7a-7bf6-4c9d-8290-a4b8cc7f5cbd
								- Objects (can be as complex as you want)
									- `Usually {} // todoList, arrays, functions`
								- Primitives (building blocks)
									- `String // 'Look at this string!`
									- `Number // 1, 2, 3, 4...`
									- `Boolean // true, false`
									- `Undefined // value that hasn't been set`
									- `Null // 'Nothing'`
							- Comparisons with primitives
							  collapsed:: true
								- _String comparison_
									- `'gordon1' === 'gordon'` will output false
							- Comparisons with objects
							  collapsed:: true
								- `[1, 2, 3] === [1, 2, 3]` equals `false`, and `{} === {}` equals `false`  because you have to explicitly refer to the same object, not just a separate object that has the same value. JavaScript saves the objects at different memory addresses (e.g. memory address 1)
								- You can workaround this behaviour by using variables e.g. `var array1 = [1, 2, 3];` then `array1 === array1`
							- Primitives comparison uses values, whereas object comparison uses references
							- Code examples
							  collapsed:: true
								- Objects are saved as a memory address first, then any properties or items are attached to it. Primitives on the other hand are just saved as a value
								- A lot of programming knowledge is based on learning how a computer thinks, and making you think like one
								- Example 4
								  ```
								  var myHouse1 = {color: 'blue'};
								  var myHouse2 = myHouse1;
								  myHouse2.color = 'red';
								  ```
									- `myHouse1.color` and `myHouse2.color` both are `'red'` because objects are stored as references to a particular memory address, not a value. So they both refer to the same object because of the `var myHouse2 = myHouse1;` line
							- Related: ((afddb9fb-9d0f-456f-b505-32fee333e255))
						- 9) Version 5 - Displaying data better
						  collapsed:: true
							- For loops
							  collapsed:: true
								- Format
								  ```
								  for (initialisation; condition; final-expression) {
								   code;
								  }
								  ```
									- Example
									  ```
									  for (var i = 0; i < 3; i++) {
									   console.log('hey');
									  }
									  ```
							- Looping over arrays
							  collapsed:: true
								- Example1 - using `i <  3` ensures it won't print the `[3]` item
								  ```
								  var array1 = ['a', 'b', 'c', 'd'];
								  
								  for (var i = 0; i < 3; i++) {
								   console.log(array1[i]);
								  }
								  ```
									- Output
									  ```
									  a
									  b
									  c
									  ```
								- Example2 - using the length function for an array allows dynamically printing any amount of items in an array
								  ```
								  var array1 = ['a', 'b', 'c', 'd'];
								  
								  for (var i = 0; i < array1.length; i++) {
								   console.log(array1[i]);
								  }
								  ```
									- Output
									  ```
									  a
									  b
									  c
									  d
									  ```
								- 6) Example - looping the `todos` array in order to show items on separate lines, instead of the object in it's totality
								  ```
								  function displayTodos() {
								    for (var i = 0; i < todos.length; i++) {
								      console.log(todos[i]);
								    }
								  }
								  ```
								- Using the debugger to set a breakpoint on the for loop, then stepping over it useful for debugging the loop at various stages of the loop
						- **<--Anki cards imported up to here-->**
						- **<--need to rewrite flashcards in Course 4 which have anonymous functions as methods. Default should be named methods-->**
						- 10) Version 6 - Toggle All
						  collapsed:: true
							- toggleAll() example
							  ```
							  function toggleAll() {
							    var completedTodos = 0; // storing completed todos as an easy way to evaluate whether everything is true
							  
							    for (var i = 0; i < todos.length; i++) {
							      if (todos[i].completed === true) {
							        completedTodos++;
							      }
							    }
							   // if (everything is true)
							    if (completedTodos === todos.length) {
							   // then change everything to false 
							      for (var i = 0; i < todos.length; i++) {
							        todos[i].completed = false;
							        console.log(todos[i]);
							      }
							   // if otherwise
							    } else {
							   // then change everything to true
							      for (var i = 0; i < todos.length; i++) {
							        todos[i].completed = true;
							        console.log(todos[i]);
							      }
							    }
							      displayTodos();
							  }
							   ```
							- weirdToggleAll() also works the same
							  ```javascript
							  function weirdToggleAll() {
							    var completedTodos = 0;
							    var allCompleted = true;
							  
							    for (var i = 0; i < todos.length; i++) {
							      if (todos[i].completed !== false) {
							        completedTodos++;
							      }
							  
							      if (completedTodos !== i + 1) {
							        allCompleted = false;
							      }
							    }
							  
							    if (allCompleted === true) {
							      for (var i = 0; i < todos.length; i++) {
							        todos[i].completed = false;
							      }
							    } else {
							      for (var i = 0; i < todos.length; i++) {
							        todos[i].completed = true;  
							      }
							    }
							  
							    displayTodos();
							  }
							  ```
						- 11) Version 7 - Buttons
						  collapsed:: true
							- Good resource for looking up HTML elements
							  https://developer.mozilla.org/en-US/docs/Web/HTML/Element
							- `<button>` HTML element can be used to create a clickable button
								- Example
							- `<button>` is placed between the `<body>` tags, but not within `<script>`
							- Sidenote about methods:
								- Inside of a property of an object, a function can be added. This makes it no longer a `property`, but instead a `method`
									- Example
									  ```
									  sayBlame: function hello() {
									   console.log('sayBlame');
									  }
									  ```
									- `log` from `console.log` is a property/method of `console`
							- `<button id='SOMETHING'>` can be used to give a button a unique id
								- e.g. `<button id='display-todos-button'>`
							- To reference that button, we can use `document.getElementById('SOMETHING');`
								- e.g. `document.getElementById('display-todos-button');`
							- `.addEventListener()` is a native method
							  id:: 632092fe-45c6-48af-965e-ca89cd23b482
								- `.addEventListener(TYPE, LISTENER, ?OPTIONS);` has 3 parameters
									- TYPE e.g. 'click'
									- LISTENER = what function e.g. displayTodos
									- ?OPTIONS - optional
								- This example works like: whenever there's a click on displayTodosButton, then trigger displayTodos function:
								  ```html
								  <body>
								    <button id='display-todos-button'>Display todos</button>
								    <script>
								      var displayTodosButton = document.getElementById('display-todos-button');
								      displayTodosButton.addEventListener('click', displayTodos);
								    </script>
								  </body>
								  ```
								- Example2: it should have a toggleAll button
								  ```html
								  <body>
								    <button id='toggle-all-button'>Toggle all</button>
								    <script>
								      var toggleAllButton = document.getElementById('toggle-all-button');
								      toggleAllButton.addEventListener('click', toggleAll);
								    </script>
								  </body>
								  ```
								- Related: ((633bf5fd-e89b-4b5a-b92d-16210350ae21))
						- 12) More functions
						  collapsed:: true
							- Creating a var that is an existing object will also point to that object
							  collapsed:: true
								- The output of this is `demoFunction() {}`
								  ```
								  function demoFunction() {}
								  
								  var experiment1 = demoFunction;
								  ```
									- Can also do `experiment1 === demoFunction` and get back `true`
							- Creating a var that is calling an existing object will return `undefined` if the object is empty, or it'll return whatever the output is
							  collapsed:: true
								- The output of this is `undefined`
								  ```
								  function demoFunction() {}
								  
								  var experiment2 = demoFunction();
								  ```
								- The output of this is `'a string'`
								  ```
								  function demoFunctionThatReturnsAString() {
								   return 'a string';
								  }
								  
								  var experiment4 = demoFunctionThatReturnsAString();
								  ```
									- Why
										- `return` inserts a value (in this case 'a string') where the function (demoFunctionThatReturnsAString) was called
							- Returning undefined
							  collapsed:: true
								- The output of this is the function itself i.e. `function demoFunctionThatReturnsUndefined() { return undefined;}`
								  ```
								  function demoFunctionThatReturnsUndefined() {
								   return undefined;
								  }
								  
								  var experiment5 = demoFunctionThatReturnsUndefined;
								  ```
								- The output of this is `undefined`
								  ```
								  function demoFunctionThatReturnsUndefined() {
								   return undefined;
								  }
								  
								  var experiment6 = demoFunctionThatReturnsUndefined();
								  ```
									- `experiment6 === undefined`
							- Functions will always return `undefined` if they're executed, unless they're not empty and have some other value they return
							- `debugger;` can act like a breakpoint when used in the console
							  collapsed:: true
								- e.g. add it at the top of some code submitted to the console
								  ```
								  debugger; 
								  
								  function demoFunctionThatReturnsUndefined() {
								   return undefined;
								  }
								  ```
									- It'll pause at that first line
							- This example will return the entire function, not print whatever is inside the function
							  collapsed:: true
								- AKA `console.log(function);`  will return the entire function, not run the function and print whatever the function would do
									- e.g. this will return `function demoFunctionThatReturnsAString() { return 'a string'; }`
									  ```
									  function demoFunctionThatReturnsAString() {
									   return 'a string';
									  }
									  
									  function logThis(thing) {
									   console.log(thing);
									  }
									  
									  logThis(demoFunctionThatReturnsAString);
									  ```
							- Example 2
							  collapsed:: true
								- AKA `console.log(runFunction());` will run the function, and print whatever the function would (rather than simply logging the whole function itself)
								- This will return `'a string'` since it actually runs the function (it uses `logThis(demoFunctionThatReturnsAString());` instead of ``logThis(demoFunctionThatReturnsAString);`
								  ```
								  function demoFunctionThatReturnsAString() {
								   return 'a string';
								  }
								  
								  function logThis(thing) {
								   console.log(thing);
								  }
								  
								  logThis(demoFunctionThatReturnsAString());
								  ```
							- _Key points_
								- `return` inserts a value where the function was called
								- Not using `return` is the same thing as having `return undefined`
							- Experiment
							  collapsed:: true
								- Example
								  ```
								  function function1(inputFunction, inputString) { 
								   return inputFunction(inputString);
								  }
								  
								  function function2(thing) {
								   return thing;
								  }
								  
								  var experiment = function1(function2, 'yolo');
								  ```
									- Show my working for trying to calculate what `experiment` is equal to e.g. use `backquotes` to swap out parameters, or use code comments, or use `=something` e.g. inputFunction`=function2`,
								- These are all true
									- experiment will be equal to 'yolo'
									- When function1 runs, inputFunction will be equal to function2
									- When function1 runs, inputString will be equal to 'yolo'
									- When function2 runs, thing will be equal to 'yolo'
									- function2 will run once
						- 13) Version 8 - Getting data from inputs
						  collapsed:: true
							- 13.4) There should be a working button for adding a todo.
							  collapsed:: true
								- HTML elements
								  ```
								   <button id='add-button'>Add</button>
								   <input id='add-input'>
								  ```
								- Code for the buttons to run
								  ```
								   // 13.4) There should be a working button for adding a todo.
								   var addButton = document.getElementById('add-button');
								   var addInput = document.getElementById('add-input');
								   addButton.addEventListener('click', add);
								  ```
								- Function
									- Old
									  ```
									   function add(initialText) { 
									   todos.push({todoText: initialText, completed: false});
									   displayTodos();
									   }
									  ```
									- New
									  ```
									   function add() { 
									   var initialText = addInput.value;
									   todos.push({todoText: initialText, completed: false});
									   displayTodos();
									   }
									  ```
									- Also: this additional last line of this function now clears the textbox after the todo is added
									  ```
									   function add() { 
									   var initialText = addInput.value;
									   todos.push({todoText: initialText, completed: false});
									   displayTodos();
									   addInput.value = '';
									   }
									  ```
							- 13.5) There should be a working button for editing a todo.
							  collapsed:: true
								- HTML elements
								  ```
								   <button id='edit-button'>Edit</button>
								   <input id='edit-position-input'>
								   <input id='edit-text-input'>
								  ```
								- Event listeners (needed for buttons to run functions)
								  ```
								  // 13.5) There should be a working button for editing a todo.
								   var editButton = document.getElementById('edit-button');
								   var editPositionInput = document.getElementById('edit-position-input');
								   var editTextInput = document.getElementById('edit-text-input');
								   editButton.addEventListener('click', edit);
								  ```
								- Function
									- Old
									  ```
									  function edit(position, newTodoText) {
									    todos[position.todoText = newTodoText);
									    displayTodos();
									  }
									  ```
									- New
									  ```
									   // 6.12) The edit function should edit objects
									   function edit() {
									   var position = editPositionInput.value;
									   var newTodoText = editTextInput.value;
									   todos[position].todoText = newTodoText;
									   displayTodos();
									   editPositionInput.value = '';
									   editTextInput.value = '';
									   }
									  ```
										- `value` property of these input boxes
										- Last two lines clear the input boxes after the todo is added
							- 13.6) There should be a working button for removing a todo.
							  collapsed:: true
								- HTML elements
								  ```
								   <button id='remove-button'>Remove</button>
								   <input id='remove-input'>
								  ```
								- Event listeners (needed for buttons to run functions)
								  ```
								   var removeButton = document.getElementById('remove-button');
								   var removeInput = document.getElementById('remove-input');
								   removeButton.addEventListener('click', remove);
								  ```
								- Function
									- Old
									  ```
									   function remove(position) {
									     todos.splice(position, 1);
									     displayTodos();
									   }
									  ```
									- New
									  ```
									  function remove() {
									    var position = removeInput.value;
									    todos.splice(position, 1);
									    displayTodos();
									    removeInput.value = '';
									  }
									  ```
							- 13.7) There should be a working button for toggling a todo.
							  collapsed:: true
								- HTML elements
								  ```
								   <button id='toggle-button'>Toggle</button>
								   <input id='toggle-input'>
								  ```
								- Event listeners (needed for buttons to run functions)
								  ```
								   // 13.7) There should be a working button for toggling a todo.
								   var toggleButton = document.getElementById('toggle button');
								   var toggleInput = document.getElementById('toggle-input');
								   toggleButton.addEventListener('click', toggle);
								  ```
								- Function
									- Old
									  ```
									   function toggle(position) {
									   if (todos[position].completed === true) {
									   todos[position].completed = false;
									   } else {
									   todos[position].completed = true;
									   }
									   displayTodos();
									   }
									  ```
									- New
									  ```
									   function toggle() {
									   var position = toggleInput.value;
									   if (todos[position].completed === true) {
									   todos[position].completed = false;
									   } else {
									   todos[position].completed = true;
									   }
									   displayTodos();
									   toggleInput.value = '';
									   }
									  ```
							- Elements are objects not primitives, because they have properties e.g. `.value` is used to access input boxes frequently
							- Setting a variable to be equal to a property will be either a reference or a primitive depending on if the property is an object or primitive e.g. `var input1Value = input1.value;`
							- `.value` initial value is `''` i.e. empty string
							- Example
							  ```
							  <html>
							    <head>
							      <title>Example</title>
							    </head>
							    <body>
							      <input id='input-1'>
							      <script>
							        var input1 = document.getElementById('input-1');
							        var input1Value = input1.value;
							        input1Value = 'changed';
							  
							        var input2 = input1;
							        input2.value = 'input 2';
							  
							        input1.value = '';
							        input2.value = '';
							      </script>
							    </body>
							  </html>
							  ```
								- For both `input1.value` and `input2.value`, it's value starts as `''`, then becomes `'input 2'`, then becomes `''`
						- 14) Version 9 - Escape from the console
						  collapsed:: true
							- Creating a bullet point list out of todos
								- `<ul>` is the element for an unordered list
								- `<li>` is a list item
								- Example structure
								  ```
								  <ul>
								    <li></li>
								  </ul>
								  ```
								- Needed methods
								  collapsed:: true
									- createElement method
										- Syntax
											- `var element = document.createElement(tagName, options);`
											- e.g. `var element = document.createElement('li');`
										- Used for creating a specific type of element
											- `document.createElement()` can be used for creating HTML elements e.g. creating `<li>` list items
									- appendChild method - can be used for example to add <li> below a <ul> (bullet points for an unordered list)
										- Syntax
											- `element.appendChild(aChild)`
											- e.g.
									- innerHTML method - can be used to set or get HTML
										- Syntax
											- `element.innerHTML = ;`
											- `var something = element.innerHTML;`
									- innerText method - similar to innerHTML, except only changes string instead of HTML
								- New version
									- New HTML element
									  ```html
									  <body>
									    <ul id='todos-ul'></ul> // new
									    <script>
									      function displayTodos() {}
									    </script>
									  </body>
									  ```
									- function displayTodos()
										- Old
										  ```javascript
										  function displayTodos() {
										    for (var i = 0; i < todos.length; i++) {
										      console.log(todos[i]);
										    }
										  }
										  ```
										- New
										  ```javascript
										  function displayTodos() {
										    var todosUl = document.getElementById('todos-ul'); //select the <ul> element by it's ID
										  
										    todos.Ul.innerHTML = ''; //clears any existing <li> elements inside of todosUl by setting it as an empty string first. This way if you run the function twice in a row, it'll clear the previous <li> elements
										  
										    for (var i = 0; i < todos.length; i++) {
										      var todoLi = document.createElement('li'); // this var will create <li> element when used
										      todosUl.appendChild(todoLi); // create <li> as a child of todoListUl
										    }
										  }
										  ```
											- Requirement: There should be an li for each todo.
											- Note: This doesn't list the text for the todo, just a bullet point for each one
									- Bugs
										- If you use functions like `add()` it'll show extra bullet points on the page, rather than matching the number of items in `todos`
											- Fix: `todos.Ul.innerHTML = '';` clears any existing <li> elements inside of todosUl by setting it as an empty string
										- It doesn't display the `todoText` or `completed` property, just the unordered bullets
											- New code:
											  ```
											  if (todos[i].completed === true) {
											   todoLi.innerText = '[X] ' + todos[i].todoText;
											   } else {
											   todoLi.innerText = '[ ] ' + todos[i].todoText;
											   }
											  ```
						- **<--submitted to GitHub snippets repo up to here-->**
						- [**<--created Anki cards up to here-->**](((629e07ee-075d-4a72-9bd0-fd63cd35f152)))
						  id:: 629ccb26-84b2-46d2-944d-7044c3629f37
						- 15) Version 10 - Click to delete
						  collapsed:: true
							- 15.2) Each todo should have it's own remove button.
							  collapsed:: true
								- This create a remove button for each <li> but the button doesn't do anything
								  ```javascript
								  // 15.2) Each todo should have it's own remove button.
								   var removeButton = document.createElement('button'); // this var will create <button> element when used
								   removeButton.innerText = 'Remove'; // label
								  
								  todoLi.appendChild(removeButton); // have the button appear in each <li>
								  ```
							- 15.4) The remove buttons should actually work.
							  collapsed:: true
								- In the debugger can place a breakpoint in the middle of the `remove()` function, then click different 'remove' buttons and see what event is also sent (local section of the tab)
									- Hovering over `toElement` says `button` each time, but hovering over 'button' will highlight the appropriate button on the screen
									- Likewise so does `target`, `currentTarget`, `srcElement` properties
								- `event` refers to the event itself i.e. mouse click (pointer action) on a 'remove' button
									- We can then access properties that are sent with this event, such as where the mouse was on the screen, screen size, button info etc
									- `target` one such property of the `event`, which tells you which particular button was pressed
									- Can also access the`id` property of the target (`event.target.id`) button, and it's the same as `id` part of HTML elements
								- `function remove()`
									- Old
									  ```javascript
									  function remove() {
									    var position = removeInput.value;
									    todos.splice(position, 1);
									    displayTodos();
									    removeInput.value = '';
									  }
									  ```
						- 16) Version 11 - Click to toggle
						- 17) Version 12 - Click to edit
					- Premium
						- It's probably worth it because of the structured progress will more likely guarantee I actually get good
					- Assorted
						- JavaScript has three ways to declare a variable: var, let, const.
						- https://medium.com/@gordon_zhu/how-to-be-great-at-asking-questions-e37be04d0603
				- DONE [Founders and Coders](((629ccb26-c33a-4e26-8262-1fe1d869027a))) pre-requisites (AKA freeCodeCamp and CodeWars)
				  :LOGBOOK:
				  CLOCK: [2022-10-18 Tue 09:15:16]--[2022-10-18 Tue 09:15:17] =>  00:00:01
				  :END:
				- [freeCodeCamp](((629ccb25-3ea5-4bc3-84fd-050077003522))) frontend course
				- ((62a0d2df-fa7f-40a6-81ef-928c8dd743d8))
				- [You Don't Know JavaScript series by Kyle Simpson](((629ccb26-ef1d-47b6-a890-d6be1548a7f5)))
				- [TeamTreehouse](((629ccb25-b2a8-4026-a415-7a478c4b5337)))
				- [Exercism track for JavaScript](https://exercism.org/tracks/javascript)
				  id:: 663a5793-1300-468a-8fe9-1e245d0b8e72
				  collapsed:: true
					- Related: ((6647026a-3097-449d-8f48-31066dd80b24))
				- [MDN Web Docs - JavaScript First Steps](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps)
				- ((663a5afd-0a96-46d9-9f30-0eb86584066a))
				- [Clientside.dev](https://www.clientside.dev)
				  collapsed:: true
					- Cons
						- First free easy exercise I've seen uses Classes not Hooks, so it's at least two years out of date
				- ((64024e3e-a577-4332-943b-5427a406cb7b))
			- [[Currently_studying]]
			- _Intermediate_
			  id:: 629d5445-b4d5-4e4a-86e1-539ebb4a897b
			  collapsed:: true
				- [Frontend Masters](https://frontendmasters.com)
				  id:: 640991f2-e312-4f6d-843f-f8b8789c5a98
				  collapsed:: true
					- [[Currently_studying]] : ((64099096-2639-4fff-9b71-b0619e5d4dc2))
					- Recommended
						- [Deep JavaScript Foundations | Frontend Masters | Frontend Masters](https://frontendmasters.com/courses/deep-javascript-v3/)
						- [Algorithms & Data Structures | Learn Algorithms with TypeScript for Interviews | Frontend Masters](https://frontendmasters.com/courses/algorithms/)
						- [JavaScript Learning Path - Write Professional, Modern JavaScript | Frontend Masters](https://frontendmasters.com/learn/javascript/)
				- Watch and Code premium course
				- ((637210b6-f566-4a57-94d5-4b2ecbda71e8))
				- https://github.com/jwasham/coding-interview-university
				- ((629ccb26-051d-46ed-910d-bd6d0e0af723))
				- _Frameworks_
					- https://www.hntrends.com - tells you what language/frameworks is popular
					- [React](((629ccb26-62cc-426a-9616-4d8969f32580)))
				- ((629ccb26-1eab-4686-a7b8-f9433a871440))
				- [freeCodeCamp](((629ccb25-3ea5-4bc3-84fd-050077003522))) backend course
				- [CSS3: The Missing Manual](((629ccb26-11e7-4183-bc26-3a72de4fcae6)))
				- Learn what is
					- ((635d53fe-64b5-4313-837f-092afae03ade))
				- **maybe** (review first)
					- Non-JS simpler alternatives
						- http://youmightnotneedjs.com
						- [HTMX](https://htmx.org/)
						  id:: 646349ad-e51d-4016-9eb9-45cd23e00e0b
						  collapsed:: true
							- [Htmx in a Nutshell | Hacker News](https://news.ycombinator.com/item?id=33987578)
							- https://nomadiq.hashnode.dev/reimagining-front-end-web-development-with-htmx-and-hyperscript
							- [Htmx Is the Future | Hacker News](https://news.ycombinator.com/item?id=35829733)
							- https://news.ycombinator.com/item?id=33218439
							- https://news.ycombinator.com/item?id=38906989
								- [GitHub - lassebomh/htmx-playground: A simple code sandbox for playing around with HTMX. No setup needed!](https://github.com/lassebomh/htmx-playground)
								-
							-
						- ((63471096-6708-422f-8f02-088fc7da91a1))
					- ((629ccb26-6ecf-41ff-b479-f404b7eddbe0)) once I reach like 3 kyu in CodeWars
			- *Advanced*
				- ((65500703-75a9-4a9c-8cd6-08519600f536))
					- {{embed ((655007c9-5a7b-4d3b-897e-d24db018a0b7))}}
- # Ecosystem
	- Languages which compile to JS
		- Most notable
			- [TypeScript](https://www.typescriptlang.org)
			  id:: 629ccb26-1eab-4686-a7b8-f9433a871440
			  collapsed:: true
				- Pros/Cons
				  collapsed:: true
					- Pros
						- [Static Typing vs Dynamic Typing](((629ccb26-636b-47cd-8953-017490c9cce9)))
						- JavaScript super-set
							- In short that means that all of your existing JS code is already a TS code. And that makes learning TypeScript a very easy task. Its learning curve is very simple, you start with renaming your .js files into .ts files and creating a very simple tsconfig.json file. Then you start learning and using new features one by one. A few months or even weeks later you will notice that you are pretty familiar with the most useful TypeScript features and the language has become your second nature.
						- Syntax sugar
							- I like sugar! And TS has plenty of it. Classes, interfaces, fat arrow functions, etc. The best part of TS syntax sugar is that there is no magic behind it and it feels as a very natural extension to JavaScript language. And I think this is one of the reasons why many of TS features are getting adopted in ECMA specifications in one way or another.
					- Cons
						- Made by Microsoft
						- Language configuration
							- I’m strongly against any language options which modify the way source code is interpreted. The amount of such options in TS is very small, most of configuration is about how to generate output, but Microsoft keeps adding language modifiers over time. I remember PHP and its bazillion options which can render your application unusable very easily and I don’t want to experience that with TypeScript. Well, at least tsconfig.json is a part of your project and not some global .ini file affecting all of the projects running on your machine.
						- No package manager
							- There is none. And everyone is using npm and JS libraries. I think TS would greatly benefit from having a separate package library which would be filled with code which uses all the benefits of the language.
					- https://medium.com/@auxx/typescript-pros-and-cons-873529634099
					- TS pros and cons: [Typescript vs Javascript - YouTube](https://www.youtube.com/watch?v=D6or2gdrHRE)
					- [What Is TypeScript? Pros and Cons of TypeScript vs. JavaScript](https://www.stxnext.com/blog/typescript-pros-cons-javascript/)
				- # Documentation
					- ## Cheatsheet
					  collapsed:: true
						- ((663a5793-9162-4de9-b20f-2a7549a57752))
					- ## My Notes
						- Array of a type
						  collapsed:: true
							- Array of `Blob`s
								- ```typescript
								  const [blobs, setBlobs] = useState<Blob[]>([]);
								  ```
						- Complex syntax examples and breakdown
						  collapsed:: true
							- collapsed:: true
							  ```typescript
							  const useClickLocalStorage = <T extends string = string>(
							    key: string,
							    fallbackValue: T,
							  ): [T, (value: T) => void] => {
							    const [value, setValue] = useState<T>(
							      () => (localStorage.getItem(key) as T) || fallbackValue,
							    );
							  };
							  ```
								- collapsed:: true
								  ```typescript
								  const useClickLocalStorage = <T extends string = string>(...)
								  ```
									- This defines a **generic function** with:
										- ### A generic type parameter:  `T`
											- You can supply the type when calling it, like:
											- ```typescript
											  useClickLocalStorage<"on" | "off">("key", "on");
											  ```
										- ### Constraint:  `T extends string`
											- `T` must be a **string** type.
											- It could be:
												- `string`
												- a string **literal** (`"dark"`, `"light"`)
												- a union (`"up" | "down"`)
												- etc.
										- ### Default value:  `= string`
											- If the caller does NOT specify `<T>`, then `T` becomes `string`.
								- Parameters
								  ```typescript
								  key: string,
								  fallbackValue: T,
								  ```
									- `key` is the localStorage key.
									- `fallbackValue` must be of type `T`.
									- Examples:
										- ```typescript
										  useClickLocalStorage("theme", "dark"); // T inferred as "dark"
										  useClickLocalStorage<string>("msg", "hello"); // T is string
										  ```
								- Return type
								  ```typescript
								  : [T, (value: T) => void]
								  ```
									- The hook returns a tuple:
										- The current value from localStorage → type `T`
										- A setter function that only accepts a value of type `T`
									- Just like a typed version of `useState`.
								- React state initialization
								  ```typescript
								  const [value, setValue] = useState<T>(
								    () => (localStorage.getItem(key) as T) || fallbackValue
								  );
								  ```
									- ### What this does:
									- `useState<T>` means the state must strictly be type `T`.
									- The initializer function runs once.
									- It tries to read from localStorage:
										- `localStorage.getItem(key)` returns `string | null`
									- Cast it to `T`:
										- `as T`
									- If it’s null → use the fallback: `|| fallbackValue`
								- Example of how TypeScript infers `T`
									- ### Example 1: T inferred from fallback value
										- ```typescript
										  const [theme, setTheme] = useClickLocalStorage("theme", "light");
										  ```
									- Here `fallbackValue` is `"light"`
									- → TypeScript infers: `T = "light"`
									- So TypeScript forces:
									- ```typescript
									  setTheme("dark");  // ❌ error, not allowed
									  setTheme("light"); // ✔ only exact string
									  ```
									- Example 2: union type
										- ```typescript
										  const [mode, setMode] = useClickLocalStorage<"dark" | "light">(
										    "mode",
										    "dark"
										  )
										  ```
										- Now only those two strings are allowed.
									- Example 3: default generic (`string`)
										- ```typescript
										  const [value, setValue] = useClickLocalStorage("msg", "hello");
										  ```
										- Since `"hello"` is assignable to string,
										- T becomes the default: `T = string`
							- collapsed:: true
							  ```typescript
							  export const useLocalStorage: typeof useClickLocalStorage = 
							    typeof localStorage !== "undefined"
							      ? useClientLocalStorage
							      : (key, fallbackValue) => [fallbackValue, () => {}];
							  ```
								- It sets its TypeScript type to the same type as another hook
								  ```typescript
								  : typeof useClickLocalStorage
								  ```
									- This tells TypeScript:
									- > “`useLocalStorage` has the same function signature as `useClickLocalStorage`.”
									- So the parameters and return type will match that hook exactly.
									- Example if `useClickLocalStorage` returns `[value, setter]`, this must too.
								- Runtime branching depending on environment
								  ```typescript
								  typeof localStorage !== "undefined"
								  ```
									- This checks whether the code is running in a browser.
										- In the **browser**, `localStorage` exists.
										- In **SSR (Next.js server, Node.js)** it does **not** exist.
									- This allows the hook to work in SSR without crashing.
								- If in browser → use the real implementation
								  ```typescript
								  ? useClientLocalStorage
								  ```
									- So the hook behaves normally when `localStorage` exists.
								- If NOT in browser → use a dummy fallback function
								  ```typescript
								  : (key, fallbackValue) => [fallbackValue, () => {}];
								  ```
									- This dummy version:
										- Simply returns the `fallbackValue`
										- And a **no-op setter** (`() => {}`)
										- Without touching `localStorage` (because it's not available)
									- This is required for SSR safety.
								- # Why this pattern exists
									- React hooks that use `localStorage` *will crash* in SSR because `localStorage` is undefined on the server.
									- This pattern ensures the hook:
										- is *typed correctly*
										- is *safe on the server*
										- still works fully on the client
									- It's a standard technique used in apps like **Next.js**, **Remix**, etc.
						- `get` and `set` keywords
						  collapsed:: true
							- `get` for getter methods
								- Can use with private properties to make them gettable
									- ```ts
									  #testStream: SpecSocket | undefined;
									  
									  get testStream() {
									    return this.#testStream;
									  }
									  ```
									- Related: ((692050d8-f707-494f-808e-e9f0f742e1ef))
								- See
									- ((69205071-d1f7-4494-85d3-b318223a73d5))
							- `set` for setter methods
								- id:: 69205071-d1f7-4494-85d3-b318223a73d5
								  ```ts
								  class Person {
								    private _age: number;
								    private _firstName: string;
								    private _lastName: string;
								  
								    constructor(age: number, firstName: string, lastName: string) {
								      this._age = age;
								      this._firstName = firstName;
								      this._lastName = lastName;
								    }
								  
								    public get age() {
								      return this._age;
								    }
								  
								    public set age(theAge: number) {
								      if (theAge <= 0 || theAge >= 200) {
								        throw new Error('The age is invalid');
								      }
								      this._age = theAge;
								    }
								  
								    public getFullName(): string {
								      return `${this._firstName} ${this._lastName}`;
								    }
								  }
								  ```
						- `#` should be used for private properties, not `_`
						  id:: 692050d8-f707-494f-808e-e9f0f742e1ef
						  collapsed:: true
							- AI answer
								- In TypeScript, using an underscore (`_`) prefix for private properties is a long-standing convention primarily used to indicate that a member is intended for internal use and should 
								  not be accessed externally.  This practice is especially common when defining backing fields for getter and setter methods to avoid naming conflicts, as the underscore helps distinguish the internal variable from the public accessor. However, this convention is not enforced by the JavaScript runtime; it is merely a signal to developers and is not a true privacy mechanism.
								- The `#` symbol, introduced in JavaScript (ES2022), provides true privacy through private class elements. When a class member is prefixed with `#`, it becomes a private element that cannot be accessed from outside the class, even via reflection or property enumeration.  This privacy is enforced at the language level, meaning it is respected during development, compilation, and at runtime.  For example, attempting to access a `#`-prefixed property from outside its class results in a syntax error.
								- While the underscore convention is still used, modern TypeScript versions (3.8+) support the `#` syntax for private fields, which is now considered a better practice because it offers genuine encapsulation. The `#` syntax is not just a naming convention but a language-level feature that prevents access entirely, unlike the `private` keyword in TypeScript, which is only enforced during type checking and is stripped away during transpilation to JavaScript.  Therefore, for true privacy, the `#` syntax is recommended over the underscore prefix.
						- `as` keyword
						  collapsed:: true
						  AKA type casting / type assertions
							- https://www.scaler.com/topics/typescript/typescript-as/
							- Double casting (`as unknown as TargetType`) vs `any`
								- ```typescript
								  variable1 as unknown as ReadableStream<Uint8Array>
								  ```
									- **`variable1 as unknown`**
										- This first converts `variable1` to `unknown`.
										- `unknown` is TypeScript’s “I don’t know what this is” type. It’s the safest top type (even safer than `any`) because you can’t directly access properties or call methods on it without further type checks.
										- Why do this? Because you might want to bypass TypeScript’s normal type checking rules temporarily.
									- **`as ReadableStream<Uint8Array>`**
										- Now, from `unknown`, you cast to the target type (`ReadableStream<Uint8Array>`).
										- TypeScript allows casting from `unknown` to any other type.
									- ### Why not just do a single cast?
										- You might try: `variable1 as ReadableStream<Uint8Array>`
											- This only works if TypeScript thinks the cast is safe or compatible.
											- If `variable1` is of an incompatible type (say, `string`), TypeScript will give an error.
											- By first casting to `unknown`, you essentially tell TypeScript:
											- > “I don’t care what this is, trust me, I know it should be a `ReadableStream<Uint8Array>`.”
										- Example that fails
											- ```ts
											  let variable1: string = "hello";
											  let stream = variable1 as ReadableStream<Uint8Array>; // ❌ TypeScript error
											  ```
										- Example that succeeds
											- ```ts
											  let stream = variable1 as unknown as ReadableStream<Uint8Array>; // ✅ Allowed
											  ```
										- `unknown` acts as a “type reset.” TypeScript no longer checks compatibility, but you acknowledge you’re taking responsibility for this cast.
									- Double casting only changes compile-time checking. It does not change the actual value at runtime.
										- ```ts
										  const x: string = "not a stream";
										  const stream = x as unknown as ReadableStream<Uint8Array>;
										  
										  stream.getReader(); // ❌ Runtime error: x does not have getReader()
										  ```
										- So, the double cast doesn’t magically convert a string into a stream
										- It bypasses TypeScript safety, which can lead to runtime crashes if you’re wrong.
									- ### When you might see this
										- Interoperating with external libraries that don’t have perfect type definitions.
										- Migrating JavaScript code to TypeScript.
										- For complex type conversions that TypeScript cannot verify.
									- ### Key takeaway:
										- The double cast is essentially a type safety escape hatch. The first `as unknown` wipes out TypeScript’s type checking, the second `as YourType` tells TypeScript what you want it to believe.
								- ### why the double cast (`as unknown as TargetType`) is **safer than just using `any`** — and where the pitfalls lie.
									- `any` disables **all type checking**. Once a variable is `any`, you can call any property or method on it, and TypeScript won’t complain — even if it will definitely fail at runtime.
										- Example:
										  ```ts
										  let x: any = 123;
										  x.toUpperCase(); // TypeScript is fine with this, but runtime crashes
										  ```
									- `unknown` is different. You **cannot directly use it** without asserting a type or checking it first:
										- ```ts
										  let x: unknown = 123;
										  x.toString(); // ✅ OK, toString exists on all objects
										  x.toUpperCase(); // ❌ Error: Object is of type 'unknown'
										  ```
									- By casting first to `unknown`, you make the conversion explicit and force yourself (or the code reviewer) to consciously cast to the target type.
							- #### Summary
								- **`any`** = completely disables TypeScript checks → easy to misuse → runtime crashes likely.
								- **`unknown`** = forces you to think about the type → safer, but needs a cast before using as another type.
								- **`as unknown as TargetType`** = explicit escape hatch → **bypasses compile-time checking**, but runtime must match your expectation.
						- Related: ((692082d7-cd69-4304-a56a-d946bf931563))
					- ## Completed learning resources (references)
						- ((63974fae-d542-47eb-bc56-902a34f2eecb))
						  collapsed:: true
							- ((63974fae-4583-480d-9c40-d4ed17c273ee))
								- {{embed ((63974fae-4583-480d-9c40-d4ed17c273ee))}}
					- ## Learning resource sorted by priority
					  id:: 63904f3c-2367-4a2e-9be3-c61d03ac828e
						- ((638d0620-69d8-4aa7-bb09-c754f8e967ac))
						- ((633de987-00dd-4d64-8595-a854c72647c2))
						- ((63fdd825-6038-4479-b887-214407b6f379))
						- [TypeHero](https://typehero.dev/)
						  collapsed:: true
							- [GitHub - typehero/typehero: Connect, collaborate, and grow with a community of TypeScript developers](https://github.com/typehero/typehero)
					- ## Assorted topics
					  collapsed:: true
						- Syntax
							- For example: `var x = "hello"` in TypeScript is the same as `var x : string = "hello"`
						- SOPs
						  collapsed:: true
							- Commands
								- `tsc -v`
								  AKA `tsc --version` | Print the current version of TypeScript
								- `tsc -w`
								  AKA `tsc --watch` | Watch input file
							- How to setup a TypeScript project
							  collapsed:: true
								- `npm install -g typescript`
								  id:: 646349ad-a758-4162-98a2-67e78cef36f4
									- This will install TypeScript compiler globally
								- `tsc --init`
									- This creates a tsconfig.json file, which is used to specify the compiler options for your project
								- Create your first TypeScript file e.g. `cat index.ts`
								- Compile your TypeScript code into JavaScript
									- e.g. `tsc index.ts` will generate a `index.js`
									- Or just `tsc` for all files?
							- Priority of TS features to utilise
							  collapsed:: true
								- ((63904f3c-71bc-480b-8f11-20935e46a3a8))
								- ((63904f3c-a301-4b67-ab59-38411595949c))
								- Add to parameters
							- Use `tsc --watch` in a side process to check if your types are passing
						- Features
							- Changelog
								- 5.2
								  collapsed:: true
									- `using`
										- [TypeScript 5.2's New Keyword: 'using' | Total TypeScript](https://www.totaltypescript.com/typescript-5-2-new-keyword-using)
										- [TypeScript 5.2's new keyword: 'Using' | Hacker News](https://news.ycombinator.com/item?id=36388894)
										-
								- [5.0](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/)
								  collapsed:: true
									- Here’s a quick list of what’s new in TypeScript 5.0!
										- [Decorators](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#decorators)
										- [`const` Type Parameters](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#const-type-parameters)
										- [Supporting Multiple Configuration Files in `extends`](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#supporting-multiple-configuration-files-in-extends)
										- [All `enum`s Are Union `enum`s](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#all-enums-are-union-enums)
										- [`--moduleResolution bundler`](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#moduleresolution-bundler)
										- [Resolution Customization Flags](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#resolution-customization-flags)
										- [`--verbatimModuleSyntax`](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#verbatimmodulesyntax)
										- [Support for `export type *`](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#support-for-export-type)
										- [`@satisfies` Support in JSDoc](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#satisfies-support-in-jsdoc)
										- [`@overload` Support in JSDoc](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#overload-support-in-jsdoc)
										- [Passing Emit-Specific Flags Under `--build`](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#passing-emit-specific-flags-under-build)
										- [Case-Insensitive Import Sorting in Editors](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#case-insensitive-import-sorting-in-editors)
										- [Exhaustive `switch`/`case` Completions](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#exhaustive-switch-case-completions)
										- [Speed, Memory, and Package Size Optimizations](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#speed-memory-and-package-size-optimizations)
										- [Breaking Changes and Deprecations](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#breaking-changes-and-deprecations)
										- [What’s Next?](https://devblogs.microsoft.com/typescript/announcing-typescript-5-0/#whats-next)
										- Optional chaining and nullish coalescing operators, two features that were introduced in [ECMAScript 2020.](https://262.ecma-international.org/11.0/)
							- It adds extra features not yet available in JavaScript
							  collapsed:: true
								- ((657a009b-e9e7-43e4-a2b4-1cb135d98e18))
								- TypeScript offers some features that aren't available in normal JavaScript (yet) e.g. enums, decorators, function overloading, tuples, access modifiers, read-only objects/members, parameter properties
								- Optional static typing
								- https://stackify.com/typescript-vs-javascript-migrate/
									- [Interfaces](https://www.typescriptlang.org/docs/handbook/interfaces.html)
									- [Generics](https://www.typescriptlang.org/docs/handbook/generics.html)
									- [Namespaces](https://www.typescriptlang.org/docs/handbook/namespaces.html)
									- [Null checking](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-0.html)
									- [Access Modifiers](https://www.typescriptlang.org/docs/handbook/classes.html)
							- *All features*
								- Interfaces + types (how to create a type)
								  id:: 63f33e7a-ca10-49fc-a66c-4ab2d887e4c5
								  collapsed:: true
									- Differences
									  id:: 63f60103-072b-4a66-a122-9bae1c823754
										- Interfaces only work with objects and functions whereas Types with all data types
										- Interfaces have additional properties, for example they can be appended to
										- Interfaces used to have better performance, but nowadays they're the same
										- Syntax differences
											-
									- Examples
										- `type QueueItem = () => Promise(void)`
									- [TypeScript: Should you use Types or Interfaces? - YouTube](https://www.youtube.com/watch?v=zM9UPcIyyhQ)
									  collapsed:: true
										- {{video https://www.youtube.com/watch?v=zM9UPcIyyhQ}}
											- {{youtube-timestamp 37}} Performance is the same. Interfaces can only be used for objects, functions, whereas Types can be used for everything
											- {{youtube-timestamp 108}} Interfaces can inherit from another interface unlike Types
											- {{youtube-timestamp 141}} Interfaces have a bunch of additional properties, e.g:
												- Declaration merging = two interfaces with the same name in the same scope will be merged
													- Example
													  ```typescript
													  interface Animal { 
													    name: string;
													  }
													  interface Animal { 
													    meow(): void;
													  }
													  const animal: Animal = { 
													    meow: () => {}, 
													    name: "cat",
													  }
													  ```
											- {{youtube-timestamp 205}} His current belief - use Types unless you need a specific feature of Interfaces
								- Type annotations
								  id:: 663a5793-9162-4de9-b20f-2a7549a57752
								  collapsed:: true
									- # Examples
										- Simple primitives
											- ```typescript
											  let age: number = 32; // number variable
											  let name: string = "John"; // string variable
											  let isUpdated: boolean = true; // Boolean variable
											  ```
										- ## Arrays
											- `any[]`
												- ```typescript
												  let mixedArray: any[] = [];
												  
												  // You can add elements of any type to this array
												  mixedArray.push(42);
												  mixedArray.push("banana");
												  mixedArray.push({ name: "John" });
												  mixedArray.push([1, 2, 3]);
												  ```
											- Array of a specific singular type
												- ```typescript
												  let numbers: number[] = [1, 2, 3, 4]; // number array
												  let numbers: Array<number> = [1, 2, 3, 4]; // number array, alternative syntax
												  let strings: string[] = ["apple", "banana", "cherry"]; // string array
												  ```
											- Mixed types i.e. union types
												- ```typescript
												  let mixed: (number | string)[] = [1, "two", 3, "four"];
												  ```
											- Multidimensional arrays
												- ```typescript
												  let matrix: number[][] = [
												      [1, 2, 3],
												      [4, 5, 6],
												  ];
												  ```
											- Array of objects or custom types or interface
												- ```typescript
												  interface Person {
												      name: string;
												      age: number;
												  }
												  
												  let people: Person[] = [
												      { name: "Alice", age: 30 },
												      { name: "Bob", age: 25 },
												  ];
												  ```
										- ```typescript
										  function doStuff(a: number, b: string): : number {}
										  ```
										- Type annotations for parameters
											- Basic parameters
												- `function ascending (a: number, b: number): number {`
											- React props? Unsure if I got this correct. Check next-ssg project with Stefan
											  collapsed:: true
												- `function ascending (a: number, b: number): number {`
												- Inline type annotations
													- ```tsx
													  const TextField = ({
													    label,
													    text,
													    onTextChange
													  }: {  label: string;  text: string;  onTextChange: (text: string) => void;}) => ...
													  ```
												- Alternatively use a type alias
													- ```tsx
													  type AscendingProps {
													    a: number;
													    b: number;
													  }
													  
													  function Ascending ({a, b}: AscendingProps): number {
													  ```
								- Generics
								  collapsed:: true
									- Examples
									  collapsed:: true
										- `const [selectedTags, setSelectedTags] = useState<Tag[ ]>([])`
						- TSX
						  id:: 6353bf0f-3b39-4ebf-8458-740378a0e562
						  collapsed:: true
							- Allows you to use TypeScript to work with React ((6353be22-20aa-447b-ba89-1b401ac74063))
							- [There are some limitations to using `.tsx` files instead of `.ts` files always](https://stackoverflow.com/a/54614279)
								- Type assertions with <> don't work as that is the marker for a jsx tag.
								- Generic arrow functions with no constraint are not parsed correctly
							- [Learning Resources]
								- https://blog.logrocket.com/how-use-typescript-react-tutorial-examples/
								- https://www.typescriptlang.org/docs/handbook/jsx.html
							- Related: ((6353be22-20aa-447b-ba89-1b401ac74063))
						- JavaScript interoperability
						  collapsed:: true
							- Since TypeScript is so closely related to JavaScript it has great interoperability capabilities, but some extra work is required to work with JavaScript libraries in TypeScript. TypeScript definitions are needed so that the TypeScript compiler understands that function calls like _.groupBy or angular.copy or $.fadeOut are not in fact illegal statements. The definitions for these functions are placed in .d.ts files.
							  http://www.typescriptlang.org/docs/handbook/namespaces.html
							- The simplest form a definition can take is to allow an identifier to be used in any way. For example, when using Lodash, a single line definition file declare var _ : any will allow you to call any function you want on _, but then of course you are also still able to make mistakes: _.foobar() would be a legal TypeScript call, but is of course an illegal call at run-time. If you want proper type support and code completion your definition file needs to to be more exact (see lodash definitions for an example).
							  https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/lodash
							- Npm modules that come pre-packaged with their own type definitions are automatically understood by the TypeScript compiler (see documentation).
							  https://www.typescriptlang.org/docs/handbook/typings-for-npm-packages.html
							- For pretty much any other semi-popular JavaScript library that does not include its own definitions somebody out there has already made type definitions available through another npm module. These modules are prefixed with "@types/" and come from a Github repository called DefinitelyTyped.
							  https://github.com/DefinitelyTyped/DefinitelyTyped#how-do-i-get-them
							- There is one caveat: the type definitions must match the version of the library you are using at run-time. If they do not, TypeScript might disallow you from calling a function or dereferencing a variable that exist or allow you to call a function or dereference a variable that does not exist, simply because the types do not match the run-time at compile-time. So make sure you load the right version of the type definitions for the right version of the library you are using.
							- To be honest, there is a slight hassle to this and it may be one of the reasons you do not choose TypeScript, but instead go for something like Babel that does not suffer from having to get type definitions at all. On the other hand, if you know what you are doing you can easily overcome any kind of issues caused by incorrect or missing definition files.
						- Converting from [[JavaScript]] to TypeScri[[]]
						  collapsed:: true
							- Any .js file can be renamed to a .ts and ran through the TypeScript compiler to get syntactically the same JavaScript code as an output (if it was syntactically correct in the first place). Even when the TypeScript compiler gets compilation errors it will still produce a .js file. It can even accept .js files as input with the --allowJs flag. This allows you to start with TypeScript right away. Unfortunately compilation errors are likely to occur in the beginning. One does need to remember that these are not show-stopping errors like you may be used to with other compilers.
							- The compilation errors one gets in the beginning when converting a JavaScript project to a TypeScript project are unavoidable by TypeScript's nature. TypeScript checks all code for validity and thus it needs to know about all functions and variables that are used. Thus type definitions need to be in place for all of them otherwise compilation errors are bound to occur. As mentioned in the chapter above, for pretty much any JavaScript framework there are .d.ts files that can easily be acquired with the installation of DefinitelyTyped packages. It might however be that you've used some obscure library for which no TypeScript definitions are available or that you've polyfilled some JavaScript primitives. In that case you must supply type definitions for these bits in order for the compilation errors to dissapear. Just create a .d.ts file and include it in the tsconfig.json's files array, so that it is always considered by the TypeScript compiler. In it declare those bits that TypeScript does not know about as type any. Once you've eliminated all errors you can gradually introduce typing to those parts according to your needs.
							  https://github.com/DefinitelyTyped/DefinitelyTyped#how-do-i-get-them
							- Some work on (re)configuring your build pipeline will also be needed to get TypeScript into the build pipeline. As mentioned in the chapter on compilation there are plenty of good resources out there and I encourage you to look for seed projects that use the combination of tools you want to be working with.
							- The biggest hurdle is the learning curve. I encourage you to play around with a small project at first. Look how it works, how it builds, which files it uses, how it is configured, how it functions in your IDE, how it is structured, which tools it uses, etc. Converting a large JavaScript codebase to TypeScript is doable when you know what you are doing. Read this blog for example on converting a 600k lines to typescript in 72 hours). Just make sure you have a good grasp of the language before you make the jump.
							  https://www.lucidchart.com/techblog/2017/11/16/converting-600k-lines-to-typescript-in-72-hours/
						- syntactic superset of JavaScript that [compiles](https://www.npmjs.com/package/typescript-compiler) to JavaScript (EcmaScript 3+). TypeScript offers type annotations which provide optional, static type checking at compile time. Since it is a superset of JavaScript, all JavaScript is syntactically valid TypeScript.
						  collapsed:: true
							- However, that does not mean all JavaScript can actually be processed by the TypeScript compiler:
							  ```javascript
							  let a = 'a';
							  a = 1; // throws: error TS2322: Type '1' is not assignable to type 'string'.
							  ```
						- [[Programming software setup]]
						- `tsconfig.json`
						- Imports and Exports
						  collapsed:: true
							- If importing just types from somewhere then you need to add `type` either to suffix `import` or within the curly brackets
								- ```typescript
								  import { Read } from './codec.js
								  import type { Consume } from './place.js'
								  import { Listen, type Touch, type Taste } from '@something/module-super'
								  ```
							- Exports
								- TypeScript node projects
									- Here's the corrected index.ts:
										- ```ts
										  export * from "./client.js";
										  export * from "./options/index.js";
										  ```
									- "./client.js" is correct - Even though the source file is client.ts, you should import with .js extension in TypeScript for Node.js projects
									- "./options" → "./options/index.js" - Since options is a directory, you need to explicitly reference the index file
						- How to do types for ((636b8509-62c3-4b08-ae56-fcc1e632600c))
						  id:: 412041b3-482c-4ccf-9ec5-c62c5dca2da8
						  collapsed:: true
							- `import { Beer } from "@/types/types";`
							-
							- `const [data, setData] = useState<Beer>()`
							- Or
							- `const [data, setData] = useState<Beer | null>()`
							- `const [url,setUrl] = useState<string>('https://api.punkapi.com/v2/beers?page=1&per_page=30')`
							-
							- ```tsx
							    const [data, setData] = useState<Beer>()
							  
							    or
							  
							    const [data, setData] = useState<Beer | null>()
							  ```
						- ((63fe5472-f72c-4a29-9067-7d7edc128d06)) features
						  id:: 68fcecf0-9d11-49c8-87a5-b44e13304cd3
							- Interfaces vs Classes
							  collapsed:: true
								- Other classes *implements* interfaces, types, classes. A class can implement multiple interfaces
									- ```typescript
									  interface Animal {
									  eat(): void;
									  }
									  
									  interface DogInterface {
									  bark(): void;
									  }
									  
									  class Dog implements Animal, DogInterface {
									  eat() {}
									  bark() {}
									  }
									  ```
								- Other classes `extends` classes. A class can only extend one other class
									- ```typescript
									  class Animal {
									  eat() {}
									  }
									  
									  class Dog extends Animal {
									  bark() {}
									  }
									  ```
							- Abstract classes vs Interfaces
							  collapsed:: true
								- Interfaces don't have implementation details at all, whereas abstract classes can include concrete properties and methods to be inherited (not just abstract properties and methods which function similarly to interface properties/methods)
								- Classes `implements` interfaces, whereas they `extends` abstract classes
								- ```typescript
								  abstract class Animal {
								  abstract makeSound(): void;
								  }
								  
								  class Dog extends Animal {
								  makeSound() {
								    console.log("woof!")
								  }
								  ```
								- ```typescript
								  interface Animal {
								  makeSound(): void;
								  }
								  
								  class Dog implements Animal {
								  makeSound() {
								    console.log("woof!")
								  }
								  ```
								- Interfaces lack constructor parameters and lack `super()` for calling parent's constructors
							- Type Parameters
							  collapsed:: true
								- ```typescript
								  // A simple class that holds two values of possibly different types
								  class Pair<A, B> {
								   first: A;
								   second: B;
								  
								   constructor(first: A, second: B) {
								  this.first = first;
								  this.second = second;
								   }
								  }
								  
								  // Create an instance with specific types (string and number)
								  const myPair = new Pair<string, number>("hello", 123);
								  
								  console.log(myPair.first);  // Output: hello
								  console.log(myPair.second); // Output: 123
								  ```
								- ```typescript
								  // Define the class with two type parameters
								  class PairOptions<T extends object, U extends object> {
								  first: T;
								  second: U;
								  
								  constructor(first: T, second: U) {
								  this.first = first;
								  this.second = second;
								  }
								  
								  serialize(): [string[], string[]] {
								  // Example serialization: convert all values to strings
								  const serT = Object.values(this.first).map(val => String(val));
								  const serU = Object.values(this.second).map(val => String(val));
								  return [serT, serU];
								  }
								  }
								  
								  // Example type definitions
								  interface FooOptions {
								  name: string;
								  count: number;
								  }
								  
								  interface BarOptions {
								  enabled: boolean;
								  notes?: string;
								  }
								  
								  // Create an instance using `new` and assign it to a variable
								  const pairInstance = new PairOptions<FooOptions, BarOptions>(
								  { name: "Example", count: 1 },
								  { enabled: true, notes: "Active" }
								  );
								  
								  console.log(pairInstance.serialize());
								  // Output: [ [ 'Example', '1' ], [ 'true', 'Active' ] ]
								  ```
								- `T` is a common generic type parameter
									- ```typescript
									  export interface GOptions<T extends object> { // This means T must be an an object, or a subtype of an object
									    defaults: Required<T>; // Any properties defined on `T` must be provided and cannot be optional
									    value: Required<T>;
									  }
									  ```
									- Example: if `T` is `{ host: string, port: number }` then `defaults` would need to be an object with both `host` and `port` properties
									- ```typescript
									  interface MyOptions {
									    host: string;
									    port: number;
									  }
									  
									  const options: GOptions<MyOptions> = {
									    defaults: { host: "localhost", port: 5037 } 
									    value: { host: "example.com", port: 1234 }
									  }
									  ```
										- Alternatively written
										  ```typescript
										  const options: GOptions<{ host: string, port: number }> = {
										    defaults: { host: "localhost", port: 5037 } 
										    value: { host: "example.com", port: 1234 }
										  }
										  ```
									- Alternative simpler example
										- ```typescript
										  interface GOptions<T extends object> {
										    defaults: Required<T>
										    value: Required<T>
										  }
										  
										  const networkOptions: GOptions<{ serverIP: number, timeout: number}> = {
										    defaults: { serverIP: "192.168.1.100", timeout: 30 } // Error: Type incorrect
										    value: { serverIP 1921681100, timeout: 30 } // Correct assignment
										  }
										  ```
							- If ScrType is an interface with many properties, then the class property
							  ```typescript
							  value: Required<ScrType>;
							  ```
							  means `value` must be an object containing all the keys defined in ScrType, with every property present and not optional.
							- ```typescript
							  static serialize<T>(options: T, order: readonly (keyof T)[]) {
							  	return order.map((key) => toScOptionValue(options[key], "-"));
							  }
							  ```
							- Complex TypeScript abstract class example
							  collapsed:: true
								- ```typescript
								  export declare abstract class GOptionsBase<T extends object, B extends GOptions<object>> implements GOptions<T> {
								    #private;
								    protected _base: B;
								    abstract get defaults(): Required<T>;
								    readonly value: Required<T>;
								    constructor(base: B, value: Required<T>);
								    abstract serialize(): string[];
								  }
								  ```
								- 1. export declare abstract class GOptionsBase<...>
									- export: Makes the class available to be imported from other modules.
									- declare: Indicates this is an ambient declaration—it declares the shape of this class without providing the implementation. Often used in .d.ts files or to describe interfaces to existing JS code.
									- abstract class: This class is abstract, meaning:
										- You cannot instantiate it directly.
										- It may contain abstract members (methods or properties) that must be implemented by subclasses.
								- 2. Generic parameters <T extends object, B extends GOptions<object>>
									- T extends object:
										- T is a generic type parameter constrained to types that are objects.
									- B extends GOptions<object>:
										- B is another generic parameter constrained to be a subtype of GOptions<object>.
									- This pattern sets typing constraints for subclasses and instances, making the class flexible and type-safe.
								- 3. implements GOptions<T>
									- The class promises to implement the interface GOptions<T>.
									- This means it must provide the methods and properties defined in that interface, aside from any declared abstract here.
								- 4. `#private`;
									- The hash (#) declares private class fields—this is a marker indicating the class has some private data.
									- The semicolon is a placeholder, and because the class is declared (no implementation here), the actual private fields are not defined in this declaration.
								- 5. protected _base: B;
									- Protected property _base of type B.
									- Accessible to this class and subclasses but not outside.
									- Stores the base object passed in, typically used internally.
								- 6. abstract get defaults(): Required<T>;
									- An abstract getter named defaults.
									- Subclasses must implement a getter returning a Required<T>.
									- Required<T> means all properties of T must be present (none optional).
									- Is a property accessor, not a method.
								- 7. readonly value: Required<T>;
									- A readonly property called value.
									- Typed as Required<T>, so it holds a complete, non-optional object based on T.
									- Because this is a declaration without implementation, this property is expected to be set in the constructor or by subclasses.
								- 8. constructor(base: B, value: Required<T>);
									- Declares a constructor taking:
										- base of type B
										- value of type Required<T>
									- No implementation here (due to declare), but this signature expresses how subclasses and consumers construct instances.
								- 9. abstract serialize(): string[];
									- Abstract method serialize returning an array of strings.
									- Subclasses must implement this method defining how to serialize the options represented by this class.
							- Related: [[JavaScript]] : ((67376787-8e8c-4977-974d-34b619380f7c))
						- Solving issues when a value might be `undefined`
						  collapsed:: true
							- Safest approach — ensures you only call the function when you actually have a number:
							  ```ts
							  if (maybeNum !== undefined) {
							  square(maybeNum); // ✅ now it's just a number
							  }
							  ```
							- If an object might be undefined but the property it's on usually isn't then you can use a ? e.g. `file?.size` instead of accessing `file.size`
							- If a value *might* be undefined you can give it a default value (nullish coalescing operator) e.g. `file.size ?? 1`
							- Non-null assertion - If you know it’s not undefined here (you’ve ensured it earlier in your code, even if TypeScript can’t see it), you can assert it:
							  ```ts
							  square(maybeNum!); // tells TS “trust me, this isn’t undefined”
							  ```
						- `enum` is a normal import (`import { EnumName } from`, whereas `interface` requires `import type { InterfaceName } from`
						- ((68d1c0cb-87c2-46b9-804a-6fafc7df91be))
						- type alias declaration
						  collapsed:: true
							- Example:
							- ```typescript
							  const SDA = {
							    TInit: { x: number; y: string },
							    otherProp: 42,
							  };
							  
							  export type S = (typeof SDA)["TInit"];
							  ```
								- `(typeof SDA)["TInit"]`
									- This is indexing into the type of SDA with the key "TInit".
									- It means the type of the property or member named "TInit" on whatever SDA is.
									- So the result is the type of SDA.TInit.
								- ```typescript
								  type S = {
								    x: number;
								    y: string;
								  };
								  ```
						- Union types
						  collapsed:: true
							- ```typescript
							  audioStream: 
							  | ReadableWriteablePair<Uint8Array, Consumable<Uint8Array>>
							  | undefined;
							  ```
								- This uses a union type, prefixed by the vertical bar (|), to indicate that the property may legally hold a value matching either of these two types
								- `ReadableWriteablePair` is likely a generic type or class that takes two type arguments. Here, it holds a `Uint8Array` for the readable side, and a `Consumable<Uint8Array>` for the writable side.
							- These are functionally identical
								- ```typescript
								  audioStream: 
								  | ReadableWriteablePair<Uint8Array, Consumable<Uint8Array>>
								  | undefined;
								  
								  videoStream: 
								  ReadableWriteablePair<Uint8Array, Consumable<Uint8Array>>
								  | undefined;
								  ```
							-
				- # [Learning Resources]
				  collapsed:: true
					- {{embed ((63904f3c-2367-4a2e-9be3-c61d03ac828e))}}
					- Beginner resources
						- [Playground](http://www.typescriptlang.org/Playground/)
					- Blog post
						- https://blog.teamtreehouse.com/getting-started-typescript
						- https://learnxinyminutes.com/docs/typescript/
						- TS in ((63209272-1088-4824-a762-4ac7ded04b0a))
						  collapsed:: true
							- https://code.visualstudio.com/docs/languages/typescript
							- https://code.visualstudio.com/docs/typescript/typescript-compiling
							- https://code.visualstudio.com/docs/typescript/typescript-tutorial
						- https://news.ycombinator.com/item?id=28837181
					- Courses
						- [TypeScript: The starting point for learning TypeScript](https://www.typescriptlang.org/docs/)
						  id:: 638d0620-69d8-4aa7-bb09-c754f8e967ac
						  collapsed:: true
							- Defining Types
								- How to use an interface declaration to an object
								  id:: 63904f3c-71bc-480b-8f11-20935e46a3a8
								  collapsed:: true
									- Example object
									  ```javascript
									  const user = {
									    name: "Hayes",
									    id: 0,
									  };
									  ```
									- You can explicitly describe this object's shape using an `interface` declaration
									  ```typescript
									  interface User {
									    name: string;
									    id: number;
									  }
									  ```
									- This then allows you to modify the original object and add a `: TypeName` after the variable declaration:
									  ```typescript
									  const user: User = {
									    name: "Hayes",
									    id: 0,
									  };
									  ```
									- Related: ((63904f3c-ab98-4640-9ba6-5c42f4d1961c))
								- You can use an `interface` declaration with classes
								  collapsed:: true
									- ```typescript
									  interface User {
									    name: string;
									    id: number;
									  }
									   
									  class UserAccount {
									    name: string;
									    id: number;
									   
									    constructor(name: string, id: number) {
									      this.name = name;
									      this.id = id;
									    }
									  }
									   
									  const user: User = new UserAccount("Murphy", 1);
									  ```
									- Related: ((6377ece3-2e80-40ca-8e8b-f9f734259790))
								- Usage with functions
								  id:: 63904f3c-a301-4b67-ab59-38411595949c
								  collapsed:: true
									- You can use `interfaces` to annotate parameters
										- ```typescript
										  function deleteUser(user: User) {
										    // ...
										  }
										  ```
									- You can use `interfaces` to annotate return values
										- ```typescript
										  function getAdminUser(): User {
										    //...
										  }
										  ```
									- Both together example
										- ```typescript
										  export function twoFer(name: User, amount: Admin ): Result {
										    if (name) {
										      return `One for ${name}, one for me.`
										    } else {
										      return `One for you, one for me.`
										    }
										  }
										  ```
									- You can alternatively not use an `interface` and instead just a standard `type`:
										- ```typescript
										  export function twoFer(name: string, amount: number): string {
										    if (name) {
										      return `One for ${name}, one for me.`
										    } else {
										      return `One for you, one for me.`
										    }
										  }
										  ```
								- Interfaces vs Type aliases
								  id:: 63904f3c-ab98-4640-9ba6-5c42f4d1961c
								  collapsed:: true
									- there are two syntaxes for building types: Interfaces and Type (aliases)
									- You should prefer `interface`. Use `type` when you need specific features.
									- ```typescript
									  // There are two main tools to declare the shape of an object: interfaces and type aliases.
									  // They are very similar, and for the most common cases act the same.
									  
									  type BirdType = {
									    wings: 2;
									  };
									  
									  interface BirdInterface {
									    wings: 2;
									  }
									  
									  const bird1: BirdType = { wings: 2 };
									  const bird2: BirdInterface = { wings: 2 };
									  
									  // Because TypeScript is a structural type system,
									  // it's possible to intermix their use too.
									  
									  const bird3: BirdInterface = bird1;
									  
									  // They both support extending other interfaces and types.
									  // Type aliases do this via intersection types, while
									  // interfaces have a keyword.
									  
									  type Owl = { nocturnal: true } & BirdType;
									  type Robin = { nocturnal: false } & BirdInterface;
									  
									  interface Peacock extends BirdType {
									    colourful: true;
									    flies: false;
									  }
									  interface Chicken extends BirdInterface {
									    colourful: false;
									    flies: false;
									  }
									  
									  let owl: Owl = { wings: 2, nocturnal: true };
									  let chicken: Chicken = { wings: 2, colourful: false, flies: false };
									  
									  // That said, we recommend you use interfaces over type
									  // aliases. Specifically, because you will get better error
									  // messages. If you hover over the following errors, you can
									  // see how TypeScript can provide terser and more focused
									  // messages when working with interfaces like Chicken.
									  
									  owl = chicken;
									  chicken = owl;
									  ```
									- ```typescript
									  // One major difference between type aliases vs interfaces
									  // are that interfaces are open and type aliases are closed.
									  // This means you can extend an interface by declaring it
									  // a second time.
									  
									  interface Kitten {
									    purrs: boolean;
									  }
									  
									  interface Kitten {
									    colour: string;
									  }
									  
									  // In the other case a type cannot be changed outside of
									  // its declaration.
									  
									  type Puppy = {
									    color: string;
									  };
									  
									  type Puppy = {
									    toys: number;
									  };
									  
									  // Depending on your goals, this difference could be a
									  // positive or a negative. However for publicly exposed
									  // types, it's a better call to make them an interface.
									  
									  // One of the best resources for seeing all of the edge
									  // cases around types vs interfaces, this stack overflow
									  // thread is a good place to start:
									  
									  // [Interfaces vs Types in TypeScript - Stack Overflow](https://stackoverflow.com/questions/37233735/typescript-interfaces-vs-types/52682220#52682220)
									  ```
									- Related: ((63904f3c-71bc-480b-8f11-20935e46a3a8))
							- Composing Types
								- You can create complex types by combining simple ones. There are two popular ways to do so: with unions, and with generics.
								- Unions
								  collapsed:: true
									- You can declare that a type could be one of many types
										- Examples
											- Mouseover `MyBoo1` and it'll be classed as `boolean`
											  ```typescript
											  type MyBoo1 = true | false;
											  ```
											- Mousseover either of these and you'll see the type classed a `string`:
											  ```typescript
											  type WindowStates = "open" | "closed" | "minimized";
											  type LockStates = "locked" | "unlocked";
											  ```
											- Mouseover this and you'll see it as `number`:
											  ```typescript
											  type PositiveOddNumbersUnderTen = 1 | 3 | 5 | 7 | 9;
											  ```
									- It also allows handling mixed types
										- Example: a function that takes an `array` or a `string`
										  ```typescript
										  function getLength(obj: string | string[]) {
										    return obj.length;
										  }
										  ```
										- This allows you to easily have a function return different values based on the type of the parameter
											- Example: return different values depending on whether it is passed a `string` or an `array`:
											  ```typescript
											  function wrapInArray(obj: string | string[]) {
											    if (typeof obj === "string") {
											      return [obj];
											    }
											    return obj;
											  }
											  ```
								- Generics
								  collapsed:: true
									- Generics provide variables to types
									- A common example is an array. An array without generics could contain anything. An array with generics can describe the values that the array contains.
										- ```typescript
										  type StringArray = Array<string>;
										  type NumberArray = Array<number>;
										  type ObjectWithNameArray = Array<{ name: string }>;
										  ```
									- You can  declare your own types that use generics:
										- ```typescript
										  interface Backpack<Type> {
										    add: (obj: Type) => void;
										    get: () => Type;
										  }
										   
										  // This line is a shortcut to tell TypeScript there is a
										  // constant called `backpack`, and to not worry about where it came from.
										  declare const backpack: Backpack<string>;
										   
										  // object is a string, because we declared it above as the variable part of Backpack.
										  const object = backpack.get();
										   
										  // Since the backpack variable is a string, you can't pass a number to the add function.
										  backpack.add(23);
										  ```
							- Structural Type System
								- One of TypeScript’s core principles is that type checking focuses on the shape that values have. This is sometimes called “duck typing” or “structural typing”.
								- In a structural type system, if two objects have the same shape, they are considered to be of the same type.
								  collapsed:: true
									- Example: The point variable is never declared to be a Point type. However, TypeScript compares the shape of point to the shape of Point in the type-check. They have the same shape, so the code passes.
									  ```typescript
									  interface Point {
									    x: number;
									    y: number;
									  }
									   
									  function logPoint(p: Point) {
									    console.log(`${p.x}, ${p.y}`);
									  }
									   
									  // logs "12, 26"
									  const point = { x: 12, y: 26 };
									  logPoint(point);
									  ```
									- The shape-matching only requires a subset of the object’s fields to match.
									  ```typescript
									  const point3 = { x: 12, y: 26, z: 89 };
									  logPoint(point3); // logs "12, 26"
									   
									  const rect = { x: 33, y: 3, width: 30, height: 80 };
									  logPoint(rect); // logs "33, 3"
									   
									  const color = { hex: "#187ABF" };
									  logPoint(color); // error, it's missing the properties from type 'Point': x, y
									  ```
								- There is no difference between how classes and objects conform to shapes:
								  collapsed:: true
									- ```typescript
									  class VirtualPoint {
									    x: number;
									    y: number;
									   
									    constructor(x: number, y: number) {
									      this.x = x;
									      this.y = y;
									    }
									  }
									   
									  const newVPoint = new VirtualPoint(13, 56);
									  logPoint(newVPoint); // logs "13, 56"
									  ```
							- [TypeScript: Documentation - The Basics](https://www.typescriptlang.org/docs/handbook/2/basic-types.html)
						- [TypeScript Roadmap: Learn to become a TypeScript developer](https://roadmap.sh/typescript)
						  id:: 63fdd825-6038-4479-b887-214407b6f379
						- [Exercism track for TypeScript](https://exercism.org/tracks/typescript)
						  id:: 633de987-00dd-4d64-8595-a854c72647c2
						  collapsed:: true
							- After a function's parameters you define the `return type`, this is the type of value that the function should return
								- Example
									- The return type here is `string`:
									  ```typescript
									  export function hello(): string {
									    return 'Goodbye, Mars!'
									  }
									  ```
										- In JavaScript you can't set the expected data type
										  ```javascript
										  export function hello() {
										    return 'Goodbye, Mars!'
										  }
										  ```
							- Two-Fer solution
								- ```typescript
								  export default function twoFer(name?: string): string {
								      return `One for ${name || "you"}, one for me.`
								  }
								  ```
							- Related: ((6647026a-3097-449d-8f48-31066dd80b24))
						- [GitHub - type-challenges/type-challenges: Collection of TypeScript type challenges with online judge](https://github.com/type-challenges/type-challenges)
						- [Type-Level TypeScript](https://type-level-typescript.com/)
						  id:: 63a9bb67-5b87-44b3-b96a-59c77cc8d505
						- Recommended by Arshi: [Learn TypeScript | Codecademy](https://www.codecademy.com/learn/learn-typescript)
						- [A text adventure game on TypeScript's type system](https://github.com/cassiozen/TDungeon)
						- TypeScript Fundamentals
						  source:: [Learn TypeScript from the ground up with James Henry](https://typescriptcourses.com/typescript-fundamentals) | #A001 ~/Documents/MUSEUM/Programming/Anki1.ods
						  collapsed:: true
							- Basics
								- `node -i`
								  Run interactive node shell
								- Instead of `var age = 1` it is `var age: number = 1` (you add a type annotation)
								- Three main types used as type annotations: `number`, `string` and `boolean`
									- Related: [Types includes 7: `number`, `string`, `boolean`, `undefined`, `null`, `object`, `symbol` (ES2015)](((629ccb26-0412-44d5-8c9b-22f20cc7e773)))
							- [**<--created Anki cards up to here-->**](((629e07ee-075d-4a72-9bd0-fd63cd35f152)))
							- If importing a class e.g. `import { Animal } from './two';` then we can open that file `two` by using command/ctrl + click on `Animal` anywhere in the file
							- Refactoring
								- Easier than find-and-replace
								- e.g. `class Animal` can be changed via right-click the name and "change symbol". (otherwise `Animal` in code comments would get affected too. This feature also changes parent files which export that class from
							- Not TypeScript-specific:
								- Running a script when the DOM is loaded (<script> element for HTML files)
								  ```javascript
								  <script>
								   document.addEventListener(
								    'DOMContentLoaded', 
								    main
								   )
								  </script>
								  														- Function - generating a random ID
								  ```javascript
								  function generateRandomID() {
								   return '#' + Math.random().toString(36).substr(2, 7)
								  }
							- yarn (Facebook's JavaScript package manager) is often faster than npm
								- yarn global add typescript
								  Installing typescript
								- In ((63209272-1088-4824-a762-4ac7ded04b0a)) terminal run `tsc --init` to create a `tsconfig.json` file
									- change `target` to different than es5?
										- `tsc --target es2015`
										- Add to `compilerOptions` bit
											- `"allowJs": true,`
												- This would then use your existing JS files
											- `outDir": "dist",`
												- This ensures existing JS files are not overwritten  (output directory)
									- Run `tsc` which uses TypeScript compiler to output JS files
								- Create a `src` folder for TS files, `dist` for output JS files
							- `tsc -w` - watch mode. Open up integrated terminal
								- This is an alternative to one-off compiles
								- Don't have to keep rerunning the ts compiler
								- That keeps doing the outDir dist to output the js file
							- If an error is made e.g. putting "yes" in a `number` variable then it'll show an error in the terminal but it will still create an output file unless tsconfig changed
								- `"noEmitOnError": true,` stops emitting a new version of this code because the type was invalid
							- String literal types
								- `var symbol: '#' = '#'` will work, that means `var symbol: '#' = '$'` won't work
								- or
								- `const symbol = '#'`
								  Added in ES201. If ES5 is the output, then it'll convert this const to a var in the JS output
							- Union types and type aliases
								- Similar to string literal types exceptmultiple choices are viable for the value
								- `const symbol: '#' | '$' | '@' = '#'`
									- It will accept either # OR $ OR @. Currently #
								- Type alias
									- `type ValidSymbol = '#' | '$'`
									- It doesn't get shown in output JavaScript
									- This allows you to use `const symbol: ValidSymbol = '$'`
									- This allows you to use union types easily everywhere
							- Function parameters
								- Example
								  ```javascript
								  `function generateRandomId(symbol: ValidSymbol, length: number) { 
								   return symbol + Math.random().toString(36)
								    .substr(2, length)
								  }
								  ```
								- Can also make the output string for example if you want to specify
								  ```javascript
								  `function generateRandomId(symbol: ValidSymbol, length: number): string { 
								   return symbol + Math.random().toString(36)
								    .substr(2, length)
								  }
								  ```
								- Use function parameters rather than global variables
							- Void and Never types
								- Void - returns no value, so no specific type
									- example (trigger a browser alert)
									  `function userAlert(): void { 
									   alert('Hello!')
								- Never - never has a chance to return a value
									- Example
									  `function userAlert(): never {
									   throw new Error('Fail')
									  }
									  `
									- Works for never ending loops,
							- Null and Undefined types
							  **Seems like intermediate JavaScript, bit over my head on March**
								- Example
								  `function main() {`
								- Null = variable doesn't exist
									- Enable it in tsconfig.json
									  `"strictNullChecks": true,`
									- Use example `if (app) {` to make the union type not be null (non-nullable types?)
								- Undefined = variable exists, but no value set
									- Example
									  ```javascript
									  function generateRandomId(symbol: ValidSymbol, length?: number) { 
									  
									  # This makes length a union type of number or undefined
									  # Same as function generateRandomId(symbol: ValidSymbol, length?: number | undefined) { 
									  
									   return symbol + Math.random().toString(36)
									    .substr(2, length)
									  }
									  ```
							- Next: Describe values using Interfaces
							  [Learn TypeScript from the ground up with James Henry](https://typescriptcourses.com/typescript-fundamentals/player/235713160)
						- [Programming in TypeScript – Full Course](https://www.freecodecamp.org/news/programming-in-typescript/)
						- [TypeScript for React Developers – Why TypeScript is Useful and How it Works](https://www.freecodecamp.org/news/typescript-for-react-developers/)
						- Max's "Understanding Typescript" course on Udemy
						- https://typescriptbyexample.com/
						- https://scrimba.com/g/gintrototypescript
						- https://www.mindzgrouptech.net/2017/02/11/typescript-tutorial-course-introduction-chapter-1/
					- Books
						- https://basarat.gitbooks.io/typescript/
						- https://pagalvin.gitbooks.io/yet-another-typescript-book/content/
					- ### Codebase examples
						- `/home/boss/Documents/Git/Other/Logseq_linked/ya-webadb`
							- [Web version of scrcpy](https://github.com/yume-chan/ya-webadb)
								- https://docs.tangoapp.dev/
						- `/home/boss/Documents/Git/Other/Logseq_linked/old-demo`
							- [FOSS version of old web app](https://github.com/tango-adb/old-demo)
					- Assorted
						- ((63bae0c2-40c2-4fe2-963d-6dd840a70a81))
							- {{embed ((63bae0c2-40c2-4fe2-963d-6dd840a70a81))}}
						- [GitHub - ronami/meta-typing: 📚 Functions and algorithms implemented purely with TypeScript's type system](https://github.com/ronami/meta-typing)
						  id:: 663b9cb0-2aec-4347-adb4-dd6db19eb3be
						-
						- Other recommended by Arshi
							- Bonus: Have a look at `ts-node` ([https://typestrong.org/ts-node/docs/](https://typestrong.org/ts-node/docs/)), which can make it easier to write and run server-sided TypeScript.
							- Bonus: Have a look at tools like NestJS ([https://docs.nestjs.com/](https://docs.nestjs.com/))
							- and Ts.ED ([https://tsed.io/](https://tsed.io/)) for other ways of writing a server with TypeScript.
							- [https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html)
							- [https://www.typescriptlang.org/docs/handbook/typescript-tooling-in-5-minutes.html](https://www.typescriptlang.org/docs/handbook/typescript-tooling-in-5-minutes.html)
							- [https://medium.com/free-code-camp/learn-typescript-in-5-minutes-13eda868daeb](https://medium.com/free-code-camp/learn-typescript-in-5-minutes-13eda868daeb)
							- https://www.youtube.com/watch?v=ahCwqrYpIuM
							- https://www.youtube.com/watch?v=zQnBQ4tB3ZA
							- https://www.youtube.com/watch?v=ydkQlJhodio
						- https://github.com/dzharii/awesome-typescript
						- https://medium.com/@jcreamer898/typescript-learning-resources-b1205a98c47c
					- [Roadmap · microsoft/TypeScript Wiki · GitHub](https://github.com/Microsoft/TypeScript/wiki/Roadmap)
					  collapsed:: true
						- 1
							- 2
								- If you want to learn Typescript, check out the following resources.
								- [TS Tutorial](https://www.typescriptlang.org/docs/handbook/release-notes/overview.html)
								- [TS Playground](https://www.typescriptlang.org/play)
								  
								  TypeScript is a superset of JS.
								  TypeScript offers all of JavaScript’s features, and an additional layer on top of these: TypeScript’s type system.
								- [Exploring ES6](https://leanpub.com/exploring-es6) book, by Axel Rauschmayer
								- [ES6 Katas](https://jskatas.org/#bundle-es6-katas) website
								- [Babel compiler](https://github.com/babel/babel)
							- 3
								- ## Recommended References
								- [TypeScript QuickStart](https://www.typescriptlang.org/docs/handbook/release-notes/overview.html)
								- [TypeScript Playground](https://www.typescriptlang.org/play)
								- [ECMAScript 2015 Language Specification](https://www.ecma-international.org/wp-content/uploads/ECMA-262_6th_edition_june_2015.pdf) (pdf)
								- [Mozilla JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
							- more
							-
				- {Archive}
				  collapsed:: true
					- https://hackr.io/tutorials/learn-typescript
		- Others
		  collapsed:: true
			- [Coffeescript](https://coffeescript.org/)
			- [Clojure](https://clojure.org/)
			- Dart
			- [Haxe](https://haxe.org/)
			- [ScalaJs](https://www.scala-js.org/)
			- and a whole host more (see this [list](https://github.com/jashkenas/coffeescript/wiki/List-of-languages-that-compile-to-JS))
			- There's two ends: languages which compile to JS and
				- On the one hand, you have future proof tools that take modern ECMAScript standards and compile it down to older JavaScript versions with Babel being the most popular one. On the other hand, you have languages that may totally differ from JavaScript which target JavaScript, like Coffeescript, Clojure, Dart, Elm, Haxe, ScalaJs, and a whole host more (see this list). These languages, though they might be better than where JavaScript's future might ever lead, run a greater risk of not finding enough adoption for their futures to be guaranteed. You might also have more trouble finding experienced developers for some of these languages, though the ones you will find can often be more enthusiastic. Interop with JavaScript can also be a bit more involved, since they are farther removed from what JavaScript actually is.
				- TypeScript sits in between these two extremes, thus balancing the risk. TypeScript is not a risky choice by any standard. It takes very little effort to get used to if you are familiar with JavaScript, since it is not a completely different language, has excellent JavaScript interoperability support and it has seen a lot of adoption recently.
			- [Elm](https://elm-lang.org/) (Rust-like)
	- _Frameworks and Libraries_
	  id:: 63baa386-e89b-4c6f-9dad-19586353252f
	  collapsed:: true
		- Sorted by end
			- Frontend
			  id:: 63679852-9cb5-4278-b624-6f742ac0088f
				- Most notable
					- ((629ccb26-62cc-426a-9616-4d8969f32580))
					- _Page builders_
					  collapsed:: true
						- https://github.com/JefMari/awesome-wysiwyg
					- CSS-in-JS libraries
					  collapsed:: true
					  id:: 629ccb26-23a1-4361-8de0-d8e3d34c8ce1
						- Overview
							- Thinking in components — No longer do you have to maintain bunch of style-sheets. CSS-in-JS abstracts the CSS model to the component level, rather than the document level (modularity).
						- Pros/Cons Vs CSS-in-CSS
						  collapsed:: true
							- Pros
							  collapsed:: true
								- the challenge is modern web is written in components not pages.
									- CSS was never actually made for component based approaches. CSS-in-JS solves exactly this problem.
								- Thinking in components — No longer do you have to maintain bunch of style-sheets. CSS-in-JS abstracts the CSS model to the component level, rather than the document level (modularity).
								- CSS-in-JS leverages the full power of the JavaScript ecosystem to enhance CSS.
								- “True rules isolation” — Scoped selectors are not enough. CSS has properties which are inherited automatically from the parent element, if not explicitly defined. Thanks to jss-isolate plugin, JSS rules will not inherit properties.
								  http://cssinjs.org/jss-isolate
								- Scoped selectors — CSS has just one global namespace. It is impossible to avoid selector collisions in non-trivial applications. Naming conventions like BEM might help within one project, but will not when integrating third-party code. JSS generates unique class names by default when it compiles JSON representation to CSS.
								- Vendor Prefixing —The CSS rules are automatically vendor prefixed, so you don’t have to think about it.
								- Code sharing — Easily share constants and functions between JS and CSS.
								- Only the styles which are currently in use on your screen are also in the DOM (react-jss).
								- Dead code elimination
								  https://en.wikipedia.org/wiki/Dead_code_elimination
								- Unit tests for CSS!
							- Cons
								- Learning curve.
								- New dependencies.
								- Harder for newer teammates to adapt to the code-base. People who are new to front-end have to learn “more” things.
								- Challenging the status quo. (not necessarily a con)
						- Libraries
							- Comparison
							  https://github.com/MicheleBertoli/css-in-js/blob/master/README.md
							- CSS loader
							  collapsed:: true
								- https://github.com/webpack/css-loader
							- styled-components
							  collapsed:: true
							  id:: 629ccb26-2f37-4f04-8f15-647f47c825c8
								- https://www.styled-components.com/
							- Glamor
							  collapsed:: true
								- https://github.com/threepointone/glamor
							- Glamorous
							  collapsed:: true
								- https://github.com/paypal/glamorous
							- Radium
							  collapsed:: true
								- https://github.com/FormidableLabs/radium
							- Reactcss
							  collapsed:: true
								- https://github.com/casesandberg/reactcss
							- React JSS
							  collapsed:: true
								- https://github.com/jsstyles/react-jss
								- Jss
								  collapsed:: true
									- https://cssinjs.org/?v=v10.0.0-alpha.9
							- Aphrodite
							  collapsed:: true
								- https://github.com/Khan/aphrodite
							- Emotion
							  collapsed:: true
								- https://emotion.sh/
						- Unsorted
						- Compared against inline styles
							- https://mxstbr.blog/2016/11/inline-styles-vs-css-in-js/
						- Related: CSS-in-[CSS](((629ccb26-0f8b-4a06-a8bb-6e57ecbfc824)))
				- Others
					- [Ember](https://emberjs.com/)
					- [jQuery](https://jquery.com/)
					  collapsed:: true
						- Heavy?
					- Asynchronous JavaScript (AJAX)
				- ((6396fb64-9aeb-4ee3-bf46-849eac2fb748)) : ((635fba72-d8b2-4372-b1f9-ce7a107f2df7))
				  collapsed:: true
					- {{embed ((635fba72-d8b2-4372-b1f9-ce7a107f2df7))}}
			- Backend
			  id:: 63baa386-3de1-4a21-b62e-a339148671de
				- [Node.js](https://nodejs.org)
				  id:: 629ccb26-3115-4d41-b4db-a686fe51a4a2
				  collapsed:: true
					- Links
						- [GitHub - nodejs/node: Node.js JavaScript runtime](https://github.com/nodejs/node)
					- Pros/Cons
					  collapsed:: true
						- Pros
							- allows us to use JavaScript server-side.
							- [NPM](https://npmjs.com) - massive registry with tons of open-source libraries
							- [Since mid-2024 has TypeScript support](https://github.com/nodejs/node/pull/53725)
					- # Documentation
						- Info
						  collapsed:: true
							- Runtime environment = extends vanilla JavaScript with some additional stuff
							  id:: 634d4cee-5275-4aee-a026-62b33517d5cd
							- JavaScript engine = a program that turn JavaScript code into binary
							- Node.js is a platform built on Chrome's JavaScript runtime for easily building fast, scalable network applications.
							  id:: 634bc0c1-27c9-4149-8209-3a28ead13b9e
							- NodeJS uses [V8](https://v8.dev) as it's JavaScript engine
							  collapsed:: true
								- It's Google's open-source JavaScript and WebAssembly engine, written in C++
								- DOM is exposed by a browser, not the engine. So it's unavailable to Node
						- ## SOPs
							- Installation
							  id:: 63974fb0-ef9b-4610-9d0a-fb5337fbfefc
							  collapsed:: true
								- Basic install
									- `sudo apt install nodejs`
									- `node -v`
									  Check Node version
								- [Install via a Node version manager](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm#using-a-node-version-manager-to-install-nodejs-and-npm)
								  id:: 64024e3e-17bd-46f7-b70d-41a02bf20981
								  collapsed:: true
									- Install `nvm`
										- Note: don't have to uninstall npm to use this
										- ```bash
										  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash
										  ```
											- [This script will install or update nvm](https://github.com/nvm-sh/nvm#install--update-script)
										- `source ~/.bashrc` to refresh bash
										- `command -v nvm` to check if it's installed (it should return `nvm`)
									- Using `nvm` (current [[Dec 22nd, 2022]] )
									  collapsed:: true
										- `nvm install node` = "node" is an alias for the latest version
											- Output
											  ```bash
											  Your user’s .npmrc file (${HOME}/.npmrc)
											  has a `globalconfig` and/or a `prefix` setting, which are incompatible with nvm.
											  Run `nvm use --delete-prefix v19.3.0` to unset it.
											  ```
									- {Archive}
										- Using `fnm` (used prior to [[Dec 22nd, 2022]] )
										  collapsed:: true
											- `fnm list` - shows all the node versions installed in the system
											- `fnm list-remote` - Shows all the available node versions which can be installed.
											- `fnm install <version>` - Install the node version locally which we got from list command. eg- fnm install v14.0.2  would install v14.0.2 locally.
											- `fnm use <version>` - Activate the given version which is installed in the system. eg - fnm use v16.13.2 would activate v16.13.2 which is installed
											- `fnm default <version>` - Set the node version to default alias. eg fnm default v16.13.2 would make  v16.13.2 as the default version for the system.
											- `fnm current` - Prints the current node version which is activated.
										- Basic install using `fnm`
										  collapsed:: true
											- `curl -fsSL https://fnm.vercel.app/install | bash`
											- `sudo nano ~/.bashrc`
											- ((644c0b9b-cdd7-48ca-900d-1ae586db9309))
											- `fnm list-remote`
											  List available versions to install
											- `fnm install 18.1.0`
											  Install a chosen version
								- Change permissions if using ((63209272-1088-4824-a762-4ac7ded04b0a)) Flatpak
									- Used ((634bc1ee-d662-4244-bf4d-6bd64e77dbd1)) to check that `~/.fnm/fnm` is owned by `root`, so Visual Studio Code in a Flatpak is unable to access that directory
									- `cd ~` to change to home directory
									- `chown boss .fnm/fnm` to change the ownership to `boss` (current user)
										- May also need to do `chown boss .fnm`
								- ...
								- https://github.com/nodesource/distributions/blob/master/README.md#using-ubuntu
								-
							- Basics
							  collapsed:: true
								- To run code, on the terminal run `node main.js` assuming `main.js` is the JS file in the directory you're in
								- `global` is main object, which is normally `document` in a browser (as browsers have the DOM)
								- `process.exit()` can exit the NodeJS process
								- [package.json](https://docs.npmjs.com/cli/v10/configuring-npm/package-json)
								  id:: 663914ec-9950-45fa-b647-a9e91775211c
									- Related: ((6550215a-3662-477b-bc03-34f555563394))
							- How to setup a new project
							  id:: 63679852-8d12-4f83-994e-52e0dcbd642f
							  collapsed:: true
								- ((634fd63d-dd88-4a10-a762-9bc0fa467de6))
								  collapsed:: true
									- {{embed ((634fd63d-dd88-4a10-a762-9bc0fa467de6))}}
								- Either
									- `npm init`
									- `git clone`
								- Create a `.gitignore` file and a few standard ignores
								  collapsed:: true
									- ```gitignore
									  node modules
									  .env
									  ```
								- Create a `.env` file and add sensitive data
								  collapsed:: true
									- Store sensitive data here e.g. port number, database URL
								- Install ((63590e56-9473-4435-9a86-177587b4ddff)) with `npm i dotenv -D`
								  collapsed:: true
									- Related: ((6368d436-0062-4e8d-9070-997898b5fa5a))
								- Install `nodemon` with `npm i nodemon -D` if it's an Express project
								- Update `package.json` with a few configs
									- Make ES Modules the default
									  ```json
									  "type": "module"
									  ```
									- *Scripts*
										- ```json
										  "scripts": {
										    "start": "node -r dotenv/config app.js",
										    "dev": "nodemon -r dotenv/config app.js"
										  }
										  ```
										- `require` will load our environment variables for us
								- `node run dev` to run the dev script
								- *If project uses a database*
									- `npm i pg`
									- Declare database URL via `.env`
									  collapsed:: true
										- ```config
										  DATABASE_URL = [Something.](https://something.com)
										  PORT = 3000
										  ```
									- `/db/index.js`
									  collapsed:: true
										- Create and export pool
										- e.g.
										  ```javascript
										  const databaseURL = process.env.DATABASE_URL
										  ```
									- `/models/models.js`
									  collapsed:: true
										- Import the database connection pool
										- Create model functions
										- Export functions
									- `/routes/routes.js`
									  collapsed:: true
										- Import express
										- Import models
										- Export as express router
											- e.g. 
											  ```javascript
											  export const routerName = express.Router();
											  ```
								- *If project uses Express*
									- `app.js`
										- Install the modules
										  collapsed:: true
											- e.g.
											  ```javascript
											  import express from "express";
											  ```
										- Declare app
										  collapsed:: true
											- ```javascript
											  const app = express();
											  ```
										- Mount the express server
										  collapsed:: true
											- ```javascript
											  app.use(express.json());
											  ```
										- Instantiate the required helper functions
										  collapsed:: true
											- e.g.
											  ```javascript
											  app.use(express.json());
											  ```
										- Import the router
										  collapsed:: true
											- ```javascript
											  import { routerName } from './routes/router.js';
											  ```
										- Instantiate the router with desired URL
										  collapsed:: true
											- ```javascript
											  app.use('/api/name', routerName);
											  ```
										- Export the app mdule
										  collapsed:: true
											- ```javascript
											  export default app;
											  ```
								- Related: ((634d2517-30eb-4bbf-b214-abae3ac1b92d))
							- ((63890cb6-2a0e-4039-9d9d-0106f11ccbf6))
							- Cheatsheet
							  id:: 660d69d8-2984-48b1-8ddd-19e4605d1188
							  collapsed:: true
								-
							- Modules
							  collapsed:: true
								- Had a strange edge case where Next.js Webpack wasn't successfully compiling a module and had an irrelevant error message about lacking a loader for the TS filetype
									- Turned out that changing the package name to be prefixed with a namespace e.g. `@yume-chan/` fixed thing. This is because it means that when this package is a symlinked dependency in other modules in their `node_modules` directory then it means it'll be nested in the namespace directory rather than just in a package name directory
									- Our `tsbuild.base.json` had an `include` value that expected a very specific directory structure `../../../src` i.e. from the nested node_module cd up to the module root directory, then cd into `src` dir
									- It also strangely required the module not being a top-level workspace - instead simply as another module within a workspace (workspace defined in top-level package.json as `dir/*`. This is also likely due to the pathing of the `tsbuild` config that it was symlinked to use, but in the end went for copying and using it as a module within another workspace for ease
							- `package.json`
								- package.json contains fuzzy versions of packages (e.g. `^1.0.0`), whilst `package.lock` contains the exact versions
						- [Official docs](https://nodejs.org/api/)
							- https://github.com/nodejs/node
							- `fs/promises`
							  id:: 63b987bc-d2a0-4131-b5c6-c6e5271085ff
							  collapsed:: true
								- [Use `fs/promises` instead of `fs` for better performance](https://advancedweb.hu/do-not-use-fs-sync-methods-in-javascript-use-fs-promises-instead/)
								- The **fs/promises** API provides the following methods:
								- ```js
								  access, copyFile, open, read, write, rename, truncate, ftruncate, 
								  rmdir, fdatasync, fsync, mkdir, readdir, readlink, symlink, fstat, 
								  lstat, stat, link, unlink, fchmod, chmod, lchmod, lchown, fchown, chown,
								   utimes, futimes, realpath, mkdtemp, writeFile, appendFile and readFile.
								  ```
								- Examples
									- ```js
									  import { promises as fs } from 'fs';
									  
									  try {
									      await fs.writeFile("/tmp/test6.js", "console.log('Hello world with Node.js v13 fs.promises!'");
									      console.info("File created successfully with Node.js v13 fs.promises!");
									  } catch (error){
									      console.error(error);
									  }
									  ```
								- Related: ((63a9bb72-6751-4d71-97b9-bfb666964e68))
								-
							- CLI Commands
								- [`npm install`](https://docs.npmjs.com/cli/v8/commands/npm-install)
								  id:: 6368d436-0062-4e8d-9070-997898b5fa5a
								  collapsed:: true
									- Aliases
										- `npm i`, etc
									- `-D, --save-dev` : Package will appear in your  `devDependencies` .
						- ## Commands
							- `npm i`
							  collapsed:: true
								- will get packages from npm's online registry, add binaries to `~/.npm` global cache, then `node_modules` project directory for source code
							- `npm ci`
							  id:: 638f1e9b-38db-4572-ba5d-907613753986
							  collapsed:: true
								- `npm ci` = like `npm i`/`npm install` except it won't check online, it'll instead check the local npm cache and download the dependencies from there after wiping the local `node_modules` folder
								- [npm Blog Archive: Introducing `npm ci` for faster, more reliable builds](https://blog.npmjs.org/post/171556855892/introducing-npm-ci-for-faster-more-reliable)
								- [Difference between npm i and npm ci in Node.js - GeeksforGeeks](https://www.geeksforgeeks.org/difference-between-npm-i-and-npm-ci-in-node-js/)
					- # Ecosystem
						- ## ((629ccb26-3115-4d41-b4db-a686fe51a4a2))-based frameworks
							- [Express.js](https://www.expressjs.org/)
							  id:: 634bc0c1-71ec-40e0-ba94-bf79e177b591
							  collapsed:: true
								- Pros/Cons
								  collapsed:: true
									- Pros
										-
									- Cons
										- [2023 discussion](https://news.ycombinator.com/item?id=38059004) - it's had little feature updates in recent years, ((653e7fcc-86aa-44ca-94e6-5f4bd8fb67a7)) especially is better
									- Unclear
									- Comparisons
								- It's a fast, unopinionated & minimalist web framework. It evolved quickly because it's made simple & straightforward. It's probably the one closer to Node.js' basic ideas of a lightweight system with a modularity approach.
								- Express is a minimal and flexible node.js web application framework, providing a robust set of features for building single and multi-page, and hybrid web applications.
								- Documentation
								  collapsed:: true
									- Installation
									  id:: 634eb68e-0e05-471b-944a-7c6dec69331d
									  ```javascript
									  npm install express
									  ```
									- [app.use](https://expressjs.com/en/4x/api.html#app.use)
									  id:: 63512738-c687-4161-b976-4b66f7a9791d
									- [Routing](https://expressjs.com/en/guide/routing.html)
									  id:: 635161eb-4317-4c8a-a2e6-b137445663a3
								- ((634bc0c1-71ec-40e0-ba94-bf79e177b591))-based frameworks
								  id:: 663a5793-124e-44d7-a216-dddeacb70f56
									- FeatherJS
									  collapsed:: true
										- Build prototypes in minutes and production ready real-time apps in days.
										- Build incredible real-time applications in record time. Feathers is a real-time, micro-service web framework for NodeJS that gives you control over your data via RESTful resources, sockets and flexible plug-ins.
										- http://feathersjs.com/
									- SailsJS
									  collapsed:: true
										- MVC framework for Node.js for building practical, production-ready apps.
										- Sails.js make it easy to build custom, enterprise-grade Node.js apps. It is designed to mimic the MVC pattern of frameworks like Ruby on Rails, but with support for the requirements of modern apps: data-driven APIs with scalable, service-oriented architecture. It's especially good for building chat, realtime dashboards, or multiplayer games.
										- http://sailsjs.com/
									- Sails.js
									  collapsed:: true
										- is a real-time, MVC framework. It was designed to emulate the MVC pattern of Ruby on Rails but with support for modern apps requirements. It does this through data-driven APIs with a scalable, service-oriented architecture.
									- Koa.js
									  collapsed:: true
										- was crafted by the team behind Express. Marketed as the "next generation web framework for Node.js," it's a smaller, more expressive, and more robust foundation for web applications and APIs.
									- Others
									  collapsed:: true
										- https://expressjs.com/en/resources/frameworks.html
								- [Learning Resources]
									- ((63ea1938-5a8e-4b77-a3d5-4a72dc88ba02))
								- Related: ((c901c50e-8262-4a97-b480-1b78b0bb639d))
							- See ((663a5793-124e-44d7-a216-dddeacb70f56))
							- [Meteor](https://www.meteor.com/)
							  collapsed:: true
								- Meteor
								  collapsed:: true
									- [https://www.meteor.com/](https://www.meteor.com/)
								- Meteor with React
								  https://www.google.com/search?q=meteor+react&ie=utf-8&oe=utf-8&client=firefox-b
							- Strapi CMS
							  collapsed:: true
								- Strapi is the most advanced Node.js open-source Content Management Framework to build powerful API with no effort.
							- [Fastify](https://fastify.dev/)
							  id:: 653e7fcc-86aa-44ca-94e6-5f4bd8fb67a7
							- [Hono](https://github.com/honojs/hono)
							- There are many more to explore, so I'll drop a few real quick: Nest.js, Hapi.js, Socket.io, Mean.js, Total.js, Derby.js & Keystone.js.
						- ## Package managers
						  id:: 63baa386-4747-40e9-b222-ab1fb5ab1bf6
							- ### Comparisons
							  collapsed:: true
								- Table
									- |Feature||npm|((67eab246-ee96-418c-9405-057861c93a62))|pnpm|
									  |--|--|--|--|--|
									  |Cache|||||
									  |2|||||
								- npm
									- Global OS-level binary cache `~/.npm/cache`
									- For each project a `node_modules` directory is created with duplicates of packages
										- Non-deterministic `node_modules` folder because of lifecycle scripts (e.g. post-install scripts)
								- pnpm
									- Allows for a centralised node_modules folder (`.pnpm/node_modules`?), then it symlinks the packages into `node_modules` directory for each project
									- Doesn't solve the problem of `~/.npm/cache` being an opaque binary blob
									- `node_modules` remain non-deterministic
								- ((63dbe34b-cf80-4fa6-8ca3-97425040ee87))
								  id:: 67eab246-ee96-418c-9405-057861c93a62
									- The cache is deterministic ZIP files rather than npm's opaque binary cache
									- yarn by default disallows post-install scripts, unless you explicitly allow them to run. This helps improve determinism
										- React and Electron are notorious for post-install scripts, need to check if yarn versions resolve this
							- ### Examples
								- [npm](https://www.npmjs.com)
								  id:: 634bc0c1-c4b8-488f-9c11-5918d0bfb50d
								  collapsed:: true
									- Workspaces
									  collapsed:: true
										- Workspaces are defined in `package.json` and these cna be hierarchical
											- Example
												- `root/`
													- `package.json` - defined 2 workspaces (project1 and project2)
													- `project1/`
														- `package.json` - defining 2 of it's own workspaces (projectA and projectB)
														- `projectA/`
															- `package.json` - no workspaces, just dependencies
														- `projectB/`
															- `package.json` - no workspaces, just dependencies
													- `project2/`
														- `package.json` - no workspaces, just dTheReality1
														  ependencies
											- Hoisting
										- Related: ((68d1c0cb-c0f2-41dc-875e-f61a2aeb6917))
									- Notable packages
									  collapsed:: true
										- [npx](https://www.npmjs.com/package/npx)
										  id:: 636a7232-bbde-4f4c-80d5-0ef4c9c21da5
										  collapsed:: true
										  Package executer - executes packages directly without having to install the modules
											- [Introducing npx: an npm package runner | by Kat Marchán | Medium](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b)
											- Difference between NPM vs NPX
												- NPM is a package manager used to install, delete, and update Javascript packages on your machine. NPX is a package executer, and it is used to execute javascript packages directly, without installing them.” Google et al.
										- [dotenv](https://www.npmjs.com/package/dotenv)
										  id:: 63590e56-9473-4435-9a86-177587b4ddff
										  collapsed:: true
										  Loads environment variables from a `.env` file into `process.env`
											- e.g. access it via the global object `process.env.S3_BUCKET`
											- #+BEGIN_CAUTION
											  Need to include `-r dotenv/config` in the `package.json` file in the Scripts section, in the command like for whatever run scripts are being used.
											  #+END_CAUTION
											- Related:
												- [Show HN: Dotenv, if it is a Unix utility | Hacker News](https://news.ycombinator.com/item?id=40191510)
												- ((63209272-1088-4824-a762-4ac7ded04b0a)) : ((6550215b-740f-4834-ba42-591ac54df33f))
										- [pg](https://www.npmjs.com/package/pg)
										  id:: 63592a1d-90b6-4646-a9ea-f1f0216bb1e6
										  collapsed:: true
										  AKA node-postgres | PostgreSQL client for Node.js
											- [Documentation](https://node-postgres.com/)
												- SOP
													- See ((9f70e86a-d654-48fe-859a-7b19f96e9c56))
												- [Connecting](https://node-postgres.com/features/connecting)
												  collapsed:: true
													- Programmatic
														- Standard template which doesn't use environment variables
															- ```javascript
															  const { Pool, Client } = require('pg')
															  const pool = new Pool({
															    user: 'dbuser',
															    host: 'database.server.com',
															    database: 'mydb',
															    password: 'secretpassword',
															    port: 3211,
															  })
															  
															  pool.query('SELECT NOW()', (err, res) => {
															    console.log(err, res)
															    pool.end()
															  })
															  
															  const client = new Client({
															    user: 'dbuser',
															    host: 'database.server.com',
															    database: 'mydb',
															    password: 'secretpassword',
															    port: 3211,
															  })
															  client.connect()
															  
															  client.query('SELECT NOW()', (err, res) => {
															    console.log(err, res)
															    client.end()
															  })
															  ```
														- Page also has templates for connecting to cloud databases and via unix sockets
														- Connection URI template - used for platforms like Heroku
															- ```javascript
															  const { Pool, Client } = require('pg')
															  const connectionString = 'postgresql://dbuser:secretpassword@database.server.com:3211/mydb'
															  const pool = new Pool({
															    connectionString,
															  })
															  
															  pool.query('SELECT NOW()', (err, res) => {
															    console.log(err, res)
															    pool.end()
															  })
															  
															  const client = new Client({
															    connectionString,
															  })
															  client.connect()
															  
															  client.query('SELECT NOW()', (err, res) => {
															    console.log(err, res)
															    client.end()
															  })
															  ```
												- Queries
												  collapsed:: true
													- Parameterised query
													  id:: 63594b55-df8e-49b8-95c1-f3433e23c751
														- SQL injection vulnerability = ensuring that people can't just pass in `DROP TABLE;` as a value and damage your database
														- Example
															- ```javascript
															  // Vulnerable version
															  const result = await query ('SELECT * FROM books WHERE id = ${id}');
															  const book = result.rows[id];
															  return book;
															  
															  // Parameterised query
															  const result = await query (`SELECT * FROM books WHERE id = $1`, [id]);
															  const book = result.rows[id];
															  return book;
															  ```
															- `$1`, `$2`, etc just means to replace that symbol in the string with whatever you write as the next parameter
															  ```javascript
															  const result = await query (`SELECT * FROM books WHERE id = $1 + $2`, [id], [test]);
															  
															  // $1 means use the next parameter here
															  // $2 means use the second parameter 
															  ```
														-
												- Pooling
													- `pg-pool` module prevents issues with having to reconnect to databases, limited number of connections, etc
													- It basically  manages the connections so you don't have too many
													  id:: 63592ccf-ef7b-4af2-8232-1ab5d40af1c1
													- https://www.cockroachlabs.com/blog/what-is-connection-pooling/
												- [Suggested Project Structure](https://node-postgres.com/guides/project-structure) - `db/index.js`
												  id:: 63593ebb-9355-413a-933e-d474755febe0
													- Pros of using this standalone file
														- Allows my project to adjust to any changes to the node-postgres API without having to trace down all the places I directly use node-postgres in my application.
														- Allows me to have a single place to put logging and diagnostics around my database.
														- Allows me to make custom extensions to my database access code & share it throughout the project.
														- Allows a single place to bootstrap & configure the database.
													- Template
														- ```javascript
														  // Requiring pg module and destructuring out Pool
														  const { Pool } = require('pg');
														  
														  // Making a variable and storing in it a new instance of pool
														  const pool = new Pool({
														    // hand in connection URL from ElephantSQL as an environment variables
														    connectionString: process.env.POSTGRES_CONNECTION_URL,
														    
														  });
														  
														  // What we're making available to require into other files
														  module.exports = {
														    // query key in our export object
														    // value of the query key is a function
														    query: (text, params, callback) => { // note: passing callback is optional for this particular version
														      // text: SQL query
														      // params: parameterised queries (prepared statements)
														      return pool.query(text, params, callback); // note: passing callback is optional for this particular version
														    },
														  };
														  ```
														- Then if you want to import this into another file
														  ```javascript
														  const { query } = require('../db/index.js')
														  ```
														- Example module function
															- Example 1
																- ```javascript
																  async function getBooks() {
																    // Query the database and return all books
																    // Use query function required in
																    // Call query and hand it the SQL query as the first argument
																    // Grab what that query function gives us back
																    // Need to await!
																    const result = await query('SELECT * FROM books;');
																    const booksArray = result.rows;
																    return booksArray;
																  }
																  ```
															- Example 2
																- ```javascript
																  async function getBookById(id) {
																    // Query the database and return the book with a matching ID
																    	// query the books table with the book id
																    	// just bring back the specific row that matches that book id
																    // Use the query function that we've required in
																    // await!
																    // Collect what query returns in a variable (result)
																    // Return the relevant part of the result
																    const result = await query (`SELECT * FROM books WHERE id = $1`, [id]); // uses parameterised query for safety
																    console.log(result.rows);
																    const book = result.rows[0]; // 0 ensures you return an object, which is the first and only item of the array 'result.rows'
																    return book;
																  }
																  ```
																- ((63594b55-df8e-49b8-95c1-f3433e23c751))
																- `$1` is a reference to the first argument of the function in SQL
																	- `id = $1` is similar to JavaScript `${id}`
										- [node-postgres](https://www.npmjs.com/package/node-postgres)
										  id:: 63904f3c-fae7-41e9-870c-43837ab8f4e5
										  collapsed:: true
											- Related:
												- ((63bae0ae-2db2-4cf2-b923-755efe250d86))
												- ((63581a1a-5436-4e35-8c2c-549fcedbb430))
										- [uuid](https://www.npmjs.com/package/uuid)
										  id:: 634e85bc-bc2c-4c49-8e81-fdf2b8f3b4a7
										  Generate unique ids
										- [jest](https://www.npmjs.com/package/jest)
										  id:: 635eb08e-60ed-4881-9b34-a2a27b514521
										  collapsed:: true
										  Check your solutions with automated tests
											- [Documentation](https://jestjs.io/docs/getting-started)
												- Getting Started
													- How to setup Jest
													  id:: 63e26542-1164-4021-83d2-1e70a3ac6c09
													  collapsed:: true
														- Install [Jest](((635eb08e-60ed-4881-9b34-a2a27b514521)))
														  ```javascript
														  npm install --save-dev jest
														  ```
														- Add to `package.json` the script for Jest
															- CommonJS version
															  ```javascript
															  "scripts": {
															      "test": "jest"
															  ```
															- ESM version
															  ```javascript
															  "scripts": {
															      "test": "node --experimental-vm-modules node_modules/jest/bin/jest.js"
															  }
															  ```
														- Make sure to export your functions from their file to make it available to the test file e.g.
														  ```javascript
														  module.exports = sum;
														  ```
															- Related: ((635eb25f-8124-4d74-8c42-bfc5541ff543))
														- Create a test file for your tests e.g. `sum.test.js` to test your `sum.js` file
														- In the test file import your functions
															- ES Modules
																- ```javascript
																  import { test, expect, describe } from "@jest/globals"; // optional
																  ```
															- {Archive} CommonJS example
															  collapsed:: true
																- ```javascript
																  const sum = require('./sum');
																  ```
														- In the test file add your test
															- Example Jest test
																- Syntax
																  ```javascript
																  test(<string-to-describe-test>, () => {
																      expect(<our-named-function>(<test-parameters>).toBe(<expected-result>);
																  });
																  ```
																- Example file `sum.test.js`
																  ```javascript
																  test('adds 1 + 2 to equal 3', () => {
																    expect(sum(1, 2)).toBe(3);
																  });
																  ```
																	- Alternatively
																	  ```javascript
																	  test('adds 1 + 2 to equal 3', () => {
																	    const actual = sum(1, 2);
																	    const expected = 4;
																	    expect(sum(actual)).toBe(expected);
																	  });
																	  ```
														- Run `npm t` or `npm test` on the terminal
														- Optional
															- `import { test, expect } from "@jest/globals";`
																- Implicit globals don't need to be imported, but it helps learning by seeing where these functions are coming from
												- [Expect](https://jestjs.io/docs/expect)
												  collapsed:: true
													- Methods
														- [`expect(value)`](https://jestjs.io/docs/expect#expectvalue)
														- [`expect.extend(matchers)`](https://jestjs.io/docs/expect#expectextendmatchers)
														- [`expect.anything()`](https://jestjs.io/docs/expect#expectanything)
														- [`expect.any(constructor)`](https://jestjs.io/docs/expect#expectanyconstructor)
														- [`expect.arrayContaining(array)`](https://jestjs.io/docs/expect#expectarraycontainingarray)
														- [`expect.assertions(number)`](https://jestjs.io/docs/expect#expectassertionsnumber)
														- [`expect.closeTo(number, numDigits?)`](https://jestjs.io/docs/expect#expectclosetonumber-numdigits)
														- [`expect.hasAssertions()`](https://jestjs.io/docs/expect#expecthasassertions)
														- [`expect.not.arrayContaining(array)`](https://jestjs.io/docs/expect#expectnotarraycontainingarray)
														- [`expect.not.objectContaining(object)`](https://jestjs.io/docs/expect#expectnotobjectcontainingobject)
														- [`expect.not.stringContaining(string)`](https://jestjs.io/docs/expect#expectnotstringcontainingstring)
														- [`expect.not.stringMatching(string | regexp)`](https://jestjs.io/docs/expect#expectnotstringmatchingstring--regexp)
														- [`expect.objectContaining(object)`](https://jestjs.io/docs/expect#expectobjectcontainingobject)
														- [`expect.stringContaining(string)`](https://jestjs.io/docs/expect#expectstringcontainingstring)
														- [`expect.stringMatching(string | regexp)`](https://jestjs.io/docs/expect#expectstringmatchingstring--regexp)
														- [`expect.addSnapshotSerializer(serializer)`](https://jestjs.io/docs/expect#expectaddsnapshotserializerserializer)
														- [`.not`](https://jestjs.io/docs/expect#not)
														- [`.resolves`](https://jestjs.io/docs/expect#resolves)
														- [`.rejects`](https://jestjs.io/docs/expect#rejects)
														- [`.toBe(value)`](https://jestjs.io/docs/expect#tobevalue)
														- [`.toHaveBeenCalled()`](https://jestjs.io/docs/expect#tohavebeencalled)
														- [`.toHaveBeenCalledTimes(number)`](https://jestjs.io/docs/expect#tohavebeencalledtimesnumber)
														- [`.toHaveBeenCalledWith(arg1, arg2, ...)`](https://jestjs.io/docs/expect#tohavebeencalledwitharg1-arg2-)
														- [`.toHaveBeenLastCalledWith(arg1, arg2, ...)`](https://jestjs.io/docs/expect#tohavebeenlastcalledwitharg1-arg2-)
														- [`.toHaveBeenNthCalledWith(nthCall, arg1, arg2, ....)`](https://jestjs.io/docs/expect#tohavebeennthcalledwithnthcall-arg1-arg2-)
														- [`.toHaveReturned()`](https://jestjs.io/docs/expect#tohavereturned)
														- [`.toHaveReturnedTimes(number)`](https://jestjs.io/docs/expect#tohavereturnedtimesnumber)
														- [`.toHaveReturnedWith(value)`](https://jestjs.io/docs/expect#tohavereturnedwithvalue)
														- [`.toHaveLastReturnedWith(value)`](https://jestjs.io/docs/expect#tohavelastreturnedwithvalue)
														- [`.toHaveNthReturnedWith(nthCall, value)`](https://jestjs.io/docs/expect#tohaventhreturnedwithnthcall-value)
														- [`.toHaveLength(number)`](https://jestjs.io/docs/expect#tohavelengthnumber)
														- [`.toHaveProperty(keyPath, value?)`](https://jestjs.io/docs/expect#tohavepropertykeypath-value)
														- [`.toBeCloseTo(number, numDigits?)`](https://jestjs.io/docs/expect#tobeclosetonumber-numdigits)
														- [`.toBeDefined()`](https://jestjs.io/docs/expect#tobedefined)
														- [`.toBeFalsy()`](https://jestjs.io/docs/expect#tobefalsy)
														- [`.toBeGreaterThan(number | bigint)`](https://jestjs.io/docs/expect#tobegreaterthannumber--bigint)
														- [`.toBeGreaterThanOrEqual(number | bigint)`](https://jestjs.io/docs/expect#tobegreaterthanorequalnumber--bigint)
														- [`.toBeLessThan(number | bigint)`](https://jestjs.io/docs/expect#tobelessthannumber--bigint)
														- [`.toBeLessThanOrEqual(number | bigint)`](https://jestjs.io/docs/expect#tobelessthanorequalnumber--bigint)
														- [`.toBeInstanceOf(Class)`](https://jestjs.io/docs/expect#tobeinstanceofclass)
														- [`.toBeNull()`](https://jestjs.io/docs/expect#tobenull)
														- [`.toBeTruthy()`](https://jestjs.io/docs/expect#tobetruthy)
														- [`.toBeUndefined()`](https://jestjs.io/docs/expect#tobeundefined)
														- [`.toBeNaN()`](https://jestjs.io/docs/expect#tobenan)
														- [`.toContain(item)`](https://jestjs.io/docs/expect#tocontainitem)
														- [`.toContainEqual(item)`](https://jestjs.io/docs/expect#tocontainequalitem)
														- [`.toEqual(value)`](https://jestjs.io/docs/expect#toequalvalue)
														- [`.toMatch(regexp | string)`](https://jestjs.io/docs/expect#tomatchregexp--string)
														- [`.toMatchObject(object)`](https://jestjs.io/docs/expect#tomatchobjectobject)
														- [`.toMatchSnapshot(propertyMatchers?, hint?)`](https://jestjs.io/docs/expect#tomatchsnapshotpropertymatchers-hint)
														- [`.toMatchInlineSnapshot(propertyMatchers?, inlineSnapshot)`](https://jestjs.io/docs/expect#tomatchinlinesnapshotpropertymatchers-inlinesnapshot)
														- [`.toStrictEqual(value)`](https://jestjs.io/docs/expect#tostrictequalvalue)
														- [`.toThrow(error?)`](https://jestjs.io/docs/expect#tothrowerror)
														- [`.toThrowErrorMatchingSnapshot(hint?)`](https://jestjs.io/docs/expect#tothrowerrormatchingsnapshothint)
														- [`.toThrowErrorMatchingInlineSnapshot(inlineSnapshot)`](https://jestjs.io/docs/expect#tothrowerrormatchinginlinesnapshotinlinesnapshot)
												- [Using Matchers](https://jestjs.io/docs/using-matchers)
												  collapsed:: true
													- Common Matchers
														- `toBe`
														  collapsed:: true
														  Test primitives with exact equality
															- Example
															  ```javascript
															  test('two plus two is four', () => {
															    expect(2 + 2).toBe(4);
															  });
															  ```
														- `not.toBe`
														  collapsed:: true
														  Test primitives for not having exact equality
															- Example
															  ```javascript
															  test('adding positive numbers is not zero', () => {
															    for (let a = 1; a < 10; a++) {
															      for (let b = 1; b < 10; b++) {
															        expect(a + b).not.toBe(0);
															      }
															    }
															  });
															  ```
														- `toEqual`
														  collapsed:: true
														  Test objects to check the value of them
															- Example
															  ```javascript
															  test('object assignment', () => {
															    const data = {one: 1};
															    data['two'] = 2;
															    expect(data).toEqual({one: 1, two: 2});
															  });
															  ```
													- Truthiness
														- Examples of many tests
														  collapsed:: true
															- ```javascript
															  test('null', () => {
															    const n = null;
															    expect(n).toBeNull();
															    expect(n).toBeDefined();
															    expect(n).not.toBeUndefined();
															    expect(n).not.toBeTruthy();
															    expect(n).toBeFalsy();
															  });
															  
															  test('zero', () => {
															    const z = 0;
															    expect(z).not.toBeNull();
															    expect(z).toBeDefined();
															    expect(z).not.toBeUndefined();
															    expect(z).not.toBeTruthy();
															    expect(z).toBeFalsy();
															  });
															  ```
														- `toBeNull`
														  collapsed:: true
														  Matches only  `null`
															- Example
															  ```javascript
															  test('null', () => {
															    const n = null;
															    expect(n).toBeNull();
															  });
															  
															  test('zero', () => {
															    const z = 0;
															    expect(z).not.toBeNull();
															  });
															  ```
														- `toBeUndefined`
														  collapsed:: true
														  Matches only  `undefined`
															- Example
															  ```javascript
															  test('undefined', () => {
															    const n = undefined;
															    expect(n).toBeUndefined();
															  });
															  
															  test('zero', () => {
															    const z = 0;
															    expect(z).not.toBeUndefined();
															  });
															  ```
														- `toBeDefined`
														  collapsed:: true
														  Is the opposite of  `toBeUndefined`
															- Example
															  ```javascript
															  test('null', () => {
															    const n = null;
															    expect(n).toBeDefined();
															  });
															  
															  test('zero', () => {
															    const z = 0;
															    expect(z).toBeDefined();
															  });
															  ```
														- `toBeTruthy`
														  collapsed:: true
														  matches anything that an  `if`  statement treats as true
															- Example
															  ```javascript
															  test('one', () => {
															    const n = 1;
															    expect(n).toBeTruthy();
															  });
															  
															  test('zero', () => {
															    const z = 0;
															    expect(z).not.toBeTruthy();
															  });
															  ```
														- `toBeFalsy`
														  collapsed:: true
														  matches anything that an  `if`  statement treats as false
															- Example
															  ```javascript
															  test('one', () => {
															    const n = 1;
															    expect(n).not.toBeFalsy();
															  });
															  
															  test('zero', () => {
															    const z = 0;
															    expect(z).toBeFalsy();
															  });
															  ```
													- Numbers
													  collapsed:: true
														- Examples
															- ```javascript
															  test('two plus two', () => {
															    const value = 2 + 2;
															    expect(value).toBeGreaterThan(3);
															    expect(value).toBeGreaterThanOrEqual(3.5);
															    expect(value).toBeLessThan(5);
															    expect(value).toBeLessThanOrEqual(4.5);
															  
															    // toBe and toEqual are equivalent for numbers
															    expect(value).toBe(4);
															    expect(value).toEqual(4);
															  });
															  ```
														- For floating point equality, use toBeCloseTo instead of toEqual, because you don't want a test to depend on a tiny rounding error.
															- Example
															  ```javascript
															  test('adding floating point numbers', () => {
															    const value = 0.1 + 0.2;
															    //expect(value).toBe(0.3);           This won't work because of rounding error
															    expect(value).toBeCloseTo(0.3); // This works.
															  });
															  ```
															- What is floating point numbers
																- Decimals aren't exact numbers because they're made up of binary
																  ```javascript
																  let number = 0.1 + 0.2;
																  
																  // number = 0.30000004
																  ```
													- `toMatch` 
													  collapsed:: true
													  Strings checked against ((6345ae08-b3a7-40fb-bd6a-35c0918159e5))
														- Example
														  ```javascript
														  test('there is no I in team', () => {
														    expect('team').not.toMatch(/I/);
														  });
														  
														  test('but there is a "stop" in Christoph', () => {
														    expect('Christoph').toMatch(/stop/);
														  });
														  ```
													- `toContain`
													  collapsed:: true
													  Check if an array or iterable contains a particular item
														- Example
														  ```javascript
														  const shoppingList = [
														    'diapers',
														    'kleenex',
														    'trash bags',
														    'paper towels',
														    'milk',
														  ];
														  
														  test('the shopping list has milk on it', () => {
														    expect(shoppingList).toContain('milk');
														    expect(new Set(shoppingList)).toContain('milk');
														  });
														  ```
													- Exceptions
													  collapsed:: true
														- If you want to test whether a particular function throws an error when it's called, use  `toThrow` .
														- Example
														  ```javascript
														  function compileAndroidCode() {
														    throw new Error('you are using the wrong JDK!');
														  }
														  
														  test('compiling android goes as expected', () => {
														    expect(() => compileAndroidCode()).toThrow();
														    expect(() => compileAndroidCode()).toThrow(Error);
														  
														    // You can also use a string that must be contained in the error message or a regexp
														    expect(() => compileAndroidCode()).toThrow('you are using the wrong JDK');
														    expect(() => compileAndroidCode()).toThrow(/JDK/);
														  
														    // Or you can match an exact error mesage using a regexp like below
														    expect(() => compileAndroidCode()).toThrow(/^you are using the wrong JDK$/); // Test fails
														    expect(() => compileAndroidCode()).toThrow(/^you are using the wrong JDK!$/); // Test pass
														  });
														  ```
													- [Learning Resources]
														- https://jestjs.io/docs/expect
												- [`test` is an alias of `it`](https://jestjs.io/docs/api#testname-fn-timeout)
												- How to use with ((63e79f3b-c770-4212-be0c-3ba1860ea88a))
												  id:: 63e4cd45-0139-423a-aa13-050a0dc7f64c
													- Examples
														- 1 - using `render(<StateContextProvider value={{`
														  collapsed:: true
															- ```tsx
															  import { render, screen, fireEvent } from "@testing-library/react";
															  import { it, expect, describe } from "@jest/globals";
															  import {
															    exampleData,
															    StateContextProvider,
															    useStateContext,
															  } from "../context/StateContextProvider";
															  import Modal from "../components/Modal";
															  
															  describe("Modal", () => {
															    const searchResults = exampleData;
															  
															    it(`renders on the homepage`, () => {
															      render(
															        <StateContextProvider
															          value={{
															            searchResults,
															            setSearchResults: jest.fn(),
															            isOpen: true,
															            setIsOpen: jest.fn(),
															            modalIndex: 0,
															            setModalIndex: jest.fn(),
															          }}
															        >
															          <Modal />
															        </StateContextProvider>
															      );
															      const actual = screen.getByTestId("Modal");
															      expect(actual).toBeInTheDocument();
															    });
															  ```
														- 2 - using `jest.mock`
														  collapsed:: true
															- ```tsx
															  import React from "react";
															  import { render, fireEvent, screen } from "@testing-library/react";
															  import { useStateContext } from "../context/StateContextProvider";
															  import MyModal from "./MyModal";
															  
															  jest.mock("../context/StateContextProvider", () => ({
															    useStateContext: jest.fn().mockReturnValue({
															      searchResults: {
															        articles: [
															          {
															            title: "Sample title",
															            content: "Sample content",
															            url: "https://sample.url",
															          },
															        ],
															      },
															      setSearchResults: jest.fn(),
															      isOpen: true,
															      setIsOpen: jest.fn(),
															      modalIndex: 0,
															      setModalIndex: jest.fn(),
															    }),
															  }));
															  
															  describe("MyModal", () => {
															    it("renders correctly and closes the modal on clicking the close button", () => {
															      render(<MyModal />);
															  
															      expect(screen.getByTestId("Modal")).toBeInTheDocument();
															      expect(screen.getByText("Sample title")).toBeInTheDocument();
															      expect(screen.getByText("Sample content")).toBeInTheDocument();
															  
															      const closeModalButton = screen.getByText("Read Article");
															      fireEvent.click(closeModalButton);
															      expect(useStateContext().setIsOpen).toHaveBeenCalledWith(false);
															    });
															  });
															  ```
												- Reference
													- [`describe(name, fn)`](https://jestjs.io/docs/api#describename-fn)
													  collapsed:: true
													  Creates a block that groups together several related tests
														- Example
														  ```javascript
														  describe('my beverage', () => {
														    test('is delicious', () => {
														      expect(myBeverage.delicious).toBeTruthy();
														    });
														  
														    test('is not sour', () => {
														      expect(myBeverage.sour).toBeFalsy();
														    });
														  });
														  ```
														- Note: make sure to import it from via `@jest/globals` if using with react-testing-library, because their version of Jest doesn't have describe [[Nov 24th, 2022]]
													- `beforeEach`
													  id:: 636274fb-9051-4d4c-ad61-f30b71d5e5cb
													  collapsed:: true
														- https://stackoverflow.com/questions/57497799/what-is-the-purpose-of-beforeeach-global-in-jest
											- Related:
												- ((6374d432-af66-4f00-9de3-39fc99e03c51))
												- ((63e2667d-bffb-447c-9442-5802f293903d))
												- ((635fa5a5-76d1-4894-a44b-c3fdcfd9cd48))
										- [supertest](https://www.npmjs.com/package/supertest)
										  id:: 636275a3-1d1a-4c08-84ea-128a21fd3907
										  collapsed:: true
										  HTTP assertions made easy via [superagent](http://github.com/visionmedia/superagent).
											- The motivation with this module is to provide a high-level abstraction for testing HTTP, while still allowing you to drop down to the [lower-level API](https://visionmedia.github.io/superagent/) provided by superagent.
											- https://github.com/visionmedia/supertest
											- https://github.com/visionmedia/superagent
										- [nodemon](https://www.npmjs.com/package/nodemon)
										  id:: 634ff3c9-3f9a-4414-9c7d-0f20fa8ab3ae
										  auto restarts the server whenever you make changes to the API. Instead of having to close web server and start it every time to see changes
										- ((634bc0c1-71ec-40e0-ba94-bf79e177b591))
										  handle http requests and send responses
										- [puppeteer](https://www.npmjs.com/package/puppeteer)
										  id:: 637920f1-86d3-42b3-9dcd-7fd99ad01f12
										  collapsed:: true
										  ((6360e332-3615-46d4-b233-fee7e35bfbbd)) tool using Chromium DevTools
											- Working example
												- ```javascript
												  import puppeteer from 'puppeteer';
												  
												  (async () => {
												  // const browser = await puppeteer.launch();
												  	const browser = await puppeteer.launch({
												  		headless: true,
												  		args: [
												  		'--no-sandbox',
												  		'--disable-setuid-sandbox',
												  		]
												  	});
												    const page = await browser.newPage();
												  
												    await page.goto('[404  |  Page Not Found  |  Google Developers](https://developers.google.com/web/');)
												  
												    // Type into search box.
												    await page.type('.devsite-search-field', 'Headless Chrome');
												  
												    // Wait for suggest overlay to appear and click "show all results".
												    const allResultsSelector = '.devsite-suggest-all-results';
												    await page.waitForSelector(allResultsSelector);
												    await page.click(allResultsSelector);
												  
												    // Wait for the results page to load and display the results.
												    const resultsSelector = '.gsc-results .gs-title';
												    await page.waitForSelector(resultsSelector);
												  
												    // Extract the results from the page.
												    const links = await page.evaluate(resultsSelector => {
												      return [...document.querySelectorAll(resultsSelector)].map(anchor => {
												        const title = anchor.textContent.split('|')[0].trim();
												        return `${title} - ${anchor.href}`;
												      });
												    }, resultsSelector);
												  
												    // Print all the files.
												    console.log(links.join('\n'));
												  
												    await browser.close();
												  })();
												  ```
											- Testing sent HTTP headers
												- ```javascript
												  await page.goto('[404 Not Found](https://www.httpbin.org/headers');) 
												  const pageContent = await page.$eval('pre', node => JSON.parse(node.innerText)); 
												  const userAgent = await page.evaluate(() => navigator.userAgent); 
												  console.log({ headers: pageContent.headers, userAgent }); 
												  ```
											- Documentation
												- Commonly used
													- `console.log(await page.content());` = Print HTML
													-
										- [morgan](https://www.npmjs.com/package/morgan)
										  id:: 63512137-0fc0-4ea9-897e-cb92d4ffa8af
										  collapsed:: true
										  HTTP request logger middleware
											- Related: ((635120f8-f9c9-4815-b2ad-f3b8dca80405))
										- [npkill](https://www.npmjs.com/package/npkill)
										  id:: 6385d52b-dfbb-4c14-8d09-e05cd3f1ff7e
										  Easily delete large `node_modules` directories on your device
										- [bcrypt - npm](https://www.npmjs.com/package/bcrypt)
										  id:: 63888994-6553-4a68-97ab-ffd052af43f6
										  Hash passwords
									- Other packages
										- ((63a048ff-b45a-4636-af0a-339ae76bbf8f))
										  id:: 63baa386-f83a-429b-9d3b-402f31139e5d
										  collapsed:: true
										- [tailwindcss](https://www.npmjs.com/package/tailwindcss)
										  collapsed:: true
											- Pros/Cons
												- Pros
													- Instead of writing CSS, you add any number of predefined CSS classes to your HTML
													- [Separation of concerns is less important than dependency direction](https://adamwathan.me/css-utility-classes-and-separation-of-concerns/)
												- Cons
											- https://github.com/tailwindlabs/tailwindcss
											- https://tailwindcss.com/
											-
									- Related: ((64024e3e-17bd-46f7-b70d-41a02bf20981))
								- [Yarn](https://yarnpkg.com/)
								  id:: 63dbe34b-cf80-4fa6-8ca3-97425040ee87
								  collapsed:: true
									- ## Documentation
										- ### Commands
											- `yarn` is equivalent to `yarn install`
										- ### SOPs
											- Run `yarn install`/`npm install` at the top-level directory whenever you update the dependencies/devDependencies in a `package.json` (or at that level if you're not referencing another local package, whether it's in a workspace or not)
											- `yarn install` will create the `node_modules` dir (if you have PnP off), which should be in gitignore since Yarn instead relies on zips. `yarn`/`yarn install` is still needed for all modules to be detected for example
											- To edit Yarn dependencies for debugging purposes then note that if you're using Docker Containers the `node_modules` dir will be inside that. You'll want to combine this with `yarn link` rather than editing each dep dir directly to instead modify a copied dir.
										- Can choose to use either a global cache `~/.yarn/cache` or project-specific `.yarn/cache`
										- `.pnp` (plug-and-play) allows yarn to use the `cache` directly, rather than having to unzip to a `node_modules` directory per project. Uses zipFS to load packages into memory?
										- Workspaces
										  id:: 68d1c0cb-c0f2-41dc-875e-f61a2aeb6917
										  collapsed:: true
											- Key Benefits
											  Centralized dependency management: One yarn install for all projects.
											  Single lockfile: Consistent installs across your team.
											  Cross-referencing: Easily develop libraries and apps together.
											- let you manage multiple packages (projects) within a single monorepo, allowing for easier dependency management and cross-package linking
											- Top-level `package.json`
												- ```json
												  {
												  "name": "my-monorepo",
												  "private": true,
												  "workspaces": ["packages/*"]
												  }
												  ```
												- The `private: true` flag is required because workspaces are not intended to be published separately
											- Create Packages ("Workspaces")
												- ```
												  mkdir -p packages/app
												  mkdir -p packages/lib
												  ```
												- Initialise a `package.json` for each of them
													- ```
													  cd packages/app
													  yarn init -y
													  cd ../lib
													  yarn init -y
													  cd ../../
													  ```
											- Using Workspace commands
												- To run a script in a specific package
													- `yarn workspace <workspace-name> <script>`
													- `yarn workspace @my-monorepo/app start`
												- To run scripts across all workspaces use:
													- `yarn workspaces foreach run <script>`
											- Referencing Workspace Packages
												- In one package's package.json, you can use another workspace as a dependency:
													- ```
													  "dependencies": {
													  "@my-monorepo/lib": "1.0.0"
													  }
													  ```
													- Though I've seen it referenced in yume-chan's libraries using `"@my-monorepo/lib": "workspace:1.0.0"
											- Each workspace does not need a top-level `package.json` if you're instead importing the workspace as it's subdirectories e.g. `workspace1/folder1/*`
											- A pattern used I've seen is certain node modules are actually a symlink to another node package
											- Top-level `package.json` example
											  collapsed:: true
												- ```json
												  "workspaces": [
												    "packages/demo",
												    "packages/tabby-launcher",
												    "packages/ya-webadb/libraries/*",
												    "packages/ya-webadb/toolchain/*"
												  ]
												  ```
												- Where each direcotry in `libraries/` or `toolchain/` are yet more packages
												- This allows you to reference a `dependency` or `devDependency` any of the packages in these workspaces from another other package in these workspaces. You can reference each package by their `name` attribute in their `package.json`
													- ```
													  "dependencies": {
													  "adb-modified": "workspace:*",
													  "@yume-chan/async": "workspace:^1.0.0"
													  }
													  ```
												- Then to import within a JS file you can use the package name as a reference:
													- ```js
													  ```
												- To use each package as a module create a symlink in `node_modules` for that package
													- Example:
														- `mkdir -p node_modules/title`
														- `ln -s node_modules/title/package-title ../package-title`
											- `npm install`/`yarn install`/etc should be used at the *top-level* directory if you're using workspaces. It'll generate `node_modules` directories full of symlinks to your other packages if you've actually added them as dependencies/devDependencies in the `package.json` for that package
									- ## Troubleshooting
										- It looks for env vars prefixed with `YARN_` so this can affect the success of a build
										- [Yarn PnP](https://yarnpkg.com/features/pnp) stops `node_modules` folder being created
											- Remember that migrating to Yarn PnP is optional: you can revert to node_modules installs at any time by setting the `nodeLinker: node-modules` setting in your project's .yarnrc.yml file.
											- Note: if using a similar setup as WC remember that `node_modules` folder may only be visible within the Docker Container itself, or on-disk if using DevContainers (if PnP is disabled)
									- Installing Yarn offline
										- Obtain a `tgz` of Yarn
										- `sudo apt install node`
										- `corepack enable`
										- `corepack install -g yarn.tgz`
									- `install-state.gz` can be added to `.gitignore` as it's a Yarn web frontend build artefact. also `node_modules` if using Yarn
									-
								- [pnpm](https://pnpm.io/)
								  id:: 63dbe359-ea1b-4b45-9575-adf889c93c81
								  collapsed:: true
									- Pros
										- Unlike ((634bc0c1-c4b8-488f-9c11-5918d0bfb50d)) or ((63dbe34b-cf80-4fa6-8ca3-97425040ee87)), installing the same dependency in two different projects it'll only have 1 copy of the dep on your disk (similar to how Nix works). It uses hard and soft links
							- Related:
								- ((63baa386-e89b-4c6f-9dad-19586353252f)) : ((63baa386-3de1-4a21-b62e-a339148671de))
						- [NW.js](https://nwjs.io/)
						  id:: 6643619d-793b-47f3-9a0b-e95d09a46684
						  collapsed:: true
							- [GitHub - nwjs/nw.js: Call all Node.js modules directly from DOM/WebWorker and enable a new way of writing applications with all Web technologies.](https://github.com/nwjs/nw.js)
							- Projects
								- streamlink-twitch-gui
								  id:: 664361ab-752c-447e-9971-c0abfffba025
									- Streamlink Twitch GUI is an ((6643619d-793b-47f3-9a0b-e95d09a46684)) application, which means that it is a web application written in JavaScript ([EmberJS](http://emberjs.com/)), HTML ([Handlebars](http://handlebarsjs.com/)) and CSS ([LessCSS](http://lesscss.org/)) and is being run by a [Node.js](https://nodejs.org) powered version of [Chromium](https://www.chromium.org/).
									- Related: ((6643612d-d5c6-4b48-a998-7237e73d5adb))
						- Node-gyp
							- is a cross-platform command-line tool written in Node.js for compiling native addon modules for Node.js. Node-gyp is not used to build Node.js itself but is used to compile native addons, which are Node.js modules written in C or C++ and require compilation on the user's machine.
					- [Learning Resources]
						- https://roadmap.sh/questions/nodejs
						- ((634d2517-30eb-4bbf-b214-abae3ac1b92d))
				- [Deno](https://deno.land/)
				  id:: 63baa386-9946-4219-9c0b-e727cadf287d
				  collapsed:: true
					- Pros/Cons
						- Pros
							- Unlike ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) it's memory-safe (built in Rust + TypeScript vs C++)
							- Backwards-compatible with ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) + npm
							- 1.0 features
								- TypeScript support (later adopted by node.js too)
								- Better security model than node.js
								- Includes a `std` library (similar to [[Python]] with common utilities like datetime, expect (jest))
								- `deno compile` makes a cross-platform binary
							- 2.0 features
								- npm support
								- Jupyter kernel
							- JSR package manager support - every package supports both JS and TS
						- Cons
							- Less community support, so might not be maintained long-term if it fails
					- https://news.ycombinator.com/item?id=26620116
					- https://github.com/denoland
					- Background
						- Made by creator of ((629ccb26-3115-4d41-b4db-a686fe51a4a2))
						- Also built on V8 like Node
					- [Deno in 100 Seconds - YouTube](https://youtu.be/F0G9lZ7gecE)
						- Deno is aJavaScript runtime, similar to Node.js. Use it to develop secure server-side apps with built-in TypeScript support, ES modules, and promise-based APIs.
					- Setup
						- Deno VSCode extension
					- [Learning Resources]
						- [You don't need Node to use NPM packages - YouTube](https://youtu.be/cv7ci6GT5Hg)
						-
				- [Bun](https://bun.sh/)
					- https://news.ycombinator.com/item?id=37434117
				- [NestJS](https://nestjs.com/)
				  collapsed:: true
					- [NestJS in 100 Seconds - YouTube](https://www.youtube.com/watch?v=0M8AYU_hPas)
					- [Nest.js Crash Course #1 - Introduction & Setup - YouTube](https://www.youtube.com/watch?v=pcX97ZrTE6M)
					-
				- _JavaScript CMS_
				  id:: 629ccb26-512b-4462-9cb0-4527492e6ddb
				  collapsed:: true
					- ((646349df-5c24-45d6-a241-75f2cb033321))
					  collapsed:: true
					- https://apostrophecms.org/
					- https://www.contentful.com/
					- https://cosmicjs.com/
					- https://prismic.io/
					- {Archive}
					  collapsed:: true
						- https://www.lullabot.com/articles/will-javascript-eat-the-monolithic-cms
						-
					- Related: ((635fba72-d8b2-4372-b1f9-ce7a107f2df7))
				- [Lit](https://lit.dev/)
				  collapsed:: true
					- Polymer abandoned, they recommend Lit instead
					  collapsed:: true
						- [Polymer](https://www.polymer-project.org/)
						  collapsed:: true
		- Libraries
			- Multer is a good package for uploading files eg photos to a backend
			  id:: 6497eb6b-de77-424c-b138-ec9d3ff79efa
			  collapsed:: true
				- Hi all, we’re trying to work out the best way of getting and storing user uploaded images which will be associated with user profiles and events that users are creating. So far we’ve investigated using Multer on the backend, to store on disk, and then save the data url as a string which is what will go up to our database. We’re a little hazy on implementation and we haven’t been able to find anything that pins down best practice here, as most guides are uploading the whole image to the database which we are trying to avoid due to the file sizes.
				  
				  Is anyone else looking at storing user uploaded images and have any resources or tips to share?
				- https://www.npmjs.com/package/multer
				- AWS S3
			- Password protecting and encrypting files on a website [Password protect a static HTML page | Hacker News](https://news.ycombinator.com/item?id=34849024)
			- [Block Protocol](https://blockprotocol.org/)
			- [Mock Service Worker](https://mswjs.io/) - seamless API mocking
			- [Three.js – JavaScript 3D Library](https://threejs.org)
			  collapsed:: true
				- [three.js examples](https://threejs.org/examples/#webgl_animation_keyframes)
			- [Show HN: Tabulator – Easy-to-use JavaScript library for interactive tables | Hacker News](https://news.ycombinator.com/item?id=18568072)
			- Airtable alternative in JS
			  collapsed:: true
				- See Handsontable in WorkFlowy
				- [React Datasheet Component](https://nadbm.github.io/react-datasheet/)
				- [react-virtualized (js table](https://bvaughn.github.io/react-virtualized/#/components/Table)
				- [Espalier | uses Handsontable for spreadsheet component](http://sdg.csail.mit.edu/projects/espalier). More info https://news.ycombinator.com/item?id=12576093
			- JSDoc - An API documentation generator for JavaScript. http://usejsdoc.org
			- Audio
			  collapsed:: true
				- [GitHub - goldfire/howler.js: Javascript audio library for the modern web.](https://github.com/goldfire/howler.js)
				-
			- [GitHub - clickvote/clickvote: Add upvotes, likes, and reviews to any context ⭐️](https://github.com/clickvote/clickvote)
			-
	- Tooling
	  id:: 63904f3c-e689-458b-a036-672778a7e77c
	  collapsed:: true
	  AKA Toolchain
		- Toolchain
		  id:: 67376786-85a0-4cc4-a8a5-02311ac19c20
			- All-in-one
			  collapsed:: true
				- *Webpack-based*
					- ((636a77ab-fbaf-4088-8f12-12f334ce25b7))
				- Comparisons
					- ((63a048ff-b45a-4636-af0a-339ae76bbf8f)) vs ((636a77ab-fbaf-4088-8f12-12f334ce25b7))
					  id:: 63a04903-cab3-45f4-9a0a-1451cf558f49
					  collapsed:: true
						- [Learning Resources]
							- [Vite 3.0 vs. Create React App - LogRocket Blog](https://blog.logrocket.com/vite-3-vs-create-react-app-comparison-migration-guide/)
							- [Use Vite for React Apps instead of CRA - DEV Community 👩‍💻👨‍💻](https://dev.to/nilanth/use-vite-for-react-apps-instead-of-cra-3pkg)
							- [create-react-app or vite for new project? : reactjs](https://teddit.pussthecat.org/r/reactjs/comments/yuxa16/createreactapp_or_vite_for_new_project/)
							-
				- [Vite](https://vitejs.dev/)
				  id:: 63a048ff-b45a-4636-af0a-339ae76bbf8f
				  collapsed:: true
					- Notably uses
						- ((63dbe84e-9cc6-4e20-9977-8a62bc3d6502)) as compiler
						- ((63dbe84b-71cf-44b7-aecd-b6650b6dd9d5)) as
						- ((63baa386-a21f-43f8-942a-ed439b515f32)) as bundler
					- [Learning Resources]
						- [Vite Crash Course | Faster Alternative To CRA - YouTube](https://youtu.be/89NJdbYTgJ8#)
						  collapsed:: true
							- {{video https://youtu.be/89NJdbYTgJ8}}
			- ((629ccb26-3115-4d41-b4db-a686fe51a4a2)) : ((63baa386-4747-40e9-b222-ab1fb5ab1bf6))
			  id:: 63dbdafa-6dcc-450f-8253-0fa668ed2b8a
			  What - lets you install, update, and manage third-party packages
			- Build/task runners
			  collapsed:: true
				- **Typical examples:**
					- Gulp
					- Grunt
					- [Turborepo](https://turbo.build/repo)
					  id:: 63a32f3c-88b8-482c-88d1-0e83b0706b88
					  collapsed:: true
						- Pros
							- Can be used to manage infinitely large monorepos
						- Related: ((63a32c57-5e6a-4a2a-b8dd-48ae0c0897d4))
					- [Nx](https://nx.dev/)
					  id:: 63dbe535-1504-4fc1-82d4-752f5cf485d3
					  collapsed:: true
						- Pros
							- Can be used to manage infinitely large monorepos
				- These are not exactly build tools in and of themselves; they're rather just used to glue together _other_ tools. For example, if you have a set of build steps where you need to run tool A after tool B, a build runner can help to orchestrate those tools.
				- [Learning Resources]
					- Monorepos
					  collapsed:: true
						- [Monorepos - How the Pros Scale Huge Software Projects // Turborepo vs Nx - YouTube](https://youtu.be/9iU_IE6vnJ8)
						- Monorepo at Google
							- They have custom tooling so that people only git clone parts of the repo (they don't use git modules)
							- Advantages
								- Library teams automatically run the tests of all the app teams to ensure that updating the library won't break anything
								- Encourages app teams to make comprehensive tests so that library updates don't cause breakages
								- Ensures that almost if not all software at any point in time will always work with the latest versions of libraries
							-
			- Bundlers
			  collapsed:: true
			  id:: 63904f3c-fa48-4c42-bb6c-4ccd2958ced9
				- Summary
				  collapsed:: true
					- Lets you write modular code and bundle it together into small packages to optimize load time.
					- ..
					- These tools take a bunch of .js files that use [modules](https://nodejs.org/api/modules.html) (either CommonJS using require() statements, or ES Modules using import statements), and combine them into a _single_ .js file. Some of them also allow specifying 'transformation steps', but their main purpose is bundling.
					- Why does bundling matter? While in Node.js you have access to a module system that lets you load files as-needed from disk, this wouldn't be practical in a browser; fetching every file individually over the network would be very slow. That's why people use a bundler, which effectively does all this work upfront, and then produces a single 'combined' file with all the same guarantees of a module system, but that can be used in a browser.
					- Bundlers can also be useful for running module-using code in very basic JS environments that don't have module support for some reason; this includes Google Sheets, extensions for PostgreSQL, GNOME, and so on.
					- **Bundlers are _not_ transpilers.** They do not compile one language to another, and they don't "make ES6 work everywhere". Those are the job of a _transpiler_. Bundlers are sometimes configured to _use_ a transpiler, but the transpiling itself isn't done by the bundler.
					- **Bundlers are _not_ task runners.** This is an especially popular misconception around Webpack. Webpack does _not_ replace task runners like Gulp; while Gulp is designed to glue together arbitrary build tasks, Webpack is specifically designed for _browser bundles_. It's commonly useful to use Webpack _with_ Gulp or another task runner.
				- *Typical examples:*
					- [Turbopack](https://turbo.build/pack)
					  id:: 63a32c57-5e6a-4a2a-b8dd-48ae0c0897d4
					  collapsed:: true
						- Rust-based successor to JavaScript-based ((63a048fa-1fc4-47d8-b62f-bfe5fcab704a))
						- Uses ((63a32dac-2cbb-4d2c-9006-1a3bb86aede2)) to transpile code before bundling it
						- Related: ((63a32f3c-88b8-482c-88d1-0e83b0706b88))
					- [Webpack](https://webpack.js.org/)
					  id:: 63a048fa-1fc4-47d8-b62f-bfe5fcab704a
					- [Parcel](https://parceljs.org/)
					- [esbuild](https://esbuild.github.io/)
					  id:: 63dbe84b-71cf-44b7-aecd-b6650b6dd9d5
					- [Rollup](https://rollupjs.org/)
					  id:: 63baa386-a21f-43f8-942a-ed439b515f32
					- [Browserify](https://browserify.org/)
				- Related: ((6396fb64-9aeb-4ee3-bf46-849eac2fb748)) : ((6396fb64-f1fa-498a-ac4f-242eed1e3dff))
			- Compilers
			  collapsed:: true
				- A **compiler** lets you compile modern language features and additional syntax like JSX or type annotations for the browsers. Popular compilers: [Babel](https://babeljs.io/), [TypeScript](https://www.typescriptlang.org/), [swc.](https://swc.rs/)
				- Examples
					- [swc](https://swc.rs/)
					  id:: 63dbe84e-9cc6-4e20-9977-8a62bc3d6502
					  collapsed:: true
						- Rust-based, notably faster than ((63de287a-692e-401f-b43f-d9221ce8c90f))
					- [Babel](https://babeljs.io/)
					  id:: 63de287a-692e-401f-b43f-d9221ce8c90f
			- Transpilers
			  collapsed:: true
				- **Typical examples:**
					- Babel
					- the TypeScript compiler
					- CoffeeScript
					- swc
					  id:: 63a32dac-2cbb-4d2c-9006-1a3bb86aede2
					- Terser
				- These tools take a bunch of code in one language, and 'compile' it to another language. They're called commonly 'transpilers' rather than 'compilers' because unlike traditional compilers, these tools don't compile to a lower-level representation; they're just different languages at a similar level of abstraction.
				- These are typically used to run code written against newer JS versions in older JS runtimes (eg. Babel), or to provide custom languages with more conveniences or constraints that can then be executed in any regular JS environment (TypeScript, CoffeeScript).
			- Process restarters
			  collapsed:: true
				- **Typical examples:** nodemon
				- These tools automatically restart your (Node.js) process when the underlying code is changed. This is used for development purposes, to remove the need to manually restart your process every change.
				- A process restarter may either watch for file changes itself, or be controlled by an external tool like a build runner.
			- Page reloaders
			  collapsed:: true
				- **Typical examples:** LiveReload, BrowserSync, Webpack hot-reload
				- These tools automatically refresh a page in the browser and/or reload stylesheets and/or re-render parts of the page, to reflect the changes in your _browser-side_ code. They're kind of the equivalent of a process restarter, but for webpages.
				- These tools are usually externally controlled; typically by either a build runner or a bundler, or both.
			- Debuggers
			  collapsed:: true
				- **Typical examples:** Chrome Developer Tools, node-inspect
				- These tools allow you to inspect _running_ code; in Node.js, in your browser, or both. Typically they'll support things like pausing execution, stepping through function calls manually, inspecting variables, profiling memory allocations and CPU usage, viewing execution logs, and so on.
				- They're typically used to find tricky bugs. It's a good idea to learn how these tools work, but often it'll still be easier to find a bug by just 'dumb logging' variables throughout your code using eg. console.log.
			- Test runners
			  id:: 63e2667d-bffb-447c-9442-5802f293903d
			  collapsed:: true
				- A **test runner** lets you run tests against your code. Popular test runners: [Jest.](https://jestjs.io/)
				- Examples
					- ((635eb08e-60ed-4881-9b34-a2a27b514521))
					- ((6360f2aa-b95c-4675-b0c4-493f0b7f8ae5))
					- ((6374d432-af66-4f00-9de3-39fc99e03c51))
					- ((636275a3-1d1a-4c08-84ea-128a21fd3907))
				- Categories
					- ## Unit Tests
						- ((67376792-bca2-4dbb-afd4-1dcf58a96cc3))
					- ## Integration Tests
					- ## End-to-End Tests
						- Robot Framework
						  collapsed:: true
						  Automation framework
							- Works with Python, .NET and Java
							- Parallel test support can be achieved by using Selenium Grid
						- TestProject Framework
						  collapsed:: true
						  Automation framework
							- Supports Pytest and Unittest frameworks
							- Requires support for parallel testing as it only runs one test at a time (slow)
							-
				- [Learning Resources]
					- Contract Testing
					  collapsed:: true
						- [1](https://snoo.habedieeh.re/r/aws/comments/ao3vgx/thoughts_on_localstack_local_testing/efzl61l/?context=3)
							- Don't try to mock AWS, design your code to be more modular, so you can test your code, and not AWS (or even an generic AWS mock).
							- See [Clean Code](https://medium.com/@eminetto/clean-architecture-using-golang-b63587aa5e3f) and/or Hexagonal Architecture. Also learn about Contract Testing.
							- The idea is that AWS or your Database have a _massive_ API. You are only using 1% of that, so why worry about it?
							  Instead, write a "thin" access layer for those systems. Each "type" of API call should have it's own function, and it should ONLY take normal objects (not specific to AWS/DB). Don't try to make these functions generic -- hard-code _everything_ that doesn't need to change in your program.
							- So instead of \`LaunchBox(...lots-of-stuff...)\`, you have \`LaunchReportBox(name, environment, owner, disk\_size) (id)\`. And instead of \`FindCustomer(name) (db\_object)\`, you have \`FindCustomer(name) (specific\_fields)\`. Yes, this means you have to have to "duplicate" structures, but it also makes it trivial to test and mock.
							- Then you run your code against AWS or the DB _once_ and store the responses as a contract. When you run your tests, it just returns that contract data. You only need to involve AWS when you are writing a new AWS accessor function, which shouldn't happen that often.
							- Or, taking a step back: End-To-End tests that involve the entire system are expensive. You should maybe do 1 small "happy path" test, but everything else should be Unit tests that don't need an external system.
					- [Testcontainers](https://testcontainers.com/)
						- Testcontainers is a fanatstic way to write the most important tests (arguably) for your app. Don't test E2E with a mock, just use a real database.
				- Related:
					- ((646349f6-d814-4277-ae6d-8a2d143c7e09))
					- ((635fa5a5-76d1-4894-a44b-c3fdcfd9cd48))
			- Validation
			  collapsed:: true
				- [Zod](https://zod.dev/)
				  id:: 63a2e8dc-8f33-4a71-aad2-dacbb1b4128f
				  collapsed:: true
					- Pros/Cons
						- Pros
							-
					- recommended by Ben Freemantle
					  id:: 63a2e8e0-86a4-4130-8169-75aa824b11c3
						- like schema validation
						- so when you define types, you can add zod validation to it for example like
						- ```
						  type person = {
						    age: z.number.min(0).max(130)
						  }
						  ```
						- i think is the syntax
						- so its type of number, with validation of it cant be less than 0 or greater than 130 built into the type
						- seems pretty handy for quickly writing types
						- and with tRPC it, they use zod built into as well
						  so your api comes pre typed
						  so when you use it on the frontend you have those types available for you to consume
						  without needing something like an sdk
					- [Learning Resources]
						- [Zod Makes TypeScript Even Better - YouTube](https://youtu.be/9UVPk0Ulm6U)
							- {{video https://youtu.be/9UVPk0Ulm6U}}
								- {{youtube-timestamp 112}} How to setup
									- `nom install zod`
									- `import { z } from 'zod';`
								- {{youtube-timestamp 197}} Zod's big notable feature
								- {{youtube-timestamp 319}} Demo - it's more concise in Zod than doing if/else statements for error checking
								-
						- [Learn Zod In 30 Minutes - YouTube](https://youtu.be/L6BE-U3oy80)
						  collapsed:: true
							- {{video https://youtu.be/L6BE-U3oy80}}
							-
			- Code formatters
			  id:: 63dbe268-004a-42e8-ad9f-c31ff0a05f90
			  collapsed:: true
				- Code Formatters
					- Remembering all the rules about code formatting can be taxing so thats where code formatters can help!
					- Code formatters automatically format code for you depending on the preferences you set. Automatic formatting enables higher code quality, especially when you are working in teams and other people are reading the code you’ve written. Many developers maintain standards of code formatting like 2-space or 4-space indentation or using single or double quotes. This helps with both readability and finding errors.
					- Two examples of code formatters are Prettier, which is used to keep your coding style consistent and ESLint, which helps detect formatting issues and find inconsistencies in your code.
					- Installation and setup guides for Prettier and ESLint:
						- Prettier Configuration:
						  https://www.digitalocean.com/community/tutorials/code-formatting-with-prettier-in-visual-studio-code
						- ESLint Configuration:
						  [https://eslint.org/docs/user-guide/getting-started](https://eslint.org/docs/user-guide/getting-started)
					- Using both of these tools together can be a very effective way to maintain high quality code but may cause conflict. The following guide will help you successfully intergrate both tools succesfully.
					  https://prettier.io/docs/en/integrating-with-linters.html
				- [Prettier](https://prettier.io)
				  id:: 63dc1965-e60c-418a-b045-991a2def0768
					- Comparisons
						- Prettier formats documents and just moves characters and whitespace, whereas ESLint is what does stuff like removes unused imports
					- Metadata
						- Name: Prettier - Code formatter
						  Id: esbenp.prettier-vscode
						  Description: Code formatter using prettier
						  Version: 9.10.4
						  Publisher: Prettier
						  VS Marketplace Link: [Prettier - Code formatter - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
					- [VSCode extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
					  id:: 63dc1b89-0a11-40e1-9db2-3380b2da19e8
					- Documentation
						- [How To Setup Prettier - YouTube](https://youtu.be/DqfQ4DPnRqI)
						  collapsed:: true
							- *Either*
								- `npm i -D prettier`
									- `npx prettier --write script.js` = format the file named `script.js`
								- ((63dc1b89-0a11-40e1-9db2-3380b2da19e8))
									- VSCode settings
										- `Editor: Default formatter` = Prettier
										- `Editor: Format on save` = enable
							- *Project-specific settings*
								- Create a `.prettierignore` file (similar to `.gitignore`) to prevent `node_modules/` from being formatted if using `npx prettier --write .`
								- Create `.prettierrc` as a custom Prettier config file
									- e.g.
									  ```json
									  {
									    "semi": true, 
									    "overrides": [ 
									      {
									        "files": "legacy/*", 
									        "options": { 
									          "semi": false
									        }
									    ]
									  }
									  ```
						- Disable in a workspace
						  id:: 660d7476-50d4-4ec0-ad40-0d0cbc7dcfb9
						  collapsed:: true
							- `touch .prettierignore`
							  Create a `.prettierignore` file
							- `nano .prettierignore`
							  Update the file
								- ```
								  # This will ignore all files
								  *
								  
								  # This will ignore a specific file
								  src/index.js
								  ```
						- Example `.prettierrc`
							- ```json
							  {
							  "printWidth": 80,
							  "tabWidth": 2,
							  "semi": true,
							  "endOfLine": "lf"
							  }
							  ```
						- `.prettierignore` can include/exclude subdirectories like so:
							- ```
							  web-frontend/packages/ya-webadb/*
							  !web-frontend/packages/ya-webadb/libraries/
							  web-frontend/packages/ya-webadb/libraries/*
							  !web-frontend/packages/ya-webadb/libraries/adb-gnirehtet/
							  !web-frontend/packages/ya-webadb/libraries/pcm-streamer/
							  ```
						- To run Prettier recursively over a target directory
						  collapsed:: true
							- Something like `yarn run /path/to/prettier/binary --write /path/to/directory`
						- VSCode how to save a file but not activate Prettier formatting on save
							- `CTRL + K`, then `CTRL + SHIFT + S`
						- How we executed Prettier across multiple Yarn workspaces
							- `yarn workspace demo exec prettier ../.. --config ../../../.prettierrc.yml --ignore-path ../../../.prettierignore --write`
			- Linter
			  collapsed:: true
				- A **linter** checks your code for common mistakes.
					- Code linting is a type of static analysis that is frequently used to find problematic patterns or code that doesn’t adhere to certain style guidelines. There are code linters for most programming languages, and compilers sometimes incorporate linting into the compilation process.
					- JavaScript, being a dynamic and loosely-typed language, is especially prone to developer error. Without the benefit of a compilation process, JavaScript code is typically executed in order to find syntax or other errors. Linting tools like ESLint allow developers to discover problems with their JavaScript code without executing it.
				- Examples
					- [ESLint](https://eslint.org/)
					  id:: 63dc17ea-92e0-4539-82ab-c666e686c832
					  collapsed:: true
						- [VSCode extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
			- [Learning Resources]
				- You may prefer to create and configure your own toolchain. A toolchain typically consists of:
				- A **minifier** makes your code more compact so that it loads faster. Popular minifiers: [Terser](https://terser.org/), [swc.](https://swc.rs/)
				- A **server** handles server requests so that you can render components to HTML. Popular servers: [Express.](https://expressjs.com/)
		- Misc utility
			- [JS Benchmark](https://jsbenchmark.com/)
			  collapsed:: true
			  more easily compare the performance of JS snippets and packages
				- https://github.com/jsbenchmark
				- Related: https://jsperf.app/
		- Related: [[Programming]] : ((6396fb64-ade6-48f7-a7f0-10b006cab400))
- # Applications/Usecases
	- ((634ae34a-1409-46ff-ace7-6fac429027b0))
	  id:: 63470fd0-de33-469e-b839-998545237069
	- _Potential projects_
	  collapsed:: true
		- _Portfolio primarily_
			- WorkFlowy/Dynalist userscript that shows data in a table view
			- WorkFlowy userscript to allow code syntax highlighting (based off of Powerpack for Dynalist)
			  collapsed:: true
				- Powerpack 2
				  https://talk.dynalist.io/t/powerpack-2/977/172
				- Powerpack 3
				  https://talk.dynalist.io/t/powerpack-3/2744
			- Firefox WebExtensions that I use
			  collapsed:: true
				- Memex by WorldBrain
				  https://workflowy.com/#/7c4066396b5a
				- Bookmark Tab
			- Website built in Bootstrap
			- Website built in ((646349df-5c24-45d6-a241-75f2cb033321))
			- React Dapp which pulls some blockchain data or smart contract
			- Small JavaScript game engine games
			- React app that will work well with Filecoin API (or Sia API for now?)
	- See [JavaScript-based games](((629ccb26-efd3-4584-aaa7-8c8bcc02034e)))
	- See dApps
		- [Crypto gaming Dapps](((629ccb25-31b7-4b77-8db8-c84628ecc4c2)))
	- Scripting
	  id:: 65cd3f2d-1087-4801-a05d-2065925ef994
	  collapsed:: true
		- https://github.com/google/zx
		  collapsed:: true
		- https://github.com/dsherret/dax
			- https://david.deno.dev/posts/dax-node-js/
		- https://bun.sh/blog/the-bun-shell
		- Related: [[Programming]] : ((65cd3f7c-24c9-4260-b67c-2fe5f005e6a2))
- # SOPs
	- Basic web project setup steps
	  id:: 67cc4979-5215-4fa5-b1f4-87825bf9f5d4
	  collapsed:: true
		- `npm init` = setup a Node project
		- `npm install express` = setup Express as webserver
		- Create an `index.js` as entrypoint file
			- `node index.js` to execute it
		- Add template express code in the index.js
		- HTML file for each webpage, or just `index.html`
		- `<script>` for all JS code
			- Can either use `src` attribute to point to a separate JavaScript file
				- `<script src="/static/player.js"></script>`
			- Or embed all the JS code in the script section
	- Related: ((634ae34a-1409-46ff-ace7-6fac429027b0)) : ((6737678f-ec7e-49b7-b52e-0ca6c7bcefa3))
- # [Learning Resources]
  collapsed:: true
	- **FOSS**
		- ((63471098-0b67-4cfc-a402-f5595cd1c583)) - how does it work offline?
	- **General Learning** - JavaScript
		- Books
		  id:: 663a5792-4ea2-4a2b-85cb-eb161e1b38c4
		  collapsed:: true
			- You Don't Know JavaScript Yet series (2nd edition) by Kyle Simpson
			  id:: 62a0d2df-fa7f-40a6-81ef-928c8dd743d8
				- Meta
					- Upcoming drafts being [completed here](https://github.com/getify/You-Dont-Know-JS), already following the [Kickstarter RSS](https://www.kickstarter.com/projects/getify/you-dont-know-js-yet-second-edition-books/posts) for updates
				- [[calibre/You Don't Know JS Yet: Get Started - Kyle Simpson (2022)]]
				  logseq.order-list-type:: number
				- [[calibre/You Don't Know JS Yet: Scope & Closures - Kyle Simpson (2022)]]
				  logseq.order-list-type:: number
				- Related: ((629ccb26-ef1d-47b6-a890-d6be1548a7f5))
			- You Don't Know JavaScript series (1st edition) by Kyle Simpson
			  id:: 629ccb26-ef1d-47b6-a890-d6be1548a7f5
				- Up & Going
				  logseq.order-list-type:: number
				  collapsed:: true
					- **TO DO**
						- Read through EPUB and make highlights and notes
						- Copy those annotations into Anki desktop flashcards (use anki-airtable?)
							- https://github.com/sirupsen/anki-airtable
							- Or other
								- https://ankiapp.freshdesk.com/support/solutions/articles/5000051548-can-i-import-decks-from-spreadsheets-tsv-csv-
								- https://www.lengthytravel.com/create-anki-deck-google-sheets-spreadsheet/
								- https://ankiweb.net/shared/info/2012433609
						- Study those flashcards periodically
					- Notes
						- Supplemental material (code examples, exercises, etc.) is available for download at http://bit.ly/ydkjs-up-going-code
				- Scope & Closures
				  logseq.order-list-type:: number
				- this & Object Prototypes
				  logseq.order-list-type:: number
				- Types & Grammar
				  logseq.order-list-type:: number
				- Assync & Performance
				  logseq.order-list-type:: number
				- ES6 & Beyond
				  logseq.order-list-type:: number
				- Related: ((62a0d2df-fa7f-40a6-81ef-928c8dd743d8))
			- Eloquent Javascript by Marijn Haverbeke [ATHENAEUM]
				- http://eloquentjavascript.net/
			- JavaScript: The Missing Manual 1st Edition by David Sawyer McFarland
			- JavaScript: The Good Parts by Douglas Crockford
			- Secrets of the JavaScript Ninja by John Resig (Author), Bear Bibeault (Author), Josip Maras (Author)
			  collapsed:: true
				- https://www.amazon.com/Secrets-JavaScript-Ninja-John-Resig/dp/1617292850/
		- Coding challenge platforms (it's like Duolingo for learning to code)
		  id:: 629ccb26-cd51-4251-b88f-61771199d1e4
		  collapsed:: true
			- https://codefights.com/
			- https://edabit.com/challenges
			- http://exercism.io/languages/javascript/about
			- Grasshopper
			  https://play.google.com/store/apps/details?id=com.area120.grasshopper&hl=en
			- [CodeWars](https://www.codewars.com)
			  id:: 629ccb26-051d-46ed-910d-bd6d0e0af723
			- https://www.coderbyte.com/
			- https://www.codingame.com/start
			- _Intermediate/Advanced_
				- [Leetcode](https://leetcode.com/)
				  id:: 629ccb26-6ecf-41ff-b479-f404b7eddbe0
				  collapsed:: true
					- Pros/Cons
						- Pros
							-
						- Cons
							- https://news.ycombinator.com/item?id=31677736
						- Unclear
						- Comparisons
							- ((629ccb26-6ecf-41ff-b479-f404b7eddbe0)) vs [[CodeWars - JavaScript]]
								- For ((629ccb26-6ecf-41ff-b479-f404b7eddbe0))
									- Leetcode generally has questions more geared towards what companies are actually asking, so it's better for interview prep
								- For  [[CodeWars - JavaScript]]
									- Gamified
									- Lots of easier questions available, great for beginners
					- Why companies want it
						- startups want people who can hit the ground running. They need to put out a product as quickly as possible and they don't have the time/money to wait several months for a new hire to learn a new area before they become productive. So they don't care about Leetcode
							- At big tech it's the opposite [so they look for Leetcode skills], they assume that as long as you have fundamental engineering skills you can learn whatever is necessary for the job, and they can afford to wait. Also, many big tech companies have very customized internal tools and frameworks, so outside knowledge of a particular tech stack provides only minor benefit.
					- My notes
					  id:: 66ba02cb-27c7-4d56-8b9b-5e140d59cbf1
						- [[LeetCode - JavaScript]]
						- [[LeetCode - Python]]
					- Ecosystem
						- [VSCode extension - LeetCode](https://marketplace.visualstudio.com/items?itemName=LeetCode.vscode-leetcode)
					- [Learning Resources]
						- [Grind 75](https://www.techinterviewhandbook.org/grind75) (v2 of ((64bcadf7-2fb0-4d59-89a7-7b565d18560b)) )
						  collapsed:: true
							- *Array*
								- *Easy*
									- [Two Sum](https://leetcode.com/problems/two-sum/description)
									  id:: 0e542595-2f6d-4864-9ff5-9f953ccd7a29
									  collapsed:: true
										- My solution
											- ```javascript
											  /**
											   * @param {number[]} nums
											   * @param {number} target
											   * @return {number[]}
											   */
											  var twoSum = function(nums, target) {
											      for (let i = 0; i < nums.length; i++) {
											          for (let j = i + 1; j < nums.length; j++) {
											              if (nums[i] + nums[j] === target) {
											                  return [i, j]
											              }
											          }
											      }
											  };
											  ```
										- Best practice - [Solutions](https://leetcode.com/problems/two-sum/solutions/127810/two-sum/)
											- Approach 1: Brute Force
											  collapsed:: true
												- Cons
													- Succeeds the first test cases, but fails the ones where they use huge integers
												- ```javascript
												  var twoSum = function(nums, target) {
												      for (let j = 0; j < nums.length; j++) {
												          for (let i = j + 1; i < nums.length; i++) {
												              console.log(`j: ${j} and i: ${i} and target: ${target}`)
												              if (nums[j] === target - nums[i]) {
												                  return [j, i]
												              }
												          }
												      }
												      return null
												  };
												  ```
											- Approach 2: Two-pass Hash Table
												- ```javascript
												  var twoSum = function(nums, target) {
												      // create a new Map
												      let map = new Map();
												      // loop over the nums
												      for (let i = 0; i < nums.length; i++) {
												        // store the complement between current num and the target
												  	  // if target 10, and num[i] = 6 there is only ONE number that we can add to 6 to make it 10. 
												          // That is the number 4. We call it the complement because it complements 6 to hit the target 10.
												          // EG if target = 10 and nums[i] = 6....  10 - 6 = complement = 4
												          let complement = target - nums[i];
												          // What we are going to do is check if the complement exists in the hashmap.
												          // If the map already contains the complement we will return an array with the index of the complieent. And current index.
												          // When calling map.get(complement) in the return, this will return the VALUE at that key 
												          if (map.has(complement)) {
												             return [map.get(complement), i];
												          } else {
												            // Since the complement does not exist as a key in the map.
												            // We store the key num[i], and index as the value for that key.
												            map.set(nums[i] , i)
												          }
												      }
												      // If there is no complement we will return an empty array. 
												  return [];
												  };
												  ```
													- ((63904f3d-96c1-429e-af8b-4a46b1bf89c5))
													- ((63904f3d-6b67-461e-bf92-5f55bc24fa36))
												- ```javascript
												  var twoSum = function(nums, target) {
												      let map = new Map();
												      for(let i = 0; i < nums.length; i ++) {
												          if(map.has(target - nums[i])) {
												              return [map.get(target - nums[i]), i];
												          } else {
												              map.set(nums[i], i);
												          }
												      }
												  	return [];
												  };
												  ```
												- One-pass Hash Table
												  ```javascript
												  var twoSum = function(nums, target) {
												      const indices = new Map();
												      for (let index = 0; index < nums.length; index++) {
												          const complement = target - nums[index];
												          if (indices.has(complement)) {
												              return [indices.get(complement), index]
												          }
												          indices.set(nums[index], index)
												      }
												  };
												  ```
									- [Best Time to Buy and Sell Stock ](https://leetcode.com/problems/best-time-to-buy-and-sell-stock)
									  collapsed:: true
										- My solution
											- ```javascript
											  ```
										- Best practice
											- ```javascript
											  ```
									- [Contains Duplicate](https://leetcode.com/problems/contains-duplicate)
									  id:: 63f3d7d0-a1ab-4f21-8ce8-fa4ae7aed53d
									- [Majority Element](https://leetcode.com/problems/majority-element)
								- *Medium*
									- [Insert Interval](https://leetcode.com/problems/insert-interval)
									- [3Sum](https://leetcode.com/problems/3sum)
									- [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self)
									- [Combination Sum](https://leetcode.com/problems/combination-sum)
									- [Merge Intervals](https://leetcode.com/problems/merge-intervals)
									- [Sort Colors](https://leetcode.com/problems/sort-colors)
									- [Container With Most Water](https://leetcode.com/problems/container-with-most-water)
							- *String*
							  collapsed:: true
								- *Easy*
									- [Valid Palindrome](https://leetcode.com/problems/valid-palindrome)
									- [Valid Anagram](https://leetcode.com/problems/valid-anagram)
									- [Longest Palindrome](https://leetcode.com/problems/longest-palindrome)
								- *Medium*
									- [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters)
									- [Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring)
									- [String to Integer (atoi)](https://leetcode.com/problems/string-to-integer-atoi)
									- [Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string)
								- *Hard*
									- [Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring)
							- *Matrix - Medium*
							  collapsed:: true
								- [Spiral Matrix](https://leetcode.com/problems/spiral-matrix)
							- *Graph*
							  collapsed:: true
								- *Easy*
									- [Flood Fill](https://leetcode.com/problems/flood-fill)
								- *Medium*
									- [01 Matrix](https://leetcode.com/problems/01-matrix)
									- [Clone Graph](https://leetcode.com/problems/clone-graph)
									- [Course Schedule](https://leetcode.com/problems/course-schedule)
									- [Number of Islands](https://leetcode.com/problems/number-of-islands)
									- [Rotting Oranges](https://leetcode.com/problems/rotting-oranges)
									- [Accounts Merge](https://leetcode.com/problems/accounts-merge)
									- [Word Search](https://leetcode.com/problems/word-search)
									- [Minimum Height Trees](https://leetcode.com/problems/minimum-height-trees)
								- *Hard*
									- [Word Ladder](https://leetcode.com/problems/word-ladder)
							- *Binary - Easy*
							  collapsed:: true
								- [Add Binary](https://leetcode.com/problems/add-binary)
							- *Binary Search*
							  collapsed:: true
								- *Easy*
									- [Binary Search](https://leetcode.com/problems/binary-search)
									- [First Bad Version](https://leetcode.com/problems/first-bad-version)
								- *Medium*
									- [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array)
									- [Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store)
								- *Hard*
									- [Maximum Profit in Job Scheduling](https://leetcode.com/problems/maximum-profit-in-job-scheduling)
							- *Binary Search Tree*
							  collapsed:: true
								- *Easy*
									- [Lowest Common Ancestor of a Binary Search Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree)
								- *Medium*
									- [Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree)
									- [Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst)
							- *Binary Tree*
							  collapsed:: true
								- *Easy*
									- [Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree)
									- [Balanced Binary Tree](https://leetcode.com/problems/balanced-binary-tree)
									- [Diameter of Binary Tree](https://leetcode.com/problems/diameter-of-binary-tree)
									- [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree)
								- *Medium*
									- [Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal)
									- [Lowest Common Ancestor of a Binary Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree)
									- [Binary Tree Right Side View](https://leetcode.com/problems/binary-tree-right-side-view)
									- [Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal)
								- *Hard*
									- [Serialize and Deserialize Binary Tree](https://leetcode.com/problems/serialize-and-deserialize-binary-tree)
							- *Hash Table - Easy*
							  collapsed:: true
								- [Ransom Note](https://leetcode.com/problems/ransom-note)
							- *Recursion - Medium*
							  collapsed:: true
								- [Permutations](https://leetcode.com/problems/permutations)
								- [Subsets](https://leetcode.com/problems/subsets)
								- [Letter Combinations of a Phone Number](https://leetcode.com/problems/letter-combinations-of-a-phone-number)
							- *Linked List*
							  collapsed:: true
								- *Easy*
									- [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists)
									- [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle)
									- [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list)
									- [Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list)
								- *Medium*
									- [LRU Cache](https://leetcode.com/problems/lru-cache)
							- *Stack*
							  collapsed:: true
								- *Easy*
									- [Valid Parentheses](https://leetcode.com/problems/valid-parentheses)
									- [Implement Queue using Stacks](https://leetcode.com/problems/implement-queue-using-stacks)
								- *Medium*
									- [Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation)
									- [Min Stack](https://leetcode.com/problems/min-stack)
								- *Hard*
									- [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water)
									- [Basic Calculator](https://leetcode.com/problems/basic-calculator)
									- [Largest Rectangle in Histogram](https://leetcode.com/problems/largest-rectangle-in-histogram)
							- *Heap*
							  collapsed:: true
								- *Medium*
									- [K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin)
									- [Task Scheduler](https://leetcode.com/problems/task-scheduler)
								- *Hard*
									- [Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream)
									- [Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists)
							- *Trie - Medium*
							  collapsed:: true
								- [Implement Trie (Prefix Tree)](https://leetcode.com/problems/implement-trie-prefix-tree)
								- [Word Break](https://leetcode.com/problems/word-break)
							- *Dynamic Programming*
							  collapsed:: true
								- *Easy*
									- [Climbing Stairs](https://leetcode.com/problems/climbing-stairs)
								- *Medium*
									- [Maximum Subarray](https://leetcode.com/problems/maximum-subarray)
									- [Coin Change](https://leetcode.com/problems/coin-change)
									- [Partition Equal Subset Sum](https://leetcode.com/problems/partition-equal-subset-sum)
									- [Unique Paths](https://leetcode.com/problems/unique-paths)
						- [Blind 75](https://leetcode.com/discuss/general-discussion/460599/blind-75-leetcode-questions)
						  id:: 64bcadf7-2fb0-4d59-89a7-7b565d18560b
						  collapsed:: true
							- [Best practice questions by the author of Blind 75 | Tech Interview Handbook](https://www.techinterviewhandbook.org/best-practice-questions/)
							- [LeetCode 75 - Study Plan - LeetCode](https://leetcode.com/study-plan/leetcode-75/)
							- [Blind 75 Leetcode problems : Detailed Video Solutions](https://takeuforward.org/interviews/blind-75-leetcode-problems-detailed-video-solutions/)
							- [Blind 75](https://leetcode.com/discuss/general-discussion/460599/blind-75-leetcode-questions)
							  collapsed:: true
								- ### Array
								- [Two Sum](https://leetcode.com/problems/two-sum/)
								- [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)
								- [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)
								- [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)
								- [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)
								- [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)
								- [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)
								- [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)
								- [3 Sum](https://leetcode.com/problems/3sum/)
								- [Container With Most Water](https://leetcode.com/problems/container-with-most-water/)
								  
								  ---
								- ### Binary
								- [Sum of Two Integers](https://leetcode.com/problems/sum-of-two-integers/)
								- [Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)
								- [Counting Bits](https://leetcode.com/problems/counting-bits/)
								- [Missing Number](https://leetcode.com/problems/missing-number/)
								- [Reverse Bits](https://leetcode.com/problems/reverse-bits/)
								  
								  ---
								- ### Dynamic Programming
								- [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/)
								- [Coin Change](https://leetcode.com/problems/coin-change/)
								- [Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/)
								- [Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/)
								- [Word Break Problem](https://leetcode.com/problems/word-break/)
								- [Combination Sum](https://leetcode.com/problems/combination-sum-iv/)
								- [House Robber](https://leetcode.com/problems/house-robber/)
								- [House Robber II](https://leetcode.com/problems/house-robber-ii/)
								- [Decode Ways](https://leetcode.com/problems/decode-ways/)
								- [Unique Paths](https://leetcode.com/problems/unique-paths/)
								- [Jump Game](https://leetcode.com/problems/jump-game/)
								  
								  ---
								- ### Graph
								- [Clone Graph](https://leetcode.com/problems/clone-graph/)
								- [Course Schedule](https://leetcode.com/problems/course-schedule/)
								- [Pacific Atlantic Water Flow](https://leetcode.com/problems/pacific-atlantic-water-flow/)
								- [Number of Islands](https://leetcode.com/problems/number-of-islands/)
								- [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)
								- [Alien Dictionary (Leetcode Premium)](https://leetcode.com/problems/alien-dictionary/)
								- [Graph Valid Tree (Leetcode Premium)](https://leetcode.com/problems/graph-valid-tree/)
								- [Number of Connected Components in an Undirected Graph (Leetcode Premium)](https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/)
								  
								  ---
								- ### Interval
								- [Insert Interval](https://leetcode.com/problems/insert-interval/)
								- [Merge Intervals](https://leetcode.com/problems/merge-intervals/)
								- [Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/)
								- [Meeting Rooms (Leetcode Premium)](https://leetcode.com/problems/meeting-rooms/)
								- [Meeting Rooms II (Leetcode Premium)](https://leetcode.com/problems/meeting-rooms-ii/)
								  
								  ---
								- ### Linked List
								- [Reverse a Linked List](https://leetcode.com/problems/reverse-linked-list/)
								- [Detect Cycle in a Linked List](https://leetcode.com/problems/linked-list-cycle/)
								- [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
								- [Merge K Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)
								- [Remove Nth Node From End Of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)
								- [Reorder List](https://leetcode.com/problems/reorder-list/)
								  
								  ---
								- ### Matrix
								- [Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/)
								- [Spiral Matrix](https://leetcode.com/problems/spiral-matrix/)
								- [Rotate Image](https://leetcode.com/problems/rotate-image/)
								- [Word Search](https://leetcode.com/problems/word-search/)
								  
								  ---
								- ### String
								- [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
								- [Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/)
								- [Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/)
								- [Valid Anagram](https://leetcode.com/problems/valid-anagram/)
								- [Group Anagrams](https://leetcode.com/problems/group-anagrams/)
								- [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)
								- [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)
								- [Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)
								- [Palindromic Substrings](https://leetcode.com/problems/palindromic-substrings/)
								- [Encode and Decode Strings (Leetcode Premium)](https://leetcode.com/problems/encode-and-decode-strings/)
								  
								  ---
								- ### Tree
								- [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)
								- [Same Tree](https://leetcode.com/problems/same-tree/)
								- [Invert/Flip Binary Tree](https://leetcode.com/problems/invert-binary-tree/)
								- [Binary Tree Maximum Path Sum](https://leetcode.com/problems/binary-tree-maximum-path-sum/)
								- [Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/)
								- [Serialize and Deserialize Binary Tree](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/)
								- [Subtree of Another Tree](https://leetcode.com/problems/subtree-of-another-tree/)
								- [Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)
								- [Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree/)
								- [Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/)
								- [Lowest Common Ancestor of BST](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)
								- [Implement Trie (Prefix Tree)](https://leetcode.com/problems/implement-trie-prefix-tree/)
								- [Add and Search Word](https://leetcode.com/problems/add-and-search-word-data-structure-design/)
								- [Word Search II](https://leetcode.com/problems/word-search-ii/)
								  
								  ---
								- ### Heap
								- [Merge K Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)
								- [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)
								- [Find Median from Data Stream](https://leetcode.com/problems/find-median-from-data-stream/)
						- [LeetCode - Top Interview Questions - Easy Collection](https://leetcode.com/explore/featured/card/top-interview-questions-easy/)
						  collapsed:: true
							- *Array*
								- [Remove Duplicates from Sorted Array](https://leetcode.com/explore/featured/card/top-interview-questions-easy/92/array/727/)
								  collapsed:: true
									- My solution
										- ```javascript
										  var removeDuplicates = function(nums) {
										      
										      nums.forEach((el, ind) => {
										          if (nums.indexOf(el) !== nums.lastIndexOf(el)) {
										              nums.splice(el, 1)
										          }
										      })
										      console.log(`nums:`, nums)
										      return nums.length
										  };
										  ```
									- Best practice
										- ```javascript
										  var removeDuplicates = function (nums) {
										      var i = 0;
										      nums.forEach(el => {
										          if (el !== nums[i]) {
										              nums[++i] = el;
										          }
										      });
										      return nums.length && i + 1;
										  };
										  ```
											- Explanation 1
												- ```javascript
												  var removeDuplicates = function (nums) {
												      var i = 0;
												      nums.forEach(function (elem) { // iterate over each element of the nums array
												          if (elem !== nums[i]) { // if elem is not the same as the previous element
												              nums[++i] = elem; // add elem to the array and then increment i to point to the next index after setting elem
												          }
												      });
												      return nums.length && i + 1;  // if nums is empty, return 0, otherwise return i + 1
												  };
												  ```
											- Explanation 2
												- ((635eb08f-9a44-4545-88c0-b7064e94f590)) because the algorithm has to be done in-place - no creation of additional arrays
												- `i` was incremented for every new unique element
												- `return nums.length && i + 1`
													- The expression `nums.length && i + 1` in this function returns the length of the modified array if it is not empty (has at least one element) and `i + 1` otherwise.
													- The `&&` operator in JavaScript is known as the logical AND operator. It returns the first operand if it is falsy, and the second operand otherwise. In this case, `nums.length` is the first operand and `i + 1` is the second operand. If `nums.length` is 0 (which is a falsy value), the expression returns 0, indicating that the array is empty. Otherwise, if `nums.length` is not 0, the expression returns `i + 1`, which is the length of the modified array with duplicates removed.
													- This way, if the input array is empty, the function will return 0, and if there are any elements in the array, it will return the length of the modified array.
										- ```javascript
										  var removeDuplicates = function(nums) {
										      let pointer = 0;    
										      for (let i = 0; i < nums.length; i++) {
										          if (nums[i] !== nums[i+1]) {
										              nums[pointer] = nums[i];
										              pointer++;
										          }
										      }
										      return pointer;
										  };
										  ```
								- [Best Time to Buy and Sell Stock II](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/564/)
								  collapsed:: true
									- My solution
										- ```javascript
										  var maxProfit = function(prices) {
										      let profit = 0
										      let prev
										      prices.reduce((acc, val, ind, arr) => {
										        // reduce starts with index 1 unlike other methods, so first need to set value of `prev` as otherwise the 0th index item is unassigned
										          if (!prev) {
										              prev = arr[ind-1]
										          }
										        // if next item is higher value than previous, then the profit is the difference
										          if (val > prev) {
										              profit += val - prev
										          }
										          prev = val // set `prev` to the current value
										      })
										          
										      return profit 
										  };
										  ```
											- Note: not using `acc` here. Probably should be swapped for `profit`
											- Similar "Implementation based on O(1) aux space"
												- ```javascript
												  var maxProfit = function(prices) {
												      let profitFromPriceGain = 0;
												      for( let i = 0 ; i < prices.length-1 ; i++ ){
												          if( prices[i] < prices[i+1] ){
												              profitFromPriceGain += (prices[i+1] - prices[i]);
												          }
												      }
												      return profitFromPriceGain;
												  }
												  ```
											- ((6350374d-3846-414b-a27e-7d32b86eec86))
									- Best practice
										- [O(n) sol by DP + state machine. Bottom-up DP + iteration](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/564/discuss/803206/PythonJSJavaGoC++-O(n)-by-DP-Greedy-+-Visualization)
											- ```javascript
											  var maxProfit = function(prices) {
											      // It is impossible to sell stock on first day, set -infinity as initial value for curHold
											      let [curHold, curNotHold] = [-Infinity, 0];
											      
											      for(const stockPrice of prices){
											          let [prevHold, prevNotHold] = [curHold, curNotHold];
											          // either keep hold, or buy in stock today at stock price
											          curHold = Math.max(prevHold, prevNotHold - stockPrice );
											          // either keep not-hold, or sell out stock today at stock price
											          curNotHold = Math.max(prevNotHold, prevHold + stockPrice );
											      }
											      // Max profit must come from notHold state finally.
											      return curNotHold; 
											  };
											  ```
								- [Rotate Array](https://leetcode.com/explore/interview/card/top-interview-questions-easy/92/array/646/)
								  collapsed:: true
									- My solution
										- ```javascript
										  var rotate = function(nums, k) {
										  	k = k % nums.length
										      nums.unshift(...nums.splice(-k));
										  };
										  ```
										- Wrong solution
											- Doesn't work if `k` > `nums.length`
												- ```javascript
												  var rotate = function(nums, k) {
												  	nums.unshift(...nums.splice(nums.length - k))
												  };
												  ```
											- Using immutable method not mutable
												- ```javascript
												  /**
												   * @param {number[]} nums
												   * @param {number} k
												   * @return {void} Do not return anything, modify nums in-place instead.
												   */
												  var rotate = function(nums, k) {
												      let arr1 = nums.slice(nums.length - k) 
												      console.log(`arr1:`, arr1)
												      let arr2 = nums.slice(0, nums.length - k)
												      console.log(`arr2:`, arr2)
												      return [...arr1, ...arr2]
												  };
												  ```
									- Best practice
										- ```javascript
										  var rotate = function (nums, k) {
										    for (let i = nums.length - 1; i >= 0; i--) {
										      nums[i + k] = nums[i];
										    }
										  
										    for (let j = k - 1; j >= 0; j--) {
										      nums[j] = nums.pop();
										    }
										  
										    // Time comlexity = O(a + b)
										  };
										  ```
											- Explanation 1
											  collapsed:: true
												- ```javascript
												  var rotate = function (nums, k) {
												    // i.e. nums = [1, 2, 3, 4, 5, 6, 7],  k = 3
												    for (let i = nums.length - 1; i >= 0; i--) {
												      nums[i + k] = nums[i];
												      // i = 6,  k = 3
												      // nums[i + k] = nums[i]
												      // nums[6 + 3] = nums[6]
												      // nums[9] = 7              nums = [1, 2, 3, 4, 5, 6, 7, , , 7]
												  
												      // i = 5,  k = 3
												      // nums[i + k] = nums[i]
												      // nums[5 + 3] = nums[5]
												      // nums[8] = 6              nums = [1, 2, 3, 4, 5, 6, 7, , 6, 7]
												  
												      // i = 4,  k = 3
												      // nums[i + k] = nums[i]
												      // nums[4 + 3] = nums[4]
												      // nums[7] = 5              nums = [1, 2, 3, 4, 5, 6, 7, 5, 6, 7]
												  
												      // i = 3,  k = 3
												      // nums[i + k] = nums[i]
												      // nums[3 + 3] = nums[3]
												      // nums[6] = 4              nums = [1, 2, 3, 4, 5, 6, 4, 5, 6, 7]
												  
												      // i = 2,  k = 3
												      // nums[i + k] = nums[i]
												      // nums[2 + 3] = nums[2]
												      // nums[5] = 3              nums = [1, 2, 3, 4, 5, 3, 4, 5, 6, 7]
												  
												      // i = 1,  k = 3
												      // nums[i + k] = nums[i]
												      // nums[1 + 3] = nums[1]
												      // nums[4] = 2              nums = [1, 2, 3, 4, 2, 3, 4, 5, 6, 7]
												  
												      // i = 0,  k = 3
												      // nums[i + k] = nums[i]
												      // nums[0 + 3] = nums[0]
												      // nums[3] = 1              nums = [1, 2, 3, 1, 2, 3, 4, 5, 6, 7]
												    }
												  
												    for (let j = k - 1; j >= 0; j--) {
												      // nums = [1, 2, 3, 1, 2, 3, 4, 5, 6, 7]
												      nums[j] = nums.pop();
												  
												      // j = 2
												      // nums[j] = nums.pop()
												      // nums[2] = 7               nums = [1, 2, 7, 1, 2, 3, 4, 5, 6]
												  
												      // j = 1
												      // nums[j] = nums.pop()
												      // nums[1] = 6               nums = [1, 6, 7, 1, 2, 3, 4, 5]
												  
												      // j = 0
												      // nums[j] = nums.pop()
												      // nums[0] = 5               nums = [5, 6, 7, 1, 2, 3, 4]
												    }
												  
												    // nums = [5, 6, 7, 1, 2, 3, 4]
												  
												    // Time comlexity = O(a + b)
												  };
												  ```
										- ```javascript
										  var rotate = function (nums, k) {
										      const len = nums.length
										      k = (k % len)
										      
										      let end = nums.splice(len - k)
										  
										      nums.splice(0,0,...end)
										  };
										  ```
								- ((63f3d7d0-a1ab-4f21-8ce8-fa4ae7aed53d))
								- ((0e542595-2f6d-4864-9ff5-9f953ccd7a29))
							- *Strings*
							- Linked List
							- Trees
							- Sorting and Searching
							- Dynamic Programming
							- Design
							- Math
							- Others
						- [Study cheatsheet from Grind 75 site](https://www.techinterviewhandbook.org/algorithms/study-cheatsheet/)
				- https://www.hackerrank.com/
				- https://www.topcoder.com/challenges/
				- https://www.codechef.com/
				- https://www.geeksforgeeks.org/
				- http://codeforces.com/
				- https://codingbat.com/
				- Firecode.io
				- Codesignal
				- ((663a58ee-f572-4e68-9a9c-474fddf637c4))
				- Edabit
				- Exercism
				- [GitHub - Lootcode-Dev/lootcode: A fantasy-themed, gamified, DSA problem practice platform to help you ace the technical interview.](https://github.com/Lootcode-Dev/lootcode)
			- https://www.reddit.com/r/dailyprogrammer
		- [Udacity](((629ccb25-bcc7-4291-837d-00682c64cd28)))
		- [freeCodeCamp](((629ccb25-3ea5-4bc3-84fd-050077003522)))
		- Become a Front End Developer nanodegree - free course modules - free modules via Udacity
		- Lynda: Programming Foundations courses
		- https://plainjs.com/javascript/ - how to do functions in vanilla JS that are normally done in jQuery
		- [JavaScript in 14 minutes by Jeremy Thomas](https://jgthms.com/javascript-in-14-minutes/)
		- How to Learn JavaScript Properly by JavaScriptIsSexy
		  http://javascriptissexy.com/how-to-learn-javascript-and-become-an-employable-programmer
		  collapsed:: true
			- Old post
			  http://javascriptissexy.com/how-to-learn-javascript-properly/
				- Resources:
					- — [Beginning JavaScript (4th Edition)](http://www.amazon.com/gp/product/0470525932/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=0470525932&linkCode=as2&tag=interhaptic-20&linkId=DMQK6I7WC6V34B77)
					- — JavaScriptIsSexy.com (4 articles)
					- — Codecademy.com (4 tracks)
					- — CodeSchool.com (1 short course)
		- Fullstack Academy's recommended free resources (sorted by Beginner to Advanced)
		  https://www.fullstackacademy.com/blog/learn-javascript-for-free-11-online-tutorials-resources 
		  collapsed:: true
			- Beginner
				- Codecademy’s JavaScript Track
				  http://www.codecademy.com/en/tracks/javascript
				  collapsed:: true
					- If 0 is a pure beginner and 100 is a professional full-stack developer, 15-20 hours of Codecademy’s JavaScript track will take you all the way to 6.8. In all seriousness, Codecademy’s step-by-step tutorial system is great for an introduction to programming in JavaScript. You will learn functions, loops, data structures and many other data types. They also have other online courses for many other languages like CSS, HTML, SQL and PYTHON.
				- Treehouse’s JavaScript Foundations
				  http://teamtreehouse.com/library/javascript-foundations
				  collapsed:: true
					- It’s not technically free, but Treehouse offers a multi-platform learning experience that includes videos, coding tutorials and quizzes. If you’re looking to gain a solid foundation in a short amount of time, the 14-day free trial might suit your needs in becoming a web developer. The benefits of this course will help you understand where JavaScript is used, basic concepts for variables, data types and conditional statements, and how to troubleshoot programming problems.
				- Udacity’s JavaScript Basics
				  collapsed:: true
					- Udacity uses videos and tutorials like the previous two resources, but also has the advantage of a relevant final project. Udacity users will create an interactive resume using the skills they’ve learned, which not only teaches you how to code, but could land you a job in any field. They also offer a Nanodegree which is an online learning credential program.
				- MDN JavaScript
				  https://developer.mozilla.org/en-US/docs/Web/JavaScript
				  collapsed:: true
					- Published by Mozilla, this site incorporates tutorials and lessons in addition to a glossary of JavaScript functions. This could be a good tab to have open next time you’re attempting those codewars.com challenges. MDN JavaScript is offered in many other languages and it's a great refresher of the JavaScript programming language. For non-expert programmers, you can use JavaScript Garden to avoid common mistakes and bugs.
				- Learn JS
				  http://www.learn-js.org/
				  collapsed:: true
					- Learn-JS.org is intended for everyone who wishes to learn the JavaScript programming language. This website is an interactive JavaScript tutorial where you can run free JavaScript code directly from the web browser. You are able to try JavaScript without even installing it. Here you can learn the basics, take advance tutorials or help others to learn by contributing with tutorials.
				- Khan Academy
				  https://www.khanacademy.org/computing/computer-programming/html-js-jquery#jquery-dom-access
				  collapsed:: true
					- This a non-profit organization that wants to provide a free, world-class code education to everyone. Khan Academy is a good learning platform where you can find tutorials not only for computer programming but for other subjects like math, arts, economics and finance. They have a JavaScript tutorial that can help you work with DOM events with jQuery, used for making animations and effects on a webpage. As their motto states, "You can learn anything. For free. For everyone. Forever."
			- Intermediate
				- Fullstack Academy's Bootcamp Prep Online
				  https://start.fullstackacademy.com/fullstack-academy-bootcamp-prep-at-your-own-pace 
				  collapsed:: true
					- This workshop-based video course has 40 hours of content and teaches all the fundamentals of JavaScript. Besides instruction on core concepts, it also reviews a large number of coding challenges, which are arranged by level of increasing difficulty, and each is followed by an instructor tutorial.  If you are searching for some advanced tutorials, Bootcamp Prep is a more demanding course for those who really are committed to attending to Fullstack Academy or other elite coding schools.
				- CoderByte
				  http://coderbyte.com/
				  collapsed:: true
					- CoderByte challenges are an excellent resource, especially if you want to apply to a more selective coding bootcamp as part of a career transition. These coding problems are a pretty accurate representation of the challenges on the Fullstack application’s technical coding assessment. Keep in mind that the beginner-level challenges are still pretty hard. If you find these too difficult, review the beginner resources listed above or consider attending an in-person coding class.
				- Eloquent JavaScript by Marijn Haverbeke
				  collapsed:: true
					- Intermediate level programmers will benefit from the first four chapters of this book, which include an overview of JavaScript syntax, functionality, loops and arrays and last but not least atoms of the data structures (numbers, booleans and strings).
					- The rest of the chapters are for advanced programmers where you can find more about HTTP and Forms, the difference between POST and GET requests, and Node.js, which is a back-end JavaScript technology that executes code server-side.
			- Intermediate/Advanced
				- Scotch.io
				  https://scotch.io/ 
				  collapsed:: true
					- Scotch.io is a blog that provides educational tutorials for programmers of all levels. This is a great resource for intermediate and advanced students who are looking to increase their knowledge of the MEAN stack and other emerging JavaScript technologies. It touches on Angular.js (web application framework for front-end development maintained by Google) and the jQuery library ("Learn jQuery for total noobs").
				- Egghead.io
				  https://egghead.io/
				  collapsed:: true
					- To paraphrase this website’s slogan: Life’s too short for any of those other resources on the internet — just watch these videos! Egghead offers short videos for proficient JavaScript developers to level-up their skills. Receive access to a decent number of lessons for free, or sign up for a paid subscription and get all the knowledge you can handle.
				- Douglas Crockford Videos
				  https://www.youtube.com/playlist?list=PL7664379246A246CB
				  collapsed:: true
					- Learn JavaScript from one of the language’s foremost pioneers. While a Hawaiian-shirted employee at Yahoo, Douglas Crockford created this lecture series on the creation, rise to popularity and implementation of JavaScript. These presentations are not only informative, but entertaining and anecdotal, too.
		- Web dev general
		  https://boards.4channel.org/g/catalog
		  collapsed:: true
			- >
			- [Full Web Development Roadmap](https://github.com/kamranahmedse/developer-roadmap)
			- Free beginner resources to get started with HTML, CSS and JavaScript
			- https://developer.mozilla.org/en-US/docs/Learn - a good starting point to learn about web dev fundamentals
			- https://javascript.info/ - quite a good JS tutorial according to many posts
			- https://www.freecodecamp.org - curriculum including HTML/CSS/JS, React, Node.js, Express, and MongoDB
			- [Your Career in Web Development Starts Here | The Odin Project](https://www.theodinproject.com) - curriculum including HTML/CSS/JS, Ruby on Rails, and SQL
			  id:: 64024e3e-a577-4332-943b-5427a406cb7b
			- https://fullstackopen.com/en/ - requires you to have basic web dev, db and git knowledge
			- [[Videogames]] : ((6370ba73-3874-4ffe-980c-64541990ee2f))
			- https://flexboxfroggy.com/ and https://codepip.com/games/grid-garden/ - learn flex/grid in CSS
			  id:: 634bc0c1-96ea-4c84-b1ad-0a4893439a2b
			-
			- >List of PHP resources
			- https://ghostbin.com/paste/sNdM3
			-
			- >List of design resources
			- https://ghostbin.com/paste/rTwHe
			-
			- >All useful documentation in one place
			- https://devdocs.io
			-
			- >Need help? Create an example and post the link
			- https://jsfiddle.net - if you need help with HTML/CSS/JS
			- https://3v4l.org - if you need help with PHP/HackLang
			- https://codesandbox.io - if you need help with React/Angular/Vue
		- More resources
		  collapsed:: true
			- [2017 Frontend Developer Handbook](https://github.com/FrontendMasters/front-end-handbook-2017/blob/master/SUMMARY.md)
			- Here is my list of really good resources to learn the language:
			  collapsed:: true
				- [Mozilla Developer Center: Core JavaScript 1.5 Guide](https://developer.mozilla.org/en/core_javascript_1.5_guide)
				- [Eloquent JavaScript](http://eloquentjavascript.net/) (Interactive tutorial)
				- [Learning Advanced JavaScript](http://ejohn.org/apps/learn/) (Interactive tutorial)
				- [QuirksMode](http://www.quirksmode.org/) (The prime source for browser compatibility information)
				- [A re-introduction to JavaScript](https://developer.mozilla.org/en/A_re-introduction_to_JavaScript) (Great article)
				- [Douglas Crockford Video Series](https://www.youtube.com/playlist?list=PL7664379246A246CB)
				- [Introduction to Object Oriented JavaScript](https://developer.mozilla.org/en/Introduction_to_Object-Oriented_JavaScript)
				- [JavaScript Prototypal Inheritance](http://www.3site.eu/doc/)
				- [ECMAScript Language Specification](http://www.ecma-international.org/publications/standards/Ecma-262.htm)
			- Udemy courses
			  collapsed:: true
				- https://www.udemy.com/understand-javascript/
			- Links on here
			  https://dev.to/arnavaggarwal/10-javascript-concepts-you-need-to-know-for-interviews
		- https://boards.4channel.org/g/thread/88407939
	- **Specific Learning**
		- Ad-blocking is HTML-based. Using canvas (like Google Docs? is moving to) would circumvent it
		- Canvas vs DOM
		  collapsed:: true
			- Google Docs moving to canvas
			  https://news.ycombinator.com/item?id=27129858
				- Pros/Cons
					- Pros
						- More performant
					- Cons
						- Possibly
				- Skia is one such cross-platform canvas tool
				- thayne:> For those more deep in web technology, I'd like to know if there are reasons to move to canvas for strictly technical merits.Performance. My company switched from dom to canvas (and then to webgl) for a document-centric app a long time ago because of performance reasons. drawing to a canvas is much faster than updating dom. Also better control over how it displays. With dom you have to worry about differences in how differeny browsers render the same dom a loy more. Although that is less of an issue than it used to be.There are downsides too though. Besides making it much more difficult for extensions to modify things, you also have to build your own spell check, because there isn't a browser API for that. However, I think google docs was already using google's own spellchecker.
		- Aspects of JavaScript
		  collapsed:: true
			- 10 JavaScript concepts you need to know for interviews
			  https://dev.to/arnavaggarwal/10-javascript-concepts-you-need-to-know-for-interviews
			  collapsed:: true
				- [Value vs. Reference](https://www.educative.io/collection/page/5679346740101120/5707702298738688/5685265389584384/) — Understand how objects, arrays, and functions are copied and passed into functions. Know that the reference is what's being copied. Understand that primitives are copied and passed by copying the value.
				- [Scope](https://scotch.io/tutorials/understanding-scope-in-javascript#toc-scope-in-javascript) — Understand the difference between global scope, function scope, and block scope. Understand which variables are available where. Know how the JavaScript engine performs a variable lookup.
				- [Hoisting](http://javascriptissexy.com/javascript-variable-scope-and-hoisting-explained/) — Understand that variable and function declarations are hoisted to the top of their available scope. Understand that function expressions are not hoisted.
				- [Closures](http://javascriptissexy.com/understand-javascript-closures-with-ease/) — Know that a function retains access to the scope that it was created in. Know what this lets us do, such as data hiding, memoization, and dynamic function generation.
				- [this](https://www.educative.io/collection/page/5679346740101120/5707702298738688/5676830073815040) — Know the rules of this binding. Know how it works, know how to figure out what it will be equal to in a function, and know why it’s useful.
				- [new](https://codeburst.io/javascripts-new-keyword-explained-as-simply-as-possible-fec0d87b2741) — Know how it relates to object oriented programming. Know what happens to a function called with new. Understand how the object generated by using new inherits from the function’s prototype property.
				- [apply, call, bind](https://codeplanet.io/javascript-apply-vs-call-vs-bind/) — Know how each of these functions work. Know how to use them. Know what they do to this.
				- [Prototypes & Inheritance](https://codeburst.io/master-javascript-prototypes-inheritance-d0a9a5a75c4e) — Understand that inheritance in JavaScript works through the [[Prototype]] chain. Understand how to set up inheritance through functions and objects and how new helps us implement it. Know what the _proto_ and prototype properties are and what they do.
				- [Asynchronous JS](https://www.youtube.com/watch?v=8aGhZQkoFbQ&t=948s) — Understand the event loop. Understand how the browser deals with user input, web requests, and events in general. Know how to recognize and correctly implement asynchronous code. Understand how JavaScript is both asynchronous and single-threaded.
				- [Higher Order Functions](https://www.sitepoint.com/higher-order-functions-javascript/) — Understand that functions are first-class objects in JavaScript and what that means. Know that returning a function from another function is perfectly legal. Understand the techniques that closures and higher order functions allow us to use.
			- [Google JavaScript style guide](https://google.github.io/styleguide/jsguide.html)
			- [I stayed away from learning/using flex-box due to perceived lack of browser support. Can't believe I've been doing without this for so long!](https://reddit.com/comments/4yvxka)
			- [Intro to Webpack](https://ehlers.berlin/intro-to-webpack-4/) - webpack can be used to bundle multiple JS files together which can then be loaded as a single file
		- Apps to build/practice
		  collapsed:: true
		  id:: 629ccb26-b10e-42fc-9159-dc41777023ac
			- Todost - todo app
			  https://codepen.io/Quentincls/pen/bvBrpo
			- [I created a small but challenging list of fun apps to build](https://medium.com/@wesharehoodies/the-secret-to-being-a-top-developer-is-building-things-heres-a-list-of-fun-apps-to-build-aac61ac0736c)
			- [Want to be a top developer? You should build things. Here’s another list to get you started.](https://medium.freecodecamp.org/the-secret-to-being-a-top-developer-is-building-things-d3d058e4e472)
			- Blockchain-related
				- [Introducing An Experienced Developer To Ethereum Smart Contract Coding In Solidity — Build Blockchain Tech](https://www.buildblockchain.tech/blog/2018/6/28/introducing-an-experienced-developer-to-ethereum-smart-contract-coding-in-solidity)
				- [So you want to build a Bitcoin HD wallet? Part 1](https://www.reddit.com/r/CryptoTechnology/comments/8t55fd/so_you_want_to_build_a_bitcoin_hd_wallet_part_1/)
				- [How to build a decentralised exchange?](https://www.reddit.com/r/CryptoTechnology/comments/8xijqn/how_to_build_a_decentralised_exchange/)
				- [Does anybody have any information on how to build a site similar to cryptowat.ch?](https://www.reddit.com/r/CryptoTechnology/comments/8yat60/does_anybody_have_any_information_on_how_to_build/)
		- https://developer.mozilla.org/en-US/docs/Web/JavaScript
		- Use SVGs rather than PNGS
		  collapsed:: true
			- https://www.checkbot.io/article/web-page-screenshots-with-svg/?
			- How to automate SVG creation - For web pages, you could use Puppeteer (headless Chrome) to save to PDF, then convert the PDF to SVG. You'd need to do some coding to set the screenshot up first so it's posed the way you want though e.g. hide elements you don't need to show and replace text/numbers with mock content.
	- https://carlanderson.xyz/when-to-start-learning-a-framework/
	- [30-seconds/30-seconds-of-code: Short JavaScript code snippets for all your development needs](https://github.com/30-seconds/30-seconds-of-code)
	- Use ESLint + Prettier to ensure code fits coding styles
	  collapsed:: true
		- ESLint - The pluggable linting utility for JavaScript and JSX
		  collapsed:: true
			- https://eslint.org/
			- Linters are amazing because if someone doesnt write code the way you like, just throw a rule in and fail any PRs that dont follow the rules. Debating about stuff like this wastes valuable engineering time.
			- We use prettier (on top of eslint/tslint) at work. Although, there are times where I hate what prettier is doing to my code, I just accept it and move on. No wasted brain cycles.
			- 100% this. We use Prettier to auto format all code. Get together with the most senior folks, decide on which style for everything, and let it do its magic.
			-
			- Do I agree with all auto formatted style changes? Nope. But I stopped worrying about it, cause now at least it's consistent across the entire codebase.
			-
			- It's liberating, I don't have to worry about stupid code style! I can just care about actual code and review comments that matter. Try it.
			- level 3
			- Haegin
				-
			- 29 points ·
			- 2 months ago
			-
			- I also use prettier and it's great, but it won't refactor code like this.
			- level 4
			- toqy
				-
			- 27 points ·
			- 2 months ago
			-
			- Eslint will, and the things it can’t auto fix it will at least tell you about.
			- level 5
			- Warbird01
				-
			- 3 points ·
			- 2 months ago
			-
			- Yup, I always use both
			- level 3
			- toqy
				-
			- 9 points ·
			- 2 months ago
			-
			- Yeah same. Eslint + prettier and precommit git hooks to run it.
			-
			- Even if your team is against it for some reason, you can run it in your own editor
	- GitHub - jeantimex/javascript-problems-and-solutions: A collection of JavaScript problems and solutions for studying algorithms.
	  https://github.com/jeantimex/javascript-problems-and-solutions
	- GitHub - danistefanovic/build-your-own-x: 🤓 Build your own (insert technology here)
	  https://github.com/danistefanovic/build-your-own-x
	- https://github.com/bmorelli25/Become-A-Full-Stack-Web-Developer
	- [Exercises for Java script](https://www.reddit.com/r/learnjavascript/comments/9akp92/exercises_for_java_script/)
	- [Pro devs, advantages/disadvantages to using ES2018?](https://www.reddit.com/r/javascript/comments/9apq4i/pro_devs_advantagesdisadvantages_to_using_es2018/)
	- Javascript colour picker https://github.com/George3d6/coloris
	- [30 seconds of interviews](https://30secondsofinterviews.org/)
	- https://github.com/gentics/headless-cms-comparison
	- [How to land a remote freelance web development job in 21 days without a fleshed out portfolio](https://medium.com/@dericksozo/remote-freelance-web-development-job-no-portfolio-2f871f298cbb)
	- [JavaScript programming interview questions?](https://www.reddit.com/r/learnjavascript/comments/93acic/javascript_programming_interview_questions/)
	- [An interactive CSS Grid builder. Supports template areas, line names and more!](https://reddit.com/comments/92319j)
	- [11 Javascript Resources For Every Level of Expertise](https://www.fullstackacademy.com/blog/learn-javascript-for-free-11-online-tutorials-resources)
	- [Best Javascript learning resource that you think (almost) no one is aware of](https://www.reddit.com/r/javascript/comments/8v2t7h/best_javascript_learning_resource_that_you_think/)
	- [Comments for JavaScript fundamentals before learning React](https://reddit.com/comments/90i06g)
	- [The 5 main pillars of learning programming](https://medium.freecodecamp.org/the-main-pillars-of-learning-programming-and-why-beginners-should-master-them-e04245c17c56)
	  collapsed:: true
		- Test-Driven Development
		- Fundamentals First
		- Libraries & Frameworks
		- Master & Apprentice
		- Challenge & Motivation
	- References/Ongoing learning
		- ((6343d066-e388-4d88-808d-94ce2960681d))
		- [JavaScript in Plain English](https://javascript.plainenglish.io)
		- [Hackterms: a dictionary of programming terms](https://www.hackterms.com/)
		- https://www.reddit.com/r/javascript
		- YouTube channels
		  collapsed:: true
			- [Web Dev Cody](https://www.youtube.com/channel/UCsrVDPJBYeXItETFHG0qzyw)
			  id:: 646349ac-4774-4376-b96f-863fd43d5b4d
			  AKA Web Dev Junkie
				- Shorts
				  id:: 6364c41b-0024-4b36-a6e3-adc75e044ac8
					- ((6367b609-cc62-4567-92f9-93038f30fdd4))
					- ((635eb08f-9a44-4545-88c0-b7064e94f590)) : ((6367af82-3703-4412-acb1-e47347b5b08f))
					- ((6367ac6e-5aa5-4d6a-a059-2efefda1df54))
					  collapsed:: true
						- {{embed ((6367ac6e-5aa5-4d6a-a059-2efefda1df54))}}
					- ((6345ae08-b3a7-40fb-bd6a-35c0918159e5))
					- ((6367a82c-cc3e-4f05-bb71-fe01e8558ebe))
					- ((6367a0ff-8d8b-4d0d-b757-9219291e7ed8))
					- ((6367a0a0-4b5c-4f7a-8212-9ec4e3007acf))
					- always use a [...spread operator] when sorting an array so you don't accidentally mutate your original array
					- [How to use closures to have multiple variables utilise a function](https://youtu.be/LC5O4rbjd-4)
					  collapsed:: true
						- Note: JavaScript classes work the same
						- ```javascript
						  // 
						  const makeCounter = () => {
						    let count = 0;
						    return () => { 
						      // by putting 'count++' inside another function instead of just returning it immediately 
						      // you can use it to make multiple separate counters
						      return count++;
						    }
						  }
						  const counter1 = makeCounter();
						  const counter2 = makeCounter();
						  console.log(counter1()) // 0
						  console.log(counter2()) // 0
						  console.log(counter2()) // 1
						  ```
					- ((63642a2b-028e-460f-aed5-9d6bf0113e1e))
					- ((6367a146-06fc-4e50-b64f-a112da9ad635))
					- ((6367a177-676f-4518-ad91-4fad0759ab49))
					- ((63642aac-c79a-4855-9c12-fae94a472481))
					  id:: 6364c41e-9a2f-4013-9da5-f1e3ebbd9de8
					- [How to clone an array](https://youtu.be/nzXc00nhbrs)
					  collapsed:: true
						- Either
							- ((63642a10-4e86-4101-961a-8311efb8ae4f))
								- {{embed ((6366bcb3-363f-471f-a46a-a9343f750433))}}
							- ((634bc0c2-0b68-4da7-83b6-5abefa297cac))
								- {{embed ((6367a1d7-df6e-400d-88d4-04c30f179e15))}}
		- [Addy's Toolkit • Web Dev & Design Resources – Curated tools & resources for people who make websites](https://toolkit.addy.codes/)
	- https://trends.builtwith.com/javascript
		- jQuery
		- Modernizr
	- Hacker News hiring trends
	  collapsed:: true
		- https://www.hntrends.com/2018/jan-react-continues-streak.html?compare1=React&compare2=AngularJS&compare3=Vue&compare4=Ember
	- [Flow](https://flow.org/) is a static type checker for JavaScript
	- [Sign In | Pluralsight](https://app.pluralsight.com/paths/skills/javascript-2022)
- # Related:
	- [[CSS]]
	- [Priority coding to-do](((629ccb27-fddd-452f-94f6-77bfc30bcfcf)))
	- [Build software for portfolio/MVPs/personal use](((633b7546-8735-4803-8694-43f949258c50)))