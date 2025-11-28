- Meta
	- Goals:
		- [Fundamentals tag, 7 kyu or harder](https://www.codewars.com/kata/search/my-languages?q=&r%5B%5D=-6&r%5B%5D=-5&r%5B%5D=-4&r%5B%5D=-7&r%5B%5D=-3&r%5B%5D=-2&r%5B%5D=-1&tags=Fundamentals&xids=completed&beta=false&order_by=total_completed%20desc)
			- Keep going until I reach <30k completions questions, then sort by Popularity, then sort by Positive Feedback
- Takeaways
	-
	- ^^- converted everything below from CodeWars links to a link to a method and notes of how to utilise it - ^^
	- ((6408d44e-1000-4594-ab4b-8e5a18543479))
	  id:: 64024e31-432b-4873-bee4-82ed3e796a76
	  collapsed:: true
		- {{embed ((6408d44e-1000-4594-ab4b-8e5a18543479))}}
- Completed solutions
	- 1 kyu (1097 score)
	- 2 kyu (404 score)
	- 3 kyu (149 score)
	  collapsed:: true
		- [Battleship field validator](https://www.codewars.com/kata/52bb6539a4cf1b12d90005b7/javascript)
		  id:: 63cf8c8e-16ef-4c89-8d92-69f6e63c6f47
		  collapsed:: true
			- Best practice
				- ```javascript
				  function validateBattlefield(field) {
				    var hit = (row, col) => (row < 0 || col < 0 || row > 9 || col > 9) ? 0 : field[row][col];
				    for (var ships = [10,0,0,0,0], row = 0; row < 10; row++) {
				      for (var col = 0; col < 10; col++) {
				        if ( hit(row,col) ) {
				          if ( hit(row-1, col-1) || hit(row-1, col+1) ) return false; // Corner is touching
				          if ( hit(row-1, col  ) && hit(row  , col-1) ) return false; // Side is touching
				          if ( ( field[row][col] += hit(row-1, col) + hit(row, col-1) ) > 4 ) return false; // Ship is too long
				          ships[field[row][col]]++; ships[field[row][col] - 1]--;
				    } } }
				    return [0,4,3,2,1].every((s,i) => s == ships[i]);
				  }
				  ```
		- [Make a spiral | Codewars](https://www.codewars.com/kata/534e01fbbb17187c7e0000c6/javascript)
		  id:: 63cf8ec4-f24a-4619-83be-737562d558e6
		  collapsed:: true
			- Best practice
			  id:: 63f90938-2ffa-431b-8137-172d6187dc67
				- ```javascript
				  function spiralize(size) {
				    if (size == 2) return [ [1,1], [0,1] ];
				    if (size == 3) return [ [1,1,1], [0,0,1], [1,1,1] ];
				    var base = spiralize(size-2);
				    var res = [[],[]];
				    for (var i = 0; i < size; i++) (res[0].push(1)) && (res[1].push(0));
				    res[1][size-1] = 1;
				    for (var i = size-3; i >= 0; i--) {
				    	res.push(base[i].reverse().concat([0,1]));
				    }
				    res[size-1][size-2] = 1;
				    return res;
				  }
				  ```
	- 4 kyu (55 score)
	  collapsed:: true
		- [Human readable duration format | Codewars](https://www.codewars.com/kata/52742f58faf5485cae000b9a/javascript)
		  id:: 63cf8c5a-7866-4ccd-b12a-4590f3b36fcf
		  collapsed:: true
			- Best practice
				- ```javascript
				  function formatDuration (seconds) {
				    var time = { year: 31536000, day: 86400, hour: 3600, minute: 60, second: 1 },
				        res = [];
				  
				    if (seconds === 0) return 'now';
				    
				    for (var key in time) {
				      if (seconds >= time[key]) {
				        var val = Math.floor(seconds/time[key]);
				        res.push(val += val > 1 ? ' ' + key + 's' : ' ' + key);
				        seconds = seconds % time[key];
				      }
				    }
				   
				    return res.length > 1 ? res.join(', ').replace(/,([^,]*)$/,' and'+'$1') : res[0]
				  }
				  ```
	- 5 kyu (21 score)
	  id:: 634bc0c2-116f-4261-95d8-6bf05209b071
	  collapsed:: true
		- [Simple Pig Latin](https://www.codewars.com/kata/520b9d2ad5c005041100000f/train/typescript)
		  id:: 63a3afae-a986-4d53-acfa-a72c13b9fc86
		  collapsed:: true
			- Best practice
				- ```typescript
				  export const pigIt = (a : string) : string =>  {
				    return a.replace(/[a-z]+/ig, x => x.slice(1) + x[0] + "ay")
				  }
				  ```
					- ((63470fd1-332b-4ebf-965d-7073b319c11b))
			- My solution
				- ```typescript
				  export const pigIt = (a : string) : string =>  {
				    let wordPig
				    let reg = /[a-z]+/i;
				  
				    return a.split(' ').map((word) => {
				      return reg.test(word) ? word.slice(1) + word[0] + 'ay' : word
				    }).join(' ');
				  }
				  ```
					- `/[a-z]+/i` = check if character matches any letter, any case
					  id:: 63a3afb0-f24c-4e0f-9c9a-00caeffabb6b
						- id:: 63a48de6-a0bd-4ca1-8e6f-c84109bcaf43
						  #+BEGIN_WARNING
						  I got stuck on this problem for a while because I used `g` unnecessarily, when I was only trying to match one character
						  #+END_WARNING
					- Recommended more concise version:
						- ```typescript
						  export const pigIt = (a : string) : string => {
						    return a.split(' ').map(function(word){ 
						        return /[a-zA-Z]+/.test(word) ? word.slice(1) + word[0] + 'ay' : word;
						    }).join(' ');
						  }
						  ```
		- [Moving Zeros To The End](https://www.codewars.com/kata/52597aa56021e91c93000cb0/javascript)
		  id:: 63a37268-10b1-4c2e-add4-4ec8558517f1
		  collapsed:: true
			- Best practice
			  id:: 63baa387-1e08-4360-8992-cf71d823a78e
				- ```javascript
				  var moveZeros = function (arr) {
				    return arr.filter((x) => {
				      return x !== 0
				    }).concat(arr.filter(function(x) {
				      return x === 0;
				    }));
				  }
				  ```
					- Alternatively written like:
					  ```javascript
					  const moveZeros = (arr) => 
					      arr.filter(x => x !== 0).concat(arr.filter(x => x === 0));
					  ```
			- My solution
				- ```javascript
				  function moveZeros(arr) {
				    let item1;
				    for (let item of arr) {
				      if (item === 0) {
				        arr.splice(arr.indexOf(item), 1)
				        arr.push(0)
				      }
				    }
				    return arr
				  }
				  ```
		- [Valid Parentheses | Codewars](https://www.codewars.com/kata/52774a314c2333f0a7000688/javascript)
		  id:: 63cf9164-5abf-48eb-b525-6356c001e05f
		  collapsed:: true
			- Best practice
			  id:: 63f8fe4c-e392-47d9-8aa9-fb166942f2c0
				- ```javascript
				  function validParentheses(parens){
				    var n = 0;
				    for (var i = 0; i < parens.length; i++) {
				      if (parens[i] == '(') n++;
				      if (parens[i] == ')') n--;
				      if (n < 0) return false;
				    }
				    
				    return n == 0;
				  }
				  ```
		- [Human Readable Time | Codewars](https://www.codewars.com/kata/52685f7382004e774f0001f7/javascript)
		  id:: 63cf8fab-9e03-4a7f-bb01-6aaa6560f99c
		  collapsed:: true
			- Best practice
				- ```javascript
				  function humanReadable(seconds) {
				    var pad = function(x) { 
				      return (x < 10) ? "0"+x : x; 
				    }
				    return pad(parseInt(seconds / (60*60))) + ":" +
				           pad(parseInt(seconds / 60 % 60)) + ":" +
				           pad(seconds % 60)
				  }
				  ```
		- [Directions Reduction](https://www.codewars.com/kata/550f22f4d758534c1100025a/javascript)
		  id:: 63cf8891-e99e-4e5a-9cbe-9dc1e009b37a
		  collapsed:: true
			- My solution
			  collapsed:: true
				- ```javascript
				  export function dirReduc(arr: string[]): string[] { 
				    let y = 0;
				    let x = 0;
				    
				    arr.map((item) => {
				      switch (item) {
				          case 'NORTH': y++; break;
				          case 'SOUTH': y--; break;
				          case 'EAST': x++; break;
				          case 'WEST': x--; break;
				      }
				    })
				    console.log(`arr: `, arr)
				    console.log(`x:`, x)
				    console.log(`y:`, y)
				  
				    if (x === 0 && y === 0) {
				      return arr
				    }
				    
				    return arr.filter((item) => {
				      console.log(`item:`, item)
				      switch (item) {
				          case 'NORTH': 
				            if (y > 0) {
				              console.log('NORTH')
				              y--
				              return item
				            } else {
				              break
				            }
				          case 'SOUTH': 
				            if (y < 0) {
				              console.log('SOUTH')
				              y++
				              return item
				            } else {
				              break
				            }
				          case 'EAST':
				            if (x > 0) {
				              console.log('EAST')
				              x--
				              return item
				            } else {
				              break
				            }
				          case 'WEST': 
				            if (x < 0) {
				              console.log('WEST')
				              x++
				              return item
				            } else {
				              break
				            }
				    }})
				  }
				  ```
			- Best practice
			  id:: 9baa8144-5bc0-47ae-ad63-afdd84db3c7d
				- ```javascript
				  function dirReduc(plan) {
				    var opposite = {
				      'NORTH': 'SOUTH', 
				      'EAST': 'WEST', 
				      'SOUTH': 'NORTH', 
				      'WEST': 'EAST'
				    };
				    
				    return plan.reduce((dirs, dir) => {
				        if (dirs[dirs.length - 1] === opposite[dir])
				          dirs.pop();
				        else
				          dirs.push(dir);
				        return dirs;
				      }, []);
				  }
				  ```
	- 6 kyu (8 score)
	  collapsed:: true
		- [Find the unique number](https://www.codewars.com/kata/585d7d5adb20cf33cb000235/javascript)
		  id:: 6402327c-0104-4468-8317-98fcece06095
		  collapsed:: true
			- My solution
			  collapsed:: true
				- ```javascript
				  function findUniq(arr) {
				    
				    let set = new Set();
				    let nonUniq
				    
				    set.add(arr[0]).add(arr[1])
				    
				    if (set.size === 1) {
				      nonUniq = arr[0]
				      for (let i = 2; i < arr.length; i++) {
				        if (arr[i] !== nonUniq) {
				          return arr[i]
				        }
				      }
				    } else {
				      for (let i = 2; i < arr.length; i++) {
				        if (arr[i] === arr[0]) {
				          return arr[1]
				        } else if (arr[i] === arr[1]) {
				          return arr[0]
				        }
				      }
				    }
				  }
				  ```
					- ((63fdd9d6-f868-4e2f-9946-fd408c683a6e))
			- Best practice
				- ```javascript
				  function findUniq(arr) {
				    arr.sort((a,b) => a-b);
				    return arr[0] == arr[1] ? arr.pop() : arr[0]
				  }
				  ```
				- ```js
				  function findUniq(arr) {
				    return arr.find(n => arr.indexOf(n) === arr.lastIndexOf(n));
				  }
				  ```
				- id:: 640232da-375d-448e-b655-994974cdc230
				  ```js
				  function findUniq(arr) {
				    let [a,b,c] = arr.slice(0,3);
				    if (a !== b && a !== c) return a;
				    for (let x of arr ) {
				      if (x !== a) return x
				    }
				  }
				  ```
					- ((63679853-46c2-4992-ab73-5c27acc7ce2e))
		- [Equal Sides Of An Array](https://www.codewars.com/kata/5679aa472b8f57fb8c000047/javascript)
		  collapsed:: true
			- My solution
				- ```javascript
				  function findEvenIndex(arr) {
				    let left = 0
				    let total = arr.reduce((a,b) => a+b)
				    if (total - arr[0] === 0) return 0
				    
				    for (let i = 0; i < arr.length; i++) {
				      left += arr[i]
				      if ((total - left - arr[i+1]) === left) {
				          return i+1
				      }
				    }
				    return -1
				  }
				  ```
			- Best practice
				- ```javascript
				  function findEvenIndex(arr) {
				    let left = 0, 
				    let right = arr.reduce((a,b) => a+b);
				    
				    for (let i = 0; i < arr.length; i++) {
				        if (i > 0) {
				          left += arr[i-1];
				        }
				        right -= arr[i];
				        
				        if(left == right) {
				          return i
				        }
				    }
				    
				    return -1;
				  }
				  ```
		- [FizzBuzz Backwards](https://www.codewars.com/kata/59ad13d5589d2a1d84000020/javascript)
		  id:: 63ef9163-b156-414c-ba00-27c352c96685
		  collapsed:: true
			- My WIP solution
			  collapsed:: true
				- ```javascript
				  function reverseFizzBuzz(array) {
				    const fizzArr = [];
				    const buzzArr = [];
				    const fizzbuzzArr = [];
				    const resultArr = [];
				  
				    array.forEach((el, ind) => {
				      switch (el) {
				        case "FizzBuzz":
				          fizzbuzzArr.push(ind + 1);
				          fizzArr.push(ind + 1);
				          buzzArr.push(ind + 1);
				          break;
				        case "Fizz":
				          fizzArr.push(ind + 1);
				          break;
				        case "Buzz":
				          buzzArr.push(ind + 1);
				          break;
				      }
				    });
				  
				    console.log(`fizzArr`, fizzArr);
				    console.log(`buzzArr`, buzzArr);
				    console.log(`fizbuzzzArr`, fizzbuzzArr);
				  
				    // check if there are multiples of 1
				    if (fizzArr[0] === 1) {
				      resultArr[0] = 1;
				    } else if (buzzArr[0] === 1) {
				      resultArr[1] = 1;
				    }
				    console.log(`resultArr:`, resultArr);
				  
				    // if both fizz and buzz are the same value
				    if (
				      fizzArr.length === buzzArr.length &&
				      fizzArr.length === fizzbuzzArr.length
				    ) {
				      for (let i = 2; i < 50; i++) {
				        if (
				          fizzbuzzArr.every((el) => {
				            return el % i === 0;
				          })
				        ) {
				          resultArr.push(i, i);
				        }
				      }
				      return resultArr;
				    }
				  
				    // Use fizzbuzz as way to find both
				    if (fizzbuzzArr.length > 0) {
				      for (let i = 2; i < 50; i++) {
				        // if buzz multiple known and
				        if (resultArr.length < 2 && resultArr[0] !== null) {
				          if (
				            fizzbuzzArr.every((el) => {
				              return el % i === 0;
				            })
				          ) {
				            if (
				              fizzArr.some((el) => {
				                return el === i;
				              })
				            ) {
				              resultArr[0] = i;
				              if (resultArr.length < 2 && resultArr[0] !== null) {
				                return resultArr;
				              }
				            }
				            if (
				              buzzArr.some((el) => {
				                return el === i;
				              })
				            ) {
				              resultArr[1] = i;
				              if (resultArr.length < 2 && resultArr[0] !== null) {
				                return resultArr;
				              }
				            }
				          }
				        }
				      }
				      return resultArr;
				    }
				  
				    // If no FizzBuzz
				    for (let i = 2; i < 50; i++) {
				      if (
				        fizzArr.every((el) => {
				          //       console.log(`el:`, el)
				          //       console.log(`i:`, i)
				          return el % i === 0;
				        })
				      ) {
				        //       console.log(`true`)
				        resultArr.push(i);
				      }
				    }
				    for (let i = 2; i < 50; i++) {
				      if (
				        buzzArr.every((el) => {
				          return el % i === 0;
				        })
				      ) {
				        resultArr.push(i);
				      }
				    }
				    console.log(`resultArr:`, resultArr);
				    return resultArr;
				  }
				  
				  ```
			- Best practice
			  id:: 4234dc95-ef8e-467a-b203-1ea773498b9b
				- ```javascript
				  function reverseFizzBuzz(array) {
				    const fizz = (array.indexOf("Fizz") + 1) ? array.indexOf("Fizz") + 1 : array.indexOf("FizzBuzz")+1;
				    const buzz = (array.indexOf("Buzz") + 1) ? array.indexOf("Buzz") + 1 : array.indexOf("FizzBuzz")+1;
				  
				  return [fizz,buzz];
				  
				  };
				  ```
					- Alternate simpler style
						- ```javascript
						  function reverseFizzBuzz(array) {
						    let fizz;
						    let buzz;
						    
						    if (array.includes("Fizz")) {
						      fizz = array.indexOf("Fizz") + 1;
						    } else {
						      fizz = array.indexOf("FizzBuzz") + 1;
						    }
						  
						    if (array.includes("Buzz")) {
						      buzz = array.indexOf("Buzz") + 1;
						    } else {
						      buzz = array.indexOf("FizzBuzz") + 1;
						    }
						  
						    return [fizz, buzz];
						  }
						  ```
		- [N-th Fibonacci](https://www.codewars.com/kata/522551eee9abb932420004a0/javascript)
		  collapsed:: true
		  id:: 63fdda25-ba87-476a-a007-24d16ef62e64
			- My solution
				- ```javascript
				  export function nthFibo(n: number): number {
				    let array = [0, 1];
				    
				    if (n === 1) {
				      return 0
				    } else if (n === 2) {
				      return 1
				    }
				    
				    for (let i = 2; i < n; i++) {
				      array.push(array[i-2] + array[i-1])
				    }
				    
				    return array[n-1];
				  }
				  ```
			- Best practice
			  id:: dc1d62b5-0302-4fcf-b0b8-3fa1df96d4fb
				- ```javascript
				  function nthFibo(n) {
				    let [prev, curr] = [0, 1];
				    for (let i = 1; i < n; i++) {
				      [prev, curr] = [curr, prev + curr];
				    }
				    return prev;
				  }
				  ```
					- Destructuring Assignment
					  id:: 63fdda25-a79c-4c89-928b-dc133cc0891d
						- `let [prev, curr] = [0, 1]` is an example of **destructuring assignment** ( ((63679853-46c2-4992-ab73-5c27acc7ce2e)) )
						  id:: 63f33581-f747-4705-b965-a7371bc28f77
							- Declaring two variables, `prev` and `curr`, and initialize them to the values `0` and `1`, respectively
							- Destructuring assignment is a feature of JavaScript that allows you to unpack values from arrays or objects into separate variables. In this case, the code is using array destructuring to unpack the first two values from the array `[0, 1]` into the variables `prev` and `curr`.
		- [Count characters in your string](https://www.codewars.com/kata/52efefcbcdf57161d4000091/train/javascript)
		  collapsed:: true
			- My solution
				- ```javascript
				  function count (string) {
				    if (string === '') {
				      return {};
				    }
				    
				    let obj = {}
				    
				    string.split('').map((el) => {
				      obj[el] === undefined ? 
				        obj[el] = 1 :
				        obj[el]++
				    })
				    return obj
				  }
				  ```
					- Also works
						- ```javascript
						  function count (string) {
						    if (string === '') {
						      return {};
						    }
						    
						    let obj = {}
						    
						    string.split('').map((el) => {
						      if (obj[`${el}`] === undefined) {
						        obj[`${el}`] = 1
						      } else {
						        obj[`${el}`]++
						      }
						    })
						    return obj
						  }
						  ```
			- Best practice
				- ```javascript
				  function count (string) {  
				    var count = {};
				    string.split('').forEach(function(s) {
				       count[s] ? count[s]++ : count[s] = 1;
				    });
				    return count;
				  }
				  ```
		- [Tribonacci Sequence](https://www.codewars.com/kata/556deca17c58da83c00002db/typescript)
		  id:: 63a2dad7-e505-4399-947c-c7f0730d7ea1
		  collapsed:: true
			- My solution
				- ``` javascripexport function tribonacci([a, b, c]: [number, number, number], n: number): number[] {
				    let array1 = [a, b, c];
				    
				    switch (n) {
				        case 0: return []
				        case 1: return [a]
				        case 2: return [a, b]
				        case 3: return [a, b, c]
				    }
				  
				    for (let i = 3; i < n; i++) {
				      array1.push(array1[i-3] + array1[i-2] + array1[i-1])
				    }
				    return array1
				  }
				  t
				  ```
			- Best practice  
			  id:: 313a98fd-dcd3-4695-bea4-a439e1d3acf4
				- ``` javascript
				  export function tribonacci(s: Array<number>, n: number): number[] {
				    for (let i = 0; s.length < n; i++) s.push(s[i] + s[i + 1] + s[i + 2]);
				    return s.slice(0,n);
				  }	  
				   
				  ```
		- [Detect Pangram](https://www.codewars.com/kata/545cedaa9943f7fe7b000048/train/javascript)
		  id:: 63a188db-4387-4688-a058-4e613005508b
		  collapsed:: true
			- Best practice
			  id:: 63baa387-5a93-4ed4-a40d-971eadeabbb0
				- collapsed:: true
				  ```javascript
				  function isPangram(string){
				    string = string.toLowerCase();
				    return "abcdefghijklmnopqrstuvwxyz".split("").every(el => {
				      string.indexOf(el) !== -1;
				    });
				  }
				  ```
					- ((63679853-a37a-4046-8ccc-7841dfaa48a9))
			- Our working solution
			  collapsed:: true
				- ```javascript
				  function isPangram(string){
				    const alphabet = {
				      a: 0,
				      b: 0,
				      c: 0,
				      d: 0,
				      e: 0,
				      f: 0,
				      g: 0,
				      h: 0,
				      i: 0,
				      j: 0,
				      k: 0,
				      l: 0,
				      m: 0,
				      n: 0,
				      o: 0,
				      p: 0,
				      q: 0,
				      r: 0,
				      s: 0,
				      t: 0,
				      u: 0,
				      v: 0,
				      w: 0,
				      x: 0,
				      y: 0,
				      z: 0
				    }
				    const letters = string.toLowerCase().split(‘’);
				    for (let letter of letters) {
				        alphabet[letter]++;
				    }
				    const values = Object.values(alphabet)
				    if (values.includes(0))
				      return false;
				    return true;
				  }
				  ```
			- WIP solution with ((63679853-1c98-454a-8932-e67322c119d9))
				- ```javascript
				  function isPangram(string){
				    let pangramArray = string.toLowerCase().split('');
				  //   console.log(`pangramArray:`,pangramArray)
				    let alphabet = [...Array(26)].map((_, i) => String.fromCharCode(i + 97));
				    let count = 0;
				    for (let letter of alphabet) {
				      if (pangramArray.some(
				        (item) => {
				  //       console.log(`item:`,item, `, letter:`,letter)
				  //       console.log(`item === letter`, item === letter)
				          item === letter
				        }
				      )) { 
				        count++ 
				      }
				    console.log(`count:`, count);
				    }
				    return true;
				  }
				  ```
		- [Convert string to camel case](https://www.codewars.com/kata/517abf86da9663f1d2000003/javascript)
		  id:: 639aedfe-27f9-4fd6-bb60-e207723da798
		  collapsed:: true
			- Best practices
			  id:: 63baa387-5558-4306-bd11-22353a8b4d6d
				- id:: 63baa387-65a0-4ded-a862-dc3fe2003008
				  ```javascript
				  function toCamelCase(str){
				        var regExp=/[-_]\w/gi;
				        return str.replace(regExp,function(match){
				              return match.charAt(1).toUpperCase();
				         });
				  }
				  ```
					- Explained:
					  collapsed:: true
						- `/[-_]\w/` matches any word character (`\w`) preceded by either a hyphen (`-`) or an underscore (`_`).
						  id:: 63f2a18f-1978-40f0-b4b6-815da6b62041
						- The `g` and `i` flags at the end of the expression mean "global" (match all occurrences) and "case-insensitive" (ignore case), respectively.
						- Here are some examples of strings that would match this regular expression:
							- `foo-bar`
							- `baz_qux`
							- `quux123`
							- `-foo`
							- `_bar`
						- And here are some examples of strings that would not match:
							- `fooBar` (no hyphen or underscore)
							- `123quux` (does not start with a hyphen or underscore)
							- `quux_` (does not have a word character after the hyphen or underscore)
							- `FOO-BAR` (case-sensitive match, but the `i` flag was used)
			- My solution
				- ```javascript
				  function toCamelCase(str){
				    return str.replace(/-/g, '_').split('_').map(
				      (word, index) => (index == 0 ? word : word.charAt(0).toUpperCase()+word.slice(1))).join('')
				  }
				  ```
			- Related: ((63470fd1-5259-4cdb-a208-b49d213b679b))
		- [Your order,  please](https://www.codewars.com/kata/55c45be3b2079eccff00010f/javascript)
		  collapsed:: true
			- Best practice
				- ```javascript
				  function order(words){
				    
				    return words.split(' ').sort(function(a, b){
				        return a.match(/\d/) - b.match(/\d/);
				     }).join(' ');
				  }
				  ```
			- My solution
				- ```javascript
				  function order(words){
				    const newWords = words.split(" ");
				    const numWordPairs = [];
				    for (let word of newWords) {
				      let property = Number(word.split("").find(character => character < 10));
				      numWordPairs.push({ order: property,  text: word})
				    }
				    numWordPairs.sort((a,b) => a.order - b.order)
				    let array = [];
				    for (let item of numWordPairs) {
				      array.push(item.text)
				    }
				    return array.join(" ");
				  }
				  ```
		- [Unique In Order](https://www.codewars.com/kata/54e6533c92449cc251001667/javascript)
		  id:: 6391bfea-254f-4297-95cb-3a4d0c20efff
		  collapsed:: true
			- Best practices
				- ```javascript
				  function uniqueInOrder(it) { 
				    let result = [] 
				    let last
				    
				    for (var i = 0; i < it.length; i++) { 
				      if (it[i] !== last) { 
				        result.push(last = it[i]) 
				      } 
				    }
				    return result
				  }
				  ```
			- My solution
				- ```javascript
				  var uniqueInOrder = function (iterable) {
				    let array = [];
				    if (typeof iterable[0] === "number") {
				      console.log("number ran")
				      iterable
				        .toString()
				        .split(",")
				        .forEach((e) => {
				          if (e !== array[array.length - 1]) {
				            array.push(e);
				          }
				        });
				        let intArray = parseInt(array.join(""))
				        console.log("int string???", intArray)
				      
				          return intArray.toString().split("").map(Number)
				    } else {
				      console.log("string ran")
				    iterable
				      .toString()
				      .split("")
				      .forEach((e, index) => {
				        if (e !== array[array.length - 1] && e !== ",") {
				          array.push(e);
				        }
				      });
				      }
				    return array;
				  };
				  ```
					- Related: ((6351322c-6b12-4902-b961-9ad79f67c9dc))
					  id:: 6391c00f-9fcf-4c2a-a121-ad8bfbc09cff
		- [Take a Ten Minutes Walk](https://www.codewars.com/kata/54da539698b8a2ad76000228)
		  id:: 6391b172-3c6f-47b6-9b37-f49aa9a2edf0
		  collapsed:: true
			- Best practice
			  id:: 6391b186-4fc6-47cd-a1ad-d06df9799a79
				- ```javascript
				  function isValidWalk(walk) {
				    var dx = 0
				    var dy = 0
				    var dt = walk.length
				    
				    for (var i = 0; i < walk.length; i++) {
				      switch (walk[i]) {
				        case 'n': dy--; break
				        case 's': dy++; break
				        case 'w': dx--; break
				        case 'e': dx++; break
				      }
				    }
				    
				    return dt === 10 && dx === 0 && dy === 0
				  }
				  ```
			- My solution
				- ```javascript
				  function isValidWalk(walk) {
				      if (walk.length !== 10) {
				        return false
				      }
				    
				      let northSouth = 0;
				      let eastWest = 0;
				    
				      for (let letter of walk) {
				        if (letter === 'n') {
				          northSouth++
				        } else if (letter === 's') 
				        {
				          northSouth--
				        }
				        if (letter === 'e') {
				          eastWest++
				        } else if (letter === 'w') 
				        {
				          eastWest--
				        }
				      }
				      if (northSouth === 0 && eastWest === 0) {
				          return true
				      } else {
				          return false
				      }
				  }
				  ```
		- [Duplicate Encoder](https://www.codewars.com/kata/54b42f9314d9229fd6000d9c/solutions/javascript)
		  id:: 639061fa-373b-46c3-9f9f-10e94045b532
		  collapsed:: true
			- Best practice
			  id:: 63906226-8908-4e27-b387-7012d73337f5
				- ```javascript
				  function duplicateEncode(word){
				    return word
				      .toLowerCase()
				      .split('')
				      .map((el, ind, arr) => 
				    		arr.indexOf(el) === arr.lastIndexOf(el) ? "(" : ")"
				      )
				      .join('');
				  }
				  ```
					- lastIndexOf
			- Keira's solution, very similar
				- ```javascript
				  function duplicateEncode(word){
				    return word.toUpperCase().split("").map((el, ind, arr) => arr.indexOf(el) === arr.lastIndexOf(el) ?  el = "(" : el = ")").join("")
				  }
				  ```
			- My solution (note: initially had some problems using ((63679853-1c98-454a-8932-e67322c119d9)) )
			  id:: 63905ece-9295-42f8-82ac-c3271a9a77e7
				- ```javascript
				  function duplicateEncode(word) {
				    const arr1 = word.toUpperCase().split('');
				    let arr3 = [];
				  
				    for (let i = 0; i < arr1.length; i++) {
				      // Clone the array
				      let arr2 = arr1.slice();
				      let filteredLetter = arr2.splice(i, 1)
				      let testDuplicate = letter => arr1[i] === letter;
				      if (arr2.some(testDuplicate)) {
				        arr3.push(')');
				      } else {
				        arr3.push('(')
				      }
				    }
				    return arr3.join('');
				  }
				  ```
				- Alternate working solution (using ((63679853-1c98-454a-8932-e67322c119d9)) in-line, cleaner)
				  id:: 63905ff4-4050-4b0e-ab42-0df243390d97
					- ```javascript
					  function duplicateEncode(word) {
					    const arr1 = word.toUpperCase().split('');
					    let arr3 = [];
					    
					    for (let i = 0; i < arr1.length; i++) {
					      // Clone the array
					      let arr2 = arr1.slice();
					      let filteredLetter = arr2.splice(i, 1)
					      if (arr2.some(letter => arr1[i] === letter)) {
					        arr3.push(')');
					      } else {
					        arr3.push('(')
					      }
					    }
					    return arr3.join('');
					  }
					  ```
					- Keira said to replace:
					  ```javascript
					  if (arr2.some((letter) => { arr1[i] === letter })) 
					  ```
					  With this, because the original wouldn't work:
					  ```javascript
					  if (arr2.some(letter => arr1[i] === letter)) 
					  ```
					- Related: ((636d5df2-5117-4f9e-8113-83bbb5eff6c1))
		- [Persistent Bugger](https://www.codewars.com/kata/55bf01e5a717a0d57e0000ec/javascript)
		  id:: 638e4105-025d-437b-9984-42a787204cfa
		  collapsed:: true
			- Best practices
			  id:: 63904f3d-450b-42f8-afce-736387712a80
				- ```javascript
				  function persistence(num) {
				     var times = 0;
				     
				     num = num.toString();
				     
				     while (num.length > 1) {
				       times++;
				       num = num.split('').map(Number).reduce((a, b) => a * b).toString();
				     }
				     
				     return times;
				  }
				  ```
					- `reduce((a, b) => a * b)`
					  id:: 63924d3c-ff3a-4f86-a07e-337af88fa6eb
						- This multiplies all the values in the array together
			- Clever
				- ```javascript
				  const persistence = num => {
				    return `${num}`.length > 1 
				      ? 1 + persistence(`${num}`.split('').reduce((a, b) => a * +b)) 
				      : 0;
				  }
				  ```
			- My solution
				- ```javascript
				  function persistence(num) {
				    let sn = num.toString();
				    let count = 0
				    while (sn > 9) {
				      let sum = 1;
				      sn.split("").forEach((sne) => (sum = sum * +sne));
				      sn = sum.toString()
				      count++}
				    return (count)
				  }
				  ```
		- [Is a number prime?](https://www.codewars.com/kata/5262119038c0985a5b00029f/javascript)
		  collapsed:: true
			- Best practice
				- ```javascript
				  function isPrime(num) {
				    if (num < 2) return false;
				    const limit = Math.sqrt(num);
				    for (let i = 2; i <= limit; ++i) {
				      if (num % i === 0) {
				        return false;
				      }
				    }
				    return true;
				  }
				  ```
					- You should test explicitly for 2 then start the loop at 3 and increment by 2 each time. Any number multiplied by an even number is even and is not prime. You should also test if limit is an integer. If it is then num is a perfect square.
					  ```javascript
					  function isPrime(num) {
					    if(num < 2 || (num > 2 && num%2 == 0))
					       return false;
					    var root = Math.sqrt(num);
					    var limit = Math.round(root);
					    if( root == limit )
					      return false;
					    for( var i = 3; i < limit; i+=2 ){
					      if(num%i == 0)
					        return false;
					    }
					    return true;
					  }
					  ```
		- [Replace With Alphabet Position](https://www.codewars.com/kata/546f922b54af40e1e90001da/solutions/javascript)
		  id:: 63736445-7ccf-467e-a7ca-877a38cfd6a5
		  collapsed:: true
			- Best practices
				- ```javascript
				  function alphabetPosition(text) {
				    var result = "";
				    for (var i = 0; i < text.length; i++){
				      var code = text.toUpperCase().charCodeAt(i)
				      if (code > 64 && code < 91) result += (code - 64) + " ";
				    }
				  
				    return result.slice(0, result.length-1);
				  }
				  ```
			- Most clever
				- ```javascript
				  let alphabetPosition = (text) => text.toUpperCase().replace(/[^A-Z]/g, '').split('').map(ch => ch.charCodeAt(0) - 64).join(' ')
				  ```
			- My solution
				- ```javascript
				  function alphabetPosition(text) {
				    const alphabetArray = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z'];
				    let returnArray = [];
				    const replaced = text.replace(/[^a-z]/gi, '');
				    for (let textLetter of replaced) {
				      returnArray.push(alphabetArray.indexOf(textLetter.toLowerCase())+1)
				    };
				    return returnArray.join(' ');
				  }
				  ```
			- [Remove all non-alphanumeric Characters from String in JS | bobbyhadz](https://bobbyhadz.com/blog/javascript-remove-non-alphanumeric-characters-from-string#:~:text=To%20remove%20all%20non%2Dalphanumeric,string%20with%20all%20matches%20replaced)
			- Related:
		- [Counting Duplicates](https://www.codewars.com/kata/54bf1c2cd5b56cc47f0007a1/train/javascript)
		  id:: 6359001a-4d38-47e3-95bd-5a3b8a18050c
		  collapsed:: true
			- Best practice
			  id:: 63904f3d-9b31-4b9f-9ab7-ae0c533a0abd
				- ```javascript
				  function duplicateCount(text){
				    return (text.toLowerCase().split('').sort().join('').match(/([^])\1+/g) || []).length;
				  }
				  ```
					- `match(/([^])\1+/g)`
						- ```javascript
						  // If there is no matches, return an empty array
						  || []
						  
						  // Back reference, match 1 or more of the preceding token
						  \1+
						    
						  // Match any character that is not in this set 
						  [^]
						  ```
						- Related: ((63470fd1-1f37-4428-9546-d674c323d5d1))
			- Our solution
				- ```javascript
				  function duplicateCount(text){
				    
				    let chars = [];
				    let duplicates = [];
				    
				    text = text.toUpperCase();
				    
				    for (let i = 0; i < text.length; i++) {
				      if (chars.includes(`${text[i]}1`) === false) {
				        let char = `${text[i]}1`;
				        chars.push(char);
				      }
				      else {
				        duplicates.push(text[i]);
				      }
				    }
				    return new Set(duplicates).size;
				  }
				  ```
		- [Bit Counting](https://www.codewars.com/kata/526571aae218b8ee490006f4/javascript)
		  id:: 6357aa2f-0642-4ce6-91f6-f5618b76b562
		  collapsed:: true
			- Best practice
				- ```javascript
				  countBits = n => n.toString(2).split('0').join('').length;
				  ```
			- 2nd best practice
			  id:: 63904f3d-b859-416a-af40-5ddf0b9b30ab
				- ```javascript
				  var countBits = function(n) {
				    return n.toString(2).replace(/0/g,'').length;
				  };
				  ```
			- My solution
				- ```javascript
				  var countBits = function(n) {
				    let binary = n.toString(2);
				    if (binary == 0) {
				      return 0;
				    } else {
				      return binary.match(/1/g).length;
				    }
				  };
				  ```
		- [Array.diff](https://www.codewars.com/kata/523f5d21c841566fde000009/javascript)
		  id:: 634fe2de-cb29-41bd-a324-de28e866f009
		  collapsed:: true
			- Best practice
			  id:: 63679853-8500-48d4-8458-ac65c6842951
				- ```javascript
				  function array_diff(a, b) {
				    return a.filter(e => !b.includes(e));
				  }
				  ```
			- My solution
				- ```javascript
				  function arrayDiff(a, b) {
				    let answer = [];
				    let matchStatus = false;
				    //check that both arrays aren't empty (else return a)
				    if (b.length > 0 && a.length > 0) {
				      //for length of a
				        for (let i = 0; i < a.length; i++) {
				          //reset matchStatus to false
				          matchStatus = false;
				          //then for length of b loop through and if match any char, change matchStatus to true
				          for (let j = 0; j < b.length; j++) {
				            if (a[i] === b[j]) {
				                matchStatus = true;
				                {break}
				              } else {
				                matchStatus = false
				              }
				           }
				          //if gets to end of that loop and matchStatus still is false, push to answer Array
				           if (matchStatus === false) {
				                answer.push(a[i])
				           }
				         }
				      //return answer after loop completed
				      return answer;
				    } else {
				      return a
				    }
				  }
				  ```
		- [Stop gninnipS My sdroW!](https://www.codewars.com/kata/5264d2b162488dc400000001)
		  collapsed:: true
			- Best practice
			  id:: 63f33e7b-3df6-4ff4-81c3-4307a8468e78
				- ```javascript
				  unction spinWords(words){
				    return words.split(' ').map(function (word) {
				      return (word.length > 4) ? word.split('').reverse().join('') : word;
				    }).join(' ');
				  }
				  ```
			- Clever
				- ```javascript
				  function spinWords(string){
				    return string.replace(/\w{5,}/g, function(w) { return w.split('').reverse().join('') })
				  }
				  ```
			- My solution
				- ```javascript
				  function spinWords(string) {
				    let arr = string.split(' ');
				    for (let i = 0; i < arr.length; i++) {
				      if (arr[i].length > 4) {
				        let reverseWord = ''
				        for (let j = (arr[i].length -1); j > -1; j--) {
				          reverseWord += arr[i][j];
				          console.log(reverseWord)
				        }
				        arr[i] = reverseWord;
				      }
				    }
				    return arr.join(' ');
				  }
				  ```
		- [Sum of Digits / Digital Root](https://www.codewars.com/kata/541c8630095125aba6000c00/solutions/javascript)
		  collapsed:: true
			- Best practice
				- ```javascript
				  function digital_root(n) {
				    return (n - 1) % 9 + 1;
				  }
				  ```
					- Explanations
					  collapsed:: true
						- 1
							- In modulo 9 arithmetic any number multiplied by 10 is the same number. We can show that by proving that any number's remainder of dividing by 9 is the same as a remainder from dividing the same number multiplied by 10:
							- ```
							  n = 9k + l // any number can be represented as k multiplicity of 9 and l remainder
							  10n = 90k + 10l
							  10n = 90k + 9l + l
							  10n = 9(10k + l) + l // the remainder is also l
							  ```
							- With that, we can write any number like so:
							- ```
							  1234 = 1 * 10^3 + 2 * 10^2 + 3 * 10 + 4
							  ```
							- which in modulo 9 arithmetic is equivalent to
							- ```
							  1 + 2 + 3 + 4
							  ```
							- So, in mod 9 arithmetic any number is equal to sum of its digits, and also to sum of that sum's digits, and so on...
						- 2
							- http://www.sjsu.edu/faculty/watkins/Digitsum0.htm
							- basically the sumdigit is the rest of the number and the closest 9 multiple below that number. IE: n = 23, closest 9 multiple below is 18(9 * 2) then 23 - 18 = 5. It is a numerical theorem you can see here. https://en.wikipedia.org/wiki/Digital_root
						- https://math.stackexchange.com/questions/99725/every-integer-is-congruent-to-the-sum-of-its-digits-mod-9
			- My solution
				- ```javascript
				  function digitalRoot(n) {
				    let string = n.toString();
				    let array = [];
				    let sum1 = 0;
				    let value = string;
				    // iterate for as long as needs be
				    for (let j = 0; j < n; j++) { 
				      value = value.toString()
				      array = value.split("");
				      // after map(Number) it should now be an array of numbers
				      array = array.map(Number);
				      for (let i = 0; i < array.length; i++) {
				        sum1 += array[i]
				      }
				      if (sum1 < 10) {
				        return sum1;
				      } else {
				        value = sum1
				        sum1 = 0;
				      }
				    }
				    return n;
				  }
				  ```
		- [Find the odd int](https://www.codewars.com/kata/54da5a58ea159efa38000836)
		  collapsed:: true
			- Best practice
				- ```javascript
				  const findOdd = (xs) => xs.reduce((a, b) => a ^ b);
				  ```
			- My solution
				- ```javascript
				  function findOdd(A) {
				    for (let i = 0; i < A.length; i++) {
				      let count = 0;
				      for (var j = 0; j < A.length; j++) {
				          if (A[i] === A[j]) {
				              count++;
				          }
				      }
				      if (count % 2 === 1) {
				          return A[i]
				      }  
				    }
				  }
				  ```
		- [Create Phone Number](https://www.codewars.com/kata/525f50e3b73515a6db000b83/solutions/javascript)
		  id:: 634da2ed-17ad-4770-98b1-6e36134ee107
		  collapsed:: true
			- Best practice
				- ```javascript
				  function createPhoneNumber(numbers){
				    var format = "(xxx) xxx-xxxx";
				    
				    for(var i = 0; i < numbers.length; i++)
				    {
				      format = format.replace('x', numbers[i]);
				    }
				    
				    return format;
				  }
				  ```
			- My solution
				- ```javascript
				  function createPhoneNumber(numbers){
				    return `(${numbers[0]}${numbers[1]}${numbers[2]}) ${numbers[3]}${numbers[4]}${numbers[5]}-${numbers[6]}${numbers[7]}${numbers[8]}${numbers[9]}`
				  }
				  ```
		- [Who likes it?](https://www.codewars.com/kata/5266876b8f4bf2da9b000362)
		  collapsed:: true
			- Best practice
				- ```javascript
				  function likes(names) {
				    names = names || [];
				    switch(names.length){
				      case 0: return 'no one likes this'; break;
				      case 1: return names[0] + ' likes this'; break;
				      case 2: return names[0] + ' and ' + names[1] + ' like this'; break;
				      case 3: return names[0] + ', ' + names[1] + ' and ' + names[2] + ' like this'; break;
				      default: return names[0] + ', ' + names[1] + ' and ' + (names.length - 2) + ' others like this';
				    }
				  }
				  ```
			- My solution
				- ```javascript
				  function likes(names) {
				    if (names.length === 0) {
				      return "no one likes this";
				    } else if (names.length === 1) {
				      return `${names[0]} likes this`;
				    } else if (names.length === 2) {
				      return `${names[0]} and ${names[1]} like this`;
				    } else if (names.length === 3) {
				      return `${names[0]}, ${names[1]} and ${names[2]} like this`;
				    } else if (names.length >= 4) {
				      return `${names[0]}, ${names[1]} and ${((names.length) - 2)} others like this`;
				    }
				  }
				  ```
		- [Multiples of 3 or 5](https://www.codewars.com/kata/514b92a657cdc65150000006/train/javascript)
		  collapsed:: true
			- Best practice
			  collapsed:: true
				- ```javascript
				  function solution(number){
				    var sum = 0;
				    
				    for(var i = 1;i< number; i++){
				      if(i % 3 == 0 || i % 5 == 0){
				        sum += i
				      }
				    }
				    return sum;
				  }
				  ```
			- My solution
			  collapsed:: true
				- ```javascript
				  function solution(number) {
				    if (number < 0) {
				      return 0;
				    }
				    let naturalNumbers = [];
				    for (let i = 0; i < number; i++) {
				      if ((i % 3 === 0) && (i % 5 === 0)) {
				        naturalNumbers.push(i);
				      } else if (i % 3 === 0) {
				        naturalNumbers.push(i);
				      } else if (i % 5 === 0) {
				        naturalNumbers.push(i);
				      }
				    }
				    let sum = 0;
				    for (let i = 0; i < naturalNumbers.length; i++) {
				      sum += naturalNumbers[i];
				    }
				    return sum;
				  }
				  ```
	- 7 kyu (3 score)
		- [Square Every Digit](https://www.codewars.com/kata/546e2562b03326a88e000020/javascript)
		  collapsed:: true
		  Repeat challenge: use ((6350374d-fdba-4eb4-b17a-f80e5e5a3fcb))
			- My solution
				- ```javascript
				  function squareDigits(num){
				    let str1 = String(num);
				    let str2 = '';
				    for (let i = 0; i < str1.length; i++) {
				      str2 += String(Math.pow(Number(str1[i]), 2))
				    }
				    return Number(str2);
				  }
				  ```
				-
			- Best practice
				- ```javascript
				  function squareDigits(num){
				    return Number(('' + num).split('').map(function (val) 
				    { 
				      return val * val;
				    }).join(''));
				  }
				  ```
				-
		- [Highest and Lowest](https://www.codewars.com/kata/554b4ac871d6813a03000035/train/javascript)
		  id:: 66ba0d32-3ccd-4c2c-bfc1-87215eb97e3e
		  collapsed:: true
		  Repeat challenge: use ((63642a10-4e86-4101-961a-8311efb8ae4f))
			- My solution
				- ```javascript
				  function highAndLow(numbers){
				    arr = numbers.split(" ");
				    arr = arr.map(item => Number(item));
				    return `${Math.max(...arr)} ${Math.min(...arr)}`
				  }
				  ```
				-
			- Best practice
				- ```javascript
				  function highAndLow(numbers){
				    numbers = numbers.split(' ');
				    return `${Math.max(...numbers)} ${Math.min(...numbers)}`;
				  }
				  ```
			- Related: ((63f2965f-e63c-44c2-89f3-ecd6f644632f))
		- [Odd or Even?](https://www.codewars.com/kata/5949481f86420f59480000e7/javascript)
		  collapsed:: true
			- My solution
				- ```javascript
				  function oddOrEven(array) {
				     let sum=0;
				     array.forEach(el => sum+=el);
				     return sum%2===0?'even':'odd'
				  }
				  ```
			- Best practice
			  id:: 60082e89-1d10-424a-baec-143f315a44ad
				- ```js
				  function oddOrEven(arr) {
				    return arr.reduce((a,b)=>a+b,0) % 2 ? 'odd' : 'even';
				  }
				  ```
		- [Printer Errors](https://www.codewars.com/kata/56541980fa08ab47a0000040/javascript)
		  id:: 6401f353-f6bc-44da-9e8e-6128381908c8
		  collapsed:: true
			- My solution
			  id:: 5ea4d18a-04f9-49d8-8ea9-5343e80b2316
				- ```javascript
				  function printerError(s) {
				    const errChar = /[^a-mA-M]/;
				    
				    let errors = 0;
				    for (let char of s) {
				      if (char.match(errChar)) {
				        errors++
				      }
				    }
				    return `${errors}/${s.length}`
				  }
				  ```
			- Best practice
				- ```javascript
				  function printerError(s) {
				      // your code
				      var count = 0;
				      for(var i = 0; i < s.length; i++) {
				        if (s[i] > "m") {
				          count++;
				        }
				      }
				      return count+"/"+s.length;
				  }
				  ```
		- [Categorize New Member](https://www.codewars.com/kata/5502c9e7b3216ec63c0001aa/javascript)
		  collapsed:: true
			- My solution
				- ```javascript
				  ```
			- Best practice
			  id:: f0479460-b90a-487a-9ec1-a856476855d5
				- ```javascript
				  function openOrSenior(data){
				    return data.map(([age, handicap]) => (age > 54 && handicap > 7) ? 'Senior' : 'Open');
				  }
				  ```
					- ((63679853-46c2-4992-ab73-5c27acc7ce2e))
		- [Two to One](https://www.codewars.com/kata/5656b6906de340bd1b0000ac/train/javascript)
		  id:: a9fb5c78-98c0-43e9-a8ad-19ae0cda5011
		  collapsed:: true
			- My solution
			  id:: 8701c966-b92f-4b3b-931d-bf0d142727ed
				- ```javascript
				  function longest(s1, s2) {
				    let set = new Set([...s1, ...s2].sort())
				    return [...set].join('')
				  }
				  ```
			- Best practice
				- ```javascript
				  function longest(s1, s2) {
				    return [...new Set(s1 + s2)].sort().join('')
				  }
				  ```
		- [String ends with?](https://www.codewars.com/kata/51f2d1cafc9c0f745c00037d/train/javascript)
		  collapsed:: true
			- My solution
				- ```javascript
				  function solution(str, ending){
				    return new RegExp(`${ending}$`).test(str);
				  }
				  ```
					- `${ending}$` is string interpolation for the `ending` parameter
					- Second `$` is an anchor that matches the end of the string
				- Alternative: checking if a string appears anywhere in another string
					- ```javascript
					  function solution(str, ending){
					    return new RegExp(ending).test(str);
					  }
					  ```
			- Best practice
				- ```javascript
				  function solution(str, ending){
				    return str.endsWith(ending);
				  }
				  ```
					- ((63fdd9d7-2555-4f15-8f94-798587be6b3c))
		- [Beginner Series #3 Sum of Numbers | Codewars](https://www.codewars.com/kata/55f2b110f61eb01779000053/javascript)
		  id:: 63fd0a42-815d-4882-bde6-68c78297e37c
		  collapsed:: true
			- My solution
			  collapsed:: true
				- ```javascript
				  function getSum(a, b)
				  {
				    if (a === b) return a;
				    
				    let smallerInt;
				    let biggerInt;
				    let sum = 0;
				    
				    if (a < b) {
				      smallerInt = a;
				      biggerInt = b;
				    } else {
				      smallerInt = b;
				      biggerInt = a;
				    }
				    
				    for (let i = smallerInt; i <= biggerInt; i++) {
				      sum += i
				    }
				    return sum
				  }
				  ```
			- Best practice
			  id:: 0bf98572-621e-4fc4-a49d-548cbb22e8ae
				- ```javascript
				  const GetSum = (a, b) => {
				    let min = Math.min(a, b),
				        max = Math.max(a, b);
				    return (max - min + 1) * (min + max) / 2;
				  }
				  ```
					- Gauss summation formula
					  id:: 63fd16e2-0108-4579-b85a-717d83927648
					  collapsed:: true
						- ```javascript
						  // Total sum = (number of pairs) * (sum of each pair) / 2
						  return (max - min + 1) * (min + max) / 2
						  ```
						- Very good for summing a sequence of numbers
						- [Gauss Summation | Let's Talk Science](https://letstalkscience.ca/educational-resources/backgrounders/gauss-summation)
					- ((63f2965f-e63c-44c2-89f3-ecd6f644632f))
				- Good example of ternary ((63f8fe4d-9e21-4df9-ac1f-0e20e98afc49))
				  id:: 63fd0a5c-cfda-4354-8c91-418c07c23978
					- ```js
					  let bigger = a > b ? a : b;
					  let smaller = a > b ? b : a;
					  
					  // Instead of:
					  let smallerInt;
					  let biggerInt;
					  
					  if (a < b) {
					    smallerInt = a;
					    biggerInt = b;
					  } else {
					    smallerInt = b;
					    biggerInt = a;
					  }
					  ```
		- [Complementary DNA](https://www.codewars.com/kata/554e4a2f232cdd87d9000038/javascript)
		  id:: 63fcf386-b599-47d6-95b3-c6f7ec41bdda
		  collapsed:: true
			- My solution
			  id:: f230a965-1bfd-4641-9f50-04837468e098
				- ```javascript
				  function DNAStrand(dna){
				    return dna.split('').map(el => {
				      switch (el) {
				          case 'A': return 'T';
				          case 'T': return 'A';
				          case 'C': return 'G';
				          case 'G': return 'C';
				      }
				    }).join('')
				  }
				  ```
			- Best practice
				- ```javascript
				  function DNAStrand(dna){
				    const pairs = {
				      'A':'T',
				      'T':'A',
				      'C':'G',
				      'G':'C'
				    };
				    
				    return dna.split('').map(el => pairs[v]).join('');
				  }
				  ```
		- [Jaden Casing Strings](https://www.codewars.com/kata/5390bac347d09b7da40006f6/javascript)
		  id:: 63f66f5b-a9f1-4c41-9489-9e5c904781c0
		  collapsed:: true
			- My solution
				- ```javascript
				  ```
			- Best practice
				- ```javascript
				  String.prototype.toJadenCase = function () { 
				    return this.split(" ").map(function(word){
				      return word.charAt(0).toUpperCase() + word.slice(1);
				    }).join(" ");
				  }
				  
				  let str = "How can mirrors be real if our eyes aren't real";
				  console.log(str.toJadenCase())
				  ```
		- [Mumbling](https://www.codewars.com/kata/5667e8f4e3f572a8f2000039/javascript)
		  id:: 63f8aa8f-f4e4-4d1a-816a-df61b5e19dcc
		  collapsed:: true
			- My solution
				- ```javascript
				  function accum(s) {
				  	return s.toUpperCase().split('').map((el, ind) => {
				      for (let i = 0; i < ind; i++) {
				        el += el.charAt(0).toLowerCase()
				      }
				      return el
				    }).join('-')
				  }
				  ```
			- Best practice
			  id:: 63f8aaa0-96f7-487f-ac99-d752662f0a56
				- ```javascript
				  function accum(s) {
				  	return s.split('').map((c, i) => (c.toUpperCase() + c.toLowerCase().repeat(i))).join('-');
				  }
				  ```
		- [Shortest Word](https://www.codewars.com/kata/57cebe1dc6fdc20c57000ac9/javascript)
		  id:: 63f8a449-3ee5-4ca1-9c55-1ac8dc03ec0a
		  collapsed:: true
			- My solution
				- ```javascript
				  function findShort(s){
				    let len = 999
				    s.split(' ').forEach(el => {
				      if (len > el.length) {
				        len = el.length
				      }
				    })
				    return len
				  }
				  ```
			- Best practice
				- ```javascript
				  const findShort = (s) => s
				    .split(' ')
				    .sort((a, b) => b.length - a.length)
				    .pop()
				    .length;
				  ```
					- ((63470fd1-5c6c-4c4d-aea0-9d111a003975)), then ((63679853-27fd-40a4-bd44-b836c61f4394)) or ((63679853-dcb7-4c52-a93f-2ba70da4b082)) is a good way to select a particular item in an array
					  id:: 63f903ec-e5f7-44e5-9bd6-7aa607d0b969
				- id:: 63f8fe4c-acc8-4c99-b271-3bc180f53ba7
				  ```javascript
				  function findShort(text) {
				    return text.split(' ')
				      .reduce((shortest, current) =>
				        current.length < shortest.length
				          ? current
				          : shortest
				      ).length;
				  }
				  ```
				- id:: 63f8fe4c-b210-4d07-b282-4fb0d47a4d9e
				  ```javascript
				  function findShort(s){
				    return Math.min.apply(null, s.split(' ').map(w => w.length));
				  }
				  ```
					- ((0257c452-a8cc-40b2-b47a-235d81f263ce))
					- ((63f8fe4d-795b-436e-9fc4-1c0cb402cbda))
				- id:: 63f8fe4c-40d8-4b0a-ab4e-2a9bc13c179a
				  ```javascript
				  function findShort(s){
				      return Math.min(...s.split(" ").map (s => s.length));
				  }
				  ```
		- [Isogram](https://www.codewars.com/kata/54ba84be607a92aa900000f1/javascript)
		  id:: 63f66c6c-a485-474c-b2b7-3c480816fe02
		  collapsed:: true
			- My solution
				- ```javascript
				  function isIsogram(str){
				    let arr = str.toLowerCase().split('')
				    for (let i = 0; i < arr.length; i++) {
				      let filtered = arr.filter((el, ind, array) => ind !== i);
				      if (!filtered.every(it => it !== arr[i])) {
				         return false
				      } 
				    }
				    return true
				  }
				  ```
			- Best practice
			  id:: 63f8fe4c-9601-4a28-bea8-a3761241253f
				- ```javascript
				  function isIsogram(str){
				  	return new Set(str.toUpperCase()).size == str.length;
				  }
				  ```
					- ((635593b3-9619-4902-8342-f7649f68f90c))
					- ((cdcdc58f-5478-4230-9f4b-3b09f00f725a))
		- [Ones and Zeros](https://www.codewars.com/kata/578553c3a1b8d5c40300037c/javascript)
		  id:: 63f21a59-5cd9-4daa-beeb-34f9df8f5296
		  collapsed:: true
			- Best practice
			  id:: 63f21a60-f0de-40b4-9674-dc3f8beb880d
				- ```javascript
				  function binaryArrayToNumbe(arr) {
				    return parseInt(arr.join(''), 2)
				  }
				  ```
		- [Friend of Foe?](https://www.codewars.com/kata/55b42574ff091733d900002f/javascript)
		  id:: 63f1fb9a-00ac-4c2f-80d9-92012054b0ed
		  collapsed:: true
			- My solution
				- ```javascript
				  function friend(friends){
				    let a = [];
				    
				    friends.forEach((el, ind, array) => {
				      if (el.length === 4) {
				        a.push(el)
				      }
				    })
				    return a
				  }
				  ```
			- Best practice
			  id:: ae73d48d-e24a-4646-914d-339e2c649502
				- ```javascript
				  function friend(friends){
				    return friends.filter(el => el.length === 4)
				  }
				  ```
		- [Number of people in the bus](https://www.codewars.com/kata/5648b12ce68d9daa6b000099/javascript)
		  id:: 63ecdf7a-481c-4647-ab53-5952c43def9e
		  collapsed:: true
			- My solution
				- ```javascript
				  var number = function(busStops){
				    let passengers = 0;
				    
				    for (let item of busStops) {
				      passengers += item[0]
				    }
				    for (let item of busStops) {
				      passengers -= item[1]
				    }
				    return passengers
				  }
				  ```
			- Best practice
			  id:: 23369854-6e65-4923-9cf3-c14763a4eeb2
				- const number = (busStops) => busStops.reduce((rem, [on, off]) => rem + on - off, 0);
		- [Exes and Ohs](https://www.codewars.com/kata/55908aad6620c066bc00002a/javascript)
		  id:: 63ecd217-58e0-4ebf-add2-fadb54b6ed59
		  collapsed:: true
			- My solution
				- ```javascript
				  function XO(str) {
				    let xs = 0;
				    let os = 0;
				    
				    str.toLowerCase().split('').forEach((el) => {
				      if (el === 'x') {
				        xs++
				      } else if (el === 'o') {
				        os++
				      }
				    })
				    
				    if (xs === os) {
				      return true
				    } else {
				      return false
				    }
				  }
				  ```
			- Best practice
			  id:: db967743-4408-46dc-a72c-7a0efcc2f248
				- ```javascript
				  function XO(str) {
				    let x = str.match(/x/gi);
				    let o = str.match(/o/gi);
				    return (x && x.length) === (o && o.length);
				  }
				  ```
		- [Find the Parity Outlier](https://www.codewars.com/kata/5526fc09a1bbd946250002dc/solutions/javascript)
		  id:: 636a274c-f69f-44b4-87a8-b554dd9f09ba
		  collapsed:: true
			- Best practice
			  id:: 636a2755-5747-4160-85a3-7d82fdd2134a
				- id:: 636a2774-a8be-47fb-b610-fc3f4093f239
				  ```javascript
				  function findOutlier(int){
				    var even = int.filter(a => a%2 == 0);
				    var odd = int.filter(a => a%2 !== 0);
				    return even.length == 1 ? even[0] : odd[0];
				  }
				  ```
			- My solution
				- ```javascript
				  function findOutlier(integers){
				    const even = integers.filter(num => num % 2 === 0);
				    let odd = integers.filter(num => num % 2 === 1);
				    if (odd.length === 0) {
				      odd = integers.filter(num => num % 2 === -1);
				    }
				    if (even.length === 1) {
				      return even[0];
				    } else {
				      return odd[0];
				    }
				  }
				  ```
		- [Descending Order](https://www.codewars.com/kata/5467e4d82edf8bbf40000155/train/javascript)
		  id:: 6364185a-26c2-4213-9783-0dc15ec30342
		  collapsed:: true
			- My solution
				- ```javascript
				  function descendingOrder(n){
				    return parseInt(n.toString().split('').sort().reverse().join(''));
				  }
				  ```
			- Best practice
				- ```javascript
				  function descendingOrder(n){
				    return parseInt(String(n).split('').sort().reverse().join(''))
				  }
				  ```
			- ((63470fd1-5c6c-4c4d-aea0-9d111a003975)) to sort an array of numbers or strings. But use ((5c654b22-085e-4bd2-9d05-6e4692cf0929)) or ((0257c452-a8cc-40b2-b47a-235d81f263ce)) instead to find the highest/lowest number in an array, as it's a lot more efficient
			- ((63470fd1-c937-4cd7-9301-de009d1fb7e0))
			- ((63470fd1-5c6c-4c4d-aea0-9d111a003975))
			- ((635eb08f-bc21-4a5c-baa9-813d9170753a))
			- ((635eb08f-cba9-45d7-a72b-d207d55081db))
		- [List Filtering](https://www.codewars.com/kata/53dbd5315a3c69eed20002dd/train/javascript)
		  id:: 63485e7f-a73d-4dff-aae6-57fe42e82542
		  collapsed:: true
			- Best practice
			  id:: 63679853-c46d-4be6-ac1c-7f591a8c75b1
				- id:: 63679853-07b8-47a1-bcf7-9a26648c0d5c
				  ```javascript
				  function filter_list(l) {
				    return l.filter(function(v) {
				      return typeof v == 'number'
				    })
				  }
				  
				  // Alternatively written as:
				  function filter_list(l) {
				   return l.filter(v => typeof v == "number")
				  }
				  ```
			- My solution
				- collapsed:: true
				  ```javascript
				  function filter_list(l) {
				    let m = [];
				    for (let i = 0; i < l.length; i++) {
				      if (typeof l[i] === 'number') {
				        m.push(l[i]);
				      }
				    }
				    return m;
				  }
				  ```
					- ((63470fd1-ff2c-4b9a-b116-136a41a52b94))
			- ((63470fd1-ed0f-45f6-9b63-2ee67c3c152f))
			  id:: 63485f43-9366-4049-add7-c85323c17b0b
		- [Disemvowel Trolls](https://www.codewars.com/kata/52fba66badcd10859f00097e/train/javascript)
		  id:: 6348574a-5ac4-4df9-99f1-1806bc0025f1
		  collapsed:: true
			- Best practice
			  id:: 63904f3d-760d-4bcb-993f-bfcfb5e2cce0
				- ```javascript
				  function disemvowel(str) {
				    return str.replace(/[aeiou]/gi, '');
				  }
				  ```
			- My solution
				- collapsed:: true
				  ```javascript
				  function disemvowel(str) {
				      let string1 = str.replace(/a/gi, "");
				      string1 = string1.replace(/e/gi, "");
				      string1 = string1.replace(/i/gi, "");
				      string1 = string1.replace(/o/gi, "");
				      string1 = string1.replace(/u/gi, "");
				      return string1;
				  }
				  ```
					- ((63470fd1-ffa6-4c1f-9d5b-88dd4374c543)) (`i` flag) - case insensitivity matches upper and lowercase vowels
					- ((63470fd1-b26f-45d0-967a-1c746f835cfc)) (`g` flag) - because otherwise I'd just use `replaceAll` but CodeWars doesn't support it yet
					- ((63470fd1-332b-4ebf-965d-7073b319c11b))
		- [Vowel Count](https://www.codewars.com/kata/54ff3102c1bad923760001f3)
		  id:: 6347b540-6c5c-4871-b4b7-cbebe82269ec
		  collapsed:: true
			- My solution
			  id:: 6347b546-72c6-4cac-b6b4-dc1143b9ed1f
			  collapsed:: true
				- ```javascript
				  function getCount(str) {
				    let vowels = "aeiou";
				    let count = 0;
				    // iterate over str
				    for (let i = 0; i < str.length; i++) {
				      // iterate over vowels
				      for (let j = 0; j < str.length; j++) {
				        // if str[i] === vowels[j]
				        if (str[i] === vowels[j]) {
				           count++;
				        }
				      }
				    }
				    return count;
				  }
				  ```
			- Best practice
			  id:: 6347b54a-7668-432a-bc12-16c412332310
				- ```javascript
				  function getCount(str) {
				    return (str.match(/[aeiou]/ig)||[]).length;
				  }
				  ```
					- ((63470fd1-1f37-4428-9546-d674c323d5d1))
	- 8 kyu (2 score)
		- [Convert boolean values to strings 'Yes' or 'No'.](https://www.codewars.com/kata/53369039d7ab3ac506000467/train/javascript)
		  collapsed:: true
			- My solution + best practice
				- ```javascript
				  function boolToWord( bool ){
				    return bool ? 'Yes':'No';
				  }
				  ```
				-
		- [String repeat](https://www.codewars.com/kata/57a0e5c372292dd76d000d7e)
		  collapsed:: true
		  Repeat challenge: use a string method
			- My solution
				- ```javascript
				  function repeatStr (n, s) {
				    let s2 = '';
				    for (let i = 0; i < n; i++) {
				      s2 += s;
				    }
				    return s2;
				  }
				  ```
				- Related: ((63679853-6e6e-4fce-87bc-93f106c2e05d))
			- Best practice
				- ```javascript
				  function repeatStr (n, s) {
				    return s.repeat(n);
				  }
				  ```
				- Related: ((63f33e7c-dd58-4555-93f9-15a02fe35376))
		- [Return Negative](https://www.codewars.com/kata/55685cd7ad70877c23000102/train/javascript)
		  collapsed:: true
		  Repeat challenge: use only Math methods
			- My solution
				- ```javascript
				  function makeNegative(num) {
				    return num > 0 ? num * -1 : num;
				  }
				  ```
				- Note: initially got this wrong because I wrote ((663a5793-7173-4ff5-afdf-a9d6b9410119)) the wrong way around
			- Best practice
				- ```javascript
				  function makeNegative(num) {
				    return -Math.abs(num);
				  }
				  ```
		- [Calculate BMI](https://www.codewars.com/kata/57a429e253ba3381850000fb/javascript)
		  id:: 63f3e221-dce8-44ae-9ae5-781b54a95db1
		  collapsed:: true
			- My solution
			  id:: 527e66c4-29b7-45e2-90d1-3e896452f943
				- ```javascript
				  function bmi(weight, height) {
				    const bmi = weight / ( height * height)
				    
				    switch (true) {
				      case bmi <= 18.5:
				        return "Underweight";
				      case bmi <= 25.0:
				        return "Normal";
				      case bmi <= 30.0:
				        return "Overweight";
				      case bmi > 30:
				        return "Obese";
				    }
				  }
				  ```
			- Best practice
				- ```javascript
				  
				  ```
		- [Remove exclamation marks](https://www.codewars.com/kata/57a0885cbb9944e24c00008e/javascript)
		  collapsed:: true
			- My solution
				- ```javascript
				  function removeExclamationMarks(s) {
				    return s.split('').filter(el => el !== '!').join('');
				  }
				  ```
			- Best practice
			  id:: 84ff6676-f0d0-41f1-9e1a-1418ee207d16
				- ```javascript
				  function removeExclamationMarks(s) {
				    return s.replace(/!/gi, '');
				  }
				  ```
			- Clever
				- ```javascript
				  function removeExclamationMarks(s) {
				    return s.split('!').join('');
				  }
				  ```
		- [Sum Arrays](https://www.codewars.com/kata/53dc54212259ed3d4f00071c/javascript)
		  id:: 63ecfa3c-c989-4dcb-ab13-7ee56afd7282
		  collapsed:: true
			- My solution
			  id:: d65cdc60-c895-4d09-9565-5dff9abd924e
				- ```javascript
				  // Sum Numbers
				  function sum (numbers) {
				    if (numbers.length === 0) {
				      return 0
				    } else {
				      return numbers.reduce((a, b) => a + b);
				    }
				  };
				  ```
			- Best practice
			  id:: 9cecf650-f642-4248-8090-53e2ecf33703
				- ```javascript
				  function sum(numbers) {
				    return numbers.reduce((a, b) => a + b, 0);
				  }
				  ```
		- [Are You Playing Banjo?](https://www.codewars.com/kata/53af2b8861023f1d88000832/javascript)
		  collapsed:: true
		  id:: 63f33e7b-1a4b-413e-b00d-efe1a87c0a8a
			- My solution
				- ```javascript
				  function areYouPlayingBanjo(name) {
				    if(name[0]==="R" || name[0]==='r'){
				      return name+" plays banjo";
				      }
				      else{
				      return name+" does not play banjo";
				    }
				  }
				  ```
			- Best practice
			  id:: d6066a95-9e02-45c9-8d0c-6a3db80390be
				- ```javascript
				  function areYouPlayingBanjo(name) {
				    return name + (name[0].toLowerCase() == 'r' ? ' plays' : ' does not play') + " banjo";
				  }
				  ```
		- [The Feast of Many Beasts | Codewars](https://www.codewars.com/kata/5aa736a455f906981800360d/javascript)
		  collapsed:: true
		  id:: 63f33e7b-8d10-4739-8c49-2dfefc8d2c1e
			- My solution
				- ```javascript
				  ```
			- Best practice
			  id:: 5aee7c7d-c7f5-4201-936b-8e496e51e5dc
				- ```javascript
				  function feast(beast, dish) {
				  	return beast[0] === dish[0] && beast[beast.length - 1] === dish[dish.length - 1]
				  }
				  ```
		- [Thinkful - Logic Drills: Traffic light](https://www.codewars.com/kata/58649884a1659ed6cb000072/javascript)
		  id:: 63d18142-3084-4ee3-af2a-1e3187a3705f
		  collapsed:: true
			- Best practices
				- ```javascript
				  function updateLight(current) {
				    return current === 'yellow' ? 'red' : current === 'green' ? 'yellow' : 'green';
				  }
				  ```
				- or
				- Using ((636d5df2-5117-4f9e-8113-83bbb5eff6c1)) and ((63e40d8b-b5b5-4124-a386-e28fb962d7e1)):
				  id:: 63d18162-cbff-4ad7-aeec-71e2d5c72360
				  ```javascript
				  const updateLight = current => ({
				    green: 'yellow',
				    yellow: 'red',
				    red: 'green',
				  })[current]
				  ```
					- Without ((636d5df2-5117-4f9e-8113-83bbb5eff6c1)) it's equivalent to:
						- ```javascript
						  const updateLight = (function(current) {
						    return {
						      green: 'yellow',
						      yellow: 'red',
						      red: 'green',
						    }[current];
						  });
						  ```
							- ((63f8e09d-f644-4c5d-b08f-10fd01812842))
					- Without ((636d5df2-5117-4f9e-8113-83bbb5eff6c1)) and ((63e40d8b-b5b5-4124-a386-e28fb962d7e1)) it's equivalent to:
					  
					  #+BEGIN_TIP
					  Probably the real best practice for readability
					  #+END_TIP
						- ```javascript
						  function updateLight(current) {
						    return {
						      green: 'yellow',
						      yellow: 'red',
						      red: 'green',
						    }[current];
						  }
						  ```
						- Or more simply, with the extra step of declaring a variable:
							- ```javascript
							  function updateLight(current) {
							    let obj = {
							      green: 'yellow',
							      yellow: 'red',
							      red: 'green',
							    }
							    return obj[current] // Has to be bracket notation, see Takeaways
							  }
							  ```
					- Takeaways
					  id:: 63f8d6e9-0f6e-4b56-ab8a-04626cbb3244
						- Dot notation requires the property name be valid, whereas you have to instead use bracket notation if you're trying to access a variable
						  id:: 63f8d8cf-e3ec-47f7-b296-7e8e026a0d45
						- If using an ((63e40d8b-b5b5-4124-a386-e28fb962d7e1)) that you want to call later, then you need to assign it to a `const`. At that point you might as well make it an ((636d5df2-5117-4f9e-8113-83bbb5eff6c1))
						  id:: 63f8e09d-f644-4c5d-b08f-10fd01812842
						- Functions with an object or array variable and with `return obj[parameter]` are a useful pattern
						- If all your function does is declare an object or array then immediately return it, you can instead use `return {key: 'property'}[parameter]`
					- Explanation 1
						- The function returns the next color of a traffic light based on the current color. It does this by defining an object that maps each color to the next color. The object is constructed using JavaScript's object literal syntax, and is wrapped in parentheses to make it an ((63e40d8b-b5b5-4124-a386-e28fb962d7e1)).
						- When the function is called with a value of `current`, the object is accessed with `current` as the key, and the value corresponding to that key is returned. This effectively returns the next color in the sequence of green, yellow, red, green, and so on.
						- For example, if you call the function with the argument `'green'`, it will return `'yellow'`, because that is the next color in the sequence. If you call it with `'red'`, it will return `'green'`, and so on.
					- Explanation 2
						- The function returns an object & we access the object with square brackets `myObject[objectKey]`. So if you call `updateLight('green')`, we call the returned object['green'] & it returns `yellow`.
						- you have to use () around {} to "shield" it from becoming function brackets instead of object brackets
						- The Object "{}" encapsulated by "()" makes it a one-liner interpreted as  the return value. Therefore, it's still within function's scope.
						- Think of an object already declared;
							- const obj = {"a": "b"}
							- How would you access the key 'a' and, therefore, get the value b'?. You'd go obj['a'] and get 'b' as a result.
							- That's what's happening here. Only the object is created on-the-air without assigning it to a variable. Hence, say the current light is green, you'd then get 'yellow' since that's the respective key-value pair
		- [DNA to RNA conversion](https://www.codewars.com/kata/5556282156230d0e5e000089/train/javascript)
		  collapsed:: true
			- My solution
			  collapsed:: true
				- ```javascript
				  function DNAtoRNA(dna) {
				    let rna = ""
				    
				    for (let i = 0; i < dna.length; i++) {
				      if (dna[i] === "G" || dna[i] === "C" || dna[i] === "A") {
				        rna = `${rna}${dna[i]}`;
				      } else if (dna[i] === "T") {
				        rna = `${rna}U`;
				      } 
				    }
				    return rna;
				  }
				  ```
			- Best practice
			  id:: 6347b429-ccfa-48c2-9891-da957cb3f19a
			  collapsed:: true
				- ```javascript
				  function DNAtoRNA(dna){
				    return dna.replace(/T/g, 'U');
				  }
				  ```
		- [Abbreviate a Two Word Name](https://www.codewars.com/kata/57eadb7ecd143f4c9c0000a3/train/javascript)
		  collapsed:: true
			- Best practice
			  collapsed:: true
				- ```javascript
				  function abbrevName(name){
				    var nameArray = name.split(" ");
				    return (nameArray[0][0] + "." + nameArray[1][0]).toUpperCase();
				  }
				  ```
			- My solution
			  collapsed:: true
				- ```javascript
				  function abbrevName(name){
				    let initials = `${name[0]}.`
				    let surnameCapitalPosition = name.indexOf(' ') + 1;
				    let secondInitial = name[surnameCapitalPosition];
				    initials += secondInitial;
				    initials = initials.toUpperCase();
				    return initials
				  }
				  ```
		- [If you can't sleep, just count sheep!!](https://www.codewars.com/kata/5b077ebdaf15be5c7f000077/train/javascript)
		  collapsed:: true
			- Best practice
			  collapsed:: true
				- ```javascript
				  var countSheep = function (num){
				    let str = "";
				    for (let i = 1; i <= num; i++) { 
				      str+= `${i} sheep...`; 
				    }
				    return str;
				  }
				  ```
			- My solution
			  collapsed:: true
				- ```javascript
				  var countSheep = function (num){
				    let sentence = "";
				    for (let i = 0; i < num; i++) {   // for loop to count how many sheep
				      let c = i + 1;   // turn integer into a string + add murmur onto that string
				      sentence = sentence + `${c} sheep...`
				    }
				    return sentence;
				  }
				  ```
		- [Sentence Smash](https://www.codewars.com/kata/53dc23c68a0c93699800041d/train/javascript)
		  collapsed:: true
			- ```javascript
			  function smash (words) {
			    // store the sentence as a variable
			    let sentence = "";
			    // iterate over the array and add each word to the sentence
			    for (let i = 0; i < words.length; i++) {
			      sentence = sentence + `${words[i]} `
			    }
			    // ensure the last character of the sentence isn't a whitespace
			    sentence = sentence.slice(0, -1);
			    // return the sentence
			     return sentence;
			  };
			  ```
		- [Opposite Number](https://www.codewars.com/kata/56dec885c54a926dcd001095/train/javascript)
		  collapsed:: true
		  id:: 6350374c-70ca-4bef-a2e8-567973e8a603
			- ```javascript
			  function opposite(number) {
			    if (number < 0) {
			      return (Math.abs(number));
			    }
			    else {
			      return (-Math.abs(number));
			    }
			  }
			  ```
		- [Multiply](https://www.codewars.com/kata/50654ddff44f800200000004/train/javascript)
		- [Even Or Odd](https://www.codewars.com/kata/53da3dbb4a5168369a0000fe/train/javascript)
		- [Sum of Positive](https://www.codewars.com/kata/5715eaedb436cf5606000381/train/javascript)
- Related:
	- ((6400dba3-cba5-42aa-8818-111b7f4ece61))
	- [[JavaScript]] : ((6341c12f-21ed-489f-bb16-1734abd32b1f))
	- ((66ba013b-f6bb-4c97-9cce-8f506bc08714))