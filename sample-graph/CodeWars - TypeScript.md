# Completed solutions
	- 5 kyu (21 score)
	- 6 kyu (8 score)
	- 7 kyu (3 score)
		- [Vowel Count](https://www.codewars.com/kata/54ff3102c1bad923760001f3/solutions/typescript?filter=all&sort=best_practice&invalids=false)
		  collapsed:: true
		  Repeat challenge: do it whilst using output of ((63470fd1-1f37-4428-9546-d674c323d5d1))
			- My solution
				- ```javascript
				  export class Kata {
				    static getCount(str: string): number {
				      let count = 0;
				      str.split('').map(l => l.match(/[aeiou]/g) ? count++ : null);
				      return count;
				    }
				  }
				  ```
				-
			- Best practice
				- ```javascript
				  export class Kata {
				    static getCount(str: string) {
				      let list = str.match(/[aeiou]/gi);
				      return list ? list.length : 0;
				    }
				  }
				  ```
				-
		- [Disemvowel Trolls](https://www.codewars.com/kata/52fba66badcd10859f00097e)
		  id:: 66bcd59d-2f68-46bb-a8f3-fa69662a2550
		  collapsed:: true
		  Repeat challenge: do not use ChatGPT
			- My solution
				- id:: 3a79d84c-5151-4266-92d2-0bff4950d7cf
				  ```javascript
				  export class Kata {
				    static disemvowel(str: string): string {
				      return str.replaceAll(/[aeiou]/gi, '');
				    }
				  }
				  ```
					- ((66bcda69-ebaa-46cb-8ac6-3b4797a2b46a))
					- ((66bcdaa8-499c-4e30-8ae8-1807ae820ef7))
					- ((63679853-5edb-4076-9cc2-53971f791893))
					- ((663a5793-a50a-4b0f-8c7e-6fdfd3a0a9b3))
				- Note: doing this on separate lines does not work because strings/arrays are immutable in [[JavaScript]]?
					- ```js
					  str.replaceAll(/[aeiou]/gi, '')
					  return str;
					  ```
					- Related: [[JavaScript]] : ((66bce5d1-babc-4aa9-b668-2fd3dd5b45be))
			- Best practice
				- ```javascript
				  export class Kata {
				    static disemvowel(str: string) {
				      return str.replace(/[aeiou]/gi, "");
				    }
				  }
				  ```
			- Related: ((63470fd1-78ae-41e3-a0b5-43bf0527755d))
	- 8 kyu (2 score)
		- [Even or Odd](https://www.codewars.com/kata/53da3dbb4a5168369a0000fe/train/typescript)
		  id:: 66bcfb80-153b-4150-8a81-55265346843f
		  collapsed:: true
		  Repeat challenge: get it right first time without any tests
			- My solution
			  id:: bafb3e0c-656f-444e-b766-3a10e38e04c3
				- id:: 63b36007-4080-4e8f-b0ab-99ab1d8f4d40
				  ```javascript
				  export function evenOrOdd(n:number):string {
				    return n % 2 ? "Odd" : "Even";
				  }
				  ```
			- Best practice
				- ```javascript
				  export function evenOrOdd(n:number):string {
				    return n % 2 === 0 ? 'Even' :'Odd';
				  }
				  ```
				-
		- [Reversed Strings](https://www.codewars.com/kata/5168bb5dfe9a00b126000018)
		  collapsed:: true
		  Repeat challenge: do it in one line
			- My solution
				- ```javascript
				  export function solution(str: string): string {
				    let arr : string[] = str.split('');
				    return arr.reverse().join('');
				  }
				  ```
				-
			- Best practice
				- ```javascript
				  export function solution(str: string): string {
				    return str.split("").reverse().join("");
				  }
				  ```
				- Clever alternative
					- ```typescript
					  export function solution(str: string): string {
					    return [...str].reverse().join('');
					  }
					  ```
		- [Opposite number](https://www.codewars.com/kata/56dec885c54a926dcd001095)
		  collapsed:: true
		  Repeat challenge: don't use the number `1`
			- My solution
				- ```javascript
				  export class Kata {
				    static opposite(n: number) {
				     return n*(-1);
				    }
				  }
				  ```
				-
			- Best practice
				- ```javascript
				  export class Kata {
				    static opposite(n: number) {
				      return -n;
				    }
				  }
				  ```
				-
- Related:
	- ((66ba013b-f6bb-4c97-9cce-8f506bc08714))
	- ((629ccb26-1eab-4686-a7b8-f9433a871440))