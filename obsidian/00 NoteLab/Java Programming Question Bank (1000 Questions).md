## Table of Contents

1. [Conditionals and Boolean Logic (150 questions)](#conditionals-and-boolean-logic-150-questions)
2. [Loops (150 questions)](#loops-150-questions)
3. [Arrays (200 questions)](#arrays-200-questions)
4. [Classes and Objects (200 questions)](#classes-and-objects-200-questions)
5. [Exception Handling (100 questions)](#exception-handling-100-questions)
6. [Collections Framework (100 questions)](#collections-framework-100-questions)
7. [Time Complexity and Algorithms (100 questions)](#time-complexity-and-algorithms-100-questions)

---

## Conditionals and Boolean Logic (150 questions)

### Basic If-Else Statements
1. What is the output when x = 5?
   ```java
   if (x > 3) {
       System.out.println("A");
   } else {
       System.out.println("B");
   }
   ```

2. Write a Java program that checks if a number is positive, negative, or zero.

3. What is wrong with this code?
   ```java
   if (score = 100)
       System.out.println("Perfect!");
   ```

4. Convert this if-else statement to a ternary operator:
   ```java
   if (temperature > 30) {
       System.out.println("Hot");
   } else {
       System.out.println("Cool");
   }
   ```

5. What is the output when age = 16?
   ```java
   if (age >= 18) {
       System.out.println("Adult");
   } else if (age >= 13) {
       System.out.println("Teen");
   } else {
       System.out.println("Child");
   }
   ```

### Boolean Expressions
6. Evaluate: `!(true && false) || (false || true)`

7. Simplify using DeMorgan's Laws: `!(x > 5 && y < 10)`

8. What is the value of `flag` after execution?
   ```java
   boolean flag = (5 != 5) || (3 >= 2);
   ```

9. Write a condition to check if a year is a leap year.

10. What is the output?
    ```java
    int a = 5, b = 3;
    System.out.println(a > b && b < a || a == b);
    ```

### Switch Statements
11. What is the output when day = 3?
    ```java
    switch(day) {
        case 1: System.out.println("Monday"); break;
        case 2: System.out.println("Tuesday"); break;
        case 3: System.out.println("Wednesday"); break;
        default: System.out.println("Invalid");
    }
    ```

12. Convert this if-else chain to a switch statement:
    ```java
    if (grade == 'A') {
        System.out.println("Excellent");
    } else if (grade == 'B') {
        System.out.println("Good");
    } else if (grade == 'C') {
        System.out.println("Average");
    } else {
        System.out.println("Fail");
    }
    ```

13. What happens if you omit the break statement in a switch case?

14. Write a switch statement that checks the month number and prints the season.

15. Can you use strings in a switch statement? If yes, give an example.

### Nested Conditionals
16. What is the output when x = 10, y = 5?
    ```java
    if (x > 5) {
        if (y > 5) {
            System.out.println("A");
        } else {
            System.out.println("B");
        }
    } else {
        System.out.println("C");
    }
    ```

17. Write a program to find the largest of three numbers using nested if statements.

18. Identify the error in this nested if structure:
    ```java
    if (score >= 90)
        System.out.println("A");
        if (score >= 80)
            System.out.println("B");
    else
        System.out.println("C");
    ```

19. Rewrite this nested if using logical operators:
    ```java
    if (x > 0) {
        if (y > 0) {
            System.out.println("First quadrant");
        }
    }
    ```

20. What is the problem with this code?
    ```java
    if (income < 50000) rate = 0.22;
    if (income < 100000) rate = 0.25;
    if (income < 150000) rate = 0.28;
    ```

### Comparing Data
21. Why shouldn't you use == to compare floating-point numbers?

22. Write code to compare two floating-point numbers with a tolerance of 0.0001.

23. How do you compare two strings for equality in Java?

24. What is lexicographic ordering in string comparison?

25. What is the output?
    ```java
    String s1 = "hello";
    String s2 = "HELLO";
    System.out.println(s1.compareTo(s2));
    ```

(Continuing with 125 more questions in this category...)

---

## Loops (150 questions)

### For Loops
26. What is the output?
    ```java
    for (int i = 1; i <= 5; i++) {
        System.out.print(i + " ");
    }
    ```

27. Write a for loop to print all even numbers between 1 and 100.

28. What is wrong with this loop?
    ```java
    for (int i = 5; i >= 0; i++) {
        System.out.println(i);
    }
    ```

29. Convert this for loop to a while loop:
    ```java
    for (int i = 0; i < 10; i += 2) {
        System.out.println(i);
    }
    ```

30. What is the output?
    ```java
    for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 3; j++) {
            System.out.print(i + "," + j + " ");
        }
        System.out.println();
    }
    ```

### While Loops
31. What is the output?
    ```java
    int i = 5;
    while (i > 0) {
        System.out.print(i + " ");
        i--;
    }
    ```

32. Write a while loop to find the first power of 2 greater than 1000.

33. What is the problem with this while loop?
    ```java
    int x = 10;
    while (x > 0) {
        System.out.println(x);
    }
    ```

34. Convert this while loop to a do-while loop:
    ```java
    int count = 0;
    while (count < 5) {
        System.out.println("Hello");
        count++;
    }
    ```

35. Write a program to calculate the sum of digits of a number using a while loop.

### Loop Control Statements
36. What is the difference between break and continue?

37. What is the output?
    ```java
    for (int i = 0; i < 10; i++) {
        if (i == 5) break;
        System.out.print(i + " ");
    }
    ```

38. Write a loop that prints numbers 1-10 but skips 5 using continue.

39. What is wrong with this break statement?
    ```java
    if (x > 10) {
        break;
    }
    ```

40. How can you exit from nested loops? Provide an example.

### Fencepost Problems
41. What is a fencepost problem in loops? Give an example.

42. Write a loop to print numbers 1-5 separated by commas (1, 2, 3, 4, 5).

43. Fix this fencepost error:
    ```java
    for (int i = 1; i <= 5; i++) {
        System.out.print(i + ", ");
    }
    ```

44. Write a program to print a multiplication table without fencepost issues.

45. What is the output of this fencepost problem?
    ```java
    System.out.print("Start:");
    for (int i = 0; i < 3; i++) {
        System.out.print(" " + i + ",");
    }
    System.out.println("End");
    ```

### Sentinel Values
46. What is a sentinel value? Provide an example.

47. Write a program that reads numbers until -1 is entered, then prints the sum.

48. What is wrong with this sentinel loop?
    ```java
    int sum = 0;
    int num = 0;
    while (num != -1) {
        sum += num;
        System.out.print("Enter number: ");
        num = input.nextInt();
    }
    ```

49. Fix the sentinel loop in question 48 to avoid fencepost problems.

50. Write a sentinel-controlled loop to find the average of positive numbers entered (sentinel = -1).

(Continuing with 100 more questions in this category...)

---

## Arrays (200 questions)

### Basic Array Operations
51. How do you declare and initialize an array of 10 integers?

52. What is the output?
    ```java
    int[] arr = {1, 2, 3, 4, 5};
    System.out.println(arr[2]);
    ```

53. Write code to find the maximum value in an array.

54. What happens if you try to access arr[5] in a 5-element array?

55. How do you copy the contents of one array to another?

### Multi-dimensional Arrays
56. How do you declare a 3x3 matrix in Java?

57. Write code to initialize a 2D array with values 1-9.

58. How would you print the diagonal elements of a square matrix?

59. Write a method to multiply two matrices.

60. What is the output?
    ```java
    int[][] grid = new int[2][3];
    System.out.println(grid.length);
    System.out.println(grid[0].length);
    ```

### Array Algorithms
61. Implement linear search on an array.

62. Write a method to reverse an array in place.

63. How would you remove duplicates from a sorted array?

64. Implement the selection sort algorithm.

65. Write a program to find all pairs in an array that sum to a given number.

### ArrayList Class
66. What is the difference between an array and an ArrayList?

67. How do you convert an ArrayList to an array?

68. Write code to remove all even numbers from an ArrayList of integers.

69. What is the output?
    ```java
    ArrayList<String> list = new ArrayList<>();
    list.add("A");
    list.add("B");
    list.add(0, "C");
    System.out.println(list);
    ```

70. How would you sort an ArrayList of custom objects?

### Array as Parameters
71. Write a method that takes an array and returns the sum of its elements.

72. How are arrays passed to methods in Java - by value or by reference?

73. Write a method that takes two arrays and returns true if they are equal.

74. What is wrong with this method?
    ```java
    public static void resize(int[] arr, int newSize) {
        arr = new int[newSize];
    }
    ```

75. Write a method that returns a new array with elements in reverse order.

(Continuing with 125 more questions in this category...)

---

## Classes and Objects (200 questions)

### Class Fundamentals
76. What are the four pillars of OOP? Explain each briefly.

77. How do you define a simple Person class with name and age attributes?

78. What is the difference between a class and an object?

79. Write a constructor for a Circle class with radius attribute.

80. What is the purpose of the toString() method?

### Encapsulation
81. Why should instance variables be private?

82. Write proper getter and setter methods for a Student class with GPA attribute.

83. What is wrong with this class definition?
    ```java
    public class Account {
        public double balance;
        // ...
    }
    ```

84. How would you make a read-only property in Java?

85. What is the benefit of using accessor methods instead of public fields?

### Inheritance
86. Create a Vehicle superclass and Car subclass that extends it.

87. What is method overriding? Give an example.

88. How do you call a superclass constructor from a subclass?

89. What is the difference between super() and this()?

90. Can a class extend multiple classes in Java? Why or why not?

### Polymorphism
91. What is polymorphism? Give an example.

92. What is the difference between compile-time and runtime polymorphism?

93. Write an example demonstrating method overloading.

94. Why can't you override static methods in Java?

95. What is dynamic method dispatch?

### Static Members
96. What is the difference between static and non-static members?

97. When would you use a static variable?

98. Can you access non-static members from a static method? Why or why not?

99. Write a class with a static counter that tracks how many instances are created.

100. What is wrong with this code?
     ```java
     public class Test {
         static int count = 0;
         public Test() {
             count++;
         }
         public static void main(String[] args) {
             Test t1 = new Test();
             Test t2 = new Test();
             System.out.println(t1.count);
         }
     }
     ```

(Continuing with 100 more questions in this category...)

---

## Exception Handling (100 questions)

### Basic Exception Handling
101. What are checked and unchecked exceptions in Java?

102. Write a try-catch block to handle division by zero.

103. What is the output?
     ```java
     try {
         int x = 5 / 0;
     } catch (ArithmeticException e) {
         System.out.println("Error: " + e.getMessage());
     }
     ```

104. How do you create a custom exception class?

105. What is the finally block used for?

### Common Exceptions
106. What causes a NullPointerException? How can you prevent it?

107. What is an ArrayIndexOutOfBoundsException and when does it occur?

108. What is the difference between throw and throws?

109. Write code that throws an IllegalArgumentException for invalid input.

110. What is a NumberFormatException and when does it occur?

### Exception Handling Best Practices
111. Why is it bad practice to catch Exception directly?

112. When should you use exception handling vs. conditional checks?

113. What is exception chaining? How is it useful?

114. How would you handle multiple exception types in a single catch block?

115. What is try-with-resources and when should you use it?

(Continuing with 85 more questions in this category...)

---

## Collections Framework (100 questions)

### Lists and ArrayLists
116. What is the difference between an array and an ArrayList?

117. How do you convert an array to an ArrayList?

118. Write code to remove all duplicates from an ArrayList.

119. What is the difference between ArrayList and LinkedList?

120. How would you sort an ArrayList of custom objects?

### Maps and HashMaps
121. What is a Map in Java? How is it different from a List?

122. How do you iterate through all key-value pairs in a HashMap?

123. Write code to count word occurrences in a string using a HashMap.

124. What is the difference between HashMap and TreeMap?

125. How would you implement a phone book using HashMap?

### Sets
126. What is a Set in Java? How is it different from a List?

127. How would you find common elements between two lists using sets?

128. What is the difference between HashSet and TreeSet?

129. Write code to remove duplicates from a list using a set.

130. When would you use a LinkedHashSet?

### Queues and Stacks
131. How would you implement a queue using ArrayList?

132. What is the difference between Queue and Stack?

133. Write code to reverse a list using a stack.

134. How does PriorityQueue differ from a regular Queue?

135. What real-world problems can be solved using stacks?

(Continuing with 65 more questions in this category...)

---

## Time Complexity and Algorithms (100 questions)

### Big-O Notation
136. What does O(1) time complexity mean? Give an example.

137. Rank these time complexities from best to worst: O(n!), O(1), O(n), O(log n), O(n²)

138. What is the time complexity of linear search? Why?

139. What is the time complexity of binary search? Why?

140. How would you determine the time complexity of nested loops?

### Searching Algorithms
141. Implement linear search and analyze its time complexity.

142. Implement binary search and explain why it requires a sorted array.

143. What is the best-case and worst-case scenario for linear search?

144. How would you modify binary search to work with descending order arrays?

145. Compare the performance of linear vs binary search for large datasets.

### Sorting Algorithms
146. Implement bubble sort and analyze its time complexity.

147. What is the advantage of merge sort over bubble sort?

148. How does quicksort work? What is its average case time complexity?

149. When would you use selection sort despite its O(n²) complexity?

150. What is a stable sorting algorithm? Give examples.

### Practical Complexity Analysis
151. Analyze the time complexity:
    ```java
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            System.out.println(i + "," + j);
        }
    }
    ```

152. What is the time complexity of this code?
    ```java
    for (int i = 1; i <= n; i *= 2) {
        System.out.println(i);
    }
    ```

153. Improve the time complexity of this code:
    ```java
    for (int i = 0; i < n; i++) {
        if (array[i] == target) {
            return true;
        }
    }
    return false;
    ```

154. What is the time complexity of accessing an element in an array vs ArrayList?

155. How does time complexity affect the choice between ArrayList and LinkedList?
