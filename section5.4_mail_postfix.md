# 第5章 メールサーバー構築

現行テキスト(v3.0.2)からの差分：
- `postfix` がデフォルトでインストールされていない → `postfix` パッケージをインストールする
- `postfix` がデフォルトではサービス無効になっている
- `saslauthd` がデフォルトでインストールされていない → `cyrus-sasl` パッケージをインストールする
- `mail` コマンドがインストールされていない → `s-nail` パッケージをインストールする


## 5.4 Postfixのインストール

```Shell
[root@host1 ~]#
[root@host1 ~]# rpm -q postfix
パッケージ postfix はインストールされていません。
[root@host1 ~]#
[root@host1 ~]# dnf search postfix
メタデータの期限切れの最終確認: 2:17:32 前の 2023年09月14日 13時34分04秒 に実施しました。
========================================= 名前 & 概要 一致: postfix ==========================================
postfix.x86_64 : Postfix Mail Transport Agent
pcp-pmda-postfix.x86_64 : Performance Co-Pilot (PCP) metrics for the Postfix (MTA)
postfix-cdb.x86_64 : Postfix CDB map support
postfix-ldap.x86_64 : Postfix LDAP map support
postfix-mysql.x86_64 : Postfix MySQL map support
postfix-pcre.x86_64 : Postfix PCRE map support
postfix-perl-scripts.x86_64 : Postfix utilities written in perl
postfix-pgsql.x86_64 : Postfix PostgreSQL map support
postfix-sqlite.x86_64 : Postfix SQLite map support
[root@host1 ~]#
[root@host1 ~]# dnf info postfix
メタデータの期限切れの最終確認: 2:18:57 前の 2023年09月14日 13時34分04秒 に実施しました。
利用可能なパッケージ
名前         : postfix
エポック     : 2
バージョン   : 3.5.9
リリース     : 19.el9
Arch         : x86_64
サイズ       : 1.4 M
ソース       : postfix-3.5.9-19.el9.src.rpm
リポジトリー : media-AppStream
概要         : Postfix Mail Transport Agent
URL          : http://www.postfix.org
ライセンス   : (IBM and GPLv2+) or (EPL-2.0 and GPLv2+)
説明         : Postfix is a Mail Transport Agent (MTA).

[root@host1 ~]#
```


```Shell
[root@host1 ~]#
[root@host1 ~]# rpm -q cyrus-sasl
パッケージ cyrus-sasl はインストールされていません。
[root@host1 ~]#
[root@host1 ~]# dnf search cyrus-sasl
メタデータの期限切れの最終確認: 3:37:36 前の 2023年09月14日 13時34分04秒 に実施しました。
========================================= 名前 完全一致: cyrus-sasl ==========================================
cyrus-sasl.x86_64 : The Cyrus SASL library
cyrus-sasl.i686 : The Cyrus SASL library
=========================================== 名前 一致: cyrus-sasl ============================================
cyrus-sasl-devel.i686 : Files needed for developing applications with Cyrus SASL
cyrus-sasl-devel.x86_64 : Files needed for developing applications with Cyrus SASL
cyrus-sasl-gs2.i686 : GS2 support for Cyrus SASL
cyrus-sasl-gs2.x86_64 : GS2 support for Cyrus SASL
cyrus-sasl-gssapi.x86_64 : GSSAPI authentication support for Cyrus SASL
cyrus-sasl-gssapi.i686 : GSSAPI authentication support for Cyrus SASL
cyrus-sasl-ldap.i686 : LDAP auxprop support for Cyrus SASL
cyrus-sasl-ldap.x86_64 : LDAP auxprop support for Cyrus SASL
cyrus-sasl-lib.x86_64 : Shared libraries needed by applications which use Cyrus SASL
cyrus-sasl-lib.i686 : Shared libraries needed by applications which use Cyrus SASL
cyrus-sasl-md5.i686 : CRAM-MD5 and DIGEST-MD5 authentication support for Cyrus SASL
cyrus-sasl-md5.x86_64 : CRAM-MD5 and DIGEST-MD5 authentication support for Cyrus SASL
cyrus-sasl-ntlm.i686 : NTLM authentication support for Cyrus SASL
cyrus-sasl-ntlm.x86_64 : NTLM authentication support for Cyrus SASL
cyrus-sasl-plain.x86_64 : PLAIN and LOGIN authentication support for Cyrus SASL
cyrus-sasl-plain.i686 : PLAIN and LOGIN authentication support for Cyrus SASL
cyrus-sasl-scram.i686 : SCRAM auxprop support for Cyrus SASL
cyrus-sasl-scram.x86_64 : SCRAM auxprop support for Cyrus SASL
cyrus-sasl-sql.i686 : SQL auxprop support for Cyrus SASL
cyrus-sasl-sql.x86_64 : SQL auxprop support for Cyrus SASL
[root@host1 ~]#
[root@host1 ~]# dnf info cyrus-sasl
メタデータの期限切れの最終確認: 3:39:08 前の 2023年09月14日 13時34分04秒 に実施しました。
利用可能なパッケージ
名前         : cyrus-sasl
バージョン   : 2.1.27
リリース     : 21.el9
Arch         : i686
サイズ       : 74 k
ソース       : cyrus-sasl-2.1.27-21.el9.src.rpm
リポジトリー : media-AppStream
概要         : The Cyrus SASL library
URL          : https://www.cyrusimap.org/sasl/
ライセンス   : BSD with advertising
説明         : The cyrus-sasl package contains the Cyrus implementation of SASL.
             : SASL is the Simple Authentication and Security Layer, a method for
             : adding authentication support to connection-based protocols.

名前         : cyrus-sasl
バージョン   : 2.1.27
リリース     : 21.el9
Arch         : x86_64
サイズ       : 71 k
ソース       : cyrus-sasl-2.1.27-21.el9.src.rpm
リポジトリー : media-BaseOS
概要         : The Cyrus SASL library
URL          : https://www.cyrusimap.org/sasl/
ライセンス   : BSD with advertising
説明         : The cyrus-sasl package contains the Cyrus implementation of SASL.
             : SASL is the Simple Authentication and Security Layer, a method for
             : adding authentication support to connection-based protocols.

[root@host1 ~]#
```


`mail` コマンドを実行してみるとインストールされていないので `s-nail` インストールするか聞かれる。  
`y` とすればインストールできるが、リポジトリがDVDメディアのみの場合はエラーになってしまうので `dnf` コマンドでインストールする。  

```Shell
[root@host1 ~]#
[root@host1 ~]# mail
bash: mail: command not found...
Install package 's-nail' to provide command 'mail'? [N/y] y

 * Waiting in queue...
 * Loading list of packages.... Failed to install packages: Failed to find s-nail;14.9.22-6.el9;x86_64;appstream

[root@host1 ~]#
[root@host1 ~]# which mail
/usr/bin/which: no mail in (/root/.local/bin:/root/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin)
[root@host1 ~]#
[root@host1 ~]# dnf search s-nail
メタデータの期限切れの最終確認: 2:18:21 前の 2023年09月14日 13時34分04秒 に実施しました。
=========================================== 名前 完全一致: s-nail ============================================
s-nail.x86_64 : Environment for sending and receiving mail
[root@host1 ~]#
[root@host1 ~]# dnf info s-nail
メタデータの期限切れの最終確認: 2:18:30 前の 2023年09月14日 13時34分04秒 に実施しました。
利用可能なパッケージ
名前         : s-nail
バージョン   : 14.9.22
リリース     : 6.el9
Arch         : x86_64
サイズ       : 621 k
ソース       : s-nail-14.9.22-6.el9.src.rpm
リポジトリー : media-AppStream
概要         : Environment for sending and receiving mail
URL          : https://www.sdaoden.eu/code.html#s-nail
ライセンス   : ISC and BSD with advertising and BSD
説明         : S-nail provides a simple and friendly environment for sending
             : and receiving mail. It is intended to provide the functionality
             : of the POSIX mailx(1) command, but is MIME capable and optionally offers
             : extensions for line editing, S/MIME, SMTP and POP3, among others.
             : S-nail divides incoming mail into its constituent messages and allows
             : the user to deal with them in any order. It offers many commands
             : and internal variables for manipulating messages and sending mail.
             : It provides the user simple editing capabilities to ease the composition
             : of outgoing messages, and increasingly powerful and reliable
             : non-interactive scripting capabilities.

[root@host1 ~]#
```


### 5.4.1 必要なパッケージをインストール

`postfix` をインストールする。

```Shell
[root@host1 ~]#
[root@host1 ~]# dnf install postfix
メタデータの期限切れの最終確認: 0:04:52 前の 2023年09月14日 16時00分04秒 に実施しました。
依存関係が解決しました。
==============================================================================================================
 パッケージ            アーキテクチャー     バージョン                    リポジトリー                  サイズ
==============================================================================================================
インストール:
 postfix               x86_64               2:3.5.9-19.el9                media-AppStream               1.4 M

トランザクションの概要
==============================================================================================================
インストール  1 パッケージ

合計サイズ: 1.4 M
インストール後のサイズ: 4.4 M
これでよろしいですか? [y/N]: y
パッケージのダウンロード:
トランザクションの確認を実行中
トランザクションの確認に成功しました。
トランザクションのテストを実行中
トランザクションのテストに成功しました。
トランザクションを実行中
  準備             :                                                                                      1/1
  scriptletの実行中: postfix-2:3.5.9-19.el9.x86_64                                                        1/1
  インストール中   : postfix-2:3.5.9-19.el9.x86_64                                                        1/1
  scriptletの実行中: postfix-2:3.5.9-19.el9.x86_64                                                        1/1
  検証             : postfix-2:3.5.9-19.el9.x86_64                                                        1/1

インストール済み:
  postfix-2:3.5.9-19.el9.x86_64

完了しました!
[root@host1 ~]#
[root@host1 ~]# rpm -q postfix
postfix-3.5.9-19.el9.x86_64
[root@host1 ~]#
[root@host1 ~]# systemctl list-unit-files -t service | grep postfix
postfix.service                            disabled        disabled
[root@host1 ~]#
```

`saslauthd` を使えるようにするために `cyrus-sasl`  をインストールする。

```Shell
[root@host1 postfix]#
[root@host1 postfix]# dnf install cyrus-sasl
メタデータの期限切れの最終確認: 0:52:49 前の 2023年09月14日 16時00分04秒 に実施しました。
依存関係が解決しました。
==============================================================================================================
 パッケージ               アーキテクチャー     バージョン                    リポジトリー               サイズ
==============================================================================================================
インストール:
 cyrus-sasl               x86_64               2.1.27-21.el9                 media-BaseOS                71 k

トランザクションの概要
==============================================================================================================
インストール  1 パッケージ

合計サイズ: 71 k
インストール後のサイズ: 143 k
これでよろしいですか? [y/N]: y
パッケージのダウンロード:
トランザクションの確認を実行中
トランザクションの確認に成功しました。
トランザクションのテストを実行中
トランザクションのテストに成功しました。
トランザクションを実行中
  準備             :                                                                                      1/1
  scriptletの実行中: cyrus-sasl-2.1.27-21.el9.x86_64                                                      1/1
  インストール中   : cyrus-sasl-2.1.27-21.el9.x86_64                                                      1/1
  scriptletの実行中: cyrus-sasl-2.1.27-21.el9.x86_64                                                      1/1
  検証             : cyrus-sasl-2.1.27-21.el9.x86_64                                                      1/1

インストール済み:
  cyrus-sasl-2.1.27-21.el9.x86_64

完了しました!
[root@host1 postfix]#
[root@host1 postfix]# rpm -q cyrus-sasl
cyrus-sasl-2.1.27-21.el9.x86_64
[root@host1 postfix]#
[root@host1 postfix]# systemctl list-unit-files -t service | grep sasl
saslauthd.service                          disabled        disabled
[root@host1 postfix]#
```

`mail` コマンドが使えるようにするために `s-nail` をインストールする

```Shell
[root@host1 ~]#
[root@host1 ~]# dnf install s-nail
メタデータの期限切れの最終確認: 0:16:06 前の 2023年09月14日 16時00分04秒 に実施しました。
依存関係が解決しました。
==============================================================================================================
 パッケージ           アーキテクチャー     バージョン                     リポジトリー                  サイズ
==============================================================================================================
インストール:
 s-nail               x86_64               14.9.22-6.el9                  media-AppStream               621 k

トランザクションの概要
==============================================================================================================
インストール  1 パッケージ

合計サイズ: 621 k
インストール後のサイズ: 1.1 M
これでよろしいですか? [y/N]: y
パッケージのダウンロード:
トランザクションの確認を実行中
トランザクションの確認に成功しました。
トランザクションのテストを実行中
トランザクションのテストに成功しました。
トランザクションを実行中
  準備             :                                                                                      1/1
  scriptletの実行中: s-nail-14.9.22-6.el9.x86_64                                                          1/1
  インストール中   : s-nail-14.9.22-6.el9.x86_64                                                          1/1
  scriptletの実行中: s-nail-14.9.22-6.el9.x86_64                                                          1/1
  検証             : s-nail-14.9.22-6.el9.x86_64                                                          1/1

インストール済み:
  s-nail-14.9.22-6.el9.x86_64

完了しました!
[root@host1 ~]#
[root@host1 ~]# rpm -q s-nail
s-nail-14.9.22-6.el9.x86_64
[root@host1 ~]#
[root@host1 ~]# mail --version
s-nail v14.9.22, 2021-02-24 (built for Linux)
[root@host1 ~]#
[root@host1 ~]# mail --help
mail (s-nail v14.9.22): send and receive Internet mail

Send-only mode: send mail "to-addr"(ess) receiver(s):
  mail [-DdEFinv~#] [-: spec] [-A account] [:-C "field: body":]
       [:-a attachment:] [:-b bcc-addr:] [:-c cc-addr:]
       [-M type | -m file | -q file | -t] [-r from-addr] [:-S var[=value]:]
       [-s subject] [-T "arget: addr"] [:-X/Y cmd:] [-.] :to-addr:

"Receive" mode, starting on [-u user], primary *inbox* or [$MAIL]:
  mail [-DdEeHiNnRv~#] [-: spec] [-A account] [:-C "field: body":]
       [-L spec] [-r from-addr] [:-S var[=value]:] [-u user] [:-X/Y cmd:]

"Receive" mode, starting on -f (secondary $MBOX or [file]):
  mail [-DdEeHiNnRv~#] [-: spec] [-A account] [:-C "field: body":] -f
       [-L spec] [-r from-addr] [:-S var[=value]:] [:-X/Y cmd:] [file]

. -d sandbox, -:/ no .rc files, -. end options and force send-mode
. -a attachment[=input-charset[#output-charset]]
. -b, -c, -r, -T, to-addr: ex@am.ple or '(Lovely) Ex <am@p.le>'
. -M, -m, -q, -t: special input (-t: template message on stdin)
. -e only mail check, -H header summary; both: message specification via -L
. -S (un)sets variable, -X/-Y execute commands pre/post startup, -#: batch mode
. Features via "$ mail -Xversion -Xx"; there is --long-help
. Bugs/Contact via "$ mail -Sexpandaddr=shquote '\$contact-mail'"
[root@host1 ~]#
```

(補足)  
`mail` コマンドの実態は `s-nail` コマンドです。

```Shell
[root@host1 ~]# which mail
/usr/bin/mail
[root@host1 ~]#
[root@host1 ~]# ls -l /usr/bin/mail
lrwxrwxrwx. 1 root root 22  9月 14 16:16 /usr/bin/mail -> /etc/alternatives/mail
[root@host1 ~]#
[root@host1 ~]# ls -l /etc/alternatives/mail
lrwxrwxrwx. 1 root root 21  9月 14 16:16 /etc/alternatives/mail -> /usr/bin/mailx.s-nail
[root@host1 ~]#
[root@host1 ~]# ls -l /usr/bin/mailx.s-nail
lrwxrwxrwx. 1 root root 15  2月 12  2022 /usr/bin/mailx.s-nail -> /usr/bin/s-nail
[root@host1 ~]#
[root@host1 ~]# ls -l /usr/bin/s-nail
-rwxr-xr-x. 1 root root 1038824  2月 12  2022 /usr/bin/s-nail
[root@host1 ~]#
```



### 5.4.2 main.cfの設定

設定ファイルは `/etc/postfix` ディレクトリにある。  

```Shell
[root@host1 ~]#
[root@host1 ~]# cd /etc/postfix/
[root@host1 postfix]#
[root@host1 postfix]# pwd
/etc/postfix
[root@host1 postfix]#
[root@host1 postfix]# ls -la
合計 236
drwxr-xr-x.   4 root root  4096  9月 14 16:05 .
drwxr-xr-x. 139 root root  8192  9月 14 16:16 ..
-rw-r--r--.   1 root root 21111  9月  8  2019 access
-rw-r--r--.   1 root root 13194  6月  4  2018 canonical
-rw-r--r--.   1 root root    60 11月 16  2022 dynamicmaps.cf
drwxr-xr-x.   2 root root     6 11月 16  2022 dynamicmaps.cf.d
-rw-r--r--.   1 root root 10221  9月 17  2016 generic
-rw-r--r--.   1 root root 23802 10月  9  2016 header_checks
-rw-r--r--.   1 root root 29369 11月 16  2022 main.cf
-rw-r--r--.   1 root root 29130 11月 16  2022 main.cf.proto
-rw-r--r--.   1 root root  6372 11月 16  2022 master.cf
-rw-r--r--.   1 root root  6372 11月 16  2022 master.cf.proto
-rw-r--r--.   1 root root 20163 11月 16  2022 postfix-files
drwxr-xr-x.   2 root root     6 11月 16  2022 postfix-files.d
-rw-r--r--.   1 root root  6929  2月 14  2016 relocated
-rw-r--r--.   1 root root 13436  1月 11  2020 transport
-rw-r--r--.   1 root root 13963  6月  4  2018 virtual
[root@host1 postfix]#
[root@host1 postfix]# postconf -n
alias_database = hash:/etc/aliases
alias_maps = hash:/etc/aliases
command_directory = /usr/sbin
compatibility_level = 2
daemon_directory = /usr/libexec/postfix
data_directory = /var/lib/postfix
debug_peer_level = 2
debugger_command = PATH=/bin:/usr/bin:/usr/local/bin:/usr/X11R6/bin ddd $daemon_directory/$process_name $process_id & sleep 5
html_directory = no
inet_interfaces = localhost
inet_protocols = all
mail_owner = postfix
mailq_path = /usr/bin/mailq.postfix
manpage_directory = /usr/share/man
meta_directory = /etc/postfix
mydestination = $myhostname, localhost.$mydomain, localhost
newaliases_path = /usr/bin/newaliases.postfix
queue_directory = /var/spool/postfix
readme_directory = /usr/share/doc/postfix/README_FILES
sample_directory = /usr/share/doc/postfix/samples
sendmail_path = /usr/sbin/sendmail.postfix
setgid_group = postdrop
shlib_directory = /usr/lib64/postfix
smtp_tls_CAfile = /etc/pki/tls/certs/ca-bundle.crt
smtp_tls_CApath = /etc/pki/tls/certs
smtp_tls_security_level = may
smtpd_tls_cert_file = /etc/pki/tls/certs/postfix.pem
smtpd_tls_key_file = /etc/pki/tls/private/postfix.key
smtpd_tls_security_level = may
unknown_local_recipient_reject_code = 550
[root@host1 postfix]#
```

設定ファイルをバックアップしておく。

```Shell
[root@host1 postfix]#
[root@host1 postfix]# cp -p main.cf maincf.orig
[root@host1 postfix]#
[root@host1 postfix]# ls -l main.cf*
-rw-r--r--. 1 root root 29369 11月 16  2022 main.cf
-rw-r--r--. 1 root root 29369 11月 16  2022 main.cf.orig
-rw-r--r--. 1 root root 29130 11月 16  2022 main.cf.proto
[root@host1 postfix]#
```

```Shell
[root@host1 postfix]#
[root@host1 postfix]# vi main.cf
　：
#
#myhostname = host.domain.tld
#myhostname = virtual.domain.tld
myhostname = mail.alpha.jp  <---★ 追記
　：
#
#mydomain = domain.tld
mydomain = alpha.jp  <---★ 追記
　：
#
#inet_interfaces = all
#inet_interfaces = $myhostname
#inet_interfaces = $myhostname, localhost
inet_interfaces = localhost, 192.168.1.101  <---★ IPアドレスを追記
　：
#
#mydestination = $myhostname, localhost.$mydomain, localhost  <---★ コメントアウト
#mydestination = $myhostname, localhost.$mydomain, localhost, $mydomain
#mydestination = $myhostname, localhost.$mydomain, localhost, $mydomain,
#       mail.$mydomain, www.$mydomain, ftp.$mydomain
mydestination = alpha.jp  <---★ 追記
　：
#
#mynetworks = 168.100.189.0/28, 127.0.0.0/8
#mynetworks = $config_directory/mynetworks
#mynetworks = hash:/etc/postfix/network_table
mynetworks = 192.168.1.101  <---★ 追記
　：
# smtp auth
smtpd_sasl_auth_enable = yes  <---★ 追記
smtpd_recipient_restrictions = permit_mynetworks, permit_sasl_authenticated, reject_unauth_destination  <---★ 追記
　：

[root@host1 postfix]#
```

### 5.4.3 書式のチェック


```Shell
[root@host1 postfix]#
[root@host1 postfix]# postfix check
[root@host1 postfix]#
[root@host1 postfix]# postconf -n
alias_database = hash:/etc/aliases
alias_maps = hash:/etc/aliases
command_directory = /usr/sbin
compatibility_level = 2
daemon_directory = /usr/libexec/postfix
data_directory = /var/lib/postfix
debug_peer_level = 2
debugger_command = PATH=/bin:/usr/bin:/usr/local/bin:/usr/X11R6/bin ddd $daemon_directory/$process_name $process_id & sleep 5
html_directory = no
inet_interfaces = localhost, 192.168.1.101   <---★
inet_protocols = all
mail_owner = postfix
mailq_path = /usr/bin/mailq.postfix
manpage_directory = /usr/share/man
meta_directory = /etc/postfix
mydestination = alpha.jp   <---★
mydomain = alpha.jp   <---★
myhostname = mail.alpha.jp   <---★
mynetworks = 192.168.1.101   <---★
newaliases_path = /usr/bin/newaliases.postfix
queue_directory = /var/spool/postfix
readme_directory = /usr/share/doc/postfix/README_FILES
sample_directory = /usr/share/doc/postfix/samples
sendmail_path = /usr/sbin/sendmail.postfix
setgid_group = postdrop
shlib_directory = /usr/lib64/postfix
smtp_tls_CAfile = /etc/pki/tls/certs/ca-bundle.crt
smtp_tls_CApath = /etc/pki/tls/certs
smtp_tls_security_level = may
smtpd_recipient_restrictions = permit_mynetworks, permit_sasl_authenticated, reject_unauth_destination   <---★
smtpd_sasl_auth_enable = yes   <---★
smtpd_tls_cert_file = /etc/pki/tls/certs/postfix.pem
smtpd_tls_key_file = /etc/pki/tls/private/postfix.key
smtpd_tls_security_level = may
unknown_local_recipient_reject_code = 550
[root@host1 postfix]#
```

### 5.4.4 ファイアウォールの設定

```Shell
[root@host1 postfix]#
[root@host1 postfix]# firewall-cmd --list-all
public (active)
  target: default
  icmp-block-inversion: no
  interfaces: enp0s3 enp0s8
  sources:
  services: cockpit dhcpv6-client dns ssh
  ports:
  protocols:
  forward: yes
  masquerade: no
  forward-ports:
  source-ports:
  icmp-blocks:
  rich rules:
[root@host1 postfix]#
[root@host1 postfix]# firewall-cmd --add-service=smtp
success
[root@host1 postfix]#
[root@host1 postfix]# firewall-cmd --list-all
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
[root@host1 postfix]#
[root@host1 postfix]#
[root@host1 postfix]# firewall-cmd --runtime-to-permanent
success
[root@host1 postfix]#
```

### 5.4.5 Postfixの起動

```Shell
[root@host1 postfix]#
[root@host1 postfix]# systemctl status postfix
○ postfix.service - Postfix Mail Transport Agent
     Loaded: loaded (/usr/lib/systemd/system/postfix.service; disabled; preset: disabled)
     Active: inactive (dead)
[root@host1 postfix]#
[root@host1 postfix]# systemctl start postfix
[root@host1 postfix]#
[root@host1 postfix]# systemctl status postfix
● postfix.service - Postfix Mail Transport Agent
     Loaded: loaded (/usr/lib/systemd/system/postfix.service; disabled; preset: disabled)
     Active: active (running) since Thu 2023-09-14 16:48:05 JST; 1s ago
    Process: 5090 ExecStartPre=/usr/sbin/restorecon -R /var/spool/postfix/pid/master.pid (code=exited, status>
    Process: 5091 ExecStartPre=/usr/libexec/postfix/aliasesdb (code=exited, status=0/SUCCESS)
    Process: 5095 ExecStartPre=/usr/libexec/postfix/chroot-update (code=exited, status=0/SUCCESS)
    Process: 5096 ExecStart=/usr/sbin/postfix start (code=exited, status=0/SUCCESS)
   Main PID: 5164 (master)
      Tasks: 3 (limit: 10992)
     Memory: 4.9M
        CPU: 405ms
     CGroup: /system.slice/postfix.service
             tq5164 /usr/libexec/postfix/master -w
             tq5165 pickup -l -t unix -u
             mq5166 qmgr -l -t unix -u

 9月 14 16:48:05 host1.alpha.jp systemd[1]: Starting Postfix Mail Transport Agent...
 9月 14 16:48:05 host1.alpha.jp restorecon[5090]: /usr/sbin/restorecon: lstat(/var/spool/postfix/pid/master.p>
 9月 14 16:48:05 host1.alpha.jp postfix/postfix-script[5162]: starting the Postfix mail system
 9月 14 16:48:05 host1.alpha.jp postfix/master[5164]: daemon started -- version 3.5.9, configuration /etc/pos>
 9月 14 16:48:05 host1.alpha.jp systemd[1]: Started Postfix Mail Transport Agent.
[root@host1 postfix]#
[root@host1 postfix]#
[root@host1 postfix]# ss -ant | grep :25
LISTEN 0      100     192.168.1.101:25        0.0.0.0:*
LISTEN 0      100         127.0.0.1:25        0.0.0.0:*
LISTEN 0      100             [::1]:25           [::]:*
[root@host1 postfix]#
[root@host1 postfix]# netstat -ant | grep :25
tcp        0      0 192.168.1.101:25        0.0.0.0:*               LISTEN
tcp        0      0 127.0.0.1:25            0.0.0.0:*               LISTEN
tcp6       0      0 ::1:25                  :::*                    LISTEN
[root@host1 postfix]#
[root@host1 postfix]#
[root@host1 postfix]# systemctl is-enabled postfix
disabled
[root@host1 postfix]#
[root@host1 postfix]# systemctl enable postfix
Created symlink /etc/systemd/system/multi-user.target.wants/postfix.service → /usr/lib/systemd/system/postfix.service.
[root@host1 postfix]#
[root@host1 postfix]# systemctl is-enabled postfix
enabled
[root@host1 postfix]#
```

# 5.4.6 saslauthdサービスの起動

```Shell
[root@host1 postfix]# 
[root@host1 postfix]# systemctl status saslauthd
○ saslauthd.service - SASL authentication daemon.
     Loaded: loaded (/usr/lib/systemd/system/saslauthd.service; disabled; preset: disabled)
     Active: inactive (dead)
[root@host1 postfix]#
[root@host1 postfix]# systemctl start saslauthd
[root@host1 postfix]#
[root@host1 postfix]# systemctl status saslauthd
● saslauthd.service - SASL authentication daemon.
     Loaded: loaded (/usr/lib/systemd/system/saslauthd.service; disabled; preset: disabled)
     Active: active (running) since Thu 2023-09-14 16:54:18 JST; 3s ago
    Process: 5359 ExecStart=/usr/sbin/saslauthd -m $SOCKETDIR -a $MECH $FLAGS (code=exited, status=0/SUCCESS)
   Main PID: 5360 (saslauthd)
      Tasks: 5 (limit: 10992)
     Memory: 1.6M
        CPU: 6ms
     CGroup: /system.slice/saslauthd.service
             tq5360 /usr/sbin/saslauthd -m /run/saslauthd -a pam
             tq5361 /usr/sbin/saslauthd -m /run/saslauthd -a pam
             tq5362 /usr/sbin/saslauthd -m /run/saslauthd -a pam
             tq5363 /usr/sbin/saslauthd -m /run/saslauthd -a pam
             mq5364 /usr/sbin/saslauthd -m /run/saslauthd -a pam

 9月 14 16:54:18 host1.alpha.jp systemd[1]: Starting SASL authentication daemon....
 9月 14 16:54:18 host1.alpha.jp saslauthd[5360]:                 : master pid is: 5360
 9月 14 16:54:18 host1.alpha.jp saslauthd[5360]:                 : listening on socket: /run/saslauthd/mux
 9月 14 16:54:18 host1.alpha.jp systemd[1]: Started SASL authentication daemon..
[root@host1 postfix]#
[root@host1 postfix]#
[root@host1 postfix]# systemctl is-enabled saslauthd
disable
[root@host1 postfix]#
[root@host1 postfix]# systemctl enable saslauthd
Created symlink /etc/systemd/system/multi-user.target.wants/saslauthd.service → /usr/lib/systemd/system/saslauthd.service.
[root@host1 postfix]#
[root@host1 postfix]# systemctl is-enabled saslauthd
enabled
[root@host1 postfix]#
```