### SSH without password

    Generate the key on the local system 

Requires Linux/Win10/ ssh-keygen.exe 

```ssh-keygen.exe```

Copy the content of id_rsa.pub to the remote (linux) box 

````
~\.ssh\id_rsa.pub 
````

````
mkdir -p ~/.ssh
nano ~/.ssh/authorized_keys
````
 
### Message Of The Day (MOTD)

````cat /etc/motd````

Use NeoFetch for a nice MOTD
````sudo apt-get install neofetch -y && sudo bash -c $'echo "neofetch" >> /etc/profile.d/mymotd.sh && chmod +x /etc/profile.d/mymotd.sh' ````

### Add unstable repo

sudo apt edit-sources
````
deb https://deb.debian.org/debian/ unstable main contrib non-free
deb-src https://deb.debian.org/debian/ unstable main contrib non-free
````

### Bash script example

https://linuxhint.com/30_bash_script_examples/

````
for i in {1..5};
do
echo "$i" ;
done
````

### install powershell
sudo apt-get install -y powershell 

Show available Shells 

 

cat /etc/shells 

Change default shell to PowerShell 

sudo chsh username -s /usr/bin/powershell 

 
 Install java (to launch .jar files) 

sudo apt-get install openjdk-9-jre 

 

Mark a file as executable (eg .jar files) 

sudo chmod +x /home/mike/Downloads/minecraft.jar 

 
  

Check SELinux status 

Sestatus 

 

Stop Firewall service 

sudo service firewalld stop 

 
 Set/change hostname 

Reboot may be required to change the hostname 

 
hostnamectl set-hostname <hostname> 

 
	
###Grep 

here's a basic grep function if you want to search for a string in raw text files:  
````
grep -r -i YOURKEYWORDHERE
````
    
    
### Sleep

## Modern Linux Tool Alternatives 

https://github.com/ibraheemdev/modern-unix
