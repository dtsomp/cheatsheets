# i3 window manager


.tmux.conf

    # Change Control-b to Control-a
    unbind C-b
    set -g prefix C-a
    # GUI-friendliness
    set -g default-terminal "screen-256color"
    setw -g mode-mouse on
    set -g mouse-select-pane on

Shortcuts

    Mod-Enter       Open terminal
    Mod-d           App launcher
    Ctrl-Shift-q    Quit application    
    Mod-d i3lock    Lock screen

Window handling
    
    Mod-w           Tabbed windows
    Mod-s           Stacked windows
    Mod-e           Switch between horizontal/vertical split   
    Mod-f           Full-screen on|off
    Mod-arrows      Move focus to other windows
    Mod-[num]       Move focus to workspace(screen)
    Mod-Shift-[num] Move window to workspace

Non-mouse config

Monitor setup:

xrandr

    # Show available modes
    xrandr

    # Position screen
    xrandr --output VGA1 --right-of LVDS1

    # Change resolution
    xrandr --output VGA1 --mode 1280x800
