# Linux

#### Filesystem

###### List files
```
ls 
```

###### List files with details
```
ls -l
```

###### List files in reverse order sorted by modification time
```
ls -latr
```

###### List directories in order of size
```
du -a | sort -n -r
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
mkdir -p /dir1/dir2/dir3
```

###### Show size of current directory
```
du -sh
```

###### Show size of current directory and all its sub-directories
```
du -sh *
```

###### Sort comma-separated list by second column numerically
```
cat fname | sort -t',' -k 2 -n -r
```

###### Find number of times a line repeats in a file
```
cat fname | sort | uniq -c
```

###### Join two lists based on first column
```
join <(sort f1) <(sort f2)
```

#### Process Management

###### List all running processes
```
ps -ef
```

###### List process running on port 5000
```
lsof -i :5000
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

###### for loop
```
for f in $(ls dir/); do echo $f; done
```

###### New Hard Disk
```
fdisk -l
mkfs.ext4 /dev/sdb
mkdir /partition
mount /dev/sdb /partition

vi /etc/fstab
<add line>
/dev/sdb               /partition           ext4    defaults        1 2
```

###### Clear terminal screen
```
clear OR [Crtl + l]
```
###### New terminal screen
```
[Crtl + Alt + T]
```
###### Switch terminal tabs
```
[Crtl + PgUp/PgDn]
```
###### Check which shell I'm running
```
echo $SHELL
```

###### Check the exit status of the last run program
```
echo $?
```

###### Check installed services
```
chkconfig --list
```

###### Search and replace a phrase in files
```
sed -i 's/pharase/replacement/g' *
```

###### Create ISO Image
```
genisoimage -o myimage.iso -V MyLabel -R -J /home/source/folder
```
###### Mount ISO
```
mount -o loop /home/myimage.iso /mnt/cdrom
```
###### Print 2 lines before and 3 lines after search match in grep
Alternately, you can use -C to match <n> lines both before and after.
```
cat file | grep -B 2 -A 3 "pattern"
```
  
###### Recursively change all occurences of a string in multiple files
```
grep -r -l "get-dc-abbr" * | xargs sed -i 's/get-dc-abbr/my-site/g'
```

###### ffmpeg extract mp4 container audio without conversion
```
ffmpeg -i video.mp4 -vn -acodec copy audio.aac
```

###### ffmpeg extract mp4 container audio with trimming
```
ffmpeg -i video.mp4 -ss 00:01:02.500 -t 00:01:03.250 -vn -acodec copy audio.aac
```

###### clip a video starting from time t1 for duration x without any re-encoding
```
ffmpeg.exe -ss t1 -i video.mp4 -t X -map 0 -c copy out.mp4
```

###### pretty print json data 
```
python3 -m json.tool pod-data.json
```

###### Quick HTTP Server
```
python -m SimpleHTTPServer 8080
python3 -m http.server 8080
```

###### Print OpenSSL Certificate
```
openssl x509 -in personal.crt -noout -text 
```

###### Print JSON doc by key
```
cat stuff.json | jq .KEYNAME
```

###### Print list in JSON doc
```
cat stuff.json | jq '.[]'
```
