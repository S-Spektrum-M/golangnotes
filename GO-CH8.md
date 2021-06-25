# CH 8: Defer Panic Recover 

## Defer
1. Executes after function ends but before return
	This:
	```go
	func main() {
		fmt.Println("start")
		defer fmt.Println("middle")
		fmt.Println("end")
	}
	```
	Prints:
	```
	start
	end
	middle
	```
2. Last in first out order
	This:
	```go
	func main() {
		defer fmt.Println("start")
		defer fmt.Println("middle")
		defer fmt.Println("end")
	}
	```
	Prints:
	```
	end
	middle
	start
	```
3. If a function is deferred it takes its argument before the defer.
	This:
	 ```go
	 a := "start"
	 defer fmt.Println(a)
	 a = "end"
	 ```
	Prints: ```start```

## Panic
In case of error ```panic``` should be used.
Panics occur after deferred statements
```go
package main

import "os"

func main() {
    _, err := os.Create("/tmp/file")
    if err != nil {
        panic(err) // panics if an error is created
    }
}
```
## Recover
Manage the behavior of a panicking goroutine
Only useful in deferred functions
Current function will not attempt to continue.
Higher functions in call stack will.

## Links
Previous: [[GO-CH7]]
Next: [[GO-CH9]]
This is a set of notes on #Golang