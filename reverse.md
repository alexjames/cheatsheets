# reverse engineering

#### hexdump

###### display file in raw format
By default, without "-C", hexdump displays data as 16-bit words on little endian systems.
```
hexdump -C <filename>
```
###### Echo binary data on the terminal
Useful for injecting shellcode
```
echo -n -e '\xff\xff\xff\xab'
```
