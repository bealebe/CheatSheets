# Vim Cheat Sheet
### Opening vim
* Open vim in using factory settings (without sourcing .vimrc and in nocompatible mode) `vim -u NONE -N`  
* Open vim without sourcing source.vim `vim u source.vim` (?)  
* Saved views location `~/.vim/view` (?)  

### Normal mode
#### Operators
* Autoindent `=`  
* Swap case `g~`  
* Make lower case `gu`. eg. `guu` will make the whole line lower case  
* Make upper case case `gU`. eg. `gUiw` will make the word under the cursor upper case  
#### Numbers
* Increment the closest number 180 times: `180<C-a>`  
* Decrement the closest number 2 times: `2<C-x>`  
#### Scroll to
* top `zt`  
* centre`zz`  
* bottom`zb`  
#### Folding
* Fold `zf`  
* Unfold `zd`  
#### Joining
* `J`  
* `gJ` includes leading whitespace  
#### Setting marks
* Set mark a at current cursor location `ma`  
* Jump to line of mark a (first non-blank character in line) `'a`  
* Delete from current line to line of mark a `d'a`   
* Change text from current line to line of mark a `c'a`   
* List all the current marks `:marks`   
* Jump to position where last change occurred in current buffer `` `. ``   
* Jump back (to line in current buffer where jumped from) `''`    
#### Record macro
* Start recording `q{register}`  
* End recording `q`  
* Execute macro at register `@{register}`  
* Execute previous macro `@@`  
#### Search
* Search current word `*`  
* forward `/`  
* back `?`  
* highlight `:noh`  
* Jump to local variable declaration `gd`  
#### Switch mode
* Normal-insert mode `<C-o>` eg. `<C-o>zz` will switch to normal-insert mode and scroll to the middle 
#### Other
* Get numeric code of char under cursor: `ga`  

### Insert mode
* Insert text from a register `<C-r>{register}`. eg. `<C-r>0` will paste the last thing that was copied    
* Insert last inserted text `<C-a>`    
* Insert char by hex code `<C-v>u{1234}`  
* Insert char by digraph `<C-k>{char1}{char2}`. eg. `<C-k>12` results in a fraction (`:help digraphs-default`)

### Visual mode
* Toggle select mode `<C-g>` (seldom used)  
* Enable character-wise visual mode `v`  
* Enable line-wise visual mode `V`  
* Enable block-wise visual mode `<C-v>`  
* Reselect the last visual selection `gv`  
* Go to other end of highlighted text `o`  
* Append after ragged visual block `<C-v>{n}j$` followed by `A`  

### Command-line mode
* List plugins (scripts) `:scriptnames`   
* Insert text from a register `:<C-r>{register}`. eg. `:<C-r>0` will paste the last thing that was copied  
* Navigate to line 1 `:1`  
* Jump to end of file `:$`  
* Put text in register after line 3 `:3pu`  
* Delete lines 2 to 5 `:2,5d`   
* Join from current line to end of file `:.,$j`  
* Print entire file `:%p`. This is the same as `:1,$jp`  
* `:'<,'>` represents the start and end of the visual selection. eg. `` :'<,'>`s/{old}/{new} `` will substitute {old} with {new} within the visual selection.
* Copy line 6 to just below the current line `:6copy` or `:6co` or `:6t`  
* Move line 2 to just below current line `:2move .` or `:2m .`
* Repeat the last command from line 2 to eof `:2,$ normal .` 
* Append a semicolon to every line `:%normal A;`  
* Repeate last Ex command `@:`  
* Rever last Ex command `<C-o>`  
* Execute previous Ex command `@@`  
* Insert current word at commmand prompt `<C-r><C-w>` eg. `:help <C-r><C-w>`  
* Open search history `q\`  
* Open command history `q:`  
* Run shell commands `!{cmd}`. eg. `!ls`  
* List buffers `:ls`  
* Open interactive shell session `:shell` or `<C-z>`  
* Exit interactive shell session `exit` or `fg`  

#### Substitute
* new for the first old in a line type `:s/old/new`  
* new for all 'old's on a line type `:s/old/new/g`  
* phrases between two line #'s type `:#,#s/old/new/g`  
* all occurrences in the file type `:%s/old/new/g`  
* ask for confirmation each time add 'c' `:%s/old/new/gc`  

### Register
* List register `:register`  

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
* forward `<space>`  
* back `<c-space>`  
* highlight `<leader><CR>` 

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
* New tab: `<leader>tn`  
* Replace text (in visual mode): `<leader>r{replacement}<CR>`  
* Spell Check: `<leader>ss`  
