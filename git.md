# git

#### Configuration

###### Set username and password
```
git config --global user.name alexjames
git config --global user.email alx.james@gmail.com
```

###### Clone a repo
```
git clone <repo URL>
```

###### Convert commit to a patch
```
git format-patch -1 <sha>
git am < file.patch
```
