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
 - `cat data.txt | tr 'a-zA-Z' 'n-za-mN-ZA-M'` //some rot13 using `tr` command.
## lvl12-13
 - `xxd -r hexdump_file_name` //this is first step and wont repeat
 - `file file_name` //use this again and again to check which compression is used
 - //below uncompression commands are to be used as per compression format we found in inner file
	- `tar -x -f file_name`
	- `gunzip file_name.gz` //note the extension is a must
	- `bzip2 -d file_name`
## lvl13-14
 - there is a private key for for next level, use that(ssh `-i` flag) to login next level.
 - feel free to use `-v` flag to analyze why key is not working, if so.
 - you might need to add key to ssh-agent// if not adding to agent, use `-o IdentitiesOnly=yes`
## lvl14-15
 - `nc localhost 30000`  //then enter the password located at /etc/bandit_pass/bandit14
## lvl15-16
 - `openssl s_connect -connect localhost:30001` //ofcourse, then give the current password
## lvl16-17
 - `nmap -p31000-32000 localhost` //to find out which ports are open
 - `openssl s_client -connect localhost:<port> -nocommands` //`nocommands` is mandatory because otherwise it understands password characters as command
 - when there is `read R BLOCK` then enter the current password
 - If you get some private key, then you know how to deal//lvl13-14
## lvl17-18
 - `diff passwords.new passwords.old`
## lvl18-19
 - You need to see some ‘arguments’ in ‘ssh’ command, that ‘directly’ runs a ‘command’ on ssh server.
## lvl19-20
 - `cat /etc/passwd | grep bandit19` //also do for `bandit20`
 - `./bandit20-do id` // running without arguments gives this help info, run it this way
 - Also play around some `id` `whoami` and `ls` commands to find out information about permissions. Try `whoami` vs `./bandit20-do whoami`
 - banditX’s password is at `/etc/bandit_pass/banditX`
## lvl20-21
 - Use `tmux` to split window into to 2.
 - `echo "__level 20 password__" | nc -l localhost 29000` // start the server that returns a message
 - Then from second `pane` within `tmux`, use the `./suconnect` binary with port `29000`(or whatever your server is listening to)
 - Next level password will show in tmux pane where server was listening.
## lvl21-22
 - `cat /etc/cron.d/cronjob_bandit22` //check the cronjob
 - `cat /usr/bin/cronjob_bandit22.sh` //check what it is doing
 - Than again `cat` the file where it is storing the password
## lvl22-23


