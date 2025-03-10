# LLDB

The acronym means "Low Level Debugger."

It's invaluable if your code fails to execute properly, and you don't know why.

First you need to compile your program using the ``-g2`` (or ``-g3``) flag.

Exemple :
```bash
cc -Wall -Wextra -Werror -g3 your_prog.c -o your_executable
```

To be clear the ``-o output_name`` flag is optional.

If you don't use the ``-g2`` flag you will end up debugging the assembly of your code.
You don't know what it is? Keep your sanity, you don't want to learn about x64dbg, registers, and memory injections.

To start debugging, launch your program like so :
```bash
lldb your_executable param1 param2 param3
```

(You don't always have parameters, it's for this example)

You are now in the lldb program.
Here are the most useful shortcuts,
if you want an extended list, you can always google it :
- ``b {function_name}`` - breakpoint will stop the program when starting to execute the function you specified (``b main`` will debug starting the main function)
- ``q`` - quits
- ``r`` - run the program
- ``n`` - next line
- ``s`` - step into, if you are on a line without a function you coded, it will do nothing, otherwise the cursor will jump into your function
- ``gui`` - start the GUI (Graphical User Interface) of LLDB, in this mode ``n`` and ``s`` works, but you don't have to press entering, shortcuts are displayed at the start of the gui mode, to quit it, press ``Esc``

In GUI mode, you have three main parts.
On the bottom you have your variables and their value,
on the right you have the Threads,
don't be scared,
the part you will mostly look at is your code and your variables.

There are not a lot of useful tips to give other than :
- know what your functions should return
- are your variables initialized?
- is your malloc protected?
- do you free after you used your variable?
- are you sure you read the subject and understood it (I have never ever in my life forgotten to add the ``\n`` at the end of a line, yeah I didn't read the end of the subject)
