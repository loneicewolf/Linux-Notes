Based on my [Answer](https://stackoverflow.com/a/67156634/14346786) to [this Question](https://stackoverflow.com/q/50361990/14346786) 

## Step 1
re-install the `linux-headers`.


---
## prerequisites 
- terminal access(`bash presumably`)
- root privileges
     - (or a user who can do 'sudo')

First, we try to re install (using APT) the `linux-headers` package -**but** adding your _specific kernel version_.  Which is determined by  the following command: `$(uname -r)`

and to do it all in one line:

---
`sudo apt install --reinstall linux-headers-$(uname -r)`

Then, as we talk about the kernel, and making changes to it (quite major too, a reinstall of a kernel that is) we want to reboot as soon as the APT command is done:

---
`sudo reboot`

If you get it couldn't find any package, (or similar) (from apt)
try `apt update` and re-try the above.

---
## Logs
Do check  `/var/log/kern.log`  for any messages that is,

- `cat /var/log/kern.log`


