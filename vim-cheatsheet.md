 
# Vim Cheat Sheet

## Modes
- `i` — insert before cursor
- `a` — insert after cursor
- `I` — insert at line start
- `A` — insert at line end
- `o` — new line below
- `O` — new line above
- `Esc` — back to normal mode
- `:` — command mode
- `v` — visual mode
- `V` — visual line mode
- `Ctrl+v` — visual block mode

## Navigation
- `h j k l` — left / down / up / right
- `w` — next word
- `b` — previous word
- `e` — end of word
- `0` — start of line
- `$` — end of line
- `gg` — top of file
- `G` — bottom of file
- `:<n>` — go to line n
- `Ctrl+d` — half page down
- `Ctrl+u` — half page up
- `%` — jump to matching bracket

## Editing
- `x` — delete character
- `dd` — delete line
- `yy` — yank (copy) line
- `p` — paste after
- `P` — paste before
- `u` — undo
- `Ctrl+r` — redo
- `ciw` — change inner word
- `di"` — delete inside quotes
- `.` — repeat last action

## Search & Replace
- `/pattern` — search forward
- `?pattern` — search backward
- `n` / `N` — next / previous match
- `:%s/old/new/g` — replace all in file
- `:%s/old/new/gc` — replace with confirmation

## Saving & Quitting
- `:w` — save
- `:q` — quit
- `:wq` or `ZZ` — save and quit
- `:q!` — quit without saving
- `:wa` — save all buffers