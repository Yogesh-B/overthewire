Notes: 
1. you may need to give parameters on ssh, `-o PubkeyAuthentication=no` and `-p <port_number_given_on_the_website>`

## lvl0
 - just use password `badit0` to login to the ssh server.
## lvl0-1
 - there is a `readme` file in the home folder, it has got the password.
## lvl1-2
 - `cat ./-` has got password for lvl2
## lvl2-3
 - `cat ./spaces\ in\ this\ filename` has got password for lvl3
## lvl3-4
 - `cd inhere`
 - `cat ./...Hiding-From-You`
## lvl4-5
 - `cd inhere`
 - `file ./*`   //this command gives info about all files, what they content. “Human readable” means PLAIN TEXT :)
## lvl5-6
 - `cd inhere`
 - `find ./ -perm 640 -ls | grep 1033` (the one with 1033 size)
 - another solution : `find -iname '*file*' -size 1033c -exec ls -l  {} +;`
## lvl6-7 
 - `cd /`
 - `find / -user bandit7 -group bandit6 -size 33c 2>/dev/null` //`2>/dev/null` is for hiding the errors.
## lvl7-8
 - `grep millionth data.txt` //use `info`(installed via `textinfo`) or `man` for learning about grep
## lvl8-9
 - `sort data.txt | uniq -uc`
## lvl9-10
 - `strings data.txt | grep ^\=`
 - another solution `grep -a '===' data.txt`
## lvl10-11
 - `base64 -d data.txt`
## lvl11-12
 - 