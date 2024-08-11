- Java is Statically typed language
- It is also a strongly typed
### ***TYPES OF DATA TYPES:***  ###

1. **Primitive Data Type**
	- Int
	- Char
	- Float
	- Double
	- Boolean
	- Byte
	- Long
	- Short
	

| **TYPE**  |     **DESCRIPTION**      | **DEFAULT** | **SIZE<br>*(IN byts)* ** |        **EXAMPLE<br>LITERALS**        |                          **RANGE OF VALUES**                           |
| :-------: | :----------------------: | :---------: | :----------------------: | :-----------------------------------: | :--------------------------------------------------------------------: |
|   `int`   | two's complement integer |      0      |            4             |          -2<br>1<br>0<br>56           |            -2,147,483,648 <br><br>to <br><br>2,147,483,647             |
|  `char`   |   Unicode<br>charcter    |   \u0000    |            2             |           'a'<br>'B'<br>'@'           |       characters representation of ASCII values<br><br>0 to 255        |
|  `float`  | IEEE 754 floating point  |     0.0     |            4             | 1.23e100f -1.23e-100f<br>.3f<br>3.14F |                         upto 7 decimal digits                          |
| `double`  | IEEE 754 floating point  |     0.0     |            8             | 1.23456e300d  -123456e-300d <br>1e1d  |                         upto 16 decimal digits                         |
| `boolean` |    `true` or `false`     |    false    |            1             |              true, false              |                              true, false                               |
|  `long`   | two's complement integer |      0      |            8             |     -2L<br>-1L<br>0L<br>1L<br>2L      | -9,223,372,036,854,775,808 <br><br>to<br><br>9,223,372,036,854,775,807 |
|  `short`  | two's complement integer |      0      |            2             |                (none)                 |                           -32,768 to 32,767                            |
|  `byte`   | two's complement integer |      0      |            1             |                (none)                 |                              -128 to 127                               |

	
2. **Non Primitive Data Type or Object Data type**
	- String
	- Array
	- Class
	- Object
	- Interface

![[../../IMAGES/Pasted image 20240810220955.png]]
### Primitive Data Type: ###

1. INTEGER:
	- Syntax:
		- `int intVar;`

2. CHARACTER:
	- The char data type is a single 16-bit Unicode character with the size of `2 bytes` (16 bits).
	>[!Tip]
	>WHY IS SIZE OF CHAR IS 2BYTE IN JAVA?
	>	-  Other languages like `C/C++ use only ASCII characters`, and `to represent all ASCII characters 8 bits is enough`. But `Java uses the Unicode system` not the ASCII code System and `to represent the Unicode system 8 bits is not enough` to represent all characters so Java uses 2 bytes for characters.
	>	- **Unicode** defines a fully `international character set` that `can represent most of the world’s written languages.` It is a unification of dozens of character sets, such as `Latin, Greek, Cyrillic, Katakana, Arabic,` and many more.
	  
	- Syntax
		- `char charVar;`

3. FLOAT:
	- `single-precision` 32-bit IEEE 754 floating-point.
	>	[!Tip]
	>		- Use a `float (instead of double)` if you need to `save memory in large arrays of floating-point numbers`.
	
	- Syntax:
		- `float floatVar;`

4. DOUBLE:
	- `Double-precision` 32-bit IEEE 754 floating-point.
	- Syntax:
		- `double DoubleVar;`

5.  BOOLEAN:
	- The `Boolean` data type` represents a logical value` that can be either `true` or `false`.
	- Values of type `Boolean` are `not implicitly or explicitly converted to any other type` (with casts).
	- Syntax:
		- `boolean BoolVar;`

6. LONG:
	- It is useful for those occasions where an int type is not large enough to hold the desired value.
	- Syntax:
		- `Long longVar;`

7. SHORT:
	- use a short to` save memory in large arrays`, in situations where the `memory savings actually matters`. 
	- Syntax:
		- `short shortVar;`

8. BYTE:
	- The byte data type is `useful for saving memory in large arrays`.
	- Syntax:
		- `byte byteVar;`

```java

// Class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating and initializing custom character
        char a = 'G';

        // Integer data type is generally
        // used for numeric values
        int i = 89;

        // use byte and short
        // if memory is a constraint
        byte b = 4;

        // this will give error as number is
        // larger than byte range
        // byte b1 = 7888888955;

        short s = 56;

        // this will give error as number is
        // larger than short range
        // short s1 = 87878787878;

        // by default fraction value
        // is double in java
        double d = 4.355453532;

        // for float use 'f' as suffix as standard
        float f = 4.7333434f;

        // need to hold big range of numbers then we need
        // this data type
        long l = 12121;

        System.out.println("char: " + a);
        System.out.println("integer: " + i);
        System.out.println("byte: " + b);
        System.out.println("short: " + s);
        System.out.println("float: " + f);
        System.out.println("double: " + d);
        System.out.println("long: " + l);
    }
}

OUTPUT:
char: G
integer: 89
byte: 4
short: 56
float: 4.7333436
double: 4.355453532
long: 12121

```

### Non Primitive or Reference Data Type: ###

>[!info]
>The Reference Data Types will `contain a memory address of variable values` because the reference types `won’t store the variable value directly in memory.
`

1. **Strings:**
   - Strings are `Array of Characters.`
   - The difference between a character array and a string in Java is, that the `string is designed to hold a sequence of characters in a single variable` whereas, `a character array is a collection of separate char-type entities`.
   - Unlike C/C++, `Java strings are not terminated with a null character`.
   >[!example]
   >- Character Array: `char[] charArray = {'H', 'e', 'l', 'l', 'o'}`;
   >- String : String `str = "Hello"`;

- Syntax: `<String_Type> <string_variable> = “<sequence_of_string>”;` 
>[!example]
>- Declare String without using new operator: `String s = "GeeksforGeeks";`
>- Declare String using new operator : `String s1 = new String("GeeksforGeeks");`
