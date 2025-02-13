# Nptel
Program in NPTEL  c programming 

 **c variable**:  

```c
#include <stdio.h>

// Global variable
int globalVar = 100;

// Function to demonstrate the use of static and automatic variables
void demonstrateVariables() {
    // Static variable (retains its value between function calls)
    static int staticVar = 10;
    
    // Automatic variable (lifetime limited to function scope)
    int autoVar = 5;

    printf("Inside demonstrateVariables function:\n");
    printf("Static Variable: %d\n", staticVar);
    printf("Automatic Variable: %d\n", autoVar);

    // Modify the variables
    staticVar++;
    autoVar++;
}

int main() {
    // Local variable (defined inside main function)
    int localVar = 20;

    printf("In main function:\n");
    printf("Global Variable: %d\n", globalVar);
    printf("Local Variable: %d\n", localVar);

    printf("\nCalling demonstrateVariables for the first time:\n");
    demonstrateVariables();

    printf("\nCalling demonstrateVariables for the second time:\n");
    demonstrateVariables();

    return 0;
}
```

### **Expected Output:**
```
In main function:
Global Variable: 100
Local Variable: 20

Calling demonstrateVariables for the first time:
Inside demonstrateVariables function:
Static Variable: 10
Automatic Variable: 5

Calling demonstrateVariables for the second time:
Inside demonstrateVariables function:
Static Variable: 11
Automatic Variable: 5
```

This code **correctly demonstrates**:
✔ **Global variables** (retain values across the whole program).  
✔ **Local variables** (exist only within their function).  
✔ **Static variables** (retain values between function calls).  
✔ **Automatic variables** (reinitialize every function call).  

---

### **C datatype:**
```c
#include <stdio.h>

int main() {
    // Integer data type
    int intVar = 10;

    // Floating-point data type
    float floatVar = 20.5f;

    // Double-precision floating-point data type
    double doubleVar = 30.123456;

    // Character data type
    char charVar = 'A';

    // String (character array)
    char stringVar[] = "Hello, C!";

    // Print the values and sizes of the variables
    printf("Integer:\n");
    printf(" Value: %d\n", intVar);
    printf(" Size: %lu bytes\n\n", sizeof(intVar));

    printf("Floating-point:\n");
    printf(" Value: %f\n", floatVar);
    printf(" Size: %lu bytes\n\n", sizeof(floatVar));

    printf("Double-precision Floating-point:\n");
    printf(" Value: %lf\n", doubleVar);
    printf(" Size: %lu bytes\n\n", sizeof(doubleVar));

    printf("Character:\n");
    printf(" Value: %c\n", charVar);
    printf(" Size: %lu bytes\n\n", sizeof(charVar));

    printf("String:\n");
    printf(" Value: %s\n", stringVar);
    printf(" Size: %lu bytes\n\n", sizeof(stringVar));

    return 0;
}
```

---

### **Expected Output:**
```
Integer:
 Value: 10
 Size: 4 bytes

Floating-point:
 Value: 20.500000
 Size: 4 bytes

Double-precision Floating-point:
 Value: 30.123456
 Size: 8 bytes

Character:
 Value: A
 Size: 1 byte

String:
 Value: Hello, C!
 Size: 10 bytes
```

### **Explanation:**
- **`sizeof(intVar)`** → Usually **4 bytes** (depends on system).
- **`sizeof(floatVar)`** → Usually **4 bytes**.
- **`sizeof(doubleVar)`** → Usually **8 bytes**.
- **`sizeof(charVar)`** → **1 byte** (as expected).
- **`sizeof(stringVar)`** → **Includes the null terminator (`\0`)**, making it **length + 1**.

---

### **C signed and unsigned variable:**
```c
#include <stdio.h>

int main() {
    // Declare signed and unsigned integers
    signed int signedVar = -100;  // Signed integer can hold negative values
    unsigned int unsignedVar = 100; // Unsigned integer can only hold non-negative values

    // Display the values of the signed and unsigned integers
    printf("Signed Integer: \n");
    printf(" Value: %d\n", signedVar);

    printf("Unsigned Integer: \n");
    printf(" Value: %u\n", unsignedVar);

    // Assigning a negative value to an unsigned integer
    unsigned int invalidUnsigned = -1;

    printf("Unsigned Integer with a negative assignment (-1):\n");
    printf(" Value: %u\n", invalidUnsigned); // Typically prints 4,294,967,295 on a 32-bit system

    return 0;
}
```

---

### **Expected Output (on a 32-bit system):**
```
Signed Integer: 
 Value:-100

Unsigned Integer: 
 Value: 100

Unsigned Integer with a negative assignment (-1):
 Value: 4294967295
```

### **Explanation:**
- **`signedVar = 100;`** → Holds positive and negative values.
- **`unsignedVar = 100;`** → Cannot hold negative values.
- **`invalidUnsigned = -1;`**  
  - Since `unsigned int` **cannot store negative values**, `-1` is stored as **the maximum possible unsigned integer**.
  - On a **32-bit system**, this results in **4,294,967,295 (2³² - 1)**.

Your corrected code now runs without errors and correctly demonstrates signed vs. unsigned integers. 🚀

Your code contains **syntax errors and incorrect assignment operations**. Below is a **corrected version** with explanations:

---

### **Key Fixes:**
1. **Fixed `printf()` Formatting Errors:**
   - `"Enter two integers (a and b): "` should be on a new line for clarity.
   - Closing quotes (`"`) were missing at the end of some `printf()` statements.

2. **Fixed `+=`, `-=`, and `*=` Operations:**
   - **`+= b;`** was incorrect (it should be `c += b;`).
   - **`c = b;`** was incorrectly placed (should use `c -= b;` and `c *= b;`).

3. **Ensured Proper Code Execution Order:**
   - **Each assignment modifies `c`, so it should be done sequentially.**

---

### **C operator:**
```c
#include <stdio.h>

int main() {
    int a, b, c;

    // Input two integers from the user
    printf("Enter two integers (a and b): ");
    scanf("%d %d", &a, &b);

    // Displaying assignment operations
    printf("\nAssignment Operations Results:\n");

    // Simple assignment
    c = a;
    printf("c = a: c = %d\n", c);

    // Add the value of b to c and assign the result to c
    c += b; // Equivalent to c = c + b
    printf("c += b: c = %d\n", c);

    // Subtract the value of b from c and assign the result to c
    c -= b; // Equivalent to c = c - b
    printf("c -= b: c = %d\n", c);

    // Multiply c by b and assign the result to c
    c *= b; // Equivalent to c = c * b
    printf("c *= b: c = %d\n", c);

    return 0;
}
```

---

### **Expected Output (Example Run):**
```
Enter two integers (a and b): 5 3

Assignment Operations Results:
c = a: c = 5
c += b: c = 8
c -= b: c = 5
c *= b: c = 15
```

---

### **Explanation of Assignment Operators:**
1. **`c = a;`** → Assigns `a` to `c`.  
2. **`c += b;`** → `c = c + b` (adds `b` to `c`).  
3. **`c -= b;`** → `c = c - b` (subtracts `b` from `c`).  
4. **`c *= b;`** → `c = c * b` (multiplies `c` by `b`).  

Your code is **almost correct**, but there's a small issue with the format specifier. `%s` is used for strings, but `"true"` and `"false"` are string literals. This works in modern compilers but is not strictly type-safe in standard C.  

---

### **Key Fixes:**
1. **Using `"true"` and `"false"` safely**:
   - Instead of `%s`, we can use **`printf()` directly** with `"true"` and `"false"`.  
   - Alternatively, we can use **`const char*`** variables for better readability.

---

### **Corrected Code:**
```c
#include <stdio.h>

int main() {
    int a, b;

    // Input two integers
    printf("Enter two integers (a and b): ");
    scanf("%d %d", &a, &b);

    // Logical operations
    printf("\nLogical Operations Results:\n");

    // Using ternary operator to print true/false
    printf("(a > 0) && (b > 0): %s\n", (a > 0 && b > 0) ? "true" : "false");
    printf("(a > 0) || (b > 0): %s\n", (a > 0 || b > 0) ? "true" : "false");
    printf("!(a > 0): %s\n", (!(a > 0)) ? "true" : "false");

    return 0;
}
```

---

### **Alternative Using `const char*`:**
```c
#include <stdio.h>

int main() {
    int a, b;
    
    // Input two integers
    printf("Enter two integers (a and b): ");
    scanf("%d %d", &a, &b);

    // Define true/false strings
    const char *trueStr = "true";
    const char *falseStr = "false";

    // Logical operations
    printf("\nLogical Operations Results:\n");
    printf("(a > 0) && (b > 0): %s\n", (a > 0 && b > 0) ? trueStr : falseStr);
    printf("(a > 0) || (b > 0): %s\n", (a > 0 || b > 0) ? trueStr : falseStr);
    printf("!(a > 0): %s\n", (!(a > 0)) ? trueStr : falseStr);

    return 0;
}
```

---

### **Expected Output (Example Runs):**
#### **Case 1: a = 5, b = 3**
```
Enter two integers (a and b): 5 3

Logical Operations Results:
(a > 0) && (b > 0): true
(a > 0) || (b > 0): true
!(a > 0): false
```

#### **Case 2: a = -2, b = 0**
```
Enter two integers (a and b): -2 0

Logical Operations Results:
(a > 0) && (b > 0): false
(a > 0) || (b > 0): false
!(a > 0): true
```

---

### **Explanation:**
1. **Logical AND (`&&`)** → `true` only if **both** conditions are `true`.
2. **Logical OR (`||`)** → `true` if **at least one** condition is `true`.
3. **Logical NOT (`!`)** → **Reverses** the condition.

Your code contains **syntax errors**, mainly in arithmetic operations and missing operators. Below is the **corrected and complete version**:

---

### **Key Fixes:**
1. **Fixed Arithmetic Operators:**
   - `difference = num1 num2;` → should be `difference = num1 - num2;`
   - `product num1 num2;` → should be `product = num1 * num2;`
   - `remainder = num1% num2;` → should be `remainder = num1 % num2;`

2. **Ensured Proper `printf()` Formatting:**
   - `printf("%d %d = %d\n", num1, num2, difference);` → Fixed to include `-`
   - `printf("%d %d = %d\n", num1, num2, product);` → Fixed to include `*`
   - `printf("%d / %d = %.2f\n", num1, num2, quotient);` → Ensured floating-point output.
   - `printf("%d %% %d = %d\n", num1, num2, remainder);` → Used `%%` to print `%`.

---

### **Corrected Code:**
```c
#include <stdio.h>

int main() {
    int num1, num2;
    int sum, difference, product, remainder;
    float quotient;

    // Input two integers
    printf("Enter two integers: ");
    scanf("%d %d", &num1, &num2);

    // Perform arithmetic operations
    sum = num1 + num2;
    difference = num1 - num2;
    product = num1 * num2;
    quotient = (float) num1 / num2; // Typecasting for accurate division
    remainder = num1 % num2;

    // Output results
    printf("\nResults:\n");
    printf("%d + %d = %d\n", num1, num2, sum);
    printf("%d - %d = %d\n", num1, num2, difference);
    printf("%d * %d = %d\n", num1, num2, product);
    printf("%d / %d = %.2f\n", num1, num2, quotient);
    printf("%d %% %d = %d\n", num1, num2, remainder);

    return 0;
}
```
**function in c**:  
---

### **Expected Output (Example Run):**
```
Enter two integers: 10 3

Results:
10 + 3 = 13
10 - 3 = 7
10 * 3 = 30
10 / 3 = 3.33
10 % 3 = 1
```

