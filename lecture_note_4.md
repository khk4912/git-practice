# Lab 4 Lecture Note

## What is Shell?

Shell is an interface that allows users to communicate with kernel.  
User runs applications and give commands through shell.

## Basic shell commands

### pwd (print working directory)

`pwd` prints the current working directory.

```sh
❯ pwd
/Users/khk4912
```

### cd (change directory)

`cd` allows users to change the current working directory.

```sh
❯ pwd
/Users/khk4912
❯
❯ cd Desktop/temp-repo/
❯
❯ pwd
/Users/khk4912/Desktop/temp-repo
```

### ls (list)

`ls` lists computer files and directories.

```sh
❯ ls
CONSTANT.py     asd.py          logs            plot            views
LICENSE         commands        main.py         plot_gen.py
__pycache__     log.py          migration_db.py utils
```

- `-l` : shows detailed informations
- `-lh`: same as `-l` but shows file size in human readable format

```sh
❯ ls -l
total 40
-rw-r--r--  1 khk4912  staff   118  2 22  2022 constant.py
-rw-r--r--  1 khk4912  staff   113  2 22  2022 exceptions.py
-rw-r--r--  1 khk4912  staff  3516  2 22  2022 main.py
-rw-r--r--  1 khk4912  staff   163  2 22  2022 model.py
-rw-r--r--  1 khk4912  staff   159  2 22  2022 utils.py
❯
❯ ls -lh
total 40
-rw-r--r--  1 khk4912  staff   118B  2 22  2022 constant.py
-rw-r--r--  1 khk4912  staff   113B  2 22  2022 exceptions.py
-rw-r--r--  1 khk4912  staff   3.4K  2 22  2022 main.py
-rw-r--r--  1 khk4912  staff   163B  2 22  2022 model.py
-rw-r--r--  1 khk4912  staff   159B  2 22  2022 utils.py
```

### mv (move)

`mv` moves files or directories.  
It can be also used to rename files or directories.

```sh
❯ ls
1      1.cpp  1.dSYM
❯
❯ mv 1.cpp 1-a.cpp
❯
❯ ls
1       1-a.cpp 1.dSYM
```

### rm (remove)

`rm` removes files or directories.

```sh
❯ ls
1       1-a.cpp 1.dSYM
❯ rm 1
❯
❯ ls
1-a.cpp 1.dSYM
```

### mkdir (make directory)

`mkdir` makes directories.

```sh
❯ ls
1-a.cpp 1.dSYM
❯
❯ mkdir code
❯
❯ ls
1-a.cpp 1.dSYM  code
```

### help / man

`help` / `man` shows the manual of the command.

### Useful arguments

- `/` : root directory
- `.` : current directory
- '..' : upper-level directory

- `/[direcory name]`: absoulte path
- `./[directory name]`: relative path
- `../[directory name]`: relative path

```sh
❯ pwd
/Users/khk4912
❯
❯ cd .. # change to upper-level directory
❯ pwd
/Users
```
