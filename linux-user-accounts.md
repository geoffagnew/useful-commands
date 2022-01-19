# User accounts on Linux

- Linux uses a multi user model, where each human using the system can have their own account with separate files and settings.
- The same is true for software and services. Things like web servers or database servers, often run using their own user accounts.
- Usually, these human or service based accounts, use what are called `Standard accounts`. They can work with their own files, but they aren't allowed to make changes to the system, and they aren't allowed to make changes to files outside their own space.
- The Superuser, or `root` account can access any file on the system (and make system-wide changes). You can borrow the Superuser's privileges by using the `su` or `sudo` command.
- It's common to borrow the Superuser privileges to perform maintenance or install software.
- You should rarely, if ever, use a computer under the `root` account.

## Permissions
- File permissions can be numeric `755` or symbolic `rwxr-xr-x`
- In each case, the permissions are made of three groups: the user (`rwx`), the group (`r-x`), and a group representing all others (`r-x`).
- Each section represents the restrictions applied to the file for that audience.
- `chmod`, `chown`, and `chgrp` are commands used to change file permissions.
