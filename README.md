### disable auto lock
```bash
gsettings set org.gnome.desktop.screensaver lock-enabled false
```
### Install virtualbox guest additions
```bash

```

### Dark mode
```bash
gsettings set org.gnome.desktop.interface gtk-theme 'Adwaita-dark'
```

### Autologon
```
TBC
```

### Run program at startup
```
TBC
```

### Networking: show default gateway
```bash
ip route list
```

- remove default gateway
```bash
sudo ip route delete default
```

- Add default gateway
```bash
sudo ip route add default via 192.168.1.1 dev eth0
```

### Uninstall bloatware
```bash
sudo apt-get remove thunderbird -y
sudo apt-get remove libreoffice* -y
sudo apt-get remove hexchat -y
sudo apt-get remove pix -y
sudo apt-get remove transmission-* -y
sudo apt-get remove bluetooth -y
sudo apt-get remove blueman -y
sudo apt-get remove celluloid -y
sudo apt-get remove hypnotix -y
sudo apt-get remove rhythmbox -y
sudo apt-get remove webapp-manager -y
sudo apt-get remove drawing -y
```

### 🔨 FIX repos/errors

```bash
sudo apt autoremove
sudo apt --fix-broken install -y
sudo apt update
sudo apt-get --allow-releaseinfo-change update
```

### SSH without password

Generate the key on the local system (Requires Win10)

```ps
ssh-keygen.exe
cat ~\.ssh\id_rsa.pub | clip # copy public key to clipboard
```

Add the clipboard contents to the authorized_keys file on the Linux box 

```bash
sudo nano ~/.ssh/authorized_keys
```


## Update/Upgrade repos
```console
sudo apt update && sudo apt upgrade
```

### Message Of The Day (MOTD)

````cat /etc/motd````

Use NeoFetch for a nice MOTD

![image](https://github.com/user-attachments/assets/3ba26c92-086e-49cc-9788-510b7e1a1101)


```bash
sudo apt-get install neofetch -y && sudo bash -c $'echo "neofetch" >> /etc/profile.d/mymotd.sh && chmod +x /etc/profile.d/mymotd.sh'
```

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

```bash
sudo apt-get install -y powershell 
```

Show available Shells 

```bash
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
```bash
sudo service firewalld stop 
```
 
## Set/change hostname 

Reboot may be required to change the hostname 

```bash
sudo hostnamectl set-hostname <hostname> 
```
	
### Grep 

Search for a string in raw text files:  
```bash
grep -r -i YOURKEYWORDHERE
```
        
### Sleep

## Modern Linux Tool Alternatives 

### cat (bat)
sudo apt-get --allow-releaseinfo-change update

https://github.com/ibraheemdev/modern-unix
