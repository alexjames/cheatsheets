# gdb

#### Starting

###### open binary
```
gdb ./a.out
```
###### quit
```
q
```
#### Examining data
###### examine 10 words above the stack pointer
```
x/10xw $rsp
```
###### print a variable in hex
```
p /x <varname>
```
###### print the value of a variable
```
p <varname>
```

#### Debugging
###### Add a breakpoint at line number
```
b <line no>
```
###### Step through assembly instructions
```
si
```
###### Next through assembly instructions
```
ni
```
###### Step through C instructions
```
s
```
###### Next through C instructions
```
n
```
