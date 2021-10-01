In this quest, you will discover how to deal with errors that may occur during the execution of your java program.

Exceptions represent the mechanism for handling errors that occur during the execution of a Java program.

When an error is detected, an object that inherits from the class **Exception** is created (an exception is said to be thrown) and propagated through the execution stack until it is processed.

These mechanisms allow to reinforce the robustness of the Java code.

#### Objectives

- Understanding what an exception is

- Know how to handle exceptions

### Try and Catch

To illustrate the role of exception handling, take the example of division by zero, which is mathematically impossible.

Read this code and execute it:

```java
public class WildException {
    public static void main(String[] args) {
        int i = 3;
        int j = 0;
        System.out.println("result = " + (i / j));
    }
}

```

In this example, the code attempts to divide the number 3 by zero, which is prohibited.

This causes an exception of the type `ArithmeticException `which is a girl's class of the general class. `Exception `which is automatically lifted for any arithmetic error.

#### 1. Result

![](https://image.noelshack.com/fichiers/2019/45/5/1573237943-exception1.jpg)

As you can see, you had an exception and your program ended abruptly. You can handle this exception in one of the following ways:

1. Try to retrieve it with `try`/`catch`

1. Add the keyword `throws` in the declaration of the block

#### 2. Keywords try, catch

Look at [this course](https://www.jmdoudoux.fr/java/dej/chap-exceptions.htm#exceptions-1) he'll teach you everything you need to know about try and catch.

#### 3. Explanations and remarks

If an adverse event occurs in the block `try `block, the possibly non-executed part of this block is abandoned and the first block `catch` is processed.

If a  `catch` block is set to capture the exception from the `try `If the block is a block, then it is processed by executing the code associated with the block.

If the block`catch` is empty (no instruction between braces) the captured exception is then ignored. Such use of the instruction`try`/`catch` is not a good practice: it is preferable to always provide an adapted treatment when catching an exception.

#### 4. Example: Maintaining the Plant by Zero Exception

We go back to our example and add exception handling:

```java
public class WildException2 {

    public static void main(String[] args) {
        try {
            int i = 3;
            int j = 0;
            System.out.println("résultat = " + (i / j));
        } catch (ArithmeticException e) {
            System.err.println("Division by Zero occurred!");
        }
        System.out.println("You handled the exception well and I continued the execution.");

    }

}

```

If there are several types of errors and exceptions to intercept, as many catch blocks as event types must be defined. By type of exception is meant "which is of the type of the class of the exception or one of its subclasses".

Thus in the sequential order of the clauses `catch` an exception type should not come after a superclass exception type. **Care must be taken with the order of the catch clauses to deal with the more specific exceptions (subclasses) first before the more general exceptions.** An error message is issued by the compiler if this is not the case.

To illustrate the importance of the order of the clauses `catch` implements this piece of code:

```java
public class WildException3 {
    public static void main(java.lang.String[] args) {
        int i = 3;
        int j = 0;
        try {
            System.out.println("result = " + (i / j));
        } catch (Exception e) {
        } catch (ArithmeticException e) {
        }
    }
}

```

If you use a_IDE_you'll have a mistake like **unreachable catch block** which simply tells you that this code will never be executed because... `ArithmeticException` is a subclass of the class `Exception`.
Otherwise, you'll get a compilation error that tells you the same thing:

![](https://image.noelshack.com/fichiers/2019/45/5/1573238099-exception2.jpg)

### Finally

Let's say you want to perform an action, whether an exception is raised or not ([Java Finally block - Exception handling](https://beginnersbook.com/2013/04/java-finally-block/)). Java allows you to use a clause via the keyword `finally`. Let's see what this code does:

```java
public class WildException4 {

    public static void main(String[] args) {
        try {
            int i = 3;
            int j = 0;
            System.out.println("résultat = " + (i / j));
        } catch (ArithmeticException e) {
            System.err.println("Division by Zero occurred!");
        } finally {
            System.out.println("In any case, we will end here.");
        }
    }
}

```

The code block inside the `finally` will be executed in any case.

### More Resources 

* [Java Exceptions - Try...Catch](https://www.w3schools.com/java/java_try_catch.asp)
* [Java Finally block - Exception handling](https://beginnersbook.com/2013/04/java-finally-block/)

### Optional

* [Chained Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/chained.html)
* [Custom Exceptions](https://docs.oracle.com/javase/tutorial/essential/exceptions/creating.html)
* [The throw instruction](https://docs.oracle.com/javase/tutorial/essential/exceptions/throwing.html)
* [The try-with-resources instruction](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html)

## Challenge

### Sum of odd numbers

To get started, [make a Fork of the following repository]() then clone it locally.
> Remember to do a_Fork_or you won't be able to push anything!

### Validation criterias

* The code is clean and contains the `try` and `catch`.
* The test `hhh` runs without error and all tests are OK.
* Use the appropriate type of exception.

