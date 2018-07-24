## How to enable tmux scrolling

- easiest way: `C-b [` by this command we enable scrolling in tmux with arrows and PageUp, PageDown.

- for mouse scrolling must do in this way:
	- first `tmux set -g > ~/.tmux.conf` this command export tmux setting into `.tmux.conf`
	- add this command `set -g mouse on` at the end of the `.tmux.conf`
	- one time exit and enter tmux.

IMPORTANT!: in mouse on state we can not select text to do this we must using `Shift + click`.