# About SUID / SGID

## First understand linux permissions

Linux permissions display with numerical values or symbolic.

Numerical permissions - `650`

Symbolic permissions - `-rw-r-x---`

Normally permissions can be split into three parts; `user`, `group`, and `other`. As shown in the table below the first number / symbol is for the `user` while the second and third refer to the `group` and `other`.
|user|group|other|
|----|-----|-----|
|6|5|0|
|rw-|r-x|---|

>Note there is an extra `-` before the user symbolic permission this is to indicate file type. EG `-` for a file and `d` for a directory.

### Changing permissions in linux

To change permissions in linux you will use `chmod`. chmod will take numerical and symbolic permissions formats.

--------

Set 650 using symbolic syntax

```shell
chmod u=rw file.txt

chmod g=rx file.txt

chmod o=rwx file.txt
```

The symbolic method uses the following syntax:

```shell
chmod <WhoWhatWhich> <FILE/DIRECTORY>
```

Who - represents identities: u,g,o,a (user, group, other, all)
What - represents actions: +, -, = (add, remove, set exact)
Which - represents access levels: r, w, x (read, write, execute)

--------

Set 650 using numerical syntax

```shell
chmod 650 file.txt
```

The numerical method uses the following syntax:

```shell
chmod <###> <FILE/DIRECTORY>
```

Start at 0

If the `read` permission should be set, add 4

If the `write` permission should be set, add 2

If the `execute` permission should be set, add 1

--------

## What is SUID / SGID

The setUID bit allows for a user to run a program as a different user. The user that the program runs as will be the owner of the file that has the SUID bit set.

## How to identify SUID / SGID

Files with SUID set can be identified by looking at the file permissions.
EG: `ls -l /usr/bin/passwd`

```shell
-rwsr-xr-x 1 root root 68208 Jul 14 22:08 /usr/bin/passwd
```

Notice how the user permissions contain an `s` where `x` should be? If your terminal supports color than the file will normally also be red or be highlighted with red.

![Red Highlight of SUID file](../../.media/mfdsHlO.png)

To find files with SUID you can run the following command.

```shell
sudo find <DIRECTORY> -user root -perm -4000 -exec ls -ldb {} \;
```

## Sticky Bit

### What is a sticky bit

There is one other special permission to be aware of. The `t` or sticky bit permission. The sticky bit gets applied to directories. When applied the sticky bit prevents files contained in a sticky directory from being deleted by anyone other than the owner user/group or root

### How to identify a sticky bit

Directories with a `t` in place of the `other` `x` permission indicates that the directory has a sticky bit

```shell
ls -ld <DIRECTORY>
```

```shell
drwxrwxrwt. 9 root root 4096 Dec  6 12:58 /tmp/
```

## Setting special permissions on a file

You will use `chmod` again to modify special permissions.

------

Set special permissions using symbolic syntax

```shell
chmod g+s <FILE/DIRECTORY>

chmod u+s <FILE/DIRECTORY>

chmod +t <DIRECTORY>
```

-------

Set special permissions using numerical syntax

```shell
chmod 4<PERMISSIONS> <FILE/DIRECTORY>

chmod 2<PERMISSIONS> <FILE/DIRECTORY>

chmod 1<PERMISSIONS> <FILE/DIRECTORY>

chmod 0<PERMISSIONS> <FILE/DIRECTORY>
```

Start at 0

SUID = 4

SGID = 2

Sticky = 1

-------

>If you are not quite sure of the numerical / symbolic permissions on a file try the `stat` command
>
>```shell
>stat <FILENAME> | grep Access
>```

------
------
# Source Resources

[GTFO BINS](https://gtfobins.github.io/)

[TryHackMe! Abusing SETUID Binaries - Vulnversity](https://www.youtube.com/watch?v=hvYWCegfEZs)

[Linux SetUID, SetGID, Sticky Bit](https://www.youtube.com/watch?v=2gHp_CgUets)

[SUID SGID STICKY-BIT](https://www.redhat.com/sysadmin/suid-sgid-sticky-bit)