 * Read a file line by line

```
with open("file.txt") as f:
    for line in f:
        print(line)
```

* Strip trailing and leading whitespace for a string
```
s = "   blah  \t he he "
s.strip()

Result: s = "blah  \t he he"
```

 * Lists
```
l = [1, 2, 4]

# Check if list is empty. This check is more efficient than len(l) which traverses the entire list

if l:
    print("List is not empty")

if not l:
    print("List is empty")
```
 * Sets
```
s = {"apple", "orange", "banana"}
s = set()           # declare an empty set, otherwise interpreter gets confused with dictionary
```

 * Dictionary
```
d = {"key1" : 1, "key2" 2}

for key in d:
    print(key)

for key, value in d.items():
    print(key, value)

d.get("key1", 0)   # return key1 or return default value 0
```
 * JSON
```
file = open("/Users/ajames/Downloads/pods.json")           
f = file.read()
d = json.loads(f)
```

