##  Trees vs Files

![picture of man tree](images/tree.jpg)


NOTE:
This implies that transforms map trees 1:1. Surprisingly, this is not a good abstraction for all compilers. For instance, the Sass compiler has a notion of “load paths” that it searches when it encounters an @import directive. Similarly, JavaScript concatenators like r.js have a “paths” option to search for imported modules. These load paths are ideally represented as a set of “tree” objects.
