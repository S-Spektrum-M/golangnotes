# CH 2: Primitives

## Types of primitives in go
1. Boolean type
2. Numeric Types
	* Integers
	* Floating Point
	* Complex Numbers
3. Text Types 
## Boolean
Booleans have two states: ```true``` and ```false```
The default state of a boolean is ```false```.
```go
var a bool
fmt.printf("%v",a) 		// false
```
```go
var a bool = true
fmt.printf("%v, %T",a,a) // true, bool
var b bool = false
fmt.printf("%v, %T",b,b) // false, bool
```
Booleans can be used to store the result of logical checks
```go
a := (1 == 2) // A == false 
```
## Numeric types
The default value of all numeric types is 0.
```go
var a int
fmt.printf("%v, %T \n",a,a) // 0, int
var b float32
fmt.printf("%v, %T \n",b,b) // 0, float32

```
### Integers
There are many types of integers in go.

|Name|Size|Range|signed?|
|-|-|-|-|
|int|varies|varies|yes|
|int8|8 bit|\[-128, 127\]|yes|
|int16|16 bit|\[-32_768, 32_767\]|yes|
|int32|32 bit|\[-2_147_483_648, 2_147_483_647\]|yes|
|int64|64 bit|\[-9_223_372_036_854_775_808, 9_223_372_036_854_775_807\]|yes|
|uint8|8 bit|\[0, 255\]|no|
|uint16|16 bit|\[0,65_535\]|no|
|uint32|32 bit|\[0, 4_294_967_295\]|no|

#### Declarations:
```go
var a int
var b int8
var c int16
var d int32
var e int64
var f uint8
var g uint16
var h uint32
```

#### Operators on integers
##### Math operators:
```go
a := 8
b := 3

fmt.Println(a + b)	// addition results in 11
fmt.Println(a - b)	// subtraction results in 5
fmt.Println(a / b)	// int division results in 2 
fmt.Println(a * b)	// muliplication results in 24
fmt.Println(a % b)	// modulo(remainder) results in 2
```

##### Bitwise logical operators:
```go
a := 10 			// 1010
b := 3  			// 0011

fmt.Println(a & b)	// and operator results in 2 
fmt.Println(a | b)	// or operator results in 11
fmt.Println(a ^ b)	// xor operator results in 9 
fmt.Println(a &^ b)	// nand results in 8
```

##### Bitshift operators:
```go
a := 8

fmt.Println(a << 3)	// left bitshift on 8 by 3 bits results in 8 * (2^3) = 64 
fmt.Println(a >> 3)	// right bitshift on 8 by 3 bits results in 8 / (2^3) = 1 
```

### Floats
Go uses the [IEE 754](https://en.wikipedia.org/wiki/IEEE_754) standard for floats.
In go there are two types of floats ```float32``` and ```float64```. 
They have 32 bit and 64 bit sizes respectively.
```go
var a float32 = 0.1
var b float64 = 0.2
```

#### Declaration
```go
	a := 3.14		// Standard Declaration
	b := 13.7E72 	// Exponent Form Declaration 
	c := 2.1e14		// Exponent Form Decleration
```

### Complex Numbers
There are two complex numbers in go ```complex64``` and ```complex128```.
```complex64``` is the sum of two ```float32```.
```complex128``` is the sum of two ```float64```.
#### Declaration
```go
var a complex64 = 1 + 2i
var b complex128 = 2 + 3i
var c complex128 = complex(1, 3)
fmt.Println(a) // (1 + 2i)
fmt.Println(b) // (2 + 3i)
```
To extract the real or imaginary component one can do the following:
```go
var a complex64 = 1 + 2i
fmt.Println(real(a)) // 1 
fmt.Println(imag(a)) // 2
```

## Text types
There are two text types in go ```string``` and  ```TODO```.

### String
Strings are immutable character arrays that are capable of storing any UTF-8 character.
#### Declaration
```go
s := "Hello, World"
var t string = "Hello, World"
```
Strings in go are character arrays so you can do the following:
```go
s := "Hello, World"
fmt.Println(s[0]) // 72
```
The code above works by printing the ASCII value of the 0th element in ```s```.

To print the real character one can do the following:
```go
s := "Hello, World"
fmt.Println(string(s[0]) // H
```
The code above works by typecasting the ASCII value of the 0th element in ```s``` to a string.

Since strings are immutable the following code is not allowed:
```go
s := "Hello, World"
s[0] = "A" // ILLEGAL
```
### Rune
Runes are like strings that store UTF-32 characters.

---
## Links
Previous: [[GO-CH1]]
Next: [[GO-CH3]]
This is a set of notes on #Golang