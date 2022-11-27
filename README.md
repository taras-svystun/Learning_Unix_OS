This the summary of the book "Learning the Unix Operating System" 5th edition by Jerry Peek, Grace Todino, John Strang.

# Chapter 1. Getting started

Useful commands:

1. ```date```
2. ```w```
3. ```who```
4. ```who am i```
5. CTRL + U -- erases the whole input line.
6. CTRL + D -- kills the current process or even terminal. The same as ```exit```.


# Chapter 3. The Unix Filesystem

1. ```ls -l``` -- to see the detailed info about the files (permissions, owners, size, etc.)
2. ```chmod``` -- to change the permissions of files and directories.
3. ```ls -R``` -- to print recorsively all subdirectories.
4. ```ls --color``` -- to print dirs and files in different colors.
5. ```less *filename*``` -- to see one-page of the file contents.
6. ```chmod *ugo* +-= *rwx*``` -- change the permissions of the file.


# Chapter 4. File management

1. ```ex*``` -- to match all files starting with "ex" of arbitrary length. Also can match directories: ```ls */summary``` will print all "summary" files from all possible dirs.
2. ```ta?as``` -- will match all files, like: taras, tawas, tapas, etc. Any character instead of ? mark.
3. ```[]``` -- to match list of possible characters. E.g. ```chap[1-5]``` will match chap3 but not chap7. Or ```ex[aA]``` will match either exa or exA.
4. ```cp ../abc/ch1 ../abc/ch2 ../abc/ch3 new_dir``` will copy 3 files into "new_dir" directory. The same as ```cp ../abc/ch[1-3] new_dir```. -i flag to ask whether to replace the existing file with same name.
5. Be carefull with the ```cp -r``` command. If you will copy dir into itself, the process will last forever, until the lack of memory.
6. ```mv``` command to move or rename files.
7. ```find``` command to find.
* -delete -- to delete found files.
* -group -- find only files from group names.
* -maxdepth, -mindepth -- depth of the search.
* -name, -iname -- name of the file in quoting marks. Allow for wildcards.
* -print
* -type -- type of file. block, character_special, directory, file, link, p, socket.
* -user uname -- finds only files that belong to uname.
* \! -- to negate. Like ```find / \! -name "*.c" -print``` -- Print out a list of all the files whose names do not end in .c.

8. ```rm``` -- to remove. Easy mistakes are either "rm *" will remove all files from the working_dir or "rm c *" (accidential space between "c" and "*") will remove all files named c and ALL files.
9. ```pr -t``` -- ptint file contents without headers and/or margins. Same as "cat".
