# Vim
## What is Vim?
Vim is a text editor for Windows, macOS, and Linux. It's known for being fast and efficient, in part because it's a small application that can run in a terminal (although it also has a graphical interface), but mostly because it can be controlled entirely with the keyboard with no need for menus or a mouse.

## Installing Vim
- Windows:
	- Go to [Vim's Website](https://www.vim.org/download.php#pc).
	- Download and install the "self-installing-executable".
- MacOS:
	- `brew install vim`.
- Linux:
	- Debian-Based Distributions: `sudo apt install vim`.
	- Arch-Based Distributions: `sudo pacman -S vim`.
	- Fedora-Based Distributions: `sudo dnf install vim-enhanced`.

Note: The command `vimtutor` is a great way to learn vim. (the vimtutor tutorial takes 30 minutes or so).

## Using Vim
**Launch Vim:**<br>
To start Vim from the shell prompt type: `vim FILENAME`.

**Vim Modes:**<br>
There are three basic modes in Vim:
- **Command mode** is where you can run commands. This is the default mode in which Vim starts up.
- **Insert mode** is where you insert i.e. write the text.
- **Visual mode** is where you visually select a bunch of text so that you can run a command/operation only on that part of the text.

To enter "INSERT" mode press `i`.<br>
To return to command mode press `esc`.

**Navigation:**
- Basic Navigation:
	- The cursor is moved using either the arrow keys or the hjkl keys.
		- left: `h`.
		- right: `l`.
		- down: `j`.
		- up: `k`.
	- jump to the start of the file: `gg`.
	- jump to the end of the file: `G` i.e. `shift + g`.
- Advanced Navigation:
	- jump to the start of a word: `w`.
	- jump to the end of a word: `e`.
	- jump to the start of a line: `0`.
	- jump to the end of a line: `$`.
	- jump to # line: `:#`. (# is the number of a line).

**Insert or Append**:
- insert (before the cursor): `i`.
- insert (at the beginning of the line): `I` i.e. `shift + i`.
- append (after the cursor): `a`.
- append (at the end of the line): `A` i.e. `shift + a`.
- insert a new line under the current line: `o`.
- insert a new line above the current line: `O` i.e. `shift + o`.

**Save and Exit:**
- write the file, but don't exit: `:w`. (equivalent to save).
- write the file, but don't exit (as root): `:w !sudo tee %`. (incase you didn't `sudo vim FILENAME`).
- quit: `:q`. (fails if there is unsaved changes).
- write and quit: `:wq`. (equivalent to save and exit).
- force quit: `:q!`. (will exit with unsaved changes).
- force quit (for all active tabs): `:qa!`.
- save and quit (for all active tabs): `:wqa`.

**Copy, Cut and Paste:**
- copy a line: `yy`.
- copy 2 lines: `2yy`.
- copy to the end of the line: `y$`.
- paste the clipboard contents (after the cursor): `p`.
- paste the clipboard contents (before the cursor): `P` i.e. `shift + p`.
- cut a character: `x`.
- cut a line: `d`.
- cut two lines: `dd`.
- cut to the end of the line: `D` i.e. `shift + d`.

**Delete and Undo**:
- delete a word: `dw`.
- delete to the end of the line: `d$`.
- delete a line: `dd`.
- undo an action: `u`.
- undo all the changes on a line: `U` i.e. `shift + u`.
- undo the undo's (i.e. redo): `ctrl + r`.

**vimgrep**<br>
You can also use "vimgrep" to use grep inside vim, allowing you to search using grep syntax and regex if you so desire.

**Search and Grep**:
- search forwards for a pattern: `/pattern`.
- search backwards for a pattern: `?pattern`.
- repeat this search in the same direction: `n`.
- repeat this search in the opposite direction: `N`.
- search for "old" and replace it with "new":
	- `:%s/old/new/g`. (without confirmation).
	- `:%s/old/new/gc`. (with confirmation for each one).
- use "grep" to search for a pattern in multiple files: `:vimgrep`.

**Tips:**
- `:help`: launches vim's help.txt.
- Special Characters:
	- `!`: allows you to execute shell commands.
	- `%`: means the current file name. (not always but usually).
	- Execute `:help cmdline-special` for more info.

## Config File
`.vimrc` is Vim's configuration file it helps you customize Vim.<br>
Here is my `.vimrc`:
```vim
syntax on
set number
set tabstop=4
cmap w!! w !sudo tee > /dev/null %
```
What each line does:
- `syntax on`: turns syntax highlighting on.
- `set number`: activates line numbering.
- `set tabstop=4`: sets the size of a tab to 4 spaces.
- `cmap w!! w !sudo tee > /dev/null %`:
	- maps `w!!` to `w !sudo tee > /dev/null %`.
	- Basically creates a shortcut for typing `w !sudo tee > /dev/null %`.
	- The `w !sudo tee` write the file as root. (From **Save and Exit Section**).
	- The `> /dev/null %` explicitly throws away the standard output since we don't need to pass anything to another piped command.
	- See the [`tee` man page](http://ss64.com/bash/tee.html) for more info. (use `man tee`, click link, or Google).

## Vim Plugins
Vim is extensible, meaning that you can add features to it through plugins. With a history spanning decades, Vim has are plenty of useful plugins to choose from and even entire sites, like [Vim Awesome](https://vimawesome.com/), dedicated to Vim plugins.

To install vim plugins, Google it!
