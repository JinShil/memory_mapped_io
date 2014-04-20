memory_mapped_io
================

A memory-mapped IO library written in the D programming language.

This library was created to support other concurrent efforts to bring the D programming language to ARM Cortex-M microcontrollers.  It is currently quite specific to the STM32 ARM Cortex-M4 microcontroller, but it would be nice if it could be made more general purpose.  

The design of this library originally influenced by a paper written by Ken Smith titled "[C++ Hardware Register Access Redux](http://yogiken.files.wordpress.com/2010/02/c-register-access.pdf)". It was then modified to take advantage of some unique features of the D programming language. 

Your critique and suggestions are welcome.

Goals
---------

* Reduces code size and increase performance by utilizing the D programming language's Compile-Time Function Execution (CTFE) feature reducing register access to as few instructions as possible.
* Provide a strong correlation between code and datasheet to make authoring code from the datasheet and verifying code against the datasheet convenient and less error-prone.
* Provide convenient access to registers and bitfileds with object-oriented syntax.
* Together with tooling, such as code completion (see [DCD](https://github.com/Hackerpilot/DCD)), provide information to the programmer to reduce the frequency with which he/she has to refer to the datasheet.

Licensing
---------

See the LICENSE file for licensing information.


