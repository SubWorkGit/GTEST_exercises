
# Sample 1: GoogleTest Example

This example demonstrates basic usage of GoogleTest for writing unit tests in C++.

---

## Directory Structure

```
sample_1/
├── CMakeLists.txt         # CMake configuration file
├── sample1.h              # Header file with function declarations
├── sample1.cc             # Source file with function implementations
├── sample1_unittest.cc    # Unit test file
├── run.sh                 # Script to build and run the tests
└── README.md              # Documentation for this exercise
```

---

## Test Code Overview

### **Source Code**
- **`sample1.h`**: Contains declarations of the `Factorial` and `IsPrime` functions.
- **`sample1.cc`**: Provides implementations for the functions declared in `sample1.h`.

### **Test Code**
- **`sample1_unittest.cc`**: Contains unit tests for the `Factorial` and `IsPrime` functions using GoogleTest.

Sample test case:
```cpp
#include <gtest/gtest.h>
#include "sample1.h"

// Tests the Factorial function.
TEST(FactorialTest, HandlesZeroInput) {
    EXPECT_EQ(Factorial(0), 1);
}

// Tests the IsPrime function.
TEST(IsPrimeTest, HandlesPositiveInput) {
    EXPECT_TRUE(IsPrime(2));
    EXPECT_FALSE(IsPrime(4));
}
```

---

## How to Build and Run

### **Using the `run.sh` Script**
To simplify the process, you can use the provided `run.sh` script. It handles building and running the tests automatically.

1. Ensure the script is executable:
   ```bash
   chmod +x run.sh
   ```
2. Run the script:
   ```bash
   ./run.sh
   ```

### **Manual Steps**
If you prefer manual steps, follow these commands:

1. Generate build files:
   ```bash
   cmake -S . -B build
   ```
2. Build the project:
   ```bash
   cmake --build build
   ```
3. Run the tests:
   ```bash
   cd build && ctest
   ```

---

## Purpose of This Exercise

This example serves as a starting point to understand:
- How to organize code and tests with GoogleTest.
- Writing and running basic test cases for C++ functions.
- Using CMake to manage dependencies and build processes.

---

## Next Steps

Feel free to:
- Modify the functions in `sample1.cc` and add more test cases in `sample1_unittest.cc`.
- Explore advanced GoogleTest features like parameterized tests, mocking, and custom assertions.

For more details, refer to the [GoogleTest Documentation](https://google.github.io/googletest/).
