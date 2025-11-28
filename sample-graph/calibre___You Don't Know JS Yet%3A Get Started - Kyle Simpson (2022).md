tags::
isbn:: NA
date:: 2022
publisher:: NA
language:: NA
authors:: [[Kyle Simpson]]
format:: [epub](/home/boss/Vaults/gocryptfs1/Calibre/Calibre-Library/Kyle Simpson/You Don't Know JS Yet_ Get Started (1808)/You Don't Know JS Yet_ Get Started - Kyle Simpson.epub)

- [[Synopsis]]
	-
- [You Don't Know JS Yet: Get Started](calibre://show-book/Calibre-Library/1808)  {{renderer calibreViewer, special, http://localhost:3296/#book_id=1808&fmt=epub&library_id=Calibre-Library&mode=read_book}} {{renderer calibreHighlight, true, 2000, http://localhost:3296, Calibre-Library, 1808, epub}}
  lastsync:: Fri Oct 04 2024 10:36:11 GMT+0100 (British Summer Time)
	- # {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/8/2/4/2[preface]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Preface
	  collapsed:: true
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/8/2/4/2[preface]/10/1:290%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} these books are written assuming you’re already comfortable with JS and have at least 6–9 months experience with it.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/8/2/4/2[preface]/12[the-parts]/4/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} These books approach JavaScript intentionally opposite of how The Good Parts treats the language. No, that doesn’t mean we’re looking at the bad parts, but rather, exploring all the parts.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/8/2/4/2[preface]/12[the-parts]/12/1:110%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Don’t buy the “X is the new Y” snake oil, that some new feature of the language instantly relegates all usage of a previous feature as obsolete and ignorant.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/8/2/4/2[preface]/12[the-parts]/16/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} I find it absurd to try to be a truly effective JavaScript developer while only using a small sliver of what the language has to offer. Can you imagine a construction worker with a toolbox full of tools, who only uses their hammer and scoffs at the screwdriver or tape measure as inferior? That’s just silly.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/8/2/4/2[preface]/16[the-mission]/10/1:86%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} you will always be more effective in your development work if you more completely understand how your code works than you are solely just getting it to produce a desired outcome.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/8/2/4/2[preface]/18[the-path]/10/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} My suggestion is you take your time going through YDKJSY. Take one chapter, read it completely through start to finish, and then go back and re-read it section by section. Stop in between each section, and practice the code or ideas from that section. For larger concepts, it probably is a good idea to expect to spend several days digesting, re-reading, practicing, then digesting some more.
		  
		  You could spend a week or two on each chapter, and a month or two on each book, and a year or more on the whole series, and you would still not be squeezing every ounce of YDKJSY out.
		- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/8/2/4/2[preface]/18[the-path]/14/1:65%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Interleave reading with lots of practice on real code in your job or on projects you participate in. Wrestle with the opinions I’ve presented along the way, debate with others, and most of all, disagree with me! Run a study group or book club. Teach mini-workshops at your office. Write blog posts on what you’ve learned. Speak about these topics at local JS meetups.
	- # {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Chapter 1: What Is JavaScript?
		- ## {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/10[about-this-book]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} About This Book
		  collapsed:: true
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/10[about-this-book]/8/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} In particular, Chapter 4 identifies three main pillars around which the JS language is organized: scope/closures, prototypes/objects, and types/coercion. JS is a broad and sophisticated language, with many features and capabilities. But all of JS is founded on these three foundational pillars.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/10[about-this-book]/10/1:18%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} even though this book is titled “Get Started,” it’s not intended as a beginner/intro book. This book’s main job is to get you ready for studying JS deeply throughout the rest of the series
		- ## {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/12[whats-with-that-name]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} What’s With That Name?
		  collapsed:: true
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/12[whats-with-that-name]/14/1:199%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} assumed syntax expectations from C (and to an extent, C++).
			  
			  For example, we use the { to begin a block of code and the } to end that block of code, just like C/C++ and Java. We also use the ; to punctuate the end of a statement.
		- ## {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Language Specification
		  collapsed:: true
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/16/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} All TC39 proposals progress through a five-stage process—of course, since we’re programmers, it’s 0-based!—Stage 0 through Stage 4. You can read more about the Stage process here: [The TC39 Process](https://tc39.es/process-document/)
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/18/1:246%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} You have to get a TC39 member to champion a proposal for it to be considered “Stage 0” officially.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/22/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} All proposals are managed in the open, on TC39’s Github repository: https://github.com/tc39/proposals
			- ### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/34[the-web-rules-everything-about-js]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} The Web Rules Everything About (JS)
			  collapsed:: true
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/34[the-web-rules-everything-about-js]/8/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Sometimes the JS specification will dictate some new or refined behavior, and yet that won’t exactly match with how it works in browser-based JS engines. Such a mismatch is historical: JS engines have had 20+ years of observable behaviors around corner cases of features that have come to be relied on by web content. As such, sometimes the JS engines will refuse to conform to a specification-dictated change because it would break that web content.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/34[the-web-rules-everything-about-js]/12/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} But occasionally, TC39 will decide the specification should stick firm on some point even though it is unlikely that browser-based JS engines will ever conform.
					- The solution? Appendix B, “[Additional ECMAScript Features for Web Browsers](https://www.ecma-international.org/ecma-262/10.0/#sec-additional-ecmascript-features-for-web-browsers)”.1 The JS specification includes this appendix to detail out any known mismatches between the official JS specification and the reality of JS on the web. In other words, these are exceptions that are allowed only for web JS; other JS environments must stick to the letter of the law.
			- ### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/36[not-all-web-js]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Not All (Web) JS…
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/36[not-all-web-js]/12/1:9%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} a wide range of JS-looking APIs, like fetch(..), getCurrentLocation(..), and getUserMedia(..), are all web APIs that look like JS. In Node.js, we can access hundreds of API methods from various built-in modules, like fs.write(..).
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/36[not-all-web-js]/14/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Another common example is console.log(..) (and all the other console.* methods!). These are not specified in JS, but because of their universal utility are defined by pretty much every JS environment, according to a roughly agreed consensus.
			- ### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/38[its-not-always-js]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} It’s Not Always JS
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/38[its-not-always-js]/4/1:10%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} console/REPL (Read-Evaluate-Print-Loop) in your browser’s Developer Tools (or Node)
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/38[its-not-always-js]/16/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} The developer console is not trying to pretend to be a JS compiler that handles your entered code exactly the same way the JS engine handles a .js file. It’s trying to make it easy for you to quickly enter a few lines of code and see the results immediately.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/14[language-specification]/38[its-not-always-js]/18/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Don’t trust what behavior you see in a developer console as representing exact to-the-letter JS semantics; for that, read the specification. Instead, think of the console as a “JS-friendly” environment.
		- ## {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/16[many-faces]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Many Faces
		  collapsed:: true
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/16[many-faces]/4/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} The term “paradigm” in programming language context refers to a broad (almost universal) mindset and approach to structuring code.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/16[many-faces]/8/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Typical paradigm-level code categories include procedural, object-oriented (OO/classes), and functional (FP):
				- Procedural style organizes code in a top-down, linear progression through a pre-determined set of operations, usually collected together in related units called procedures.
				- OO style organizes code by collecting logic and data together into units called classes.
				- FP style organizes code into functions (pure computations as opposed to procedures), and the adaptations of those functions as values.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/16[many-faces]/14/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Some languages are heavily slanted toward one paradigm—C is procedural, Java/C++ are almost entirely class oriented, and Haskell is FP through and through.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/16[many-faces]/18/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} JavaScript is most definitely a multi-paradigm language. You can write procedural, class-oriented, or FP-style code
		- ## {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Backwards & Forwards
		  collapsed:: true
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/8/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Backwards compatibility means that once something is accepted as valid JS, there will not be a future change to the language that causes that code to become invalid JS.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/12/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} That “guarantee” is no small thing. Maintaining backwards compatibility, stretched out across almost 25 years of the language’s history, creates an enormous burden and a whole slew of unique challenges.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/16/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} There are some small exceptions to this rule. JS has had some backwards-incompatible changes, but TC39 is extremely cautious in doing so. They study existing code on the web (via browser data gathering) to estimate the impact of such breakage, and browsers ultimately decide and vote on whether they’re willing to take the heat from users for a very small-scale breakage weighed against the benefits of fixing or improving some aspect of the language for many more sites (and users).
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/20/1:31%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Being forwards-compatible means that including a new addition to the language in a program would not cause that program to break if it were run in an older JS engine.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/20/1:198%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} JS is not forwards-compatible, despite many wishing such, and even incorrectly believing the myth that it is.
			- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/22/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} HTML and CSS, by contrast, are forwards-compatible but not backwards-compatible. If you dug up some HTML or CSS written back in 1995, it’s entirely possible it would not work (or work the same) today. But, if you use a new feature from 2019 in a browser from 2010, the page isn’t “broken” – the unrecognized CSS/HTML is skipped over, while the rest of the CSS/HTML would be processed accordingly.
			- ### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/30[jumping-the-gaps]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Jumping the Gaps
			  collapsed:: true
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/30[jumping-the-gaps]/4/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Since JS is not forwards-compatible, it means that there is always the potential for a gap between code that you can write that’s valid JS, and the oldest engine that your site or application needs to support.
				- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/30[jumping-the-gaps]/6/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} If the feature is a new syntax, the program will in general completely fail to compile and run, usually throwing a syntax error. If the feature is an API (such as ES6’s Object.is(..)), the program may run up to a point but then throw a runtime exception and stop once it encounters the reference to the unknown API.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/30[jumping-the-gaps]/12/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} For new and incompatible syntax, the solution is transpiling. Transpiling is a contrived and community-invented term to describe using a tool to convert the source code of a program from one form to another (but still as textual source code). Typically, forwards-compatibility problems related to syntax are solved by using a transpiler (the most common one being Babel (https://babeljs.io)) to convert from that newer JS syntax version to an equivalent older syntax.
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/30[jumping-the-gaps]/14/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} For example, a developer may write a snippet of code like:
				  collapsed:: true
					- ```js
					  if (something) {
					      let x = 3;
					      console.log(x);
					  }
					  else {
					      let x = 4;
					      console.log(x);
					  }
					  ```
					- This is how the code would look in the source code tree for that application. But when producing the file(s) to deploy to the public website, the Babel transpiler might convert that code to look like this:
					- ```js
					  var x$0, x$1;
					  if (something) {
					      x$0 = 3;
					      console.log(x$0);
					  }
					  else {
					      x$1 = 4;
					      console.log(x$1);
					  }
					  ```
				- {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/30[jumping-the-gaps]/26/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} You may wonder: why go to the trouble of using a tool to convert from a newer syntax version to an older one? Couldn’t we just write the two variables and skip using the let keyword? The reason is, it’s strongly recommended that developers use the latest version of JS so that their code is clean and communicates its ideas most effectively.
				  
				  Developers should focus on writing the clean, new syntax forms, and let the tools take care of producing a forwards-compatible version of that code that is suitable to deploy and run on the oldest-supported JS engine environments.
			- ### {{renderer calibreViewer, yellow, http://localhost:3296/#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/32[filling-the-gaps]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Filling the Gaps
			  collapsed:: true
				- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/32[filling-the-gaps]/4/1:1%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} f the forwards-compatibility issue is not related to new syntax, but rather to a missing API method that was only recently added, the most common solution is to provide a definition for that missing API method that stands in and acts as if the older environment had already had it natively defined. This pattern is called a polyfill (aka “shim”).
				- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/32[filling-the-gaps]/6/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Consider this code:
					- ```js
					  // getSomeRecords() returns us a promise for some
					  // data it will fetch
					  var pr = getSomeRecords();
					  
					  // show the UI spinner while we get the data
					  startSpinner();
					  
					  pr
					  .then(renderRecords)   // render if successful
					  .catch(showError)      // show an error if not
					  .finally(hideSpinner)  // always hide the spinner
					  ```
				- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/32[filling-the-gaps]/10/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} This code uses an ES2019 feature, the finally(..) method on the promise prototype. If this code were used in a pre-ES2019 environment, the finally(..) method would not exist, and an error would occur.
				- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/32[filling-the-gaps]/12/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} A polyfill for finally(..) in pre-ES2019 environments could look like this:
				  collapsed:: true
					- ```js
					  if (!Promise.prototype.finally) {
					      Promise.prototype.finally = function f(fn){
					          return this.then(
					              function t(v){
					                  return Promise.resolve( fn() )
					                      .then(function t(){
					                          return v;
					                      });
					              },
					              function c(e){
					                  return Promise.resolve( fn() )
					                      .then(function t(){
					                          throw e;
					                      });
					              }
					          );
					      };
					  }
					  ```
				- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/32[filling-the-gaps]/16/6/2/2/1:129%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} always use a robust, official polyfill wherever possible, such as the collection of polyfills/shims in ES-Shim.
				  
				  The if statement protects the polyfill definition by preventing it from running in any environment where the JS engine has already defined that method. In older environments, the polyfill is defined, but in newer environments the if statement is quietly skipped.
				  
				  Transpilers like Babel typically detect which polyfills your code needs and provide them automatically for you. But occasionally you may need to include/define them explicitly, which works similar to the snippet we just looked at.
				- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/32[filling-the-gaps]/22/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Always write code using the most appropriate features to communicate its ideas and intent effectively. In general, this means using the most recent stable JS version. Avoid negatively impacting the code’s readability by trying to manually adjust for the syntax/API gaps. That’s what tools are for!
				- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/18[backwards-forwards]/32[filling-the-gaps]/24/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} Transpilation and polyfilling are two highly effective techniques for addressing that gap between code that uses the latest stable features in the language and the old environments a site or application needs to still support. Since JS isn’t going to stop improving, the gap will never go away. Both techniques should be embraced as a standard part of every JS project’s production chain going forward.
		- ## {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/20[whats-in-an-interpretation]/2/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} What’s in an Interpretation?
	- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/20[whats-in-an-interpretation]/4/1:28%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} code written in JS: is it an interpreted script or a compiled program? The majority opinion seems to be that JS is an interpreted (scripting) language. But the truth is more complicated than that.
	- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/20[whats-in-an-interpretation]/10/1:61%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} The real reason it matters to have a clear picture on whether JS is interpreted or compiled relates to the nature of how errors are handled.
	  
	  Historically, scripted or interpreted languages were executed in generally a top-down and line-by-line fashion; there’s typically not an initial pass through the program to process it before execution begins
	- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/20[whats-in-an-interpretation]/16/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} In scripted or interpreted languages, an error on line 5 of a program won’t be discovered until lines 1 through 4 have already executed. Notably, the error on line 5 might be due to a runtime condition, such as some variable or value having an unsuitable value for an operation, or it may be due to a malformed statement/command on that line. Depending on context, deferring error handling to the line the error occurs on may be a desirable or undesirable effect.
	  
	  Compare that to languages which do go through a processing step (typically, called parsing) before any execution occurs
	- {{renderer calibreViewer, yellow, /#book_id=1808&bookpos=epubcfi%28/10/2/4/2[chapter-1-what-is-javascript]/20[whats-in-an-interpretation]/22/1:0%29&fmt=epub&library_id=Calibre-Library&mode=read_book }} In this processing model, an invalid command (such as broken syntax) on line 5 would be caught during the parsing phase, before any execution has begun, and none of the program would run.