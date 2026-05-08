# configure dnsmasq on unix and linux

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

"resolvd" on OpenBSD; 
"NetworkManager" on Fedora;
Kali I thought will be as well as Fedora?

Anyway, you need to disable DNS related manage tools.

Because a file called "resolv.conf" is important.

This file mainly tell how your computer work a part of accessing 
DNS.

Disabling configuration manage tool will stop updating "resolv.conf" 
file to make sure the machine will parse the name server as you 
like.

After that, you can start to configure dnsmasq.