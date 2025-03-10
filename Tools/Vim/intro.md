# VIM, Vi IMproved

Vim was created to enhance the basic unix editor ``vi``.

## Summary
- [Configuration](#configuration)
- [Getting started](#getting-started)
- [Vim Shortcuts](#vim-shortcuts)

### Configuration

The Vim configuration can be huge.
If you install plug-ins,
then add custom commands, and so on your files will be hundreds of lines.

**During the Piscine, we advise you to not over modify your config file.
Try to keep your environment as close as the one in exam to avoid being lost with default parameters**.

To modify your configuration, you'll need to take a look at the ``vimrc`` file.

In a terminal :
```bash
vim ~/.vimrc
```
If the file was not already created, vim will create it for you. Yes, you need to put the ``.`` before the ``vimrc``.

Now customize the config file to your liking!

The doc can be tricky to find but work with the help of your cluster. Google has also a lot of answers and the ``:options`` in Vim will also help you.

**Tips:** 
- if you encounter trouble aligning your variables, you should look at the list of possible configurations for your Vim; some tabs are not stopping properly
- you are encouraged to compare and share your knowledge about this with your neighbors and friends, keep in mind you will succeed with them

### Getting started

Vim is now your favorite terminal-based text editor.
You start by hating on it for the strange way of handling files,
but you get used to it, and now you have Vim shortcuts in your IDE.

When you open a file, you are in normal mode. There are three main modes :
- Normal (``Esc`` to go back to this mode), it's like viewing a file, you can use some shortcuts in this mode, you can also type commands
- Visual (``v`` key), it's the mode to select stuff, copy, and so on
- Insert (``i`` key), you can now edit the file, use arrows and

You can also use the mode ``Replace``,
but it's not that useful and few people use it anyway.

If you are not in ``Insert`` mode, you won't be able to change anything.
When entering ``Visual`` mode, the selection starts where the cursor currently is, that's why the ``Normal`` mode exists.

### Vim Shortcuts

This page is already long enough, so here is the file you might download or copy: 
- [Shortcuts file](./shortcuts.md)
