gitintosh
=========

Simple wrapper to check access to git repositories when using SSH protocol


Simple usage
------------

To make it work, prefix lines into the authorized_keys by the following options:

  command="/path/to/gitintosh exec GIT_USER=user1",no-port-forwarding,no-agent-forwarding,no-X11-forwarding,no-pty

Then create the file /path/to/gitintosh/conf/user like the following:

  user1;/home/storage/user1



