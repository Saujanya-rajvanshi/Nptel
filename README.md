# Nptel
Program in NPTEL  c programming 

Your code is well-structured and **correct**. It demonstrates the concepts of **global, local, static, and automatic variables** in C.

---

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

---

### **Explanation of Variable Scope & Lifetime:**
1. **Global Variable (`globalVar`)**:
   - Declared outside `main()`, accessible throughout the program.
   - **Retains its value across the entire execution**.

2. **Local Variable (`localVar`)**:
   - Declared inside `main()`, only accessible within `main()`.
   - **Does not exist outside `main()`**.

3. **Static Variable (`staticVar`)**:
   - Declared inside `demonstrateVariables()` with the `static` keyword.
   - **Retains its value across multiple function calls**.
   - **Increments across function calls**, as shown in the output.

4. **Automatic Variable (`autoVar`)**:
   - Declared inside `demonstrateVariables()`, but **not explicitly marked as `static`**.
   - **Reinitialized each time the function is called**, so it always prints `5`.

---

### **Key Takeaways:**
- **Global variables** persist for the entire program.
- **Local variables** exist only inside their function.
- **Static variables** retain their value between function calls.
- **Automatic variables** reset every time the function executes.

Your code is perfect for understanding these concepts. **Let me know if you need further improvements or explanations!**

---

### **C:**
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

Now the program runs correctly and outputs the expected results. Let me know if you need further modifications!
