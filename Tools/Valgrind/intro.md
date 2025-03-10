# ..: valgrind, the gate of dead warriors :..

**If you don't know what the ``malloc`` function does, don't bother reading this part.**

After going through the Norm, let's take a look at where you can fail easily: memory leaks.

Here's a little trick for you, if a project allows ``malloc`` but doesn't talk about ``free``, you don't need to use valgrind.

So, now that you are sure that you need to use valgrind, let's learn.

Valgrind is a memory checker tool. It is used to search for leaks in your code.

When you use the ``malloc`` function, you 'reserve' space in your memory.
The ``free`` function undo this operation to allow this space to be used again.
Forgetting to ``free`` memory space will create leaks,
even is you have only one leaked byte in your project, **your final score will be 0**.

Valgrind is your best friend, or a black crow depending on when you execute it.
It will show you how many bytes you lost during the execution of your project.
Don't be afraid about big numbers, a ``malloc`` in a loop can do a lot.

If you are here, you know how to compile. When you compile your project, add the ``-g2`` (``-g3`` is overkill) flag.
Then when using valgrind add the ``--leak-check=full`` flag. Valgrind will print the lines where the ``malloc`` function was used and so you can deduct which var was not freed.

For a quick example of a debugging session about leaks, look here :
- [ex1](./ex1.md)

If you feel like adding an example to this guide, create an issue, and we will talk about it!
