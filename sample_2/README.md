
# Sample2 - Google Test Example

This is an example project that demonstrates how to use Google Test framework to test a simple C++ class `MyString`.

## Overview

The `MyString` class is a simple implementation for managing C-style strings (`char*`). It supports:
- Default construction (empty string).
- Construction from a C-string.
- Copy construction.
- Setting a new value with memory management.

This project includes unit tests for the `MyString` class, written using the Google Test framework.

## File Structure

```
.
├── CMakeLists.txt       # CMake configuration for building and testing
├── sample2.h            # Header file for the MyString class
├── sample2.cc           # Implementation of the MyString class
├── sample2_unittest.cc  # Unit tests for the MyString class
├── run.sh               # Script to build and run tests
```

## Features of `MyString`

1. **Default Constructor**: Initializes the object with `nullptr`.
2. **Constructor from C-String**: Clones the provided C-string.
3. **Copy Constructor**: Performs a deep copy of another `MyString` object.
4. **Set Method**: Allows setting a new string and safely manages memory.
5. **Length Method**: Returns the length of the string (or 0 if `nullptr`).

## Unit Tests

The project uses the Google Test framework to test the following:

1. **Default Constructor**:
   - The string is initialized to `nullptr`.
   - The length is `0`.

2. **Constructor from C-String**:
   - The string is correctly cloned.
   - The length matches the input string.

3. **Copy Constructor**:
   - The cloned object correctly copies the string content.

4. **Set Method**:
   - Updates the string correctly.
   - Handles cases where the new value is the same as the old value.
   - Safely handles `nullptr` input.

### Example Test Output
Run the tests with `ctest` or directly execute the test binary. Example output:
```
[==========] Running 4 tests from 1 test suite.
[----------] Global test environment set-up.
[----------] 4 tests from MyString
[ RUN      ] MyString.DefaultConstructor
[       OK ] MyString.DefaultConstructor (0 ms)
[ RUN      ] MyString.ConstructorFromCString
[       OK ] MyString.ConstructorFromCString (0 ms)
[ RUN      ] MyString.CopyConstructor
[       OK ] MyString.CopyConstructor (0 ms)
[ RUN      ] MyString.Set
[       OK ] MyString.Set (0 ms)
[----------] 4 tests from MyString (0 ms total)
[----------] Global test environment tear-down
[==========] 4 tests from 1 test suite ran. (0 ms total)
[  PASSED  ] 4 tests.
```

## How to Build and Run

### Prerequisites
- CMake 3.14 or higher.
- A C++ compiler with C++14 support.
- Google Test is automatically downloaded using `FetchContent`.

### Steps

#### Using the Script
You can use the provided `run.sh` script to automate the build and test process:
```bash
./run.sh
```

#### Manual Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/sample2.git
   cd sample2
   ```
2. Create a build directory and configure the project:
   ```bash
   mkdir build
   cd build
   cmake ..
   ```
3. Build the project:
   ```bash
   cmake --build .
   ```
4. Run the tests:
   ```bash
   ctest
   ```
   Or execute the test binary directly:
   ```bash
   ./sample2_unittest
   ```

## License

This project is licensed under the [BSD-3-Clause License](LICENSE). See the full license in the source files.

## Acknowledgments

- [Google Test](https://github.com/google/googletest) for the testing framework.
- A example from Google Test documentation.

---
