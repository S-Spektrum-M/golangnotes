# CH 7: Loops
## For loops
1. Simple loops
	```go
	for i := 0; i < 100; i++ {
		fmt.Printf("%d \n", i) // print all numbers on [0-100) 
	}
	```
2. Exiting early
	```go
	break
	continue
	goto
	```
3. looping over collections
	1. Arrays, Slices, Maps, Strings, Channels
	```go
	a := []string{"Foo", "Bar"}
	for i, s := range a {
    	fmt.Println(i, s)
	}
	```

## Links
Previous: [[GO-CH6]]
Next: [[GO-CH8]]
This is a set of notes on #Golang