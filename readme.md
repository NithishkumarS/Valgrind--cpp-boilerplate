# C++ Boilerplate
[![Build Status](https://travis-ci.org/NithishkumarS/Valgrind--cpp-boilerplate.svg?branch=valgrind_exercise)](https://travis-ci.org/NithishkumarS/Valgrind--cpp-boilerplate.svg?branch=valgrind_exercise)
[![Coverage Status](https://coveralls.io/repos/github/NithishkumarS/Valgrind--cpp-boilerplate/badge.svg?branch=valgrind_exercise)](https://coveralls.io/github/NithishkumarS/Valgrind--cpp-boilerplate?branch=valgrind_exercise)

## Overview

Simple starter C++ project with:

- cmake
- googletest

## Standard install via command-line
```
git clone --recursive https://github.com/dpiet/cpp-boilerplate
cd <path to repository>
mkdir build
cd build
cmake ..
make
Run tests: ./test/cpp-test
Run program: ./app/shell-app
```
- Git

    It is possible to manage version control through Eclipse and the git plugin, but it typically requires creating another project. If you're interested in this, try it out yourself and contact me on Canvas.

## Run Valgrind test

To install valgrind
```
sudo apt install valgrind
```
To install Kcachegrind
```
sudo apt install kcachegrind
```
For identifying errors, memory leaks using valgrind
```
cd <path to repository>
valgrind --tool=memcheck --leak-check=full ./build/app/shell-app 
```
Function and Memory Profiling:
```
valgrind --tool=callgrind ./build/app/shell-app
valgrind --tool=massif ./build/app/shell-app
```
The above two commands produce a callgrind.out and massif.out files respectively.

To visualize callgrind.out file we use Kcachegrind.
```
kcachegrind
```
In the application that opens up, click on open menu. Select the callgrind.out file from your repository.

To visualize massif.out file in the terminal.
```
ms_print massif.out.<process id>
```
