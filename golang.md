# Golang
## Maps
```
func main() {
	  // defines map: string -> string
    capitals := make(map[string]string)
    
    // assign keys and values
	  capitals["USA"] = "Washington DC"
	  capitals["Germany"] = "Berlin"
    
    // get size of map
    size := len(capitals)
    
    fmt.Println(capitals)
    fmt.Println(size)
}

```
