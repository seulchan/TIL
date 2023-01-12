# Modules, libraries and packages

Modules and packages can easily be confused because of their similarities, but there are a few differences. Modules are similar to files, while packages are like directories that contain different files. Modules are generally written in a single file, but that's more of a practice than a definition. 

Packages are essentially a type of module. Any module that contains the  ```__path__``` definition is a package. Packages, when viewed as a directory, can contain sub-packages and other modules. Modules, on the other hand, can contain classes, functions and data members just like any other Python file. 

Library is a term that's used interchangeably with imported packages. But in general practice, it refers to a collection of packages.

Despite the differences between modules, packages and libraries, you can import any of them using import statements.  