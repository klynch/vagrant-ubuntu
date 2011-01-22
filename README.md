Ubuntu Vagrant base box
=======================

Build bootable `i386` and `amd64` Ubuntu ISOs for use with Vagrant/VirtualBox.

Building
--------
Configure settings in `config.sh`, then build the ISO images:

	./build-iso

Building virtual machines through VirtualBox:

	./build-vbox

Building Vagrant boxes:

	./build-vagrant

There are matching `clean-{iso,vbox,vagrant}` programs that remove the products of their build counterparts.

Build dependencies
------------------

* `curl`
* `m4`
* `mkisofs`


Features in the ISO
-------------------

* Network access is configured using sane default settings.  WiFi is
  not supported.
* The hostname is `devstructure`; the domain is `vagrantup.com`.  These
  are configurable.
* The system clock is set to UTC.
* The entire disk is partitioned `ext4` without LVM.
* The default kernel for the architecture is used.  `linux-server` for
  `amd64` and `linux-generic-pae` for `i386`.
* The `root` and `vagrant` users exist; both their password are `vagrant`.
  Vagrant's standard insecure SSH key is authorized for `vagrant`.  These
  are all configurable.
* DevStructure's Debian archive is added to the source list.
* OpenSSH server is installed.
* VirtualBox Guest Additions are installed.

Features in the Vagrant boxes
-----------------------------

* Ruby 1.8.7
* RubyGems 1.3.7
* Chef 0.9.12


