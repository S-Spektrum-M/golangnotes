# CH4: Arrays and Slices
1. Arrays
	1. Collection of items w/ same type
	2. Fixed size
	3. Declaration styles
	```go
	a := [3]int{1, 2, 3} 		
	a := [...]int{1, 2, 3} 		
	var a [3]int
	```
	4. 0 indexed
	5. ```len``` function returns size of array
	6. Copies refer to different underlying data
2. Slices
	1. Backed by an array
	2. Slice existing array or slice
	3. Literal style
	4. via make function:
	```go
	a := make([]int, 10) //Slice w/ capacity and length 10
	a := make([]int, 10, 100) //Slice w/ length 10 and capacity 100
	```
	5. ```len``` function returns length of slice.
	6. ```cap``` function return capacity of underlying array.
	7. ```append``` function to add elements to a slice.
		1. May cause expensive copy operation if underlying array too small.
	8. Copies refer to the same underlying array.
	
## Links
Previous: [[GO-CH003]]
Next: [[GO-CH005]]
This is a set of notes on #Golang