6. 
$ cat processes.sh
#! /bin/bash
#List processes based on %cpu and memory usage

echo "Start Time" `date`
# By default, it display the list of processes based on the cpu and memory usage #
if [ $# -eq 0 ]
then

	echo "List of processes based on the %cpu Usage"
	ps -e -o pcpu,cpu,nice,state,cputime,args --sort pcpu  # sorted based on %cpu
	echo "List of processes based on the memory Usage"
	ps -e -orss=,args= | sort -b -k1,1n # sorted bases rss value

# If arguements are given (mem/cpu)
else
	case "$1" in
	mem)
	 echo "List of processes based on the memory Usage"
 	 ps -e -orss=,args= | sort -b -k1,1n
	 ;;
 	cpu)
	 echo "List of processes based on the %cpu Usage"
	 ps -e -o pcpu,cpu,nice,state,cputime,args --sort pcpu
	 ;;
 	*)
		echo "Invalid Argument Given \n"
		echo "Usage : $0 mem/cpu"
		exit 1
 	esac	

fi
echo "End Time" `date`
exit 0

# I completed these with a single line of code
# this displays the top 10 CPU users
ps aux k-pcpu | head -11
# this display the top 10 memory users
ps aux k-pcpu | head -11




7. 
#!/bin/bash
echo "Please enter username:"
read username
echo "Please enter the new password:"
read -s password1
echo "Please repeat the new password:"
read -s password2

# Check both passwords match
if [ $password1 != $password2 ]; then
    echo "Passwords do not match"
     exit    
fi

# Does User exist?
id $username &> /dev/null
if [ $? -eq 0 ]; then
    echo "$username exists... changing password."
else
    echo "$username does not exist - Password could not be updated for $username"; exit 
fi

# Change password
echo -e "$password1\n$password1" | passwd $username

8. #!/bin/bash
for i in `cat /var/tmp/users`; do
echo -e "linuxpassword\nlinuxpassword" | passwd $i
done
