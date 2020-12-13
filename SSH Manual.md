# SSH Key (Ubuntu)

##### Steps to create a SSH Key in Ubuntu.

##### See SSH version.
```
ssh -V
```
##### Show SSH manual (commands).
```
man ssh
```
##### Change to the SSH directory.
```
cd ~/.ssh

If the directory is no recognized, we'll have to create a new key.
```
##### Create a new key.
```
ssh-keygen -t rsa -b 4096 -C <GIT_Email>

> Press Enter
> Enter a passphrase
```
##### Change to the SSH directory.
```
cd ~/.ssh
```

##### In this point we'll have 2 files:
```
id_rsa  -- private key
id_rsa.pub  -- complete key (SHA256)
```

##### Now we have to add our new key to the {ssh-agent} in order to use this key by default without the need for using a password.

##### We are telling to the agent to go and see what keys are created.
```
eval "$(ssh-agent -s)"
```

##### Add the key.
```
ssh-add ~/.ssh/<private key>

It is going to ask us the passphrase
```

##### Finally we have to go to GitHub and add the complete key, to see the content we can make a nano or a cat to the .pub key (complete key). If git asks for passphrase after following the previous steps, run the command:
```
ssh-add
```
