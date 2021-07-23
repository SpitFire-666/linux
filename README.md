# linux stuff

SSH without password

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
 
