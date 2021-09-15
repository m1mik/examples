https://overthewire.org/wargames/bandit
ssh bandit9@bandit.labs.overthewire.org -p 2220
#9 UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

`pwd` (print working directory)<br/>
`ls`, `ls -l` (table view), `ls -a` (all including hidden), `ls -al`, `ls -lh` (cast file size to human read format)<br/>
`ls -lR <folderName>` (list recursively for folderName)<br/>
ctrl+shift t (open terminal), alt + arrowUp (expand terminal)<br/>
/home/userName/folderName (change directory from the system directory root)<br/>
`whatis <commandName>` (e.g. `whatis nano` => - Nano's ANOther editor)<br/>
`touch <filename.extension>` (create file)<br/>
`echo "string content"`(display a line of text)<br/>
`echo "hello" > mytext.txt` (set string "hello" to mytext.txt)<br/>
`cat mytext.txt` (print content of mytext.txt)<br/>
`cat /etc/passwd > passwd.txt` (redicrect content of /etc/passwd file to passwd.txt file)<br/>
`mkdir <dirName>`<br/>
`cp <filename> <destination>` (copy <filename> to <destination>)<br/>
`mv <filename> <destination>` (move <filename> to <destination>)<br/>
`mv <fileName> <newFileName>` (rename file)<br/>
`rmdir` (remove directory)<br/>
ctrl + x (close file opened in NANO)<br/>

---

`vi <fileName>` (open file into VIM)<br/>
i (insert content to file opened via VIM)<br/>
:q! (close file opened via VIM)<br/>

---

`chmod <u (current user) | g (group) | o (other users) | a (all users)><= | +><rwx (read, write, execute)> <fileName>` (e.g. chmod u=rwx text.sh)<br/>
`chmod go=rwx text.sh` (set rwx for group and other users for text.sh)<br/>
`chmod go-wx text.sh` (drop wx perms. for group and other for text.sh)<br/>
r - 4, w - 2 , x - 1 (binary values for read, write, executable flags)<br/>
`cmod 444 text.sh` (set only read perms. for currentUser,group,otherUsers => -r--r--r-- )<br/>
`cmod 744 text.sh` (set rwx perms. for current user but only read perms. for group and otherUsers)<br/>
`cmod 777 -R <folderName>` (set all perms recusively to folderName and to all included files)<br/>
`sudo bash` (open terminal as a root user (super user do))<br/>
chown (change file owner and group | change ownhership of a file)<br/>
`chown root text.sh` (assing ownership for text.sh to the root user)<br/>
chgrp (change group)<br/>
`groups <userName>` => (e.g.
`groups mike`
mike: mike adm cdrom sudo dip lpadmin plugdev ...)<br/>
`chgrp root text.sh` (change group of text.sh file to root group)<br/>

---

grep (print lines matching a pattern and also HIGHLIGHT the text color)<br/>
man grep ("manual pages"; shows documentation for grep; it help you to find string patterns in the files)<br/>
`grep "my interest text" <directoryPath>` (find "my interest text" in directoryPath; !NB case sensitive by default; -i set ignore for case sensitive)<br/>
`cat /etc/passwd | grep "my text value"` (it will show only matched lines with "my text value" but not the entire content of /etc/passwd)<br/>

<p>`>` ("greater" sign riderect output of the command to another place; e.g. cat /etc/passwd > ~/Desktop/text.txt)<p><br/>

`ifconfig | grep inet` (shows inet from ifconfig)<br/>

locate (find file by name)
man locate (show manual for locate)
`locate /etc --all "passwd"` (show all findings of passwd within /etc folders)<br/>
`locate "passwd" | grep "/etc/passwd"` (same output but with highlighted text)<br/>
`locate --all "*.conf" | grep resolve` (find all .conf files wich contains resolve in path)<br/>
`locate --all -c proxychains` (-c shows number of matches with proxychains)<br/>

---

GET SYSTEM INFO:
`whoami` (username)<br/>
`hostname`<br/>
`sudo vim /etc/hostname`<br/>
`id` (user id)<br/>
`lsb_release -a` (utility which is show what system is in use; installed by default)<br/>
`cat /etc/os-release` (or cat /etc/\*release)<br/>
`lscpu` (info about cpu)<br/>
`uname` (sytem and kernel info)<br/>
`who` (username and time when logged in)<br/>

---

find (find utility)
`sudo find <path> -type <f | d> <<file|directory>Name>`
(e.g. sudo find / -type f -name "proxychains.conf"
-size +1M (same search request but where file size is more than 1 megabyte)
)<br/>
`find . -type f -size 1033c ! -executable | xargs file`<br/>
(find here file with size 1033 bytes which is not (! sign) executable and pipe with xargs)<br/>
(find for unique string which occures only once in file: `cat data.txt | sort | uniq -u`)<br/>
