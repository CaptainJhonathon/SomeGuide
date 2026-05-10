# Using SSH for Github
this document is based the assumption that you can use ssh-keygen to generate your keys(if you don't know, please check github docs)

# 1. Why I can't connect Github with "ssh -T git@github.com" even I had generated and deployed my public key?

## Reason: ssh wouldn't know which key shuold be used defaulty
To solve this is simple, edit in ssh config file.
1. searching path like: ~/.ssh/config   
"~" means the user root directory.Find the config in ".ssh"(if you don't just create one)
2. edit config file like following
```
Host github.com
    HostName github.com
    IdentityFile ~/.ssh/(your_private_key_file)
    User git
```
# 2. How can I solve "github.com refused connection port 22" ?
Reason: probably banned by strict network policy or other unknown reason
To solve this is simple, edit in ssh config file base on ***question 1***.  
1. modify and add below "Host github.com" as following
```
HostName ssh.github.com
Port 443
```