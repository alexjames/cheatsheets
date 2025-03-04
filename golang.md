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

### Server Reflection
Reflection is useful for:
 * Dynamic discovery of services and methods.
 * Debugging and testing, especially when the server implementation is not directly available.
 * Building tools like API explorers or dynamic client generators.
By enabling reflection, you avoid needing to know the exact service interface ahead of time, which is often needed when building gRPC clients manually. It gives flexibility and more power when interacting with gRPC servers.

In golang, you have to use the `google.golang.org/grpc/reflection` package.
```
grpcurl -plaintext localhost:50051 list
grpcurl -plaintext localhost:50051 describe myservice.MyService
```
