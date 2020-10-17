### shrewvpn
#### why the git repo?
stuff from the official site does not compile on debian buster, so i fixed the source.
#### what changed?
idk, sat down for an hour and changed some files so there are no compiler errors anymore, do a diff or something.
#### how to ..
##### .. install
```shell script
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
make -j $(nproc)
make install
# or into a directory
make install DESTDIR=shrewvpn
# or automated
./install.sh
```
#####  .. configuring
```shell script
sudo cp /usr/local/etc/iked.conf.sample /usr/local/etc/iked.conf
```
##### .. running
```shell script
sudo iked

ii : created ike socket 0.0.0.0:500
ii : created natt socket 0.0.0.0:4500
## : IKE Daemon, ver 2.2.1
## : Copyright 2013 Shrew Soft Inc.
## : This product linked OpenSSL 1.1.1g  21 Apr 2020

ikec --help

ii : ## : VPN Connect, ver 2.2.1
## : Copyright 2013 Shrew Soft Inc.
## : press the <h> key for help
!! : invalid parameters specified ...
>> : ikec -r "name" [ -u <user> ][ -p <pass> ][ -a ]
 -r	site configuration path
 -u	connection user name
 -p	connection user password
 -a	auto connect

```