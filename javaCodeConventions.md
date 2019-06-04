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
  - [Directory Layout](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#directory-layout)
    - [Source Directories](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#source-directories)
    - [Target Directories](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#target-directories)
    - [Text Files](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#text-files)
  - [Source File Sections](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#source-file-sections)
    - [Beginning Comments](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#beginning-comments)
    - [Package Statements](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#package-statements)
    - [Import Statements](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#import-statements)
    - [Class and Interface Declarations](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#Class-and-Interface-Declarations)
- [Packages](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#packages)  
  - [Package Structure](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#package-structure)
- [Classes](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#classes)  


## Source Files

### Source File Basics
  Java source files should contain only one public class or interface.  Files may contain inner classes and interfaces    associated with the the top level class, however, the top level class should be the first class in the file.
Files should be no longer than 2000 lines if possible.</br></br>

### Source File Names
  The source file should be case sensitive and use capital letters to delimit words.  The file should be named after its top level class or interface, plus the *.java* extension. Package and subpackage names should be lowercase.</br></br>
  
### Directory Layout
Common directory layouts will help other users find your project quickly and reliably.</br>
#### Source Directories
 The source files house all material for building the project. The source directory should contain a subdirectory for main (the main build artifact), test (unit tests for the build), and any other attributes associated with creating the build. Source files should be laid out in the following path format according to the Apache Maven Project Standard Directory Layout:

 
|  Path               |   File Type                          |
| :----               |    :----                             |
| src/main/java       | Application/Library sources          |
| src/main/resources  | Application/Library resources/configuration files                                                             |
| src/main/filters    | Resource filter files(contains files that inject values into the resources folder during the build phase)     |
| src/main/webapp     | Web application sources(contains resources like JavaScript, CSS, HTML files, view templates, and images)      |
| src/test/java       | Test sources                         |
| src/test/resources  | Test resources/configuration files   |
| src/test/filters    | Test resource filter files(contains files that inject values into the resources folder during the test phase) |
| src/it              | Integration Tests                    |
| src/assembly        | Assembly descriptor                  |
| src/site            | Site                                 |</br>

#### Target Directories
 The target files are created to specify a location to house all output of the build.  Target files should be labeled as target/xxxxx using the appropriate description for what will be housed in the file.  For example, for compiled .class files and resources from src/main/resources should be named target/classes.
 
 #### Text Files
 Certain text files can be included in the package structure in order to associate important information with the project.  *All projects must contain a README.txt* which contains a description for the project/build.  Examples of common text files are as follows:
 
 |  File Name          |   Description                        |
 | :----               |    :----                             |
 | LICENSE.txt         | Project's license                    |
 | NOTICE.txt          | Notices and attributions required by libraries the project depends on                                    |
 | README.txt          | Project's readme                     | </br>


**TODO:FINISH THIS**</br></br>

### Source File Sections
  Files should be well organized in sections separated by one space and ordered accordingly:
  - Beginning comments and license or copyright information
  - Package statements
  - Import statements
  - Class and interface declarations</br>

#### Beginning Comments
  Beggining comments should follow [javaDoc standards](https://www.oracle.com/technetwork/articles/javase/index-137868.html).
It should list the version (using the @version tag), the programmer(s)(using the @author tag), the date(using the @since tag), the copyright(if present), and a brief description of the program and its uses.</br>

#### Package Statements
  Package statements do not follow the column limit, and therefore, should not be wrapped.</br>

#### Import Statements
  Import statements do not follow the column limit, and therefore, should not be wrapped.
  Imports should be ordered:
  1. Static imports in one block
  2. Non-static imports in the next block
  If there are both static and non-static imports, seperate the two blocks with a single blank line.  The imports in each block should be ordered in ASCII sort order.</br>
  Static imports should not be used for static nested classes, and should only be imported with normal imports.</br>
  Wildcard imports are not allowed.</br>
  Import of *java.lang.** is not required.  '*' imports should be minimized, and all declared imports must be used.</br>

#### Class and Interface Declarations
  Each top level class(of any visibility type) resides in its own source file and should be listed first. Their class members and initializers ordered in a logical manner.  Do not order by date added (ie. add new methods at the bottom ect.).</br>
  Subclasses of 'Exception' should have a name ending with 'Exception'.</br>
  *TODO: Add something?? Idk talk to JT* </br> </br> </br>
  
## Packages
  
  ### Package Structure
  Projects should be organized into packages using a standard package naming scheme.  Use the reversed domain name, followed by the project specific packages and should be in all lowercase letters.</br>
  For example, if you would like to create an application *myApp* as a part of Delta's IT department, the package name would be: com.deltaairlines.it.myapp and a class myClass inside this application would be: com.deltaairlines.it.myapp.myClass.  This would be located in your directory as src/main/java/com/deltaairlines/it/myapp/myclass and would be compiled into target/classes/com/deltaairlines/it/myapp/myclass.  Remember, the root of the source directory is src/main/java and the package should fall under this root. 
  
  **TODO add visual example!** </br> </br> </br>
  
  
  ## Classes
  
  
 </br>
  If a class has multiple constructors, list them sequentially by number of parameters.  If overriding a method, **always** use the @Override tag.




