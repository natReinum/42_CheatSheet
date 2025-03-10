# Vim Shortcuts

In ``Normal`` mode :
- ``i`` - enter ``Insert`` mode
- ``v`` - enter ``Visual`` mode
- ``u`` - undo, like ``Ctrl + Z`` in IDEs and most software like Word
- ``:w`` - write, will save the file where the cursor is
- ``:q`` - quit, quit Vim, but does not save (you will see a warning or use ``:wq``)
- ``!`` - forces an operation, like force quit ``:q!``
- ``:!shell_cmd`` - allows you to execute shell commands in vim like ``:!ls``
- ``:x`` - it's like ``:wq``
- ``:{range}s/pattern/replacement/{flag}`` - allow you to replace in your file a pattern, this one deserves a section :
    - ``{range}`` - correspond to the lines to look for :
        -  ``%`` is the entire file
        - ``start,end`` are the line to start and end the search (``1,5`` for exemple for lines 1 to 5)
        - ``.`` or no ``{range}`` is current line
    - ``pattern`` is the regexp pattern to look for (cf. [grep](../Commands/grep.md))
    -  ``replacement`` is the characters to replace the pattern with
    - ``{flag}`` can be combined :
        - ``g`` means global replacement (in the line)
        - ``c`` to confirm the change (keys will be displayed at the bottom)
        - ``i`` case-insensitive matching (if you don't know what it means Google it)
        - ``I`` case-sensitive matching
        - ``e`` avoid display of errors
- ``?characters`` search for the characters you entered in your file
- ``:line_number`` - go to ``line_number`` (``:42`` will teleport the cursor to line 42)
- ``:vs file_path`` - vertical split, puts the current file on the right and the new file on the left
- ``:sp file_path`` - horizontal split, puts the current file at the bottom and the new file on the top (you can mix it with ``:vs`` as much as you want)
- ``Ctrl + w w`` - navigate between splits in a clockwise pattern
- ``Ctrl + w W`` - navigate between splits in a counter-clockwise pattern
- ``Ctrl + w h`` - move to the window on the left
- ``Ctrl + w j`` - move to the window below
- ``Ctrl + w k`` - move to the window above
- ``Ctrl + w l`` - move to the window on the right.
- ``Ctrl + z`` - puts vim as a background task (to resume, in the same terminal type ``fg``)
- ``:tabnew file_path`` - opens a file in a new tab
- ``g t`` - go to next tab
- ``g T`` - go to previous tab
- ``yy`` - copy current line
- ``dd`` - delete current line (maintain second ``d`` to keep deleting)
- ``p`` - paste copied **OR** deleted line (if you ``yy`` then ``dd`` a different line you will paste the second one)
- ``PageUp``/``PgUp`` moves the cursor up a page
- ``PageDown``/``PgDn`` moves to cursor down a page

In ``Visual`` mode:
- ``Esc`` go back to ``Normal`` mode
- ``y`` copy
- ``d`` delete
- ``arrows`` moves the end of your cursor

For more shortcuts, google them.
