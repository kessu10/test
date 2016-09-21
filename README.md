BLA BLA test

fork test

$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
[default] Box 'oskari-precise64' was not found. Fetching box from specified URL for
the provider 'virtualbox'. Note that if the URL does not have
a box for this provider, you should interrupt Vagrant now and add
the box yourself. Otherwise Vagrant will attempt to download the
full box prior to discovering this error.
Downloading box from URL: http://oskari.org/boxes/oskari-precise64.box
Extracting box...ate: 1279k/s, Estimated time remaining: --:--:--)
Successfully added box 'oskari-precise64' with provider 'virtualbox'!
[default] Importing base box 'oskari-precise64'...
[default] Matching MAC address for NAT networking...
[default] Setting the name of the VM...
[default] Clearing any previously set forwarded ports...
[default] Clearing any previously set network interfaces...
[default] Preparing network interfaces based on configuration...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] -- 80 => 8080 (adapter 1)
[default] Booting VM...
[default] Waiting for machine to boot. This may take a few minutes...
DL is deprecated, please use Fiddle
[default] Machine booted and ready!
[default] The guest additions on this VM do not match the installed version of
VirtualBox! In most cases this is fine, but in rare cases it can
prevent things such as shared folders from working properly. If you see
shared folder errors, please make sure the guest additions within the
virtual machine match the version of VirtualBox you have installed on
your host and reload your VM.

Guest Additions Version: 4.2.0
VirtualBox Version: 4.3
[default] Mounting shared folders...
[default] -- /vagrant

$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
[default] Box 'oskari-precise64' was not found. Fetching box from specified URL for
the provider 'virtualbox'. Note that if the URL does not have
a box for this provider, you should interrupt Vagrant now and add
the box yourself. Otherwise Vagrant will attempt to download the
full box prior to discovering this error.
Downloading box from URL: http://oskari.org/boxes/oskari-precise64.box
Extracting box...ate: 1279k/s, Estimated time remaining: --:--:--)
Successfully added box 'oskari-precise64' with provider 'virtualbox'!
[default] Importing base box 'oskari-precise64'...
[default] Matching MAC address for NAT networking...
[default] Setting the name of the VM...
[default] Clearing any previously set forwarded ports...
[default] Clearing any previously set network interfaces...
[default] Preparing network interfaces based on configuration...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] -- 80 => 8080 (adapter 1)
[default] Booting VM...
[default] Waiting for machine to boot. This may take a few minutes...
DL is deprecated, please use Fiddle
[default] Machine booted and ready!
[default] The guest additions on this VM do not match the installed version of
VirtualBox! In most cases this is fine, but in rare cases it can
prevent things such as shared folders from working properly. If you see
shared folder errors, please make sure the guest additions within the
virtual machine match the version of VirtualBox you have installed on
your host and reload your VM.

Guest Additions Version: 4.2.0
VirtualBox Version: 4.3
[default] Mounting shared folders...
[default] -- /vagrant

vagrant@precise64:~$ ./postinstall.sh
++ sed -i -e '/Defaults\s\+env_reset/a Defaults\texempt_group=admin' /etc/sudoers
sed: can't read /etc/sudoers: Permission denied
++ case "$platform" in
++ groupadd -r admin
groupadd: group 'admin' already exists
++ true
++ usermod -a -G admin vagrant
usermod: cannot lock /etc/passwd; try again later.
++ sed -i -e 's/%admin ALL=(ALL) ALL/%admin ALL=(ALL) NOPASSWD:ALL/g' /etc/sudoers
sed: can't read /etc/sudoers: Permission denied
++ echo 'LC_ALL="en_US"'
./postinstall.sh: line 51: /etc/default/locale: Permission denied
++ case "$platform" in
++ apt-get -y install build-essential zlib1g-dev libssl-dev libreadline-dev make curl git-core
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
++ clone_dir=/tmp/ruby-build-1423
++ git clone https://github.com/sstephenson/ruby-build.git /tmp/ruby-build-1423
Cloning into '/tmp/ruby-build-1423'...
remote: Reusing existing pack: 2856, done.
remote: Total 2856 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (2856/2856), 472.89 KiB | 379 KiB/s, done.
Resolving deltas: 100% (1254/1254), done.
++ /tmp/ruby-build-1423/bin/ruby-build 1.8.7-p358 /opt/vagrant_ruby
Downloading ruby-1.8.7-p358.tar.gz...
-> http://cache.ruby-lang.org/pub/ruby/1.8/ruby-1.8.7-p358.tar.gz
error: failed to download ruby-1.8.7-p358.tar.gz

BUILD FAILED

Inspect or clean up the working tree at /tmp/ruby-build.20140130201355.1437
Results logged to /tmp/ruby-build.20140130201355.1437.log

Last 10 log lines:
/tmp/ruby-build.20140130201355.1437 ~
wget: unable to resolve host address `wwwp.nls.fi'
++ rm -rf /tmp/ruby-build-1423
++ unset clone_dir
++ /opt/vagrant_ruby/bin/gem install polyglot net-ssh-gateway mime-types --no-ri --no-rdoc
ERROR:  Could not find a valid gem 'polyglot' (>= 0) in any repository
ERROR:  While executing gem ... (Gem::RemoteFetcher::FetchError)
    SocketError: getaddrinfo: Name or service not known (http://rubygems.org/latest_specs.4.8.gz)
++ /opt/vagrant_ruby/bin/gem install chef --no-ri --no-rdoc
ERROR:  Could not find a valid gem 'chef' (>= 0) in any repository
ERROR:  While executing gem ... (Gem::RemoteFetcher::FetchError)
    SocketError: getaddrinfo: Name or service not known (http://rubygems.org/latest_specs.4.8.gz)
++ /opt/vagrant_ruby/bin/gem install puppet --no-ri --no-rdoc
ERROR:  Could not find a valid gem 'puppet' (>= 0) in any repository
ERROR:  While executing gem ... (Gem::RemoteFetcher::FetchError)
    SocketError: getaddrinfo: Name or service not known (http://rubygems.org/latest_specs.4.8.gz)
++ groupadd puppet
groupadd: group 'puppet' already exists
++ echo 'PATH=$PATH:/opt/vagrant_ruby/bin'
./postinstall.sh: line 102: /etc/profile.d/vagrant_ruby.sh: Permission denied
++ vssh=/home/vagrant/.ssh
++ mkdir -p /home/vagrant/.ssh
++ chmod 700 /home/vagrant/.ssh
++ cd /home/vagrant/.ssh
++ wget --no-check-certificate https://raw.github.com/mitchellh/vagrant/master/keys/vagrant.pub -O /home/vagrant/.ssh/authorized_keys
--2014-01-30 20:13:57--  https://raw.github.com/mitchellh/vagrant/master/keys/vagrant.pub
Resolving raw.github.com (raw.github.com)... 185.31.16.133
Connecting to raw.github.com (raw.github.com)|185.31.16.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 409 [text/plain]
Saving to: `/home/vagrant/.ssh/authorized_keys'

100%[======================================>] 409         --.-K/s   in 0s

2014-01-30 20:13:58 (5.06 MB/s) - `/home/vagrant/.ssh/authorized_keys' saved [409/409]

++ chmod 0600 /home/vagrant/.ssh/authorized_keys
++ chown -R vagrant:vagrant /home/vagrant/.ssh
++ unset vssh
++ apt-get -y remove virtualbox-ose-guest-dkms
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
++ apt-get -y remove virtualbox-ose-guest-utils
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
+++ uname -r
++ apt-get -y install linux-headers-3.2.0-23-generic
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
+++ cat /home/vagrant/.vbox_version
++ VBOX_VERSION=4.3.6
++ mount -o loop /home/vagrant/VBoxGuestAdditions_4.3.6.iso /mnt
mount: only root can do that
++ yes
++ sh /mnt/VBoxLinuxAdditions.run
sh: 0: Can't open /mnt/VBoxLinuxAdditions.run
++ umount /mnt
umount: /mnt is not mounted (according to mtab)
++ rm -f /home/vagrant/VBoxGuestAdditions_4.3.6.iso
+++ uname -r
++ apt-get -y remove linux-headers-3.2.0-23-generic
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
++ apt-get -y install nfs-common
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
++ echo 'UseDNS no'
./postinstall.sh: line 149: /etc/ssh/sshd_config: Permission denied
++ case "$platform" in
++ echo 'Welcome to your Vagrant-built virtual machine.'
./postinstall.sh: line 157: /etc/motd.tail: Permission denied
++ date
./postinstall.sh: line 162: /etc/vagrant_box_build_time: Permission denied
++ cat
./postinstall.sh: line 166: /etc/rc.local: Permission denied
++ apt-get -y remove build-essential make curl git-core
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
++ apt-get -y autoremove
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
++ apt-get -y clean
E: Could not open lock file /var/cache/apt/archives/lock - open (13: Permission denied)
E: Unable to lock the download directory
++ rm -f '/var/lib/dhcp3/*'
++ rm /etc/udev/rules.d/70-persistent-net.rules
rm: cannot remove `/etc/udev/rules.d/70-persistent-net.rules': Is a directory
++ mkdir /etc/udev/rules.d/70-persistent-net.rules
mkdir: cannot create directory `/etc/udev/rules.d/70-persistent-net.rules': File exists
++ rm -rf /dev/.udev/
rm: cannot remove `/dev/.udev/rules.d/root.rules': Permission denied
++ rm /lib/udev/rules.d/75-persistent-net-generator.rules
rm: cannot remove `/lib/udev/rules.d/75-persistent-net-generator.rules': No such file or directory
++ rm -f '/home/vagrant/*.iso' /home/vagrant/postinstall.sh
++ dd if=/dev/zero of=/EMPTY bs=1M
dd: opening `/EMPTY': Permission denied
++ rm -f /EMPTY
++ exit
vagrant@precise64:~$
____________________________________________
$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
[default] Importing base box 'oskari-precise64'...
[default] Matching MAC address for NAT networking...
[default] Setting the name of the VM...
[default] Clearing any previously set forwarded ports...
[default] Clearing any previously set network interfaces...
[default] Preparing network interfaces based on configuration...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] -- 80 => 8080 (adapter 1)
[default] Booting VM...
[default] Waiting for machine to boot. This may take a few minutes...
DL is deprecated, please use Fiddle
[default] Machine booted and ready!
[default] The guest additions on this VM do not match the installed version of
VirtualBox! In most cases this is fine, but in rare cases it can
prevent things such as shared folders from working properly. If you see
shared folder errors, please make sure the guest additions within the
virtual machine match the version of VirtualBox you have installed on
your host and reload your VM.

Guest Additions Version: 4.2.0
VirtualBox Version: 4.3
[default] Mounting shared folders...
[default] -- /vagrant

kessu@kessu-10 ~/ubuntu64
$ vagrant ssh
Welcome to Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic x86_64)

 * Documentation:  https://help.ubuntu.com/
Welcome to your Vagrant-built virtual machine.
Last login: Fri Jan 24 13:06:43 2014 from 192.168.0.2
vagrant@precise64:~$ ls
oskari  oskari-server  postinstall.sh
vagrant@precise64:~$ cp postinstall.sh ../
cp: cannot create regular file `../postinstall.sh': Permission denied
vagrant@precise64:~$ sudo cp  postinstall.sh ../
vagrant@precise64:~$ sudo ./postinstall.sh
+ sed -i -e /Defaults\s\+env_reset/a Defaults\texempt_group=admin /etc/sudoers
+ groupadd -r admin
groupadd: group 'admin' already exists
+ true
+ usermod -a -G admin vagrant
+ sed -i -e s/%admin ALL=(ALL) ALL/%admin ALL=(ALL) NOPASSWD:ALL/g /etc/sudoers
+ echo LC_ALL="en_US"
+ apt-get -y install build-essential zlib1g-dev libssl-dev libreadline-dev make curl git-core
Reading package lists... Done
Building dependency tree
Reading state information... Done
libreadline-dev is already the newest version.
zlib1g-dev is already the newest version.
build-essential is already the newest version.
make is already the newest version.
The following extra packages will be installed:
  libcurl3 libssl1.0.0
The following NEW packages will be installed:
  curl git-core libcurl3
The following packages will be upgraded:
  libssl-dev libssl1.0.0
2 upgraded, 3 newly installed, 0 to remove and 154 not upgraded.
Need to get 2,999 kB of archives.
After this operation, 1,137 kB of additional disk space will be used.
Err http://us.archive.ubuntu.com/ubuntu/ precise-updates/main libssl-dev amd64 1.0.1-4ubuntu5.11
  Could not resolve 'wwwp.nls.fi'
Err http://us.archive.ubuntu.com/ubuntu/ precise/main git-core all 1:1.7.9.5-1
  Could not resolve 'wwwp.nls.fi'
Err http://security.ubuntu.com/ubuntu/ precise-security/main libssl-dev amd64 1.0.1-4ubuntu5.11
  Could not resolve 'wwwp.nls.fi'
Err http://security.ubuntu.com/ubuntu/ precise-security/main libssl1.0.0 amd64 1.0.1-4ubuntu5.11
  Could not resolve 'wwwp.nls.fi'
Err http://security.ubuntu.com/ubuntu/ precise-security/main libcurl3 amd64 7.22.0-3ubuntu4.6
  Could not resolve 'wwwp.nls.fi'
Err http://security.ubuntu.com/ubuntu/ precise-security/main curl amd64 7.22.0-3ubuntu4.6
  Could not resolve 'wwwp.nls.fi'
Failed to fetch http://security.ubuntu.com/ubuntu/pool/main/o/openssl/libssl-dev_1.0.1-4ubuntu5.11_amd64.deb  Could not resolve 'wwwp.nls.fi'
Failed to fetch http://security.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.0.0_1.0.1-4ubuntu5.11_amd64.deb  Could not resolve 'wwwp.nls.fi'
Failed to fetch http://security.ubuntu.com/ubuntu/pool/main/c/curl/libcurl3_7.22.0-3ubuntu4.6_amd64.deb  Could not resolve 'wwwp.nls.fi'
Failed to fetch http://security.ubuntu.com/ubuntu/pool/main/c/curl/curl_7.22.0-3ubuntu4.6_amd64.deb  Could not resolve 'wwwp.nls.fi'
Failed to fetch http://us.archive.ubuntu.com/ubuntu/pool/main/g/git/git-core_1.7.9.5-1_all.deb  Could not resolve 'wwwp.nls.fi'
E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
+ clone_dir=/tmp/ruby-build-1500
+ git clone https://github.com/sstephenson/ruby-build.git /tmp/ruby-build-1500
Cloning into '/tmp/ruby-build-1500'...
remote: Reusing existing pack: 2856, done.
remote: Total 2856 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (2856/2856), 472.89 KiB | 396 KiB/s, done.
Resolving deltas: 100% (1254/1254), done.
+ /tmp/ruby-build-1500/bin/ruby-build 1.8.7-p358 /opt/vagrant_ruby
Downloading ruby-1.8.7-p358.tar.gz...
-> http://dqw8nmjcqpjn7.cloudfront.net/26bd55358847459a7752acdbd33a535f
Installing ruby-1.8.7-p358...
Installed ruby-1.8.7-p358 to /opt/vagrant_ruby

Downloading rubygems-1.6.2.tar.gz...
-> http://dqw8nmjcqpjn7.cloudfront.net/0c95a9869914ba1a45bf71d3b8048420
Installing rubygems-1.6.2...
Installed rubygems-1.6.2 to /opt/vagrant_ruby

+ rm -rf /tmp/ruby-build-1500
+ unset clone_dir
+ /opt/vagrant_ruby/bin/gem install polyglot net-ssh-gateway mime-types --no-ri --no-rdoc
Successfully installed polyglot-0.3.3
Fetching: net-ssh-2.7.0.gem (100%)
Fetching: net-ssh-gateway-1.2.0.gem (100%)
Successfully installed net-ssh-2.7.0
Successfully installed net-ssh-gateway-1.2.0
Fetching: mime-types-2.1.gem (100%)
ERROR:  Error installing mime-types:
        mime-types requires Ruby version >= 1.9.2.
3 gems installed
+ /opt/vagrant_ruby/bin/gem install chef --no-ri --no-rdoc
Fetching: mixlib-config-2.1.0.gem (100%)
Fetching: mixlib-cli-1.4.0.gem (100%)
Fetching: mixlib-shellout-1.3.0.gem (100%)
Fetching: diff-lcs-1.2.5.gem (100%)
Fetching: hashie-2.0.5.gem (100%)
Fetching: rack-1.5.2.gem (100%)
Fetching: chef-zero-1.7.3.gem (100%)
Fetching: puma-1.6.3.gem (100%)
Building native extensions.  This could take a while...
Fetching: coderay-1.1.0.gem (100%)
Fetching: slop-3.4.7.gem (100%)
Fetching: method_source-0.8.2.gem (100%)
Fetching: pry-0.9.12.6.gem (100%)
Fetching: chef-11.8.2.gem (100%)
Successfully installed mixlib-config-2.1.0
Successfully installed mixlib-cli-1.4.0
Successfully installed mixlib-shellout-1.3.0
Successfully installed diff-lcs-1.2.5
Successfully installed hashie-2.0.5
Successfully installed rack-1.5.2
Successfully installed chef-zero-1.7.3
Successfully installed puma-1.6.3
Successfully installed coderay-1.1.0
Successfully installed slop-3.4.7
Successfully installed method_source-0.8.2
Successfully installed pry-0.9.12.6
Successfully installed chef-11.8.2
13 gems installed
+ /opt/vagrant_ruby/bin/gem install puppet --no-ri --no-rdoc
Fetching: json_pure-1.8.1.gem (100%)
Fetching: hiera-1.3.1.gem (100%)
Fetching: rgen-0.6.6.gem (100%)
Fetching: puppet-3.4.2.gem (100%)
Successfully installed json_pure-1.8.1
Successfully installed hiera-1.3.1
Successfully installed rgen-0.6.6
Successfully installed puppet-3.4.2
4 gems installed
+ groupadd puppet
groupadd: group 'puppet' already exists
+ echo PATH=$PATH:/opt/vagrant_ruby/bin
+ vssh=/home/vagrant/.ssh
+ mkdir -p /home/vagrant/.ssh
+ chmod 700 /home/vagrant/.ssh
+ cd /home/vagrant/.ssh
+ wget --no-check-certificate https://raw.github.com/mitchellh/vagrant/master/keys/vagrant.pub -O /home/vagrant/.ssh/authorized_keys
--2014-01-30 20:59:18--  https://raw.github.com/mitchellh/vagrant/master/keys/vagrant.pub
Resolving raw.github.com (raw.github.com)... 185.31.17.133
Connecting to raw.github.com (raw.github.com)|185.31.17.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 409 [text/plain]
Saving to: `/home/vagrant/.ssh/authorized_keys'

100%[======================================>] 409         --.-K/s   in 0s

2014-01-30 20:59:19 (1010 KB/s) - `/home/vagrant/.ssh/authorized_keys' saved [409/409]

+ chmod 0600 /home/vagrant/.ssh/authorized_keys
+ chown -R vagrant:vagrant /home/vagrant/.ssh
+ unset vssh
+ apt-get -y remove virtualbox-ose-guest-dkms
Reading package lists... Done
Building dependency tree
Reading state information... Done
Package virtualbox-ose-guest-dkms is not installed, so not removed
0 upgraded, 0 newly installed, 0 to remove and 156 not upgraded.
+ apt-get -y remove virtualbox-ose-guest-utils
Reading package lists... Done
Building dependency tree
Reading state information... Done
Package virtualbox-ose-guest-utils is not installed, so not removed
0 upgraded, 0 newly installed, 0 to remove and 156 not upgraded.
+ uname -r
+ apt-get -y install linux-headers-3.2.0-23-generic
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following extra packages will be installed:
  linux-headers-3.2.0-23
The following NEW packages will be installed:
  linux-headers-3.2.0-23 linux-headers-3.2.0-23-generic
0 upgraded, 2 newly installed, 0 to remove and 156 not upgraded.
Need to get 12.4 MB of archives.
After this operation, 67.3 MB of additional disk space will be used.
Err http://us.archive.ubuntu.com/ubuntu/ precise/main linux-headers-3.2.0-23 all 3.2.0-23.36
  Could not resolve 'wwwp.nls.fi'
Err http://us.archive.ubuntu.com/ubuntu/ precise/main linux-headers-3.2.0-23-generic amd64 3.2.0-23.36
  Could not resolve 'wwwp.nls.fi'
Failed to fetch http://us.archive.ubuntu.com/ubuntu/pool/main/l/linux/linux-headers-3.2.0-23_3.2.0-23.36_all.deb  Could not resolve 'wwwp.nls.fi'
Failed to fetch http://us.archive.ubuntu.com/ubuntu/pool/main/l/linux/linux-headers-3.2.0-23-generic_3.2.0-23.36_amd64.deb  Could not resolve 'wwwp.nls.fi'
E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
+ cat /home/vagrant/.vbox_version
+ VBOX_VERSION=4.3.6
+ mount -o loop /home/vagrant/VBoxGuestAdditions_4.3.6.iso /mnt
/home/vagrant/VBoxGuestAdditions_4.3.6.iso: No such file or directory
+ yes
+ sh /mnt/VBoxLinuxAdditions.run
sh: 0: Can't open /mnt/VBoxLinuxAdditions.run
+ umount /mnt
umount: /mnt: not mounted
+ rm -f /home/vagrant/VBoxGuestAdditions_4.3.6.iso
+ uname -r
+ apt-get -y remove linux-headers-3.2.0-23-generic
Reading package lists... Done
Building dependency tree
Reading state information... Done
Package linux-headers-3.2.0-23-generic is not installed, so not removed
0 upgraded, 0 newly installed, 0 to remove and 156 not upgraded.
+ apt-get -y install nfs-common
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages will be upgraded:
  nfs-common
1 upgraded, 0 newly installed, 0 to remove and 155 not upgraded.
Need to get 241 kB of archives.
After this operation, 1,024 B of additional disk space will be used.
Err http://us.archive.ubuntu.com/ubuntu/ precise-updates/main nfs-common amd64 1:1.2.5-3ubuntu3.1
  Could not resolve 'wwwp.nls.fi'
Failed to fetch http://us.archive.ubuntu.com/ubuntu/pool/main/n/nfs-utils/nfs-common_1.2.5-3ubuntu3.1_amd64.deb  Could not resolve 'wwwp.nls.fi'
E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
+ echo UseDNS no
+ echo Welcome to your Vagrant-built virtual machine.
+ date
+ cat
+ apt-get -y remove build-essential make curl git-core
Reading package lists... Done
Building dependency tree
Reading state information... Done
Package git-core is not installed, so not removed
Package curl is not installed, so not removed
The following packages will be REMOVED:
  build-essential debhelper dpkg-dev make
0 upgraded, 0 newly installed, 4 to remove and 156 not upgraded.
After this operation, 2,556 kB disk space will be freed.
(Reading database ... 61191 files and directories currently installed.)
Removing build-essential ...
Removing debhelper ...
Removing dpkg-dev ...
Removing make ...
Processing triggers for man-db ...
+ apt-get -y autoremove
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages will be REMOVED:
  fakeroot g++ g++-4.6 html2text intltool-debian libalgorithm-diff-perl
  libalgorithm-diff-xs-perl libalgorithm-merge-perl libdpkg-perl
  libstdc++6-4.6-dev po-debconf
0 upgraded, 0 newly installed, 11 to remove and 156 not upgraded.
After this operation, 28.2 MB disk space will be freed.
(Reading database ... 60636 files and directories currently installed.)
Removing fakeroot ...
update-alternatives: using /usr/bin/fakeroot-tcp to provide /usr/bin/fakeroot (fakeroot) in auto mode.
Removing g++ ...
Removing html2text ...
Removing po-debconf ...
Removing intltool-debian ...
Removing libalgorithm-merge-perl ...
Removing libalgorithm-diff-xs-perl ...
Removing libalgorithm-diff-perl ...
Removing libdpkg-perl ...
Removing g++-4.6 ...
Removing libstdc++6-4.6-dev ...
Processing triggers for man-db ...
+ apt-get -y clean
+ rm -f /var/lib/dhcp3/*
+ rm /etc/udev/rules.d/70-persistent-net.rules
rm: cannot remove `/etc/udev/rules.d/70-persistent-net.rules': Is a directory
+ mkdir /etc/udev/rules.d/70-persistent-net.rules
mkdir: cannot create directory `/etc/udev/rules.d/70-persistent-net.rules': File exists
+ rm -rf /dev/.udev/
+ rm /lib/udev/rules.d/75-persistent-net-generator.rules
rm: cannot remove `/lib/udev/rules.d/75-persistent-net-generator.rules': No such file or directory
+ rm -f /home/vagrant/{*.iso,postinstall*.sh}
+ dd if=/dev/zero of=/EMPTY bs=1M
dd: writing `/EMPTY': No space left on device
76557+0 records in
76556+0 records out
80275763200 bytes (80 GB) copied, 129.326 s, 621 MB/s
+ rm -f /EMPTY
+ exit


org.apache.jasper.JasperException: PWC6345: There is an error in invoking javac.  A full JDK (not just JRE) is required
	at org.apache.jasper.compiler.DefaultErrorHandler.jspError(DefaultErrorHandler.java:92)