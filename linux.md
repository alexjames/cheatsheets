# Linux

#### Filesystem

###### list files
```
ls 
```

###### list files with details
```
ls -l
```

###### list files in reverse order sorted by modification time
```
ls -latr
```

###### Change directory
```
cd <dirname>
```
###### Move back to previous directory
```
cd -
```

###### Copy file1 to file2
```
cp file1 file2
```

###### Create a symbolic link to a file
Symbolic links can point to a file on any volume
```
ln -s file link
```

###### Create a directory
```
mkdir dir1
```

###### Create a directory and its intermediate directories if they don't exist
```
mkdir /dir1/dir2/dir3
```

#### Process Management

###### List all running processes
```
ps -ef
```

###### Suspend current running job
```
CTRL + Z
```

###### Let suspended job run in the background
```
bg
```

###### List all background jobs
```
jobs
```

###### Move a job (say 2) from the jobs list back to the foreground
```
fg %2
```

###### Move last stopped/background job back to the foreground
```
fg
```

#### Miscellaneous

###### Check which shell I'm running
```
echo $SHELL
```
