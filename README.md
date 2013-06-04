Debian with Grsecurity
==============

Everything erased, again.  Starting over with github.


<pre>
# apt-get install build-essential libncurses5-dev wget less htop sysstat screen
# make oldconfig
# make menuconfig
</pre>

http://www.debian.org/doc/manuals/debian-faq/ch-kernel.en.html
http://www.howtoforge.com/hardening-the-linux-kernel-with-grsecurity-debian
<pre>
# apt-get install kernel-package
# time fakeroot make-kpkg -j5 --initrd kernel_image kernel_headers
</pre>

http://en.wikibooks.org/wiki/Grsecurity/Configuring_and_Installing_grsecurity
<pre>
# time fakeroot make -j5 deb-pkg
</pre>
