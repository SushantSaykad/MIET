# C Programming Practical Programs (19 Programs)

This repository contains 19 beginner-friendly C programs covering basic data types, operators, control statements, functions, recursion, arrays, matrices, pointers, structures, and file handling.

## Table of Contents

1. [Data Types and Sizes](#1-data-types-and-sizes)
2. [Arithmetic, Relational, and Logical Operators](#2-arithmetic-relational-and-logical-operators)
3. [Conditional Expression and Order of Evaluation](#3-conditional-expression-and-order-of-evaluation)
4. [Bitwise Operators](#4-bitwise-operators)
5. [Assignment Operators](#5-assignment-operators)
6. [Control Flow Statements](#6-control-flow-statements)
7. [Factorial Using a Function](#7-factorial-using-a-function)
8. [Sum of Digits Using Recursion](#8-sum-of-digits-using-recursion)
9. [Menu-Driven Arithmetic Calculator](#9-menu-driven-arithmetic-calculator)
10. [Fibonacci Series](#10-fibonacci-series)
11. [One-Dimensional Array](#11-one-dimensional-array)
12. [Largest and Smallest Array Elements](#12-largest-and-smallest-array-elements)
13. [Transpose of a Matrix](#13-transpose-of-a-matrix)
14. [Access Array Elements Using Pointers](#14-access-array-elements-using-pointers)
15. [Swap Two Numbers Using Pointers](#15-swap-two-numbers-using-pointers)
16. [Student Record Using a Structure](#16-student-record-using-a-structure)
17. [Search and Sort Student Records](#17-search-and-sort-student-records)
18. [Read, Calculate, and Write File Data](#18-read-calculate-and-write-file-data)
19. [Copy One File to Another](#19-copy-one-file-to-another)

---

## 1. Data Types and Sizes

**Aim:** Declare and initialize variables of different data types and display their sizes using `sizeof`.

**File:** `01_data_types.c`

```c
#include <stdio.h>

int main(void) {
    int age = 18;
    char grade = 'A';
    float percentage = 85.5f;
    double distance = 12345.678;
    long int population = 100000L;

    printf("Integer: %d, Size: %zu bytes\n", age, sizeof(age));
    printf("Character: %c, Size: %zu bytes\n", grade, sizeof(grade));
    printf("Float: %.2f, Size: %zu bytes\n", percentage, sizeof(percentage));
    printf("Double: %.3f, Size: %zu bytes\n", distance, sizeof(distance));
    printf("Long integer: %ld, Size: %zu bytes\n", population, sizeof(population));

    return 0;
}
```

**Note:** Sizes depend on the compiler and system.

## 2. Arithmetic, Relational, and Logical Operators

**Aim:** Perform arithmetic, relational, and logical operations.

**File:** `02_operators.c`

```c
#include <stdio.h>

int main(void) {
    int a = 10, b = 3;

    printf("Arithmetic:\n");
    printf("a + b = %d\n", a + b);
    printf("a - b = %d\n", a - b);
    printf("a * b = %d\n", a * b);
    printf("a / b = %d\n", a / b);
    printf("a %% b = %d\n", a % b);

    printf("\nRelational:\n");
    printf("a > b = %d\n", a > b);
    printf("a == b = %d\n", a == b);
    printf("a != b = %d\n", a != b);

    printf("\nLogical:\n");
    printf("(a > 5 && b < 5) = %d\n", a > 5 && b < 5);
    printf("(a < 5 || b < 5) = %d\n", a < 5 || b < 5);
    printf("!(a == b) = %d\n", !(a == b));

    return 0;
}
```

**Note:** In C, relational and logical expressions return `1` for true and `0` for false. Integer division `10 / 3` gives `3`.

## 3. Conditional Expression and Order of Evaluation

**Aim:** Demonstrate the conditional (`?:`) operator and operator precedence.

**File:** `03_conditional_expression.c`

```c
#include <stdio.h>

int main(void) {
    int a = 12, b = 20;
    int largest = (a > b) ? a : b;
    int result = 2 + 3 * 4;

    printf("Largest number = %d\n", largest);
    printf("2 + 3 * 4 = %d\n", result);

    return 0;
}
```

**Explanation:** The conditional operator checks the condition before `?`. If true, it selects the expression before `:`; otherwise, it selects the expression after `:`. In `2 + 3 * 4`, multiplication has higher precedence than addition, so the result is `14`. Precedence determines grouping; it does not mean every operand is evaluated in a fixed left-to-right order.

## 4. Bitwise Operators

**Aim:** Perform bitwise AND, OR, XOR, NOT, left shift, and right shift.

**File:** `04_bitwise_operators.c`

```c
#include <stdio.h>

int main(void) {
    unsigned int a = 5, b = 3;

    printf("a = %u, b = %u\n", a, b);
    printf("a & b = %u\n", a & b);
    printf("a | b = %u\n", a | b);
    printf("a ^ b = %u\n", a ^ b);
    printf("~a = %u\n", ~a);
    printf("a << 1 = %u\n", a << 1);
    printf("a >> 1 = %u\n", a >> 1);

    return 0;
}
```

**Note:** Bitwise operators work on the binary representation of integers. The value printed by `~a` depends on the width of `unsigned int`.

## 5. Assignment Operators

**Aim:** Demonstrate simple and compound assignment operators.

**File:** `05_assignment_operators.c`

```c
#include <stdio.h>

int main(void) {
    int a = 10;

    printf("Initial a = %d\n", a);

    a += 5;
    printf("After a += 5: %d\n", a);

    a -= 3;
    printf("After a -= 3: %d\n", a);

    a *= 2;
    printf("After a *= 2: %d\n", a);

    a /= 4;
    printf("After a /= 4: %d\n", a);

    a %= 4;
    printf("After a %%= 4: %d\n", a);

    return 0;
}
```

## 6. Control Flow Statements

**Aim:** Demonstrate `if-else`, `switch`, and loops.

**File:** `06_control_flow.c`

```c
#include <stdio.h>

int main(void) {
    int number, i;

    printf("Enter an integer: ");
    if (scanf("%d", &number) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    if (number > 0)
        printf("The number is positive.\n");
    else if (number < 0)
        printf("The number is negative.\n");
    else
        printf("The number is zero.\n");

    switch (number % 2 == 0) {
        case 1:
            printf("The number is even.\n");
            break;
        case 0:
            printf("The number is odd.\n");
            break;
    }

    printf("Numbers from 1 to 5:\n");
    for (i = 1; i <= 5; i++)
        printf("%d ", i);

    printf("\n");

    return 0;
}
```

## 7. Factorial Using a Function

**Aim:** Calculate the factorial of a non-negative integer using a function.

**File:** `07_factorial_function.c`

```c
#include <stdio.h>

unsigned long long factorial(int n) {
    unsigned long long result = 1;
    int i;

    for (i = 1; i <= n; i++)
        result *= (unsigned long long)i;

    return result;
}

int main(void) {
    int n;

    printf("Enter a non-negative integer (0 to 20): ");
    if (scanf("%d", &n) != 1 || n < 0 || n > 20) {
        printf("Invalid input. Enter a number from 0 to 20.\n");
        return 1;
    }

    printf("Factorial of %d = %llu\n", n, factorial(n));
    return 0;
}
```

**Note:** This program limits input to `0` through `20` to avoid overflow for the chosen return type.

## 8. Sum of Digits Using Recursion

**Aim:** Find the sum of digits of a non-negative integer using recursion.

**File:** `08_sum_digits_recursion.c`

```c
#include <stdio.h>

int sumDigits(unsigned int n) {
    if (n == 0)
        return 0;

    return (int)(n % 10) + sumDigits(n / 10);
}

int main(void) {
    unsigned int n;

    printf("Enter a non-negative integer: ");
    if (scanf("%u", &n) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    printf("Sum of digits = %d\n", sumDigits(n));
    return 0;
}
```

## 9. Menu-Driven Arithmetic Calculator

**Aim:** Use `switch-case` to perform arithmetic operations selected by the user.

**File:** `09_menu_calculator.c`

```c
#include <stdio.h>

int main(void) {
    double a, b;
    char op;

    printf("Enter an operation (+, -, *, /): ");
    if (scanf(" %c", &op) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    printf("Enter two numbers: ");
    if (scanf("%lf %lf", &a, &b) != 2) {
        printf("Invalid numbers.\n");
        return 1;
    }

    switch (op) {
        case '+':
            printf("Result = %.2f\n", a + b);
            break;
        case '-':
            printf("Result = %.2f\n", a - b);
            break;
        case '*':
            printf("Result = %.2f\n", a * b);
            break;
        case '/':
            if (b == 0.0)
                printf("Error: division by zero is not allowed.\n");
            else
                printf("Result = %.2f\n", a / b);
            break;
        default:
            printf("Invalid operator.\n");
    }

    return 0;
}
```

## 10. Fibonacci Series

**Aim:** Print the first `n` terms of the Fibonacci series using a loop.

**File:** `10_fibonacci.c`

```c
#include <stdio.h>

int main(void) {
    int n, i;
    unsigned long long first = 0, second = 1, next;

    printf("Enter number of terms (1 to 94): ");
    if (scanf("%d", &n) != 1 || n < 1 || n > 94) {
        printf("Invalid input. Enter a number from 1 to 94.\n");
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("%llu ", first);

        if (i < n - 1) {
            next = first + second;
            first = second;
            second = next;
        }
    }

    printf("\n");
    return 0;
}
```

## 11. One-Dimensional Array

**Aim:** Initialize and display the elements of a one-dimensional array.

**File:** `11_one_dimensional_array.c`

```c
#include <stdio.h>

int main(void) {
    int numbers[] = {10, 20, 30, 40, 50};
    int i;
    int size = (int)(sizeof(numbers) / sizeof(numbers[0]));

    printf("Array elements:\n");
    for (i = 0; i < size; i++)
        printf("numbers[%d] = %d\n", i, numbers[i]);

    return 0;
}
```

## 12. Largest and Smallest Array Elements

**Aim:** Find the largest and smallest values in an array.

**File:** `12_largest_smallest_array.c`

```c
#include <stdio.h>

int main(void) {
    int numbers[] = {25, 10, 48, 7, 32};
    int size = (int)(sizeof(numbers) / sizeof(numbers[0]));
    int largest = numbers[0], smallest = numbers[0];
    int i;

    for (i = 1; i < size; i++) {
        if (numbers[i] > largest)
            largest = numbers[i];

        if (numbers[i] < smallest)
            smallest = numbers[i];
    }

    printf("Largest element = %d\n", largest);
    printf("Smallest element = %d\n", smallest);

    return 0;
}
```

## 13. Transpose of a Matrix

**Aim:** Find and display the transpose of a matrix using a two-dimensional array.

**File:** `13_matrix_transpose.c`

```c
#include <stdio.h>

int main(void) {
    int matrix[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    };
    int transpose[3][2];
    int i, j;

    for (i = 0; i < 2; i++) {
        for (j = 0; j < 3; j++)
            transpose[j][i] = matrix[i][j];
    }

    printf("Original matrix:\n");
    for (i = 0; i < 2; i++) {
        for (j = 0; j < 3; j++)
            printf("%d ", matrix[i][j]);
        printf("\n");
    }

    printf("Transpose:\n");
    for (i = 0; i < 3; i++) {
        for (j = 0; j < 2; j++)
            printf("%d ", transpose[i][j]);
        printf("\n");
    }

    return 0;
}
```

## 14. Access Array Elements Using Pointers

**Aim:** Access array elements using pointer arithmetic.

**File:** `14_array_pointers.c`

```c
#include <stdio.h>

int main(void) {
    int numbers[] = {10, 20, 30, 40, 50};
    int *ptr = numbers;
    int i;
    int size = (int)(sizeof(numbers) / sizeof(numbers[0]));

    for (i = 0; i < size; i++)
        printf("Element %d = %d\n", i, *(ptr + i));

    return 0;
}
```

## 15. Swap Two Numbers Using Pointers

**Aim:** Swap two integers by passing their addresses to a function.

**File:** `15_swap_pointers.c`

```c
#include <stdio.h>

void swap(int *x, int *y) {
    int temp = *x;
    *x = *y;
    *y = temp;
}

int main(void) {
    int a = 10, b = 20;

    printf("Before swap: a = %d, b = %d\n", a, b);
    swap(&a, &b);
    printf("After swap:  a = %d, b = %d\n", a, b);

    return 0;
}
```

## 16. Student Record Using a Structure

**Aim:** Store and display a student's name, roll number, and marks using a structure.

**File:** `16_student_structure.c`

```c
#include <stdio.h>

struct Student {
    char name[50];
    int rollNumber;
    float marks;
};

int main(void) {
    struct Student student = {"Amit", 101, 87.5f};

    printf("Student Details\n");
    printf("Name: %s\n", student.name);
    printf("Roll Number: %d\n", student.rollNumber);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}
```

## 17. Search and Sort Student Records

**Aim:** Store multiple student records, sort them by roll number, and search for a roll number.

**File:** `17_student_search_sort.c`

```c
#include <stdio.h>

#define MAX_STUDENTS 5

struct Student {
    char name[50];
    int rollNumber;
    float marks;
};

int main(void) {
    struct Student students[MAX_STUDENTS], temp;
    int i, j, searchRoll, found = 0;

    for (i = 0; i < MAX_STUDENTS; i++) {
        printf("Enter name, roll number, and marks for student %d: ", i + 1);
        if (scanf("%49s %d %f", students[i].name,
                  &students[i].rollNumber, &students[i].marks) != 3) {
            printf("Invalid input.\n");
            return 1;
        }
    }

    /* Sort students by roll number using bubble sort. */
    for (i = 0; i < MAX_STUDENTS - 1; i++) {
        for (j = 0; j < MAX_STUDENTS - 1 - i; j++) {
            if (students[j].rollNumber > students[j + 1].rollNumber) {
                temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            }
        }
    }

    printf("\nStudents sorted by roll number:\n");
    for (i = 0; i < MAX_STUDENTS; i++) {
        printf("Roll: %d, Name: %s, Marks: %.2f\n",
               students[i].rollNumber, students[i].name, students[i].marks);
    }

    printf("\nEnter roll number to search: ");
    if (scanf("%d", &searchRoll) != 1) {
        printf("Invalid input.\n");
        return 1;
    }

    for (i = 0; i < MAX_STUDENTS; i++) {
        if (students[i].rollNumber == searchRoll) {
            printf("Student found: %s, Marks: %.2f\n",
                   students[i].name, students[i].marks);
            found = 1;
            break;
        }
    }

    if (!found)
        printf("Student with roll number %d not found.\n", searchRoll);

    return 0;
}
```

**Note:** This example reads one-word names. To support full names with spaces, use `fgets()` for name input.

## 18. Read, Calculate, and Write File Data

**Aim:** Read integers from `input.txt`, calculate their sum, and write the result to `output.txt`.

**File:** `18_file_calculation.c`

```c
#include <stdio.h>

int main(void) {
    FILE *input, *output;
    int number;
    long long sum = 0;
    int count = 0;

    input = fopen("input.txt", "r");
    if (input == NULL) {
        printf("Could not open input.txt. Create it with integer values first.\n");
        return 1;
    }

    while (fscanf(input, "%d", &number) == 1) {
        sum += number;
        count++;
    }

    if (ferror(input)) {
        printf("Error while reading input.txt.\n");
        fclose(input);
        return 1;
    }
    fclose(input);

    output = fopen("output.txt", "w");
    if (output == NULL) {
        printf("Could not open output.txt for writing.\n");
        return 1;
    }

    fprintf(output, "Count = %d\nSum = %lld\n", count, sum);
    fclose(output);

    printf("Calculation complete. Check output.txt.\n");
    return 0;
}
```

**Sample `input.txt`:**
```text
10 20 30 40
```

**Expected `output.txt`:**
```text
Count = 4
Sum = 100
```

## 19. Copy One File to Another

**Aim:** Copy the contents of a text file into another file using file handling.

**File:** `19_copy_file.c`

```c
#include <stdio.h>

int main(void) {
    FILE *source, *destination;
    int ch;

    source = fopen("source.txt", "r");
    if (source == NULL) {
        printf("Could not open source.txt. Create the file first.\n");
        return 1;
    }

    destination = fopen("destination.txt", "w");
    if (destination == NULL) {
        printf("Could not open destination.txt for writing.\n");
        fclose(source);
        return 1;
    }

    while ((ch = fgetc(source)) != EOF) {
        if (fputc(ch, destination) == EOF) {
            printf("Error while writing to destination.txt.\n");
            fclose(source);
            fclose(destination);
            return 1;
        }
    }

    if (ferror(source)) {
        printf("Error while reading source.txt.\n");
        fclose(source);
        fclose(destination);
        return 1;
    }

    fclose(source);
    fclose(destination);

    printf("File copied successfully to destination.txt.\n");
    return 0;
}
```

---

## How to Compile and Run

You need a C compiler such as GCC.

Compile a program:

```bash
gcc 01_data_types.c -o 01_data_types
```

Run on Windows Command Prompt:

```bash
01_data_types.exe
```

Run on Linux/macOS:

```bash
./01_data_types
```

Replace the filename with the program you want to run. For example, compile `07_factorial_function.c` using:

```bash
gcc 07_factorial_function.c -o factorial
```

### File Handling Setup

- For Program 18, create `input.txt` in the program's working directory and add integer values separated by spaces or new lines.
- For Program 19, create `source.txt` in the program's working directory and add the text you want to copy.
- The programs create `output.txt` and `destination.txt`, respectively.

## Topics Covered

- Variables and data types
- Arithmetic, relational, logical, bitwise, and assignment operators
- Conditional operator and operator precedence
- `if-else`, `switch-case`, and loops
- Functions and recursion
- Fibonacci series and factorial
- One-dimensional and two-dimensional arrays
- Pointers and pointer-based swapping
- Structures, searching, and sorting
- File input/output and file copying

## Author

Add your name and GitHub profile here.
