Running UBOS on Raspberry Pi
============================

You can run UBOS on your Raspberry Pi by downloading an image, writing it to an SD card,
and booting your Raspberry Pi with that card.

Both Raspberry Pi "Model B" and "Model B Plus" are supported out of the box. ("Model A"
and "Model A Plus" do not have built-in networking, which UBOS requires to install
new apps.) If you are not sure which model you have, consult
`this page <http://www.raspberrypi.org/products/>`_.

#. Download a UBOS boot image from `depot.ubos.net`.
   Beta 1 images for the Raspberry Pi are at
   `http://depot.ubos.net/yellow/armv6h/images <http://depot.ubos.net/yellow/armv6h/images>`_.
   Look for a file named ``ubos_yellow_armv6h_LATEST.img``
   or ``ubos_yellow_armv6h_LATEST.img.xz`` (the same, compressed).

#. Write this image file "raw" to an SD card appropriate for your Raspberry Pi. This
   operation depends on your operating system:

   * :doc:`/users/writing-image/windows`
   * :doc:`/users/writing-image/macosx`
   * :doc:`/users/writing-image/linux`

#. Remove the SD card, insert it into your Raspberry PI, connect an Ethernet cable,
   and plug in the Raspberry Pi power cord.

   It is recommended you connect a monitor and keyboard to your Raspberry Pi for your
   first boot.

#. When the boot process is finished, log in as user ``root`` from the console. By
   default, there is no password on the console.

#. Now: wait. The Raspberry Pi is not a very fast computer, and UBOS needs to generate
   a few cryptographic keys before it is ready to use. That might take 5 or 10 minutes.
   To determine whether UBOS ready, execute:

   .. code-block:: none

      systemctl is-system-running

#. If you have Ethernet plugged in, and your network has a DHCP server (most networks do),
   your computer should automatically acquire an IP address. You can check with::

      > ip addr

   Make sure you are connected to the internet before attempting to proceed.

#. Update the code to the latest and greatest::

      > ubos-admin update

#. You are now ready to :doc:`set up your first app and site </users/firstsite>`.



