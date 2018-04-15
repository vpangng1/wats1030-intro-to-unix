# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Paste the output of the `pwd` command here: /home/cabox/workspace
* What directories and files do you see when you run `ls`? LICENSE file, challenge_files directory, nix_scavenger_hunt_stretch.md file, README.md file, nix_scavenger_hunt.md file, and super_scavenger.md file
* ls will list the contents in the current directory. ls -alh is ls with three separate options. `-a` will list all files beginning with `.`, `-l` will list the files in a long format, `-h` will list the file size in human readable format
* Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command: `-a` will list all files beginning with `.`, `-l` will list the files in a long format, `-h` will list the file size in human readable format
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem: bin, boot, dev, etc, fastboot, home, lib, lib64, media, mnt, opt, proc, root, run, sbin, srv, sys, tmp, usr, var 
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory: /
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. Run `pwd` and paste the response here: /home/cabox
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern.: 3
* Use the `cd` command to move "up" one directory.: /home/cabox/workspace
* Press the up arrow on your keyboard. The previous command `pwd` gets displayed in the console
* Press the up arrow a few more times. ls -1 | grep 'demo'
* Run the `history` command.: the history command displays all commands that have been entered in the console starting with the oldest

### Observing the System

* Discover what account you are logged into using the `whoami` command.: cabox
* Discover who else is on your system with the `who` command.: no
* How long has your system been running?: 21:04:48 up 56 min, 1 user, load average: 0.00, 0.00, 0.00
* Run `ps aux` and review the results.: process status displays information about the processes that have controlling terminals. `aux` are 3 separate options. `-a` displays information about all the users' processes running a controlling terminal. `-u` displays proccess belonging to each specified username. `-x` displays processes that do not run on terminals. Together this command displays all processes regardless of whether the terminal is on or off.
* Run `top` and review the results.: Unlike ps which takes a snapshot of the processes running at the time, the `top` command displays the real time information about the processes that are running.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename.: 2
* Use the `more` command to view one of the `credit_cards` files you just discovered.: 01-15-2015
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`.: /home/cabox/workspace/challenge_files/tmp
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). How many files did you find?: 2
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*: eaque_molestiae.txt, Nisi modi Waldo sed corporis sit explicabo ut est. 

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. What do you see in the `files.txt` file?: list of the directories and files of the challenge_files directory
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. Describe what you see when you run `ls -alh | more`.: `-a` will list all files beginning with `.`, `-l` will list the files in a long format, `-h` will list the file size in human readable format. 
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. Paste the list of processes that reference your username here: 538, 540, 541, 542, 544, 545, 780, 781
