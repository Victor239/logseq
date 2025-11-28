# Completed solutions
	- 5 kyu (21 score)
	- 6 kyu (8 score)
	- 7 kyu (3 score)
	- 8 kyu (2 score)
		- [Quadrants | Codewars](https://www.codewars.com/kata/643af0fa9fa6c406b47c5399/train/shell)
		  collapsed:: true
		  Repeat challenge: use a single if-else statement and ternary operators. can look up ternary operator syntax
			- My solution
				- ```shell
				  #!/bin/bash
				  
				  : '
				  Parameters:
				  $1 - X coordinate
				  $2 - Y Coordinate
				  '
				  
				  # Initialize direction variables
				  num1=""
				  num2=""
				  
				  # Determine the direction for the X coordinate
				  if (( $1 > 0 )); then
				    num1="e"  # East
				  else
				    num1="w"  # West
				  fi
				  
				  # Determine the direction for the Y coordinate
				  if (( $2 > 0 )); then
				    num2="n"  # North
				  else
				    num2="s"  # South
				  fi
				  
				  # Determine the quadrant based on num1 and num2
				  if [[ $num1 == "e" && $num2 == "n" ]]; then
				    echo 1
				  elif [[ $num1 == "w" && $num2 == "n" ]]; then
				    echo 2
				  elif [[ $num1 == "w" && $num2 == "s" ]]; then
				    echo 3
				  elif [[ $num1 == "e" && $num2 == "s" ]]; then
				    echo 4
				  fi
				  
				  exit
				  ```
					- With some ChatGPT help for formatting
			- Best practice
				- ```shell
				  #!/bin/bash
				  
				  if (($1 > 0)); then
				    (($2 > 0 )) && echo 1 || echo 4
				  else
				    (($2 > 0 )) && echo 2 || echo 3
				  fi
				  ```
		- [Keep Hydrated! | Codewars](https://www.codewars.com/kata/582cb0224e56e068d800003c/train/shell)
		  collapsed:: true
		  Repeat challenge: use
			- My solution
				- ```shell
				  #!/bin/bash
				  time=$1
				  echo $time*0.5/1 | bc
				  ```
					- `| bc` suffix allows you to do arithmetic with decimals, instead of integers only
					  id:: 19485a88-a441-470e-86b2-9f32402c953a
					- `/1` rounds the resulting number, so it's instead an integer instead of a decimal/floating point
					  id:: 678cda80-df87-4c61-9f3e-07b91e6e7dab
			- Best practice
				- ```shell
				  #!/bin/bash
				  time=$1
				  echo "$1/2" | bc
				  ```
		- [Grasshopper - Debug sayHello | Codewars](https://www.codewars.com/kata/5625618b1fe21ab49f00001f/train/shell)
		  collapsed:: true
		  Repeat challenge: use
			- My solution/best practice
				- ```shell
				  #!/bin/bash 
				  say_hello(){
				     echo "Hello, $1"
				  }
				  say_hello "$1"
				  ```
		- [Beginner Series #2 Clock | Codewars](https://www.codewars.com/kata/55f9bca8ecaa9eac7100004a/train/shell)
		  collapsed:: true
		  Repeat challenge: use
			- My solution
				- ```shell
				  h=$1
				  m=$2
				  s=$3
				  
				  echo $(((h*3600000)+(m*60000)+(s*1000)))
				  ```
				-
			- Best practice
				- ```shell
				  h=$1
				  m=$2
				  s=$3
				  echo $(( ($h * 3600 + $m * 60 + $s) * 1000 ))
				  ```
		- [Grasshopper - Summation | Codewars](https://www.codewars.com/kata/55d24f55d7dd296eb9000030/train/shell)
		  collapsed:: true
		  Repeat challenge: use
			- My solution
				- ```shell
				  #!/bin/bash
				  
				  n=$1
				  num=0
				  
				  for ((i=0; i<n; i++)); do
				    num=$((num + i + 1))
				  done
				  
				  echo "$num"
				  ```
			- Best practice
				- ```shell
				  #!/bin/bash
				  
				  n=$1
				  num=0
				  
				  for ((i=0; i<n; i++)); do
				    num=$((num + i + 1))
				  done
				  
				  echo "$num"
				  ```
				-
		- [Expressions Matter | Codewars](https://www.codewars.com/kata/5ae62fcf252e66d44d00008e/train/shell)
		  collapsed:: true
		  Repeat challenge: use
			- My solution
				- ```shell
				  #!/bin/bash
				  
				  a=$1
				  b=$2
				  c=$3
				  
				  var=$((a * b * c))
				  
				  if (((a * b) * c > var)); then
				    var=$(((a * b) * c))
				  fi
				  if ((a * (b * c) > var)); then
				    var=$((a * (b * c)))
				  fi
				  #
				  if ((a + b * c > var)); then
				    var=$((a + b * c))
				  fi
				  
				  if ((a + (b * c) > var)); then
				    var=$((a + (b * c)))
				  fi
				  
				  if (((a + b) * c > var)); then
				    var=$(((a + b) * c))
				  fi
				  #
				  if ((a * b + c > var)); then
				    var=$((a * b + c))
				  fi
				  
				  if ((a * (b + c) > var)); then
				    var=$((a * (b + c)))
				  fi
				  
				  if (((a * b) + c > var)); then
				    var=$(((a * b) + c))
				  fi
				  
				  if ((a + b + c > var)); then
				    var=$((a + b + c))
				  fi
				  
				  printf "%s\n" "$var"
				  ```
			- Best practice
				- ```shell
				  a=$1
				  b=$2
				  c=$3
				  
				  printf "$((a + b + c))\n $(((a + b)*c))\n $((a * (b + c)))\n $((a * b * c))" | sort -n | tail -n 1
				  ```
			- Best practice 2
				- ```shell
				  a=$1
				  b=$2
				  c=$3
				  # your code here
				  
				  ar=($( echo "$1 * ($2 + $3)" | bc )
				      $( echo "$1 * $2 * $3" | bc )
				      $( echo "$1 + $2 + $3" | bc )
				      $( echo "$1 + $2 * $3" | bc )
				      $( echo "$1 * $2 + $3" | bc )
				      $( echo "($1 + $2) * $3" | bc ))
				  IFS=$'\n'
				  echo "${ar[*]}" | sort -nr | head -n1
				  ```
		- [Volume of a Cuboid | Codewars](https://www.codewars.com/kata/58261acb22be6e2ed800003a/train/shell)
		  collapsed:: true
		  Repeat challenge: use
			- My (limited) solution
				- ```shell
				  #!/bin/bash
				  length=$1
				  width=$2
				  height=$3
				  
				  #Can handle integers only
				  #echo $((length * width * height))
				  
				  # Use bc for floating-point arithmetic
				  echo "$length * $width * $height" | bc
				  ```
					- To handle decimals in your script, you need to modify it since `((...))` only works with integer arithmetic in Bash. For decimal (floating-point) operations, you'll need to use a tool like `bc` (Bash Calculator), which supports floating-point arithmetic.
					  id:: 4910918d-a2dc-47cf-9f45-1e0dcf14fdfb
			- Best practice
				- ```shell
				  #!/bin/bash
				  echo $1*$2*$3 | bc
				  ```
		- [Remove String Spaces | Codewars](https://www.codewars.com/kata/57eae20f5500ad98e50002c5/shell)
		  collapsed:: true
		  Repeat challenge: use
			- My solution
				- ```shell
				  var="$1"
				  array1=()
				  
				  for ((i = 0; i < ${#var}; i++)); do
				    char="${var:i:1}"
				  
				    if [[ "$char" == " " ]]; then
				      : 
				    else
				      array1+=("$char")
				    fi
				  
				  done
				  
				  printf "%s" "${array1[@]}"
				  ```
					- With comments
					  collapsed:: true
						- ```shell
						  var="$1"
						  array1=()
						  
						  # Loop through each character of the string
						  for ((i = 0; i < ${#var}; i++)); do
						    # Get the ith character of the string
						    char="${var:i:1}"
						  
						    if [[ "$char" == " " ]]; then
						      :  # This is a no-op, does nothing
						    else
						      # Append the character to the array
						      array1+=("$char")
						    fi
						  
						    # Print the character without a newline (as opposed to echo which adds a newline)
						    #printf "%s" "$char"
						  done
						  
						  # Print the resulting array
						  # echo "${array1[@]}" # echo adds spaces/newlines automatically
						  printf "%s" "${array1[@]}"
						  ```
					- ((678cc3ba-42a6-4c2c-a6ab-047be5e0b01f))
			- Best practice
				- id:: b39b308a-c1c0-455e-be4e-af7bc83df1df
				  ```shell
				  echo ${1// /}
				  ```
					- It is basic string replacement where the syntax = `${var_name/replacement/pattern_to_replace}`, thus in this case, every space is replaced by nothing, eliminating all spaces.
					- Here are some examples: [string - Replace one character with another in Bash - Stack Overflow](https://stackoverflow.com/questions/5928156/replace-one-character-with-another-in-bash)
					- More details on parameter expansion here: [Shell Parameter Expansion (Bash Reference Manual)](https://www.gnu.org/software/bash/manual/html_node/Shell-Parameter-Expansion.html)
		- [Grasshopper - Terminal game move function | Codewars](https://www.codewars.com/kata/563a631f7cbbc236cf0000c2/shell)
		  collapsed:: true
		  Repeat challenge: use
			- My solution
				- ```shell
				  ```
				-
			- Best practice
			  id:: 7bb53ae2-9d3e-4b44-97ff-c8ee3023577e
				- ```shell
				  #!/bin/bash
				  echo $(( $1+$2*2 ))
				  ```
				- Better explained:
					- ```shell
					  position=$1
					  roll=$2
					  echo $((position + 2 * roll))
					  ```
					- `$((...))` is the Bash arithmetic expansion syntax. It is used specifically for performing arithmetic calculations (addition, subtraction, multiplication, etc.) and evaluating expressions in the context of integer math.
					- Inside `((...))`, you can reference variables (like position and roll), and Bash will automatically treat them as numbers for evaluation.
					- The result of the arithmetic expression inside `$((...))` is then expanded (calculated) and passed to echo to be printed.
				- Wrong syntax:
					- `$(...)` is used for command substitution, which executes a command and replaces it with the output of that command.
					- The expression position `+ 2 * roll` is not a command; it's just an arithmetic expression, and Bash expects to execute a command inside `$(...)`.
					- As a result, Bash tries to execute position `+ 2 * roll` as a command, which leads to an error because position and roll are not valid commands.
- Related:
	- [[Terminal]] : ((644c0b9b-9c03-42c8-99b7-f9dfb8282bbb))
	- ((66ba013b-f6bb-4c97-9cce-8f506bc08714))