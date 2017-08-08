# Vim Cheat Sheet

## Commands

### Opening vim
Open vim in using factory settings (without sourcing .vimrc and in nocompatible mode) `vim -u NONE -N`  
Open vim without sourcing source.vim `vim u source.vim`

## Numbers
Increment the closest number 180 times: `180<C-a>`  
Decrement the closest number 2 times: `2<C-x>`  

### Substitute
```
:s/old/new # new for the first old in a line type    
:s/old/new/g # new for all 'old's on a line type       
:#,#s/old/new/g # phrases between two line #'s type       
:%s/old/new/g # all occurrences in the file type        
:%s/old/new/gc # ask for confirmation each time add 'c'             
```

### Scrolling
```
zt # top 
zz # centre
zb # bottom
```

### Folding
```
zf # fold
zd # unfold
```

### Joining
```
J 
gJ # includes leading whitespace
```
### Insert
Insert text from a register `Ctrl+r`  
Last inserted text `C-a`  

### Visual
Block mode selection `C-v`  
Reselect text `gv`  

### Setting marks
```
ma # set mark a at current cursor location
'a # jump to line of mark a (first non-blank character in line)
d'a # delete from current line to line of mark a
c'a # change text from current line to line of mark a
:marks # list all the current marks
`.  # jump to position where last change occurred in current buffer
' ' # jump back (to line in current buffer where jumped from)
```

### Complete mode
```
i C-x
	C-p, C-n # Word completion
	C-l Line completion
```

### Record macro
```
q {register} # start recording
q # end recording
@ {register} # execute macro at register
@@ # execute previous macro
```

### Syntax
Disbale auto-checking in syntastic plugin `:SyntasticToggleMode`  
Force syntax: `:set syntax=java`  

### Search
Search current word `*`  

### Other
Saved views location `~/.vim/view`  
Repeat command on more than one line in visual mode `:normal .`  
List of scripts(plugins) `:scriptnames`  
Jump to local variable declaration `gd`  

## Mappings from https://github.com/amix/vimrc  
leader: ` map <leader> ,`  
Spell Check: `map <leader>ss :setlocal spell!<cr>`  

Search:
```
map <space> /
map <c-space> ?
map :noh<cr> <leader><cr> 
```

New tab: `map tn <cr> :tabnew<cr>`  

Replace text: `vnoremap <silent> <leader>r :call VisualSelection('replace')<CR>`  
