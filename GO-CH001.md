# CH 1: Variables
Variables are essential to any language. They store data for access later. Go is no exception

## Go variable declaration

```go
var foo int
varName = 10
```
The format above follows a system of
```var varName varType```
```varName = value```

This can be truncated to:
```go
var foo int = 10
```
The format above follows a system of
```var varName varType = value```

However this can be made simpler still using the walrus operator.
The walrus operator is a different kind of assignment operator.
```go
foo := 10
```
This bypasses the need to specify the type or add the ```var``` keyword.

## Shadowing
The walrus operator also allows for shadowing.
```go
func main() {
    n := 0
    if true {
        n := 1
        n++
    }
    fmt.Println(n) // 0
}
```
The ```n := 1``` statement in line 4  re-declares n within that scope.

To get around this quirk one can do the following:
```go
import ( "fmt" )
func main() {
    n := 0
    if true {
        n = 1
        n++
    }
    fmt.Println(n) // 2
```
The ```=``` operator does not re-declare n but simply re-assigns n.

In go all declared variables must be used.
The following would be invalid code:
```go
package main

func main() {
	a := 0
}
```
This is invalid since ```a``` is declared but not used.
## Visibility
A lower case first letter implies a package scope variable.
```go
var variable int // package scope
```

An upper case first letter implies a variable to export.
```go
var Variable int // for export
```

There is also no private scope for variables in go.

## Type Conversions
In go type casting looks like such:
```destinationType(variable)```
```go
var i int = 10
float(i)
```
For strings one should use the package ```strconv```

## Naming Convention
The convention in go is to follow Camel Case.
The only exception is for acronyms which are capitalized.

Names should be as short as reasonably possible.
* Longer Names for Longer living variable

---
## Links
Next: [[GO-CH002]]
This is a set of notes on #Golang
