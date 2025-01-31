# Nptel
Program in NPTEL  c programming 

Here is your **full and correct code**:  

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

Let me know if you need modifications! 🚀

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
