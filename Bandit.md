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
 - there is a private key for for next level, use that to login next level.
 - feel free to use `-v` flag to analyze why key is not working, if so.
 - you might need to add key to ssh-agent
