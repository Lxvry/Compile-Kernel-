# Compile-Kernel-
A simple or generic compile kernel on ubuntu server.

1. First step, download ssh-service in ubuntu server. `apt install ssh-service` to use it from our PowerShell or our daily     operating system.


To continue we will go to the official kernel page: `kernel.org`, but we will do this from our operating system.
https://kernel.org/

And now, we can see the following:

[imagen kernel]

We connect at this point through the SSH service.
`ssh usuario@[IP]`

The next step, is to download a series of packages or binaries to our Ubuntu Server.

- apt install `git`
- apt install `fakeroot`
- apt install `xz-utils`
- apt install `build-essential`
- apt install `ncurses-dev`
- apt install `bc`
- apt install `flex`
- apt install `libssl-dev`
- apt install `libelf-dev`
- apt install `bison`


Now from our operating system we share the downloaded file to our Ubuntu Server. We will do this with the PowerShell command console, with the following command in Windows: `python -m http.server 80` and Linux: `sudo python3 -m http.server 80`.

Following this, on our Ubuntu Server, perfom the corresponding download.

Ubuntu Server:
`wget http://[IP]:<PORT>/linux-<version>.tar.xz`

and extract the file.
`tar -xvf linux-<version>.tar.xz`

This will create a directory for us.

So now with the command `uname -a`, we can see the name and version of the kernel of our device.

We copy the current kernel configuration to the local .config file in the current directory.
`cp /boot/config-$(uname -r). config`

This is what we should use to keep the starting point configuration

Now we enter the directory created by the tar.
`cd linux-<version>`

and now finally we proceed to compile. 
`make menuconfig`


Something like this will appear. Here we'll select and remove whatever we need based on our objective.
(Be careful though, any changes that are not responsible can damage the kernel and your system.)

Once all that is done, we proceed to save and exit.

Now we compile with the new kernel configurations. (This process can take 1 hour or even 3, it all depends on your equipment.)
`make` 

For all changes to be applied, just reboot.















