# Java Cheet Sheet

## Table of Contents

1. [Java Execution Process](#java-execution-process)
2. [Variable & Types](#variable--types)
1. [Stream API](#stream-api)
2. [lambda expression](#lambda-expression)
3. [Enum](#enum)

## Java Execution Process
- **Compilation:** IDE takes help from Java Compiler which comes with JDK to compile Java code. Java Compiler converts Java Source Code `.java` file to Java Byte Code `.class` file. This Java Byte Code or `.class` file is platform independent. That means you can run this `.class` file in any machine if JRE is available there.

- **Execution:** To execute Java Byte Code/`.class` file, have to have JRE. JRE has Software Component named JVM. It converts Java Byte Code/`.class` to `Native Code`, so machine can understand. For this reason we can run/execute java code in any OS if machine has JRE, more specifically JVM.

## Variable & Types
> Variable is container where we can temporary store single data somewhere in computer memory.
Variable is two types:
- Primitive Type - to store simple value
- Non-primitive / Reference Type - to store complex objects

**Primitive Types**
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


```java

```

## Stream API

**[⬆ back to top](#table-of-contents)**

## lambda expression

**[⬆ back to top](#table-of-contents)**

## Enum

**[⬆ back to top](#table-of-contents)**