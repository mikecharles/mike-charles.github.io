---
published: false
---

## Keeping Track of Your IP With Dropbox

There are two parts to remotely connecting to your computer:

1. Setting up port forwarding on your router
2. Knowing your IP address

For number 2, you could pay for a DynDNS account, or any number of dynamic DNS services, or you can use this simple trick to keep track of your IP address, no matter where you are.



    0,30 * * * * /usr/local/bin/wget -qO- http://checkip.dyndns.org | sed 's/[a-zA-Z/<> :]//g' > $HOME/Dropbox/Documents/ip.txt