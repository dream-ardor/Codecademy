## HELLO WORLD: JAVA

### Compilation: Creating Executables

Compilation helped us catch an error. Now that we've corrected the file, let's walk through a successful compilation.

As a reminder, we can compile a .java file from the terminal with the command: javac FileName.java.

If the file compiles successfully, this command produces an executable class: FileName.class. Executable means we can run this program from the terminal.

We run the executable with the command: java FileName. Note that we leave off the .class part of the filename.

Here's a full compilation cycle as an example:
```java
// within the file: Welcome.java
public class Welcome {
  public static void main(String[] args) {
    System.out.println("Welcome to Codecademy's Java course!");
  }
}
```
We have one file: Welcome.java. We compile with the command: javac Welcome.java. The terminal shows no errors, which indicates a successful compilation.

We now have two files:

Welcome.java, our original file with Java syntax.
Welcome.class, our compiled file with Java bytecode, ready to be executed by the Java Virtual Machine.
We can execute the compiled class with the command: java Welcome.

The following is printed to the screen:

Welcome to Codecademy's Java course!

### Instructions

Let's compile and execute our program!

Run the ls command in the terminal to see the uncompiled .java file.

Compile the file from the terminal!

Enter ls again to see the new .class file.

Run the executable file from the terminal!
