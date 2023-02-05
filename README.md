# Vim Talon Cursorless Dictionary

Inspired by: https://vim.rtorr.com/
Vim Docs: https://vimdoc.sourceforge.net/

## Cursor Movements (normal mode)

| Vim Command | Meaning                                         | Talon/Cursorless |
|-------------|-------------------------------------------------|------------------|
| h           | left                                            |                  |
| j           | down                                            | south            |
| k           | up                                              | north            |
| l           | right                                           |                  |
| gj          | down (multi-line text)                          |                  |
| gk          | up (multi-line text)                            |                  |
| H           | top of screen                                   |                  |
| M           | middle of screen                                |                  |
| L           | bottom of screen                                |                  |
| w           | start of next word                              |                  |
| W           | start of next word (words contain punctuations) |                  |
| e           | end of next word                                |                  |
| E           | end of next word (words contain punctuations)   |                  |
| b           | start of last word                              |                  |
| B           | start of last word (words contain punctuations) |                  |
| ge          | end of last word                                |                  |
| gE          | end of last word (words contain punctuations)   |                  |
| 0           | start of line                                   | head             |
| $           | end of line                                     | tail             |
| ^           | first non-blank character of line               |                  |
| g_          | last non-blank character of line                |                  |
| %           | matching (pair-)character                       |                  |
| gg          | first line of document                          |                  |
| G           | last line of document                           |                  |
| gd          | local declaration                               |                  |
| gD          | global declaration                              |                  |
| {           | previous paragraph                              |                  |
| }           | next paragraph                                  |                  |
| zz          | center cursor on screen                         |                  |
| zt          | position on top                                 |                  |
| zb          | position on bottom                              |                  |
| Ctrl + d    | move down 1/2 page                              |                  |
| Ctrl + u    | move up 1/2 page                                |                  |
| Ctrl + b    | move back (1 page up)                           |                  |
| Ctrl + f    | move forward (1 page down)                      |                  |
| Ctrl + e    | move down one line                              |                  |
| Ctrl + y    | move up one line                                |                  |

(f,t,F,T, ';' and ',' are not needed in Cursorless. I can jump directly to a [target])

## Insert/Append Text (insert mode)

| Vim Command | Meaning                  | Talon/Cursorless |
|-------------|--------------------------|------------------|
| i           | insert before cursor     |                  |
| I           | insert at start of line  |                  |
| a           | append after cursor      |                  |
| A           | append at end of line    |                  |
| o           | open new line below      | pour [target]    |
| O           | open new line above      | drink [target]   |
| ea          | append after end of word |                  |
| ESC         | exit insert mode         | -                |

(Ctrl + h, w, j, t, d, n, p, rx, ox not needed here because of no difference between "normal" and "insert mode" in
the Cursorless setting)

## Editing (normal mode)

| Vim Command | Meaning                               | Talon/Cursorless |
|-------------|---------------------------------------|------------------|
| r           | replace single character              |                  |
| R           | replace characters until ESC          |                  |
| J           | join lines                            |                  |
| gJ          | join lines without space between them |                  |
| cw          | change to end of word                 |                  |
| C           | change to end of line                 |                  |
| u           | undo                                  | nope             |
| U           | Restore whole line                    |                  |
| Ctrl + r    | redo                                  | yes indeed       |
| .           | repeat last command                   | repeat that      |
| gu          | switch to lower case (with motion)    |                  |
| gU          | switch to upper case (with motion)    |                  |
| g~          | switch case (with motion)             |                  |

(g~, gwip, cc, s, S, xp are missing)

## Commands for marking text (visual mode)

| Vim Command | Meaning                                       | Cursorless         |
|-------------|-----------------------------------------------|--------------------|
| v           | start visual mode and select a letter         |                    |
| V           | start line-wise visual mode and select a line | take line [target] |
| o           | move to other end of marked area              |                    |
| Ctrl + v    | start visual block mode                       |                    |
| O           | move to other corner of block                 |                    |
| aw          | mark a word                                   | take [target]      |
| ab          | a block with `()`                             |                    |
| aB          | a block with `{}`                             |                    |
| at          | a block with `<>`                             |                    |
| ib          | inner block with `()`                         |                    |
| iB          | inner block with `{}`                         |                    |
| it          | inner block with `<>`                         |                    |
| ESC         | exit visual mode                              |                    |

## Commands (visual mode)

| Vim Command | Meaning              | Talon/Cursorless |
|-------------|----------------------|------------------|
| y           | copy selected        | copy that        |
| u           | switch to lower case |                  |
| U           | switch to upper case |                  |
| ~           | switch case          |                  |
| <           | shift to left        |                  |
| >           | shift to right       |                  |
| d           | delete               |                  |

## Registers

(I have already a clipboard feature in my IDE)

## Marks and Positions

| Vim Command | Meaning                              | Talon/Cursorless |
|-------------|--------------------------------------|------------------|
| :marks      | list of marks                        |                  |
| ma          | toggle mark (a -> local/A -> global) |                  |
| `a          | jump to position of a/A              |                  |
| y`a         | yank text to position of a/A         |                  |
| `0          | go to previously exited              |                  |
| `"          | go to last edited of this file       |                  |
| `.          | go to last change of this file       |                  |
| ``          | go to position before last jump      |                  |
| :ju[mps]    | list of jumps                        |                  |
| Ctrl + i    | newer position in jump list          |                  |
| Ctrl + o    | older position in jump list          |                  |
| :changes    | list of changes                      |                  |
| g,          | newer position in change list        |                  |
| g;          | older position in change list        |                  |
| Ctrl + ]    | jump to tag under cursor             |                  |

(The command `'a` jumps to the beginning of line with mark `a/A`)
(remember to `set ideamarks` in .ideavimrc to use native IntelliJ-bookmarks)

## Macros

| Vim Command | Meaning          | Talon/Cursorless |
|-------------|------------------|------------------|
| qa          | record macro 'a' |                  |
| q           | stop recording   |                  |
| @a          | run macro 'a'    |                  |
| @@          | run last macro   |                  |

(Run macro x times: x@a or x@@)

## Cut, paste and move text (normal mode)

| Vim Command             | Meaning                                                        | Talon/Cursorless    |
|-------------------------|----------------------------------------------------------------|---------------------|
| yy                      | copy line                                                      |                     |
| yw                      | copy characters from cursor position to before next word       |                     |
| yiw                     | copy word under cursor                                         |                     |
| yaw                     | copy word under cursor with space after or before              |                     |
| Y                       | copy to end of line                                            |                     |
| p                       | paste after cursor                                             |                     |
| P                       | paste before cursor                                            |                     |
| gp                      | paste after cursor and leave cursor after new text             |                     |
| gP                      | paste before cursor and leave cursor after new text            |                     |
| dd                      | delete/cut line                                                |                     |
| dw                      | delete/cut characters from cursor position to before next word |                     |
| diw                     | delete/cut word under cursor                                   | chuck [target]      |
| daw                     | delete/cut word under cursor and the space after or before     |                     |
| x                       | delete/cut character under cursor                              |                     |
| D                       | delete/cut to end of line                                      | chuck tail [target] |
| D                       | delete/cut to end of line                                      |                     |
| :[range]d               | delete/cut from [range] (e.g. 2,7 for line 2 to line 7)        |                     |
| :g/{pattern}/d          | delete all line containing pattern                             |                     |
| :g!/{pattern}/d         | delete all lines not containing pattern                        |                     |
| :[range]mo[ve] {adress} | move lines given by [range] to below {adress}                  |                     |

(For ranges, you can use: `.` = current line, `$1` = start of file, `$d` = end of file )

## Indent text (normal mode)

| Vim Command | Meaning        | Talon |
|-------------|----------------|-------|
| <<          | shift to left  |       |
| >>          | shift to right |       |

(`<%`, `>%`, `>ib`, `>at`, `3==`, `=%`, `=iB`, `gg=G`, `]p` are probably not needed. I have a formatter in my IDE)

## Save and exit

| Vim Command | Meaning         | Talon |
|-------------|-----------------|-------|
| :w          | write file      | disk  |
| :wa         | write all files |       |
| :q          | exit            |       |

## Search and replace

| Vim Command    | Meaning                                                               | Talon |
|----------------|-----------------------------------------------------------------------|-------|
| /pattern       | search forward in file for pattern                                    |       |
| ?pattern       | search backward in file for pattern                                   |       |
| \pattern       | 'very magic': non-aphanum chars are interpreted as sepcial regex syms |       |
| n              | go to next search match                                               |       |
| N              | go to previous search match                                           |       |
| :%s/old/new/g  | substitute all `old` with `new` in current file                       |       |
| :%s/old/new/gc | substitute all `old` with `new` in current file with confirmations    |       |
| :noh[lsearch]  | remove highlighting from search matches                               |       |

## Search in multiple files

(I can use a direct mapping to IDE actions to achieve this)

## Tabs

| Vim Command  | Meaning                         | Talon                |
|--------------|---------------------------------|----------------------|
| :tabnew      | open new tab                    | tab (open/new)       |
| gt           | next tab                        | tab next             |
| gT           | previous tab                    | tab (last/previous)  |
| #gt          | tab number #                    | go tab #             |
| :tabm[ove] # | move current tab to #           | -                    |
| :tabc[lose]  | close current tab               | tab close            |
| :tabo[nly]   | close all tabs but the current  | -                    |
| :tabdo       | run command for all tabs        | -                    |
| Ctrl + wT    | Move current split into own tab | -                    |
| -            | Duplicate tab                   | tab duplicate        |
| -            | Restore tab                     | tab (reopen/restore) |
| -            | Tab search (Browser)            | tab search <text>    |

## Working with multiple files

| Vim Command | Meaning                               | Talon |
|-------------|---------------------------------------|-------|
| Ctrl + ws   | window split                          | -     |
| Ctrl + wv   | window split vertically               | -     |
| Ctrl + ww   | switch window                         | -     |
| Ctrl + wq   | quit window                           | -     |
| Ctrl + wx   | exchange current window with next one | -     |
| Ctrl + w=   | make all windows equal height & width | -     |

(I can use a direct mapping to IDE actions to achieve this in Talon)

(Ctrl+wh, wl, wj, wk are mapped differently in my .ideavim-settings)

? buffer commands probably not needed, because I'm already in an IDE

## Diff

Todo

## More [g]lobal commands

https://vimdoc.sourceforge.net/htmldoc/vimindex.html#g

| Vim Command | Meaning                                            | Talon/Cursorless |
|-------------|----------------------------------------------------|------------------|
| gi          | insert text before the first non-blank in the line |                  |

## Square bracket commands

Todo

## surround.vim

https://github.com/tpope/vim-surround

| Vim Command          | Meaning                                    | Talon/Cursorless |
|----------------------|--------------------------------------------|------------------|
| ds[target]           | delete [target]-surroundings               |                  |
| cs[target1][target2] | change surroundings [target1] to [target2] |                  |
| ys[motion][target]   | change surrounding of [motion] to [target] |                  |

## .ideavim (personal settings)

https://github.com/JetBrains/ideavim
https://ideavim.sourceforge.net/vim/motion.html

(I can use a direct mapping to IDE actions to achieve this)

| .ideavim Command | Meaning         | jetbrains.talon | vscode.talon |
|------------------|-----------------|-----------------|--------------|
| ]w               | next camel hump | go camel right  | -            |
| K                | open man page   |                 |              |

Todo
