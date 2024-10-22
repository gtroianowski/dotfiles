

# Notes on copy/pasting in tmux through ssh connection
Of all the approaches I looked into, the one that ended up working best was to use OSC52 code. 
The added difficulty in `tmux` is that the codes need to be sent to the right tty. Here are some breadcrumbs:
- In tmux, run some bash script with the content being copied as argument. 
- The script will encode the content in base64 and use OSC52 escape codes to communicate it to the relevant tty and get picked up by iterm2


Some references:
- https://stackoverflow.com/a/60667122
- https://sunaku.github.io/tmux-yank-osc52.html : this page helped a lot! However, I wanted a solution without using `xsel/xclip` to avoid having to run an X server. `set-window-option -g allow-passthrough on` may help (I have tested solutions with older versions of `tmux`)