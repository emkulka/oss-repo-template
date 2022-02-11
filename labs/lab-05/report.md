# Lab 05 - Build Systems

## CMake tutorial - steps 1 through 5

### Step 1

(results are from the end of this step)

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

`tutorial.cxx`

```
// A simple program that computes the square root of a number
#include <cmath>
#include <iostream>
#include <string>

#include "TutorialConfig.h"

#ifdef USE_MYMATH
#  include "MathFunctions.h"
#endif

int main(int argc, char* argv[])
{
  if (argc < 2) {
    // report version
    std::cout << argv[0] << " Version " << Tutorial_VERSION_MAJOR << "."
              << Tutorial_VERSION_MINOR << std::endl;
    std::cout << "Usage: " << argv[0] << " number" << std::endl;
    return 1;
  }

  // convert input to double
  const double inputValue = std::stod(argv[1]);

  // calculate square root
#ifdef USE_MYMATH
    const double outputValue = mysqrt(inputValue);
#else
    const double outputValue = sqrt(inputValue);
#endif
  std::cout << "The square root of " << inputValue << " is " << outputValue
            << std::endl;
  return 0;
}
```

`CMakeLists.txt`

```
cmake_minimum_required(VERSION 3.10)

# set the project name and version
project(Tutorial VERSION 1.0)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

option(USE_MYMATH "Use tutorial provided math implementation" ON)

# configure a header file to pass some of the CMake settings
# to the source code
configure_file(TutorialConfig.h.in TutorialConfig.h)

# add the MathFunctions library
if(USE_MYMATH)
	add_subdirectory(MathFunctions)
	list(APPEND EXTRA_LIBS MathFunctions)
	list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/MathFunctions")
endif()

# add the executable
add_executable(Tutorial tutorial.cxx)

target_link_libraries(Tutorial PUBLIC ${EXTRA_LIBS})

# add the binary tree to the search path for include files
# so that we will find TutorialConfig.h
target_include_directories(Tutorial PUBLIC
	                          "${PROJECT_BINARY_DIR}"
				  ${EXTRA_INCLUDES}
			 )
```

other modified code

`TutorialConfig.h.in`

```
// the configured options and settings for Tutorial
#define Tutorial_VERSION_MAJOR @Tutorial_VERSION_MAJOR@
#define Tutorial_VERSION_MINOR @Tutorial_VERSION_MINOR@
#cmakedefine USE_MYMATH
```

screenshots of running `Tutorial` code (with mysqrt*)

- without input ![image](https://user-images.githubusercontent.com/25308429/153652535-6c927639-f051-4ee5-b05f-487c69a6ed12.png)
- with 10 ![image](https://user-images.githubusercontent.com/25308429/153652593-fc3152c5-2c05-4cf0-9a28-9ba84a6e09de.png)
- with 4294967296 ![image](https://user-images.githubusercontent.com/25308429/153652649-a544523f-9837-4ad5-83b5-2313c0468f0d.png)

*note: using sqrt in Step 2 produces the same output as step 1

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

