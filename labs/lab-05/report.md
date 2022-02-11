# Lab 05 - Build Systems

## CMake tutorial - steps 1 through 5

### Step 1

`tutorial.cxx`
```
// A simple program that computes the square root of a number
#include <cmath>
#include <iostream>
#include <string>
#include "TutorialConfig.h"

int main(int argc, char* argv[])
{
  if (argc < 2) {
    std::cout << argv[0] << " Version " << Tutorial_VERSION_MAJOR << "."
	                  << Tutorial_VERSION_MINOR << std::endl;
    std::cout << "Usage: " << argv[0] << " number" << std::endl;
    return 1;
  }

  // convert input to double
  const double inputValue = std::stod(argv[1]);

  // calculate square root
  const double outputValue = sqrt(inputValue);
  std::cout << "The square root of " << inputValue << " is " << outputValue
            << std::endl;
  return 0;
}
```

`CMakeLists.txt`
```
make_minimum_required(VERSION 3.10)

# set the project name and version
project(Tutorial VERSION 1.0)

#specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

#configure a header file
configure_file(TutorialConfig.h.in TutorialConfig.h)

# add the executable
add_executable(Tutorial tutorial.cxx)

# add directory to list of paths
target_include_directories(Tutorial PUBLIC
	                           "${PROJECT_BINARY_DIR}"
			)
```
other modified code

`TutorialConfig.h.in`
```
// the configured options and settings for Tutorial
#define Tutorial_VERSION_MAJOR @Tutorial_VERSION_MAJOR@
#define Tutorial_VERSION_MINOR @Tutorial_VERSION_MINOR@
```

screenshots of running `Tutorial` code

- without input ![image](https://user-images.githubusercontent.com/25308429/153645207-f385ad81-87ce-4764-bfef-06b448c9e32e.png)
- with 10 ![image](https://user-images.githubusercontent.com/25308429/153645257-1da9abcb-04d0-422b-9181-84d3a0bc26fc.png)
- with 4294967296 ![image](https://user-images.githubusercontent.com/25308429/153645292-862b374c-ad31-45a4-b3ef-b15ab2411b61.png)


### Step 2

modified code (?)

`tutorial.cxx`

`CMakeLists.txt`

screenshots of running `Tutorial` code

- without input
- with 10
- with 4294967296

### Step 3

`CMakeLists.txt`

`MathFunctions/CMakeLists.txt`

screenshots of running `Tutorial` code

- without input
- with 10
- with 4294967296

### Step 4

`CMakeLists.txt`

`MathFunctions/CMakeLists.txt`

output of running `ctest -VV`

### Step 5

`CMakeLists.txt`

`MathFunctions/CMakeLists.txt`

screenshots of running `Tutorial` for USE_MYMATH case code

- without input
- with 10
- with 4294967296

## Build systems example from class repository

Makefile

`CMakeLists.txt`

Makefile created by cmake

Relative size of the two executables

Results of running the program

