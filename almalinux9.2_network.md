# ネットワーク設定

## OS情報

```Shell
[root@host1 ~]#
[root@host1 ~]# cat /etc/almalinux-release
AlmaLinux release 9.2 (Turquoise Kodkod)
[root@host1 ~]#
[root@host1 ~]# cat /etc/os-release
NAME="AlmaLinux"
VERSION="9.2 (Turquoise Kodkod)"
ID="almalinux"
ID_LIKE="rhel centos fedora"
VERSION_ID="9.2"
PLATFORM_ID="platform:el9"
PRETTY_NAME="AlmaLinux 9.2 (Turquoise Kodkod)"
ANSI_COLOR="0;34"
LOGO="fedora-logo-icon"
CPE_NAME="cpe:/o:almalinux:almalinux:9::baseos"
HOME_URL="https://almalinux.org/"
DOCUMENTATION_URL="https://wiki.almalinux.org/"
BUG_REPORT_URL="https://bugs.almalinux.org/"

ALMALINUX_MANTISBT_PROJECT="AlmaLinux-9"
ALMALINUX_MANTISBT_PROJECT_VERSION="9.2"
REDHAT_SUPPORT_PRODUCT="AlmaLinux"
REDHAT_SUPPORT_PRODUCT_VERSION="9.2"
[root@host1 ~]#
```

## OSインストール直後の状態

`network-scripts` による設定変更は廃止(deprecated)されているので `mncli` コマンドでの操作が必要になる。  
また、`/etc/resolv.conf` も `NetworkManager` が生成するので `/etc/resolv.conf` を編集しないほうが良い。  

```Shell
[root@host1 ~]#
[root@host1 ~]# ls -l /etc/sysconfig/network-scripts/
合計 4
-rw-r--r--. 1 root root 1244  4月 10 21:44 readme-ifcfg-rh.txt
[root@host1 ~]#
[root@host1 ~]# cat /etc/sysconfig/network-scripts/readme-ifcfg-rh.txt
NetworkManager stores new network profiles in keyfile format in the
/etc/NetworkManager/system-connections/ directory.

Previously, NetworkManager stored network profiles in ifcfg format
in this directory (/etc/sysconfig/network-scripts/). However, the ifcfg
format is deprecated. By default, NetworkManager no longer creates
new profiles in this format.

Connection profiles in keyfile format have many benefits. For example,
this format is INI file-based and can easily be parsed and generated.

Each section in NetworkManager keyfiles corresponds to a NetworkManager
setting name as described in the nm-settings(5) and nm-settings-keyfile(5)
man pages. Each key-value-pair in a section is one of the properties
listed in the settings specification of the man page.

If you still use network profiles in ifcfg format, consider migrating
them to keyfile format. To migrate all profiles at once, enter:

# nmcli connection migrate

This command migrates all profiles from ifcfg format to keyfile
format and stores them in /etc/NetworkManager/system-connections/.

Alternatively, to migrate only a specific profile, enter:

# nmcli connection migrate <profile_name|UUID|D-Bus_path>

For further details, see:
* nm-settings-keyfile(5)
* nmcli(1)
[root@host1 ~]#
```

```Shell
[root@host1 ~]# 
[root@host1 ~]# nmcli con
NAME    UUID                                  TYPE      DEVICE 
enp0s3  3075ca3a-1122-3c7a-a5c1-48f7cd8063c0  ethernet  enp0s3 
lo      80baca5b-005f-4db6-a00d-a0324c520a75  loopback  lo     
[root@host1 ~]# 
[root@host1 ~]# 
[root@host1 ~]# nmcli connection show enp0s3
connection.id:                          enp0s3
connection.uuid:                        3075ca3a-1122-3c7a-a5c1-48f7cd8063c0
connection.stable-id:                   --
connection.type:                        802-3-ethernet
connection.interface-name:              enp0s3
connection.autoconnect:                 はい
connection.autoconnect-priority:        -999
connection.autoconnect-retries:         -1 (default)
connection.multi-connect:               0 (default)
connection.auth-retries:                -1
connection.timestamp:                   1694150652
connection.read-only:                   いいえ
connection.permissions:                 --
connection.zone:                        --
connection.master:                      --
connection.slave-type:                  --
connection.autoconnect-slaves:          -1 (default)
connection.secondaries:                 --
connection.gateway-ping-timeout:        0
connection.metered:                     不明
connection.lldp:                        default
connection.mdns:                        -1 (default)
connection.llmnr:                       -1 (default)
connection.dns-over-tls:                -1 (default)
connection.mptcp-flags:                 0x0 (default)
connection.wait-device-timeout:         -1
connection.wait-activation-delay:       -1
802-3-ethernet.port:                    --
802-3-ethernet.speed:                   0
802-3-ethernet.duplex:                  --
802-3-ethernet.auto-negotiate:          いいえ
802-3-ethernet.mac-address:             --
802-3-ethernet.cloned-mac-address:      --
802-3-ethernet.generate-mac-address-mask:--
802-3-ethernet.mac-address-blacklist:   --
802-3-ethernet.mtu:                     自動
802-3-ethernet.s390-subchannels:        --
802-3-ethernet.s390-nettype:            --
802-3-ethernet.s390-options:            --
802-3-ethernet.wake-on-lan:             default
802-3-ethernet.wake-on-lan-password:    --
802-3-ethernet.accept-all-mac-addresses:-1 (default)
ipv4.method:                            manual
ipv4.dns:                               192.168.1.10
ipv4.dns-search:                        --
ipv4.dns-options:                       --
ipv4.dns-priority:                      0
ipv4.addresses:                         192.168.1.101/24
ipv4.gateway:                           192.168.1.1
ipv4.routes:                            --
ipv4.route-metric:                      -1
ipv4.route-table:                       0 (unspec)
ipv4.routing-rules:                     --
ipv4.replace-local-rule:                -1 (default)
ipv4.ignore-auto-routes:                いいえ
ipv4.ignore-auto-dns:                   いいえ
ipv4.dhcp-client-id:                    --
ipv4.dhcp-iaid:                         --
ipv4.dhcp-timeout:                      0 (default)
ipv4.dhcp-send-hostname:                はい
ipv4.dhcp-hostname:                     --
ipv4.dhcp-fqdn:                         --
ipv4.dhcp-hostname-flags:               0x0 (none)
ipv4.never-default:                     いいえ
ipv4.may-fail:                          はい
ipv4.required-timeout:                  -1 (default)
ipv4.dad-timeout:                       -1 (default)
ipv4.dhcp-vendor-class-identifier:      --
ipv4.link-local:                        0 (default)
ipv4.dhcp-reject-servers:               --
ipv4.auto-route-ext-gw:                 -1 (default)
ipv6.method:                            auto
ipv6.dns:                               --
ipv6.dns-search:                        --
ipv6.dns-options:                       --
ipv6.dns-priority:                      0
ipv6.addresses:                         --
ipv6.gateway:                           --
ipv6.routes:                            --
ipv6.route-metric:                      -1
ipv6.route-table:                       0 (unspec)
ipv6.routing-rules:                     --
ipv6.replace-local-rule:                -1 (default)
ipv6.ignore-auto-routes:                いいえ
ipv6.ignore-auto-dns:                   いいえ
ipv6.never-default:                     いいえ
ipv6.may-fail:                          はい
ipv6.required-timeout:                  -1 (default)
ipv6.ip6-privacy:                       -1 (unknown)
ipv6.addr-gen-mode:                     eui64
ipv6.ra-timeout:                        0 (default)
ipv6.mtu:                               自動
ipv6.dhcp-duid:                         --
ipv6.dhcp-iaid:                         --
ipv6.dhcp-timeout:                      0 (default)
ipv6.dhcp-send-hostname:                はい
ipv6.dhcp-hostname:                     --
ipv6.dhcp-hostname-flags:               0x0 (none)
ipv6.auto-route-ext-gw:                 -1 (default)
ipv6.token:                             --
proxy.method:                           none
proxy.browser-only:                     いいえ
proxy.pac-url:                          --
proxy.pac-script:                       --
GENERAL.NAME:                           enp0s3
GENERAL.UUID:                           3075ca3a-1122-3c7a-a5c1-48f7cd8063c0
GENERAL.DEVICES:                        enp0s3
GENERAL.IP-IFACE:                       enp0s3
GENERAL.STATE:                          アクティベート済み
GENERAL.DEFAULT:                        はい
GENERAL.DEFAULT6:                       いいえ
GENERAL.SPEC-OBJECT:                    --
GENERAL.VPN:                            いいえ
GENERAL.DBUS-PATH:                      /org/freedesktop/NetworkManager/ActiveConnection/2
GENERAL.CON-PATH:                       /org/freedesktop/NetworkManager/Settings/1
GENERAL.ZONE:                           --
GENERAL.MASTER-PATH:                    --
IP4.ADDRESS[1]:                         192.168.1.101/24
IP4.GATEWAY:                            192.168.1.1
IP4.ROUTE[1]:                           dst = 192.168.1.0/24, nh = 0.0.0.0, mt = 100
IP4.ROUTE[2]:                           dst = 0.0.0.0/0, nh = 192.168.1.1, mt = 100
IP4.DNS[1]:                             192.168.1.10
IP6.ADDRESS[1]:                         fe80::a00:27ff:febe:a8a6/64
IP6.GATEWAY:                            --
IP6.ROUTE[1]:                           dst = fe80::/64, nh = ::, mt = 1024
[root@host1 ~]# 
[root@host1 ~]# cat /etc/NetworkManager/system-connections/enp0s3.nmconnection 
[connection]
id=enp0s3
uuid=3075ca3a-1122-3c7a-a5c1-48f7cd8063c0
type=ethernet
autoconnect-priority=-999
interface-name=enp0s3
timestamp=1694144965

[ethernet]

[ipv4]
address1=192.168.1.101/24,192.168.1.1
dns=192.168.1.10;
method=manual

[ipv6]
addr-gen-mode=eui64
method=auto

[proxy]
[root@host1 ~]# 
```


```Shell
[root@host1 ~]#
[root@host1 ~]# cat /etc/resolv.conf
# Generated by NetworkManager
search alpha.jp
nameserver 192.168.1.10
[root@host1 ~]#
```

## 設定変更


```Shell
[root@host1 ~]# 
[root@host1 ~]# nmcli con
NAME    UUID                                  TYPE      DEVICE 
enp0s3  3075ca3a-1122-3c7a-a5c1-48f7cd8063c0  ethernet  enp0s3 
lo      80baca5b-005f-4db6-a00d-a0324c520a75  loopback  lo     
[root@host1 ~]# 
```

IPアドレスを設定する
```Shell
[root@host1 ~]#
[root@host1 ~]# nmcli con mod enp0s3 ipv4.addresses 192.168.1.1/24
[root@host1 ~]#
```


デフォルトゲートウェイを設定する
```Shell
[root@host1 ~]#
[root@host1 ~]# nmcli con mod enp0s3 ipv4.gateway  192.168.1.254/24
[root@host1 ~]#
```

参照するDNSサーバーを追加する
```Shell
[root@host1 ~]#
[root@host1 ~]# nmcli conn mod enp0s3 +ipv4.dns 8.8.8.8
[root@host1 ~]# nmcli conn mod enp0s3 +ipv4.dns 8.8.8.9
[root@host1 ~]#
```

参照するDNSサーバーを削除する
```Shell
[root@host1 ~]#
[root@host1 ~]# nmcli conn mod enp0s3 -ipv4.dns 8.8.8.8
[root@host1 ~]# nmcli conn mod enp0s3 -ipv4.dns 8.8.8.9
[root@host1 ~]#
```

IPv6を無効化する
```Shell
[root@host1 ~]#
[root@host1 ~]# nmcli con mod enp0s3 ipv6.method ignore
[root@host1 ~]# nmcli con mod enp0s3 ipv4.may-fail no
[root@host1 ~]#
```

設定を反映させる
```Shell
[root@host1 ~]#
[root@host1 ~]# nmcli con down enp0s3 && nmcli con up enp0s3
[root@host1 ~]#

または

[root@host1 ~]#
[root@host1 ~]# systemctl restart NetworkManager
[root@host1 ~]#
```

## その他の操作

追加したNICを登録する。  
ここではVirtualBoxでホストオンリーアダプターを追加した際の操作を例示しています。  

```Shell
[root@host00 ~]# 
[root@host00 ~]# nmcli con
NAME    UUID                                  TYPE      DEVICE 
enp0s3  d1ce7368-eda2-34c4-a40a-f93122e9646f  ethernet  enp0s3 
lo      6c022664-89ba-428f-826e-955b3bb3f507  loopback  lo     
[root@host00 ~]#
[root@host00 ~]# nmcli con add type ethernet ifname enp0s8 con-name enp0s8
接続 'enp0s8' (7dc80882-d8b6-463b-8b33-c10b80fadc19) が正常に追加されました。
[root@host00 ~]# 
[root@host00 ~]# nmcli con
NAME    UUID                                  TYPE      DEVICE 
enp0s3  d1ce7368-eda2-34c4-a40a-f93122e9646f  ethernet  enp0s3 
enp0s8  7dc80882-d8b6-463b-8b33-c10b80fadc19  ethernet  enp0s8 
lo      6c022664-89ba-428f-826e-955b3bb3f507  loopback  lo     
[root@host00 ~]# 
[root@host00 ~]# nmcli con mod enp0s8 ipv4.addresses 192.168.56.10/24
[root@host00 ~]# nmcli con mod enp0s8 ipv4.method manual
[root@host00 ~]# 
[root@host00 ~]# cat /etc/NetworkManager/system-connections/enp0s8.nmconnection 
[connection]
id=enp0s8
uuid=7dc80882-d8b6-463b-8b33-c10b80fadc19
type=ethernet
interface-name=enp0s8
timestamp=1694153318

[ethernet]

[ipv4]
address1=192.168.56.10/24
method=manual

[ipv6]
addr-gen-mode=default
method=auto

[proxy]
[root@host00 ~]# 
[root@host00 ~]# reboot
　　：
＜再起動＞
　　：
[root@host00 ~]# 
[root@host00 ~]# ip address show
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:a7:55:1c brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.10/24 brd 192.168.1.255 scope global noprefixroute enp0s3
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fea7:551c/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:7b:97:6f brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.10/24 brd 192.168.56.255 scope global dynamic noprefixroute enp0s8
       valid_lft 498sec preferred_lft 498sec
    inet6 fe80::3669:14:5300:108/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
[root@host00 ~]# 
```