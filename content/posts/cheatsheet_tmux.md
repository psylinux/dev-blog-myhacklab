---
author: Marcos Azevedo
date: '2021-03-25T17:19:34-03:00'
linktitle: 'Cheat Sheet :: Tmux'
title: 'Cheat Sheet :: Tmux'
categories:
  - cheatsheet
  - sysadmin
  - shell
tags:
  - cheatsheet
  - shell
  - tmux
  - linux
  - sysadmin
weight: 10
date updated: '2021-03-25T17:19:34-03:00'

---


## Working with Sessions

### New Session

- Start a New Session

  ```bash
  $> tmux new-session
  ```

- Or you can type

  ```bash
  $> tmux
  ```

- Or you can use the **shorthand**

  ```bash
  $> tmux new
  ```

- If you're **already inside** the `tmux`

  ```vim
    : new
  ```

- Start a New Session with the name **mysession**

  ```bash
  $> tmux new -s mysession : new -s mysession
  ```

### Kill/Delete Sessions

- Kill/Delete **mysession**

  ```bash
  $> tmux kill-session -t mysession
  ```

- Or you can use the **shorthand**

  ```bash
  $> tmux kill-ses -t mysession
  ```

- Kill/Delete all sessions *but* **mysession**

  ```bash
  $> tmux kill-session -a -t mysession
  ```

- Kill/Delete all sessions *but* the **current** session

  ```bash
  $> tmux kill-session -a
  ```

### Rename session

- If you're **already inside** the `tmux`

  ```vim
  Ctrl + b + $
  ```

### Move Between Sessions

- Move to Previous Session // If you're **already inside** the `tmux`

  ```vim
  Ctrl + b + (
  ```

- Move to Next Session // If you're **already inside** the `tmux`

  ```vim
  Ctrl + b + )
  ```

### Attach to an Existing Session

#### Attach to the Last Session

  ```bash
  $> tmux attach-session
  ```

- Or

  ```bash
  $> tmux attach
  ```

- Or

  ```bash
  $> tmux at
  ```

- Or you can use the **shorthand**

  ```bash
  $> tmux a
  ```

#### Attach to an Existing Session with the Name **mysession**

  ```bash
  $> tmux attach-session -t mysession
  ```

- Or

  ```bash
  $> tmux attach -t mysession
  ```

- Or

  ```bash
  $> tmux at -t mysession
  ```

- Or you can use the **shorthand**

  ```bash
  $> tmux a -t mysession
  ```

### Detach from Session

- If you're **already inside** the `tmux`

  ```vim
  Ctrl + b + d
  ```

### Show ALL sessions

- Listing ALL sessions

  ```bash
  $> tmux list-sessions
  ```

- Or you can use the **shorthand**

  ```bash
  $> tmux ls
  ```

- If you're **already inside** the `tmux`

  ```vim
  Ctrl + b + s
  ```

## Working with `tmux` Window

### Start a new Window

- Start a new session with the name **mysession** and window name **mywindow**

  ```bash
  $> tmux new -s mysession -n mywindow
  ```

- Create a new Window // If you're **already inside** the `tmux`

  ```vim
  Ctrl + b + c
  ```

### Rename a Window

- Rename current window

  ```vim
  Ctrl + b + ,
  ```

- Close the current window

  ```vim
  Ctrl + b + &
  ```

### Moving Between Windows

- Previous window

  ```vim
  Ctrl + b + p
  ```

- Next window

  ```vim
  Ctrl + b + n
  ```

- Select window by number

  ```vim
  Ctrl + b + 0...9
  ```

### Reorder a Window

- Swap window number 2 and 1

  ```vim
    : swap-window -s 2 -t 1
  ```

## Working with Panes

### Toggle Panes

- Toggle last active pane

  ```vim
  Ctrl + b + ;
  ```

### Split the Pane

- Split pane vertically

  ```vim
  Ctrl + b + %
  ```

- Split pane horizontally

  ```vim
  Ctrl + b + "
  ```

### Moving Between Panes

- Move the current pane to the left

  ```vim
  Ctrl + b + {
  ```

- Move the current pane t the right

  ```vim
  Ctrl + b + }
  ```

### Switching Between Panes

- Switch to pane to the direction

  ```vim
  Ctrl + b + ⬆
  Ctrl + b + ⬇
  Ctrl + b + ⬅
  Ctrl + b + ⮕
  ```

### Toggle synchronize-panes

- Send the same command to all panes

  ```vim
    : setw synchronize-panes
  ```

### Toggle Between Panes

- Toggle between pane layouts

  ```vim
  Ctrl + b + <SpaceBar>
  ```

- Switch to next pane

  ```vim
  Ctrl + b + o
  ```

- Show pane numbers (Type the number to go to that pane)

  ```vim
  Ctrl + b + q
  ```

### Toggle the Pane Zoom

  ```vim
  Ctrl + b + z
  ```

### Convert a Pane into a Window

  ```vim
  Ctrl + b + !
  ```

### Resize the Pane

- Resize the current pane height

  ```vim
  Ctrl + b + ⬆
  Ctrl + b + ⬇
  ```

- Resize the current pane width

  ```vim
  Ctrl + b + ⬅
  Ctrl + b + ⮕
  ```

### Close the Pane

- Close the Current Pane

  ```vim
  Ctrl + b + x
  ```

## Enter in Copy Mode (Buffer)

- Enter in Copy Mode

  ```vim
  Ctrl + b + [
  ```

- Enter in Copy Mode and Scroll One Page Up

  ```vim
  Ctrl + b + PgUp
  ```

- Quit Mode

  ```vim
    q
  ```

- Go to Top Line

  ```vim
    g
  ```

- Go to Bottom Line

  ```vim
    G
  ```

### Scroll using the Keyboard Cursor (Arrows)

- Scroll Up

  ```vim
  Keyboard Up Cursor // ⬆
  ```

- Scroll Down

  ```vim
  Keyboard Down Cursor // ⬇
  ```

- Scroll Left

  ```vim
  Keyboard Left Cursor // ⬅
  ```

- Scroll Right

  ```vim
  Keyboard Right Cursor // ⮕
  ```

### Scroll using the `vim` keys

**FIRST: Remember to Set the `vim` keys in Buffer Mode**. Go to [Set the runtime tmux Options](#set-the-runtime-tmux-options) section to learn more.

- Move Cursor to the Left

  ```vim
    h
  ```

- Move Cursor Down

  ```vim
    j
  ```

- Move Cursor to the Up

  ```vim
    k
  ```

- Move Cursor to the Right

  ```vim
    l
  ```

- Move Cursor Forward One Word At a Time

  ```vim
    w
  ```

- Move Cursor Backward One Word At a Time

  ```vim
    b
  ```

- Search forward

  ```vim
    /
  ```

- Search backward

  ```vim
    ?
  ```

- Go to the Next Keyword Occurrence

  ```vim
    n
  ```

- Go to the Previous Keyword Occurrence

  ```vim
    N
  ```

### Working with Buffers

- Start a Selection

  ```vim
    <SpaceBar>
  ```

- Clear the Selection

  ```vim
    <Esc>
  ```

- Copy selection

  ```vim
    <Enter>
  ```

- Paste the Contents of Buffer_0

  ```vim
  Ctrl + b + ]
  ```

- Display the Buffer_0 Contents

  ```vim
    : show-buffer
  ```

- Copy the Entire Visible Contents of Pane to a Buffer

  ```vim
    : capture-pane
  ```

- Show All Buffers

  ```vim
    : list-buffers
  ```

- Show All Buffers and Paste Selected

  ```vim
    : choose-buffer
  ```

- Save the Buffer Contents to the file `buf.txt`

  ```vim
    : save-buffer buf.txt
  ```

- Delete the Buffer_1

  ```vim
    : delete-buffer -b 1
  ```

- Enter the Command Mode

  ```vim
  Ctrl + b + :
  ```

## Set the runtime tmux Options

- Set OPTION for All Sessions

  ```vim
    : set -g OPTION
  ```

- Set OPTION for All Windows

  ```vim
    : setw -g OPTION
  ```

- Set to use `vim` keys in Buffer Mode

  ```vim
    : setw -g mode-keys vi
  ```

- Set the `vim` Buffer Size in Runtime (history)

  ```vim
  set-option -g history-limit 50000
  ```

- Start a New Session with a Defined Buffer Size (history)

  ```bash
  tmux set-option -g history-limit 50000; new-session
  ```

## Help

- Show Every Session, Window, Pane, etc...

  ```bash
  $> tmux info
  ```

- Show Shortcuts

  ```vim
  Ctrl + b + ?
  ```
