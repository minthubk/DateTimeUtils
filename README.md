# DateTimeUtils 

This library is a package of functions that let you manipulate objects and or java date string. it combine the most common functions used when managing dates under android, such as converting a mysql /sqlLite date to a Date object and vis-versa etc.

This library is available under the [MIT License](http://www.opensource.org/licenses/mit-license.php).



## Usage

The DateTimeUtils library is available from [JitPack](https://jitpack.io/#thunder413/NetRequest/1.2).

First add JitPack dependency line in your project `build.gradle` file:

```xml
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```

And then simply add the following line to the `dependencies` section of your app module `build.gradle` file:

```groovy
compile 'com.github.thunder413:DateTimeUtils:1.3'
```

Javadocs are available [here](http://https://github.com/thunder413/NetRequest/apidocs/index.html).

## Examples

### formatDate

``formatDate`` is a method that allow you to convert ``date object`` to ``string`` or vice-versa

#### Date string to Date object 

```java
// MySQL/SQLite dateTime example
Date date = DateTimeUtils.formatDate("2017-06-13 04:14:49");
// Or also with / separator
Date date = DateTimeUtils.formatDate("2017/06/13 04:14:49");
// MySQL/SQLite date example
Date date = DateTimeUtils.formatDate("2017-06-13");
// Or also with / separator
Date date = DateTimeUtils.formatDate("2017/06/13");
```
#### Date object to date string MySQL/SQLite

```java
String date = DateTimeUtils.formatDate(new Date());
```

### formatWithStyle

``formatWithStyle``  allow to parse date into localized format using most common style

#### Date object to localized date

```java
DateTimeUtils.formatWithStyle(new Date(), DateTimeStyle.FULL); // Tuesday, June 13, 2017
DateTimeUtils.formatWithStyle(new Date(), DateTimeStyle.LONG); // June 13, 2017
DateTimeUtils.formatWithStyle(new Date(), DateTimeStyle.MEDIUM); // Jun 13, 2017
DateTimeUtils.formatWithStyle(new Date(), DateTimeStyle.SHORT); // 06/13/17
```

#### Date string to localized date

```java
DateTimeUtils.formatWithStyle("2017-06-13", DateTimeStyle.FULL); // Tuesday, June 13, 2017
DateTimeUtils.formatWithStyle("2017-06-13", DateTimeStyle.LONG); // June 13, 2017
DateTimeUtils.formatWithStyle("2017-06-13", DateTimeStyle.MEDIUM); // Jun 13, 2017
DateTimeUtils.formatWithStyle("2017-06-13", DateTimeStyle.SHORT); // 06/13/17
```

### formatWithPattern

``formatWithPattern`` allow to define your own parse pattern following  ``SimpleDateFormat`` scheme

#### Date string as source

```jade
DateTimeUtils.formatWithPattern("2017-06-13", "EEEE, MMMM dd, yyyy"); // Tuesday, June 13, 2017
```

#### Date object as source

```java
DateTimeUtils.formatWithPattern(new Date(), "EEEE, MMMM dd, yyyy"); // Tuesday, June 13, 2017
```

 ### isToday

``isToday`` Tell whether or not a given date is today date 

```java
// Date object as source
boolean state = DateTimeUtils.isToday(new Date());
// Date String as source
boolean state = DateTimeUtils.isToday("2017-06-15 04:14:49");
```

### isYesterday

``isYesterday`` Tell whether or not a given date is yesterday date 

```java
// Date object as source
boolean state = DateTimeUtils.isYesterday(new Date());
// Date String as source
boolean state = DateTimeUtils.isYestrday("2017-06-15 04:14:49");
```

### getDateDiff

``getDateDiff`` give you the difference between two date in days, hours, minutes, seconds or milliseconds ``DateTimeUnits`` 

```java

```

