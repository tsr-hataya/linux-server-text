# 第3章 DNSサーバー構築

## 3.6 講師マシンへのDNSキャッシュサーバーの設定

### 3.6.1 必要なパッケージを確認

```Shell
[root@host0 ~]#
[root@host0 ~]# rpm -q unbound bind-utils
パッケージ unbound はインストールされていません。
bind-utils-9.16.23-11.el9.x86_64
[root@host0 ~]#
```

### 3.6.2 unboundのインストール

※インターネットに接続できない前提で、事前に [リポジトリをDVDメディアに切り替える](/almalinux9.2_repo.md) を実施。

DVDメディアがマウントされていて、リポジトリリストにDVDメディアが表示することを確認する。
```Shell
[root@host0 ~]#
[root@host0 ~]# df -h
ファイルシス               サイズ  使用  残り 使用% マウント位置
devtmpfs                     4.0M     0  4.0M    0% /dev
tmpfs                        890M     0  890M    0% /dev/shm
tmpfs                        356M  8.7M  347M    3% /run
/dev/mapper/almalinux-root    17G  5.4G   12G   32% /
/dev/sda1                   1014M  290M  725M   29% /boot
tmpfs                        178M  100K  178M    1% /run/user/0
/dev/sr0                     8.7G  8.7G     0  100% /run/media/root/AlmaLinux-9-2-x86_64-dvd
[root@host0 ~]#
[root@host0 ~]# dnf repolist
repo id                                       repo の名前
media-AppStream                               AlmaLinux 9 - DVD Media AppStream
media-BaseOS                                  AlmaLinux 9 - DVD Media BaseOS
[root@host0 ~]#
```

`unbound` のパッケージがあるか確認する。
```Shell
[root@host0 ~]#
[root@host0 ~]# dnf search unbound
メタデータの期限切れの最終確認: 0:50:53 前の 2023年09月08日 15時47分10秒 に実施しました。
=========================================== 名前 完全一致: unbound ===========================================
unbound.x86_64 : Validating, recursive, and caching DNS(SEC) resolver
========================================= 名前 & 概要 一致: unbound ==========================================
pcp-pmda-unbound.x86_64 : Performance Co-Pilot (PCP) metrics for the Unbound DNS Resolver
python3-unbound.x86_64 : Python 3 modules and extensions for unbound
unbound-libs.i686 : Libraries used by the unbound server and client applications
unbound-libs.x86_64 : Libraries used by the unbound server and client applications
[root@host0 ~]#
[root@host0 ~]# dnf info unbound
メタデータの期限切れの最終確認: 0:51:03 前の 2023年09月08日 15時47分10秒 に実施しました。
利用可能なパッケージ
名前         : unbound
バージョン   : 1.16.2
リリース     : 3.el9
Arch         : x86_64
サイズ       : 963 k
ソース       : unbound-1.16.2-3.el9.src.rpm
リポジトリー : media-AppStream
概要         : Validating, recursive, and caching DNS(SEC) resolver
URL          : https://nlnetlabs.nl/projects/unbound/
ライセンス   : BSD
説明         : Unbound is a validating, recursive, and caching DNS(SEC) resolver.
             :
             : The C implementation of Unbound is developed and maintained by NLnet
             : Labs. It is based on ideas and algorithms taken from a java prototype
             : developed by Verisign labs, Nominet, Kirei and ep.net.
             :
             : Unbound is designed as a set of modular components, so that also
             : DNSSEC (secure DNS) validation and stub-resolvers (that do not run
             : as a server, but are linked into an application) are easily possible.

[root@host0 ~]#

```


`unbound` をインストールする
```Shell
[root@host0 ~]#
[root@host0 ~]# dnf install unbound
メタデータの期限切れの最終確認: 0:00:36 前の 2023年09月08日 16時41分39秒 に実施しました。
依存関係が解決しました。
==============================================================================================================
 パッケージ                アーキテクチャー    バージョン                  リポジトリー                 サイズ
==============================================================================================================
インストール:
 unbound                   x86_64              1.16.2-3.el9                media-AppStream              963 k
依存関係のインストール:
 unbound-libs              x86_64              1.16.2-3.el9                media-AppStream              547 k

トランザクションの概要
==============================================================================================================
インストール  2 パッケージ

合計サイズ: 1.5 M
インストール後のサイズ: 4.8 M
これでよろしいですか? [y/N]: y
パッケージのダウンロード:
AlmaLinux 9 - DVD Media AppStream                                             3.0 MB/s | 3.1 kB     00:00
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
  scriptletの実行中: unbound-libs-1.16.2-3.el9.x86_64                                                     1/2
  インストール中   : unbound-libs-1.16.2-3.el9.x86_64                                                     1/2
  scriptletの実行中: unbound-libs-1.16.2-3.el9.x86_64                                                     1/2
Created symlink /etc/systemd/system/timers.target.wants/unbound-anchor.timer → /usr/lib/systemd/system/unbound-anchor.timer.

  インストール中   : unbound-1.16.2-3.el9.x86_64                                                          2/2
  scriptletの実行中: unbound-1.16.2-3.el9.x86_64                                                          2/2
  検証             : unbound-1.16.2-3.el9.x86_64                                                          1/2
  検証             : unbound-libs-1.16.2-3.el9.x86_64                                                     2/2

インストール済み:
  unbound-1.16.2-3.el9.x86_64                         unbound-libs-1.16.2-3.el9.x86_64

完了しました!
[root@host0 ~]#
[root@host0 ~]#
[root@host0 ~]# rpm -q unbound
unbound-1.16.2-3.el9.x86_64
[root@host0 ~]#
[root@host0 ~]# unbound -V
Version 1.16.2

Configure line: --build=x86_64-redhat-linux-gnu --host=x86_64-redhat-linux-gnu --program-prefix= --disable-dependency-tracking --prefix=/usr --exec-prefix=/usr --bindir=/usr/bin --sbindir=/usr/sbin --sysconfdir=/etc --datadir=/usr/share --includedir=/usr/include --libdir=/usr/lib64 --libexecdir=/usr/libexec --localstatedir=/var --sharedstatedir=/var/lib --mandir=/usr/share/man --infodir=/usr/share/info --with-pythonmodule --with-pyunbound PYTHON=/usr/bin/python3 --enable-dnstap --with-libnghttp2 --with-libevent --with-pthreads --with-ssl --disable-rpath --disable-static --enable-relro-now --enable-pie --enable-subnet --enable-ipsecmod --with-conf-file=/etc/unbound/unbound.conf --with-pidfile=/run/unbound/unbound.pid --enable-sha2 --disable-gost --enable-ecdsa --with-rootkey-file=/var/lib/unbound/root.key --enable-linux-ip-local-port-range --disable-sha1
Linked libs: libevent 2.1.12-stable (it uses epoll), OpenSSL 3.0.7 1 Nov 2022
Linked modules: dns64 python ipsecmod subnetcache respip validator iterator

BSD licensed, see LICENSE in source package for details.
Report bugs to unbound-bugs@nlnetlabs.nl or https://github.com/NLnetLabs/unbound/issues
[root@host0 ~]#
[root@host0 ~]#
[root@host0 ~]# systemctl list-unit-files -t service | grep unbound
unbound-anchor.service                     static          -
unbound-keygen.service                     disabled        disabled
unbound.service                            disabled        disabled
[root@host0 ~]#
```

### 3.6.3 リクエストを受け付けるIPアドレスの設定

```Shell
[root@host0 ~]#
[root@host0 ~]# vi /etc/unbound/local.d/interface.conf
interface: 192.168.1.10
interface: 127.0.0.1
[root@host0 ~]#
[root@host0 ~]#
```


### 3.6.4 利用可能なクライアントの設定

```Shell
[root@host0 ~]#
[root@host0 ~]# vi /etc/unbound/local.d/client.conf
access-contorol: 192.168.1.0/24 allow
[root@host0 ~]#
[root@host0 ~]#
```

### 3.6.5 受講者ドメインの設定

```Shell
[root@host0 ~]#
[root@host0 ~]# vi /etc/unbound/conf.d/stub.conf
stub-zone:
    name: alpha.jp.
    stub-addr: 192.168.1.101
    stub-prime: no
    stub-first: no
stub-zone:
    name: beta.jp.
    stub-addr: 192.168.1.102
    stub-prime: no
    stub-first: no
[root@host0 ~]#
```

### 3.6.6 unbound-keygenの起動

```Shell
[root@host0 ~]#
[root@host0 ~]# systemctl start unbound-keygen
[root@host0 ~]#
[root@host0 ~]# systemctl status unbound-keygen
○ unbound-keygen.service - Unbound Control Key And Certificate Generator
     Loaded: loaded (/usr/lib/systemd/system/unbound-keygen.service; disabled; preset: disabled)
     Active: inactive (dead)

 9月 08 16:59:05 host0 systemd[1]: Starting Unbound Control Key And Certificate Generator...
 9月 08 16:59:05 host0 unbound-control-setup[43975]: setup in directory /etc/unbound/
 9月 08 16:59:06 host0 unbound-control-setup[43983]: Certificate request self-signature ok
 9月 08 16:59:06 host0 unbound-control-setup[43983]: subject=CN = unbound-control
 9月 08 16:59:06 host0 unbound-control-setup[43975]: removing artifacts
 9月 08 16:59:06 host0 unbound-control-setup[43975]: Setup success. Certificates created. Enable in unbound.c>
 9月 08 16:59:06 host0 systemd[1]: unbound-keygen.service: Deactivated successfully.
 9月 08 16:59:06 host0 systemd[1]: Finished Unbound Control Key And Certificate Generator.
 9月 08 16:59:06 host0 systemd[1]: unbound-keygen.service: Consumed 1.153s CPU time.
[root@host0 ~]#
[root@host0 ~]#
[root@host0 ~]# ls -la /etc/unbound/
合計 84
drwxr-xr-x    5 root root      214  9月  8 16:59 .
drwxr-xr-x. 138 root root     8192  9月  8 16:42 ..
drwxr-xr-x    2 root unbound    47  9月  8 16:55 conf.d
-rw-r--r--    1 root root     1261  4月  7 22:17 icannbundle.pem
drwxr-xr-x    2 root unbound    29  9月  8 16:42 keys.d
drwxr-xr-x    2 root unbound    58  9月  8 16:48 local.d
-rw-r--r--    1 root root      556  4月  7 23:24 root.key
-rw-r--r--    1 root root    48528  4月  7 22:17 unbound.conf
-rw-------    1 root unbound  2484  9月  8 16:59 unbound_control.key   <--- 追加された
-rw-r-----    1 root unbound  1501  9月  8 16:59 unbound_control.pem   <--- 追加された
-rw-------    1 root unbound  2484  9月  8 16:59 unbound_server.key   <--- 追加された
-rw-r-----    1 root unbound  1549  9月  8 16:59 unbound_server.pem   <--- 追加された
[root@host0 ~]#
```

### 3.6.7 unbound-keygenの起動

```Shell
[root@host0 ~]#
[root@host0 ~]# unbound-checkconf
unbound-checkconf: no errors in /etc/unbound/unbound.conf
[root@host0 ~]#
```

```Shell
[root@host0 ~]#
[root@host0 ~]#
[root@host0 ~]# cat /etc/unbound/local.d/interface.conf
interface: 192.168.1.10
interface: 127.0.0.1...   <--- 余計な文字(末尾の...)が含まれている
[root@host0 ~]#
[root@host0 ~]# unbound-checkconf
[1694160242] unbound-checkconf[44088:0] fatal error: cannot parse interface specified as '127.0.0.1...'
[root@host0 ~]#
```

### 3.6.8 ファイアウォールの設定

```Shell
[root@host0 ~]#
[root@host0 ~]# firewall-cmd --add-service=dns
success
[root@host0 ~]#
[root@host0 ~]# firewall-cmd --list-all
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3
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
[root@host0 ~]#
[root@host0 ~]# firewall-cmd --runtime-to-permanent
success
[root@host0 ~]#
```

### 3.6.9 unboundの起動と確認

```Shell
[root@host0 ~]#
[root@host0 ~]# systemctl start unbound
[root@host0 ~]#
[root@host0 ~]# systemctl status unbound
● unbound.service - Unbound recursive Domain Name Server
     Loaded: loaded (/usr/lib/systemd/system/unbound.service; disabled; preset: disabled)
     Active: active (running) since Fri 2023-09-08 17:14:51 JST; 4s ago
    Process: 44160 ExecStartPre=/usr/sbin/unbound-checkconf (code=exited, status=0/SUCCESS)
    Process: 44161 ExecStartPre=/bin/bash -c if [ ! "$DISABLE_UNBOUND_ANCHOR" == "yes" ]; then /usr/sbin/unbo>
   Main PID: 44163 (unbound)
      Tasks: 4 (limit: 10992)
     Memory: 22.5M
        CPU: 107ms
     CGroup: /system.slice/unbound.service
             mq44163 /usr/sbin/unbound -d

 9月 08 17:14:51 host0 systemd[1]: Starting Unbound recursive Domain Name Server...
 9月 08 17:14:51 host0 unbound-checkconf[44160]: unbound-checkconf: no errors in /etc/unbound/unbound.conf
 9月 08 17:14:51 host0 systemd[1]: Started Unbound recursive Domain Name Server.
 9月 08 17:14:51 host0 unbound[44163]: [44163:0] notice: init module 0: ipsecmod
 9月 08 17:14:51 host0 unbound[44163]: [44163:0] notice: init module 1: validator
 9月 08 17:14:51 host0 unbound[44163]: [44163:0] notice: init module 2: iterator
 9月 08 17:14:51 host0 unbound[44163]: [44163:0] info: start of service (unbound 1.16.2).
[root@host0 ~]#
[root@host0 ~]#
[root@host0 ~]# ss -an | grep :53
udp   UNCONN 0      0                                       127.0.0.1:53               0.0.0.0:*
udp   UNCONN 0      0                                    192.168.1.10:53               0.0.0.0:*
udp   UNCONN 0      0                                       127.0.0.1:53               0.0.0.0:*
udp   UNCONN 0      0                                    192.168.1.10:53               0.0.0.0:*
udp   UNCONN 0      0                                       127.0.0.1:53               0.0.0.0:*
udp   UNCONN 0      0                                    192.168.1.10:53               0.0.0.0:*
udp   UNCONN 0      0                                       127.0.0.1:53               0.0.0.0:*
udp   UNCONN 0      0                                    192.168.1.10:53               0.0.0.0:*
udp   UNCONN 0      0                                         0.0.0.0:5353             0.0.0.0:*
udp   UNCONN 0      0                                            [::]:5353                [::]:*
tcp   LISTEN 0      256                                  192.168.1.10:53               0.0.0.0:*
tcp   LISTEN 0      256                                  192.168.1.10:53               0.0.0.0:*
tcp   LISTEN 0      256                                  192.168.1.10:53               0.0.0.0:*
tcp   LISTEN 0      256                                  192.168.1.10:53               0.0.0.0:*
tcp   LISTEN 0      256                                     127.0.0.1:53               0.0.0.0:*
tcp   LISTEN 0      256                                     127.0.0.1:53               0.0.0.0:*
tcp   LISTEN 0      256                                     127.0.0.1:53               0.0.0.0:*
tcp   LISTEN 0      256                                     127.0.0.1:53               0.0.0.0:*
[root@host0 ~]#
[root@host0 ~]#
[root@host0 ~]# netstat -an | grep :53
tcp        0      0 192.168.1.10:53         0.0.0.0:*               LISTEN
tcp        0      0 127.0.0.1:53            0.0.0.0:*               LISTEN
udp        0      0 127.0.0.1:53            0.0.0.0:*
udp        0      0 192.168.1.10:53         0.0.0.0:*
udp        0      0 127.0.0.1:53            0.0.0.0:*
udp        0      0 192.168.1.10:53         0.0.0.0:*
udp        0      0 127.0.0.1:53            0.0.0.0:*
udp        0      0 192.168.1.10:53         0.0.0.0:*
udp        0      0 127.0.0.1:53            0.0.0.0:*
udp        0      0 192.168.1.10:53         0.0.0.0:*
udp        0      0 0.0.0.0:5353            0.0.0.0:*
udp6       0      0 :::5353                 :::*
[root@host0 ~]#
```

### 3.6.10 自動起動の設定

```Shell
[root@host0 ~]#
[root@host0 ~]# systemctl is-enabled unbound
disabled
[root@host0 ~]#
[root@host0 ~]# systemctl enable unbound
Created symlink /etc/systemd/system/multi-user.target.wants/unbound.service → /usr/lib/systemd/system/unbound.service.

[root@host0 ~]#
[root@host0 ~]# systemctl is-enabled unbound
enabled
[root@host0 ~]#
```

### 3.6.11 名前解決の確認

```Shell
[root@host0 ~]#
[root@host0 ~]# cat /etc/resolv.conf
# Generated by NetworkManager
nameserver 8.8.8.8
nameserver 8.8.4.4
[root@host0 ~]#
```

```Shell
[root@host0 ~]#
[root@host0 ~]# host www.yahoo.co.jp 192.168.1.10
Using domain server:
Name: 192.168.1.10
Address: 192.168.1.10#53
Aliases:

www.yahoo.co.jp is an alias for edge12.g.yimg.jp.
edge12.g.yimg.jp has address 183.79.248.252
[root@host0 ~]#
[root@host0 ~]# host www.yahoo.co.jp 127.0.0.1
Using domain server:
Name: 127.0.0.1
Address: 127.0.0.1#53
Aliases:

www.yahoo.co.jp is an alias for edge12.g.yimg.jp.
edge12.g.yimg.jp has address 182.22.28.252
[root@host0 ~]#
```

```Shell
[root@host0 ~]#
[root@host0 ~]# dig @192.168.1.10 www.yahoo.co.jp

; <<>> DiG 9.16.23-RH <<>> @192.168.1.10 www.yahoo.co.jp
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 59046
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;www.yahoo.co.jp.               IN      A

;; ANSWER SECTION:
www.yahoo.co.jp.        873     IN      CNAME   edge12.g.yimg.jp.
edge12.g.yimg.jp.       33      IN      A       183.79.248.252

;; Query time: 0 msec
;; SERVER: 192.168.1.10#53(192.168.1.10)
;; WHEN: Fri Sep 08 17:34:06 JST 2023
;; MSG SIZE  rcvd: 88

[root@host0 ~]#
[root@host0 ~]# dig @127.0.0.1 www.yahoo.co.jp

; <<>> DiG 9.16.23-RH <<>> @127.0.0.1 www.yahoo.co.jp
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 7454
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;www.yahoo.co.jp.               IN      A

;; ANSWER SECTION:
www.yahoo.co.jp.        776     IN      CNAME   edge12.g.yimg.jp.
edge12.g.yimg.jp.       30      IN      A       182.22.28.252

;; Query time: 0 msec
;; SERVER: 127.0.0.1#53(127.0.0.1)
;; WHEN: Fri Sep 08 17:26:57 JST 2023
;; MSG SIZE  rcvd: 88

[root@host0 ~]#
```

```Shell
[root@host0 ~]#
[root@host0 ~]# nslookup www.yahoo.co.jp 192.168.1.10
Server:         192.168.1.10
Address:        192.168.1.10#53

Non-authoritative answer:
www.yahoo.co.jp canonical name = edge12.g.yimg.jp.
Name:   edge12.g.yimg.jp
Address: 183.79.248.252

[root@host0 ~]#
[root@host0 ~]# nslookup www.yahoo.co.jp 127.0.0.1
Server:         127.0.0.1
Address:        127.0.0.1#53

Non-authoritative answer:
www.yahoo.co.jp canonical name = edge12.g.yimg.jp.
Name:   edge12.g.yimg.jp
Address: 183.79.249.124

[root@host0 ~]#
```