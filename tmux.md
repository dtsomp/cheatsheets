# tmux

Control-b is the keyboard shortcut to do anything in tmux.  
Change it.   
Nobody uses it.   
It is horribly uncomfortable.  

.tmux.conf

    # Change Control-b to Control-a
    unbind C-b
    set -g prefix C-a
    # GUI-friendliness
    set -g default-terminal "screen-256color"
    setw -g mode-mouse on
    set -g mouse-select-pane on

Shortcuts

    Ctrl-a c        new window
    Ctrl-a "        split window into panes horizontally
    Ctrl-a %        split window into panes vertically
    Ctrl-a <arrows> change focus
    Ctrl-a !        break pane to new window
    Ctrl-a ?        list available commands
    Ctrl-a w        list windows and select window
    Ctrl-a Ctrl-o   swap panes
    Ctrl-a ,        rename window

    Ctrl-a :source-file ~/.tmux.conf    :   reload the configuration

Copy-pasting:

    1. Ctrl-a [         enter scroll mode (Esc to exit)
    2. move
    3. Ctrl-space       start highlighting
    4. Alt-w            copy highlighted text
    5. Ctrl-a ]         paste
