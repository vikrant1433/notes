# rotate windows
- prefix + <alt>-o
# tmux-copycat plugin key bindings
* `prefix + ctrl-f` - simple file search
* `prefix + ctrl-g` - jumping over git status files (best used after git status command)
* `prefix + alt-h` - jumping over SHA-1 hashes (best used after git log command)
* `prefix + ctrl-u` - url search (http, ftp and git urls)
* `prefix + ctrl-d` - number search (mnemonic d, as digit)
* `prefix + alt-i` - ip address search
# session

* rename session 
* `prefix + $` 
# to swap panes
- `prefix + {`
# to install tmux v2.0 on ubuntu 14.04
```bash
sudo apt-get update
sudo apt-get install  python-software-properties software-properties-common -y
sudo add-apt-repository ppa:pi-rho/dev -y
sudo apt-get update
sudo apt-get install  tmux=2.0-1~ppa1~t -y
```

# to maximize and restore current pane
- `prefix + z` : to toggle maximize pane and unmaximize 

# tmux cheat sheet
- `https://gist.github.com/andreyvit/2921703`
# tmux-yank
## key bindings _not_ in copy mode
- `prefix + y` :  copies text from the command line to clipboard.
- `prefix + Y` (shift-y) : copy pane current working directory to system clipboard 
## key bindings in copy mode
- `y` - copy selection to system clipboard
- `Y` (shift-y) - put selection - equivalent to copying a selection, and pasting it to the command line
- `Alt-y` - performs both of the above: copy to system clipboard and put to command line (deprecated, not useful)
# tmux plugin manager
- [link]( https://github.com/tmux-plugins/tpm)
- `git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`
## tpm key bindings
- `prefix + I `: installs new plugins from github or any other git repository
- `prefix + U` : updates plugin(s)
- `prefix + alt + u` : remove/uninstall plugins not on the plugin list

## Basics

? get help
Session management

s list sessions
$ rename the current session
d detach from the current session
Windows

c create a new window
, rename the current window
w list windows
% split horizontally
" split vertically
n change to the next window
p change to the previous window
0 to 9 select windows 0 through 9
Panes

% create a horizontal pane
" create a vertical pane
h move to the left pane. *
j move to the pane below *
l move to the right pane *
k move to the pane above *
k move to the pane above *
q show pane numbers
o toggle between panes
} swap with next pane
{ swap with previous pane
! break the pane out of the window
x kill the current pane
Miscellaneous

t show the time in current pane
