# Development-Docs
Code conventions are important to programmers for a number of reasons:
* 80% of the lifetime cost of a piece of software goes to maintenance.
* Hardly any software is maintained for its whole life by the original author.
* Code conventions improve the readability of the software, allowing engineers to understand new code more quickly and thoroughly.
* If you ship your source code as a product, you need to make sure it is as well packaged and clean as any other product you create.

For a full code conventions please visit [Code Conventions for the Java TM Programming Language](http://www.oracle.com/technetwork/java/javase/documentation/codeconvtoc-136057.html)

# Table of contents

* [Use a consistent style](#use-a-consistent-style)
    * [Naming Conventions](#naming-conventions)
    * [Comments](#comments)
    * [Declarations](#declarations)
    * [Statements](#statements)


## Use a consistent style

### Naming Conventions

* Packages - The prefix of a unique package name is always written in all-lowercase

```
    org.my.package
    org.my.package.models
    org.my.package.controllers
    org.my.package.utils
``` 

* Classes, Interfaces - Class names should be nouns, in mixed case with the first letter of each internal word capitalized. Try to keep your class names simple and descriptive

```
    class Train;
    class TrainController;
    class TrainUtils;
```

* Methods - Methods should be verbs, in mixed case with the first letter lowercase, with the first letter of each internal word capitalized.

```
    run();
    runFast();
    getBackground();
```

* Variables - Variables names should be short yet meaningful. The choice of a variable name should be designed to indicate the casual observer the intent of its use. One-character variable names should be avoided except for temporary "throwaway" variables.

```
    int i;
    float myWidth;
```

* Constants - The names of variables declared class constants should be all uppercase with words separated by underscores ("_")

```
    static final int MIN_WIDTH = 4;
    static final int MAX_WIDTH = 999;
```


### Comments

Comments should be used to give overviews of code and provide additional information that is not readily available in the code itself. Comments should contain only information that is relevant to reading and understanding the program. For example, information about how the corresponding package is built or in what directory it resides should not be included as a comment.

* Block Comments - Block comments are used to provide descriptions of files, methods, data structures and algorithms. 

```
    /*
    * Here is a block comment.
    */
```

* Single-Line Comments - Short comments can appear on a single line indented to the level of the code that follows.

```
    if (condition) {

        /* Handle the condition. */
        ...
    }
```

* End-Of-Line Comments - The // comment delimiter can comment out a complete line or only a partial line. 

```
    if (foo > 1) {

        // Do a double-flip.
        ...
    }
    else {
        return false;          // Explain why here.
    }
    //if (bar > 1) {
    //
    //    // Do a triple-flip.
    //    ...
    //}
    //else {
    //    return false;
    //}
```

* [Documentation Comments](http://www.oracle.com/technetwork/java/javase/documentation/index-137868.html) - Doc comments describe Java classes, interfaces, constructors, methods, and fields. Each doc comment is set inside the comment delimiters /**...*/, with one comment per class, interface, or member. This comment should appear just before the declaration:

```
    /**
    * The Example class provides ...
    */
    public class Example { ...
```


### Declarations

* Number Per Line - One declaration per line is recommended since it encourages commenting. In other words,

```
    int level; // indentation level
    int size;  // size of table
    
    is preferred over
    int level, size;

    Do not put different types on the same line. Example:
    int foo,  fooarray[]; //WRONG!
```

* Initialization - Try to initialize local variables where they're declared. The only reason not to initialize a variable where it's declared is if the initial value depends on some computation occurring first.


### Statements

* Simple Statements - Each line should contain at most one statement. Example:

argv++;         // Correct
argc--;         // Correct  
argv++; argc--; // AVOID!

* Compound statements - Compound statements are statements that contain lists of statements enclosed in braces "{ statements }". See the following sections for examples.
    * The enclosed statements should be indented one more level than the compound statement.
    * The opening brace should be at the end of the line that begins the compound statement; the closing brace should begin a line and be indented to the beginning of the compound statement.
    * Braces are used around all statements, even single statements, when they are part of a control structure, such as an if-else or for statement. This makes it easier to add statements without accidentally introducing bugs due to forgetting to add braces.

```
    if (condition) {
        statements;
    } else {
        statements;
    }

    if (condition) //AVOID! THIS OMITS THE BRACES {}!
        statement;

    for (initialization; condition; update) {
        statements;
    }

    while (condition) {
        statements;
    }

    do {
        statements;
    } while (condition);

    switch (condition) {
    case ABC:
        statements;
        /* falls through */
    case DEF:
        statements;
        break;
    case XYZ:
        statements;
        break;
    default:
        statements;
        break;
    }

    try {
        statements;
    } catch (ExceptionClass e) {
        statements;
    }

    try {
        statements;
    } catch (ExceptionClass e) {
        statements;
    } finally {
        statements;
    }
```
