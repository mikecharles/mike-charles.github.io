---
published: false
---

## Keeping Track of Your IP With Dropbox

Connecting to your computer remotely always requires at least these 2 things:

1. Setting up port forwarding on your router
2. Knowing your IP address

For number 2, you could pay for a DynDNS account, or any number of dynamic DNS services, or you can use this simple trick to keep track of your IP address, no matter where you are.

The way I do this is to use `wget` to retrieve the public IP address on the computer I want to connect to. Do you have wget? Open the terminal and type `wget`. If you don't have it, get it with [brew](http://brew.sh)

Then put this in your cron on the computer you want to connect to:

    0,30 * * * * /usr/local/bin/wget -qO- http://checkip.dyndns.org | sed 's/[a-zA-Z/<> :]//g' > $HOME/Dropbox/Documents/ip.txt
    
Now every 30 minutes, the file `$HOME/Dropbox/Documents/ip.txt` will be updated with your computer's IP address, and you can check this file remotely to always have the latest IP to connect to.