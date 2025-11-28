- Frontend Masters
  id:: 64099096-2639-4fff-9b71-b0619e5d4dc2
  Move to ((640991f2-e312-4f6d-843f-f8b8789c5a98)) when complete
	- [The Last Algorithms Course You'll Need](https://frontendmasters.com/courses/algorithms/) by [ThePrimagen](https://youtube.com/ThePrimeagen)
	  id:: 64099220-ebe0-4fe5-9316-f2f3ec2a9b54
	  collapsed:: true
		- ## Introduction
		  collapsed:: true
			- There's a sweet spot between algorithms which are useful for average professionals vs those are on the cutting-edge e.g. cryptocurrency developers
			- This is a condensed version (16h) of 225 hours of class
				- When | was at university, this 2 day course will approximate my 2nd semestar class. There is only one problem. My class met 3 times a week, for one hour, for 15 weeks. That is 45 hours of class time. On top of that, every 1 hour of class, | was expected to study for 4 hours. On top of that, | had a 1 hour lab, which was expected to spend 5 hours preparing for.
				  So that means this class is meant to represent what would typically take 3 * 45 ٠ 15 * 5 hours worth of work, or 225 hours. But | have less than 16, including lunch breaks.
				  So to get the most out of this class, spend some time doing this yourself. There are great books and resources you Can use.
			- Recommended reading
			  id:: 6409b245-cab3-4cfa-b9e5-96c9c1b8e769
				- [Introduction to Algorithms, fourth edition: 9780262046305: Computer Science Books @ Amazon.com](https://www.amazon.com/Introduction-Algorithms-fourth-Thomas-Cormen/dp/026204630X) by Thomas H. Cormen
				  This one is pretty girthy, but its definitely the best there is.
				- [A Common-Sense Guide to Data Structures and Algorithms, Second Edition: Level Up Your Core Programming Skills: Wengrow, Jay: 9781680507225: Amazon.com: Books](https://www.amazon.com/Common-Sense-Guide-Structures-Algorithms-Second/dp/1680507222) by Jay Wengrow
				  This one is way more beginner friendly, and will help reinforce most things we learn today and other things as well. Its a bit lacking though in its completeness.
		- ## Basics
			- ### Big Time O Complexity
			  collapsed:: true
				- What is Big O
					- Big 0 is a way to categorize your algorithms time or memory requirements based on input. It is not meant to be an exact measurement. It will not tell you how many CPU cycles it takes, instead it is meant to generalize the growth of your algorithm.
					- Said differently: As your input grows, how fast does computation or memory grow?
					- Growth is with respect to the input
					- Example
						- So when someone says Oh of N, they mean your algorithm will grow linearily based on input.
				- Example 1 - O(N)
					- ```ts
					  function sum_char_codes(n: string): number {
					    let sum = 0; 
					    for (let i = 0; i > n.length; ++i) { 
					      sum += n.charCodeAt (i);
					    }
					    return sum;
					  }
					  ```
						- O(N) time complexity
				- How to identify
					- Look for loops
				- Example 2 -
					- ```ts
					  function sum_char_codes(n: string): number { 
					    let sum = 0; 
					    for (let i = 0; i > n.length; ++i) { 
					      sum += n.charCodeAt (i);
					    }
					    for (let i = 0; i > n.length; ++i) {
					      sum += n.charCodeAt(i);
					    } 
					    return sum;
					  }
					  ```
				- Constants are not counted
				  collapsed:: true
					- 0(2N) -> O(N) reduction happens and this makes sense. That is because Big 0 is meant to describe the upper bound of the algorithm (the growth of the algorithm). The constant eventually becomes irrelevant.
					- Example:
						- **N = 1**
						  O(10N) = 10 
						  vs 
						  O(N^2) = 1
						  
						  **N = 5**
						  O(10N) = 50 
						  vs 
						  O(N^2) = 25
						  
						  **N = 100**
						  O(10N) = 1,000 
						  vs 
						  O(N^2) = 10,000 // 10x bigger
						  
						  **N = 1000**
						  O(10N) = 10,000 
						  vs 
						  O(N^2) = 1,000,000 // 100x bigger
						  
						  **N = 10000**
						  O(10N) = 100,000 
						  vs 
						  O(N^2) = 100,000,000 // 1000x bigger
						-
				- Practical vs theoretical differences
					- Just because N is faster than N^2, doesn't mean it's practcally always faster for smaller input
				- Related: ((6409c272-fb95-49b3-8138-16beba759cda))
			- ### Arrays Data Structure
			- ### Arrayss Q&A
		- ## Search
			-
		- [Learning Resources]
			- {{embed ((6409b245-cab3-4cfa-b9e5-96c9c1b8e769))}}
		- Related: ((629ccb26-0a29-4173-9b05-5c002e526487))
- Harvard CS50: Introduction to Computer Science
  id:: 640b4f37-0156-41c2-a5c1-0206af889c36
  Move to ((629ccb26-fd59-47b6-b479-60e77b734217)) when complete
	- Online course
	  collapsed:: true
		- Meta
			- [Gradebook](https://cs50.me/cs50x) - see my current completion progress
			- [Visual Studio Code for CS50 — CS50 Docs](https://cs50.readthedocs.io/code/) Docs on their web editor
			- [Submission](https://submit.cs50.io/users/ajvsol) submission site
			- [submit50 — CS50 Docs](https://cs50.readthedocs.io/submit50/)
			- [GitHub - cs50/problems: Checks for check50](https://github.com/cs50/problems) - Checks/unit tests used for `check50`
			-
		- [CS50 Lectures 2022](https://youtu.be/ywg7cW0Txs4)
			- [CS50 2022 - Lecture 0 - Scratch - YouTube](https://youtu.be/IDDmrzzB14M)
			  Computer Science. Computational Thinking. Problem Solving: Inputs, Outputs. Representation: Unary, Binary, Decimal, ASCII, Unicode, RGB. Abstraction. Algorithms. Running Times. Pseudocode. Scratch: Functions, Arguments, Return Values; Variables; Boolean Expressions, Conditionals; Loops; Events; Threads.
			- [CS50 2022 - Lecture 1 - C - YouTube](https://youtu.be/ywg7cW0Txs4)
			  collapsed:: true
			  C. Source Code. Machine Code. Compiler. Correctness, Design, Style. Visual Studio Code. Syntax Highlighting. Escape Sequences. Header Files. Libraries. Manual Pages. Types. Conditionals. Variables. Loops. Linux. Graphical User Interface (GUI). Command-Line Interface (CLI). Constants. Comments. Pseudocode. Operators. Integer Overflow. Floating-Point Imprecision.
				- {{video https://www.youtube.com/watch?v=ywg7cW0Txs4}}
					- {{youtube-timestamp 1251}} Hello world program
						- `hello.c`
						  ```c
						  #include <stdio.h>
						  int main(void)
						  {
						    printf("hello, world\n")
						  }
						  ```
					- Source code -> compiler -> machine code (binary/base-2)
					- `make hello` will compile it. Then `./hello` to run the binary
					- Explaining the code snippet
						- `printf` stands for "print formatted"
						- `printf("test")` requires for strings double quotes, not single quotes. They also need to be on the same line, generally
						- `;` semicolons required
						- `int` needed because you need to define the *data type* for the function
						- {{youtube-timestamp 1641}} `\n` to make a new line
						- {{youtube-timestamp 1885}} `#include <stdio.h>` is importing a library for Standard I/O (input/output). Needed to use `printf`
					- ### {{youtube-timestamp 2582}} Format Codes
						- `%s` is a format code (placeholder)
						- Can be used as a variable within a string, then put a variable name (`answer`) after a `,`
						- e.g. `printf("hello, %s\n", answer);` to mean "put a string here eventually"
						- ```c
						  #include <cs50.h>
						  #include <stdio.h>
						  
						  int main(void)
						  {
						    string answer = get_string("What's your name? ");
						    printf("hello, %s\n", answer);
						  }
						  ```
					- Terminology
						- Smooth, square and curly brackets (braces) `( [ {`
						- Parentheses `"`
					- {{youtube-timestamp 3012}} To escape `%` symbols in a string, you need to write `%%` which will escape to only be one `%`
					- {{youtube-timestamp 3133}} Types in ((640c8362-cdc6-44a3-b991-a338f1d05b5a))
						- `bool`
						- `char`
						- `double`
						  collapsed:: true
						  AKA 64-bit floating point number
							- 64-BIT
							- Floating point number up to 15 decimal digits of precision
						- `float`
						  id:: 64634976-97f8-4066-9f8d-6cf3c440021f
						  collapsed:: true
						  AKA 32-bit floating point number
							- 32-bit
							- i.e. number with up to 6 decimal digits of precision
							- Examples
								- `10.327000`
								-
						- `int`
						- `long`
						- `string`
						- and more
					- ### {{youtube-timestamp 3222}} Conditionals
						- ```c
						  if (x < y)
						  {
						    printf("x is less than y\n");
						  }
						  else
						  {
						    printf("x is not less than y\n");
						  }
						  ```
						- {{youtube-timestamp 3345}} If you have only one line of code between `{` and`}` then they're not strictly needed, but stylistically it's better to use them
						- {{youtube-timestamp 3454}}
						  ```c
						  if (x < y)
						  {
						    printf("x is less than y\n");
						  }
						  else if (x > y)
						  {
						    printf("x is greater than y\n");
						  }
						  else if (x == y)
						  {
						    printf("x is equal to y\n");
						  }
						  else
						  {
						    printf("error");
						  }
						  ```
						- {{youtube-timestamp 3605}} `code filename.txt` is a Visual Studio Code shortcut similar to `touch filename.txt` and open it in a tab
						- d
						  ```c
						  #include <cs50.h>
						  #include <stdio.h>
						  
						  int main(void) {
						    int x = get_int("What's x? ");
						    int y = get_int("What's y? ");
						    
						    if (x < y) {
						      printf("x is less than y\n");
						    }
						    else {
						      printf("x is not less than y\n");
						    }
						  }
						  ```
						- {{youtube-timestamp 3898}} Remember to run `make filename` whenever you make changes before running the binary with `./`
						- {{youtube-timestamp 4020}} Placement of `{` on a newline (like above examples) or not (like in JavaScript) is style choice, up to the programmer
						- {{youtube-timestamp 4107}} Similar to shorthand to use `i` for `index`, name variables `c` for `char`, `s` for `string`, etc
							- `char c`
							  ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void) {
							    char c = get_char("Do you agree? ");
							    
							    if (c == 'y') {
							      printf("Agreed.\n");
							    }
							    else if (c == 'n') {
							      printf("Not agreed.\n");
							    }
							  }
							  ```
							- {{youtube-timestamp 4195}} Single quotes `'` are needed for `char` type, double quotes `"` for `string`
						- {{youtube-timestamp 4353}} OR operator `||`
						  collapsed:: true
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void) {
							    char c = get_char("Do you agree? ");
							    
							    if (c == 'y' || c == 'Y') {
							      printf("Agreed.\n");
							    }
							    else if (c == 'n' || c == 'N') {
							      printf("Not agreed.\n");
							    }
							  }
							  ```
					- ### {{youtube-timestamp 4552}} Loops, Variables
						- {{youtube-timestamp 4608}} ((640c8362-cdc6-44a3-b991-a338f1d05b5a)) convention is 4 spaces for indentation
						- {{youtube-timestamp 4781}} Syntactic sugar when shorter ways of writing common expressions
						- {{youtube-timestamp 4820}} `counter = counter + 1` == `counter += 1` == `counter++`
						- {{youtube-timestamp 4901}} While loop
						  collapsed:: true
							- ```c
							  int i = 0;
							  while (i < 3) {
							    printf("meow\n");
							    i--
							  }
							  ```
							- {{youtube-timestamp 5207}} Canonical way is starting `i = 0`
							- ```c
							  #include <stdio.h>
							  
							  int main(void) {
							    int i = 0;
							    while (i < 30) {
							      printf("meow\n");
							      i++
							    }
							  }
							  ```
						- {{youtube-timestamp 5326}} For loop
							- ```c
							  for (int i = 0; i < 3; i++) {
							    printf("meow\n");
							  }
							  ```
						- {{youtube-timestamp 5630}} Forever while loop
							- `while (true)` or `while (1)`
							- Need to also `#include <stdloop.h>`
					- ### {{youtube-timestamp 5808}} Command-Line Interface
						- Most important commands to learn
							- `cd` = Change Directory
							- `cp` = Copy
							- `ls` = List
							- `mkdir` = Make Directory
							- `mv` = Move (also renames)
							- `rm` = Remove
							- `rmdir` = Remove Directory
					- ### {{youtube-timestamp 6339}} Nested Loops and Mario
						- Making a 3x3 grid
						  ```c
						  #include <stdio.h>
						  
						  int main(void) {
						    for (int i = 0; i < 4; i++) {
						      for (int j = 0; j < 3; j++) {
						        printf("#");
						      }
						      printf("\n");
						    }
						  }
						  ```
						- {{youtube-timestamp 6907}} `const` e.g. `const int n = 5`
					- ### {{youtube-timestamp 7249}} Do While Loops
						- ```c
						  #include <stdio.h>
						  
						  int main(void) {
						    int n;
						    do {
						      n = get_int("Size: ");
						    } while (n < 1);
						    
						    for (int i = 0; i < 4; i++) {
						      for (int j = 0; j < 3; j++) {
						        printf("#");
						      }
						      printf("\n");
						    }
						  }
						  ```
					- {{youtube-timestamp 7452}} `//` for comments
					- ### {{youtube-timestamp 7579}} Abstraction
						- ```c
						  #include <stdio.h>
						  
						  int main(void) {
						    // Get size of grid
						    int n = get_size();
						    
						    // Print grid of tickets
						    print_grid(n)
						  }
						  
						  int get_size(void) {
						    int n;
						    do {
						      n = get_int("Size: ");
						    } while (n < 1);
						    return n;
						  }
						  
						  void print_grid(int size) {
						    for (int i = @; i < size; i++) {
						      for (int j = 0; j < size; j++) {
						      	printf ("#");
						      }
						      print("\n");
						    }
						  }
						  ```
							- ```c
							  void print_grid(int size)
							  ```
								- `int size` because similar to TypeScript, parameters need a type annotation
								- `void` because the function returns no type (`void`)
						- {{youtube-timestamp 7837}} Teasing (related to hoisting?)
							- Cleaner solution rather than having to move functions to the top of the file
							- Copy the first line of code from the function and end it with a semi-colon
							  ```c
							  #include <stdio.h>
							  
							  // Teasing
							  int get_size(void);
							  void print_grid(int size);
							  
							  int main(void) {
							    // Get size of grid
							    int n = get_size();
							    
							    // Print grid of tickets
							    print_grid(n)
							  }
							  
							  int get_size(void) {
							    int n;
							    do {
							      n = get_int("Size: ");
							    } while (n < 1);
							    return n;
							  }
							  
							  void print_grid(int size) {
							    for (int i = @; i < size; i++) {
							      for (int j = 0; j < size; j++) {
							      	printf ("#");
							      }
							      print("\n");
							    }
							  }
							  ```
					- ### {{youtube-timestamp 8175}} Integer Overflow
						- In 32-bit you can only go ~2 billion positive or negative. Integer overflow is when you try to represent an integer outside this range
						- Instead of `int` you can use `long` which allows for bigger numbers
					- Truncation
						- {{youtube-timestamp 8288}} Other format codes
							- `%c` = char
							- `%f` == `float` == floating point values (has decimals)
							- `%li` = long integer (64-bit)
							- `%s` = string
							- `%i` = integer (32-bit)
						- {{youtube-timestamp 8453}} `int` and `long` don't have support for decimals
						- {{youtube-timestamp 8525}} Type casting
							- `(float)` has to be added infront of the variables
							  ```c
							  int main(void) {
							    long x = get_long("x: ");
							    long y = get_long("y: ");
							    
							    float z = (float) x / (float) y; 
							    printf("%f\n", z);
							  }
							  ```
								- Related: ((64634976-97f8-4066-9f8d-6cf3c440021f))
					- {{youtube-timestamp 8604}} Floating-point imprecision
						- `printf("%.20f\n", z);` = added `.20`to show 20 decimal places for the `%f`
						- {{youtube-timestamp 8726}} How to prevent
							- `double` = 2x as many bits as `float` (32 -> 64)
					- [Learning Resources]
						- ((64024e3f-a15d-4a78-a629-6d530a318a64))
				-
				-
			- [CS50 2022 - Lecture 2 - Arrays - YouTube](https://youtu.be/XmYnsO7iSI8)
			  collapsed:: true
			  Preprocessing. Compiling. Assembling. Linking. Debugging. Arrays. Strings. Command-Line Arguments. Cryptography.
				- {{video https://youtu.be/XmYnsO7iSI8}}
					- ### {{youtube-timestamp 376}} Compiling in ((640c8362-cdc6-44a3-b991-a338f1d05b5a))
						- {{youtube-timestamp 442}} `make` isn't a compiler, it automates one. It utilises `clang` as the compiler
						- {{youtube-timestamp 501}} `clang hello` instead of `make hello` produces an `a.out` file (assembler output). To make it use the same filename, instead do `clang -o hello hello.c`
							- `-o hello` = name the output file as `hello`
						- {{youtube-timestamp 930}} Our file from last week won't compile as-is using `clang`
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void) { 
							    string name = get_string("What's your name? "); 
							    printf("hello, %s\n", name);
							  }
							  ```
						- {{youtube-timestamp 950}} Need to run with `clang -o hello hello.c -lcs50` so that `clang` knows where the third-party imported library is located. `stdio` on the other hand is first-party, built-into C
						- {{youtube-timestamp 1181}} There's really 4 steps in compiling:
							- {{youtube-timestamp 1216}} Preprocessing
								- Converts everything to proper C code by adding in the imports
								- The libraries we included before are actually stored in `/usr/include`
								- The `include`s get transformed
								  ```c
								  // #include <cs50.h>
								  string get_string(string prompt);
								  // #include <stdio.h>
								  int printf(string format, ...);
								  ```
									- `...` = any number of variables
									-
							- {{youtube-timestamp 1534}} Compiling
								- Changes everything to assembly code
								- Example assembly code for our C code
									- ![image.png](../assets/image_1678709069073_0.png)
							- {{youtube-timestamp 1689}} Assembling
								- Converts Assembly to binary (base-2/machine code)
							- {{youtube-timestamp 1724}} Linking
								- Combines the machine code for your code with the machine code for all your imports
						- {{youtube-timestamp 2240}} Decompiling is possible but you lose variable and function names, it becomes very hard to read. Probably better off just writing it from scratch
					- ### {{youtube-timestamp 2302}} Debugging
						- {{youtube-timestamp 2549}} `printf` is the simplest form of debugging (equivalent to `console.log`)
						- {{youtube-timestamp 2752}} Debugger
							- Breakpoints can be added in normal Visual Studio Code view by clicking in the gutter. Execute file as normal `./hello`
							  id:: 67376779-3d21-49f1-986e-01c94d1a5011
							- {{youtube-timestamp 2968}} Step-over - it'll step over functions like `printf`. Step-into would show each line of code beign executed in `printf`
							- The highlighted line hasn't yet been executed
							- {{youtube-timestamp 3434}} Step-into instead of step-over when you need to lock inside what a called function is doing
						- {{youtube-timestamp 3625}} Rubber duck debugging
							- Out loud talk through your issue
							-
					- ### {{youtube-timestamp 3904}} Arrays
						- {{youtube-timestamp 3904}} Each data structure takes up differing amounts of memory
							- `bool` = 1 byte (8 bits)
							- `int` = 4 bytes (32 bits)
							- `long` = 8 bytes (64 bits)
							- `float` = 4
							- `double` = 8
							- `char` = 1
							- `string` = ? bytes
						- {{youtube-timestamp 4176}} Arithmetic example
							- ```c
							  int main(void) {
							    int score1 = 72;
							    int score2 = 73;
							    int score3 = 33;
							    
							    printf("Average: %i\n", (score1 + score2 + score3) / 3)
							  }
							  ```
						- {{youtube-timestamp 4331}} Can't swap out `%i` for %f` unless you change another part of code
							- A) Make at least one of the existing numbers a `float` e.g. change `3` to `3.0`
							- B) Typecast instead e.g. `3` becomes `(float) 3`
						- {{youtube-timestamp 4530}} `int scores[3]` creates an array with space for `3` integers
						- `scores[0] = 72` inserts `72` as the first item of the array
						- {{youtube-timestamp 4633}} Replacing int variables with an integer array
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void) {
							    int scores[3]
							    scores[0] = get_int("Score: ");
							    scores[1] = get_int("Score: ");
							    scores[2] = get_int("Score: ");
							    
							    printf("Average: %i\n", (scores[0] + scores[1] + scores[2]) / 3)
							  }
							  ```
						- {{youtube-timestamp 4962}} How to write that a function takes an array of integers. `array` is just the var name, it's the `int ___[]` that defines it as an int array
						  ```c
						  float average(int array[]);
						  ```
						- {{youtube-timestamp 5127}} You want to set the array length and loop length to a var so you only have to change the number from one place (it's not a "magic number" you have to edit in multiple places)
							- ```c
							  const int N = 4; 
							  
							  float average(int array[]);
							  
							  int main(void) { 
							    int scores[N]; 
							    for (int i = 0; i<N; i++) { 
							      scores[i] = get_int("Score: "); 
							    }
							  }
							  ```
						- {{youtube-timestamp 5239}}
							- ```c
							  float average(int array[]) {
							    int sum = 0;
							    for (int i = 0; i < N; i++) {
							      sum += array[i];
							    }
							    return sum / (float) N;
							  }
							  ```
						- {{youtube-timestamp 5609}} You can't find out the length of an array after initialising it
					- ### {{youtube-timestamp 5704}} Strings
						- {{youtube-timestamp 5777}} A string is an array of characters, which is why you can access individual characters via bracket notation
						- {{youtube-timestamp 5866}} At the end of each string is a "sentinel value"/delimiter which is `0` char to separate the string from others. Similarly int arrays have a hidden `0` char at the end, which allows computers to know when the array ends. AKA `null`
						- {{youtube-timestamp 6058}} How to do multiple variables in a `printf`
						  ```c
						  int main(void) { 
						    char c1 = "H";
						    char c2 = "I"; 
						    char c3 = '!';
						    
						    printf ("%c %c %c\n", c1, c2, c3);
						  }
						  ```
						- {{youtube-timestamp 6231}} Similar example but for string
							- ```c
							  int main(void) {
							    string s = "HI!";
							    // or %c is valid. Strings are arrays of chars but also be expressed as int
							    printf("%i %i %i\n", s[0], s[1], s[2]);
							  }
							  ```
						- {{youtube-timestamp 6318}} Each string is just an array of chars
							- ```c
							  int main(void) {
							    string s = "HI!";
							    string t = "BYE!";
							  
							    printf("%s\n", s);
							    printf("%s\n", t);
							  }
							  ```
							- Each square being a byte:
							  ![image.png](../assets/image_1678795894869_0.png)
						- {{youtube-timestamp 6428}} How to initialise an array of strings in ((640c8362-cdc6-44a3-b991-a338f1d05b5a)) (`arrayType varName[arrayLength]`)
							- ```c
							  int main(void) {
							    // arrayType varName[arrayLength]
							    string words[2];
							    
							    words[0] = "HI!";
							    words[1] = "BYE!";
							  
							    printf("%s\n", words[0]);
							    printf("%s\n", words[1]);
							    // returns: HI!
							    // BYE!
							  }
							  ```
						- {{youtube-timestamp 6467}} You can access each character in an array of strings by using double bracket notation
							- ```c
							  int main(void) {
							    // Initalise with a length of 2
							    string words[2];
							    
							    words[0] = "HI!";
							    words[1] = "BYE!";
							  
							    printf("%c%c%c\n", words[0][0], words[0][1], words[0][2]);
							    printf("%c%c%c\n", words[1][0], words[1][1], words[1][2], words[1][3]);
							    // returns: HI!
							    // BYE!
							  }
							  ```
						- {{youtube-timestamp 6562}} There's no double `\0` to end an array of strings, it's just one `\0` for the last array item. This is why you can't figure out the length of an array once it's initialised, but you can for a `string`. Strings are special and end with `0`, whereas arrays don't have a special delimiter
							- ![image.png](../assets/image_1678795691630_0.png)
						- {{youtube-timestamp 6652}} How to get the length of a string using a while loop in ((640c8362-cdc6-44a3-b991-a338f1d05b5a))
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void) {
							    string name = get_string("What's your name? ");
							    
							    int n = 0;
							    while (name[n] != '\0') {
							      n++
							    }
							    printf("%i\n", n);
							  }
							  ```
						- {{youtube-timestamp 6788}} There's a library for `string` functions in ((640c8362-cdc6-44a3-b991-a338f1d05b5a)) called [`string.h`](https://manual.cs50.io/#string.h)
						- {{youtube-timestamp 6809}} `strlen` is the function in `string.h` to get string length
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  #include <string.h>
							  
							  int main(void) {
							    string name = get_string("What's your name? ");
							    int n = strlen(name);
							    printf("%i\n", n);
							  }
							  ```
						- {{youtube-timestamp 6878}} [`ctype.h`](https://manual.cs50.io/#ctype.h) library - for data types in C
							- The difference between a lowercase letter and it's uppercase version is always 32 in ASCII
							- ASCII chart
							  id:: 64634976-9fee-489a-b73a-2349e05c35ee
								- ![image.png](../assets/image_1678811769692_0.png)
								- Related: ((646349b0-26df-4b6d-9ae4-46abda612f2f))
							- Make uppercase.c
								- ```c
								  #include <cs50.h>
								  #include <stdio.h>
								  #include <ctype.h>
								  
								  int main(void) {
								    string s = get_string("Before: ");
								    printf("After: ");
								    for (int i = 0; i < strlen(s); i++) {
								      // Loop through each character, check if it's a letter
								      if (s[i] >= 'a' && s[i] <= 'z') {
								        // Convert it to uppercase by reducing it by 32 - see ASCII chart
								        printf("%c", s[i] - 32);
								      } else {
								        printf("%c", s[i]);
								      }
								    }
								    printf("\n");
								  }
								  ```
							- {{youtube-timestamp 7208}} Version using the library `ctype` - using the `strlen` function
								- ```c
								  #include <cs50.h>
								  #include <stdio.h>
								  #include <ctype.h>
								  
								  int main(void) {
								    string s = get_string("Before: ");
								    printf("After: ");
								    for (int i = 0; i < strlen(s); i++) {
								        printf("%c", toupper(s[i]));
								    }
								    printf("\n");
								  }
								  ```
							- {{youtube-timestamp 7379}} The loop checking for the length of `s` each time is inefficient, wastes CPU cycles **(important)**
								- ```c
								  // Before
								  for (int i = 0; i < strlen(s); i++)
								    
								  // After
								  for (int i = 0, n = strlen(s); i < n; i++)
								  ```
					- ### Command-Line Arguments
					  id:: 64634975-ab05-48ed-9688-bd8ff6f2d619
						- {{youtube-timestamp 7549}} `void` in `int main(void)` means it takes no CLI arguments
						- {{youtube-timestamp 7627}} `argc` = argument count, `argv` = argument value? the strings you enter as CL arguments
							- ```c
							  int main(int argc, string argv[]) { 
							    string name = get_string("What's your name? "); 
							    printf("hello, %s\n", name);
							  }
							  ```
						- {{youtube-timestamp 7704}} How to make a basic CL argument in your program
							- ```c
							  int main(int argc, char *argv[]) { 
							    printf("hello, %s\n", argv[1]);
							  }
							  
							  // Running this via `./greet David`
							  // Returns: `hello, David`
							  ```
						- {{youtube-timestamp 7731}} `argv[0]` is always the name of the expression used to execute the program e.g. `./greet` here
						- {{youtube-timestamp 7786}} and `argc` = `2` (length), because you've entered 1 expression and 1 argument i.e. `./greet` and `name`
						- {{youtube-timestamp 7866}} Nowadays there's two official ways to define a main function:
							- ```c
							  // No CLI arguments
							  int main(void)
							    
							  // Yes CLI arguments
							  int main(int argc, string argv[])
							  ```
						- Related: ((642437fb-baa6-4c18-a3d1-596ecbccb6c4))
					- ### {{youtube-timestamp 8046}} Exit Status
						- 404 = not found
						- HTTP error code
						- {{youtube-timestamp 8141}} `int` means it'll return an integer, `0` by default (success)
							- ```c
							  int main(void)
							  ```
						- {{youtube-timestamp 8247}} `echo $?` can be run after executing a program (e.g. `./status` for `1` or `./status David` for `0`) to show the exit status of a program (showing what it returns)
						  id:: 642437fb-baa6-4c18-a3d1-596ecbccb6c4
							- ```c
							  int main(int argc, string argv[]) {
							    if (argc != 2) { 
							      printf("Missing command-line argument\n"); 
							      return 1;
							    }
							    else { 
							      printf("hello, %s\n", argv([1]);
							      return 0;
							    }
							  }
							  ```
					- ### {{youtube-timestamp 8379}} Cryptography
						- Transforming plaintext and key > via cipher (algorithm) > to ciphertext
						-
			- [CS50 2022 - Lecture 3 - Algorithms - YouTube](https://youtu.be/4oqjcKenCH8)
			  collapsed:: true
			  Searching: Linear Search, Binary Search. Sorting: Bubble Sort, Selection Sort, Merge Sort. Asymptotic Notation: *O* , Ω, Θ. Recursion.
				- Most important:
					- ((643a7163-4f01-4c96-8b4c-dc3701fcbddc))
					- For `check50` tool, ensure that there's no space before `\n`. It expects this style
				- {{video https://youtu.be/4oqjcKenCH8}}
					- ### {{youtube-timestamp 72}} Algorithms
					- ### {{youtube-timestamp 469}} Linear Search
						- Just starting at one end of the array and checking each sequentially
						- ```
						  For i from 0 to 26-1
						  	If 50 is behind doors[i]
						  		Return true
						  Return false
						  ```
					- ### {{youtube-timestamp 732}} Binary Search
						- Pre-requisite: the array has to be sorted
						- {{youtube-timestamp 856}} Keep looking in the middle of the selection of the array, then make a new subsection using the left or right half
						- ```
						  If no doors left
						  	Return false
						  If 50 is behind doors[middle]
						  	Return true
						  Else if 50 < doors[middle]
						  	Search left half
						  Else if 50 > doors[middle]
						  	Search right half
						  ```
						- {{youtube-timestamp 954}}
							- ```c
							  If no doors left
							  	Return false
							  If 50 is behind doors[middle]
							  	Return true
							  Else if 50 < doors[middle]
							  	Search doors[0] through doors[middle - 1]
							  Else if 50 > doors[middle]
							  	Search doors[middle + 1] through doors[length - 1]
							  ```
					- ### Running Time
						- {{youtube-timestamp 1286}} Big O notation
							- ![image.png](../assets/image_1680528039104_0.png)
						- {{youtube-timestamp 1308}} O(n/2) is irrelevant because it's the same shape
							- ![image.png](../assets/image_1680528122163_0.png)
						- {{youtube-timestamp 1351}} Upper-bound, how long an algorithm might take in worst case scenario (slowest at top):
						  id:: 643a7163-086b-4ebe-8f88-d1ed28f62336
							- O(*n*²)
							  id:: 642ad30b-9fff-4cba-ac25-bb3dd0262cee
							  Selection sort
							- O(*n* log *n*)
							  id:: 643a7163-2f8f-4e0c-829e-af060359b08f
							  Merge sort
							- O(*n*)
							  id:: 642ad322-cf6c-4360-9e3e-a4e24f264d56
							  Linear search
							- O(log *n*)
							  id:: 642ad32c-4d27-468c-b0c5-d9f5e5eca51c
							  Binary search
							- O(1)
							  id:: 64634975-e3c4-4a85-9a40-6f58d87852e5
							  Finite number of steps, can even be say 999 steps. Regardless of how much underlying data there is
						- {{youtube-timestamp 1432}} Linear search is ((642ad322-cf6c-4360-9e3e-a4e24f264d56)) whereas binary search is ((642ad32c-4d27-468c-b0c5-d9f5e5eca51c))
						- {{youtube-timestamp 1521}} Ω (omega) describes lower-bound of an algorithm (how fast it might be if it gets lucky first time)
						  id:: 643a7163-c0d5-4f5f-a110-81ab4d4005b0
							- Ω(*n*²)
							  id:: 643a7163-5a80-4690-b11f-70282d809ee5
							  Selection sort
							- Ω(*n* log *n*)
							  id:: 643a7163-a94c-42e2-aada-ea92c4f7fdf5
							- Ω(*n*)
							  id:: 643a7163-9507-4130-9c35-0f5fd422c7b2
							  Bubble sort
							- Ω(log *n*)
							- Ω(1)
							  Linear search or binary search might get lucky and get it on first check
						- {{youtube-timestamp 1656}} Θ (theta) can be used if an algorithm has identical Big *O* and Ω values
							- Θ(*n*²)
							  id:: 643a7163-0b32-48c8-aca8-89f2a30c7ef9
							- Θ(*n* log *n*)
							  id:: 643a7163-2f40-496b-82dc-83383361a586
							- Θ(*n*)
								- e.g. counting all students in a room
							- Θ(log *n*)
							  id:: 643a7163-ff68-4fad-b85d-7d75741a1847
							- Θ(1)
					- ### search.c
						- {{youtube-timestamp 1796}} Can use curley brackets when initialising an array to get the compiler to allocate you that much memory for the array
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    int numbers[] = {20, 500, 10, 5, 100, 1, 50};
							  }
							  ```
								- Alternatively:
								  ```c
								  int numbers[7];
								  numbers[0] = 20;
								  numbers[1] = 500; 
								  // etc
								  ```
						- {{youtube-timestamp 1891}} Example linear search
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    
							    int numbers[] = {20, 500, 10, 5, 100, 1, 50};
							    
							    int n = get_int("Number: ");
							    // Linear search
							    for (int i = 0; i < 7; i++)
							    {
							      if (numbers[i] == n)
							      {
							        printf("Found\n");
							        return 0;
							      }
							    }
							    printf("Not found\n");
							    return 1;
							  }
							  ```
						- {{youtube-timestamp 2049}} [`strcmp`](https://manual.cs50.io/3/strcmp) is needed to compare strings inside arrays
						  id:: 643a7163-4f01-4c96-8b4c-dc3701fcbddc
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    string strings[] = {"battleship", "boot", "cannon", "iron", "thimble", "top hat"};
							    
							    string s = get_string("String: ");
							    // Linear search
							    for (int i = 0; i < 7; i++)
							    {
							      // The line `if (strings[i] == s)` wouldn't work because strings are arrays of chars?
							      // Instead use strcmp:
							      if (strcmp(strings[i], s) == 0)
							      {
							        printf("Found\n");
							        return 0;
							      }
							    }
							    printf("Not found\n");
							    return 1;
							  }
							  ```
						- {{youtube-timestamp 2261}} Segmentation fault error occurs when you touched memory you shouldn't have e.g. looped too many times
						- {{youtube-timestamp 2490}} related: ((642437fb-baa6-4c18-a3d1-596ecbccb6c4))
						- {{youtube-timestamp 2577}} Storing both names and numbers for a phonebook
							- `phonebook.c`
							  ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  #include <string.h>
							  
							  int main(void)
							  {
							    string names[] = {"Carter", "David"};
							    string numbers[] = {"+1-617-495-1000", "+1-949-468-2750"};
							    
							    string name = get_string("Name: ");
							    for (int i = 0; i < 2; i++)
							    {
							      if (strcmp(names[i], name) == 0)
							      {
							        printf("Found %s\n", numbers[i]);
							        return 0;
							      }
							    }
							    printf("Not found\n");
							    return 1;
							  }
							  ```
						- {{youtube-timestamp 2818}} Cons of the previous design:
							- Difficult to update the phonebook if it scales to much more users
							- Not built to ensure the order of arrays stays the same
					- ### structs
						- {{youtube-timestamp 2941}} Arrays are one type of data structure, but we can invent our own using primitives like string and int
						- {{youtube-timestamp 3023}} How to create a struct - example
							- ```c
							  typedef struct // Create own definition + the type of it is a 'structure'
							  {
							    string name;
							    string number;
							  }
							  person; // Name of type that you're creating
							  ```
						- {{youtube-timestamp 3090}} Integrating a struct by refactoring the previous example - uses dot notation
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  #include <string.h>
							  
							  typedef struct 
							  {
							    string name;
							    string number;
							  }
							  person;
							  
							  int main(void)
							  {
							    person people[2];
							    
							    people[0].name = "Carter";
							    people[0].number = "+1-617-495-1000";
							    
							    people[1].name = "David";
							    people[1].number = "+1-622-413-1001";
							   
							    string name = get_string("Name: ");
							    for (int i = 0; i < 2; i++)
							    {
							      if (strcmp(people[i].name, name) == 0)
							      {
							        printf("Found %s\n", people[i].number);
							        return 0;
							      }
							    }
							    printf("Not found\n");
							    return 1;
							  }
							  ```
					- ## {{youtube-timestamp 3532}} Sorting
						- e.g. sort the numbers into ascending order (initially `72541603`)
						- Short description of sorting algos examined:
							- Selection sort iterates through the unsorted portions of a list, selecting the smallest element each time and moving it to its correct location.
							- Bubble sort compares pairs of adjacent values one at a time and swaps them if they are in the incorrect order. This continues until the list is sorted.
							- Merge sort recursively divides the list into two repeatedly and then merges the smaller lists back into a larger one in the correct order.
						- ### {{youtube-timestamp 3776}} Selection Sort
							- {{youtube-timestamp 3808}} Analyses the entire list to find the smallest number, then swaps that number with the number at position `0`
							- {{youtube-timestamp 3992}} Pseudocode version:
								- ```c
								  For i from 0 to n-1
								    Find smallest number between numbers[i] and numbers[n-1]
								    Swap smallest number with numbers[i]
								  ```
						- ### {{youtube-timestamp 4033}} Bubble Sort
							- {{youtube-timestamp 4076}} Just compares one number with the next number
							- {{youtube-timestamp 4160}} Largest numbers "bubble" their way to the top
							- {{youtube-timestamp 4218}} To confirm when to stop, do another full loop and when there's no swaps then stop
						- ### {{youtube-timestamp 4276}} Comparing Algorithms
							- {{youtube-timestamp 4356}} To calculate efficiency of algorithms vs each other, count how many comparisons took place
							- {{youtube-timestamp 4473}} Algorithm efficiency of selection sort = *n*(*n* - 1)/2 **->** (*n²* - 1)/2 **->** *n²*/2 - *n*/2
								- i.e. `(n - 1) + (n - 2) + (n - 3) + ... + 1`
								- Because to get the first smallest number is `(n - 1)`
								- To get the second smallest number is `(n - 2)`
								- etc
							- {{youtube-timestamp 4485}} It's basically ((642ad30b-9fff-4cba-ac25-bb3dd0262cee)) (you get to ignore that it gets divided by 2 and subtract a number, because when *n* is really large it doesn't really matter)
								- Related: ((643a7163-086b-4ebe-8f88-d1ed28f62336))
							- {{youtube-timestamp 4574}} Selection sort is ((643a7163-5a80-4690-b11f-70282d809ee5)), so because it's also ((642ad30b-9fff-4cba-ac25-bb3dd0262cee)) that makes it ((643a7163-0b32-48c8-aca8-89f2a30c7ef9))
								- Related: ((643a7163-c0d5-4f5f-a110-81ab4d4005b0))
							- {{youtube-timestamp 4709}} Bubble sort is ((642ad30b-9fff-4cba-ac25-bb3dd0262cee)) and ((643a7163-9507-4130-9c35-0f5fd422c7b2))
						- ((642437fb-c486-462e-9f9c-e508fcfda137))
					- ### {{youtube-timestamp 5246}} Recursion
						- Recursion is the ability of a function to call itself
						- {{youtube-timestamp 5555}} Pyramid example - print bricks in a pyramid shape
							- ```c#
							  #include <cs59.h>
							  #include <stdio.h>
							  
							  void draw(int n);
							  
							  int main(void) 
							  { 
							    int height = get_int("Height: "); 
							    draw(height); 
							  }
							  
							  void draw(int n)
							  {
							    for (int i = 0; i < n; i++)
							    {
							      for (int j = 0; j < i + 1; j++) 
							      {
							        printf("#");
							      }
							      printf("\n");
							    }
							  }
							  ```
						- {{youtube-timestamp 5715}} How to do the previous example recursively
							- ```c#
							  #include <cs59.h>
							  #include <stdio.h>
							  
							  void draw(int n);
							  
							  int main(void) 
							  { 
							    draw(1);
							  }
							  
							  void draw(int n)
							  {
							    // Base case
							    if (n <= 0) 
							    {
							      return;
							    }
							    
							    draw(n + 1);
							    
							    for (int i = 0; i < n; i++)
							    {
							      printf("#");
							    }
							    printf("\n");
							  }
							  ```
						- {{youtube-timestamp 6060}} Base classes can be used to exit a recursive program at the appropriate time
							- Example in previous example
								- ```c#
								  if (n <= 0) 
								  {
								    return;
								  }
								  ```
					- ### {{youtube-timestamp 6280}} Merge Sort
					  id:: 642437fb-c486-462e-9f9c-e508fcfda137
						- Depends on recursion
						- Pseudocode
							- ```
							  If only one number
							  	Quit
							  Else
							    Sort left half of numbers
							    Sort right half of numbers
							    Merge sorted halves
							  ```
						- {{youtube-timestamp 6544}} You keep looking at the left half, of the left half, of the left half until you end up with 2 numbers. Then compare and sort those.
						- {{youtube-timestamp 6662}} Then sort the next pair -> then the merge stage involves comparing the first numbers of each half, and each digit after that
						- {{youtube-timestamp 7038}} Merge sort is ((643a7163-2f40-496b-82dc-83383361a586)), because it's ((643a7163-2f8f-4e0c-829e-af060359b08f)) and ((643a7163-a94c-42e2-aada-ea92c4f7fdf5))
					- Asymptotic Notation: *O* , Ω, Θ.
				- Practical exercises learnings
					- `#define MAX 9` = create a constant named `MAX` whose value is `9`
			- [CS50 2022 - Lecture 4 - Memory](https://youtu.be/AcWIE9qazLI)
			  collapsed:: true
			  Pointers. Segmentation Faults. Dynamic Memory Allocation. Stack. Heap. Buffer Overflow. File I/O. Images.
				- Most important
					- Pointers
						- ((64634975-2aac-4c24-8965-f1768f785446))
				- Practical exercise learnings
					- 2x hexadecimal (base-16) digits (pair e.g. 00 to FF) are 8 bits/1 byte and is represented in binary (base-2) like so e.g. `00000000`,`11111111`
					- The prefix `0x` is often used to indicate that a value is in hexadecimal format e.g. first pair is `0x00`, or `0xff`
					- RGB colour code is 24 bits per pixel (3x hexadecimal pairs)
					- Bitmaps use 1 bit per pixel (black or white only), whereas BMP supports up to 32-bit. JPEG and PNG support 24 bit, possibly more
					- ### filter-less
						- Needed to use ((64634976-97f8-4066-9f8d-6cf3c440021f)), not `int` as the var type for grayscale
						- Needed to use `round` function from `<math.h>` to help convert ((64634976-97f8-4066-9f8d-6cf3c440021f)) back into `int`
						- Use them together e.g. `float blurB = round(Btotal / 9);` for most effectiveness
						- `continue` keyword - works like `break` in a loop except Instead of forcing termination, it forces the next iteration of the loop to take place, skipping any code in between.
					- ### recover
						- ((64634975-ab05-48ed-9688-bd8ff6f2d619))
						- ((64b50f8f-8f45-4d93-8809-5e40140bd5a8))
							- Example
								- ```c
								  sprintf(buffer, "hello, %s\n", i);
								  ```
						- ((6483382a-2a6d-4412-8896-66879d1f596f))
						- `typedef uint8_t BYTE;`
						  Define a `BYTE` for later use
							- `uint8` = unsigned integer of length 8 bits
							- Note: also need to import the relevant library via `#include <stdint.h>`
						- Standard ((64b50f8f-d179-429d-b234-ffb5642d9615)) loop
							- ```c
							  while (fread(buffer, 1, BLOCK_SIZE, raw_file) == BLOCK_SIZE)
							  {
							  }
							  ```
						- Write a filename
							- ```c
							  image = fopen(filename, "w");
							  ```
						- To specify a string should be in the format `001.jpg`
							- ```c
							  sprintf(filename, "%03i.jpg", count);
							  ```
							- In C, the format specifier `%03i` is used in conjunction with the `printf()` function to format and print an integer value with leading zeros. Let's break down what each part of `%03i.jpg` means:
								- `%` - It indicates the start of a format specifier.
								- `0` - It specifies that leading zeros should be used for padding.
								- `3` - It specifies the minimum width of the printed value. In this case, it means the minimum width is 3 characters.
								- `i` - It specifies that the argument to be printed is an integer.
								- `.jpg` - It is a string literal that will be printed as part of the output.
							- So, when you use `%03i.jpg` as a format specifier with `printf()`, it means that the integer value will be printed with leading zeros to make it three characters wide, followed by the string ".jpg". This is often used in scenarios where you want to generate file names with sequential numbers padded with zeros, such as "001.jpg", "002.jpg", and so on.
				- {{video https://youtu.be/AcWIE9qazLI}}
					- ## {{youtube-timestamp 72}} Memory
						- {{youtube-timestamp 189}} Bitmap for images in just binary
					- ## {{youtube-timestamp 419}} Hexadecimal
						- {{youtube-timestamp 414}} RGB is max 255, 255, 255. Alternatively can be represented as hexadecimal eg. FFFFFF
						- {{youtube-timestamp 487}} Hexadecimal is 0-9 A-F, AKA base-16
						- {{youtube-timestamp 766}} Hexadecimal maps very easily to binary
					- ## {{youtube-timestamp 927}} Addresses
						- {{youtube-timestamp 1042}} Convention to indicate a number is hexadecimal is prefixing it with `0x` e.g. 0x5, 0xF
						  id:: 64634975-2e97-4e31-9123-f0dd5694ceff
						- {{youtube-timestamp 1268}} `&` prefix allows us to get the address of a variable in memory
						- {{youtube-timestamp 1291}} `*` (dereference operator) allows us to go to a specific address in memory
						- {{youtube-timestamp 1328}} `%p`, and `&` before `n` allows us to print the address in memory
							- ```c
							  int main(void)
							  {
							    int n = 50;
							    printf("%p\n", &n);
							  }
							  
							  // returns `0x7fff84f2ff0c` for example
							  ```
					- ## {{youtube-timestamp 1382}} Pointers
						- {{youtube-timestamp 1466}} It's a variable which contains the address of some value AKA it's an address in memory
						- {{youtube-timestamp 1493}} Prefix variable names with `*` if it's going to be a pointer (i.e. you called a variable's address using prefix `&`)
							- ```c
							  int main(void)
							  {
							    int n = 50;
							    int *p = &n;
							    printf("%p\n", p);
							  }
							  
							  // returns `0x7fff84f2ff0c` for example
							  ```
						- {{youtube-timestamp 1809}} Visual example of the previous example's variables in memory
						  collapsed:: true
							- ![image.png](../assets/image_1682362618360_0.png)
						- {{youtube-timestamp 1881}} Integers are 4 bits, but pointers are 8 bits
					- ## {{youtube-timestamp 2134}} Strings
						- {{youtube-timestamp 2205}} Recap of what strings look like in memory - ends with a null character `\0`
							- ![image.png](../assets/image_1682362969278_0.png)
						- {{youtube-timestamp 2302}} When you create a var (e.g. `string s = "HI!"`) you're making a pointer to the first character (`H`/`s[0]`)
						- {{youtube-timestamp 2439}} `string` is actually a CS50 struct. In C it actually is instead called `char *`, e.g:
						  ```c
						  string s = "HI!"
						  char *s = "HI!"
						  ```
						- {{youtube-timestamp 2585}} They made it using `typedef char *string;`
						- {{youtube-timestamp 2760}} How to go to an address using a variable. Code changed from `"%p", p` to `"%i", *p`. AKA dereferencing a pointer
						  id:: 64634975-2aac-4c24-8965-f1768f785446
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    int n = 50;
							    int *p = &n;
							    printf("%i\n", *p);
							  }
							  // returns: 50
							  ```
						- {{youtube-timestamp 2963}} `%p` always shows the pointer for the var
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    char *s = "HI!";
							    printf("%p\n", s);
							  }
							  ```
						- {{youtube-timestamp 3130}} `%s` can be used with `printf` string vars to call that var
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    char *s = "HI!";
							    printf("%s\n", s);
							  }
							  ```
						- {{youtube-timestamp 3264}} The pointer for a whole string var as well as the `0` index of that string are the same. `1` and other index isn't the same
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    char *s = "HI!";
							    printf("%p\n", s); // 0x999999999
							    printf("%p\n", &s[0]); // 0x999999999
							    printf("%p\n", &s[1]); // 0x333333333
							  }
							  ```
					- ## {{youtube-timestamp 3484}} Pointer Arithmetic
						- {{youtube-timestamp 3534}} To get the address of each character in a string, you can use `*` and pointer arithmetic
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    char *s = "HI!";
							    printf("%c\n", *s); // 0x999999999
							    printf("%c\n", *(s+1)); // 0x333333333
							    printf("%c\n", *(s+2)); // 0x777777777
							  }
							  ```
						- {{youtube-timestamp 3601}} Bracket notation is the syntactic sugar that is powered by pointer arithmetic underneath. We use square bracket notation because it's more readable
						- {{youtube-timestamp 3690}} One way to get a segmentation fault is by trying to access say the 50000th character in a string, because you're trying to access memory which isn't allocated to that string
						- {{youtube-timestamp 3806}} Using `%s` instead of `%c` as well as pointer arithmetic allows us to print only a substring (until the null symbol `\0`)
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  
							  int main(void)
							  {
							    char *s = "HI!";
							    printf("%s\n", s); // returns: HI!
							    printf("%s\n", s+1); // returns: I!
							    printf("%s\n", s+2); // returns: !
							  }
							  ```
					- ## {{youtube-timestamp 3932}} Comparing Strings
						- {{youtube-timestamp 3973}} `strcmp` had to be used last week to compare strings because you can't just use equality operator `==` as they both point to different memory addresses
						- {{youtube-timestamp 4388}} `strcmp` solves this issue by going to the actual memory address then comparing it character by character
							- ```c
							  #include <cs50.h>
							  #include <stdio.h>
							  #include <string.h>
							  
							  int main(void)
							  { 
							    string s = get_string("s: "); 
							    string t = get_string("t: ");
							    
							    // if (strcmp(s, t) == 0)
							    if (s == t) 
							    { 
							      printf ("Same\n"); 
							    } 
							    else 
							    { 
							      printf ("Different\n");
							    }
							  }
							  ```
							- These strings point to different parts of memory (visual example)
							  collapsed:: true
								- ![image.png](../assets/image_1682437853396_0.png)
						- {{youtube-timestamp 4493}} If you instead use `if (*s == *t) ` instead of `if (s == t)` that's basically what `strcmp` does, except also looping over every character for each
					- ## {{youtube-timestamp 4681}} Copying
						- {{youtube-timestamp 4809}} Assigning a variable to another one just copies the pointer - the second var points to the same address:
							- ```c
							  string s = "hi";
							  string t = s; // returns: "hi"
							  
							  s = "bye";
							  printf("%s", s); // returns: "bye"
							  printf("%s", t); // returns: "bye"
							  ```
						- {{youtube-timestamp 5012}} ((64b5bdf0-8cba-4b0a-9c07-0c8d0e886628)) and ((64b5bdf0-77d0-4577-bed4-072c62636b03)) are needed for copying
						- {{youtube-timestamp 5125}} Current libraries
							- ```c
							  #include <cs50.h>
							  #include <ctype.h>
							  #include <stdio.h>
							  #include <stdlib.h> // <-- newest, needed for malloc and free
							  #include <string.h>
							  ```
						- {{youtube-timestamp 5133}} `malloc(strlen(s) + 1)` can be used to allocate a free chunk of memory equal to the size of the original var `s` (+1 is for the null char `\0`)
							- ```c
							  int main(void)
							  {
							    string s = get_string("s: ");
							    string t = malloc(strlen(s) + 1);
							  }
							  ```
						- {{youtube-timestamp 5220}} Next copy every character into the new string var
						  collapsed:: true
							- ```c
							  for (int i = 0; i < strlen(s) + 1; i++)
							  {
							    t[i] = s[i];
							  }
							  ```
						- {{youtube-timestamp 5550}} Better version that doesn't call `strlen` function every loop
						  collapsed:: true
							- ```c
							  for (int i = 0, n = strlen(s) + 1; i < n; i++)
							  {
							    t[i] = s[i];
							  }
							  ```
						- {{youtube-timestamp 5640}} Best version - there's a function called `strcpy` which can be used instead of writing it out manually
							- ```c
							  int main(void)
							  {
							    string s = get_string("s: ");
							    string t = malloc(strlen(s) + 1); /// for int there's no need for the `+ 1`, string however has a null char at the end
							    
							    strcpy(t, s);
							  }
							  ```
						- {{youtube-timestamp 5765}} Prevent accidentally having too much in a string by checking for null (`if (s == NULL) return 1;`)
							- ```c
							  int main(void)
							  {
							    string s = get_string("s: ");
							    
							    if (s == NULL)
							    {
							      return 1;
							    }
							    
							    string t = malloc(strlen(s) + 1);
							    if (t == NULL)
							    {
							      return 1;
							    }
							    
							    strcpy(t, s);
							    
							    printf("%s", s);
							    printf("%s", t);
							    
							    return 0;
							  }
							  ```
						- {{youtube-timestamp 5824}} Use `free` also after using `malloc`
						  Note: when the program exits it'll automatically free the memory. But it's best practice to `free` throughout, especially if it's a long-running program
							- ```c
							  strcpy(t, s);
							    
							    printf("%s", s);
							    printf("%s", t);
							    
							    free(t);
							  
							    return 0;
							  }
							  ```
					- ## {{youtube-timestamp 5933}} Valgrind
						- {{youtube-timestamp 5951}} Unfinished example
							- ```c
							  #include <stdio.h>
							  #include <stdlib.h>
							  
							  int main(void)
							  {
							    int *x = malloc();
							  }
							  ```
						- {{youtube-timestamp 6148}} Valgrind can detect obvious memory bugs e.g. `valgrind ./myprogram`
					- ## {{youtube-timestamp 6379}} Garbage Values
						- {{youtube-timestamp 6456}} If you allocate an array but don't assign values to it, it will be filled with garbage values. This will contain values from previous functions, libraries, etc. It doesn't initialise as null
							- ```c
							  int main(void)
							  {
							    int scores[1024];
							    for (int i = 0: i > 1024; i++)
							    {
							    	printf("%i\n", scores[i]);
							    }
							  }
							  ```
					- ## {{youtube-timestamp 6552}} Pointer Fun with Blinky
						- {{youtube-timestamp 6586}} next
						- {{youtube-timestamp 6713}} Initialising pointers (e.g. `int* x;`) doesn't point them anywhere yet - need to create pointees
						- {{youtube-timestamp 6722}} Next allocate memory e.g. `x = malloc(sizeof(int))` - otherwise it'll have a garbage value
						- {{youtube-timestamp 6722}} Then dereference the pointer `*x` to store the number `42`in it's pointee
							- ```c
							  *x = 42;
							  ```
						- {{youtube-timestamp 6810}} To make another var point to the same pointee, use `y = x;`
						- {{youtube-timestamp 6823}} And if you want to change the value for `y`, can use `*y = 13;`. Note: previous step is required
					- ## {{youtube-timestamp 6902}} Swap
						- {{youtube-timestamp 7013}} If you want two variables to swap the values they store with each other, you basically need a third empty variable to temporarily store the contents of A before you move the data of B to container A
						- {{youtube-timestamp 7023}} Code example version A (doesn't work) - uses values
							- ```c
							  void swap(int a, int b)
							  {
							    int tmp = a;
							    a = b;
							    b = tmp;
							  }
							  ```
						- {{youtube-timestamp 7318}} Swap holds this data in this order:
						  collapsed:: true
							- Machine code
							- Globals - i.e. global vars
							- Heap - where `malloc` gets memory from. In a column of memory it gets allocated vertically downwards
							- Stack - where functions store variables and arguments. In a column of memory it gets allocated vertically upwards
						- {{youtube-timestamp 7617}} Code version B (working) - instead uses references
							- ```c
							  void swap(int *a, int *b)
							  {
							    int tmp = *a;
							    *a = *b;
							    *b = tmp;
							  }
							  ```
							- Variables are locally scoped
						- {{youtube-timestamp 7805}} To call this function use `swap(&x, &y);`
					- ## {{youtube-timestamp 7893}} Overflow
						- {{youtube-timestamp 7937}} Buffer overflows e.g. stack overflow, heap overflow. When your memory gets too full and causes bugs in other parts of memory
					- ## {{youtube-timestamp 7990}} scanf
						- {{youtube-timestamp 8036}} `scanf` scans the users keyboard for input
						- {{youtube-timestamp 8089}} New function - replacement for `get_int` (text prompt asking for an int value)
							- ```c
							  int main(void)
							  {
							    int x;
							    printf("x: ");
							    scanf("%i", &x);
							    printf("x: %i\n", x);
							  }
							  ```
						- {{youtube-timestamp 8146}} Function replacement for `get_string`
							- ```c
							  int main(void)
							  {
							    char s[4];
							    printf("s: ");
							    scanf("%s", s);
							    printf("s: %s\n", s);
							  }
							  ```
					- ## {{youtube-timestamp 8446}} Phonebook
						- {{youtube-timestamp 8475}} Saving names and numbers to a CSV file
						  id:: 6483382a-2a6d-4412-8896-66879d1f596f
							- ```c
							  int main(void)
							  {
							    FILE *file = fopen("phonebook.csv", "a");
							    
							    string name = get_string("Name: "); 
							    string number = get_string("Number: ");
							    
							    fprintf(file, "%s,%s\n", name, number);
							    
							    fclose(file);
							  }
							  ```
						-
					- Pointers. Segmentation Faults. Dynamic Memory Allocation. Stack. Heap. Buffer Overflow. File I/O. Images.
			- [CS50 2022 - Lecture 5 - Data Structures - YouTube](https://youtu.be/X8h4dq9Hzq8)
			  id:: 64634975-edb5-400f-bfe6-bb629801f70c
			  collapsed:: true
			  Abstract Data Types. Queues, Stacks. Linked Lists. Trees, Binary Search Trees. Hash Tables. Tries.
				- Most important
					- ((64b9335b-3d6e-42d5-9830-bf7148d57a38))
				- Practical exercise learnings
					- ### Inheritance
						- ((64b5bdf0-8cba-4b0a-9c07-0c8d0e886628))
					- ### Speller
						- Asymptotic time
						  collapsed:: true
							- Theoretically, on input of size n, an algorithm with a running time of n is “asymptotically equivalent,” in terms of O, to an algorithm with a running time of 2n. Indeed, when describing the running time of an algorithm, we typically focus on the dominant (i.e., most impactful) term (i.e., n in this case, since n could be much larger than 2). In the real world, though, the fact of the matter is that 2n feels twice as slow as n.
							  
							  The challenge ahead of you is to implement the fastest spell checker you can! By “fastest,” though, we’re talking actual “wall-clock,” not asymptotic, time.
						- Defines
						  collapsed:: true
							- Example: `#define LENGTH 45`
							- Also notice our use of `#define`, a “preprocessor directive” that defines a “constant” called `LENGTH` that has a value of `45`. It’s a constant in the sense that you can’t (accidentally) change it in your own code. In fact, `clang` will replace any mentions of `LENGTH` in your own code with, literally, `45`. In other words, it’s not a variable, just a find-and-replace trick.
						- Makefiles
						  collapsed:: true
							- And, lastly, recall that `make` automates compilation of your code so that you don’t have to execute `clang` manually along with a whole bunch of switches. However, as your programs grow in size, `make` won’t be able to infer from context anymore how to compile your code; you’ll need to start telling `make` how to compile your program, particularly when they involve multiple source (i.e., `.c`) files, as in the case of this problem. And so we’ll utilize a `Makefile`, a configuration file that tells `make` exactly what to do. Open up `Makefile`, and you should see four lines:
							  collapsed:: true
								- The first line tells `make` to execute the subsequent lines whenever you yourself execute `make speller` (or just `make`).
								- The second line tells `make` how to compile `speller.c` into machine code (i.e., `speller.o`).
								- The third line tells `make` how to compile `dictionary.c` into machine code (i.e., `dictionary.o`).
								- The fourth line tells `make` to link `speller.o` and `dictionary.o` in a file called `speller`.
						- Your spell checker must not leak any memory. Be sure to check for leaks with `valgrind`.
						- [strcasecmp](https://manual.cs50.io/3/strcasecmp)
						  Compare two strings ignoring case
						- Good generic way to loop over any string
							- ```c
							  for (int i = 0; word[i] != '\0'; i++)
							  {
							  }
							  ```
				- {{video https://www.youtube.com/watch?v=X8h4dq9Hzq8}}
					- ### {{youtube-timestamp 193}} Stacks and Queues
						- {{youtube-timestamp 217}} Queues are FIFO (First In First Out) e.g. queueing for cashier, message queues
						- {{youtube-timestamp 272}} Two functions of queues: enqueue (add item to end of queue) and dequeue (remove item from start of queue)
						- {{youtube-timestamp 319}} Stacks are not FIFO - LIFO (Last In First Out) e.g. piling chairs in a stack, email inbox
						- {{youtube-timestamp 447}} Two functions of stacks: push (add item to top of stack) and pop (add item to top of stack)
						- {{youtube-timestamp 482}} Example typedef of a stack. Not suitable?
							- ```c
							  const int capacity = 50;
							  
							  typedef struct
							  {
							    person people[CAPACITY]; // max size
							    int size; // current size
							  }
							  stack;
							  ```
					- ### {{youtube-timestamp 843}} Resizing Arrays
						- {{youtube-timestamp 1038}} If trying to resize an array it's not possible normally if the next bits are already in use. A workaround is used. Otherwise involve having to move to a new memory address
						- {{youtube-timestamp 1338}} Instead of using bracket notation use `malloc` to assign how much memory you need. This way it can more dynamically adjust to the size requirements
							- ```c
							  // Old version
							  int list[4];
							  
							  // New version
							  #include <stdlib>h>
							  
							  int *list = malloc(3 * sizeof(int))
							  if (list == NULL) 
							  {
							    return 1;
							  }
							  ```
						- {{youtube-timestamp 1583}} If you need to later increase the size of malloc, can use a bigger `tmp` variable, a loop to copy it from the original store to `tmp`. You can't just create a new line with `int *list = malloc(3 * sizeof(int))` as Valgrind will complain you've lost memory
							- ```c
							  int *tmp = malloc(4 * sizeof(int));
							  
							  if (tmp == NULL)
							  {
							    free(list);
							    return 1;
							  }
							  
							  for (int i = 0; i < 3; i++)
							  {
							    tmp[i] = list[i];
							  }
							  
							  free(list);
							  list = tmp;
							  ```
						- {{youtube-timestamp 2012}} `realloc` should be used instead. It does the copy process for you
							- ```c
							  int *tmp = malloc(4 * sizeof(int));
							  
							  // Remove the for loop
							  
							  int *tmp = realloc(list, 4 * sizeof(int));
							  
							  list = tmp;
							  ```
						- {{youtube-timestamp 2176}} You should still use `tmp` values with `realloc` to prevent a memory leak
					- ### {{youtube-timestamp 2304}} Linked Lists
						- {{youtube-timestamp 2398}} `->` operator is equivalent using both `.` + `*`
						  id:: 64b9335b-3d6e-42d5-9830-bf7148d57a38
							- `*` is used for multiplication, declaring pointers, dereferencing pointers (create it and then go to that address)
							- `->` is used whenever you want to use both `*` and `.` i.e. you want to go to a value, go to an address, then look inside a structure
							- e.g. these two are equivalent
								- ```c
								  person *parent0 = create_family(generations - 1);
								  p->parents[0] = create_family(generations - 1);
								  ```
						- {{youtube-timestamp 2513}} Linked lists involve values in multiple different areas in memory, and each contains the address of where the list continues (links forward to the next list). It starts off with an item which only contains an address and no other value
						- {{youtube-timestamp 3018}} `typedef` for each node (list) of a linked list. Note: written differently because it's self-referential
							- ```c
							  typedef struct node
							  {
							    int number;
							    struct node *next; // pointer to next list
							  }
							  node;
							  ```
						- {{youtube-timestamp 3262}} Advantages of linked lists is that it works faster than stacks/queues because `malloc`/`realloc` isn't needed to copy data when resizing. Additionally they don't need be contiguous in memory (unlike arrays), they can each be in different parts of memory
						- {{youtube-timestamp 3278}} Disadvantage is that
							- it uses more memory because each node needs to also store the address of where to point to next
							- Bracket notation no longer works - it's not easy for the computer to work out where each index position is
							- Binary search algorithm no longer possible because it's not possible to easily go to the middle of the array
						- {{youtube-timestamp 3489}} Working out how to create a linked list in code
							- ```c
							  node *list = NULL;
							  node *n = malloc(sizeof(node));
							  // Start at the first node and set the number property as `1`
							  n->number = 1 // Equivalent to `(*n).number = 1`
							  // Remove garbage value for `next`
							  n->next = NULL;
							  
							  // Another way to reference `n` (linked link start)
							  list = n;
							  
							  node *n = malloc(sizeof(node));
							  
							  ```
						- {{youtube-timestamp 4115}} Linked Lists work like stacks (they're LIFO). It only requires making the pointing the new node to the current last list, then having the list originator point to the new last list
						- {{youtube-timestamp 4211}} In code
							- ```c
							  typedef struct node
							  {
							    int number;
							    struct node *next; // pointer to next list
							  }
							  node;
							  
							  int main(argc. char *argv[])
							  {
							    node *list = NULL;
							    
							    for (int i = 1; i < argc; i++)
							    {
							      int number = atoi(argv[i]); // atoi = string to integer conversion
							      
							      node *n = malloc(sizeof(node));
							      if (n == NULL)
							      {
							        return 1;
							      }
							      n->number = number;
							      n->next = NULL; // get rid of garbage value
							      
							      n->next = list; 
							      list = n;
							    }
							    
							    // loop to print each node
							    node *ptr = list;
							    while (ptr != NULL)
							    {
							      printf("%i\n", ptr->number);
							      ptr = ptr->next; // Looks at the `next` field, which stores the address of the next node
							    }
							    
							    // Free up the memory
							    ptr = list;
							    while (ptr != NULL)
							    {
							      node *next = ptr->next;
							      free(ptr);
							      ptr = next;
							    }
							  }
							  
							  // run with `./list 1 2 3`
							  ```
						- {{youtube-timestamp 5044}} Alternative method using `for` loops
						- {{youtube-timestamp 5114}} Performance of searching linked lists is *O(n)*
					- ### {{youtube-timestamp 5448}} Trees
						- {{youtube-timestamp 5491}} Speed of binary search but dynamism of linked list
						- {{youtube-timestamp 5535}} Binary search trees
						- {{youtube-timestamp 5566}} Linked lists unlike arrays allow easily inserting elements into the middle of the data structure without having to copy and move data around, as you have to give a defined size to your array in advance
						- {{youtube-timestamp 5738}} Imagine you had a linked list of `1` to `7`. Then you can represent a binary search tree like:
							- ![image.png](../assets/image_1690968005839_0.png)
						- {{youtube-timestamp 5898}} typedef for `node` required
							- ```c
							  typedef struct node 
							  {
							    int number; 
							    struct node *left; 
							    struct node *right;
							  }
							  node;
							  ```
						- {{youtube-timestamp 5934}} Example binary search tree code
							- ```c
							  // first arg is root of tree, and int is what you're looking for
							  bool search(node *tree, int number) 
							  {
							    if (tree == NULL)
							    {
							      return false;
							    }
							    // is what you're looking for LESS than the tree's own number
							    else if (number < tree->number) 
							    {
							      // return the left branch's value for that level
							      return search(tree->left, number);
							    }
							    // if it isn't LESS than but is GREATER than, then return it
							    else if (number < tree->number) 
							    {
							      return search(tree->right, number);
							    }
							    // if it is instead the number in this node, then return it
							    else
							    {
							      return true;
							    }
							  }
							  ```
						- {{youtube-timestamp 6125}} Disadvantage: this method above uses a lot of memory
						- {{youtube-timestamp 6245}} To be a Binary Search Tree the values must be sorted beforehand
					- ### {{youtube-timestamp 6377}} Dictionaries
						- {{youtube-timestamp 6481}} Dictionaries are Word:Definition matches. They're an example of Key-Value pairs
						- {{youtube-timestamp 6568}} ((642ad32c-4d27-468c-b0c5-d9f5e5eca51c)) is realistic as ((64634975-e3c4-4a85-9a40-6f58d87852e5)) is unlikely
					- ### {{youtube-timestamp 6574}} Hashing and Hash Tables
						- {{youtube-timestamp 6594}} Transforms a value into a simpler version of that value
						- {{youtube-timestamp 6738}} Hash tables are a combination of arrays and linked lists in order to get the best of both worlds
						- {{youtube-timestamp 6896}} Arrays are used to sort values into buckets, then linked lists are used to hold all the values within a bucket
							- Example: phone contacts are sorted by first letter. Each of 26 letters is a bucket
							- Finding the correct bucket is ((642ad322-cf6c-4360-9e3e-a4e24f264d56)) (as it's 26 max). Finding the correct contact card within that bucket is
					- ### {{youtube-timestamp 7457}} Tries
						- Tries isn't ((642ad322-cf6c-4360-9e3e-a4e24f264d56)), it's actually ((64634975-e3c4-4a85-9a40-6f58d87852e5))
						- {{youtube-timestamp 7488}} It's short for "retrieval", but pronounced "try"
						- {{youtube-timestamp 7489}} It's a tree, where each of the nodes are an array
						- {{youtube-timestamp 7571}} Example storing a name: each letter is in a separate array, which means it scales well for searching any length name
							- Harry, Hagrid
							- ![image.png](../assets/image_1691071063402_0.png)
						- {{youtube-timestamp 7617}} It's speed is therefore ((64634975-e3c4-4a85-9a40-6f58d87852e5)) i.e. max *O(50)* runtime if that's the longest name allowed
						- {{youtube-timestamp 7734}} However it uses a lot more memory space. This is a common tradeoff for better performance
						- {{youtube-timestamp 7815}} Example data structure
							- ```c
							  typedef struct node 
							  {
							    char *number; 
							    struct node *children[26];
							  }
							  node;
							  ```
						- {{youtube-timestamp 7987}} It's performance is dependent on the length of the key only, not on the number of values stored
			- [CS50 2022 - Lecture 6 - Python - YouTube](https://youtu.be/5Jppcxc1Qzc)
			  Python: Functions, Arguments, Return Values; Variables; Boolean Expressions, Conditionals; Loops. Modules, Packages.
			- [CS50 2022 - Lecture 7 - SQL - YouTube](https://youtu.be/zrCLRC3Ci1c)
			  SQL: Tables; Types; Statements; Constraints; Indexes; Keywords, Functions; Transactions. Race Conditionals. SQL Injection Attacks
			- [CS50 2022 - Lecture 8 - HTML, CSS, JavaScript - YouTube](https://youtu.be/alnzFK-4xMY)
			  Internet: Routers; TCP/IP; DNS. HTTP: URLs, GET, POST. HTML: Tags; Attributes. Servers. CSS: Properties; Selectors. Frameworks. JavaScript: Variables; Conditionals; Loops. Events.
			- [CS50 2022 - Cybersecurity - YouTube](https://youtu.be/Kuy4cEXpXEE)
			- [CS50 2022 - Lecture 9 - Flask - YouTube](https://youtu.be/oVA0fD13NGI)
			  Flask. Route. Decorators. Requests, Responses. Sessions. Cookies.
			- [CS50 2022 - Lecture 10 - Emoji - YouTube](https://youtu.be/iXG0sXlzuF0)
			  Precision. Unicode: Emoji, Code Points, ZWJ.
		- [Learning Resources]
			- Recommended books
				- Hacker’s Delight, Second Edition
				  Henry S. Warren Jr.
				  Pearson Education, 2013
				  ISBN 0-321-84268-5
				- How Computers Work, Tenth Edition
				  Ron White
				  Que Publishing, 2014
				  ISBN 0-7897-4984-X
				- Programming in C, Fourth Edition
				  Stephen G. Kochan
				  Pearson Education, 2015
				  ISBN 0-321-77641-0
			- [submit50](https://cs50.readthedocs.io/submit50/) info
	- [CS50 2021](https://youtube.com/8mAITcNt710)
	  collapsed:: true
		- {{video https://youtu.be/8mAITcNt710}}
			- Meta
				- ⭐️ Course Contents ⭐️
				  collapsed:: true
					- {{youtube-timestamp 0}} Lecture 0 - Scratch
					- {{youtube-timestamp 6310}} Lecture 1 - C
					- {{youtube-timestamp 15203}} Lecture 2 - Arrays
					- {{youtube-timestamp 22843}} Lecture 3 - Algorithms
					- {{youtube-timestamp 31075}} Lecture 4 - Memory
					- {{youtube-timestamp 39797}} Lecture 5 - Data Structures
					- {{youtube-timestamp 47736}} Lecture 6 - Python
					- {{youtube-timestamp 56365}} Lecture 7 - SQL
					- {{youtube-timestamp 64855}} Lecture 8 - HTML, CSS, JavaScript
					- {{youtube-timestamp 73418}} Lecture 9 - ((646349df-3dfb-4073-baba-acbe4bb9506c))
					- {{youtube-timestamp 81541}} Lecture 10 - Emoji
					- {{youtube-timestamp 86570}} Cybersecurity
				- Slides, source code, and more at [CS50: Computer Science Courses and Programs from Harvard | edX](https://cs50.harvard.edu)
			- {{youtube-timestamp 0}} Lecture 0 - Scratch
			  id:: 63becc33-7a6a-4d5c-8222-f25ff15aa742
			  collapsed:: true
				- Related: ((63bae0c2-287d-4995-9929-1a277166e286))
			- {{youtube-timestamp 15203}} Lecture 2 - Arrays
			- {{youtube-timestamp 22843}} Lecture 3 - Algorithms
			- {{youtube-timestamp 31075}} Lecture 4 - Memory
			- {{youtube-timestamp 39797}} Lecture 5 - Data Structures
			- {{youtube-timestamp 47736}} Lecture 6 - Python
			- {{youtube-timestamp 56365}} Lecture 7 - SQL
			- {{youtube-timestamp 64855}} Lecture 8 - HTML, CSS, JavaScript
			- {{youtube-timestamp 73418}} Lecture 9 - Flask
			- {{youtube-timestamp 81541}} Lecture 10 - Emoji
			- {{youtube-timestamp 86570}} Cybersecurity
	- Original location
	- {{embed ((629ccb26-fd59-47b6-b479-60e77b734217))}}