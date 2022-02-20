# Bash_Security_Check
Hi this is my first bash script to practise bash programming.
This script filters a given username, or username-list tranfered through stdin, acording to given criteria to find out the acces rights of the user.
Here are some examples for usage: 

### 1. filters user which are not present
  $echo "mail root doesnotExist" | .security_check.sh 
#### output:
  mail
  
  root

### 2. user from /etc/passwd with id > 1000 without "username"
  cat /etc/passwd | cut -d : -f 1 | ./security_check.sh -I -u "username"
#### output:
  nobody

### 3. user id <  1000 and active login shell
  $echo "mail root 'username'" | ./securtiy_check.sh -l -i
#### output:
  root
