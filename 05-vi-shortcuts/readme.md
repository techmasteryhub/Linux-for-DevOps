# VI Editor Shortcuts (Linux for DevOps)

## Introduction to VI Editor

The **VI editor** is one of the most widely used text editors in Linux.
For DevOps engineers, it is essential for editing configuration files, scripts, logs, and system settings directly from the terminal.

VI works in different modes, and understanding them is the key to using it effectively.

---

# Modes in VI Editor

## 1. Normal Mode (Default Mode)

This is the mode you enter when you open a file.

Used for:

* Navigation
* Copy, paste, delete
* Running commands

---

## 2. Insert Mode

Used for editing or adding text.

* Press `i` → Enter Insert Mode
* Press `Esc` → Return to Normal Mode

---

## 3. Command Mode

Used for saving, quitting, and advanced operations.

* Press `:` in Normal Mode to enter Command Mode

---

# Basic Navigation in VI

Move around the file efficiently using these keys:

```text id="vimnav"
h → move left  
l → move right  
j → move down  
k → move up  
```

### Line Navigation

* `0` → Start of line
* `^` → First non-space character
* `$` → End of line

### Word Navigation

* `w` → Next word
* `b` → Previous word

### File Navigation

* `gg` → Go to start of file
* `G` → Go to end of file
* `:n` → Go to line number n

---

# Insert Mode Shortcuts

These commands help you enter Insert Mode in different positions:

* `i` → Insert before cursor
* `I` → Insert at beginning of line
* `a` → Append after cursor
* `A` → Append at end of line
* `o` → New line below
* `O` → New line above
* `Esc` → Exit Insert Mode

---

# Editing Text in VI

## Delete Operations

* `x` → Delete character at cursor
* `X` → Delete character before cursor
* `dw` → Delete word
* `dd` → Delete entire line
* `d$` → Delete to end of line
* `d0` → Delete to beginning of line
* `D` → Delete from cursor to end of line

---

## Undo and Redo

* `u` → Undo last action
* `Ctrl + r` → Redo

---

## Copy and Paste

* `yy` → Copy line
* `yw` → Copy word
* `p` → Paste after cursor
* `P` → Paste before cursor

---

# Search and Replace

## Searching

```bash id="vimsearch1"
/pattern   # Search forward
?pattern   # Search backward
```

* `n` → Next match
* `N` → Previous match

---

## Replace Operations

```bash id="vimreplace1"
:%s/old/new/g
```

* Replace all occurrences in file

```bash id="vimreplace2"
:s/old/new/g
```

* Replace in current line only

---

# Working with Multiple Files

## File Operations

* `:e filename` → Open a new file
* `:w` → Save file
* `:wq` → Save and exit
* `:q!` → Quit without saving

---

## Split Screen Editing

```bash id="vimsplit1"
:split filename
```

* Horizontal split

```bash id="vimsplit2"
:vsplit filename
```

* Vertical split

### Switching Between Splits

* `Ctrl + w + w` → Switch between windows

---

# Quick VI Cheat Sheet

| Task        | Shortcut        |
| ----------- | --------------- |
| Insert mode | `i`, `a`, `o`   |
| Save file   | `:w`            |
| Quit        | `:q`            |
| Save & quit | `:wq`           |
| Delete line | `dd`            |
| Copy line   | `yy`            |
| Paste       | `p`             |
| Undo        | `u`             |
| Search      | `/pattern`      |
| Replace     | `:%s/old/new/g` |

---

🚀 VI editor is a must-have skill for DevOps engineers because it allows fast, efficient, and direct editing of files on remote Linux servers without needing a GUI.

