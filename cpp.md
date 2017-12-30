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
String reverse
```
std::reverse(str.begin(), str.end());
```

### Min/Max
```
#include<algorithm>
...
int x = 5, y = 39;
min_val = std::min(x, y);
max_val = std::max(x, y);
```

### Square Root
```
#include<cmath>
sqrt(X);
```

### Vector arrays
Initialize a vector array of size num with all values set to 0.
```
vector<int> v(num, 0);
```


### 2D vector arrays
Notice the space after `>`. Used to get it to compile correctly.
```
X = Y = 4;
vector<vector<int> > V(X, vector<int>(Y, 0));
V[2][3] = 6;
```

### Hashmaps
```
unordered_map<char, int> hm;
hm.insert({'c', 5});
if (hm.find('c') == hm.end())
    cout << "not found";
else
    cout << "found";

hm.erase('c');

hm['c'] = 5;

if (hm.find('c') == hm.end())
    cout << "not found";
else
    cout << "found";
````

### Uppercase/Lowercase
```
std::toupper('c');
std::tolower('X');

std::isupper('C')
std::islower('C')
```

### Traverse a hashmap
```
for (auto &kv : hm)
{
    cout << "key : " << kv.first << " value : " << kv.second;
}
```

### Token parse loop
```
str == "ab,cd,gdf,we,d,s,d";

while (true)
{
   auto pos = str.find(",");
   token = str.substr(0, pos);
   // sub-string upto but not including the position found.
   // if pos == npos, the whole string is returned
   
   if (pos == string::npos)
   {
     str = "";
     break;
   }
   str = str.substr(pos + 1);
}
```

### Queue of co-ordinates
```
queue<pair<int, int>> q;
...
q.push(make_pair(x, y)); // type-conversion is implicit
...
cout << q.front().first << " " << q.front().second;
```
