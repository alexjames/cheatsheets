# C++ primer
##
C++ is a compiled language i.e. source files are compiled to object files, which are then linked together to form a binary. C++ is a statically typed language i.e. the type of every entity (object, value, name or expression) must be known at compile time.

The << operator, known as the 'put-to' operator, writes it's second argument onto it's first argument.
```
std::cout << "Hi";    // put Hi to std::cout
```

## Initialization
```
double x = 3.2;
double x {3.2};
vector <int> v {1, 2, 3, 4, 5};

// {} checks for type safety (in most cases!), so use it preferably.
```

Use auto when the type can be deduced from the initializer.
```
auto boolean_val = true;
auto x = 3.14;
auto y = fn(4);

// Don't use auto if it can cause ambiguity while reading the code. 
```

## Scope and lifetimes
There is local (block) scope, class scope and namespace scope. Objects created in a namespace have a lifetime equivalent to the life of the program. Objects created by new live on until they are destoryed by delete.

const - the data is never changed
constexpr - evaluated at compile time, usually placed in the data-segment ROM

For a function to be used in a constexpr, it must also be declared as constexpr.
```
constexpr int mul(int x, int y) {return x + y;}
...
constexpr int minutes = mul(24, 60);
```

### range loops
```
int v[] = {1, 2, 3};
// "For every element in the specified collection put a "copy" of the element in x"
for (auto x : v)
  cout <<< x << endl;
for (auto x : {1, 2, 3})
  cout << x << endl;
// "For every element in the specified collection put a reference to the element in x"
for (auto& x : v)
  cout <<< x << endl;

// References cannot be changed once initialized (const by design) and don't need to be dereferenced with '*'.
```
References are useful in as function arguments, because they ensure that copies of the arguments are not made and the object that is passed to the function is actually modified.
```
void modifies_v(vector<int> &v);  // modifies argument
void modifies_v(vector<int> v);   // makes a copy of v and modifies this copy
void cannot_modify_v(const vector<int> &v);   // passed by reference and function cannot modify it, saves cost of copying
```

### nullptr
Older C programs used NULL or 0 to denote null-pointers. However, 0 and NULL can be interpretted as integers in expressions, so having an explicit `nullptr` keyword to denote an unassigned pointer makes sense.
```
int *p = nullptr;
```
