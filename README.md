Debian with Grsecurity
==============

Everything erased, again.  Starting over with github from the best of my memory.


<pre>
# apt-get install build-essential libncurses5-dev wget less htop sysstat screen
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
# dpkg -i ../*.deb
</pre>
