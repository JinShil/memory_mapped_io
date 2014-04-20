memory_mapped_io
================

A memory-mapped IO library written in the D programming language.

This library was created to support other concurrent efforts to bring the D programming language to ARM Cortex-M microcontrollers.  It is currently quite specific to the STM32 ARM Cortex-M4 microcontroller, but it would be nice if it could be made more general purpose.  

The design of this library originally influenced by a paper written by Ken Smith titled "[C++ Hardware Register Access Redux](http://yogiken.files.wordpress.com/2010/02/c-register-access.pdf)". It was then modified to take advantage of some unique features of the D programming language. 

To date, this library has only been used with the [GDC compiler](https://github.com/D-Programming-GDC/GDC).

Goals
---------

* Reduces code size and increase performance by utilizing the D programming language's Compile-Time Function Execution (CTFE) feature reducing register access to as few instructions as possible.
* Provide a strong correlation between code and datasheet to make authoring code from the datasheet and verifying code against the datasheet convenient and less error-prone.
* Provide convenient access to registers and bitfileds with object-oriented syntax.
* Together with tooling, such as code completion (see [DCD](https://github.com/Hackerpilot/DCD)), provide context-sensitive information to the programmer to reduce the frequency with which he/she has to refer to the datasheet.

Features
--------
* Enforces word, half-word, and byte access policy at compile time.  See Access.
* Enforces mutability constraints such as read, write, readwrite, etc... at compile time. See Mutability.
* Optimizes byte-aligned and half-word aligned bitfields generating atomic read/write operations resulting in smaller code size and faster performance.
* It optimizes bitfieds of a single bit, via bit-banding, generating atomic read/write operations resulting in smaller code size and faster performance.
* It can combine multiple bitfield accesses within a single register into one read-modify-write operation resulting in smaller code size and faster performance.
* It enables intuitive and obvious register modeling that directly cross-references back to register specifications.

Licensing
---------

See the LICENSE file for licensing information.

Contributing
------------

Your critique, suggestions, pull requests, issue reports, and other participation is most welcome.  I can be contacted vir IRC at [FreeNode](http://freenode.net)'s #d channel (irc://irc.freenode.net/d)

TODO
---------

* Add complete DDoc comments to all interfaces
* Add a real-world example
* Add example showing importance of tooling (code completion)
