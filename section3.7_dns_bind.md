# 第3章 DNSサーバー構築

## 3.7 受講者マシンへのDNSサーバーの設定

### 3.7.2 DNSパッケージを確認

```Shell
[root@host1 ~]#
[root@host1 ~]# rpm -q bind bind-chroot bind-utils
パッケージ bind はインストールされていません。
パッケージ bind-chroot はインストールされていません。
bind-utils-9.16.23-11.el9.x86_64
[root@host1 ~]#
```

### 3.7.3 bindのインストール

※インターネットに接続できない前提で、事前に [リポジトリをDVDメディアに切り替える](/almalinux9.2_repo.md) を実施。

DVDメディアがマウントされていて、リポジトリリストにDVDメディアが表示することを確認する。
```Shell
[root@host1 ~]#
[root@host1 ~]# df -h
ファイルシス               サイズ  使用  残り 使用% マウント位置
devtmpfs                     4.0M     0  4.0M    0% /dev
tmpfs                        890M     0  890M    0% /dev/shm
tmpfs                        356M  5.6M  351M    2% /run
/dev/mapper/almalinux-root    17G  5.1G   12G   30% /
/dev/sda1                   1014M  290M  725M   29% /boot
tmpfs                        178M  108K  178M    1% /run/user/0
/dev/sr0                     8.7G  8.7G     0  100% /run/media/root/AlmaLinux-9-2-x86_64-dvd
[root@host1 ~]#
[root@host1 ~]# dnf repolist
repo id                                       repo の名前
media-AppStream                               AlmaLinux 9 - DVD Media AppStream
media-BaseOS                                  AlmaLinux 9 - DVD Media BaseOS
[root@host1 ~]#
[root@host1 ~]#
```

`bind` と `bind-chroot` のパッケージがあるか確認する。
```Shell
[root@host1 ~]#
[root@host1 ~]# dnf search bind
AlmaLinux 9 - DVD Media BaseOS                                                 14 MB/s | 1.9 MB     00:00
AlmaLinux 9 - DVD Media AppStream                                              33 MB/s | 6.9 MB     00:00
=========================================== 名前 & 概要 一致: bind ===========================================
bind.x86_64 : The Berkeley Internet Name Domain (BIND) DNS (Domain Name System) server
bind-chroot.x86_64 : A chroot runtime environment for the ISC BIND DNS server, named(8)
　　：
　　：
============================================== 名前 一致: bind ===============================================
　　：
　　：
============================================== 概要 一致: bind ===============================================
　　：
　　：
[root@host1 ~]#
[root@host1 ~]# dnf info bind
メタデータの期限切れの最終確認: 0:00:56 前の 2023年09月12日 16時03分23秒 に実施しました。
利用可能なパッケージ
名前         : bind
エポック     : 32
バージョン   : 9.16.23
リリース     : 11.el9
Arch         : x86_64
サイズ       : 488 k
ソース       : bind-9.16.23-11.el9.src.rpm
リポジトリー : media-AppStream
概要         : The Berkeley Internet Name Domain (BIND) DNS (Domain Name System) server
URL          : https://www.isc.org/downloads/bind/
ライセンス   : MPLv2.0
説明         : BIND (Berkeley Internet Name Domain) is an implementation of the DNS
             : (Domain Name System) protocols. BIND includes a DNS server (named),
             : which resolves host names to IP addresses; a resolver library
             : (routines for applications to use when interfacing with DNS); and
             : tools for verifying that the DNS server is operating properly.

[root@host1 ~]#
[root@host1 ~]# dnf info bind-chroot
メタデータの期限切れの最終確認: 0:01:00 前の 2023年09月12日 16時03分23秒 に実施しました。
利用可能なパッケージ
名前         : bind-chroot
エポック     : 32
バージョン   : 9.16.23
リリース     : 11.el9
Arch         : x86_64
サイズ       : 17 k
ソース       : bind-9.16.23-11.el9.src.rpm
リポジトリー : media-AppStream
概要         : A chroot runtime environment for the ISC BIND DNS server, named(8)
URL          : https://www.isc.org/downloads/bind/
ライセンス   : MPLv2.0
説明         : This package contains a tree of files which can be used as a
             : chroot(2) jail for the named(8) program from the BIND package.
             : Based on the code from Jan "Yenya" Kasprzak <kas@fi.muni.cz>

[root@host1 ~]#
```


`bind` と `bind-chroot` をインストールする

```Shell
[root@host1 ~]#
[root@host1 ~]# dnf install bind bind-chroot bind-utils
メタデータの期限切れの最終確認: 0:03:03 前の 2023年09月12日 16時03分23秒 に実施しました。
パッケージ bind-utils-32:9.16.23-11.el9.x86_64 は既にインストールされています。
依存関係が解決しました。
==============================================================================================================
 パッケージ                   アーキテクチャー  バージョン                   リポジトリー               サイズ
==============================================================================================================
インストール:
 bind                         x86_64            32:9.16.23-11.el9            media-AppStream            488 k
 bind-chroot                  x86_64            32:9.16.23-11.el9            media-AppStream             17 k
依存関係のインストール:
 bind-dnssec-doc              noarch            32:9.16.23-11.el9            media-AppStream             45 k
 python3-bind                 noarch            32:9.16.23-11.el9            media-AppStream             61 k
 python3-ply                  noarch            3.11-14.el9                  media-BaseOS               103 k
弱い依存関係のインストール:
 bind-dnssec-utils            x86_64            32:9.16.23-11.el9            media-AppStream            113 k

トランザクションの概要
==============================================================================================================
インストール  6 パッケージ

合計サイズ: 827 k
インストール後のサイズ: 2.5 M
これでよろしいですか? [y/N]: y
パッケージのダウンロード:
AlmaLinux 9 - DVD Media BaseOS                                                3.0 MB/s | 3.1 kB     00:00
GPG 鍵 0xB86B3716 をインポート中:
 Userid     : "AlmaLinux OS 9 <packager@almalinux.org>"
 Fingerprint: BF18 AC28 7617 8908 D6E7 1267 D36C B86C B86B 3716
 From       : /etc/pki/rpm-gpg/RPM-GPG-KEY-AlmaLinux-9
これでよろしいですか? [y/N]: y
鍵のインポートに成功しました
トランザクションの確認を実行中
トランザクションの確認に成功しました。
トランザクションのテストを実行中
トランザクションのテストに成功しました。
トランザクションを実行中
  準備             :                                                                                      1/1
  インストール中   : bind-dnssec-doc-32:9.16.23-11.el9.noarch                                             1/6
  インストール中   : python3-ply-3.11-14.el9.noarch                                                       2/6
  インストール中   : python3-bind-32:9.16.23-11.el9.noarch                                                3/6
  インストール中   : bind-dnssec-utils-32:9.16.23-11.el9.x86_64                                           4/6
  scriptletの実行中: bind-32:9.16.23-11.el9.x86_64                                                        5/6
  インストール中   : bind-32:9.16.23-11.el9.x86_64                                                        5/6
  scriptletの実行中: bind-32:9.16.23-11.el9.x86_64                                                        5/6
  インストール中   : bind-chroot-32:9.16.23-11.el9.x86_64                                                 6/6
  scriptletの実行中: bind-chroot-32:9.16.23-11.el9.x86_64                                                 6/6
  検証             : python3-ply-3.11-14.el9.noarch                                                       1/6
  検証             : bind-32:9.16.23-11.el9.x86_64                                                        2/6
  検証             : bind-chroot-32:9.16.23-11.el9.x86_64                                                 3/6
  検証             : bind-dnssec-doc-32:9.16.23-11.el9.noarch                                             4/6
  検証             : bind-dnssec-utils-32:9.16.23-11.el9.x86_64                                           5/6
  検証             : python3-bind-32:9.16.23-11.el9.noarch                                                6/6

インストール済み:
  bind-32:9.16.23-11.el9.x86_64                        bind-chroot-32:9.16.23-11.el9.x86_64
  bind-dnssec-doc-32:9.16.23-11.el9.noarch             bind-dnssec-utils-32:9.16.23-11.el9.x86_64
  python3-bind-32:9.16.23-11.el9.noarch                python3-ply-3.11-14.el9.noarch

完了しました!
[root@host1 ~]#
[root@host1 ~]#
[root@host1 ~]# rpm -q bind bind-chroot bind-utils
bind-9.16.23-11.el9.x86_64
bind-chroot-9.16.23-11.el9.x86_64
bind-utils-9.16.23-11.el9.x86_64
[root@host1 ~]#
[root@host1 ~]#
[root@host1 ~]# systemctl list-unit-files -t service | grep named
named-chroot-setup.service                 static          -
named-chroot.service                       disabled        disabled
named-setup-rndc.service                   static          -
named.service                              disabled        disabled
systemd-hostnamed.service                  static          -
[root@host1 ~]#
[root@host1 ~]#
```


### 3.7.4 ゾーン設定の流れ

```Shell
[root@host0 ~]#
[root@host0 ~]#
[root@host0 ~]#
```

### 3.7.5 /etc/named.confの基本設定

インストール直後の `/etc/named.conf`

```Shell
[root@host1 ~]#
[root@host1 ~]# cat /etc/named.conf
//
// named.conf
//
// Provided by Red Hat bind package to configure the ISC BIND named(8) DNS
// server as a caching only nameserver (as a localhost DNS resolver only).
//
// See /usr/share/doc/bind*/sample/ for example named configuration files.
//

options {
        listen-on port 53 { 127.0.0.1; };
        listen-on-v6 port 53 { ::1; };
        directory       "/var/named";
        dump-file       "/var/named/data/cache_dump.db";
        statistics-file "/var/named/data/named_stats.txt";
        memstatistics-file "/var/named/data/named_mem_stats.txt";
        secroots-file   "/var/named/data/named.secroots";
        recursing-file  "/var/named/data/named.recursing";
        allow-query     { localhost; };

        /*
         - If you are building an AUTHORITATIVE DNS server, do NOT enable recursion.
         - If you are building a RECURSIVE (caching) DNS server, you need to enable
           recursion.
         - If your recursive DNS server has a public IP address, you MUST enable access
           control to limit queries to your legitimate users. Failing to do so will
           cause your server to become part of large scale DNS amplification
           attacks. Implementing BCP38 within your network would greatly
           reduce such attack surface
        */
        recursion yes;

        dnssec-validation yes;

        managed-keys-directory "/var/named/dynamic";
        geoip-directory "/usr/share/GeoIP";

        pid-file "/run/named/named.pid";
        session-keyfile "/run/named/session.key";

        /* https://fedoraproject.org/wiki/Changes/CryptoPolicy */
        include "/etc/crypto-policies/back-ends/bind.config";
};

logging {
        channel default_debug {
                file "data/named.run";
                severity dynamic;
        };
};

zone "." IN {
        type hint;
        file "named.ca";
};

include "/etc/named.rfc1912.zones";
include "/etc/named.root.key";

[root@host1 ~]#
```

設定ファイルをバックアップしておく。

```Shell
[root@host1 ~]#
[root@host1 ~]# cp -p /etc/named.conf /etc/named.conf.orig
[root@host1 ~]#
[root@host1 ~]# ls -l /etc/named.conf*
-rw-r-----. 1 root named 1722  4月  6 01:11 /etc/named.conf
-rw-r-----. 1 root named 1722  4月  6 01:11 /etc/named.conf.orig
[root@host1 ~]#
```

設定ファイルをバックアップしておく。

```Shell
[root@host1 ~]#
[root@host1 ~]# cp -p /etc/named.conf /etc/named.conf.orig
[root@host1 ~]#
[root@host1 ~]# ls -l /etc/named.conf*
-rw-r-----. 1 root named 1722  4月  6 01:11 /etc/named.conf
-rw-r-----. 1 root named 1722  4月  6 01:11 /etc/named.conf.orig
[root@host1 ~]#
```

設定ファイルを修正する

```Shell
[root@host1 ~]#
[root@host1 ~]# vi /etc/named.conf
//
// named.conf
//
// Provided by Red Hat bind package to configure the ISC BIND named(8) DNS
// server as a caching only nameserver (as a localhost DNS resolver only).
//
// See /usr/share/doc/bind*/sample/ for example named configuration files.
//

options {
        listen-on port 53 { 127.0.0.1; 192.168.1.101; };  <---★ 修正
        listen-on-v6 port 53 { ::1; };
        directory       "/var/named";
        dump-file       "/var/named/data/cache_dump.db";
        statistics-file "/var/named/data/named_stats.txt";
        memstatistics-file "/var/named/data/named_mem_stats.txt";
        secroots-file   "/var/named/data/named.secroots";
        recursing-file  "/var/named/data/named.recursing";
        allow-query     { any; };  <---★ 修正

        /*
         - If you are building an AUTHORITATIVE DNS server, do NOT enable recursion.
         - If you are building a RECURSIVE (caching) DNS server, you need to enable
           recursion.
         - If your recursive DNS server has a public IP address, you MUST enable access
           control to limit queries to your legitimate users. Failing to do so will
           cause your server to become part of large scale DNS amplification
           attacks. Implementing BCP38 within your network would greatly
           reduce such attack surface
        */
        recursion no;  <---★ 修正

        dnssec-validation yes;

        managed-keys-directory "/var/named/dynamic";
        geoip-directory "/usr/share/GeoIP";

        pid-file "/run/named/named.pid";
        session-keyfile "/run/named/session.key";

        /* https://fedoraproject.org/wiki/Changes/CryptoPolicy */
        include "/etc/crypto-policies/back-ends/bind.config";
};

logging {
        channel default_debug {
                file "data/named.run";
                severity dynamic;
        };
};

zone "." IN {
        type hint;
        file "named.ca";
};

include "/etc/named.rfc1912.zones";
include "/etc/named.root.key";

zone "alpha.jp" IN {  <---★ 正引きゾーンの設定を追加
    type master;
    file "alpha.jp.zone";
    allow-update{ none; };
};

[root@host1 ~]#
```


### 3.7.6 ゾーンファイルの設定

```Shell
[root@host1 ~]#
[root@host1 ~]# cd /var/named/
[root@host1 named]#
[root@host1 named]# pwd
/var/named
[root@host1 named]#
[root@host1 named]# ls -l
合計 16
drwxr-x---. 8 root  named   73  9月 12 16:06 chroot
drwxrwx---. 2 named named    6  4月  6 01:11 data
drwxrwx---. 2 named named    6  4月  6 01:11 dynamic
-rw-r-----. 1 root  named 2253  4月  6 01:11 named.ca
-rw-r-----. 1 root  named  152  4月  6 01:11 named.empty
-rw-r-----. 1 root  named  152  4月  6 01:11 named.localhost
-rw-r-----. 1 root  named  168  4月  6 01:11 named.loopback
drwxrwx---. 2 named named    6  4月  6 01:11 slaves
[root@host1 named]#
```

```Shell
[root@host1 named]#
[root@host1 named]# cp -p named.empty alpha.jp.zone
[root@host1 named]#
[root@host1 named]# ls -l
合計 20
-rw-r-----. 1 root  named  152  4月  6 01:11 alpha.jp.zone
drwxr-x---. 8 root  named   73  9月 12 16:06 chroot
drwxrwx---. 2 named named    6  4月  6 01:11 data
drwxrwx---. 2 named named    6  4月  6 01:11 dynamic
-rw-r-----. 1 root  named 2253  4月  6 01:11 named.ca
-rw-r-----. 1 root  named  152  4月  6 01:11 named.empty
-rw-r-----. 1 root  named  152  4月  6 01:11 named.localhost
-rw-r-----. 1 root  named  168  4月  6 01:11 named.loopback
drwxrwx---. 2 named named    6  4月  6 01:11 slaves
[root@host1 named]#
[root@host1 named]#
[root@host1 named]# vi alpha.jp.zone
$TTL 3H
$ORIGIN alpha.jp.
@       IN SOA host1 root (
                                        2023091201      ; serial
                                        1D      ; refresh
                                        1H      ; retry
                                        1W      ; expire
                                        3H )    ; minimum
        NS      host1.alpha.jp.
        MX 10   mail.alpha.jp.

host1   A       192.168.1.101
www     A       192.168.1.101
mail    A       192.168.1.101
vhost1  CNAME   www
vhost2  CNAME   www
[root@host1 named]#
```



### 3.7.7 設定ファイルの書式確認と注意点

設定ファイルのチェック

`named-checkconf` でエラーがない場合は何も表示されない。

```Shell
[root@host1 ~]#
[root@host1 ~]# named-checkconf /etc/named.conf
[root@host1 ~]#
```

`named-checkconf` でエラーがある場合はエラー箇所を教えてくれる。  

```Shell
[root@host1 ~]#
[root@host1 ~]# named-checkconf
/etc/named.conf:65: missing ';' before end of file
[root@host1 ~]#
```


ゾーンファイルのチェック


`named-checkzone` でエラーがない場合は OK と表示される。

```Shell
[root@host1 named]#
[root@host1 named]# named-checkzone alpha.jp. /var/named/alpha.jp.zone
zone alpha.jp/IN: loaded serial 2023091201
OK
[root@host1 named]#
[root@host1 named]#
```

`named-checkzone` でエラーがある場合はエラー箇所を教えてくれる。 

```Shell
[root@host1 named]#
[root@host1 named]# named-checkzone alpha.jp. /var/named/alpha.jp.zone
dns_rdata_fromtext: /var/named/alpha.jp.zone:10: near 'mail.alpha.jp.': not a valid number
zone alpha.jp/IN: loading from master file /var/named/alpha.jp.zone failed: not a valid number
zone alpha.jp/IN: not loaded due to errors.
[root@host1 named]#
```


### 3.7.8 ファイアウォールの設定

```Shell
[root@host1 named]#
[root@host1 named]# firewall-cmd --add-service=dns
success
[root@host1 named]#
[root@host1 named]# firewall-cmd --list-all
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3 enp0s8
  sources:
  services: cockpit dhcpv6-client dns ssh   <--- dnsが追加された
  ports:
  protocols:
  forward: yes
  masquerade: no
  forward-ports:
  source-ports:
  icmp-blocks:
  rich rules:
[root@host1 named]#
[root@host1 named]# firewall-cmd --runtime-to-permanent
success
[root@host1 named]#
```

### 3.7.9 bindの起動と確認

```Shell
[root@host1 named]#
[root@host1 named]# systemctl start named-chroot
[root@host1 named]#
[root@host1 named]#
[root@host1 named]# systemctl status named-chroot
● named-chroot.service - Berkeley Internet Name Domain (DNS)
     Loaded: loaded (/usr/lib/systemd/system/named-chroot.service; disabled; preset: disabled)
     Active: active (running) since Tue 2023-09-12 16:37:33 JST; 4s ago
    Process: 41085 ExecStartPre=/bin/bash -c if [ ! "$DISABLE_ZONE_CHECKING" == "yes" ]; then /usr/sbin/named>
    Process: 41095 ExecStart=/usr/sbin/named -u named -c ${NAMEDCONF} -t /var/named/chroot $OPTIONS (code=exi>
   Main PID: 41103 (named)
      Tasks: 4 (limit: 10992)
     Memory: 11.5M
        CPU: 51ms
     CGroup: /system.slice/named-chroot.service
             mq41103 /usr/sbin/named -u named -c /etc/named.conf -t /var/named/chroot

 9月 12 16:37:33 host1.alpha.jp named[41103]: network unreachable resolving './NS/IN': 2001:dc3::35#53
 9月 12 16:37:33 host1.alpha.jp named[41103]: network unreachable resolving './DNSKEY/IN': 2001:500:1::53#53
 9月 12 16:37:33 host1.alpha.jp named[41103]: network unreachable resolving './NS/IN': 2001:500:1::53#53
 9月 12 16:37:33 host1.alpha.jp named[41103]: network unreachable resolving './DNSKEY/IN': 2001:500:2f::f#53
 9月 12 16:37:33 host1.alpha.jp named[41103]: network unreachable resolving './NS/IN': 2001:500:2f::f#53
 9月 12 16:37:33 host1.alpha.jp named[41103]: network unreachable resolving './DNSKEY/IN': 2001:500:2f::f#53
 9月 12 16:37:33 host1.alpha.jp named[41103]: network unreachable resolving './DNSKEY/IN': 2001:503:ba3e::2:3>
 9月 12 16:37:33 host1.alpha.jp named[41103]: network unreachable resolving './DNSKEY/IN': 2001:503:c27::2:30>
 9月 12 16:37:33 host1.alpha.jp named[41103]: managed-keys-zone: Initializing automatic trust anchor manageme>
 9月 12 16:37:33 host1.alpha.jp named[41103]: resolver priming query complete
[root@host1 named]#
[root@host1 named]#
[root@host1 named]# ss -anl | grep :53
udp   UNCONN 0      0                                       0.0.0.0:5353               0.0.0.0:*
udp   UNCONN 0      0                                       127.0.0.1:53               0.0.0.0:*
udp   UNCONN 0      0                                            [::]:5353                [::]:*
udp   UNCONN 0      0                                           [::1]:53                  [::]:*
tcp   LISTEN 0      10                                      127.0.0.1:53               0.0.0.0:*
tcp   LISTEN 0      10                                          [::1]:53                  [::]:*
[root@host1 named]#
[root@host1 named]# netstat -anl | grep :53
tcp        0      0 127.0.0.1:53            0.0.0.0:*               LISTEN
tcp6       0      0 ::1:53                  :::*                    LISTEN
udp        0      0 0.0.0.0:5353            0.0.0.0:*
udp        0      0 127.0.0.1:53            0.0.0.0:*
udp6       0      0 :::5353                 :::*
udp6       0      0 ::1:53                  :::*
[root@host1 named]#
```

### 3.7.10 自動起動の設定

```Shell
[root@host1 named]#
[root@host1 named]# systemctl is-enabled named-chroot
disabled
[root@host1 named]#
[root@host1 named]# systemctl enable named-chroot
Created symlink /etc/systemd/system/multi-user.target.wants/named-chroot.service → /usr/lib/systemd/system/named-chroot.service.
[root@host1 named]#
[root@host1 named]# systemctl is-enabled named-chroot
enabled
[root@host1 named]#
```

### 3.7.11 名前解決の確認

```Shell
[root@host1 ~]#
[root@host1 ~]# cat /etc/resolv.conf
# Generated by NetworkManager
search alpha.jp
nameserver 192.168.1.10
[root@host1 ~]#
```

```Shell
[root@host1 ~]#
[root@host1 ~]# host host1.alpha.jp 192.168.1.101
Using domain server:
Name: 192.168.1.101
Address: 192.168.1.101#53
Aliases:

host1.alpha.jp has address 192.168.1.101
[root@host1 ~]#
[root@host1 ~]# host www.alpha.jp 192.168.1.101
Using domain server:
Name: 192.168.1.101
Address: 192.168.1.101#53
Aliases:

www.alpha.jp has address 192.168.1.101
[root@host1 ~]#
[root@host1 ~]# host mail.alpha.jp 192.168.1.101
Using domain server:
Name: 192.168.1.101
Address: 192.168.1.101#53
Aliases:

mail.alpha.jp has address 192.168.1.101
[root@host1 ~]#
[root@host1 ~]# host -t ns alpha.jp 192.168.1.101
Using domain server:
Name: 192.168.1.101
Address: 192.168.1.101#53
Aliases:

alpha.jp name server host1.alpha.jp.
[root@host1 ~]#
[root@host1 ~]# host -t mx alpha.jp 192.168.1.101
Using domain server:
Name: 192.168.1.101
Address: 192.168.1.101#53
Aliases:

alpha.jp mail is handled by 10 mail.alpha.jp.
[root@host1 ~]#
```

```Shell
[root@host1 ~]#
[root@host1 ~]#
[root@host1 ~]# dig alpha.jp azfr @192.168.1.101

; <<>> DiG 9.16.23-RH <<>> alpha.jp azfr @192.168.1.101
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 2564
;; flags: qr rd ra; QUERY: 1, ANSWER: 0, AUTHORITY: 1, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;alpha.jp.                      IN      A

;; AUTHORITY SECTION:
alpha.jp.               3600    IN      SOA     host1.alpha.jp. root.alpha.jp. 2023091201 86400 3600 604800 10800

;; Query time: 22 msec
;; SERVER: 192.168.1.10#53(192.168.1.10)
;; WHEN: Thu Sep 14 12:58:31 JST 2023
;; MSG SIZE  rcvd: 84

;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: REFUSED, id: 59231
;; flags: qr rd; QUERY: 1, ANSWER: 0, AUTHORITY: 0, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 765122ea6f76d93d01000000650284e7dd3512833a2de490 (good)
;; QUESTION SECTION:
;azfr.                          IN      A

;; Query time: 0 msec
;; SERVER: 192.168.1.101#53(192.168.1.101)
;; WHEN: Thu Sep 14 12:58:31 JST 2023
;; MSG SIZE  rcvd: 61

[root@host1 ~]#
[root@host1 ~]# dig host1.alpha.jp @192.168.1.101

; <<>> DiG 9.16.23-RH <<>> host1.alpha.jp @192.168.1.101
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 45914
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 235c98be4f5e839c010000006502845d417ca430ca543f4c (good)
;; QUESTION SECTION:
;host1.alpha.jp.                        IN      A

;; ANSWER SECTION:
host1.alpha.jp.         10800   IN      A       192.168.1.101

;; Query time: 0 msec
;; SERVER: 192.168.1.101#53(192.168.1.101)
;; WHEN: Thu Sep 14 12:56:13 JST 2023
;; MSG SIZE  rcvd: 87

[root@host1 ~]#
[root@host1 ~]# dig www.alpha.jp @192.168.1.101

; <<>> DiG 9.16.23-RH <<>> www.alpha.jp @192.168.1.101
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 53245
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 0e101a3d0b0c64b5010000006502846425b19c8eec9eaded (good)
;; QUESTION SECTION:
;www.alpha.jp.                  IN      A

;; ANSWER SECTION:
www.alpha.jp.           10800   IN      A       192.168.1.101

;; Query time: 0 msec
;; SERVER: 192.168.1.101#53(192.168.1.101)
;; WHEN: Thu Sep 14 12:56:20 JST 2023
;; MSG SIZE  rcvd: 85

[root@host1 ~]#
[root@host1 ~]# dig mail.alpha.jp @192.168.1.101

; <<>> DiG 9.16.23-RH <<>> mail.alpha.jp @192.168.1.101
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 36152
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: 34d14a5a8d319b58010000006502846abfacab70857fb701 (good)
;; QUESTION SECTION:
;mail.alpha.jp.                 IN      A

;; ANSWER SECTION:
mail.alpha.jp.          10800   IN      A       192.168.1.101

;; Query time: 0 msec
;; SERVER: 192.168.1.101#53(192.168.1.101)
;; WHEN: Thu Sep 14 12:56:26 JST 2023
;; MSG SIZE  rcvd: 86

[root@host1 ~]#
[root@host1 ~]# dig ns alpha.jp @192.168.1.101

; <<>> DiG 9.16.23-RH <<>> ns alpha.jp @192.168.1.101
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 12432
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 2
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: d0c252b1eb92dfb20100000065028471d344a7be6afdbeca (good)
;; QUESTION SECTION:
;alpha.jp.                      IN      NS

;; ANSWER SECTION:
alpha.jp.               10800   IN      NS      host1.alpha.jp.

;; ADDITIONAL SECTION:
host1.alpha.jp.         10800   IN      A       192.168.1.101

;; Query time: 0 msec
;; SERVER: 192.168.1.101#53(192.168.1.101)
;; WHEN: Thu Sep 14 12:56:33 JST 2023
;; MSG SIZE  rcvd: 101

[root@host1 ~]#
[root@host1 ~]# dig mx alpha.jp @192.168.1.101

; <<>> DiG 9.16.23-RH <<>> mx alpha.jp @192.168.1.101
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 50832
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 2
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
; COOKIE: ece37ee5c371e94c0100000065028476efcddc75d445e6a2 (good)
;; QUESTION SECTION:
;alpha.jp.                      IN      MX

;; ANSWER SECTION:
alpha.jp.               10800   IN      MX      10 mail.alpha.jp.

;; ADDITIONAL SECTION:
mail.alpha.jp.          10800   IN      A       192.168.1.101

;; Query time: 0 msec
;; SERVER: 192.168.1.101#53(192.168.1.101)
;; WHEN: Thu Sep 14 12:56:38 JST 2023
;; MSG SIZE  rcvd: 102

[root@host1 ~]#
```

```Shell
[root@host1 ~]#
[root@host1 ~]# nslookup host1.alpha.jp 192.168.1.101
Server:         192.168.1.101
Address:        192.168.1.101#53

Name:   host1.alpha.jp
Address: 192.168.1.101

[root@host1 ~]#
[root@host1 ~]# nslookup www.alpha.jp 192.168.1.101
Server:         192.168.1.101
Address:        192.168.1.101#53

Name:   www.alpha.jp
Address: 192.168.1.101

[root@host1 ~]#
[root@host1 ~]# nslookup mail.alpha.jp 192.168.1.101
Server:         192.168.1.101
Address:        192.168.1.101#53

Name:   mail.alpha.jp
Address: 192.168.1.101

[root@host1 ~]#
[root@host1 ~]# nslookup -type=ns alpha.jp 192.168.1.101
Server:         192.168.1.101
Address:        192.168.1.101#53

alpha.jp        nameserver = host1.alpha.jp.

[root@host1 ~]#
[root@host1 ~]# nslookup -type=mx alpha.jp 192.168.1.101
Server:         192.168.1.101
Address:        192.168.1.101#53

alpha.jp        mail exchanger = 10 mail.alpha.jp.

[root@host1 ~]#
```