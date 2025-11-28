- Meta
	- {{embed ((650bfce0-c829-4e70-9a73-b2a9738f81e5))}}
- Takeaways
	- ^^- converted everything below from CodeWars links to a link to a method and notes of how to utilise it - ^^
	- [[C#]] : ((650bfd83-b79c-4eb6-aeb3-2578fd73df32))
	  collapsed:: true
		- {{embed ((650bfd83-b79c-4eb6-aeb3-2578fd73df32))}}
- Completed solutions
	- 5 kyu (21 score)
	- 6 kyu (8 score)
	- 7 kyu (3 score)
	- 8 kyu (2 score)
		- [Grasshopper - Grade book](https://www.codewars.com/kata/55cbd4ba903825f7970000f5/train/csharp)
		  collapsed:: true
			- My solution
				- ```javascript
				  using System;
				  
				  public class Kata
				  {
				    public static char GetGrade(int s1, int s2, int s3)
				    {
				      int total = (s1 + s2 + s3) / 3;
				      
				      if (total >= 90 && total <= 100)
				      {
				        return 'A';
				      }
				      else if (total >= 80 && total < 90)
				      {
				        return 'B';
				      }
				      else if (total >= 70 && total < 80)
				      {
				        return 'C';
				      }
				      else if (total >= 60 && total < 70)
				      {
				        return 'D';
				      }
				      else {
				        return 'F';
				      }
				    }
				  }
				  ```
			- Best practice
				- ```javascript
				  using System;
				  
				  public class Kata
				  {
				    public static char GetGrade(int s1, int s2, int s3)
				    {
				      var s = (s1 + s2 + s3)/3;
				      if (60 > s) return 'F';
				      if (70 > s) return 'D';
				      if (80 > s) return 'C';
				      if (90 > s) return 'B';
				      return 'A';
				   }
				  }
				  ```
					- Remember that curly brackets are optional sometimes
					  id:: 650c05e4-ec3c-4711-857d-7e22f4e53d97
						- Example
							- ```c#
							  if (60 > s) return 'F';
							  
							  // 2nd example
							  if (60 > s)
							      {
							        return 'D';
							      }
							  ```
- Related:
	- ((6400dba3-cba5-42aa-8818-111b7f4ece61))
	- [[C#]]
	- ((66ba013b-f6bb-4c97-9cce-8f506bc08714))