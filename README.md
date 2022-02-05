# synchronic
A basic shell script which uses rsync to create incremental local backups.

## Installation
1. Ensure that [rsync](https://rsync.samba.org/) is installed on your system.  
On Debian or Ubuntu–based distros, this can be done by simplying typing  
`sudo apt install rsync`  
in a terminal.
2. Edit the locations.txt file such that each line in the file  
contains two absolute path strings: the path of the source folder,  
and the path of the target folder separated by a space.  
For example:  
`
/home/john/Documents /run/media/john/BackupDrive/Documents
/home/john/Games /run/media/John/BackupDrive/Games
`  
`
⋮
`
3. Place this script and the locations.txt file into  
a folder which is in your PATH variable.  
For example:
    * Suppose you extracted the zipped folder into a folder with path `/home/<your_username>/<path_to_folder>`.  
    * Adding this folder depends to you PATH variable is different for each shell.  
    For the Bash shell, edit the .profile file located in your home  folder; in this example, the absolute path to the file is  
    `/home/<your_username>/.profile`
    For any other shell, check its documentation.
    * Open the `.profile` file and append the following line to it:
    `PATH=$PATH:/home/<your_username>/<path_to_folder>`  
    **Replace <your_username> and <path_to_folder> with your  
    own username and path to the folder.

## Configuration
1. Edit the locations.txt file. Each line in this file  
must contain two absolute path strings:
    - The first string is the absolute path of the source folder/file.  
    This is the folder/file that you want to back up.
    - The second string is the absolute path of the target folder/file.  
    This is the folder/file that you want as a copy of the original.
2. Place the locations.txt file in the folder where you placed  
the synchronic script.

## Usage
1. You need to install rsync and edit the locations.txt file before  
attempting to run the script.
2. Open a terminal and type synchronic.  
`$ synchronic`

## Informational
* The script does not delete existing content in the target folder, but only  
adds newer content to the same.
* Be careful when editing the `locations.txt` file. Ensure that the source and  
target folders/files are correct.