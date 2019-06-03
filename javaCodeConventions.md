TODO:
-fix links to table of contents
- add contents
- review and update conventions
  -references: </br><https://github.com/facebook/jcommon/wiki/Coding-Standards> , </br><https://github.com/twitter/commons/edit/master/src/java/com/twitter/common/styleguide.md>,</br>
<https://google.github.io/styleguide/javaguide.html>,<https://www.oracle.com/technetwork/java/codeconventions-150003.pdf>, </br>
<https://www.oracle.com/technetwork/java/codeconventions-150003.pdf>

# Java Code Conventions

This guide is meant to serve as a standard for writing clean, readable code in an aim to be consistent between projects and increase longevity.  Most software will be maintained by people other than the original author throughout its lifecycle, so it is important to create your project in a manner others can understand quickly, easily, and thoroughly.  Following these guidelines will help to create sustainable and consistent software across authors.  While you should try to adhere to these guidelines, readability trumps these rules and you should use your best judgement.


## Table of Contents
- [Source Files](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#source-files)
  - [Source File Basics](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#source-file-basics)
  - [Source File Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#source-file-names)
  - [Source File Sections](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#source-file-sections)
    - [Beginning Comments](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#beginning-comments)
    - [Package Statements](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#package-statements)
    - [Import Statements](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#import-statements)
    - [Class and Interface Declarations](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#Class-and-Interface-Declarations)
   


## Source Files

### Source File Basics
  Java source files should contain only one public class or interface.  Files may contain private classes and interfaces    associated with the the top level class, however, the top level class should be the first class in the file.</br></br>
Files should be no longer than 2000 lines if possible.

### Source File Names
  The source file should be case sensitive and use capital letters to delimit words.  The file should be named after its top level class or interface, plus the *.java* extension. Package and subpackage names should be lowercase.
  
### Directory Layout
Common directory layouts will help other users find your project quickly and reliably.  
**TODO:FINISH THIS**

### Source File Sections
  Your file should be well organized in sections separated by one space and ordered accordingly:
  - Beginning comments and license or copyright information
  - Package statements
  - Import statements
  - Class and interface declarations

#### Beginning Comments
  Beggining comments should follow [javaDoc standards](https://www.oracle.com/technetwork/articles/javase/index-137868.html).
It should list the version (using the @version tag), the programmer(s)(using the @author tag), the date(using the @since tag), the copyright(if present), and a brief description of the program and its uses.  

#### Package Statements
  Package statements do not follow the column limit, and therefore, should not be wrapped.

#### Import Statements
  Import statements do not follow the column limit, and therefore, should not be wrapped.
  Imports should be ordered:
  1. Static imports in one block
  2. Non-static imports in the next block
  If there are both static and non-static imports, seperate the two blocks with a single blank line.  The imports in each block should be ordered in ASCII sort order.</br>
  Static imports should not be used for static nested classes, and should only be imported with normal imports.</br>
  Wildcard imports are not allowed.</br>
  Import of *java.lang.** is not required.  '*' imports should be minimized, and all declared imports must be used.

#### Class and Interface Declarations
  Each top level class resides in its own source file and should be listed first. Their class members and initializers ordered in a logical manner.  Do not order by date added (ie. add new methods at the bottom ect.).</br>
  Subclasses of 'Exception' should have a name ending with 'Exception'.
  
  
  
  
  
 </br>
  If a class has multiple constructors, list them sequentially by number of parameters.  If overriding a method, **always** use the @Override tag.


