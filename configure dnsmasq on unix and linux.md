# configure dnsmasq on unix and linux

**_Best reference dnsmasq [setup.html mirror to and by myself](./storing/ref/dnsmasq/setup.html). Under source code of dnsmasq..._**

**_Also [FAQ](./storing/ref/dnsmasq/FAQ)._**

## configure dnsmasq DNS on unix and linux

### Intro

Build up a local nework after using too much ip address 
for directing host.

It is time to use DNS to make it better.

I had notice that dnsmasq provide DHCP, DNS, PXE and some 
features while being light weight.

In 2024, I failed, but through recently a little research about 
OpenBSD and some luck to hit my head.

I use dnsmasq to make local DNS possible for the first time.

### General idea
OpenBSD and Linux distros usually controal network configurations 
through some tools.

|OpenBSD|Fedora|Kali|
|---|---|---|
|resolvd| NetworkManager| as well as Fedora?(I fogot)

Anyway, you need to disable DNS related manage tools.

Because a file called "resolv.conf" is important.

This file mainly tell how your computer work a part of accessing 
DNS.

Disabling configuration manage tool will stop updating "resolv.conf" 
file to make sure the machine will parse the name server as you 
like.

After that, you can start to configure dnsmasq by mannual.

### Exact steps of my way

0. Check environment

    |Referenc environment|
    |---|
    |OpenBSD|

1. Kill or diable dns related service

    find and disable or kill resolvd, here's an example to kill resolvd temporarily:
    ```
    top
    /resolvd
    k (pid)
    q
    ```

    On OpenBSD, **rcctl** looks like the same position as **systemctl**,
    so we can disable by using:
    ```
    rcctl disable resolvd
    ```

2. Edit resolv.conf

    The **resolv.conf** is usually located in:
    ```
    /etc/resolv.conf
    ```

    Edit resolv.conf with tool you like, adding these to the top:
    ```
    nameserver xxx.xxx.xxx.xxx
    ```
    Don't forget to save!

    ps: the query order is from top to bottom.

3. Edit dnsmasq.conf or run without .conf file