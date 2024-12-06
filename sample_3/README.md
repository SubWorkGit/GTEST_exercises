# Sample 3 - Google Test Advanced Features: Test Fixture

This example is part of the **official Google Test samples**, demonstrating the use of **test fixtures** to test a C++ queue implementation.

## Overview

The `Queue` class is a simple queue implemented using a singly-linked list, supporting common operations such as:
- Enqueueing elements.
- Dequeueing elements.
- Mapping a function to the elements of the queue.

### Test Fixture

A **test fixture** is used to:
- Share common setup and teardown logic across multiple test cases.
- Maintain independent test environments to ensure test isolation and repeatability.

---

## Files

### 1. **`sample3-inl.h`**
Contains the implementation of the `Queue` class and its supporting structures:
- `QueueNode`: Represents a node in the queue.
- `Queue`: Implements the queue with methods for enqueueing, dequeueing, clearing, and mapping elements.

### 2. **`sample3_unittest.cc`**
Defines unit tests using Google Test:
- Uses `QueueTestSmpl3` as the test fixture.
- Tests the queue's functionality with `TEST_F`.

### 3. **`run.sh`**
A script to automate the build and test process for this sample.

---

## Tests

### Test Cases
The tests are organized into three main cases:

1. **Default Constructor (`DefaultConstructor`)**
   - Validates that a newly constructed queue is empty.

2. **Dequeue (`Dequeue`)**
   - Tests removing elements from both empty and non-empty queues.
   - Ensures proper memory management.

3. **Map (`Map`)**
   - Verifies the `Map` method applies a function correctly to all elements of the queue.

### Example Assertions
- `EXPECT_EQ` and `ASSERT_EQ` ensure values are as expected.
- `ASSERT_TRUE` validates non-null pointers after operations.

---

## Key Concepts

### 1. Google Test Features
- **Test Fixtures (`TEST_F`)**
  - Enable shared setup and teardown across multiple test cases.
- **Assertions**
  - Use `ASSERT_*` for critical checks that terminate the test on failure.
  - Use `EXPECT_*` for non-critical checks that allow tests to continue.

### 2. Unit Testing Best Practices
- **Test Independence**: Each test is isolated and does not depend on the state left by another.
- **Focus on Single Responsibility**: Each test validates one specific aspect of functionality.

---

## How to Build and Run

### Using the `run.sh` Script
You can execute the tests with the provided `run.sh` script:
```bash
./run.sh
```

### Manual Steps
1. Configure the project using CMake:
   ```bash
   cmake -B build -S .
   ```
2. Build the project:
   ```bash
   cmake --build build
   ```
3. Run the tests:
   ```bash
   cd build
   ctest
   ```

---

## Output Example

On successful execution, the output might look like:
```
[==========] 3 tests from 1 test suite ran. (5 ms total)
[  PASSED  ] 3 tests.
```

---

## Learning Outcomes

This sample demonstrates:
- How to use test fixtures in Google Test.
- Best practices for writing unit tests.
- Testing advanced C++ features like templates and custom memory management.

---

## Reference

This example is adapted from the **Google Test official samples**, which are designed to illustrate common use cases of the Google Test framework. For more examples, visit the [Google Test GitHub repository](https://github.com/google/googletest/tree/main/googletest/samples).
