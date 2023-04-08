### Anatomy of a File or Directory

A quick way to look at a lot of interesting information is to use the following command

```shell
$ ls -lh
```

Which in my home folder will

```shell
➜  ~ ls -lh
total 136K
drwxr-xr-x  3 xavierperret xavierperret 4.0K Sep 21 12:56  Android
drwxr-xr-x  5 xavierperret xavierperret 4.0K Sep 30 18:16  AndroidStudioProjects
...
-rw-rw-r--  1 xavierperret xavierperret   85 Oct 14 14:26  bim.txt
-rw-rw-r--  1 xavierperret xavierperret   26 Sep 30 14:52  courses.txt
drwxr-xr-x  2 xavierperret xavierperret 4.0K Oct 14 18:06  Desktop
....
rw-rw-r--  1 xavierperret xavierperret   85 Oct  6 20:44  file.txt
drwxrwxr-x  8 xavierperret xavierperret 4.0K Sep 21 15:10  flutter
...
rw-rw-r--  1 xavierperret xavierperret   24 Oct  7 16:41  perret_xavier
-rw-r--r--  1 xavierperret xavierperret 4.8K Oct  7 14:38  tem
rwxrwxr-x  7 xavierperret xavierperret 4.0K Oct 15 08:30  wrk
drwxr-xr-x  9 xavierperret xavierperret 4.0K Oct 19 15:24  Zotero
➜  ~ 
```

Let's look at the anatomy of a file

```shell
drwxr-xr-x  3 xavierperret xavierperret 4.0K Sep 21 12:56  Android
-rw-r--r--  1 xavierperret xavierperret 4.8K Oct  7 14:38  tem
```

The first piece of information indicates the type of [[File]]

- `-` or ` ` => regular file
- `d` => directory
- `c` => character file
- `b` => block

Then, the rights are displayed[^1]

Then the owner, group owner, size, dates and time and finally the name of the [[File]] or [[Directory]].
