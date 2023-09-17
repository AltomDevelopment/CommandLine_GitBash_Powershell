# Command Line (CLI) Cheat Sheet
---

## Working with Directories 

- **pwd** Displays the path of the current working Directory
- **cd <directory>** Change directory to <directory>
- **cd\\** Takes you to the top of the directory tree
- **cd ..** Navigate to parent directory
- **dir** List directory contents
- **dir -la** List detailed directory contents, including hidden files 
- **mkdir <directory>** Create new directory named <directory>
- **ren [old_folder][new_folder]** Renames an old folder name with a new folder name 
## Working with Files

- **rm <file>** Delete <file>
- **rm -r <directory>** Delete <directory>
- **rm -f<file>** Force Delete <file> (add -r to force delete a directory)
- **mv <file-old> <file-new>** Rename <file-old> to <file-new>
- **mv <file> <directory>** Move <file> to <directory> (possibly overwriting an existing file)
- **cp <file> <directory>** Copy <file> to <directory> (possibly overwritting an existing file)
- **cp -r <directory1> <directory2>** Copy <directory1> and its contents to <directory2> (possibly overwritting files in an existing directory)
- **touch <file>** Update file access & modification time (and create <file> if it doesn't exist)

## Search

- **find <dir> -name "<file>"** Find all files named <file> inside <dir> (use wildcards [*] to search for parts of filenames, e.g."file.*")
- **findstr "<text>" <file>** Output all occurences of <text> inside <file> (add -i for case-insensitivity)
- **findstr -rl "<text>" <dir>** Search for all files containing <text> inside <dir>

## Output

- **cat <file>** Output the contents of <file>
- **more <file>** Output the contents of <file> using the more command (which supports pagination etc.)
- **head <file>** Output the first 10 lines of <fie>
- **<cmd> > <file>** Direct the output of <cmd> into <file>
- **<cmd> >> <file>** Append the output of <cmd> to <file>
- **<cmd1> | <cmd2>** Direct the output of <cmd1> to <cmd2>
- **clear** Clear the command line window

## Permissions

- **chmod 755 <file>** Change permissions of <file> to 755
- **chmod -R 600 <directory>** Change permissions of <directory> (and its contents) to 600
- **chown <user>;<group> <file>** Change ownership of <file> to <user> and <group> (add -R to include a directory's contents)

## Network

- **ipconfig** Shows complete info about the network 
- **tracert** Shows complete information about a packets path
- **NSLOOKUP** Displays info for diagnosing (DNS) infastructure 
- **ROUTE** Helps you manually configure Routes 
- **DISKPART** Helps you manage your computers drives 
- **FORMAT** Format a disk 
- **ping <host>** Ping <host> and display status
- **whois <domain>** Output whois information for <domain>
- **curl -O <url/to/file>** Download <file> (via HTTP(S) or FTP)
- **ssh <username>@<host>** Establish an SSH connection to <host> with user <username>
- **scp <file> <user>@<host>:/remote/path** Copy <file> to a remote <host>

## Processes

- **ps ax** Output currently running processes
- **top** Display live information about curently running processes
- **kill <pid>** Quit process with ID <pid>

## Getting Help

**<command> --help**

## Keyboard Shortcuts

- **CTRL + A** moves caret to the beggining
- **CTRL + K** moves caret to the end of the line
- **CTRL + E** deletes all characters after
- **CTRL + U** deletes all characters infront of
- **CTRL + L** clears the screen
- **CTRL + C** abort a running command

## Home Folder

the ~ character addresses the path of your home folder
**cd /Users/your-username/projects/**
turns into
**cd ~/projects**

**whoami** 
Retrieves your username

## File Permissions

Unix Systems file permissions set using 3 digits 
(permissions of owning user, second for its group, and third for anyone else)
Add up the desired access rights for each digit as following:

4- access/read (r)
2- modify/write(w)
1- execute(x)

For Example 755 means "rwx" for owner and "rx for both group and anyone.

## The Tab Key

Autocompletes directory paths that you've written

## Combining Commands

use the ; if you want to run more then one command at once 
code placed after the && operator will only be run if the previous command completes successfully.
the || operator only continues if the previous command fails

**cd ~videos || mkdir ~/videos**
this command will only create the folder if the cd command fails

## Arrow Keys

ARROW UP
step through the last called command, ARROW DOWN to go back in the command call history

calling the history command prints a list of all recent commands 

## Directing Output

> operator will direct output to a file
| operator will direct output to another command 
Example:
This command will list the current directorys contents, search the list for PDF files and display the results with the less command 
**dir | findstr ".pdf" | more** 

## More Commands

- **ASSOC**
Displays or modifies file extension associations
- **ATTRIB**
Displays or changes file attributes
- **BREAK**
Sets or clears extended CTRL+C checking 
- **BCDBOOT**
used to copy critical files to the system partition and to create a new system BCD storage 
- **BCDEDIT** 
Sets properties in boot database to control boot loading
- **CACLS**
Shows or changes access control lists (ACLS) of files
- **CALL**
Calls a batch program from another
- **CHCP**
Displays or sets the active page code number 
- **CHKDSK**
Checks a disk and displays a status report
- **CHKNTFS**
Displays or modifies the checking of disk at boot time 
- **CHOICE**
Batch file command that allows users to select from a set of options 
- **CIPHER**
Displays or alters the encryption of directories (files) on NTFS partitions 
- **CLIP**
Redirects output off another command to the Windows clipboard 
- **CMDKEY**
Creates, Lists, and deletes stored usernames and passwords or credentials 
- **COLOR** 
Sets the default console colors 
- **COMP**
Compares the contents of 2 files or sets of files byte by byte 
- **COMPACT** 
Displays or alters the compression of files on NTSF partitions 
- **CONVERT**
Converts DAT volumes to NTFS. You cannot convert the current drive.
- **COPY**
Copies one or more files to another location 
- **DATE** 
Displays or sets the date
- **DEFRAG**
disk defragment accessory
- **DEL**
Deletes one or more files
- **DISKCOMP**
Compares the contents or 2 floppy disks
- **DISKCOPY**
Copies the contents of one floppy disk to another 
- **DISKPART**
Display or configures Disk Partition Properties 
- **DOSKEY**
Edits command lines, recalls Windows Commands, and creates macros
- **DRIVERQUERY**
Displays current device driver status and properties 
- **ECHO** 
Displays Messages, or turns commands echoing on or off
- **ENDLOCAL**
Ends localiztion of environment changes in  a batch file 
- **ERASE**
Deletes one or more files 
- **EXIT**
Quits and closes the command shell
- **EXPAND** 
Expands compressed files 
- **FC**
Comapares two files or sets of files and displays the differences between them 
- **FIND**  
Searches for a text string in a file or files 
- **FOR** 
Runs a specified command for each item in a set 
- **FORFILES**
Selects files in a folder for batch processing 
- **FORMAT** 
Formats a disc for use with Windows 
- **FSUTIL**
Displays or configures the file system properties 
- **FTYPE**
Displays or modifies fie types used in file extensions associations 
- **GOTO** 
Directs the Windows Command interpreter to a labeled line in a batch program
- **GPRESULT**
Display the Group Policy Information for machine or User 
- **GRAFTABL**
Enables Windows to display an extended character set in graphics mode
- **ICACLS**
Display, Modify, Backup, or Restore ACL's for files and directories 
- **IF** 
Performs conditional processing in batch programs 
- **LABEL**
Creates, changes or deletes the volume label of a disk 
- **MD** 
Makes a directory 
- **MKLINK** 
Creates Symbolic Links and Hard Links 
- **MODE** 
Configures a system device
- **MORE**
Displays the output one screen at a time 
- **MOVE**
Moves one or more files from one directory to another directory 
- **OPENFILES**
Queries, displays, or disconnects open files or files opened by network users 
- **PATH** 
Displays or sets a search path for exe files 
- **PAUSE**
Suspends processing of a batch file 
- **POPD** 
Restores the previous value of the current directory saved by PUSHD
- **PRINT**
prints a text file
- **PROMPT** 
Changes the Windows command Prompt 
- **PUSHD**
Saves the current directory then changes it  
- **RD**
Removes a directory
- **RECOVER**
Recovers readable information from a bad or defective disk 
- **REM** 
Designates comments (remarks) in a batch file 
- **REN**
Renames a file or files 
- **REPLACE**
replaces files
- **ROBOCOPY**
Advanced utility to copy files and directory trees
- **SET**
Displays, Sets, or Removes environment variables for current session
- **SETLOCAL** 
Begins localization of environment changes in a batch file 
- **SETX**
Sets Environmental Variables 
- **SC**
Displays or configures services (background processes)
- **SCHTASKS**
Schedules commands and programs to run on a computer 
- **SHIFT** 
Shifts the position of replaceable parameters in batch files 
- **SHUTDOWN** 
Allows proper local or remote shutdown of machine
- **SORT**
Sorts Input
- **START** 
Starts a seperate window to run a specified programs or command 
- **SUBST**
Associates a path with a drive Letter
- **SYSTEMINFO**
Displays machine specific properties and configuration
- **TAKEOWN**
Allows an administrator to take ownership of a file 
- **TASKLIST**
Displays all currently running tasks including services 
- **TASKKILL**
Kil running process or applications
- **TIME**
Display or sets the system time
- **TIMEOUT** 
Pauses the command processsor for the specified number of seconds
- **TITLE**
Sets the window title for a CMD.exe session
- **TREE** 
Graphically displays the directory structure of a drove or path
- **TYPE**
Displays the contents of a text file
- **VER**
Displays the windows version
- **VERIFY** 
Tells Windows whether or verify that your files are written correctly to a disk 
- **VOL** 
Displays a disk olume label and serial number
- **VSSADMIN**
Valume Shadow Copy Service Administration tool 
- **WHERE** 
Displays the locations of files that match a search pattern 
- **WMIC**
Displays the WMI information inside interactive command shell
- **XCOPY**
Copies files and directory trees 