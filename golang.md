# Golang
## Maps
```
// defines map: string -> string
capitals := make(map[string]string)

// defines map with at least capacity 5, reallocation occurs if size exceeds 5
capitals := make(map[string]string, 5)

// define map with initialization
capitals := map[string]string {"India" : "Delhi", "China" : "Beijing"}

// assign keys and values
capitals["USA"] = "Washington DC"
capitals["Germany"] = "Berlin"

// get size of map
size := len(capitals)
```
