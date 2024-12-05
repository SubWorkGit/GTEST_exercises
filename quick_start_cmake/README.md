
# Quickstart Example: GoogleTest with CMake

This example demonstrates the integration of GoogleTest with CMake, based on the [GoogleTest Quickstart Guide](https://google.github.io/googletest/quickstart-cmake.html).

---

## Directory Structure

```
quickstart/
├── CMakeLists.txt   # CMake configuration file
├── hello_test.cc    # Test code
└── README.md        # Documentation for this exercise
```

---

## Test Code Overview

**`hello_test.cc`** contains the following example test:

```cpp
#include <gtest/gtest.h>

// Demonstrate some basic assertions.
TEST(HelloTest, BasicAssertions) {
    // Expect two strings not to be equal.
    EXPECT_STRNE("hello", "world");
    // Expect equality.
    EXPECT_EQ(7 * 6, 42);
}
```

### Test Details:
1. **`EXPECT_STRNE("hello", "world")`**: Verifies that the two strings are not equal.
2. **`EXPECT_EQ(7 * 6, 42)`**: Verifies that the expression `7 * 6` evaluates to `42`.

---

## How to Run This Example

### Prerequisites:
- **CMake** version 3.14 or later.
- A compatible C++ compiler that supports C++14 or later.
- GoogleTest (downloaded automatically by `FetchContent`).

### Steps:

1. **Generate build files**:
   ```bash
   cmake -S . -B build
   ```

2. **Build the test binary**:
   ```bash
   cmake --build build
   ```

3. **Run the test**:
   ```bash
   cd build && ctest
   ```

### Expected Output:
For a successful test, the output should look like this:
```
Test project .../quickstart/build
    Start 1: HelloTest.BasicAssertions
1/1 Test #1: HelloTest.BasicAssertions ........   Passed    0.00 sec

100% tests passed, 0 tests failed out of 1
```

