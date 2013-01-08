gitintosh
=========

Simple wrapper to check access to git repositories when using SSH protocol


Installation
------------

Install Gitintosh where you want, usely into /opt/gitintosh. After Dazzle initialization, edit the /etc/passwd file to change the shell for the user storage. Replace it with /bin/sh.

Gitintosh use SSH functionnality to override the user command by the one found into the authorized_keys file.


Simple usage
------------

Usely, when linking a user to your SparkleShare host, your will use Dazzle like this:

    # dazzle link

This works great, but you can't control who access to projects.

Instead of using Dazzle to link a user, you could now use Gitintosh to do the same thing, like the following:

    # gitintosh link

Gitintosh will ask you for the SparkleShare link code, and the valid user email address corresponding to this link code. Then, it will do the same as Dazzle does: ading a the link code to the authorized_keys file into /home/storage/.ssh. But, it will also prefix the link code with this additionnal options (user1 is an example):

    command="GIT_USER=user1 /path/to/gitintosh exec",no-port-forwarding,no-agent-forwarding,no-X11-forwarding,no-pty

Once the link is created, you should complete the user file located into the conf directory of the project. The syntax is relatively simple:

    user1;/home/storage/user1

If you want user1 could access to the project owned by user2, then simply follow this example:

    user1;/home/storage/user1,/home/storage/user2

