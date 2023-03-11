# Java Cheet Sheet

## Table of Contents

1. [Variable](#variable)
2. [Primitive vs Reference](#Primitive-vs-Reference)
3. [Implicit & Explicit Casting](#Implicit--Explicit-Casting)
4. [Scanner](#Scanner)
5. [Math & NumberFormat](#Math--NumberFormat)
6. [String](#String)
7. [Array](#Array)
8. [Collection Framework](#Collection-Framework)
8. [Stream API](#stream-api)
9. [lambda expression](#lambda-expression)
10. [Enum](#enum)
11. [Java Execution Process](#java-execution-process)
12. [Setup Eclipse for JDK](#setup-eclipse-for-jdk)

## Variable
**Variable** is container where we can temporary store single data somewhere in computer memory.
```java 
String txt = "hello world";
```
**Constant Variable** created by final keyword. As a convention, all letters of constant variable should be uppercase.
```java
final double PI = 3.14;
```
**Type of Variable:**
- Primitive Type - to store simple value
- Non-primitive / Reference Type - to store complex objects

|Type|Byte|Range|Example|
|-|-|-|-|
|`byte`|1|[-128, 127]|`byte age = 30;`|
|`short`|2|[-32k, 32k]|`short computerPrice = 2200;`|
|`int`|4|[-2B, 2B]|`int yearlySalary = 150000;`|
|`long`|8|more larger|`long likeCounts = 5_987_432_235L;`|
|`float`|4|6-7 decimal digits|`float ticketCost = 105.52F;`|
|`double`|8|15 decimal digits|`double yearlyCost = 540_235.458;`|
|`char`|2|A-Z|`char letter = 'B';`|
|`boolean`|1|true/false|`boolean isStudent = false;`|
**[⬆ back to top](#table-of-contents)**
## Primitive vs Reference
**Primitive:** 
- to store simple value like int, float, double, boolean
- it doesn't have any property/members
- no need to allocate and release memory explicitly. Memory allocated by JRE. <br/>
- **Copied by Value:** 
Always Primitive Data stored in different memory location, so it's independent. That means we change one, another one shouldn't be affected.
```java
byte a = 1; // 1
byte b = a; // 1
```
<img src="img/primitive_1.png">

```java
byte a = 1; // 1
byte b = a; // 1
a = 2; // 2
```
<img src="img/primitive_2.png">

**Reference/Non-Primitive:** 
- to store complex value like Date, Array, String.
- most of the time, it has some properties/members
- need to allocate the memory by `new` keyword and JRE automitacally release the memory.<br/>  
- **Copied by Reference:**
When we try to store reference type data into another variable, it stores the address of reference object instead of reference object. That means if we change one ref of object property, another one should be affected. 

```java
Point point1 = new Point(10, 20);
Point point2 = point1;

System.out.println(point1.x); // 10
System.out.println(point2.x); // 10
```
<img src="img/reference_1.jpg">

```java
Point point1 = new Point(10, 20);
Point point2 = point1;
point1.x = 15;

System.out.println(point1.x); // 15
System.out.println(point2.x); // 15
```
<img src="img/reference_2.jpg">

**[⬆ back to top](#table-of-contents)**
## Implicit & Explicit Casting
**Implicit Casting:** if we convert/store a value into different type of data which is taking bigger memory space then before, known as implicit/automatic casting.
```java
byte age = 45;
int ageOfMonth = age * 12;
System.out.println(ageOfMonth); // 540
```
> under the hood, java stores this age with anonymous int variable in somewhere in memory and copy that int value, then multiply with int 12. 
<br/>

**Explicit Casting:** Store bigger byte data into less byte data type.
```java
double monthlyCost = 4500.78;
int yearlyCost = (int) monthlyCost * 12;
System.out.println(yearlyCost); // 54000
```
Note: Covertion only possible with compatible data like `String` cann't be converted directly into `int`. if want to do that, need to convert `String` to `int` or `double` and so on first using `Integer.parseInt()`, `Double.parseDouble()`
**[⬆ back to top](#table-of-contents)**
## Scanner
```java
Scanner scanner = new Scanner(System.in);
		
System.out.print("Input your name: ");
String name = scanner.nextLine();
System.out.print("Input your age: ");
int age = scanner.nextInt();

// for String input
scanner.next() // return the token. token separated by space
scanner.nextLine() // return whole line 
// for other primitive input, there is individual method
scanner.nextByte();
scanner.nextShort();
scanner.nextInt();
scanner.nextLong();
scanner.nextFloat();
scanner.nextDouble();

scanner.hasNext();
```
**[⬆ back to top](#table-of-contents)**
## Math & NumberFormat
```java
Math.round(55.3F); // 55
Math.ceil(55.3F); // 56.0 - return as double
(int) Math.floor(55.3F); // 55 - return as double, so casting by int
Math.max(45, 78); // 78
Math.min(45, 78); // 45
Math.random(); // 0.8646041914172147
int number = (int) (Math.random() * 100); 
System.out.println(number); // 93
```
```java
// NumberFormat is a Abstract Class. It's a half bake cookie, not ready to eat. 
// That means, cann't possible to create object directly. So, creating object here following Factory approch
NumberFormat currency = NumberFormat.getCurrencyInstance();
System.out.println(currency.format(6588456.5057)); // $6,588,456.51
System.out.println(NumberFormat.getPercentInstance().format(0.1)); // 10%
```
**[⬆ back to top](#table-of-contents)**
## String 
Though `String` is reference type, there are two ways to create String instance -> one is `new` operator and another is String Literal. Since String is oftenly used, so there is a shorthand like literal and its standard as well.
> Note: Any methods, that modify string, always return a new String object, original String shouldn't be affected. Because in Java - String is Immutable. that means it's not changeable/mutable.
<br />

**Common String Methods**
```java
String str = "Hello World";

str.toUpperCase();
str.toLowerCase();
str.charAt(i);
str.contains("Hello");
str.equals("Hello World");
str.equalsIgnoreCase("hello world");
str.startsWith("Hello");
str.endsWith("World");
str.replace("Hello", "Dolly"); str.replaceAll("l", "L");
str.indexOf("W"); str.indexOf("Wor"); str.lastIndexOf("o"); 
str.isEmpty();
str.join(" ", list);
str.trim();
```
**Escape Sequence**
```java
// escape sequence using '\'
System.out.println("c:\\windows\\users\\john"); // c:\windows\users\john
System.out.println("Hello \"World\""); // Hello "World"
System.out.println("Hello \tWorld"); // Hello 	World
System.out.println("Hello \nWorld"); // for new line
```
**[⬆ back to top](#table-of-contents)**
## Array 
Array helps us to store more then one value but its length is fixed. That means, if we create an Array for five elements, we cann't store the six elements. 
**Single Dimension**
```java 
// older way
int[] nums = new int[5];
nums[0] = 1;
nums[1] = 2;
// by default array returns the string of its memory location
System.out.println(nums); // [I@75a1cd57 

// to see the String representation of an Array, need to use Arrays.toString(arrName)
System.out.println(Arrays.toString(nums));
// [1, 2, 0, 0, 0] - non-initialize value should be initialized by default value like int default value is 0
```
```java
// newer way (It's preferable, if we know the data before initializing)
int[] nums = {1, 2, 3, 4, 5};
System.out.println(Arrays.toString(nums)); // [1, 2, 3, 4, 5]
```
```java
nums.length; // to see the length
Arrays.sort(nums); // to sort 
```
**Multi Dimension**
```java 
// older way
int[][] nums = new int[2][2];
nums[0][0] = 1;
nums[0][1] = 2;
nums[0][0] = 3;
nums[1][1] = 4;
System.out.println(Arrays.deepToString(nums)); // [[3, 2], [0, 4]]

// newer way (It's preferable)
int[][] nums = {{1, 2}, {3, 4}};
```
**[⬆ back to top](#table-of-contents)**
## Stream API

**[⬆ back to top](#table-of-contents)**

## lambda expression

**[⬆ back to top](#table-of-contents)**

## Enum

**[⬆ back to top](#table-of-contents)**

## Java Execution Process
- **Compilation:** IDE takes help from Java Compiler which comes with JDK to compile Java code. Java Compiler converts Java Source Code `.java` file to Java Byte Code `.class` file. This Java Byte Code or `.class` file is platform independent. That means you can run this `.class` file in any machine if JRE is available there.

- **Execution:** To execute Java Byte Code/`.class` file, have to have JRE. JRE has Software Component named JVM. It converts Java Byte Code/`.class` to `Native Code`, so machine can understand. For this reason we can run/execute java code in any OS if machine has JRE, more specifically JVM.

**[⬆ back to top](#table-of-contents)**

## Setup Eclipse for JDK
 - Right click your project > properties
 - Select "Java Build Path" on left, then click on "Libraries" tab
 - Select "JRE System Library", click on "Edit" btn
 - Select "Altenate JRE", then click on "Installed JREs.." button
 - Select "Installed JREs", then click on "Add" button
 - Select "Standard VM", then click on "Next" button
 - Click on "Directory" button, then select your JDK home directory and click "Finish" button
 - Select JDK checkbox, then click "OK" button
 - Select "Alternate JRE", then select jdk from dropdown list and click "Finish" button
 - Click "Apply" button, then click "Ok" button
**others**
 - update maven project to get latest framework updates 
 - build project - run project as `Maven clean` and `Maven install`

**[⬆ back to top](#table-of-contents)**

## Templates/Snippet for Eclipse
 - Prepare/download template/snippet file as xml
 - In Eclipse, select Windows > Preferences
 - Expand "Cucumber" and then select "Template" file
 - Click "import"
 - Browse to the downloaded templates XML file and click "Open"
 - Click "Apply" and then "Ok"
```xml
<?xml version="1.0" encoding="UTF-8"?>
<templates>
    <template 
        autoinsert="true" 
        context="org.hello.natural.cucumber.Cucumber.Step" 
        deleted="false"
        description=""
        enabled="true"
        name="AID: Action with Inline Data">
        When I perform [ACTION_NAME] with NAME1 as "VALUE1", NAME2 as "VALUE2"
    </template>
    <template 
        autoinsert="true" 
        context="org.hello.natural.cucumber.Cucumber.Step" 
        deleted="false"
        description=""
        enabled="true"
        name="ALD: Action with Labeled Data">
        When I perform [ACTION_NAME] with [LABEL_Of_the_DATA]
    </template>
    <template 
        autoinsert="true" 
        context="org.hello.natural.cucumber.Cucumber.Step" 
        deleted="false"
        description=""
        enabled="true"
        name="AND: Action with No Data">
        When I perform [ACTION_NAME]
    </template>
    <template 
        autoinsert="true" 
        context="org.hello.natural.cucumber.Cucumber.Step" 
        deleted="false"
        description=""
        enabled="true"
        name="CFLD: Control Fill - Labeled Data">
        When I enter [Labeled_Data]
    </template>
    <template 
        autoinsert="true" 
        context="org.hello.natural.cucumber.Cucumber.Step" 
        deleted="false"
        description=""
        enabled="true"
        name="CAC: Control Action - Click">
        When I click LOGIN_BUTTON control
    </template>
    <template 
        autoinsert="true" 
        context="org.hello.natural.cucumber.Cucumber.Step" 
        deleted="false"
        description=""
        enabled="true"
        name="BSND: Browser - Start App with No Data">
        When I start [google] application
    </template>
    <template 
        autoinsert="true" 
        context="org.hello.natural.cucumber.Cucumber.Step" 
        deleted="false"
        description=""
        enabled="true"
        name="CVD: Control Verify - Disabled">
        Then I should verify that CONTROL_NAME is disabled
    </template>
</templates>
```