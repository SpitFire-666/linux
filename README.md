### SSH without password

Generate the key on the local system (Requires Win10)
- this creates a key then copies its contents to the clipboard

```ps
ssh-keygen.exe -f file
cat .\file.pub | clip
```

Add the clipboard contents to the id_rsa.pub file on the Linux box 

````
mkdir ~/.ssh
sudo nano ~/.ssh/id_rsa.pub
````

```console
mkdir -p ~/.ssh
nano ~/.ssh/authorized_keys
```

## Update/Upgrade repos
```console
sudo apt update && sudo apt upgrade
```

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

## SMB Server
- Install samba:
```console
sudo apt-get install samba -y
```
- configure samba:
```console
sudo nano /etc/samba/smb.conf
```
- Append this config - adjust the Valid users line if required:

````
[sharedfolder]
comment = secured shared folder
path = /srv/samba/data
Valid users = pi
guest ok = no
writable = yes
privatable = no
browsable = yes
````

- Create a login for user "pi"
```console
sudo smbpasswd -a pi
```
- Restart the service
```console
sudo service smbd restart
```

- If you get an error about guest access on Windows, use gpedit.msc to adjust this setting:

```
Computer configuration > administrative templates > network > Lanman Workstation: "Enable insecure guest logons" = Enabled
```


### Bash script example

https://linuxhint.com/30_bash_script_examples/

````console
for i in {1..5};
do
echo "$i" ;
done
````

### install powershell

```console
sudo apt-get install -y powershell 
```

Show available Shells 

```console
cat /etc/shells 
```

Change default shell to PowerShell 
```console
sudo chsh username -s /usr/bin/powershell 
```
 
 Install java (to launch .jar files) 
```console
sudo apt-get install openjdk-9-jre 
```

Mark a file as executable (eg .jar files) 
```console
sudo chmod +x /home/mike/Downloads/minecraft.jar 
```
 

## Check SELinux status 
```console
Sestatus 
```

## Stop Firewall service 
````
sudo service firewalld stop 
````
 
## Set/change hostname 

Reboot may be required to change the hostname 

````
sudo hostnamectl set-hostname <hostname> 
````
	
### Grep 

Search for a string in raw text files:  
```console
grep -r -i YOURKEYWORDHERE
```
        
### Sleep

## Modern Linux Tool Alternatives 

https://github.com/ibraheemdev/modern-unix
