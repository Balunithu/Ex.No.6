# EX.NO.6 – AI-ASSISTED PROGRAMMING AND DEBUGGING


**Register No.: 212223220071** 

## Aim

To write and implement programs using multiple AI tools to automate programming, debugging, optimization, complexity analysis, unit-test generation, and comparison of AI-assisted coding with manual coding.

## AI Tools Required

1. ChatGPT – Code generation, debugging, optimization and explanation.
2. Google Gemini – Alternative code generation and code review.
3. GitHub Copilot – AI-assisted coding and suggestions.

## Explanation

AI-assisted programming uses Artificial Intelligence tools to support programmers in writing, debugging, optimizing, and testing software. In this experiment, a programmer persona is used to develop a **Student Marks Analyzer** application. The application accepts student marks, calculates the total and average, and determines the grade.

The same problem is implemented using **Python, C, and Java** with the assistance of multiple AI tools. The generated programs are analyzed for correctness, readability, efficiency, and maintainability. Bugs are intentionally introduced and AI tools are used to identify and correct them. The optimized versions are then analyzed using time and space complexity.

### Problem Statement

Develop a Student Marks Analyzer that:

* Accepts marks of students.
* Calculates the total marks.
* Calculates the average.
* Determines the grade.
* Displays the result.

### Persona Pattern

**Persona:** Experienced Software Developer and Code Reviewer

**Prompt used:**

> Act as an experienced software developer. Develop a Student Marks Analyzer that accepts marks, calculates total and average, and determines the grade. Generate clean, readable, and optimized code in Python, C, and Java. Identify possible bugs, explain the time and space complexity, and generate suitable unit tests.

## 1. Python Implementation

```python
def calculate_result(marks):
    total = sum(marks)
    average = total / len(marks)

    if average >= 90:
        grade = "A"
    elif average >= 75:
        grade = "B"
    elif average >= 60:
        grade = "C"
    elif average >= 50:
        grade = "D"
    else:
        grade = "F"

    return total, average, grade


marks = [85, 78, 92, 88, 76]

total, average, grade = calculate_result(marks)

print("Total:", total)
print("Average:", average)
print("Grade:", grade)
```

### Output

```text
Total: 419
Average: 83.8
Grade: B
```

## 2. C Implementation

```c
#include <stdio.h>

int main() {
    int marks[] = {85, 78, 92, 88, 76};
    int n = 5;
    int total = 0;

    for (int i = 0; i < n; i++) {
        total += marks[i];
    }

    float average = (float)total / n;

    char grade;

    if (average >= 90)
        grade = 'A';
    else if (average >= 75)
        grade = 'B';
    else if (average >= 60)
        grade = 'C';
    else if (average >= 50)
        grade = 'D';
    else
        grade = 'F';

    printf("Total: %d\n", total);
    printf("Average: %.2f\n", average);
    printf("Grade: %c\n", grade);

    return 0;
}
```

### Output

```text
Total: 419
Average: 83.80
Grade: B
```

## 3. Java Implementation

```java
public class StudentMarksAnalyzer {

    public static void main(String[] args) {

        int[] marks = {85, 78, 92, 88, 76};
        int total = 0;

        for (int mark : marks) {
            total += mark;
        }

        double average = (double) total / marks.length;

        String grade;

        if (average >= 90)
            grade = "A";
        else if (average >= 75)
            grade = "B";
        else if (average >= 60)
            grade = "C";
        else if (average >= 50)
            grade = "D";
        else
            grade = "F";

        System.out.println("Total: " + total);
        System.out.println("Average: " + average);
        System.out.println("Grade: " + grade);
    }
}
```

### Output

```text
Total: 419
Average: 83.8
Grade: B
```

## Bug Identification and Debugging

AI tools were used to identify common programming errors.

### Buggy Code

```python
marks = []

total = sum(marks)
average = total / len(marks)

print(average)
```

### Identified Bug

The program produces a **ZeroDivisionError** because the list is empty and `len(marks)` is zero.

### Corrected Code

```python
marks = []

if len(marks) == 0:
    print("No marks available")
else:
    total = sum(marks)
    average = total / len(marks)
    print(average)
```

### Other Bugs Identified

| Bug                       | Description                                  | Solution                    |
| ------------------------- | -------------------------------------------- | --------------------------- |
| Empty input               | Division by zero                             | Check input length          |
| Invalid marks             | Marks may be below 0 or above 100            | Validate the range          |
| Integer division          | Average may lose precision in some languages | Use floating-point division |
| Incorrect grade condition | Wrong grade may be assigned                  | Check conditions carefully  |
| Invalid data type         | Non-numeric input may cause errors           | Validate input              |

## Code Optimization

The optimized implementation uses a single loop to calculate the total and then calculates the average once.

For `n` marks:

**Time Complexity:** O(n)

**Space Complexity:** O(n) for storing the marks.

The grade calculation requires a fixed number of comparisons, so it is **O(1)**.

## Unit Tests

Example unit tests for the Python implementation:

```python
def test_result():
    assert calculate_result([90, 90, 90]) == (270, 90.0, "A")
    assert calculate_result([75, 75, 75]) == (225, 75.0, "B")
    assert calculate_result([60, 60, 60]) == (180, 60.0, "C")
    assert calculate_result([50, 50, 50]) == (150, 50.0, "D")
    assert calculate_result([40, 40, 40]) == (120, 40.0, "F")
```

### Test Case Table

| Test Case | Input      | Expected Grade | Result |
| --------- | ---------- | -------------- | ------ |
| 1         | 90, 90, 90 | A              | Pass   |
| 2         | 75, 75, 75 | B              | Pass   |
| 3         | 60, 60, 60 | C              | Pass   |
| 4         | 50, 50, 50 | D              | Pass   |
| 5         | 40, 40, 40 | F              | Pass   |

## Comparison of Manual Coding and AI-Assisted Coding

| Feature           | Manual Coding                     | AI-Assisted Coding                     |
| ----------------- | --------------------------------- | -------------------------------------- |
| Code generation   | Written manually                  | Generated with AI assistance           |
| Development speed | Comparatively slower              | Faster                                 |
| Debugging         | Requires manual analysis          | AI can identify possible bugs          |
| Optimization      | Developer dependent               | AI suggests improvements               |
| Unit tests        | Written manually                  | Can be generated automatically         |
| Explanation       | Developer prepares explanation    | AI can explain code                    |
| Accuracy          | Depends on programmer             | Requires human verification            |
| Learning          | Improves programming fundamentals | Helps understand alternative solutions |

## Code Quality Analysis

The AI-generated programs were analyzed based on correctness, readability, efficiency, maintainability, and testing.

* **Correctness:** The generated programs produced the expected output.
* **Readability:** Meaningful variable names and simple control structures were used.
* **Efficiency:** The algorithms have O(n) time complexity.
* **Maintainability:** Functions and modular structures make the code easier to modify.
* **Testing:** AI tools can generate multiple test cases quickly.
* **Debugging:** AI tools can identify common syntax, logical, and runtime errors.
* **Human Verification:** AI-generated code must always be reviewed and tested by the programmer.

## Conclusion

Thus, the Student Marks Analyzer was successfully developed using Python, C, and Java with the assistance of multiple AI tools. The AI tools helped in code generation, bug identification, optimization, complexity analysis, and unit-test generation. The comparison showed that AI-assisted programming can significantly reduce development time and improve productivity, while manual review and testing are still necessary to ensure correctness, security, and code quality.

## Result

The corresponding prompt was executed successfully, and the programs were generated, debugged, optimized, tested, and analyzed using multiple AI-assisted programming tools.
