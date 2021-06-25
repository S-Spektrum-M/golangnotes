# CH 9: Pointers
& = address of
\* = value of
```go
var a int = 42
var b *int = &a
fmt.Println(a, *b) 	// 42 42
a = 27
fmt.Println(a, *b) 	// 27 27
*b = 14
fmt.Println(a, *b) 	// 14 14
var b *int
fmt.Println(b)		// <nil>
```
The zero value of a pointer is ```nil```
```go
```
## Links
Previous: [[GO-CH008]]
Next: [[GO-CH010]]
This is a set of notes on #Golang