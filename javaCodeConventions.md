# Java Code Conventions

This guide is meant to serve as a standard for writing clean, readable code in an aim to be consistent between projects and increase longevity.  Most software will be maintained by people other than the original author throughout its lifecycle, so it is important to create your project in a manner others can understand quickly, easily, and thoroughly.  Following these guidelines will help to create sustainable and consistent software across authors.  While you should try to adhere to these guidelines, readability trumps these rules and you should use your best judgement.  This guide was made in while referencing [Oracle's Code Conventions](https://www.oracle.com/technetwork/java/codeconventions-150003.pdf), [Facebook's Coding Standards](https://github.com/facebook/jcommon/wiki/Coding-Standards), [Twitter's Coding Standards](https://github.com/twitter/commons/edit/master/src/java/com/twitter/common/styleguide.md), and [Google's Style Guide](https://google.github.io/styleguide/javaguide.html).


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
  - [Package Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#package-names)
- [Classes](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#classes)
  - [Class Structure](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#class-structure) 
  - [Overriding and Overloading](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#overriding-and-overloading)
- [Formatting](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#formatting)
  - [Blank Lines](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#blank-lines)
  - [Blank Spaces](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#blank-spaces)
  - [Indentation](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#indentation)
  - [Line Breaks](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#line-breaks)
  - [Wrapping](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#wrapping)
  - [Braces](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#braces)
  - [Parenthesis](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#parenthesis)
- [Naming Conventions](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#naming-conventions)
  - [Source File and Package Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#source-file-and-package-names)
  - [Class Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#class-names)
  - [Test Class Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#test-class-names)
  - [Interface Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#interface-names)
  - [Method Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#method-names)
  - [Test Method Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#test-method-names)
  - [Variable Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#variable-names)
  - [Parameter Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#parameter-names)
  - [Constant Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#constant-names)
- [Programming Practices](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#programming-practices)
  - [Visibility Modifiers](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#visibility-modifiers)
  - [Interfaces](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#interfaces)
  - [Annotations](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#annotations)
  - [This Keyword](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#this-keyword)
  - [Accessing Static Variables and Methods](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#accessing-static-variables-and-methods)
  - [Ternary Statements](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#ternary-statements)


## Source Files

### Source File Basics
  Java source files should contain only one public class or interface.  Files may contain inner classes and interfaces    associated with the the top level class, however, the top level class should be the first class in the file.
Files should be no longer than 2000 lines if possible.</br></br>

### Source File Names
  The source file should be case sensitive and use capital letters to delimit words.  The file should be named after its top level class or interface, plus the `.java` extension. Package and subpackage names should be lowercase.</br></br>
  
### Directory Layout
Common directory layouts will help other users find your project quickly and reliably.</br>

#### Source Directories
 The source files house all material for building the project. The source directory should contain a subdirectory for main (the main build artifact), test (unit tests for the build), and any other attributes associated with creating the build. Source files should be laid out in the following path format according to the Apache Maven Project Standard Directory Layout:

 
|  Path               |   File Type                          |
| :----               |    :----                             |
| `src/main/java`       | Application/Library sources          |
| `src/main/resources`  | Application/Library resources/configuration files                                                            |
| `src/main/filters`    | Resource filter files(contains files that inject values into the resources folder during the build phase)    |
| `src/main/webapp`     | Web application sources(contains resources like JavaScript, CSS, HTML files, view templates, and images)     |
| `src/test/java`       | Test sources                         |
| `src/test/resources`  | Test resources/configuration files   |
| `src/test/filters`    | Test resource filter files(contains files that inject values into the resources folder during the test phase)|
| `src/it`              | Integration Tests                    |
| `src/assembly`        | Assembly descriptor                  |
| `src/site`            | Site                                 |</br>

#### Target Directories
 The target files are created to specify a location to house all output of the build.  Target files should be labeled as `target/xxxxx` using the appropriate description for what will be housed in the file.  For example, for compiled `.class` files and resources from `src/main/resources` should be named `target/classes`.
 
 #### Text Files
 Certain text files can be included in the package structure in order to associate important information with the project.  *All projects must contain a `README.txt`* which contains a description for the project/build.  Examples of common text files are as follows:
 
 |  File Name          |   Description                        |
 | :----               |    :----                             |
 | `LICENSE.txt`         | Project's license                    |
 | `NOTICE.txt`          | Notices and attributions required by libraries the project depends on                                    |
 | `README.txt`          | Project's readme                     | </br>


### Source File Sections
  Files should be well organized in sections separated by one space and ordered accordingly:
  - Beginning comments and license or copyright information
  - Package statements
  - Import statements
  - Class and interface declarations</br>

#### Beginning Comments
  Beggining comments should follow [javaDoc standards](https://www.oracle.com/technetwork/articles/javase/index-137868.html).
It should list the version (using the `@version` tag), the programmer(s)(using the `@author` tag), the date(using the `@since` tag), the copyright(if present), and a brief description of the program and its uses.</br>

#### Package Statements
  Package statements do not follow the column limit, and therefore, should not be wrapped.</br>

#### Import Statements
  Import statements do not follow the column limit, and therefore, should not be wrapped.
  Imports should be ordered by top-level package with blank lines separating blocks in the following order and manner:
  1. Static imports in one block
  2. Non-static imports in the next block
  If there are both static and non-static imports, seperate the two blocks with a single blank line.  The imports in each block should be ordered in ASCII sort order.</br>
  Static imports should not be used for static nested classes, and should only be imported with normal imports.</br>
  Wildcard imports are not allowed.</br>
  Import of `java.lang.*` is not required.  `*` imports should be minimized, and all declared imports must be used.</br>

#### Class and Interface Declarations
  Each top level class(of any visibility type) resides in its own source file and should be listed first. Their class members and initializers ordered in a logical manner.  Do not order by date added (ie. add new methods at the bottom ect.).</br>
  Subclasses of '`Exception`' should have a name ending with '`Exception`'.</br>
  
  
## Packages
  
  ### Package Structure
  Projects should be organized into packages using a standard package naming scheme.  Use the reversed domain name, followed by the project specific packages and should be in all lowercase letters.</br> </br>
  For example, if you would like to create an application *`myApp`* as a part of Delta's IT department, the package name would be: `com.deltaairlines.it.myapp` and a class *`myClass`* inside this application would be: `com.deltaairlines.it.myapp.myclass`.</br>
  This would be located in your directory as `src/main/java/com/deltaairlines/it/myapp/myclass` and would compile into `target/classes/com/deltaairlines/it/myapp/myclass`.</br>
  Remember, the root of the source directory is `src/main/java` and the package should fall under this root. </br> </br>
  Another Example: </br>
  ![Maven Tree1](https://i.stack.imgur.com/Cc9HB.png "Via Stack Overflow") </br> </br>
  
  ### Package Names
  Package names should be all lowercase with seperate words concatinated together *without underscores*. </br> </br> </br>

## Classes
  
  ### Class Structure
  Classes should be structured for readibility and uniformity between objects.  This ordering should be followed as much as possible, however, if another structure or ordering is more logical and leads to easier readibility, opt for that.  Use your best judgement. </br>
  Classes should be grouped in the following order with a blank line seperating each group:
  1. `public static` variables
  2. package private `static` variables
  3. `private static` variables
  4. `public` instance variables
  5. package private instance variables
  6. `private` instance variables
  7. constructors
  8. `static` constructor methods
  9. `abstract` methods (only applicable for abstract classes)
  10. methods:
      1. `public` instance methods
      2. `public static` methods
      3. `private` instance methods
      4. `private static` instance methods
  11. non-`public` inner classes
  12. non-`public static` inner classes
  13. `public` inner classes
  14. `public static` inner classes </br> </br>
  
  ### Overriding and Overloading
  If a class has multiple constructors, list them sequentially by number of parameters.  </br>
  If overriding a method, **always** use the `@Override` tag. </br> </br> </br>


## Formatting


### Blank Lines
Blank lines can improve readability, however, they should be used consistently with the following rules in order to keep uniform code:

 |  Number of Lines   |   Location                                                      |
 | :----              |    :----                                                        |
 | Two                | Between class and interface definitions                         |
 | Two                | Between sections of a source file                               |
 | One                | Between methods                                                 |
 | One                | Between the local variables in a method and its first statement |
 | One                | Before a block or single-line comment                           |
 | One                | Between logical sections inside a method to improve readbility  |
 | One                | Between consecutive members or initializers of a class field, method, nested class, static initializer, or      instance initializer <ul><li>A blank line between two consecutive fields is optional and should used as needed to create logical groupings of fields</li></ul>| </br>

### Blank Spaces
A single blank space should appear in the following places **only**:
- Between a reserved word (such as `if`, `for`, `while`) and its open parentheses that follows on the same line
  - *Note:* a blank space should not be used between a method name and its opening parenthesis
- Between a reserved word (such as `else` or `catch`) and the closing curly brace immediately preceeding
- Before any open curly brace **except** when used as follows:
  - @SomeAnnotation({a, b})
  - String[][] x = {{"foo"}}
- After commas in argument lists
- On both sides of binary operators, ternary operators, or any other 'operator-like' symbol (such as conjunctive ampersands, ors ( `|` ,  `||` ), colons in foreach statements, and arrows in lambda expressions) **except** for:
  - colons in method references
  - dot seperators (such as `Object.toString()`)
  - unary operators (such as i++ or --i)
- Following the closing parenthesis of casts
- Between the type and variable of a declaration (such as `List<String> myList`) </br>

A single blank space is *optional* in the following places:
- On both sides of the double slash (`//`) that begins an end-of-line comment
- Just inside both braces of an array initializer </br> </br>

*Note:* These rules only address *interior* spaces, not additional spaces at the start of a line. </br>

Trailing whitespace is forbidden, and can cause issues for those who use keyboard shortcuts.</br> </br>

### Indentation
Indent with four spaces, not TABs. TABs should be set at 8 spaces.   </br> </br>

### Line Breaks
Line breaks should be used wisely and thoughtfully. </br>
In general, they should be used to:
1. Wrap a line which exceeds the column limit using the rules outlined in the following section
2. Logically seperate a thought in order to show hierarchy and seperation. 
  -Line breaks should be used for clarity and conveying information about your code.  If a line break will add information to the viewer about the code where the break is used, it is appropriate to use a line break. </br>

Use your best judgement when using line breaks, and when in doubt, default to less linebreaks.  </br> </br>

**TODO: Add visuals**

### Wrapping
Lines should not be longer than 80 characters. When a line does not fit under 80 characters, wrap it according to to these guidelines:
- Break after a comma
- Break before an operator
- Prefer higher level breaks to lower level breaks
- Align the new line with the beginning of the expression at the same level of the previous line </br>
If these rules create squished code or creates confusing formatting, use 8 spaces instead.  Line wrapping is meant to create clear code, so readability is the priority. </br> </br>
**TODO:uhhhhh (google & fb)**

### Braces
Code should follow the One True Brace Style ([1TBS](https://en.wikipedia.org/wiki/Indentation_style)) as described in the rules which follow. </br>
Braces should always be used for loops and if statements, even where they are optional.</br>
There should be no line break before the opening brace, and there should be a line break after the opening brace.  There should be a line break before the closing breace, and there should be a line break after the closing brace *only if* the brace terminates a statement or body of a method, constructor, or named class.  There is no line break after the brace if an else or comma follows the brace. </br>
An empty block may be closed on the same line it is opened (except when included in a multi-block statement), or it may follow the above rules.</br>
**TODO: write this clearly and add more visuals!** </br> </br>

### Parenthesis
Grouping parenthesis should be used liberally, and there should be no assumption of order presedence.  Optional grouping parenthesis may be omitted **only** if there is no reasonable chance the code will be misinterpreted without them. </br> </br>

## Naming Conventions
Names should be clear and concise. A user should be able to understand what the variable is or does by the name.  </br>
All identifiers should only contain Ascii letters, digits, and, in a few cases, underscores.  Single character or extremely short variable names are to be avoided, except as an indexer for loop iterations.

### Source File and Package Names
See [Source File Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#source-file-names) and [Package Names](https://github.com/KristenEBrown/codeConventions/blob/master/javaCodeConventions.md#package-names). </br> </br>

### Class Names
Class names are written in UpperCamelCase, and are typically nouns or noun phrases. They should be simple and discriptive.  Do not use acronyms or abbreviations, unless they are more commonly used than the complete word such as URL or HTML. </br> </br>

### Test Class Names
Test classes are named starting with the name of the class they are testing and end with the word `Test`.  Otherwise, they follow the same rules as classes. </br> </br>

### Interface Names
Interfaces should follow the same rules as classes. </br> </br>

### Method Names
Method names should be verbs or verb phrases in lowerCamelCase. </br> </br>

### Test Method Names
Test method names should use lowerCamelCase in each component, and each logical component should be seperated by underscores. </br>
Typically, they should follow the pattern of `<methodUnderTest>_<state>`. </br>
For example:
- `push_emptyStack` </br> </br>

### Variable Names
Variable names should be in lowerCamelCase and should be short and meaningful.  The name should be reflective of its use to the casual viewer.  </br>
One letter variables should only be used for temporary "throwaway" variables such as those used in loops.  Commonly used temporary variables include `i`, `j`, `k`, `m`, and `n` for integers, and `c`, `d`, and `e` for characters. </br> </br>

### Parameter Names
Parameters should be written in lowerCamelCase, and should not use one character parameter names in public methods. </br> </br>

### Constant Names
Constant variables (static final fields whos contents are immutible) should be ALL CAPS and words should be seperated by underscores. </br>
For example:
- `MIN_HEIGHT = 5` </br> </br> </br>

## Programming Practices

### Visibility Modifiers
**DO NOT** make any instance or class public without good reason.  This can lead to security issues and give improper access to the user. </br> 
Instead, *always* make getters and setters for accessing values in an alien object type, including in nested inner classes where java allow the container class to access private and protected feilds.  </br> </br>

### Interfaces
Any class which is non-trivial to construct or performs non-trivial action should be an interface when possible, especially when future classes will be performing those actions as well. This allows for abstraction and future mutability as interfaces allow multiple classes to impliment the outlined behavior whereas classes only allow one direct subclass.  </br> </br>

### Annotations
  Annotations appear immediately after the documentation block, and listed on their own line with one annotation per line.
  If overriding a method, **always** use the `@Override` tag, including for overriding a superclasses method. This will make the compiler help you out and avoid VERY hard to find bugs.</br>
  The `@Override` tag may only be ommitted if the parent method is `@Deprecated`</br>
  Use `@Nullable` when a variable, parameter, or method return may be `null`, even if it is private, however *try to use [`Optional`](https://docs.oracle.com/javase/8/docs/api/java/util/Optional.html) instead.* </br>
  `@VisibleForTesting` is allowed for testing if you must, **BUT**, testing private methods may be an indication those methods belong in a different class or in a public interface.  Code that is hard to test indictes that improvements can be made to this code.
  
### Null
  Object parameters to public constructors should always be checked against `null` unless `null` is allowed by the `@Nullable` tag. </br>
  By default, disallow `null`, even if the field/method is private. </br> </br>
  
 
### This Keyword
Only use `this.xxx` when accessing outside variable scopes.  </br>
For example: </br>
- This is the correct use of the `this` keyword (count is an instance field in the class which houses this method): </br>
  `public setCount(int count) {` </br>
      `this.count = count;` </br>
  `}` </br>
    
- The `this` keyword should not be used in this example: </br>
  `public setCount(int newCount) {` </br>
      `count = newCount;` </br>
  `}` </br> </br>
    
### Accessing Static Variables and Methods
Do not access static variables or methods using an instance of the class.  Instead, use the class name. </br>
For example:
- `Dogs.packNum`     //Good
- `Fido.packNum`     //Bad  
- `newDog().packNum` //Very Bad
*where packNum is a static variable belonging to the Dogs class* </br> </br>

### Ternary Statements
Expressions before ? in ternary statements should be surrounded by parenthesis.
For example:
- `aBool ? aFunct() : bFunct()`  //Good
- `(a < b) ? a : b`              //Good   
- `a < b ? a : b`                //Bad

### Caught Exceptions
It is best practice to **always** handle a caught exception.  If it is truly appropriate to take no action inside a catch block, justify your reasoning inside that catch block. </br>
In tests, if the caught exception is expected to be thrown, a commented is not needed as long as the error name starts with `expected.


