# Servel things to use openssh
this file contain things about using ssh

# SFTP
Usually, openssh-server and openssh-client will provide a sub-system sftp to transfer your files easily.It will use your configuration of ssh so it will be all set up as you configure ssh.    

By the way, ***using sftp command should be similar to ssh***.

# X11 Forwarding and X server
X11 Forwarding allows you get a graphic window from remote host.    
Most of time(I believed), people will use Windows to connect a linux host.  

***VcXsrv*** is a Windwos X Server tool
setting up is easy  

VcXsrc :
1. notice your "Display number" when you're setting X server
2. make sure you tick Disable access control (We will figure it out how to use it later, it might be a sucurity problem)

Linux host(ssh session) :
1. setting environment variabel
```
export DISPLAY=LOCAL_HOST_IP:DISPLAY_NUMBER.0
(exaple)
export DISPLAY=192.168.0.1:0.0
```
2. test with firefox
```
firefox
```

if all success a firefox window should be opened on your local host !