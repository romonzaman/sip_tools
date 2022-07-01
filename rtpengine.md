#### rtpengine setup

```bash
apt install debhelper  libcurl4-openssl-dev libpcre3-dev libxmlrpc-core-c3-dev markdown libavfilter-dev libavformat-dev libavresample-dev libevent-dev libglib2.0-dev libhiredis-dev libjson-glib-dev libpcap0.8-dev libpcap-dev libssl-dev dkms module-assistant nfs-common unzip libb-hooks-op-check-perl libexporter-tidy-perl libbencode-perl libcrypt-rijndael-perl libdigest-hmac-perl libio-socket-inet6-perl libsocket6-perl
```

[optional]
```bash
curl https://codeload.github.com/BelledonneCommunications/bcg729/tar.gz/1.0.4 > bcg729_1.0.4.orig.tar.gz
tar zxf bcg729_1.0.4.orig.tar.gz
cd bcg729-1.0.4
git clone https://github.com/ossobv/bcg729-deb.git debian
dpkg-buildpackage -us -uc -sa
dpkg -i libbcg729-0_1.0.4-0osso3+deb9_amd64.deb
dpkg -i libbcg729-dev_1.0.4-0osso3+deb9_amd64.deb
```

```
#nano /etc/apt/sources.list
#deb http://archive.ubuntu.com/ubuntu focal-backports main restricted universe multiverse
```

```bash
git clone https://github.com/sipwise/rtpengine.git
cd rtpengine
dpkg-buildpackage --no-sign
```

```bash
apt-get install default-libmysqlclient-dev gperf libcrypt-openssl-rsa-perl libdigest-crc-perl libio-multiplex-perl libiptc-dev libjson-perl libmosquitto-dev libnet-interface-perl libspandsp-dev libsystemd-dev libwebsockets-dev libxtables-dev python3-websockets libconfig-tiny-perl

dpkg -i ngcp-rtpengine-daemon_10.5.0.0+0~mr10.5.0.0_amd64.deb
dpkg -i ngcp-rtpengine-iptables_10.5.0.0+0~mr10.5.0.0_amd64.deb
dpkg -i ngcp-rtpengine-kernel-dkms_10.5.0.0+0~mr10.5.0.0_all.deb
dpkg -i ngcp-rtpengine-recording-daemon_10.5.0.0+0~mr10.5.0.0_amd64.deb
dpkg -i ngcp-rtpengine-utils_10.5.0.0+0~mr10.5.0.0_all.deb
dpkg -i ngcp-rtpengine_10.5.0.0+0~mr10.5.0.0_all.deb
```

```
/usr/bin/rtpengine -f -E --no-log-timestamps --pidfile /run/rtpengine/ngcp-rtpengine-daemon.pid --config-file /etc/rtpengine/rtpengine.conf
```
