## Experience Level Selection

**Before starting, select your experience level:**

- Complete Beginner (Need 50/100 - focus on Problems 1-2)
- Intermediate (Need 70/100 - should handle Problems 1-3)
- Advanced (Need 80/100 - expected to attempt all problems)
- Free to use your most comfortable programming language

---

## Problem 1: Basic Variables and Operations (Easy - 12 Questions)

### Multiple Choice Questions (6 questions)

**Q1.** What will be the output of this pseudocode?

```
SET x = 5
SET y = 3
PRINT x + y
```

a) 8 b) 53 c) 5 + 3 d) Error

**Q2.** Which of the following is a valid variable name in most programming languages? a) 2variable b) variable-name c) variable_name d) variable name

**Q3.** What data type is the value `"Hello World"`? 
a) Integer b) Float c) String d) Boolean

**Q4.** Which operator is used for exponentiation in most programming languages? 

a) ^ b) ** c) exp d) pow

**Q5.** What is the result of `10 MOD 3` (modulus operation)?
a) 3 b) 1 c) 0 d) 3.33

**Q6.** What will this expression evaluate to: `NOT TRUE`?
a) TRUE b) FALSE c) 1 d) 0

### Tracing Questions (3 questions)

**Q7.** Trace through this pseudocode and determine the final value of `result`:

```
SET a = 10
SET b = 4
SET result = a - b * 2
PRINT result
```

What is printed?

**Q8.** What will be the output of this pseudocode?

```
SET x = 7
SET y = x + 3
SET x = y - 2
PRINT x, y
```

**Q9.** Trace this pseudocode step by step:

```
SET num = 15
SET num = num + 5
SET num = num DIV 4  // integer division
PRINT num
```

What is the final output?

### Coding Questions (3 questions)

**Q10.** Write a function to calculate the area of a rectangle given length and width. _Requirements: Declare variables, get input, calculate area, display result_

**Q11.** Write function to swap the values of two variables without using a third variable. _Show the step-by-step process_

**Q12.** write a function that converts temperature from Celsius to Fahrenheit. _Formula: F = (C × 9/5) + 32_

**Q13.** Write a function for a program that calculates compound interest and determines how many years it takes for an investment to double. _Formula: A = P(1 + r/n)^(nt)_ _Handle edge cases and provide year-by-year breakdown_

**Q14.** Write a Code that implements a basic calculator supporting parentheses and operator precedence. *Support: +, -, _, /, (, )_ _Use proper parsing and evaluation algorithms_

**Q15.** Write a Code for a function that converts any decimal number to any base (2-16). _Handle negative numbers and fractional parts_ _Include proper digit mapping for bases > 10_

---

## Problem 2: Control Structures (Medium - 15 Questions)

### Multiple Choice Questions (6 questions)

**Q13.** What will this pseudocode do?

```
SET x = 10
IF x > 5 THEN
    PRINT "Greater"
ELSE
    PRINT "Lesser"
END IF
```

a) Print "Greater" b) Print "Lesser" c) Print both d) Error

**Q14.** Which loop structure is best for iterating a known number of times? a) WHILE loop b) FOR loop c) DO-WHILE loop d) Infinite loop

**Q15.** What will this pseudocode output?

```
FOR i = 0 TO 2
    PRINT i
END FOR
```

a) 1 2 3 b) 0 1 2 c) 0 1 2 3 d) 1 2 3 4

**Q16.** What will happen with this pseudocode?

```
SET x = 0
WHILE x < 3
    PRINT x
    SET x = x + 1
END WHILE
```

a) Prints 0, 1, 2 b) Prints 1, 2, 3 c) Infinite loop d) Error

**Q17.** What is the purpose of the `BREAK` statement? a) Skip to next iteration b) Exit the loop entirely c) Pause the program d) Create a new loop

**Q18.** What does `CONTINUE` do in a loop?
a) Exits the loop b) Skips remaining code in current iteration c) Restarts the loop d) Pauses execution

### Tracing Questions (4 questions)

**Q19.** Trace this pseudocode:

```
SET total = 0
FOR i = 1 TO 3
    SET total = total + i * 2
END FOR
PRINT total
```

What is the final value of `total`?

**Q20.** What will this pseudocode print?

```
SET x = 10
WHILE x > 0
    IF x MOD 2 = 0 THEN
        PRINT "Even:", x
    END IF
    SET x = x - 3
END WHILE
```

**Q21.** Trace through this nested loop:

```
SET result = ""
FOR i = 1 TO 2
    FOR j = 1 TO i
        SET result = result + STRING(i)
    END FOR
END FOR
PRINT result
```

What is the final value of `result`?

**Q22.** What does this pseudocode output?

```
SET count = 0
FOR i = 0 TO 4
    IF i MOD 2 = 1 THEN
        SET count = count + 1
    END IF
END FOR
PRINT count
```

### Coding Questions (5 questions)

**Q23.** Write pseudocode to find the largest number among three given numbers. _Use IF-ELSE statements, no arrays_

**Q24.** Write a Code for a simple guessing game where the user has 3 attempts to guess a number between 1-10. _Include input validation and feedback_

**Q25.** Write a Code to calculate the factorial of a positive integer using a loop. _Example: 5! = 5 × 4 × 3 × 2 × 1 = 120_

**Q26.** Write a Code that prints all even numbers from 2 to 20. _Use appropriate loop structure_

**Q27.** Write pseudocode to validate a password with these rules:

- At least 8 characters long
- Contains at least one digit
- Contains at least one uppercase letter _Return TRUE if valid, FALSE otherwise_

---

## Problem 3: Functions and Data Structures (Medium-Hard - 15 Questions)

### Multiple Choice Questions (6 questions)

**Q28.** What will this function return?

```
FUNCTION addNumbers(a, b)
    RETURN a + b
END FUNCTION

SET result = addNumbers(3, 7)
```

a) 10 b) 37 c) "3 + 7" d) Nothing

**Q29.** What is the scope of variable `x` in this pseudocode?

```
FUNCTION calculate()
    SET x = 5
    RETURN x * 2
END FUNCTION
```

a) Global scope b) Local to the function c) Both global and local d) Undefined

**Q30.** What will this pseudocode output?

```
FUNCTION greet(name = "World")
    RETURN "Hello, " + name + "!"
END FUNCTION

PRINT greet()
```

a) Hello, World! b) Hello, name! c) Hello, ! d) Error

**Q31.** What is the length of this array?

```
SET myArray = [1, 2, [3, 4], 5]
```

a) 3 b) 4 c) 5 d) 6

**Q32.** What will `myArray[1]` return from `SET myArray = ["a", "b", "c", "d"]`? a) "a" b) "b" c) "c" d) Error

**Q33.** In a hash table/dictionary, what is the average time complexity for lookup operations? a) O(1) b) O(log n) c) O(n) d) O(n²)

### Tracing Questions (4 questions)

**Q34.** Trace this function:

```
FUNCTION processList(numbers[])
    SET total = 0
    FOR each num IN numbers
        IF num MOD 2 = 0 THEN
            SET total = total + num
        END IF
    END FOR
    RETURN total
END FUNCTION

SET result = processList([1, 2, 3, 4, 5, 6])
PRINT result
```

What is printed?

**Q35.** What will this pseudocode output?

```
FUNCTION modifyArray(arr[])
    ADD 4 TO arr
    RETURN arr
END FUNCTION

SET original = [1, 2, 3]
SET newArray = modifyArray(original)
PRINT LENGTH(original), LENGTH(newArray)
```

**Q36.** Trace through this hash table manipulation:

```
SET scores = {"Alice": 85, "Bob": 92}
SET scores["Charlie"] = 78
SET scores["Alice"] = scores["Alice"] + 5
PRINT scores["Alice"], SIZE(scores)
```

**Q37.** What does this nested function return?

```
FUNCTION outer(x)
    FUNCTION inner(y)
        RETURN x + y
    END FUNCTION
    RETURN inner(x * 2)
END FUNCTION

SET result = outer(3)
PRINT result
```

### Coding Questions (5 questions)

**Q38.** Write a function in pseudocode that takes an array of integers and returns the sum of all positive numbers. _Handle edge cases like empty arrays_

**Q39.** Create pseudocode for a function that reverses a string without using built-in reverse functions. _Example: "hello" becomes "olleh"_

**Q40.** Write pseudocode for a function that finds the second largest number in an array. _Handle cases where array has duplicates or insufficient elements_

**Q41.** Create a function that checks if a string is a palindrome (reads same forwards and backwards). _Ignore case and spaces. Example: "A man a plan a canal Panama"_

**Q42.** Write pseudocode for a simple stack implementation with push, pop, and isEmpty operations. _Use an array as the underlying data structure_

---

## Problem 4: Advanced Concepts (Hard - 8 Questions)

### Multiple Choice Questions (3 questions)

**Q43.** What is the time complexity of binary search in a sorted array? a) O(1) b) O(log n) c) O(n) d) O(n²)

**Q44.** What will this recursive function return for `factorial(4)`?

```
FUNCTION factorial(n)
    IF n <= 1 THEN
        RETURN 1
    END IF
    RETURN n * factorial(n - 1)
END FUNCTION
```

a) 24 b) 12 c) 4 d) 10

**Q45.** In object-oriented programming, what is inheritance? a) Creating multiple objects b) One class acquiring properties of another class c) Hiding implementation details d) Grouping related functions

### Tracing Questions (2 questions)

**Q46.** Trace this recursive function:

```
FUNCTION fibonacci(n)
    IF n <= 1 THEN
        RETURN n
    END IF
    RETURN fibonacci(n-1) + fibonacci(n-2)
END FUNCTION

SET result = fibonacci(5)
PRINT result
```

What is the output?

**Q47.** Trace this sorting algorithm:

```
FUNCTION bubbleSort(arr[], n)
    FOR i = 0 TO n-2
        FOR j = 0 TO n-2-i
            IF arr[j] > arr[j+1] THEN
                SWAP arr[j] AND arr[j+1]
            END IF
        END FOR
    END FOR
END FUNCTION

SET numbers = [64, 34, 25]
CALL bubbleSort(numbers, 3)
PRINT numbers
```

### Coding Questions (3 questions)

**Q48.** Write a recursive function that calculates the sum of all numbers from 1 to n. _Include base case and recursive case_

**Q49.** Create pseudocode for a binary search algorithm that finds a target value in a sorted array. _Return the index if found, -1 if not found_

**Q50.** Design pseudocode for a simple class "BankAccount" with the following:

- Properties: accountNumber, balance, ownerName
- Methods: deposit(amount), withdraw(amount), getBalance()
- Include proper encapsulation and validation

**Q51.** Write  a function that implements the Merge Sort algorithm. _Include the merge helper function and handle the divide-and-conquer approach_
_Requirements: Split array recursively, merge sorted subarrays_

**Q52.** Create  a Graph representation using adjacency lists and implement a Depth-First Search (DFS) traversal. _Include: addVertex, addEdge, and DFS functions_ _Handle visited tracking and recursive exploration_

**Q53.** Design  a Hash Table implementation with collision handling using chaining. _Include: hash function, insert, search, delete operations_ _Handle dynamic resizing when load factor exceeds 0.75_

**Q54.** Write a function for finding the Longest Common Subsequence (LCS) between two strings using dynamic programming. _Example: LCS("ABCDGH", "AEDFHR") = "ADH"_ _Create the DP table and reconstruct the solution_

**Q55.** Create a function for a Red-Black Tree insertion algorithm. _Include: node structure, insertion, rotation operations, and rebalancing_ _Handle all cases for maintaining Red-Black tree properties_

**Q56.** write a code  for implementing Dijkstra's shortest path algorithm. _Use a priority queue/min-heap for efficient vertex selection_ _Handle edge weights and return shortest distances from source to all vertices_

**Q57.** Write  a function that solves the N-Queens problem using backtracking. _Place N queens on an N×N chessboard so no two queens attack each other_ _Include constraint checking and backtracking logic_

**Q58.** Write a Code for a Trie (Prefix Tree) data structure with insert, search, and prefix matching operations. _Include: node structure, word insertion, complete word search, and finding all words with given prefix_ _Handle end-of-word marking and memory-efficient implementation_

---

## Scoring Guidelines

### Complete Beginners (Need 25/50 correct = 50%)

- Focus on Problems 1-2
- Should demonstrate understanding of basic programming concepts
- Coding questions can be partially correct for credit

### Intermediate (Need 35/50 correct = 70%)

- Should handle Problems 1-3 confidently
- Expected to write functional pseudocode
- Should understand control structures and basic algorithms

### Advanced (Need 40/50 correct = 80%)

- Expected to perform well across all problems
- Should demonstrate understanding of advanced concepts
- Coding solutions should be efficient and well-structured

## Evaluation Criteria for Coding Questions:

- **Correctness**: Does the pseudocode solve the problem?
- **Logic**: Is the algorithmic thinking sound?
- **Structure**: Proper use of control structures and functions
- **Edge Cases**: Consideration of special cases
- **Clarity**: Readable and well-organized pseudocode