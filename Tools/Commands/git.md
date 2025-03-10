# ..: git, Global Information Tracker :..

You **NEED** to know how to use ``git``.

This command allows you to post your code on the intra (among other things).

The options you need to know are :
- ``git init`` - the current folder will be considered as a git repository
- ``git clone url`` - clone the giving git url (when you register for a project, you will have a link for this)
- ``git add file1 file2 ...`` - the specified file(s) will be included in your next commit
- ``git commit`` - commit the file and prepare the push. it's required to put a message so add the parameter ``-m "text"`` to specify the commit message, commits are local before push them
- ``git push`` - the files you added in all of your commit will be pushed to the server. Do this to also save your files if you ever have trouble with your session, your files will be saved in the server
- ``git status`` - the file you added with ``git add`` and the file you forgot to add will be shown

**If you are in exam, this part does not concern you.**

If you don't want to make your life difficult, register to a project and use :
- ``git clone project_url``

This way
you avoid manipulation of the upstream and your current dir will automatically push to the 42 Server.

When you ``git init``, git does not know where to push. So here what you need to do :
- add your files and create a commit (or multiple your choice)
- ``git remote add origin {url}`` - will tell you git to push to this URL (found on your project page)
- ``git push --set-upstream origin master`` - to push to the ``master`` branch

After this you can use ``git commit -m "message"`` then ``git push`` and you will be good to go.
