# Intro to Linux
## Some Linux Commands
- `ssh <user>@<host>` used to ssh into a machine and remotely run commands interactively.
- `echo` used to print text to screen.
- `man <command>` used to show a manual about the command, some commands have `--help` or `-h` flags.
- `ls [-la] [dir]` used to list every file/directory in the directory.
- `cat [-n] file` used outputs the contents of files to the console. (`-n` to output number of lines).
- `touch file` used to creates files.
- `su user` used to switch between users. (`su` is equivalent to `su root`).
- Operations:
	* `>`: redirect the output of any command to a file.
	* `>>`: appends the output of a command to a file, instead of erasing it.
	* `&&`: allows you to execute a second command after the first one has executed *successfully*.
	* `&`:  unlike `&&`, `&` has nothing to do. `&` is a background operator.
	* `$`: is an unusually special operator, as it is used to denote environment variables.
	* `|`: the | operator allows you to take the output of a command and use it as input for a second command.
	* `;`: The `;` operator works like `&&`, however it *does not* require the first command to execute successfully.
---
- `chmod <permissions> <file>`: chmod allows you to set the different permissions for a file, and control who can read it.

|Digit|Meaning                                        |
|-----|-----------------------------------------------|
|1    |That file can be executed                      |
|2    |That file can be written to                    |
|3    |That file can be executed and written to       |
|4    |That file can be read                          |
|5    |That file can be read and executed             |
|6    |That file can be written to and read           |
|7    |That file can be read, written to, and executed|

- `chmod uge file`: (u=user; g=group; e=everyone) e.g. `chmod 764 file`.
---
- `chown user file` or `chown user:group file`: allows us to change the user and group for any file.
- `rm [-r]`: used to delete files or with `-r` directories.
- `mv <file> <destination>`:
	* Allows you to move files from one place to another.
	* Or rename it `mv ~/file ~/ghfds`.
- `cp [-r] <file> <destination>`:
	* Allows you to copy files from one place to another.
	* `-r` to copy directories.
- `pwd`: shows the location of the current/working directory.
- `cd <directory>`: change location to that directory.
- `mkdir <directory name>`: makes a directory.
- `ln`: used to make links
	* `ln source destination`:
		* "Hard links" a file to created link.
		* Meaning What ever is done to the created link, is also done to the original file.
	* `ln -s <file> <destination>`:
		* Symbolically links(symlink) a file to created link.
		* Meaning that the actual symbolic link has no data in it at all, it's just a reference to another file.
- `find`:
	* `find dir`: allows you to find files.
	* `find dir -user`: to list every file owned by a specific user.
	* `find dir -group`: to list every file owned by a specific group.
	* `find dir criteria action 2>/dev/null`:
		* Use this when you get permission error.
		* E.g. `find . -name "data*.txt" -print 2>/dev/null`.
- `grep`: It allows you find data inside of data.
	* `grep <string> <file>`.
	* `grep <string> <file> -n`.
	* `grep <string> <file> <file2>`.
	* `grep <regular expression> <file>`.
- `sudo`:
	* `sudo <command>`:
		* Allows you to run as administrator a command.
		* Equivalent to `sudo -u root <command>`.
	* `sudo -u user <command>`: allows you to run as a user.
	* `sudo -l`: lists your current sudo privileges.
- `uname [-a]`: displays system information.
- `free [-h]`: shows memory usage. (`-h` for human readable format).
- `df [-h]`: shows disk space usage. (`-h` for human readable format).
- `id`: shows your current user id.
- `hexdump [-C]`: displays data in hex numbers. (`-C` to show ASCII too).
- `sleep X`: delay for a specified amount of time.
- `whoami`: prints the current user.
- `whereis`: locate the binary, source, and manual page files for a command.
- `adduser username`: adds a user.
- `addgroup groupname`: adds a group.
- `usermod -a -G <groups seperated by commas> <user>`: adds a user to a group.
- `nano file`: edit file in terminal. (I prefer `vim file`).
- `shutdown [now]`: to shutdown the PC. (`shutdown now` to shutdown now).
- `reboot`: to restart/reboot your PC.

## Important Files and Directories
Everything on the linux file system extends from "/". / is the equivalent of C: in Windows. Meaning that for example if you were to delete "/", you would delete every file on your system.
- **/etc/passwd** - Stores user information - Often used to see all the users on a system.
- **/etc/shadow** - Has all the passwords of these users.
- **/tmp** - Every file inside it gets deleted upon shutdown - used for temporary files.
- **/etc/sudoers** - Used to control the sudo permissions of every user on the system.
- **/home** - The directory where all your downloads, documents etc are. - The equivalent on Windows is *C:\Users\<user>*.
- **/root** - The root user's home directory - The equivilent on Windows is *C:\Users\Administrator*.
- **/usr** - Where all your software is installed.
- **/bin** and **/sbin** - Used for system critical files - **DO NOT DELETE**.
- **/var** - The Linux miscellaneous directory, a myriad of processes store data in **/var**.
- **$PATH** - Stores all the binaries you're able to run - same as *%PATH%* on Windows.

## Installing Packages
- `sudo apt install package`: to install a package.
- `apt search package`: to search for a package.
- `sudo snap install package`: to install snap packages.
- `sudo flatpak install package`: to install flatpak packages.

## Processes
- `ps`: to show a list of user created processes.
- `ps -ef`: to show a list of all system processes.
- `ps aux`:
	* a: This option prints the running processes from all users.
	* u: This option shows user or owner column in output.
	* x: This option prints the processes those have not been executed from the terminal.
	* Collectively the options "aux" print all the running process in system regardless from where they have been executed.
- `kill <PID>`: to kill a process. (PID: Process ID).

## Some tips
- Pressing Up or Down Arrow navigate through previous commands.
- Pressing **Ctrl+R** opens a search prompt to search through previous commands.
- Pressing **Ctrl+C** to exit a running program.
- Pressing **Tab** for tab completion.

