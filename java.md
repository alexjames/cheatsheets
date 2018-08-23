### Hashmaps
```
HashMap <Character, Boolean> hm = new HashMap <Character, Boolean>();
hm.put('c', true);
hm.remove('c');

if (hm.containsKey('c')) {
  boolean value = hm.get('c');
}

hm.size()  // get size

// Other examples
HashMap <Integer, String> hm = new HashMap <Integer, String>();
```

### Java Strings
```
// Traversing over a string and converting to lowercase
// Java has static methods Character.toUpperCase() and Character.toLowerCase()
// Java strings are immutable by design (for security, synchronization, etc)
// so we use StringBuilder to build strings.

StringBuilder result = new StringBuilder();
for (char ch : str.toCharArray()) {
    result.append(Character.toLowerCase(ch));
}
return result.toString();

```
