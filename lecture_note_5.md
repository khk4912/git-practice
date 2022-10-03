# Lab 5 (CLI 2)

## I/O Redirection

Using `>` after a command can redirect the standard output to a file.

```sh
❯ ls -la > file_list.txt
❯ cat file_list.txt
total 40
drwxr-xr-x   9 khk4912  staff   288 10  3 19:44 .
drwxr-xr-x  35 khk4912  staff  1120 10  2 23:28 ..
drwxr-xr-x  15 khk4912  staff   480 10  3 19:39 .git
-rw-r--r--   1 khk4912  staff  1059  9  7 15:50 LICENSE
-rw-r--r--   1 khk4912  staff   123  9  7 16:05 README.md
-rw-r--r--   1 khk4912  staff     0 10  3 19:44 file_list.txt
-rw-r--r--   1 khk4912  staff    13  9 23 01:13 hello
-rw-r--r--   1 khk4912  staff  2350  9 23 01:15 lecture_note_4.md
-rw-r--r--   1 khk4912  staff   136 10  3 19:44 lecture_note_5.md
```

Using `>>` appends output to an existing file if it already exists or create a new file if it does not exist.

```sh
❯ echo Hello there! >> hello.txt
❯ echo test >> hello.txt
❯
❯ cat hello.txt
Hello there!
test
```

Using `<` after a command can redirect the standard input from a file.

```sh
❯ cat words.txt
school
class
home
new
lecture
❯
❯
❯ sort < words.txt
class
home
lecture
new
school
```

Or you can even use both `>` and `<` at the same time.

```sh
❯ sort < words.txt > sorted_words.txt
❯
❯ cat sorted_words.txt
class
home
lecture
new
school
```

## Pipelines (|)

Pipelines are a way to chain commands together. The output of one command is used as the input of the next command.

```sh
❯ cat words.txt | sort
class
home
lecture
new
school
```

## Special Characters

- `*`: all files and directories in the current directory
- `~`: home directory

```sh
❯ echo *
LICENSE README.md hello lecture_note_4.md lecture_note_5.md sorted_words.txt words.txt
❯
❯ echo ~
/Users/khk4912
```

- `\`: used to ignore line change in command

```sh
❯ ls \
> -l
total 56
-rw-r--r--  1 khk4912  staff  1059  9  7 15:50 LICENSE
-rw-r--r--  1 khk4912  staff   123  9  7 16:05 README.md
-rw-r--r--  1 khk4912  staff    13  9 23 01:13 hello
-rw-r--r--  1 khk4912  staff  2350  9 23 01:15 lecture_note_4.md
-rw-r--r--  1 khk4912  staff  1716 10  3 19:53 lecture_note_5.md
-rw-r--r--  1 khk4912  staff    30 10  3 19:50 sorted_words.txt
-rw-r--r--  1 khk4912  staff    30 10  3 19:49 words.txt
```

## Permissions

All files and directories have a permission assigned differently for the owner, group, and others.

The permission is represented by 3 characters.

- `r`: read
- `w`: write
- `x`: execute

The first 3 characters represent the owner's permission, the second 3 characters represent the group's permission, and the last 3 characters represent the others' permission.

ex) `-rw-r--r--` means that the owner has read and write permissions, the group and others have only read permission.

You can change the permission of a file or directory using `chmod`.

```sh
❯ ls -l hello
-rw-r--r--  1 khk4912  staff  13  9 23 01:13 hello
❯
❯ chmod 600 hello
❯ ls -l hello
-rw-------  1 khk4912  staff  13  9 23 01:13 hello
```

The digits are represented as follows.

```
rwx rwx rwx -> 111 111 111
rwx r-- r-- -> 111 100 100

rwx -> 111 -> 7
r-- -> 100 -> 4
```

## Superuser

A superuser has all system adminstrative privileges.  
Put `sudo` before the command can run the command as a superuser.

```sh
❯ sudo cat hello
Hello World
```

## Shell Script

A shell script is a file that contains a list of commands.

```sh
❯ vi myscript.sh
❯
❯ cat myscript.sh
echo "Hello, Shell Script!"
❯
❯ sh myscript.sh
Hello, Shell Script!
```
