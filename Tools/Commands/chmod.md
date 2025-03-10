# ..: chmod, change mode :..

This command defines who can read, write, and execute a file or a directory.
There are two ways of using this command
- using number notation
- using symbolic notation

For more information about this command, read the manual (``man``).

Number notation is a combination of three numbers :
- the first one represents the rights of the owner
- the second one represents the rights of the group
- the third one represents the rights of others

Each possible right corresponds to a number :
- 0: none
- 4: read
- 2: write
- 1: execute

You can combine them to give multiple accessibility like ``6 = 4 + 2`` is ``write + read``.

Example using number notation :

```bash
chmod 754 my_file
# gives the owner the rights to read, write and execute
# gives the group the rights to read and execute
# gives others the right to read
``` 

By mindful of who is allowed to read your files, you might have security issues.

Example with symbolic notation :

```bash
chmod u+x my_file
# gives the owner (u) the right to execute the file
```

The only parameter we will talk about is ``-R``.
It means recursive so when you use ``chmod`` on a directory it applies to each file of each subdirectory.

You should check the options as always with the command ``man``.
