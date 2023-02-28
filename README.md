# Java Cheet Sheet

## Table of Contents

1. [Variable & Types](#variable--types)
2. [Stream API](#stream-api)
3. [lambda expression](#lambda-expression)
4. [Enum](#enum)
5. [Java Execution Process](#java-execution-process)
6. [Setup Eclipse for JDK](#setup-eclipse-for-jdk)

## Variable & Types
**Variable** is container where we can temporary store single data somewhere in computer memory.
Type of Variable:
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