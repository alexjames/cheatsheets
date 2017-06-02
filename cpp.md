### Sorting
```
#include<algorithm>
...
vector<int> v;
...
std::sort(v.begin(), v.end());
```

### String manipulation
Integer to string and vice-versa
```
// a = "23+43"
// formula -> find + substr + stoi (c++11)
auto pos = a.find('+');
int vara = std::stoi(a.substr(0, pos));
int varb = std::stoi(a.substr(pos + 1, a.length()));
```
Convert a number to a string
```
std::string num = std::to_string(23);
```

### Min/Max
```
#include<algorithm>
...
int x = 5, y = 39;
min_val = std::min(x, y);
```
