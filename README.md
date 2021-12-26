# NetworkPingScan

In this shell script we iterate through all possible IPs in a subnet and we perform a ping scan through out. 
the script is very simple to understand and consists of a for loop that iterated through 1 to 254, i.e. the range of possible values of a device in a subnet. 

we run a ping scan with :
    	ping -c 1 $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" &

where `-c 1` means that we will only ping one IP once.
In case of a successful ping the return message starts with "64 bytes ..." so we grep those lines.
the IP that we scanned is present in the 4th item if we split using space.
then we translate the result and remove the ':' from the end of the string.
