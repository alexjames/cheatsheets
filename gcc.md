# gcc

###### Standard compilation
```
gcc foo.c bar.c -o output
```

###### Only compile and generate object files, do not run linker
```
gcc -c foo.c
```

###### Stop after compilation, do not assemble
```
gcc -S foo.c
```

###### Compile with debug info
```
gcc -g foo.c bar.c -o output
```
