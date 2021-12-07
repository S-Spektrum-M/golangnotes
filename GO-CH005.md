# CH 5: Maps and Structs

## Maps
1. Collection of value types that are accessed by keys
2. Created via literals or make function
3. Members accessed via key syntax
	```go
	 myMap["key"] = "value"
	```
4. Check for presence with 
	```go
	_, ok = myMap["key"]
	```
5. multiple assignments refer to same underlying data
	```go
        statePopulations := map[string]int {
				"California" : 39250017,
                "Texas" : 27862596,
                "Florida" : 20612439,
        }
        sp := statePopulations
        fmt.Printf("%p \n", statePopulations) 	// 0xc000080150
        fmt.Printf("%p \n", sp) 				// 0xc000080150
	}
	```
	
## Structs
1. Collection of disparate data types that describe a single topic
2. Keyed by named fields
3. Normally created as types, but can be anonymous
4. Value types
5. No inheritance but can use composition via embedding
6. Tags can be added to struct fields describe field.
7. 

## Links
Previous: [[GO-CH004]]
Next: [[GO-CH006]]
This is a set of notes on #Golang