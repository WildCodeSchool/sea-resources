Quests

## Introduction to Java Generics

We already created at least one simple List for a specific Class ourself for a start although Java already provides classes for this purpose. At the time, the authors of the List classes provided by Java were written, the programmers could not know about the classes that their list will be used for. Since every class is derived from java.lang.Object, the first versions of Java simply used that class to represent the items in the List. This imposes some problems that Java generics solve.

![Tiger](https://www.publicdomainpictures.net/pictures/220000/velka/tiger-1492874115lfH.jpg)

The first versions of Java did not include generics. In fact, a similar approach used in the C++ language called templates, was explicitly rejected because it was thought to add unnecessary complexity to the Java language. Generics where introduced with Java 1.5 or short Java 5 codenamed 'Tiger' in September 2004.

## 🤓 By the end of this quest, you will:

✅ Understand why Generics are used
✅ Realize the limitations and challenges when using Generics

- - -

## 👉 Why we need generics

Take a simple list as outlined belowe

```java
public class FixedSizeList {
    private List<Object> items = new ArrayList<>();

    public void add(Object object) { /* ... */ }
    public Object get(int index) { /* ... */ }

}
```

As you can see, the `add()` method of this list accepts every type of Object, since every type of Object is derived from java.lang.Object. This makes our list into a general purpose container.

Now have a look at the `get()` method. When you want to access an item that you put into this list, the declaration has a return type of `Object`. It is impossible to know what the concrete type of the returned value is. The only, least common denominator, that is clear is, that the returend value is a `java.lang.Object` since every class is derived from this class in Java.

To solve this problem, you could use a cast to the concrete class

```java
    // ...
    Apple apple1 = new Apple();

    fixedSizedList.add(apple1);

    Object result = fixedSizedList.get(0);

    Apple apple2 = (Apple) result;
```

This will work as long as you are 100% sure that the list will only ever have apples stored in the list. Remember that the `add()` method will accept anything so it is easy to put anything in the list.

To solve this problem, we would have to rewrite the `FixedSizeList` and use the `Apple` class for the items. Again, this will only solve the problems for Apples with a `FixedSizeListForApples`. For a pear, we would have to write another list and for every other class we would have to write yet another list class. This is a lot of work.

The solution to this problem is to make the type of the item more flexible by extending the language to allow parameters for the class declaration. These parameter work much like parameters for functions, but at a different level. They are used by the compiler at compile time while parameters for functions work at runtime.

To add a parameter for generics, the type parameter is added to the class in angle brackets

```java
    // ...
    class GenericFixedSizeList<T> { /* ... */ }
```

This is comparable to methods, where the type parameter is added in parenthesis

```java
    // ...
    void someMethod( Integer i) { /* ... */ }
```

There is a subtle difference here. The type parameter for generics has no type itself as it is clear that this is a type - or simply put, the name of a class.

Wherever the `java.lang.Object` type is used in the class itself, it has to be replaced with the generic type parameter name.

```java
public class FixedSizeList<T> {
    private List<T> items = /* ... */

    public void add(T object) { /* ... */ }
    public T get(int index) { /* ... */ }

}
```

To use this generic class for our Apple class, we have to provide the type parameter when we create a list.

```java
    FixedSizedList<Apple> fixedSizedList = new FixedSizedList<Apple>();
```

There is one important thing to keep in mind

> The type parameter is resolved at compile time.

To access the items in the generic list, we need no cast anymore.

```java
    // ...
    Apple apple1 = new Apple();

    fixedSizedList.add(apple);

    Apple apple2 = fixedSizedList.get(0);
```

Remember one thing like a mantra

> Cast is bad

Avoid them when you can - and in most cases you can.

## Conclusion

With this introduction to Java generics, we created a generic collection class that will save us a lot of time. Instead of writing a large number of specific classes for repetitive tasks, we can now write a single class and reuse that. There are several things to consider when using Java Generics. Look at the following Cheat Sheet for more details.

```ressource
Java Generics Cheat Sheet
https://www.jrebel.com/blog/java-generics-cheat-sheet
```

You can use your search engine to search for a cheat sheet that suits your preferences of color or that provides a more details description.

- - -

## 🔬 Exercise

You could use the **instanceof** operator to make a cast safe. Try to solve the problem for a non-generic list with three concrete types (Apple, Pear, Banana) and compare the result to the use of a generic class.

- - -

## ☝️ Summary

This quest introduced Java generics, the reasone to use them and a simple implementation 

- - -

## 💪 Challenge

The challenge for this quest is to implement the `FixedSizedList` with an `ArrayList<T>`. Make sure that the list never contains more then 5 elements.
Your class should implement these methods:

* `void add(T element)` adds an element to the list (or not if max size is reached)
* `void remove(T element)` removed an element from the list if it is contained
* `T get(int index)` returns the element at index `index`
* `int size()` returns the size of the list
* `boolean contains(T element)` checks if element is included in the list

You can post a gist with the `FixedSizeList` implementation and you unit tests.

Things to look for:

- Provide a test with null values
- Provide a test with adding more than 5 values
- Provide a test with removing an non-included element


## 🧐 Acceptance criteria

⭙ You wrote a generic list class
⭙ You have unit tests to check if things work
⭙ Your code is commited and pushed to your git server
