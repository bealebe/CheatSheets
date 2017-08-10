# Vim Cheat Sheet
### Opening vim
Open vim in using factory settings (without sourcing .vimrc and in nocompatible mode) `vim -u NONE -N`  
Open vim without sourcing source.vim `vim u source.vim` (?)  
Saved views location `~/.vim/view` (?)  

### Normal mode
#### Operators
Autoindent `=`  
Swap case `g~`  
Make lower case `gu`. eg. `guu` will make the whole line lower case  
Make upper case case `gU`. eg. `gUiw` will make the word under the cursor upper case  
#### Numbers
Increment the closest number 180 times: `180<C-a>`  
Decrement the closest number 2 times: `2<C-x>`  
#### Scrolling
top `zt`  
centre`zz`  
bottom`zb`  
#### Folding
fold `zf`  
unfold `zd`  
#### Joining
`J`  
`gJ` includes leading whitespace  
#### Setting marks
set mark a at current cursor location `ma`  
jump to line of mark a (first non-blank character in line) `'a`  
delete from current line to line of mark a `d'a`   
change text from current line to line of mark a `c'a`   
list all the current marks `:marks`   
jump to position where last change occurred in current buffer `` `. ``   
jump back (to line in current buffer where jumped from) `''`    
#### Record macro
start recording `q{register}`  
end recording `q`  
execute macro at register `@{register}`  
execute previous macro `@@`  
#### Search
Search current word `*`  
forward `/`  
back `?`  
highlight `:noh`  
Jump to local variable declaration `gd`  
#### Switch mode
Normal-insert mode `<C-o>` eg. `<C-o>zz` will switch to normal-insert mode and scroll to the middle 
#### Other
Get numeric code of char under cursor: `ga`  

### Insert mode
Insert text from a register `<C-r>{register}`. eg. `<C-r>0` will paste the last thing that was copied    
Insert last inserted text `<C-a>`    
Insert char by hex code `<C-v>u{1234}`  
Insert char by digraph `<C-k>{char1}{char2}`. eg. `<C-k>12` results in a fraction (`:help digraphs-default`)

### Visual mode
Toggle select mode `<C-g>` (seldom used)  
Enable character-wise visual mode `v`  
Enable line-wise visual mode `V`  
Enable block-wise visual mode `<C-v>`  
Reselect the last visual selection `gv`  
Go to other end of highlighted text `o`  
Append after ragged visual block `<C-v>{n}j$` followed by `A`  
Repeat command on more than one line `:normal .` 

### Command-line mode
List plugins (scripts) `:scriptnames`   
Insert text from a register `:<C-r>{register}`. eg. `:<C-r>0` will paste the last thing that was copied  
Navigate to line 1 `:1`  
Jump to end of file `:$`  
Put text in register after line 3 `:3pu`  
Delete lines 2 to 5 `:2,5d`   
Join from current line to end of file `:.,$j`  
Print entire file `:%p`. This is the same as `:1,$jp`  
`:'<,'>` represents the start and end of the visual selection. eg. ` `:'<,'>`s/{old}/{new}` ` will substitute {old} with {new} within the visual selection.

#### Substitute
new for the first old in a line type `:s/old/new`  
new for all 'old's on a line type `:s/old/new/g`  
phrases between two line #'s type `:#,#s/old/new/g`  
all occurrences in the file type `:%s/old/new/g`  
ask for confirmation each time add 'c' `:%s/old/new/gc`  

### Complete mode
```
i C-x
	C-p, C-n # Word completion
	C-l Line completion
```
### Tabs and Spaces
http://vimcasts.org/episodes/tabs-and-spaces/  

## Personalisation
https://github.com/amix/vimrc  

leader: `,`  

### Search:
forward `<space>`  
back `<c-space>`  
highlight `<leader><CR>` 

### Plugins

* mru `<leader>f` opens recent files  
* nerdtree `<leader>nn` opens nerdtree, `m` opens menu 
* vim-surround `cs<old><new>`, `ys<new>`, `(visual)S<new>` (?)
* vim-commentary `gc`
* vim-yankstack `<C-p>`, `<C-P>`
* vim-syntastic
	* Disbale auto-checking in syntastic plugin `:SyntasticToggleMode`  
	* Force syntax: `:set syntax=java`  

### Other
New tab: `<leader>tn`  
Replace text (in visual mode): `<leader>r{replacement}<CR>`  
Spell Check: `<leader>ss`  



