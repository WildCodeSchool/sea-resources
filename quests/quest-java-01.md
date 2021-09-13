That's it, now you are finally ready to start developing, for real using Java! However, before racing off into the sunset, let’s take a step back, fasten our seatbelts, and navigate through this first quest together.

In this quest, we want to show you the ropes of the Java language, so that you can get out there and start using them independently!

#### Goals

- Understand the basic concepts in Java, JRE, JDK and JVM languages

- Create and compile a class

### Installing the JDK

Java is a programming language, and although colloquially, we often say that we will "install Java" on our computer.

In reality, when you want to start running programs written in Java, you do not need to install the Java language itself, but rather something called the _JRE_ (Java Runtime Environment).

In fact, a program that is written in Java needs to be converted in order to be understood by computers: this process is called compilation. Conveniently, there is a compiler built into the _JDK_ (Java Development Kit).

Because you are here, you probably are striving to create your own programs in Java, and this means that you will eventually want to compile and execute these programs. In theory, in order to achieve this you would need to install both the _JRE_ and the _JDK_. However, often times the _JDK_ alone is sufficient, as it contains tools that can be used to both compile and execute code.

Once the *JDK* is installed, check the version using the following command:

```Bash
javac --version

```

You should have version 11 or higher. If you don’t, seek out help.

> Java version 11 is the current LTS release which should be the minimum for every new Java project. Legacy projects often require Java version 8 and should, if possible, be updated to a newer version of Java.

```resource
https://www.java.com/en/download/faq/techinfo.xml
# Java SE, Java EE, JDK, JRE what differences?
```

### Your first class

#### 1. Creating the file

We know your fingers are itching to start typing out your very first Java program!

First, get organised and make a new `JavaProjects` folder on your computer, in which you can store all your future Java applications.

In that `JavaProjects` folder, create a folder called `JavaIntro` and, inside this folder, create a blank file called: `HelloWorld.java`.

You should now have the following file path structure:

```Bash
JavaProjects/JavaIntro/HelloWorld.java

```

Your Java file must use the _.java_ extension, and should have a name that is written in _CamelCase_ that starts with a capital letter.

Edit your brand new file using your favorite editor.

We are using Visual Studio Code here, you can start in with `code`.

```bash
code JavaProjects/JavaIntro/HelloWorld.java

```

#### 2. Declaring a class

Your Java file should only contain one **class**. A class must have the same name as the file (but without the file extension, obviously) and it is declared as follows:

```java
class ClassName {

}

```

In the above example, `ClassName` will need to be replaced by the actual name of our class; namely `HelloWorld`.

#### 3. The main() method

In its current form, this class will be of no use to you. It is lacking an **entry point** which is required in order to be able to carry out a series of actions in your code.

This entry point takes the form of the **main()** method. Inside the brackets of the `HelloWorld` class, go ahead and add the following code:

```java
public static void main(String[] args) {
// display Hello World! in the terminal
}

```

We will break down the syntax of this method later. For now, just go ahead and use it as it is.

#### 4. Posting a message

As it stands, your _main()_ method doesn’t do anything. You want to change this and get it to display a message for you containing the following (highly original) words: "Hello World!".

To do this, go ahead and add the following snippet of code in the terminal, just underneath the comment `// display Hello World!`:

```java
System.out.println("Hello World!");

```

> A comment is a line of code that is ignored and not executed by the program. In Java, you can write comments in two different ways:
either in-line, by adding two forward slashes (`//`) at the start of the line
or across several lines, by adding these characters: `/*` right before the start of the comment and these characters: `*/` right after the end of the comment

#### 5. Indentation

The last step before you run your program is checking if you have properly indented your code!

Unlike with _Python_, when it comes to Java, proper indentation is not necessarily required to successfully compile your code. However, it does make your code easier for humans to read, and since you will probably have to work together with other human beings, that's a really good thing!

"Indenting" is the process of aligning and pushing lines of code across the horizontal axis to make them easier to look at and understand.

The two main rules are as follows:

- if you open a bracket, the next line should be indented to the right by pressing the tab key (or by using four spaces).

- if you close a bracket, the next line should be less indented and one tab (or four spaces) should be removed.

Let's look at an example:

```java
class ClassName {

public static void main(String[] args) {
// do stuff
System.out.println("Awesome!");
}
}

```

> As you can see in the above example, after a class has been declared, two lines should be skipped for the purpose of improved readability.

```resource
https://www.baeldung.com/java-main-method
# Java main Method Explained
```

### Compiling

If everything has gone well up until this point, you should have the following code written inside your class:

```java
class HelloWorld {

public static void main(String[] args) {
// display Hello World! in the terminal
System.out.println("Hello World!");
}
}

```

Because Java is a **compiled** language, and it cannot be executed by the computer as is, we have to use a tool to convert this language into _bytecode_.

A program that is compiled in Java cannot be directly executed by the computer's processor, but can be executed by the _JVM_ (Java Virtual Machine). The advantage of this system is that once the code had been compiled into _bytecode_ it can then be executed on all kinds of different machines and operating systems, without needing to be modified.

Imagine the _JVM_ as a multilingual translator, who takes care of explaining your program to any machine that might run it.

So now you can compile your HelloWorld class using the **javac** tool, which you installed previously when you downloaded the _JDK_.

The command to compile a Java class is as follows:

```Bash
cd JavaProjects/JavaIntro
javac ClassName.java

```

In the command above, you will have to replace “ClassName” placeholder with the actual name of your file.

If everything goes well, you should get a message that begins with the word **done**. However, if you do get an error message, check it carefully to uncover the cause and correct the problem:

- is the file correctly named?

- did you remember to re-save the file after you added to it?

- did you execute the command from the same location where the class is saved?

- have you made a copy and paste error (scroll back up to the top of the page to double check)?

- is javac installed properly?

> If after all this, the program still doesn't compile, seek out help, and ask your trainer if you’re really stuck.

Looking at the contents of your folder, you should find there is a new file called `HelloWorld.class`. This is the compiled file! If you take a look at its contents, you will see that it is not really readable by humans. That’s because this file contains the _bytecode_, which will be run by the _JVM_!

```resource
https://www.quora.com/What-is-Java-bytecode
# What is Java bytecode?
```

```resource
https://www.dummies.com/programming/java/how-to-use-the-javac-command/
# How to use javac command
```

### Executing

All your hard work in this quest is about to pay off! In order to start to reap the fruits of your labour, you will have to execute your code in the _JRE_, using the **java** command like this:

```Bash
java ClassName

```

Please be aware that you need to execute this command using only the class name and not the name of the file (so leaving out the _.java_ extension)!

If everything has gone according to plan, you should see that the program has returned "Hello World!” in the terminal.

In the previous section, we discovered how our _bytecode_ was compiled into the `HelloWorld.class` file, which was not able to be read by humans. If you are interested in understanding more about how the _JVM_ works, I recommend reading the resources below.

These resources also cover the use of the **javap** command, which allows you to "decompile" a program in order to view the contents of the compiled code in a more understandable format, in order to understand how it will be read by the machine.

You can try it out on your compiled code by typing the following:

```Bash
javap -c HelloWorld.class

```

It might be overwhelming at first glance, but the output contains comments which explain in detail what each line does. Don't worry if you don't understand everything, it's definitely not necessary for your future as a programmer to do so!

```resource
https://www.cubrid.org/blog/3826357
# Understanding JVM Internals
```

## Challenge

### Create your own script

1. Create a new folder in `JavaProjects`, named `NoticeMe`.
1. In the `NoticeMe` folder, create a `Senpai.java` file.
1. Declare a `Senpai` class and include a _main()_ method, as shown in the quest.
1. Within your _main()_ method, write some code that will display the text "Notice me Senpai".
1. Compile and execute your code to ensure that it works correctly.
1. Copy your code into a Github **Gist** and include the `Senpai.java` in the solution.

### Validation criterias

- Your file should be named `Senpai.java` and include a class called `Senpai`.
- Your class must compile without throwing error messages.
- When your compiled class is executed, a message reading: "Notice me Senpai" appears in the terminal.