# 第5章 メールサーバー構築

現行テキスト(v3.0.2)からの差分：
- Thunderbirdのバージョンが新しくなっており画面が変更されている  

そのた気がついたこと  
- インストール後に画面解像度を1024x768ぐらいに変更しておいたほうが良い。  
- Thunderbirdの初期設定を再度実施したい場合は `~/.thunderbird` を削除すれば良い。
- ホストにIPアドレスが割り当てられるタイミングと、postfixが起動するタイミングが合わないのか、自動起動を有効化しているpostfixが起動に失敗している時があるので、postfixが動作しているか確認をしたほうが良いかも。

  ```Shell
  [root@host1 ~]#
  [root@host1 ~]# systemctl status postfix
  × postfix.service - Postfix Mail Transport Agent
      Loaded: loaded (/usr/lib/systemd/system/postfix.service; enabled; preset: disabled)
      Active: failed (Result: exit-code) since Wed 2023-09-27 16:32:45 JST; 53s ago
      Process: 1065 ExecStartPre=/usr/sbin/restorecon -R /var/spool/postfix/pid/master.pid (code=exited, status=255/EXCEPTION)
      Process: 1093 ExecStartPre=/usr/libexec/postfix/aliasesdb (code=exited, status=0/SUCCESS)
      Process: 1118 ExecStartPre=/usr/libexec/postfix/chroot-update (code=exited, status=0/SUCCESS)
      Process: 1132 ExecStart=/usr/sbin/postfix start (code=exited, status=1/FAILURE)
          CPU: 97ms

  9月 27 16:32:44 host1.alpha.jp systemd[1]: Starting Postfix Mail Transport Agent...
  9月 27 16:32:44 host1.alpha.jp restorecon[1065]: /usr/sbin/restorecon: lstat(/var/spool/postfix/pid/master.pid) failed: No such file or directory
  9月 27 16:32:44 host1.alpha.jp postfix[1132]: fatal: parameter inet_interfaces: no local interface found for 192.168.1.101
  9月 27 16:32:45 host1.alpha.jp systemd[1]: postfix.service: Control process exited, code=exited, status=1/FAILURE
  9月 27 16:32:45 host1.alpha.jp systemd[1]: postfix.service: Failed with result 'exit-code'.
  9月 27 16:32:45 host1.alpha.jp systemd[1]: Failed to start Postfix Mail Transport Agent.
  [root@host1 ~]# 
  [root@host1 ~]# systemctl restart postfix
  [root@host1 ~]#
  [root@host1 ~]# systemctl status postfix
  ● postfix.service - Postfix Mail Transport Agent
      Loaded: loaded (/usr/lib/systemd/system/postfix.service; enabled; preset: disabled)
      Active: active (running) since Wed 2023-09-27 16:35:19 JST; 1s ago
      Process: 2446 ExecStartPre=/usr/sbin/restorecon -R /var/spool/postfix/pid/master.pid (code=exited, status=255/EXCEPTION)
      Process: 2447 ExecStartPre=/usr/libexec/postfix/aliasesdb (code=exited, status=0/SUCCESS)
      Process: 2449 ExecStartPre=/usr/libexec/postfix/chroot-update (code=exited, status=0/SUCCESS)
      Process: 2450 ExecStart=/usr/sbin/postfix start (code=exited, status=0/SUCCESS)
    Main PID: 2518 (master)
        Tasks: 3 (limit: 10992)
      Memory: 4.4M
          CPU: 414ms
      CGroup: /system.slice/postfix.service
              tq2518 /usr/libexec/postfix/master -w
              tq2519 pickup -l -t unix -u
              mq2520 qmgr -l -t unix -u

  9月 27 16:35:19 host1.alpha.jp systemd[1]: Starting Postfix Mail Transport Agent...
  9月 27 16:35:19 host1.alpha.jp restorecon[2446]: /usr/sbin/restorecon: lstat(/var/spool/postfix/pid/master.pid) failed: No such file or directory
  9月 27 16:35:19 host1.alpha.jp postfix/postfix-script[2516]: starting the Postfix mail system
  9月 27 16:35:19 host1.alpha.jp postfix/master[2518]: daemon started -- version 3.5.9, configuration /etc/postfix
  9月 27 16:35:19 host1.alpha.jp systemd[1]: Started Postfix Mail Transport Agent.
  [root@host1 ~]#
  ```


## 5.7 メールクライアントソフトでのメールの送受信


### 5.7.1 Dovecotパッケージの追加


```Shell
[root@host1 ~]#
[root@host1 ~]# dnf search dovecot
メタデータの期限切れの最終確認: 4 days, 23:23:55 前の 2023年09月14日 17時23分37秒 に実施しました。
=========================================== 名前 完全一致: dovecot ===========================================
dovecot.x86_64 : Secure imap and pop3 server
========================================= 名前 & 概要 一致: dovecot ==========================================
dovecot-mysql.x86_64 : MySQL back end for dovecot
dovecot-pgsql.x86_64 : Postgres SQL back end for dovecot
dovecot-pigeonhole.x86_64 : Sieve and managesieve plug-in for dovecot
[root@host1 ~]#
[root@host1 ~]# dnf info dovecot
AlmaLinux 9 - DVD Media BaseOS                                                3.8 MB/s | 3.9 kB     00:00
AlmaLinux 9 - DVD Media AppStream                                             4.2 MB/s | 4.3 kB     00:00
利用可能なパッケージ
名前         : dovecot
エポック     : 1
バージョン   : 2.3.16
リリース     : 8.el9
Arch         : x86_64
サイズ       : 4.7 M
ソース       : dovecot-2.3.16-8.el9.src.rpm
リポジトリー : media-AppStream
概要         : Secure imap and pop3 server
URL          : https://www.dovecot.org/
ライセンス   : MIT and LGPLv2
説明         : Dovecot is an IMAP server for Linux/UNIX-like systems, written with security
             : primarily in mind.  It also contains a small POP3 server.  It supports mail
             : in either of maildir or mbox formats.
             :
             : The SQL drivers and authentication plug-ins are in their subpackages.

[root@host1 ~]#
[root@host1 ~]# dnf install dovecot
メタデータの期限切れの最終確認: 0:00:23 前の 2023年09月19日 16時47分46秒 に実施しました。
依存関係が解決しました。
==============================================================================================================
 パッケージ           Arch          バージョン                                   リポジトリー           サイズ
==============================================================================================================
インストール:
 dovecot              x86_64        1:2.3.16-8.el9                               media-AppStream        4.7 M
依存関係のインストール:
 clucene-core         x86_64        2.3.3.4-42.20130812.e8e3d20git.el9           media-AppStream        585 k
 libexttextcat        x86_64        3.4.5-11.el9                                 media-AppStream        209 k

トランザクションの概要
==============================================================================================================
インストール  3 パッケージ

合計サイズ: 5.5 M
インストール後のサイズ: 20 M
これでよろしいですか? [y/N]: y
パッケージのダウンロード:
トランザクションの確認を実行中
トランザクションの確認に成功しました。
トランザクションのテストを実行中
トランザクションのテストに成功しました。
トランザクションを実行中
  準備             :                                                                                      1/1
  インストール中   : libexttextcat-3.4.5-11.el9.x86_64                                                    1/3
  インストール中   : clucene-core-2.3.3.4-42.20130812.e8e3d20git.el9.x86_64                               2/3
  scriptletの実行中: dovecot-1:2.3.16-8.el9.x86_64                                                        3/3
  インストール中   : dovecot-1:2.3.16-8.el9.x86_64                                                        3/3
  scriptletの実行中: dovecot-1:2.3.16-8.el9.x86_64                                                        3/3
  検証             : clucene-core-2.3.3.4-42.20130812.e8e3d20git.el9.x86_64                               1/3
  検証             : dovecot-1:2.3.16-8.el9.x86_64                                                        2/3
  検証             : libexttextcat-3.4.5-11.el9.x86_64                                                    3/3

インストール済み:
  clucene-core-2.3.3.4-42.20130812.e8e3d20git.el9.x86_64             dovecot-1:2.3.16-8.el9.x86_64
  libexttextcat-3.4.5-11.el9.x86_64

完了しました!
[root@host1 ~]#
[root@host1 ~]# rpm -q dovecot
dovecot-2.3.16-8.el9.x86_64
[root@host1 ~]#
[root@host1 ~]# dovecot --version
2.3.16 (7e2e900c1a)
[root@host1 ~]#
```


### 5.7.2 Dovecotの設定

```Shell
[root@host1 ~]#
[root@host1 ~]# cd /etc/dovecot/
[root@host1 dovecot]#
[root@host1 dovecot]# pwd
/etc/dovecot
[root@host1 dovecot]#
[root@host1 dovecot]# ls -la /etc/dovecot/
合計 24
drwxr-xr-x.   3 root root   40  9月 19 16:48 .
drwxr-xr-x. 140 root root 8192  9月 19 16:48 ..
drwxr-xr-x.   2 root root 4096  9月 19 16:48 conf.d
-rw-r--r--.   1 root root 4333  8月  6  2021 dovecot.conf
[root@host1 dovecot]#
[root@host1 dovecot]# ls -la /etc/dovecot/conf.d/
合計 132
drwxr-xr-x. 2 root root  4096  9月 19 16:48 .
drwxr-xr-x. 3 root root    40  9月 19 16:48 ..
-rw-r--r--. 1 root root  5248  8月  6  2021 10-auth.conf
-rw-r--r--. 1 root root  1781  8月  6  2021 10-director.conf
-rw-r--r--. 1 root root  3757  8月  6  2021 10-logging.conf
-rw-r--r--. 1 root root 17795  4月  7 14:22 10-mail.conf
-rw-r--r--. 1 root root  3569  8月  6  2021 10-master.conf
-rw-r--r--. 1 root root  1585  8月  6  2021 10-metrics.conf
-rw-r--r--. 1 root root  3648  4月  7 14:22 10-ssl.conf
-rw-r--r--. 1 root root  1657  8月  6  2021 15-lda.conf
-rw-r--r--. 1 root root  3111  8月  6  2021 15-mailboxes.conf
-rw-r--r--. 1 root root  4520  8月  6  2021 20-imap.conf
-rw-r--r--. 1 root root  1367  8月  6  2021 20-lmtp.conf
-rw-r--r--. 1 root root  4066  8月  6  2021 20-pop3.conf
-rw-r--r--. 1 root root  4299  8月  6  2021 20-submission.conf
-rw-r--r--. 1 root root   676  8月  6  2021 90-acl.conf
-rw-r--r--. 1 root root   292  8月  6  2021 90-plugin.conf
-rw-r--r--. 1 root root  2596  8月  6  2021 90-quota.conf
-rw-r--r--. 1 root root   499  8月  6  2021 auth-checkpassword.conf.ext
-rw-r--r--. 1 root root   489  8月  6  2021 auth-deny.conf.ext
-rw-r--r--. 1 root root   343  8月  6  2021 auth-dict.conf.ext
-rw-r--r--. 1 root root   924  8月  6  2021 auth-ldap.conf.ext
-rw-r--r--. 1 root root   561  8月  6  2021 auth-master.conf.ext
-rw-r--r--. 1 root root   515  8月  6  2021 auth-passwdfile.conf.ext
-rw-r--r--. 1 root root   788  8月  6  2021 auth-sql.conf.ext
-rw-r--r--. 1 root root   611  8月  6  2021 auth-static.conf.ext
-rw-r--r--. 1 root root  2182  8月  6  2021 auth-system.conf.ext
[root@host1 dovecot]#
```


設定ファイルをバックアップしておく。

```Shell
[root@host1 dovecot]#
[root@host1 dovecot]# cp -p dovecot.conf dovecot.conf.orig
[root@host1 dovecot]#
[root@host1 dovecot]# ls -la
合計 32
drwxr-xr-x.   3 root root   65  9月 19 16:56 .
drwxr-xr-x. 140 root root 8192  9月 19 16:48 ..
drwxr-xr-x.   2 root root 4096  9月 19 16:48 conf.d
-rw-r--r--.   1 root root 4333  8月  6  2021 dovecot.conf
-rw-r--r--.   1 root root 4333  8月  6  2021 dovecot.conf.orig
[root@host1 dovecot]#
[root@host1 dovecot]#
[root@host1 dovecot]# cp conf.d/10-mail.conf conf.d/10-mail.conf.orig
[root@host1 dovecot]#
[root@host1 dovecot]# cp conf.d/10-auth.conf conf.d/10-auth.conf.orig
[root@host1 dovecot]#
[root@host1 dovecot]# cp conf.d/10-ssl.conf conf.d/10-ssl.conf.orig
[root@host1 dovecot]#
[root@host1 dovecot]# ls -la conf.d/
合計 164
drwxr-xr-x. 2 root root  4096  9月 19 17:02 .
drwxr-xr-x. 3 root root    65  9月 19 16:56 ..
-rw-r--r--. 1 root root  5248  8月  6  2021 10-auth.conf
-rw-r--r--. 1 root root  5248  9月 19 17:02 10-auth.conf.orig
-rw-r--r--. 1 root root  1781  8月  6  2021 10-director.conf
-rw-r--r--. 1 root root  3757  8月  6  2021 10-logging.conf
-rw-r--r--. 1 root root 17897  9月 19 17:02 10-mail.conf
-rw-r--r--. 1 root root 17795  9月 19 16:58 10-mail.conf.orig
-rw-r--r--. 1 root root  3569  8月  6  2021 10-master.conf
-rw-r--r--. 1 root root  1585  8月  6  2021 10-metrics.conf
-rw-r--r--. 1 root root  3648  4月  7 14:22 10-ssl.conf
-rw-r--r--. 1 root root  3648  9月 19 17:02 10-ssl.conf.orig
-rw-r--r--. 1 root root  1657  8月  6  2021 15-lda.conf
-rw-r--r--. 1 root root  3111  8月  6  2021 15-mailboxes.conf
-rw-r--r--. 1 root root  4520  8月  6  2021 20-imap.conf
-rw-r--r--. 1 root root  1367  8月  6  2021 20-lmtp.conf
-rw-r--r--. 1 root root  4066  8月  6  2021 20-pop3.conf
-rw-r--r--. 1 root root  4299  8月  6  2021 20-submission.conf
-rw-r--r--. 1 root root   676  8月  6  2021 90-acl.conf
-rw-r--r--. 1 root root   292  8月  6  2021 90-plugin.conf
-rw-r--r--. 1 root root  2596  8月  6  2021 90-quota.conf
-rw-r--r--. 1 root root   499  8月  6  2021 auth-checkpassword.conf.ext
-rw-r--r--. 1 root root   489  8月  6  2021 auth-deny.conf.ext
-rw-r--r--. 1 root root   343  8月  6  2021 auth-dict.conf.ext
-rw-r--r--. 1 root root   924  8月  6  2021 auth-ldap.conf.ext
-rw-r--r--. 1 root root   561  8月  6  2021 auth-master.conf.ext
-rw-r--r--. 1 root root   515  8月  6  2021 auth-passwdfile.conf.ext
-rw-r--r--. 1 root root   788  8月  6  2021 auth-sql.conf.ext
-rw-r--r--. 1 root root   611  8月  6  2021 auth-static.conf.ext
-rw-r--r--. 1 root root  2182  8月  6  2021 auth-system.conf.ext
[root@host1 dovecot]#
```

`/etc/dovecot/dovecot.conf` の設定を変更する

```Shell
[root@host1 dovecot]#
[root@host1 dovecot]# vi dovecot.conf
　：
# Protocols we want to be serving.
#protocols = imap pop3 lmtp submission
protocols = imap pop3
　：
# A comma separated list of IPs or hosts where to listen in for connections.
# "*" listens in all IPv4 interfaces, "::" listens in all IPv6 interfaces.
# If you want to specify non-default ports or anything more complex,
# edit conf.d/master.conf.
#listen = *, ::
listen = *, ::
　：
[root@host1 dovecot]#
```


`/etc/dovecot/conf.d/10-mail.conf` の設定を変更する

```Shell
[root@host1 dovecot]#
[root@host1 dovecot]# vi conf.d/10-mail.conf
##
## Mailbox locations and namespaces
##

# Location for users' mailboxes. The default is empty, which means that Dovecot
# tries to find the mailboxes automatically. This won't work if the user
# doesn't yet have any mail, so you should explicitly tell Dovecot the full
# location.
#
# If you're using mbox, giving a path to the INBOX file (eg. /var/mail/%u)
# isn't enough. You'll also need to tell Dovecot where the other mailboxes are
# kept. This is called the "root mail directory", and it must be the first
# path given in the mail_location setting.
#
# There are a few special variables you can use, eg.:
#
#   %u - username
#   %n - user part in user@domain, same as %u if there's no domain
#   %d - domain part in user@domain, empty if there's no domain
#   %h - home directory
#
# See doc/wiki/Variables.txt for full list. Some examples:
#
#   mail_location = maildir:~/Maildir
#   mail_location = mbox:~/mail:INBOX=/var/mail/%u
#   mail_location = mbox:/var/mail/%d/%1n/%n:INDEX=/var/indexes/%d/%1n/%n
#
# <doc/wiki/MailLocation.txt>
#
#mail_location =
mail_location = mbox:~/mail:INBOX=/var/mail/%u
　：
# Group to enable temporarily for privileged operations. Currently this is
# used only with INBOX when either its initial creation or dotlocking fails.
# Typically this is set to "mail" to give access to /var/mail.
#mail_privileged_group =
mail_privileged_group = mail
　：
# Grant access to these supplementary groups for mail processes. Typically
# these are used to set up access to shared mailboxes. Note that it may be
# dangerous to set these if users can create symlinks (e.g. if "mail" group is
# set here, ln -s /var/mail ~/mail/var could allow a user to delete others'
# mailboxes, or ln -s /secret/shared/box ~/mail/mybox would allow reading it).
#mail_access_groups =
mail_access_groups = mail
　：
[root@host1 dovecot]#
```

`/etc/dovecot/conf.d/10-auth.conf` の設定を変更する

```Shell
[root@host1 dovecot]#
[root@host1 dovecot]# vi conf.d/10-auth.conf
##
## Authentication processes
##

# Disable LOGIN command and all other plaintext authentications unless
# SSL/TLS is used (LOGINDISABLED capability). Note that if the remote IP
# matches the local IP (ie. you're connecting from the same computer), the
# connection is considered secure and plaintext authentication is allowed.
# See also ssl=required setting.
#disable_plaintext_auth = yes
disable_plaintext_auth = no
　：
[root@host1 dovecot]#
```


`/etc/dovecot/conf.d/10-ssl.conf` の設定を変更する

```Shell
[root@host1 dovecot]#
[root@host1 dovecot]# vi conf.d/10-ssl.conf
##
## SSL settings
##

# SSL/TLS support: yes, no, required. <doc/wiki/SSL.txt>
# disable plain pop3 and imap, allowed are only pop3+TLS, pop3s, imap+TLS and imaps
# plain imap and pop3 are still allowed for local connections
#ssl = required
ssl = no
　：
[root@host1 dovecot]#
```

`doveconf` コマンドで設定値を確認する

```Shell
[root@host1 dovecot]#
[root@host1 dovecot]# doveconf -n
# 2.3.16 (7e2e900c1a): /etc/dovecot/dovecot.conf
# OS: Linux 5.14.0-284.11.1.el9_2.x86_64 x86_64 AlmaLinux release 9.2 (Turquoise Kodkod)
# Hostname: host2
disable_plaintext_auth = no
first_valid_uid = 1000
mail_access_groups = mail
mail_location = mbox:~/mail:INBOX=/var/mail/%u
mail_privileged_group = mail
mbox_write_locks = fcntl
namespace inbox {
  inbox = yes
  location =
  mailbox Drafts {
    special_use = \Drafts
  }
  mailbox Junk {
    special_use = \Junk
  }
  mailbox Sent {
    special_use = \Sent
  }
  mailbox "Sent Messages" {
    special_use = \Sent
  }
  mailbox Trash {
    special_use = \Trash
  }
  prefix =
}
passdb {
  driver = pam
}
ssl = no
ssl_cert = </etc/pki/dovecot/certs/dovecot.pem
ssl_cipher_list = PROFILE=SYSTEM
ssl_key = # hidden, use -P to show it
userdb {
  driver = passwd
}
[root@host1 dovecot]#
```

### 5.7.3 ファイアウォールの設定

```Shell
[root@host1 dovecot]#
[root@host1 dovecot]# firewall-cmd --list-all
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3 enp0s8
  sources:
  services: cockpit dhcpv6-client dns smtp ssh
  ports:
  protocols:
  forward: yes
  masquerade: no
  forward-ports:
  source-ports:
  icmp-blocks:
  rich rules:
[root@host1 dovecot]#
[root@host1 dovecot]# firewall-cmd --add-service=pop3
success
[root@host1 dovecot]#
[root@host1 dovecot]# firewall-cmd --add-service=imap
success
[root@host1 dovecot]#
[root@host1 dovecot]# firewall-cmd --list-all
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3 enp0s8
  sources:
  services: cockpit dhcpv6-client dns imap pop3 smtp ssh
  ports:
  protocols:
  forward: yes
  masquerade: no
  forward-ports:
  source-ports:
  icmp-blocks:
  rich rules:
[root@host1 dovecot]#
[root@host1 dovecot]# firewall-cmd --runtime-to-permanent
success
[root@host1 dovecot]#
```

### 5.7.4 Dovecotの起動

```Shell
[root@host1 dovecot]#
[root@host1 dovecot]# systemctl status dovecot
○ dovecot.service - Dovecot IMAP/POP3 email server
     Loaded: loaded (/usr/lib/systemd/system/dovecot.service; disabled; preset: disabled)
     Active: inactive (dead)
       Docs: man:dovecot(1)
             https://doc.dovecot.org/
[root@host1 dovecot]#
[root@host1 dovecot]# systemctl start dovecot
[root@host1 dovecot]#
[root@host1 dovecot]# systemctl status dovecot
● dovecot.service - Dovecot IMAP/POP3 email server
     Loaded: loaded (/usr/lib/systemd/system/dovecot.service; disabled; preset: disabled)
     Active: active (running) since Tue 2023-09-19 17:11:59 JST; 3s ago
       Docs: man:dovecot(1)
             https://doc.dovecot.org/
    Process: 4061 ExecStartPre=/usr/libexec/dovecot/prestartscript (code=exited, status=0/SUCCESS)
   Main PID: 4067 (dovecot)
     Status: "v2.3.16 (7e2e900c1a) running"
      Tasks: 4 (limit: 10992)
     Memory: 5.1M
        CPU: 85ms
     CGroup: /system.slice/dovecot.service
             tq4067 /usr/sbin/dovecot -F
             tq4068 dovecot/anvil
             tq4069 dovecot/log
             mq4070 dovecot/config

 9月 19 17:11:59 host2 systemd[1]: Starting Dovecot IMAP/POP3 email server...
 9月 19 17:11:59 host2 dovecot[4067]: master: Dovecot v2.3.16 (7e2e900c1a) starting up for imap, pop3, lmtp (>
 9月 19 17:11:59 host2 systemd[1]: Started Dovecot IMAP/POP3 email server.
[root@host1 dovecot]#
[root@host1 dovecot]# ss -ant | grep :110
LISTEN 0      100           0.0.0.0:110       0.0.0.0:*
LISTEN 0      100              [::]:110          [::]:*
[root@host1 dovecot]#
[root@host1 dovecot]# ss -ant | grep :143
LISTEN 0      100           0.0.0.0:143       0.0.0.0:*
LISTEN 0      100              [::]:143          [::]:*
[root@host1 dovecot]#
[root@host1 dovecot]# netstat -ant | grep :110
tcp        0      0 0.0.0.0:110             0.0.0.0:*               LISTEN
tcp6       0      0 :::110                  :::*                    LISTEN
[root@host1 dovecot]#
[root@host1 dovecot]# netstat -ant | grep :143
tcp        0      0 0.0.0.0:143             0.0.0.0:*               LISTEN
tcp6       0      0 :::143                  :::*                    LISTEN
[root@host1 dovecot]#
[root@host1 dovecot]# systemctl is-enabled dovecot
disabled
[root@host1 dovecot]#
[root@host1 dovecot]# systemctl enable dovecot
Created symlink /etc/systemd/system/multi-user.target.wants/dovecot.service → /usr/lib/systemd/system/dovecot.service.
[root@host1 dovecot]#
[root@host1 dovecot]# systemctl is-enabled dovecot
enabled
[root@host1 dovecot]#
```


### 5.7.5 Thunderbirdのインストール

```Shell
[root@host1 ~]#
[root@host1 ~]# dnf search thunderbird
メタデータの期限切れの最終確認: 5 days, 1:16:19 前の 2023年09月14日 16時00分04秒 に実施しました。
======================================= 名前 & 概要 一致: thunderbird ========================================
thunderbird.x86_64 : Mozilla Thunderbird mail/newsgroup client
[root@host1 ~]#
[root@host1 ~]# dnf info thunderbird
AlmaLinux 9 - DVD Media BaseOS                                                3.8 MB/s | 3.9 kB     00:00
AlmaLinux 9 - DVD Media AppStream                                             4.2 MB/s | 4.3 kB     00:00
利用可能なパッケージ
名前         : thunderbird
バージョン   : 102.10.0
リリース     : 2.el9_1.alma
Arch         : x86_64
サイズ       : 102 M
ソース       : thunderbird-102.10.0-2.el9_1.alma.src.rpm
リポジトリー : media-AppStream
概要         : Mozilla Thunderbird mail/newsgroup client
URL          : http://www.mozilla.org/projects/thunderbird/
ライセンス   : MPLv1.1 or GPLv2+ or LGPLv2+
説明         : Mozilla Thunderbird is a standalone mail and newsgroup client.

[root@host1 ~]#
[root@host1 ~]# dnf install thunderbird
メタデータの期限切れの最終確認: 0:00:06 前の 2023年09月19日 17時16分29秒 に実施しました。
依存関係が解決しました。
==============================================================================================================
 パッケージ             アーキテクチャー  バージョン                         リポジトリー               サイズ
==============================================================================================================
インストール:
 thunderbird            x86_64            102.10.0-2.el9_1.alma              media-AppStream            102 M

トランザクションの概要
==============================================================================================================
インストール  1 パッケージ

合計サイズ: 102 M
インストール後のサイズ: 277 M
これでよろしいですか? [y/N]: y
パッケージのダウンロード:
トランザクションの確認を実行中
トランザクションの確認に成功しました。
トランザクションのテストを実行中
トランザクションのテストに成功しました。
トランザクションを実行中
  準備             :                                                                                      1/1
  インストール中   : thunderbird-102.10.0-2.el9_1.alma.x86_64                                             1/1
  scriptletの実行中: thunderbird-102.10.0-2.el9_1.alma.x86_64                                             1/1
  検証             : thunderbird-102.10.0-2.el9_1.alma.x86_64                                             1/1

インストール済み:
  thunderbird-102.10.0-2.el9_1.alma.x86_64

完了しました!
[root@host1 ~]#
[root@host1 ~]# rpm -q thunderbird
thunderbird-102.10.0-2.el9_1.alma.x86_64
[root@host1 ~]#
[root@host1 ~]# thunderbird --version
 Thunderbird 102.10.0
[root@host1 ~]#
```


### 5.7.6 Thunderbirdの起動

`host1.alpha.jp` に `usera` でログインして、画面左上「アクティビティ」をクリック
![image 001](/images/section5.7/section5.7-001.jpg)

画面下「アプリケーションを表示」をクリック
![image 002](/images/section5.7/section5.7-002.jpg)

「Thunderbird」をクリック
![image 003](/images/section5.7/section5.7-003.jpg)

UserAのアカウント情報を入力して「手動設定」をクリック
![image 004](/images/section5.7/section5.7-004.jpg)

受信サーバーの情報を入力し下にスクロールする
![image 005](/images/section5.7/section5.7-005.jpg)

送信サーバーの情報を入力し「完了」をクリック
![image 006](/images/section5.7/section5.7-006.jpg)

警告が表示されてしまうが「接続する上での危険性を理解しました」にチェックをいれて「確認」をクリック
![image 007](/images/section5.7/section5.7-007.jpg)

![image 008](/images/section5.7/section5.7-008.jpg)

「アカウントの作成が完了しました」と表示されればOKなので「完了」をクリックする 
同様の操作を `host2.beta.jp` の `userb` でも行う
![image 009](/images/section5.7/section5.7-009.jpg)

メールの画面が表示される
![image 010](/images/section5.7/section5.7-010.jpg)

`usera@alpha.jp` から `userb@beta.jp` にメールを送信する  
メールを送信するには「メール作成」をクリック  
宛先、件名、本文 を入力して「送信」をクリックすると送信される
![image 011](/images/section5.7/section5.7-011.jpg)

正常に送信されれば「送信済みトレイ」に入る
![image 012](/images/section5.7/section5.7-012.jpg)

※`userb@beta.jp` で操作  
`usera@alpha.jp` からのメールが受信できている
![image 013](/images/section5.7/section5.7-013.jpg)

![image 014](/images/section5.7/section5.7-014.jpg)

受信したメールを「返信」してみる
![image 015](/images/section5.7/section5.7-015.jpg)

![image 016](/images/section5.7/section5.7-016.jpg)

※`usera@alpha.jp` で操作  
`userb@beta.jp` からの返信メールが受信できている
![image 017](/images/section5.7/section5.7-017.jpg)


### おまけ

telnetコマンドでIMAPログインをする


```Shell
[root@host1 ~]#
[root@host1 ~]# dnf install telnet
メタデータの期限切れの最終確認: 0:38:56 前の 2023年09月20日 16時53分32秒 に実施しました。
依存関係が解決しました。
==============================================================================================================
 パッケージ           アーキテクチャー     バージョン                     リポジトリー                  サイズ
==============================================================================================================
インストール:
 telnet               x86_64               1:0.17-85.el9                  media-AppStream                63 k

トランザクションの概要
==============================================================================================================
インストール  1 パッケージ

合計サイズ: 63 k
インストール後のサイズ: 121 k
これでよろしいですか? [y/N]: y
パッケージのダウンロード:
トランザクションの確認を実行中
トランザクションの確認に成功しました。
トランザクションのテストを実行中
トランザクションのテストに成功しました。
トランザクションを実行中
  準備             :                                                                                      1/1
  インストール中   : telnet-1:0.17-85.el9.x86_64                                                          1/1
  scriptletの実行中: telnet-1:0.17-85.el9.x86_64                                                          1/1
  検証             : telnet-1:0.17-85.el9.x86_64                                                          1/1

インストール済み:
  telnet-1:0.17-85.el9.x86_64

完了しました!
[root@host1 ~]#
```


```Shell
[root@host1 ~]#
[root@host1 ~]# telnet localhost 143
Trying ::1...
Connected to localhost.
Escape character is '^]'.
* OK [CAPABILITY IMAP4rev1 SASL-IR LOGIN-REFERRALS ID ENABLE IDLE LITERAL+ AUTH=PLAIN] Dovecot ready.
a login usera password
a OK [CAPABILITY IMAP4rev1 SASL-IR LOGIN-REFERRALS ID ENABLE IDLE SORT SORT=DISPLAY THREAD=REFERENCES THREAD=REFS THREAD=ORDEREDSUBJECT MULTIAPPEND URL-PARTIAL CATENATE UNSELECT CHILDREN NAMESPACE UIDPLUS LIST-EXTENDED I18NLEVEL=1 CONDSTORE QRESYNC ESEARCH ESORT SEARCHRES WITHIN CONTEXT=SEARCH LIST-STATUS BINARY MOVE SNIPPET=FUZZY PREVIEW=FUZZY PREVIEW STATUS=SIZE SAVEDATE LITERAL+ NOTIFY SPECIAL-USE] Logged in
b select INBOX
* FLAGS (\Answered \Flagged \Deleted \Seen \Draft)
* OK [PERMANENTFLAGS (\Answered \Flagged \Deleted \Seen \Draft \*)] Flags permitted.
* 0 EXISTS
* 0 RECENT
* OK [UIDVALIDITY 1695197428] UIDs valid
* OK [UIDNEXT 1] Predicted next UID
b OK [READ-WRITE] Select completed (0.001 + 0.000 secs).
c close INBOX
c OK Close completed (0.001 + 0.000 secs).
logout
logout BAD Error in IMAP command: Invalid command name (0.001 + 0.000 secs).
d logout
* BYE Logging out
d OK Logout completed (0.001 + 0.000 secs).
Connection closed by foreign host.
[root@host1 ~]#
```
