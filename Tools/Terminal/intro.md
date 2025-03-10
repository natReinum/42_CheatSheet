# Terminal

Your greatest ally and the most pleasant way of navigating in your system.

### Basics

Technically, the only command you need to know is ``man``.
'Man' is short for Manual.
It will display the documentation of the command you type next.

Exemple :
```bash
man valgrind
```

It will always be here for you when you need help with a command.

The shortcut to start a new terminal session is ``Ctrl + Alt + T``.
You can change the default terminal to the one you prefer in ``Settings → Keyboard → Shortcuts``

Use ``Tab`` for autocompletion (in ``fish``, the ``Tab`` key autocomplete the next word and ``Arrow Right`` complete the full sentence).

Small list of terminal emulator :
- ``fish``, great use of macros and shortcuts
- ``ohmyzsh``, has colors and easy navigation between directories
- ``GNOME Terminal``, basic but customizable
- ``Terminator``, multiple terminals in one window

### Commands

Let's go through the most important command and how the terminal behaves

When you start a terminal, by default, you start in your user directory, which is :
```bash
/home/your_user
```

It's the same when you open your explorer. From here, let's look at what you can do.

### Basic commands :
- [pwd](../Commands/pwd.md)
- [ls](../Commands/ls.md)
- [cd](../Commands/cd.md)
- [cat](../Commands/cat.md)
- [mkdir](../Commands/mkdir.md)
- [touch](../Commands/touch.md)
- [tree](../Commands/tree.md)
- [nautilus](../Commands/nautilus.md)
- [git](../Commands/git.md)

### Advanced commands :
- [chmod](../Commands/chmod.md)
- [find](../Commands/find.md)
- [grep](../Commands/grep.md)

### Useful To Know

Because this guide purpose is to help you throw the basics, let's look at specific characters in the terminal :
- ``~`` is used to replace ``/home/your_user``
- ``.`` means current directory
- ``..`` signify the previous directory, you can chain them (``../../..``)
- ``/`` is the root of your hard drive, you can find the system files and so on. In Clusters and Exams you are restrained so modify and sometimes read those files
- ``>`` redirect the output of the command on the left to something (usually a file) on the right
- ``|`` allows you to redirect the output of the previous command to the next one (``cmd1 | cmd2`` will behave like ``cmd2 output_cmd1``)
- ``&&`` will execute commands one after the other one but only if the precedent one succeed (``cmd1 && cmd2`` will execute ``cmd2`` only if ``cmd1`` does not fail)
- ``*`` is a very practical wildcard, it allows you to signify "everything" for exemple ``*.c`` means all ``.c`` files
- ``\`` is the escape character, it forces your terminal to identify the next character as a character and not a possible operator (``echo "Hello \"world\" !"`` will display ``Hellow "world" !``, try without backslashes and see how the terminal behave)
