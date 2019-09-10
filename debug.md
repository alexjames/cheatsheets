# Debugging stuff

## Core Dumps
Core files are generated in the current working directory of a process

Check if core files are enabled
```
ulimit -c
```
Enable core files
```
ulimit -c unlimited
```
Check the current working directory of a process
```
sudo ls -l /proc/<pid>/cwd
```
