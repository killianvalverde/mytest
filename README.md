# mytest

## Table of Contents
- [Introduction](#introduction)
- [Documentation](#documentation)
- [Supported Compilers](#supported-compilers)
- [Requirements](#requirements)
- [Build](#build)
- [Install](#install)

## Introduction

Project for testing.

## Documentation

To access the help menu of this software in order to know all the available options and commands, 
simply run `mytest --help` in a terminal after installing it.

To generate Doxygen documentation, run the command `doxygen Doxyfile`. The generated files will 
be stored in the `docs` directory

## Supported Compilers

The following compilers are currently known to be compatible:

| Compiler                                                   | Standard Library | Test Environment   |
|:-----------------------------------------------------------| :--------------- | :----------------- |
| [GCC](https://gcc.gnu.org/) >= 11.4.0                      | libstdc++        | Ubuntu 22.04       |
| [MSVC](https://visualstudio.microsoft.com/) >= 19.41.34123 | Microsoft STL    | Visual Studio 2022 |

## Requirements

To compile this software, you must have the following tools and libraries installed:

| Software                                                                 | Type         | Platform Dependency | Linux Installation Command |
|:-------------------------------------------------------------------------|:-------------|:--------------------|:---------------------------|
| [CMake](https://www.cmake.org/) >= 3.22                                  | Build system | All                 | `sudo apt install cmake`   |
| [speed](https://github.com/killianvalverde/speed/tree/develop) (develop) | Library      | All                 | Unavailable                |

## Build

Use the folowing commands to buil and install the CMake project:

1. Create a directory to hold the build output and generate the native build scripts:

       cmake -S . -B cmake-build-release -DCMAKE_BUILD_TYPE=Release

2. Compile the project directly from CMake using the native build scripts:

       cmake --build cmake-build-release --config Release

## Install

By default, CMake installs the software in a standard location. If you wish to customize the 
installation directory, use the `--prefix <path>` option at the end of the CMake command to specify 
the desired path. Note that depending on your system, elevated privileges may be required to 
complete the installation. The provided commands take this into account.

### Linux

Run the following Bash command to install the software with root privileges:

    sudo cmake --install cmake-build-release --config Release

### Windows

Run the following PowerShell command to install the software with administrator privileges:

    Start-Process powershell -Verb RunAs -ArgumentList "-Command", `
        "Set-Location -Path '$PWD'; cmake --install cmake-build-release --config Release; pause"
