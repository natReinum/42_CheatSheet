# Ex1

In this example, we will debug a simple main. Remember that your personal experience is far more important than what the internet will tell you. Encounter errors and bugs; that's how you become a greater programmer.

**This example is not a part of any project.**

main.c
```C++
#include <stdlib.h>
#include <stdio.h>

int main(int argc, char **argv)
{
    char    *param_array;
    
    if (argc < 2)
        return (1);
    param_array = malloc((argc - 1) * sizeof(int));
    if (!param_array)
        return (1);
    *param_array = **++argv;
    printf("%c\n", param_array[0]);
    return (0);
}
```

Let's compile with flags :
```bash
cc -Werror -Wall -Wextra -g2 main.c -o leaks
```

Then valgrind the output :
```bash
valgrind --leak-check=full ./leaks "Hey"
```

We will just look at the interesting lines, so keep in mind this is **NOT** the exact output of valgrind ;
```
==21559== HEAP SUMMARY:
==21559==     in use at exit: 4 bytes in 1 blocks
==21559==   total heap usage: 2 allocs, 1 frees, 1,028 bytes allocated
==21559== 
==21559== 4 bytes in 1 blocks are definitely lost in loss record 1 of 1
==21559==    at 0x4846828: malloc (in /usr/libexec/valgrind/vgpreload_memcheck-amd64-linux.so)
==21559==    by 0x10919C: main (main.c:10)
==21559== 
==21559== LEAK SUMMARY:
==21559==    definitely lost: 4 bytes in 1 blocks
```

We can observe that we have lost four bytes.
If we want to get technical, we lost a ``sizeof(int)`` because ``argc - 1 = 1`` in our example above.

We lost our memory from a ``malloc`` at the address ``0x10919C`` or,
using words we comprehend, in the file ``main.c`` at line 10.

Line 10 :
```C++
    param_array = malloc((argc - 1) * sizeof(int));
```

So, here is the corrected version of ``main.c`` :
```C++
#include <stdlib.h>
#include <stdio.h>

int main(int argc, char **argv)
{
    char    **param_array;
    
    if (argc < 2)
        return (1);
    param_array = malloc((argc - 1) * sizeof(int));
    if (!param_array)
        return (1);
    *param_array = **++argv;
    printf("%c\n", param_array[0]);
    free(param_array); // ####### our fix #######
    return (0);
}
```

Let's run our test again :
```bash
cc -Werror -Wall -Wextra -g2 main.c -o noleaks | valgrind --leak-check=full ./noleaks "Hey"
```

No leaks !!
```
==22530== HEAP SUMMARY:
==22530==     in use at exit: 0 bytes in 0 blocks
==22530==   total heap usage: 2 allocs, 2 frees, 1,028 bytes allocated
```

Happy debug. It's not always that simple, but with perseverance you can do it!
