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
* Slices
```
indexing starts from 0 to n-1, reverse indexing starts from -n to -1
# all elements
a[:]

# first n elements
a[:n]

# last n elements
a[-n:]

# elements between index n to m-1
a[n:m]

# every second element (starting from the first)
a[::2]

# every second element starting from the second
a[1::2]
```

Linked List Implementation

```
class ListNode:
    def __init__(self, object):
        self.val = object
        self.next = None

class LinkedList:
    def __init__(self, object = None, head = None):
        self.head = head

    def addNode(self, object):
        if self.head == None:
            self.head = ListNode(object)
            return
        n = self.head
        while n.next != None:
            n = n.next
        n.next = ListNode(object)

    def addNodeAtPosition(self, object, pos):
        if pos < 0:
            raise Exception("nah!")

        if pos == 0:
            n = self.head
            self.head = ListNode(object)
            self.head.next= n
            return
        
        n = self.head
        while pos > 1:
            if n == None:
                raise Exception("nah!")
            n = n.next
            pos = pos - 1
        c = n.next
        n.next = ListNode(object)
        n.next.next = c
        

    def traverse(self):
        n = self.head
        while n != None:
            print(n.val)
            n = n.next
```
