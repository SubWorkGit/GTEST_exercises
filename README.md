
# GTEST_exercises

This repository contains a collection of exercises designed to practice and demonstrate the use of **Google Test (gtest)**, a popular C++ testing framework. Each sample focuses on different aspects of writing unit tests with Google Test, helping developers improve their testing skills and gain hands-on experience.

The samples in this repository are based on examples from the [Google Test documentation](https://google.github.io/googletest/), with additional notes and organization to showcase knowledge and usage.

## **Purpose**

The goal of this repository is to:
- Showcase knowledge and practical applications of Google Test.
- Learn the fundamentals of Google Test through structured examples.
- Provide a reference for setting up and using Google Test with CMake.
- Share organized and well-documented sample exercises.

## **Structure**

The repository is organized into sample exercises, each in its own directory:

- **`quick_start_cmake/`**: Demonstrates how to set up and run a simple test project using Google Test with CMake.
- **`sample_1/`**: Introduces basic usage of Google Test to verify simple functions.
- **`sample_2/`**: Explores testing a class with multiple member functions, showcasing more complex test scenarios.
- **`sample_3/`**: Demonstrates the use of test fixtures for setting up and tearing down shared resources in tests.

Each sample includes:
- Source code for the tests.
- A `CMakeLists.txt` file for building the project.
- A `run.sh` script for executing tests easily.
- A README file explaining the sample in detail.

## **Getting Started**

### **Prerequisites**

- A C++ compiler (e.g., GCC, Clang, or MSVC).
- [CMake](https://cmake.org/) installed on your system.
- Basic knowledge of C++ and unit testing concepts.

### **How to Run the Tests**

1. Clone this repository:
   ```bash
   git clone https://github.com/SubWorkGit/GTEST_exercises.git
   cd GTEST_exercises
   ```

2. Navigate to a sample directory, e.g., `sample_1`:
   ```bash
   cd sample_1
   ```

3. Build the project using CMake:
   ```bash
   cmake -S . -B build
   cmake --build build
   ```

4. Run the tests:
   ```bash
   ./build/sample1_test
   ```
   Alternatively, use the provided `run.sh` script:
   ```bash
   ./run.sh
   ```

## **References**

- [Google Test Documentation](https://google.github.io/googletest/)
- [Google Test GitHub Repository](https://github.com/google/googletest)
- [CMake Official Documentation](https://cmake.org/documentation/)
- [Unit Testing Basics](https://en.wikipedia.org/wiki/Unit_testing)
