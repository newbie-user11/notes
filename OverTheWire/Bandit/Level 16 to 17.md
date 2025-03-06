**Password**
JQttfApK4SeyHwDlI9SXGR50qclOAil1

**Relevant Commands**
`nmap -sV -vvvv -p 31000-32000` to enumerate ports with ssl.
`openssl s_client --connect localhost:31790` to reveal RSA key
`ssh -i /tmp/random_sshkey -p 2220 bandit17@localhost`

**Process**
Gain access to level 17 using RSA key revealed at port with ssl using command `ssh -i <keyname> -p 2220 bandit17@localhost`. Once logged into level 17 find password under path /etc/bandit_pass/bandit17

**Password to Level 17**
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e