# CH 10: Functions
## Declaration
```go
func myFunc(myParam1 myType) myReturnType {
}
```

## Pointers
```go
package main

import (
	"fmt"
)

func swap(a, b int) {
	tmp := a
	a = b
	b = tmp
}
func main() {
	a := 5
	b := 10
	fmt.Printf("A: %v\n",a)	// 5
	fmt.Printf("B: %v\n",b) // 10
	swap(a, b)
	fmt.Printf("A: %v\n",a)	// 5
	fmt.Printf("B: %v\n",b)	// 10
}
```
This doesn't work because a copy of ```a``` and ```b``` are
sent to ```swap``` and then swapped.
```go
package main

import (
	"fmt"
)

func swap(a, b *int) {
	tmp := *a
	*a = *b
	*b = tmp
}
func main() {
	a := 5
	b := 10
	fmt.Printf("A: %v\n",a)	// 5
	fmt.Printf("B: %v\n",b) // 10
	swap(a, b)
	fmt.Printf("A: %v\n",a)	// 10
	fmt.Printf("B: %v\n",b)	// 5
}
```
This works since the pointer is passed rather than the value.

## Variatic Parameters
```go
package main

import(
	"fmt"
)

func main() {
	sum(1,2,3,4,5) // "The sum is 15"
}

func sum(values ...int) {
	// Takes in variable number of ints
	result := 0
	for _, v := range values {
		result += v
	}
	fmt.Println("The sum is", result)
}
```
You can only have one and the must be at the end.

## Return
```go
package main

import(
	"fmt"
)

func main() {
	fmt.Printf("The sum is %d \n", sum(1,2,3,4,5)) // "The sum is 15"
}

func sum(values ...int) int {
	// Takes in variable number of ints
	result := 0
	for _, v := range values {
		result += v
	}
	return result
}
```
```result``` is returned to ```main()```

## Returning Errors
```go
package main

import "fmt"

func main() {
	result, err := divide(5.0, 0.0)
	if (err != nil) {
		fmt.Println(err)		
	}
	fmt.Println(result)
}

func divide(a, b float64) (float64, error){
	if (b == 0.0) {
		return 0.0, fmt.Errorf("Cannot divide by zero")
	}
	return a/b, nil
}

```

## Methods
```go
package main

import (
    "fmt"
)

func main() {
    p := person{
        name: "A person",
        age: 19,
        height: 76,
        weight: 98,
    }
    p.printDetails()
}

type person struct {
    name string
    age int8
    height float32
    weight float32
}

func (p person) printDetails() {
    fmt.Printf("Name: %v\n", p.name)
    fmt.Printf("Age: %v\n", p.age)
    fmt.Printf("Height: %v\n", p.height)
    fmt.Printf("Weight: %v\n", p.weight)
}
```

## Links
Previous: [[GO-CH009]]
Next: [[GO-CH011]]
This is a set of notes on #Golang