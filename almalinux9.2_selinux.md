# SELinux

## OSインストール直後の状態

デフォルトで `Enforcing` になっている。

```Shell
[root@host1 ~]#
[root@host1 ~]# getenforce
Enforcing
[root@host1 ~]#
[root@host1 ~]# cat /etc/sysconfig/selinux

# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
# See also:
# https://docs.fedoraproject.org/en-US/quick-docs/getting-started-with-selinux/#getting-started-with-selinux-selinux-states-and-modes
#
# NOTE: In earlier Fedora kernel builds, SELINUX=disabled would also
# fully disable SELinux during boot. If you need a system with SELinux
# fully disabled instead of SELinux running with no policy loaded, you
# need to pass selinux=0 to the kernel command line. You can use grubby
# to persistently set the bootloader to boot with selinux=0:
#
#    grubby --update-kernel ALL --args selinux=0
#
# To revert back to SELinux enabled:
#
#    grubby --update-kernel ALL --remove-args selinux
#
SELINUX=enforcing
# SELINUXTYPE= can take one of these three values:
#     targeted - Targeted processes are protected,
#     minimum - Modification of targeted policy. Only selected processes are protected.
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted


[root@host1 ~]#
```

## 設定変更

コマンド操作で設定変更可能なので、設定ファイル(`/etc/sysconfig/selinux`)の編集は不要です。


[2.5. SELinux の無効化 Red Hat Enterprise Linux 9 | Red Hat Customer Portal](https://access.redhat.com/documentation/ja-jp/red_hat_enterprise_linux/9/html/using_selinux/enabling_and_disabling_selinux-disabling_selinux_changing-selinux-states-and-modes)


```Shell
[root@host1 ~]#
[root@host1 ~]# rpm -q grubby
grubby-8.40-63.el9.x86_64
[root@host1 ~]#
[root@host1 ~]# grubby --update-kernel ALL --args selinux=0
[root@host1 ~]#
[root@host1 ~]# reboot
[root@host1 ~]#
　：
再起動
　：
[root@host1 ~]#
[root@host1 ~]# getenforce
Disabled
[root@host1 ~]#
```
