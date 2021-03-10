# Vim

#### Navigation 

###### Move to top of file
```
gg
```

###### Move to end of file
```
G
```

###### Beginning of next word
```
w
```

###### End of next word
```
e
```

###### Previous word
```
b
```

###### Beginning of line
```
^
```

###### End of line
```
$
```

###### Search
```
/<string>
```

###### Search from current cursor position
```
./<string>
```

###### Split window
Horizontal split
```
:split
```
Vertical split
```
:vsplit
```
Move between panes
```
[Ctrl + w] + <arrow key>
```

###### Set mark (a) at this position
```
ma
```

###### jump to mark a
```
`a
```

#### Editing

###### Insert mode
```
i
```

###### Save and quit
```
:wq
```

###### Repeat last action
```
.
```

###### Delete everything until the end of this line
```
D
```

###### Append from this point
```
a
```

###### Copy (yank) a line
```
yy
```

###### Paste a yanked line
```
p
```

###### Paste a yanked line 10 times
```
10p
```

###### Delete an entire word
```
dw
```

###### Search and replace
```
:%s/<find>/<replace>/gc
```

###### Search and replace from cursor downwards
```
:.,$s/<find>/<replace>/gc
```

###### Cycle through multiple files
```
vim *.txt
:n (next file)
:N (previous file)
```
###### Highlight column for more than 80 characters
```
:set textwidth=80
:set colorcolumn=+1
```
###### Traverse filesystem
```
:e .
```
###### Move between open files
```
:bn
```
###### Copy to System clipboard
```
[Shift]["][+]yy (while holding shift) [in insert mode]
```
###### Show line number and character position
```
:set ruler
```
###### Insert characters at start of multiple lines
```
[Esc]
[Ctrl + V]
[select text]
[Shift + i]
[type text]
[Esc]
```

