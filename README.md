Debian with Grsecurity
==============

Everything erased, again.  Starting over with github from the best of my memory.


<pre>
# apt-get install build-essential fakeroot libncurses5-dev wget less htop sysstat screen
# cat /proc/modules | cut -d " " -f 1 | sort

# make oldconfig
# make menuconfig
</pre>

These use the `make-kpkg` utility.  The Debian/Ubuntu way.<br />
http://www.debian.org/doc/manuals/debian-faq/ch-kernel.en.html<br />
http://www.howtoforge.com/hardening-the-linux-kernel-with-grsecurity-debian
<pre>
# apt-get install kernel-package
# time fakeroot make-kpkg -j5 --initrd kernel_image kernel_headers
</pre>

Grsecurity recommends doing it this way instead.  I didn't like the way make-kpkg puts the kernel version twice and
random garbage title shit, so I'm going to use this even though the .deb's it creates are bigger.
http://en.wikibooks.org/wiki/Grsecurity/Configuring_and_Installing_grsecurity
<pre>
# time fakeroot make -j5 deb-pkg
...
real    16m37.387s
user    36m38.217s
sys     4m5.459s
# dpkg -i ../*.deb
</pre>

ehci-hcd
uhci-hcd
ohci-hcd
usbhid

load_video
insmod gzio
insmod part_msdos
insmod ext2
set root='(hd0,msdos2)'
search --no-floppy --fs-uuid --set=root <uuid etc>

real    36m55.823s
user    77m16.818s
sys     7m6.519s

http://debian-handbook.info/browse/stable/sect.kernel-compilation.html<br />

