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

