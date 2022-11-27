This the summary of the book "Learning the Unix Operating System" 5th edition by Jerry Peek, Grace Todino, John Strang.

# Chapter 1. Getting started

1. `date`
2. `w`
3. ```who```
4. ```who am i```
5. CTRL + U -- erases the whole input line.
6. CTRL + D -- kills the current process or even terminal. The same as ```exit```.
7. `man` command allows to print the docs for any input command.

# Chapter 3. The Unix Filesystem

1. ```ls -l``` -- to see the detailed info about the files (permissions, owners, size, etc.)
2. ```chmod``` -- to change the permissions of files and directories.
3. ```ls -R``` -- to print recorsively all subdirectories.
4. ```ls --color``` -- to print dirs and files in different colors.
5. ```less *filename*``` -- to see one-page of the file contents.
6. `chmod (1) (2) (3) -- change the permissions of the file.
   - (1) which permission you want to change
     - `u` -- user.
     - `g` -- group.
     - `o` -- others.
   - (2) whether to
     - `+` -- add the permission.
     - `-` -- delete the permission.
     - `=` -- specify it exactly.
   - (3) what permissions you want to affect
     - `r` -- read.
     - `w` -- write.
     - `x` -- execute.


# Chapter 4. File management

1. ```ex*``` -- to match all files starting with "ex" of arbitrary length. Also can match directories: ```ls */summary``` will print all "summary" files from all possible dirs.
2. ```ta?as``` -- will match all files, like: taras, tawas, tapas, etc. Any character instead of ? mark.
3. ```[]``` -- to match list of possible characters. E.g. ```chap[1-5]``` will match chap3 but not chap7. Or ```ex[aA]``` will match either exa or exA.
4. ```cp ../abc/ch1 ../abc/ch2 ../abc/ch3 new_dir``` will copy 3 files into "new_dir" directory. The same as ```cp ../abc/ch[1-3] new_dir```. ```-i``` flag to ask whether to replace the existing file with same name.
5. Be carefull with the ```cp -r``` command. If you will copy dir into itself, the process will last forever, until the lack of memory.
6. ```mv``` command to move or rename files.
7. ```find``` command to find.
   * ```-delete``` -- to delete found files.
   * ```-group``` -- find only files from group names.
   * ```-maxdepth```, ```-mindepth``` -- depth of the search.
   * ```-name```, ```-iname``` -- name of the file in quoting marks. Allow for wildcards.
   * ```-print```
   * ```-type``` -- type of file. ```b```lock, ```c```haracter_special, ```d```irectory, ```f```ile, ```l```ink, ```p```, ```s```ocket.
   * ```-user uname``` -- finds only files that belong to uname.
   * ```\!``` -- to negate. Like ```find / \! -name "*.c" -print``` -- Print out a list of all the files whose names do not end in .c.

8. ```rm``` -- to remove. Easy mistakes are either ```rm *``` will remove all files from the working_dir or ```rm c *``` (accidential space between "c" and "\*") will remove all files named c and ALL files.
9. ```pr -t``` -- ptint file contents without headers and/or margins. Same as ```cat```.


# Chapter 5. Redirecting I/O

1. `< file` to give a file for program standrd input.
   - E.g. `mail abc@abs.com < to_do`

2. `>` operator if the program writes to its standard output you can make it write to a file.

   - E.g. `ls > ls_res` will write the result of `ls` command inside the "ls_res" file.
   - or such usage is possible: `cat > to_do` then write all you need, followed by ^D. Your writings are saved into "to_do" file.

3. `|` -- to send the output of one program to the input of another.

   - `ls -l | grep 'Aug'` -- to print all names that contain 'Aug'.
  
4. `grep` command.
   - `-c` -- print only count of files.
   - `-i` -- ihnore case.
   - `-n` -- include numbering.
   - `-v` -- select those lines which do not match the pattern.

5. `>>` same as `>` but not overwrites, but appends to existing file contents.
   - from 2. `cat >> to_do` input say "Drink a cup of water" followed by ^D.

6. `sort` sorts the contents of a file (not changing the original file).
   - `-n` -- sort numerically.
   - `-r` -- reverse ordering.
   - `-f` -- sort upper and lower case together.
   - `+x` -- ignore first x fields when sorting.

7. `ls -l | grep '4' | sort +4n` -- this command will print only files, which names contain '4' and then sort numerically by size (skips first 4 fields). Or add `| less` to recieve the output in a page format.
