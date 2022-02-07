# desperate-archlinux-toolchain-pkgbuilds
Desperate times need desperate solutions - unsigned official PKGBUILDS hotfixed to be able to compile. 

# Why am I doing this?
Well, the toolchain is now almost 6 months old and some packages from AUR need `glibc` v2.34 or greater to work (mainly the ones ported from OpenSUSE)

# Why are the PKGBUILDS not signed?
Well, it's mainly for only my use and I simply do not want to bother. I'm not the maintainer.

# How to compile the toolchain myself?
## Toolchain build order: 
`linux-api-header->glibc->binutils->gcc->binutils->glibc`

Go to a directory according to the order above and run this command:
`makepkg -si --skipinteg`

Don't forget to modify your `/etc/makepkg.conf` to use all your threads (for me `MAKEFLAGS="-j12"`)

# I don't want to compile!
For you, I have binaries in the `binaries` (obviously) folder. You can install them with `sudo pacman -U` and the binaries you want (at least `linux-api-headers`, `gcc`, `glibc`, `binutils` and then choose what you need).

#### BUT HEY, I'M JUST A RANDOM GUY ON THE INTERNET! I know it's weird saying "Don't trust me", but don't. You don't know who I am, so be careful when you download stuff. This is for those old ThinkPad users, my friends, weak PSs, or whatever. Use it only when you have no other chance, you can't check if I put anything malicious in the binaries.

(But TBH, I don't have the necessary skills to do something malicious...)
