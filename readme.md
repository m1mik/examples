https://overthewire.org/wargames/bandit
ssh bandit9@bandit.labs.overthewire.org -p 2220
#9 UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

`pwd` (print working directory)
`ls`, `ls -l` (table view), `ls -a` (all including hidden), `ls -al`, `ls -lh` (cast file size to human read format)
`ls -lR <folderName>` (list recursively for folderName)
ctrl+shift t (open terminal), alt + arrowUp (expand terminal)
/home/userName/folderName (change directory from the system directory root)
`whatis <commandName>` (e.g. `whatis nano` => - Nano's ANOther editor)
`touch <filename.extension>` (create file)
`echo "string content"`(display a line of text)
`echo "hello" > mytext.txt` (set string "hello" to mytext.txt)
`cat mytext.txt` (print content of mytext.txt)
`cat /etc/passwd > passwd.txt` (redicrect content of /etc/passwd file to passwd.txt file)
`mkdir <dirName>`
`cp <filename> <destination>` (copy <filename> to <destination>)
`mv <filename> <destination>` (move <filename> to <destination>)
`mv <fileName> <newFileName>` (rename file)
`rmdir` (remove directory)
ctrl + x (close file opened in NANO)

---

`vi <fileName>` (open file into VIM)
i (insert content to file opened via VIM)
:q! (close file opened via VIM)

---

`chmod <u (current user) | g (group) | o (other users) | a (all users)><= | +><rwx (read, write, execute)> <fileName>` (e.g. chmod u=rwx text.sh)
`chmod go=rwx text.sh` (set rwx for group and other users for text.sh)
`chmod go-wx text.sh` (drop wx perms. for group and other for text.sh)
r - 4, w - 2 , x - 1 (binary values for read, write, executable flags)
`cmod 444 text.sh` (set only read perms. for currentUser,group,otherUsers => -r--r--r-- )
`cmod 744 text.sh` (set rwx perms. for current user but only read perms. for group and otherUsers)
`cmod 777 -R <folderName>` (set all perms recusively to folderName and to all included files)
`sudo bash` (open terminal as a root user (super user do))
chown (change file owner and group | change ownhership of a file)
`chown root text.sh` (assing ownership for text.sh to the root user)
chgrp (change group)
`groups <userName>` => (e.g.
`groups mike`
mike: mike adm cdrom sudo dip lpadmin plugdev ...)
`chgrp root text.sh` (change group of text.sh file to root group)

---

grep (print lines matching a pattern and also HIGHLIGHT the text color)
man grep ("manual pages"; shows documentation for grep; it help you to find string patterns in the files)
`grep "my interest text" <directoryPath>` (find "my interest text" in directoryPath; !NB case sensitive by default; -i set ignore for case sensitive)
`cat /etc/passwd | grep "my text value"` (it will show only matched lines with "my text value" but not the entire content of /etc/passwd)

> ("greater" sign riderect output of the command to another place; e.g. cat /etc/passwd > ~/Desktop/text.txt)

## `ifconfig | grep inet` (shows inet from ifconfig)

locate (find file by name)
man locate (show manual for locate)
`locate /etc --all "passwd"` (show all findings of passwd within /etc folders)
`locate "passwd" | grep "/etc/passwd"` (same output but with highlighted text)
`locate --all "*.conf" | grep resolve` (find all .conf files wich contains resolve in path)
`locate --all -c proxychains` (-c shows number of matches with proxychains)

---

GET SYSTEM INFO:
`whoami` (username)
`hostname`
`sudo vim /etc/hostname`
`id` (user id)
`lsb_release -a` (utility which is show what system is in use; installed by default)
`cat /etc/os-release` (or cat /etc/\*release)
`lscpu` (info about cpu)
`uname` (sytem and kernel info)
`who` (username and time when logged in)

---

find (find utility)
`sudo find <path> -type <f | d> <<file|directory>Name>` (e.g. sudo find / -type f -name "proxychains.conf"
-size +1M (same search request but where file size is more than 1 megabyte)
)
`find . -type f -size 1033c ! -executable | xargs file` (find here file with size 1033 bytes which is not (! sign) executable and pipe with xargs)
(find for unique string which occures only once in file: `cat data.txt | sort | uniq -u`)
