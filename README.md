


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

### Sleep

## Modern Linux Tool Alternatives 

https://github.com/ibraheemdev/modern-unix
