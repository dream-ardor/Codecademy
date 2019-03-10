## HELLO WORLD: JAVA

### Compilation: Catching Errors

Java is a compiled programming language, meaning the code we write in a .java file is transformed into byte code by a compiler before it is executed by the Java Virtual Machine on your computer.

A compiler is a program that translates human-friendly programming languages into other programming languages that computers can execute.

Steps of Java Compilation

Previous exercises have automatically compiled and run the files for you. Off-platform development environments can also compile and run files for you, but it's important to understand this aspect of Java development so we'll do it ourselves.

The compiling process catches mistakes before the computer runs our code.

The Java compiler runs a series of checks while it transforms the code. Code that does not pass these checks will not be compiled.

This exercise will use an interactive terminal. Codecademy has a lesson on the command line if you'd like to learn more.

We compile a .java file with the terminal command: javac ExampleFile.java.

A successful compilation produces a .class file: ExampleFile.class, that we execute with the terminal command java ExampleFile.

An unsuccessful compilation produces a list of errors. No .class file is made until the errors are corrected and the compile command is run again.

### Instructions

Let's practice compiling and executing a file by entering commands in the terminal!

Our text editor contains a broken program so we can see how compilers help us catch mistakes. Don't make any corrections!

In the terminal, type this command: javac Compiling.java and press enter or return.

Use the Check Work button to progress through checkpoints.

Do you see the error?

The compiler is telling us one of the print statements is missing a semicolon.

In the terminal, type ls and press return or enter.

The ls command lists all the available files.

There is only one file: Compiling.java, we did not successfully compile the file because of the error.

Add the missing semicolon in the text editor.

We'll compile and execute this file in the next exercise!
