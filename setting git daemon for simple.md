# setting git daemon for simple
Get a self-host git server is very attractive.

It's not that hard, and it's also available which verified by me on android termux.

If you ever question about authentication, you can refer to git document.

Assuming you had set up sshd, now install git and create a git repository (here's an example called "test-git").

Let's say we got a directory like this:
```
work
\ test-git
```

In work dir, we run:
```
git daemon --reuseaddr --base-path=. .
```

Now you can clone repo under LAN by using:
```
git clone git://xxx.xxx.xxx.xxx/test-git
```
BTW, if you set up DNS in LAN or hostname, you can try replace xxx.xxx.xxx.xxx (which is ip address) with them.

Back to the moment after you runing 'git clone'.

The git said "access denied or repository not exported"

That's because linux style of privilege management.

Solution is easy,
```
cd test-git
touch git-daemon-export-ok
```

More info refer to [git pro book page about git daemon](https://git-scm.com/book/en/v2/Git-on-the-Server-Git-Daemon)