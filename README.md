# The DriveScript 0.2 specification

This document is intended as a reference and a showcase of the DriveScript language.

*Table of Contents* 
1. Hello World
2. Primitive Datatypes
3. Reference Datatypes
4. Operators
5. Loops 
6. Functions 

## Hello World

The following codeblock is an example of a Hello World program. 
The code will print 

```
driveplan <MyFirstDrivePlan>{
   setup {}
   run {
        console.log("Hello world");
        drive( █ █ █ █ ) 
   }

}
```
## Primitive Datatypes

|category      | Minimum waarde| Maximum waarde  |default| example   |
|----          | ------------- |:-------------:  | -----:| -----:    |
|Integer       | col 3 is      | right-aligned   | 0 | $1600     |
|Floating point| col 2 is      | centered        |   $12 |   $12     |
|other          | -----| are neat        |    $1 |    $1     |
|slow down

## Reference Datatypes

|category       | Minimum waarde| Maximum waarde  |default| example   |
|----           | ------------- |:-------------:  | -----:| -----:    |
|Driveplan      | --      | right-aligned   | 0 | $1600     |
|Engine         | col 2 is      | centered        |   $12 |   $12     |
|Sensor         | -----| are neat        |    $1 |    $1     |
|slow down

## Operators

The drivescript language supports the following Algorithmic Operators

| Algorithmic | Description |
| --- | --- | 
| '+' | addition
| '-' | substraction
| '*' | multiplication
|'/' | division

The drivescript language supports the following Comparitive Operators.

They are mostly used within conditional expresions which are used in loops & for branching purposes. 
<table class="comparator">
<tr>
<td> Comparision </td> <td>  Description </td> <td>  usage example </td>
</tr>
<tr>
    <td> == </td>
    <td> equals </td>
    <td>

```
{
    int a = 5;
    DRIVE TILL (a == 10)
    {
        a = a + 1
        print(a)
    }
}
```
</td>    
</tr>
<tr>
    <td> != </td>
    <td> not equal </td>
    <td>

```
{ 
    IF (b == 4) {
          int a = 7;
          print(a);
    } ELSE {
          print(b);
    }
}
```
</td>    
</tr>

<tr>
    <td> > </td>
    <td> greater than </td>
    <td>

```
{ 
    IF (b > c) {
          print("Var b is larger than var c");
    } ELSE {
          print("Var c is larger than var b");
    }
}
```
</td>    
</tr>

<tr>
    <td> >= </td>
    <td> greater than or equal </td>
    <td>

```
{
    int b = 5;
    DRIVE TILL (b >= 200)
    {
        a = a + 10
        print(a)
    }
}
```
</td>    
</tr>

<tr>
    <td> < </td>
    <td> smaller than </td>
    <td>

```
{
    int b = 200;
    DRIVE TILL (b < 200)
    {
        b = b - 5
    }
}
```
</td>    
</tr>

<tr>
    <td> <= </td>
    <td> smaller than or equal </td>
    <td>

```
{ 
    Float d = 3.2
    Float e = 5.7
    IF (e > d) {
          print("var E is larger than var D);
    } ELSE {
         print("var D is larger than var E);
    }
}

```
</td>    
</tr>

</table>

## Loops & Branching

The drivescript compiler supports several types of loops. 
```
DRIVE TILL [CONDITION]
{
    [COMMANDS]
}
```
```
IF [CONDITION]
{
    [COMMANDS]
}
```
or with an else statement
```
IF [CONDITION]
{
    [COMMANDS]
} ELSE 
{
    [COMMANDS]  
}
```
## Use of Functions
A function has several characteristics

| Function property | Example |  Description |
| --- | --- | ---
| prefix | ф | used to indicate a Function declaration or Function call.
| return type | void, int, Float String| Datatype of return value
| function name | test() |
```
 Ф void test() {
  int a = 6;
  }
```
## Postfixes for Speed up / Slow down

The speed of a car may be used in a numeric way like:

```
speed(0)
```
I've also implemented a postfix to control the speed of the car. 
```
 LeftEngine █ █ █ █  can be used to speed the car up
 LeftEngine ▄ ▄ ▄    can be used to slow the car down
 Car █               Speeds everything up
 Car ▄               Slows everything down
```

## stopping

```
LeftEngine stop //Can be used to stop one of the engines.
FULL STOP works //like a emergency stop and end the program, similair to System.exit() in JAVA.
```

