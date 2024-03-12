1.docker pull ubuntu:latest -Download imagine ubuntu
2.docker run -it --name my_linux_container ubuntu:latest -Create a container
3.adduser john -Add new user john
4.set a password 
5.Introduce the info -Full name 						
		  -room number
		  -work phone
		  -home phone
		  -others
6.is the information corect?
7.cat /etc/passwd verify if passwd exist
8.echo '#!/bin/bash' > script.sh -Create a filr
9.echo 'echo "Fisier"' >> script.sh - Put in file
10../script.sh - verify
11.sed 's/\//\\/g' /etc/passwd > /etc/passwd_modified
12.awk -F: '/^john:/ {print $6}' /etc/passwd -Print jhon home directory
13.awk -F: '{print $1}' /etc/passwd Print all user from psswd 
14.awk -F: 'END {print NR}' /etc/passwd Count user from psswd (20)
15.awk -F: '{if ($3 >= 0 && $3 <= 10) print $1}' /etc/passwd Print users between interval 
16.awk -F: '{if ($NF == "/bin/bash" || $NF == "/bin/sh") print $1}' /etc/passwd -Find the users with standard shell (root , jhon)
17.sed 's/\//\\/g' /etc/passwd > /etc/passwd_modified -Change / with\ 
18.ip a | grep 'inet ' | grep -v 127.0.0.1 | awk '{print $2}' | cut -f1 -d'/'
19.hostname -I | awk '{print $1}' -Print private ip adress
I can,t print public id adress
20.root@57e4f913b59e:/# su - john Switch to jhon user 
21. echo "Directorul home al utilizatorului john:" -Print home directori for jhon
21.echo $HOME


