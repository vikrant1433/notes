## to execute the current line in any program (e.g. bash)
* `.w !bash` - this will write the current line into the stdin of bash program  here `.` can be any range of lines
## to execute the current line as an ex command
* `yy:@"`
## fugitive plugin
* `[c`	jump to previous hunk
* `]c`	jump to next hunk
* `dp`	shorthand for `:diffput`
* `do`	shorthand for `:diffget`
* When you call `:Gwrite` from vimdiff mode, it writes the current file to the index and exits vimdiff mode.
## vim-notes
* https://github.com/xolox/vim-notes
## to know your current colorscheme
* echo g:colors_name
## case-insensitive filename completion
> :set wildignorecase
## change case of whole line
* guu : convert the whole line to lower case
* gUU : convert the whole line to upper case
* g~~ : toggle the case of whole line 

## help system
* <c-]> : go to subject topic under the cursor
* <c-t> : go to previous cursor location

## Searching
* `/{pattern}/{offset}` search forward for the pattern and go offset lines up (if offset is -ve) or down (if offset is +ve)
* `/<CR>` search forward for last search pattern
## screen movement commands
* zz or z. center the screen on the cursor
* zt scroll the screen so that the cursor is at the top
* zb scroll the screen so that the cursor is at the bottom

## to windows operations
* `Ctrl+w, S` mirror the selected file in horizontal split
* `Ctrl+w, v`  mirror the selected file in vertical split
* `Ctrl+w, q` to close one
* `Ctrl+w, J` if you have vertical split move the selected window to horizontal split
* `Ctrl+w, L` if you have horizontal split move the selected window to vertical split

## to open multiple files in vertical split view from the command line
* `vim -O[n] file1 file2 file3` for verticle split use: [n] to restrict the maximum number of windows to open 
* `vim -o[n] file1 file2 file3` for horizontal split use: [n] to restrict the maximum number of windows to open 
* `vim -p file1 file2 file3` open files in tabs
## to close all files
* `:qa`

## Ctrl-p plugin 
* `c-p` to search for a file starting with cwd 
* `c-v` to open the selected file in vertical split
* `c-s` to open the selected file in horizontal split
* `c-t` to open the selected file in new tab
## vim-instant-markdown
* [https://github.com/suan/vim-instant-markdown]

## to open file in read only mode
* `vim -R filename`
* to set from vim `:set ro`
## to turn buffer into tab pages
* `:tab ball`
## to insert output of external command to current line
* `:,!ls | wc -l `- this will insert the count of number of files in the current line
## to get the diff of two opened file side by side in vertical split
* `:windo diffthis`
to get out of diffmode `:diffoff!`
## to copy nth line and paste it on mth line 
* `:4co.<CR>` copy 4th line from top and paste the content to current line
* `:4co10<CR>` copy 4th line from top and paste the content to 10th line

## to move nth line to kth line
* `:4mo.<CR>` move 4th line from top and paste the content to current line
* `:4mo10<CR>` move 4th line from top and paste the content to 10th line
note:**instead of a single line a range of line can be used like :1,4co.**

## replace a text with newline
* use `\r` instead of `\n` for replacing use `\n` for searching
## replace exact word
* `%s/\<word\>/newword/g`
## Easyclip plugin
* to replace a word under cursor with copied text `siW`
* to replace current line with copied text `ss`
* `m<motion>` - delete over the given motion and copy text to clipboard
* `m<motion>` - delete over the given motion and copy text to clipboard
## to mark a location
* `mx` to mark the current location with character `x`
* `backtick x` or `apostrophe x` to go mark `x`

## to open file in verticle split file name under cursor
* nnoremap gf :vertical wincmd f<CR>
## to convert ^M linebreak to normal linebreak
* `:%s/<Ctrl-V><Ctrl-M>/\r/g`
* Where `<Ctrl-V><Ctrl-M>` means type `Ctrl+V` then `Ctrl+M`.
to convert the case of a word
======
* gu{motion} - for lower case
* gU{motion} - for upper case

to increment and decrement numbers under the cursor
====
* <c-a> : increment
* <c-x> : decrement
-------------
* `:g/pattern/cmd` : `g` will run the command on all the lines that match the pattern and `:v/pattern/cmd` or `:g!/pattern/cmd` will run the command which doesn't match the `pattern` e.g. `g/pattern/d` will delete all the lines that match the pattern `pattern`
* `expand('string')` expands the vim string
* to redirect the output of a command to the current file `:%! [cmd]`
* to copy text to a register `"ay`. to paste content of register a `"ap`
* `command vim -` to redirect the output of a bash command to vim
* `:let @a = system('echo "foo"')` store the output of echo command to register `a`. `"ap` to paste the content of register `a`
* `:%!cat -s` - to delete multiple blank lines with a single blank line
* `gcii` - to comment code at same indent level
* `gcai` - to comment code at same indent level even if there are newlines
### to toggle case
    - ~ - toggle case of selected characters
    - U - in visual mode convert selected characters to UPPER case
    - u - in visual mode convert selected characters to lower case
### To go to previous editing buffer
    - `<C-^>` or `<C-6>` or `:b#`
### To apply airline theme
    - `let g:airline_theme='base16'`
### To repeat findx
    - `;`
### NERDTree
=====
    - to open a tab silently `T`
    - to open NERDTree `<C-E>`
### searching flags
    - `g` - global
    - `c` - confirming
    - `i` - ignore case
### Managing multiple files at onece
    - `:tabnew [file]`
    - `:tabm[ove]` # - move current tab to position # (zero-indexed), no argument = end
    - `:tabc[lose]` - close current file
    - `:tabo` - close all other tabs except current
VIM-SPF13
=========
* to install `curl http://j.mp/spf13-vim3 -L -o - | sh`
### To remove a plugin from vim-spf13
    > echo UnBundle \'AutoClose\' >> ~/.vimrc.bundles.local
    > echo UnBundle \'scrooloose/syntastic\' >> ~/.vimrc.bundles.local  

**Remember to run ':BundleClean!' after this to remove the existing directories**
### To remove ^M character from vim
    - `:%s/^M//g`
to enter ^M press ctrl-v and ctrl-m
### Cursor movement
    - `^` - Move to first non-blank character of the line
    - `0` - Move to first character of the line
    - `<C-b>` move back one fullscreen
    - `<C-f>` move forward one fullscreen
    - `<C-d>` move forward half screen
    - `<C-u>` move back half screen
    - `{` and `}` - jump to the prev/next empty line.

### searching
* \* - Word under cursor - forward (bounded)
* # - Word under cursor - backward (bounded)
* g\* - Word under cursor - forward (unbounded)
* g# - Word under cursor - backward (unbounded)
### to display date in vim
```
    :nnoremap <F5> "=strftime("%c")<CR>P
    :inoremap <F5> <C-R>=strftime("%c")<CR>")"
```
* to wrap entire line in parentheses with `yssb` or `yss)`  
* to wrap selected text in visible mode with quotes `VwS'`
### to position the middle/top/bottom screen with cur

#### to exit out of insert mode in vim
* `ctrl+c`
* `D` to delete till end of line from the cursor:
Features to add:
* indentation lines

* showing spaces and tab character

* add easymotion feature to ideavim

### Easymotion
`<leader><leader>w` # to go to starting of any word
`<leader><leader>w` # to go to starting of any word

### to goto last cursor position
* '' (two apostrophe) # go to the start of the line  
* `\`\`` (two backticks)  # go to the same line
### to close all windows except current one
* `ctrl-w o`

### To install plugins in vim spf13:
* write `Bundle` `plugin name` in git url in ~/.vimrc.bundle.local file and then run the below command in terminal
* `vim +BundleInstall! +BundleClean +q` 
* `<leader>ev` open all vim configuration file for editing
* `<leader>sv` source the .vimrc file

### good colorschemes
* anderson
* 0x7a69_dark
* anotherdark but have underline
* antares

### to source the .vimrc file
* `:[so]urce /path/to/.vimrc`
### leader>c<space>
e.g. <comma> c <space>

* auto indenting gg=G
* gg- go to start of 1st line
* = - indent
* G - upto last line

### to run any command directly from the vim use ! followed by the command to be run.
> e.g. ! wc %
### shows the word count of current file

* b, B, r, and a are aliases for ), }, ], and >
### to list all installed plugins in vim
> :scriptnames
### to set zsh shell for vim

> :set shell=/path/to/zsh

### vim-multiple-cursor
* ctrl-n for selecting the word under the cursor and by pressing it again it will select the next occurrence of that word and create a virtual cursor
* ctrl-p unselect the __current__ selection
* ctrl-x unselect the current selection and select the next occurrence

### surround.vim
* csxx change surround takes two arguments 1st can be (,{,’,”,[ or a tag	second can be any replacement char as 1st argument
* ysmx you surround takes two arguments 1st is any valid vim motion key and second is any valid surround char
dsx delete surround takes one argument that can be any valid surround char.

* J for joining lines convert \n to space
* % means current file
* a means all
* i means inner
### text objects
* ax x can be {,[,’,”,\`,<
* < left shift in normal mode (4 spaces)
* right shift in normal mode (4 spaces)
* at	a <tag> </tag> block (with tags)		|v_at|
*  `aw`	a word (with white space)			|v_aw|
*  `iw`	inner word					|v_iw|
*  `aW`	a WORD (with white space)			|v_aW|
*  `iW`	inner WORD					|v_iW|
*  `as`	a sentence (with white space)			|v_as|
*  `is`	inner sentence					|v_is|
*  `ap`	a paragraph (with white space)			|v_ap|
*  `ip`	inner paragraph					|v_ip|
*  `ab`	a () block (with parenthesis)			|v_ab|
*  `ib`	inner () block					|v_ib|
*  `aB`	a {} block (with braces)			|v_aB|
*  `iB`	inner {} block					|v_iB|
*  `at`	a <tag> </tag> block (with tags)		|v_at|
*  `it`	inner <tag> </tag> block			|v_it|
*  `a<`	a <> block (with <>)				|v_a<|
*  `i<`	inner <> block					|v_i<|
*  `a[`	a [] block (with [])				|v_a[|
*  `i[`	inner [] block					|v_i[|
*  `a"`	a double quoted string (with quotes)		|v_aquote|
*  `i"`	inner double quoted string			|v_iquote|
*  `a'`	a single quoted string (with quotes)		|v_a'|
*  `i'`	inner simple quoted string			|v_i'|
*  `a\``	a string in backticks (with backticks)		|v_a`|
*  `i\``	inner string in backticks			|v_i`|

*-------------------------------------------------------------------

* viB from normal mode select inner text between `{}` parenthesis
* vib from normal mode select inner text between `()` parenthesis
* vab is same as vib except it also selects braces
* vaB

* `ctrl+W` R "Swap top/bottom or left/right split
* `ctrl+W` T "Break out current window into a new tabview
* `ctrl+W` o "Close every window in the current tabview but the current one
* `ctrl+w_` "Max out the height of the current split
* `ctrl+w|` "Max out the width of the current split
* `ctrl+w=` "Normalize all split sizes, which is very handy when resizing terminal

### to open files in new tabs
> vim -p file1 file2 file3

### code folding
* `za` toggle code folding
* `zR` unfolds everything
* `zM` folds everything
* `zf` create folding for selected lines
* `zf#j`	create folding for #lines down
* `zf#k`	create folding for #lines up
*---------
* `<leader>ig`     `,ig` - to toggle tab highlighting in vim
* `gt` or `ctrl-page-up` - goto next tab
* `gT` or `ctrl-page-down` - goto prev tab
* `zt` - to make your current line at the top of the screen
* `z.` - to make your current line at the middle of the screen
* `zb` - to make your current line at the bottom of the screen
### to close a tab 
* `:q`
* so copy a line - `y` in normal mode
* to change esp key in vintage plugin of sublime
* paste the below code in user keymap

```json
{
    "keys": ["j", "k"],
    "command": "exit_insert_mode",
    "context":  [
                    { "key": "setting.command_mode", "operand": false },
                    { "key": "setting.is_widget", "operand": false }
                ]
}
```
* C - To delete from cursor to end of line and begin insert
* W - `Forward` to the beginning of the next WORD
a WORD is defined as words separated by whitespace

### To be read:
* [ vim-markdown ]( https://github.com/tpope/vim-markdown )
## todo
* how to create snippets?
