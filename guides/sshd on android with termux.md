# sshd on android with termux
Install termux.

Install sshd.

Run sshd with simple command.
```
sshd
```
You can set sshd_conf as you want by refering related document.

After opening sshd, you can use pc to work.

To connect this sshd,
```
ssh root@xxx.xxx.xxx.xxx -p 8022
```
The termux will handle to use a delicate user by android system.

You can check by,
```
whoami
```