
# Terminal Commands for DecriptOS

The Terminal (or CLI=Command Line Interface) is a textual interface through which you can interact with the Linux Operating System. The following commands are fundamental to getting started with the terminal.
## Generic commands

**1. `ls` - List of files and/or folders**

This command lists all the files and folders in the current directory.

Example:
```
ls
```

you can also use it to preview certain folders or files starting with the full or partial name:
```
ls folder_name 
ls name*
ls *folder
ls *lder*
```

**2. `cd` - Change directory**

This command allows you to move between directories. You can specify an absolute or relative directory.

Examples:
```
cd /absolute/path
cd destination_folder
cd .. (to return to the parent folder)
cd ~ (to return to your home directory, or even just cd)
```

**3. `mkdir` - Create a new folder**

This command creates a new folder in the current directory or in a specific location.

Examples:
```
mkdir new_folder
mkdir /existing/path/new_folder
```

**4. `touch` - Create a new file**

This command creates a new empty file in the current directory or in a specific location.

Examples:
```
touch new_file.txt
touch /existing/path/new_file.txt
```

**5. `rm` - Remove files and folders**

This command removes files and folders. Use with caution as deleted files are not moved to the recycle bin, but are permanently deleted.

Examples:
```
rm file_to_remove.txt
rm -r folder_to_remove
rm -d empty_folder_to_remove
```

**6. `cp` - Copy files and folders**

This command copies files and folders from one location to another.

Examples:
```
cp files_to_copy.txt /path/destination
cp -r folder_to_copy /path/destination
```

**7. `mv` - Move or rename files and folders**

This command moves or renames files and folders.

Examples:
```
mv file_to_move.txt /path/destination
mv old_name.txt new_name.txt
```

**8. `cat` - Show the contents of a file**

This command displays  the contents of a file on the terminal.

Example:
```
cat file_to_displays.txt
```

**9. `grep` - Search within files**

This command searches for a given string within one or more files.

Example:
```
grep "word_to_search" file(s)_of_interest.txt
```

**10. `sudo` - Run commands as administrator**

This command executes the next command with administrator privileges (sudo = super user do). 

Examples:
```
sudo apt update
sudo apt upgrade
```

**11. `open` - opens a file or folder**

This command opens a file with the default program or a folder.

Examples:
```
open folder 
open . (opens the current folder)
open file.txt
```

**12. `ip addr` - show IP address specifications**

Example:
```
ip addr
```

**13. `passwd` - sets the system password**

Example:
```
sudo passwd
```

**14. `ip addr` - show IP address specifications**

Example:
```
ip addr
```

**15. `ssh-keygen` - SSH key generation**

Example:
```
ssh-keygen -t ed25519 -C james.moriarty@decripto.org
```

To connect GitHub via ssh:

- create SSH key
  `ssh-keygen -t ed25519 -C james.moriarty@decripto.org`

[enter the file in which to save the key or skip to keep `/home/decripto/.ssh/id_ed25519`]

[enter password or skip]

- compile the SSH key in the .pub file in the `/home/decripto/.ssh/` (something like: `ssh-ed25519 AAAAC3NzaCC1.....7kX0J`)

- open github and go under settings, SSH, new, paste and give a name

**16. `man` - for the manual page of a command**

Example:
```
man ls (show the manual page for the command 'ls')
man mkdir (show the manual page for the command 'mkdir')
```

# DecriptOS commands

DecriptOS has several terminal "shortcuts" that allow you to speed up your work, some are for starting programs, others for creating templates.

**1. `dinit` - Initialize a local workbook**

This command initializes a folder, creating the files draft-article.md, material.md in the "material" folder, and report.md, in the current folder. The files are templates that will help speed up the collection and organization of material pertaining to a given project under analysis.

Example:
```
dinit.sh
```

**2. `Kraken` - Start the Kraken**

This command starts the Kraken program in the terminal, which assists during the investigation by automating some processes, such as opening tabs and saving some data.

Example:
```
Kraken (standard boot)
Kraken -h (help message)
```

**3. `redshift` - Controls screen colors to protect eyes from blue light**

This command allows you to control the tone of the monitor in a fixed or time-based manner.

Example:
```
redshift -h
redshift -O 5500 (set tone at 5500 K)
redshift -x (reset to the original color of the LCD)
```

# Git commands to synchronize folders with GitHub

Git is a widely used distributed version control system. Below you will find some main commands for synchronizing folders with GitHub using Git.

**1. `git init` - Initialize a local Git repository**

This command initializes a new local Git repository in the current directory.

Example:
```
git init
```

Then configure git with the main branch:
```
git config --global init.default branch main
```

to create or rename the main branch to "main":
```
git branch -M main
```

and configure your credentials for commits
```
git config --global user.name "James Moriarty"
git config --global user.email james.moriarty@decripto.org
```

**2. `git clone` - Clone an existing repository**

This command clones an existing Git repository from GitHub into the current directory.

Example:
```
git clone https://github.com/utente/repository.git
```

**3. `git status` - Check the status of the folder and files**

Example:
```
git clone https://github.com/utente/repository.git
```

**4. `git diff` - Show the differences between the last commit and the current file**

It can also be used to show the differences between 2 branches with `..`

Example:
```
git diff main..altra-branch
```

**5. `git add` - Adds files to the repository**

This command adds one or more files to the Git repository.

Example:
```
git add file_to_add.txt
```

or to add them all use `add .`

Example:
```
git add .
```

**6. `git commit` - Make a commit of the changes**

This command creates a new commit with the changes made. The `-m` parameter allows you to enter the comment below.

Example:
```
git commit -m "Description of the changes"
```

Please note: if a description is not added to the commit, Vim will be opened from terminal to enter it. Vim is a pain in the ass, so always enter the message immediately.

To enter the description with Vim:
- press the i key to enter text
- write the description
- press Esc to exit the input mode
- press `:wq` to write and exit 

**7. `git push` - Synchronize remote changes**

This command sends local commits to the remote repository on GitHub.

Example:
```
git push origin branch_name
```

**8. `git pull` - Update the local repository**

This command updates the local repository with changes from the remote repository on GitHub.

Example:
```
git pull origin branch_name
```

These are just some of the most common commands used in the terminal for working with Git. There are many other commands and options available that you can explore further [here](https://training.github.com/downloads/github-git-cheat-sheet/).
