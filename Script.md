---
date updated: 2021-10-20 15:56

---

Topic: #operating_system
Tags: #review #pn_2_1
Links: [[GNU Linux]]
Date Created: 20-10-21

---

# Script

## Script in few words

## Script in details

A [[Script]] is a text file, which can be executed with a command, containing a sequence of command [[Shell]].
This command is either `source` or if made executable with `chmod u+x script.sh` then `./script.sh`.

```shell
$ source script.sh
$ chmod u+x script.sh
$ ./script.sh
```

### Sha-bang

We should always start with **sha-bang**, that indicates with which [[Interpreter]] we want to run the script

```shell
#!/bin/bash
# here with bash
```

```shell
#!/bin/zsh
# here with zsh
```

Then we can without fear run

```shell
chmod u+x script.sh
./script.sh
```

### Variables

The scope of a variable is **global**.

```shell
foo=bar # assignment
echo foo
echo $foo
echo ${foo}
echo "${foo}bar"
```

### Conditions

```shell
if [ EXPRESSION ]; then
	foo
	...
else
	bar
	...
fi
```

```shell
#!/bin/sh echo "Please talk to me ..."
while : 
do 
	read INPUT_STRING 
	case $INPUT_STRING in 
		hello) 
			echo "Hello yourself!" 
			;; 
		bye) 
			echo "See you again!" break 
			;; 
		*) 
			echo "Sorry, I don't understand" 
			;;
	esac
done
echo 
echo "That's all folks!"
```

### Test

```shell
test EXPRESSION
# or the equivalent
[ EXPRESSION ]
```

| Syntax            | Action                            |
| ----------------- | --------------------------------- |
| `-e FILE`         | file exist ?                      |
| `-d FILE`         | file exist && is a file           |
| `-x FILE`         | file exist && is executable       |
| `-w FILE`         | file exist && is writable         |
| `FILE1 -nt FILE2` | file1 is more recent than file2 ? |
| `FILE1 -ot FILE2` | file1 is older than file2 ?       |

### More test

| Syntax               | Action                                      |
| -------------------- | ------------------------------------------- |
| `!EXPRESSION`        | Return `true` if `EXPRESSION` is `false`    |
| `EXPR1 -a EXPR2`     | Return `true` if `EXPR1` **and** `EXPR2`    |
| `EXPR1 -o EXPR2`     | Return `true` if `EXPR1` **or** `EXPR2`     |
| `STRING1 = STRING2`  | Return `true` if both strings are equal     |
| `STRING1 != STRING2` | Return `true` if both strings are not equal |

### Loop

```shell
for VAR in LIST; do
	foo $VAR
	...
done
```

A `LIST` can be

- [[Element]] separated by spaces, e.g. `for foo in bar1 bar2 bar3; do`
- Range `for I in {1..9}`
- Regular Expression for files `for FILE in *.txt`

### Substitute commands

A way to get the **result** of a command.

```shell
foo1=`echo bar1`
foo2=$(echo bar2)

foo3=`CMD OPTIONS ARGUMENTS` 
foo4=$(CMD OPTIONS ARGUMENTS)
```

### Return of command

A way to get the **return code** of a command

```shell
ls -lh
RES=$? # get the RETURN CODE of last command
```

### Arguments

```shell
echo $0 # script name
echo $1 # first argument
echo $2 # second argument
... # ...
echo $@ # list of parameters without $0
```

### Functions

Functions don't have return, but one can use **global variables** or **substitution of commands**

```shell
function foo {
	echo bar
	echo "$1" # access args passed to function
	echo "$2"
}
foo bim bam # bim and bam are two arguments passed
res=$(foo bim bam)
```

### Exercise

Write a script that

- Delete content of folder `data/backup`
- Copy every file `*.txt` and `*.dat` from `data/` to `data/backup`
- Change file permission of copied file so that there is just reading right to user and group

```shell
rm -f data/backup/* # delete content of folder `data/backup`
cp data/*.txt data/*.dat data/backup/ # copy *.txt & *.dat from data/ -> data/backup
chmod 440 data/backup/*
```

Now with variables

```shell
#!/bin/bash

SOURCE=data/
DESTINATION=data/backup/

rm -f ${DESTINATION}* 
cp ${SOURCE}*.txt ${SOURCE}*.dat ${DESTINATION} 
chmod 440 ${DESTINATION}/*
```

Now with conditions and test

```shell
#!/bin/bash

SOURCE=data/
DESTINATION=data/backup/

if [ -d ${DESTINATION} ]; then
  rm -f ${DESTINATION}* 
else
  mkdir -p ${DESTINATION}
fi
  

cp ${SOURCE}*.txt ${SOURCE}*.dat ${DESTINATION} 
chmod 439 ${DESTINATION}/*
```

Now with loops

```shell
#!/bin/bash

SOURCE=data/
DESTINATION=data/backup/

if [ -d ${DESTINATION} ]; then
  rm -f ${DESTINATION}*
else
  mkdir -p ${DESTINATION}
fi

for FILE in ${SOURCE}*.txt ${SOURCE}*.dat; do
  cp ${FILE} ${DESTINATION}
  echo "Copied ${FILE} from ${SOURCE} to ${DESTINATION}"
done

chmod 440 ${DESTINATION}/*
```

Now with arguments

```shell
#!/bin/bash

SOURCE=$1
DESTINATION=$2

if [ -d ${DESTINATION} ]; then
  rm -f ${DESTINATION}* 
else
  mkdir -p ${DESTINATION}
fi
  
for FILE in ${SOURCE}*.txt ${SOURCE}*.dat; do
  cp ${FILE} ${DESTINATION}
  echo "Copied ${FILE} from ${SOURCE} to ${DESTINATION}"
done

chmod 440 ${DESTINATION}/*
```

Now with function

```shell
#!/bin/bash

SOURCE=$1
DESTINATION=$2

if [ -d ${DESTINATION} ]; then
  echo "Clearing content of folder @ ${DESTINATION}"
  rm -f ${DESTINATION}*
else
  echo "Creating folder @ ${DESTINATION}"
  mkdir -p ${DESTINATION}
fi

function backup {
  for FILE in $1*.txt $1*.dat; do
    cp ${FILE} $2
    echo "Copied ${FILE} from $1 to $2"
  done

  chmod 440 $2/*
}

backup $SOURCE $DESTINATION
```

## References

- [[ISC-332 - Programmation système]]
- <https://www.shellscript.sh/case.html>
