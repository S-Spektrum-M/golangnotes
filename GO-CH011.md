# CH 11: Interfaces
"Interface types express generalizations or abstractions 
about the behaviors of other types." (Kernighan and Donovan, 171)

In go interfaces are satisfied implicitly. This means that there is no need 
to declare all interfaces a concrete type satisfies.

Interfaces are special abstract types where you don't know its values 
but you do know what it can do.

## Declaration
```go
type myInterface interface {
	myMethodName (myArg int) (myReturn, error)
	// No implementation
}
```
Once all methods are implemented by a concrete type it is considered an
instance of that interface.
## Interface Embedding
```go
package io
type Reader interface {
	Read(p []byte) (n int, err error)
}

type Writer interface {
	Write(p []byte) (n int, err error)
}

type Closer interface {
	Close() error
}
type ReadWriter interface {
	Reader
	Writer
}

type ReadWriteCloser interface {
	Reader
	Writer
	Closer
}
```
This combines the interfaces to create composite interfaces

This can also be done as such:
```go
package io
type ReadWriter interface {
	Read(p []byte) (n int, err error)
	Write()
}

type ReadWriteCloser interface {
	ReadWriter
	Close() error
}
```
This foregoes the need to create other interfaces.

## Interface Satisfaction
A type satisfies an interface if it contains all the methods the interface requires
```go
var w io.Writer			// Requires Write method
w = os.Stdout			// OK: os.File has Write method
w = new(bytes.Buffer)	// OK: bytes.Buffer has Write method
w = time.Second			// Compile Err: time.duration doesn't have Write method

var rwc io.ReadWriteCloser	// Requires Write method
rwc = os.Stdout				// OK: os.File has Write method
rwc = new(bytes.Buffer)		// Compile Err: bytes.Buffer doesn't have Close method

```
This also applies when the right hand side is an interface
```go
w = rwc		// OK: rwc has Write method
rwc = w		// Compile Err: w lacks Close and Read methods
```

If a concrete type has more methods than the interface that wraps it the 
other methods may not be used. 

### Empty interfaces
Since empty interfaces have no methods we can all values satisfy it.
This allows us to assign any value to it.
```go
var any interface{}
any = true
any = 12.34 
any = "hello"
```

## Type Assertion
A type assertion is a operation for an interface value. It follows the 
following syntax.

``x.(t)`` Where x is a expression of an interface type and T is the asserted type

### Concrete Asserted Types
```go
var a interface{}
a = 1
fmt.Printf("%v", a.(int))
```
### Dynamic Asserted Types

## Links
Previous: [[GO-CH010]]
Next: [[GO-CH012]]
This is a set of notes on #Golang