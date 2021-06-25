# CH 3: Constants

## Declaration
```go
const myConst int = 42
```
This is similar to variable declaration but the ```var``` keyword is replaced with the ```const``` keyword.


## Enumerated Constants
```go
const (
	a = iota // 0
	b // 1
	c // 2
	d // 3
	e // 4
)
```
##  Notes
1. Immutable but can be shadowed.
2. Replaced by the compiler at compile time
	1. Value must be calculable at compile time
3.  Named like variables
	1.  PascalCase for exported constants.
	2.  camelCase for internal constants.
4. Typed constants work like immutable variables
	1. Can interoperate only with the same type
5. Untyped constants work like literals
	1. Can interoperate with similar types.
6. Enumerated constants
	1. Special symbol ```iota``` allows related constants to be created easily
	2. Iota starts at 0 in each ```const``` block and increments by one
	3. Watch out of constant values that match zero values for the variables.
7. Enumerated expressions
	1.  Operations that can be determined at compile time
		1.  Arithmetic
		2.  Bitwise operations
		3.  Bitshifts
		
## Links
Previous: [[GO-CH2]]
Next: [[GO-CH4]]
This is a set of notes on #Golang