# Firewalld

## OSインストール直後の状態

デフォルトで `enable` になっている。

```Shell
[root@host1 ~]#
[root@host1 ~]# systemctl list-unit-files -t service | grep firewalld
firewalld.service                          enabled         enabled
[root@host1 ~]#
[root@host1 ~]# systemctl status firewalld
● firewalld.service - firewalld - dynamic firewall daemon
     Loaded: loaded (/usr/lib/systemd/system/firewalld.service; enabled; preset: enabled)
     Active: active (running) since Fri 2023-09-08 11:57:51 JST; 11min ago
       Docs: man:firewalld(1)
   Main PID: 761 (firewalld)
      Tasks: 2 (limit: 10980)
     Memory: 42.7M
        CPU: 693ms
     CGroup: /system.slice/firewalld.service
             mq761 /usr/bin/python3 -s /usr/sbin/firewalld --nofork --nopid

 9月 08 11:57:50 host1.alpha.jp systemd[1]: Starting firewalld - dynamic firewall daemon...
 9月 08 11:57:51 host1.alpha.jp systemd[1]: Started firewalld - dynamic firewall daemon.
[root@host1 ~]#
[root@host1 ~]# systemctl is-enabled firewalld
enabled
[root@host1 ~]#
```

## 設定変更

`systemctl`コマンドで停止、無効化ができる。

firewalld 停止

```Shell
[root@host1 ~]#
[root@host1 ~]# systemctl stop firewalld
[root@host1 ~]#
[root@host1 ~]# systemctl status firewalld
○ firewalld.service - firewalld - dynamic firewall daemon
     Loaded: loaded (/usr/lib/systemd/system/firewalld.service; enabled; preset: enabled)
     Active: inactive (dead) since Fri 2023-09-08 12:11:18 JST; 3s ago
   Duration: 13min 27.312s
       Docs: man:firewalld(1)
    Process: 761 ExecStart=/usr/sbin/firewalld --nofork --nopid $FIREWALLD_ARGS (code=exited, status=0/SUCCES>
   Main PID: 761 (code=exited, status=0/SUCCESS)
        CPU: 765ms

 9月 08 11:57:50 host1.alpha.jp systemd[1]: Starting firewalld - dynamic firewall daemon...
 9月 08 11:57:51 host1.alpha.jp systemd[1]: Started firewalld - dynamic firewall daemon.
 9月 08 12:11:18 host1.alpha.jp systemd[1]: Stopping firewalld - dynamic firewall daemon...
 9月 08 12:11:18 host1.alpha.jp systemd[1]: firewalld.service: Deactivated successfully.
 9月 08 12:11:18 host1.alpha.jp systemd[1]: Stopped firewalld - dynamic firewall daemon.
[root@host1 ~]#
```

firewalld 無効化

```Shell
[root@host1 ~]#
[root@host1 ~]# systemctl disable firewalld
Removed "/etc/systemd/system/multi-user.target.wants/firewalld.service".
Removed "/etc/systemd/system/dbus-org.fedoraproject.FirewallD1.service".
[root@host1 ~]#
[root@host1 ~]# systemctl is-enabled firewalld
disabled
[root@host1 ~]#
```

firewalld 有効化

```Shell
[root@host1 ~]#
[root@host1 ~]# systemctl enable firewalld
Created symlink /etc/systemd/system/dbus-org.fedoraproject.FirewallD1.service → /usr/lib/systemd/system/firewalld.service.
Created symlink /etc/systemd/system/multi-user.target.wants/firewalld.service → /usr/lib/systemd/system/firewalld.service.
[root@host1 ~]#
[root@host1 ~]# systemctl is-enabled firewalld
enabled
[root@host1 ~]#
```
