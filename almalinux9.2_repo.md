# リポジトリ

## リポジトリファイル

```Shell
[root@host0 ~]#
[root@host0 ~]# cd /etc/yum.repos.d/
[root@host0 yum.repos.d]#
[root@host0 yum.repos.d]# ls -la
合計 60
drwxr-xr-x.   2 root root 4096  9月  8 11:13 .
drwxr-xr-x. 137 root root 8192  9月  8 15:25 ..
-rw-r--r--.   1 root root 1023  5月  9 23:23 almalinux-appstream.repo
-rw-r--r--.   1 root root  987  5月  9 23:23 almalinux-baseos.repo
-rw-r--r--.   1 root root  951  5月  9 23:23 almalinux-crb.repo
-rw-r--r--.   1 root root  987  5月  9 23:23 almalinux-extras.repo
-rw-r--r--.   1 root root 1107  5月  9 23:23 almalinux-highavailability.repo
-rw-r--r--.   1 root root  951  5月  9 23:23 almalinux-nfv.repo
-rw-r--r--.   1 root root  963  5月  9 23:23 almalinux-plus.repo
-rw-r--r--.   1 root root 1107  5月  9 23:23 almalinux-resilientstorage.repo
-rw-r--r--.   1 root root  939  5月  9 23:23 almalinux-rt.repo
-rw-r--r--.   1 root root  951  5月  9 23:23 almalinux-sap.repo
-rw-r--r--.   1 root root  999  5月  9 23:23 almalinux-saphana.repo
[root@host0 yum.repos.d]#
[root@host0 yum.repos.d]# dnf repolist
repo id                                       repo の名前
appstream                                     AlmaLinux 9 - AppStream
baseos                                        AlmaLinux 9 - BaseOS
extras                                        AlmaLinux 9 - Extras
[root@host0 yum.repos.d]#
```

## DVDメディアを使う場合

メディアのパスは `/run/media/[DVDをマウントしたユーザー]/AlmaLinux-9-2-x86_64-dvd` になる。  
また、インターネットのリポジトリを使用しない場合は `dnf config-manager --disable [repo id]` で無効化できる。

```Shell
[root@host0 ~]#
[root@host0 ~]# cd /etc/yum.repos.d/
[root@host0 yum.repos.d]#
[root@host0 yum.repos.d]# vi almalinux-media.repo
[media-BaseOS]
name=AlmaLinux $releasever - DVD Media BaseOS
baseurl='file:///run/media/root/AlmaLinux-9-2-x86_64-dvd/BaseOS'
enabled=1
gpgcheck=1
countme=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-AlmaLinux-9
metadata_expire=86400
enabled_metadata=1

[media-AppStream]
name=AlmaLinux $releasever - DVD Media AppStream
baseurl='file:///run/media/root/AlmaLinux-9-2-x86_64-dvd/AppStream'
enabled=1
gpgcheck=1
countme=1
gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-KEY-AlmaLinux-9
metadata_expire=86400
enabled_metadata=1
[root@host0 yum.repos.d]# dnf repolist
repo id                                       repo の名前
appstream                                     AlmaLinux 9 - AppStream
baseos                                        AlmaLinux 9 - BaseOS
extras                                        AlmaLinux 9 - Extras
media-AppStream                               AlmaLinux 9 - DVD Media AppStream
media-BaseOS                                  AlmaLinux 9 - DVD Media BaseOS
[root@host0 yum.repos.d]#
[root@host0 yum.repos.d]# dnf config-manager --disable appstream
[root@host0 yum.repos.d]# dnf config-manager --disable baseos
[root@host0 yum.repos.d]# dnf config-manager --disable extras
[root@host0 yum.repos.d]#
[root@host0 yum.repos.d]# dnf repolist
repo id                                       repo の名前
media-AppStream                               AlmaLinux 9 - DVD Media AppStream
media-BaseOS                                  AlmaLinux 9 - DVD Media BaseOS
[root@host0 yum.repos.d]#
[root@host0 yum.repos.d]#
```