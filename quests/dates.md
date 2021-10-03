As a developer, you'll often have to work with dates: sometimes you'll have to modify them, or change their format (European, American dates...), or deal with different time zones.Java contains several classes to make your life easier when managing dates: this quest will allow you to discover some of them.

#### Objectives

- Formatting a `Date` object with `SimpleDateFormat`

- Using a `Calendar`

### Date and SimpleDateFormat

If you want to work with dates, the class`Date` is the first one you're gonna meet in tutorials. However, it is not necessarily the most practical, nor the most complete.

It remains practical if you want to create a date that is initialized at the moment of instantiation:

```java
Date current = new Date(); // Represents the time at which the Date object is allocated

```

> You're gonna need to import the library:`java.util.Date`

If you want to display the date in a specific format, you will need the class`SimpleDateFormat` :

```java
SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
Date current = new Date();
System.out.println(sdf.format(current)); // 22/03/2019 15:15:54

```

> You're gonna need to import the library:`java.text.SimpleDateFormat`

The advantage of`SimpleDateFormat`is that it also allows the reverse operation: if you have defined a format, you can easily get the object`Date` correspondent:

```java
SimpleDateFormat format = new SimpleDateFormat("dd/MM/yyyy");
try {
    Date birthday = format.parse("01/01/1970");
    System.out.println(birthday); // Thu Jan 01 00:00:00 CET 1970
} catch (ParseException e) {
    e.printStackTrace();
}

```

It is mandatory to use`try` and`catch` in order to recover from possible errors: when using the method`parse`If the date does not exist or is incorrectly formatted, it is possible that the date does not exist or is incorrectly formatted. Don't worry, you'll see the use of exceptions later.

> You're gonna need to import the library:`java.text.ParseException`

```resource
http://tutorials.jenkov.com/java-date-time/parsing-formatting-dates.html
# Parsing and Formatting Dates in Java
```

### Calendar

The class`Calendar` is super useful when you want to create a date from a day, a month and a year, or do operations on it (add days for example).

By default, an instance of`Calendar` will be created on today's date:

```java
Calendar c = Calendar.getInstance();

```

> You're gonna need to import the library:`java.util.Calendar`

You can then retrieve the data from the object using these methods:

```java
int year = c.get(Calendar.YEAR);
int month = c.get(Calendar.MONTH); // Be careful: January = 0, December = 11
int dayOfMonth = c.get(Calendar.DAY_OF_MONTH);
int dayOfWeek = c.get(Calendar.DAY_OF_WEEK);

```

> Attention: the recovered month starts at 0 for January! The day starts at 1.

You'll find all the methods of the class`Calendar` as a resource.

It is not mandatory to create an object on the current date. For example, you can use the class`GregorianCalendar` to set a specific date:

```java
Calendar c = new GregorianCalendar(2019, 3, 22, 13, 30, 00);

```

> You're gonna need to import the library:`java.util.GregorianCalendar`

If you want to format a date contained in an instance of`Calendar`you're also going to use`SimpleDateFormat`.
Convert the object`Calendar` at`Date` by means of`getTime` :

```java
SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss"); 
Calendar c = new GregorianCalendar(2019, 3, 22, 13, 30, 00);
Date d = c.getTime();
System.out.println(sdf.format(d)); // 22/04/2019 13:30:00

```

```resource
https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html
# Class Calendar
```

## Challenge
### Date formatting

In order to practice creating dates, first of all[make a](https://github.com/WildCodeSchool/quest-java-date)[Fork](https://github.com/WildCodeSchool/quest-java-date)[ of the following deposit](https://github.com/WildCodeSchool/quest-java-date) then clone it locally.
> Be sure to do a_Fork_or you won't be able to grow anything !
1. Once the project is locally recovered, open the file`TestDate.java`
1. You will see that it already contains code to retrieve three data: a day, a month and a year.
1. Use this data and your knowledge gained in the quest to calculate the following information:

A date formatted as "month-day-year", ex:`04-22-2019`The day of the week corresponding to the date, ex:`2`
1. Concatenates texts_"The date is: "_ and_"The day of week is:"_ in front of the corresponding data, before displaying them in the terminal.

Expected outcome :

```bash
$ Please fill a day (1-31) :
$ 22
$ Please fill a month (1-12) :
$ 4
$ Please fill a year :
$ 2019
$ The date is : 04-22-2019
$ The day of week is : 2

```

### Validation criterias
- To the compilation and execution of`TestDate`If you click on the "Save" button, a result corresponding to the expected one appears.
- The "month-day-year" format is respected.
- The number of the month is the one entered.
