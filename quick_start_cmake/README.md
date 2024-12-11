
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

## Using CMake in This Repository

This repository demonstrates how to integrate **GoogleTest** with **CMake** for unit testing in C++. Below is an overview of how CMake is used in this example:

### Key Points
1. **Project Configuration:**
   - The `CMakeLists.txt` file sets up the project and specifies the necessary configurations for GoogleTest.
   - The project uses `cmake_minimum_required` to define the CMake version and `project()` to name the project.

2. **Fetching GoogleTest:**
   - The repository uses `FetchContent` to automatically download and include GoogleTest. This avoids manually installing dependencies.

   ```cmake
   include(FetchContent)
   FetchContent_Declare(
       googletest
       URL https://github.com/google/googletest/archive/refs/tags/release-1.12.1.zip
   )
   FetchContent_MakeAvailable(googletest)
   ```

3. **Defining the Tests:**
   - The test source files are compiled into an executable using `add_executable`.
   - The `gtest` and `gtest_main` libraries are linked to the test executable to enable testing.

   ```cmake
   add_executable(sample_test sample_test.cc)
   target_link_libraries(sample_test gtest gtest_main)
   ```

### Why Use CMake?
Using CMake makes it easy to manage dependencies, configure builds across multiple platforms, and integrate testing frameworks like GoogleTest. This repository showcases a streamlined approach to leveraging CMake with GoogleTest.

---

## How to Run This Example

### Prerequisites:
- **CMake** version 3.14 or later.
- A compatible C++ compiler that supports C++14 or later.
- GoogleTest (downloaded automatically by `FetchContent`).


### Building the Project
To configure and build the project, follow these steps:

1. **Create and Configure the Build Directory**
   Use the `cmake -S . -B build` command to generate the build files. The `-S` flag specifies the source directory, and the `-B` flag specifies the build directory.
   ```bash
   cmake -S . -B build
   ```

2. **Build the Project**
   Use the `cmake --build` command to compile the source code:
   ```bash
   cmake --build build
   ```

3. **Run the Tests**
   Navigate to the build directory and execute the tests using `ctest`:
   ```bash
   cd build
   ctest
   ```
