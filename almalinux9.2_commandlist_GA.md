# AlmaLinux9.2 コマンド一覧

OSインストール直後、Guest Additions インストール後の状態

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

## コマンド一覧

```Shell
[root@host1 ~]#
[root@host1 ~]# echo $PATH
/root/.local/bin:/root/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin
[root@host1 ~]#
```

### /root/.local/bin

```Shell
[root@host1 ~]#
[root@host1 ~]# ls /root/.local/bin
ls: '/root/.local/bin' にアクセスできません: そのようなファイルやディレクトリはありません
[root@host1 ~]#
```

### /root/bin

```Shell
[root@host1 ~]#
[root@host1 ~]# ls /root/bin
ls: '/root/bin' にアクセスできません: そのようなファイルやディレクトリはありません
[root@host1 ~]#
```

### /usr/local/sbin/

```Shell
[root@host1 ~]#
[root@host1 ~]# ls /usr/local/sbin/
[root@host1 ~]#
```

### /usr/local/bin/

```Shell
[root@host1 ~]#
[root@host1 ~]# ls /usr/local/bin/
[root@host1 ~]#
```

### /usr/sbin/

```Shell
[root@host1 ~]#
[root@host1 ~]# ls /usr/sbin
ModemManager                           grub2-setpassword            pwhistory_helper
NetworkManager                         grub2-switch-to-blscfg       pwunconv
VBoxService                            grubby                       quotacheck
accessdb                               halt                         quotaoff
accton                                 hdparm                       quotaon
adcli                                  hwclock                      quotastats
addgnupghome                           hypervfcopyd                 raid-check
addpart                                hypervkvpd                   ras-mc-ctl
adduser                                hypervvssd                   rasdaemon
agetty                                 iconvconfig                  rcvboxadd
alsa-info.sh                           ifconfig                     rcvboxadd-service
alsactl                                ifenslave                    rdisc
alternatives                           ifstat                       rdma
anacron                                init                         readprofile
applygnupgdefaults                     insmod                       realm
arp                                    install-info                 reboot
arpd                                   installkernel                repquota
arping                                 intel_sdsi                   resize2fs
arptables                              ip                           resizepart
arptables-nft                          ip6tables                    restorecon
arptables-nft-restore                  ip6tables-nft                restorecon_xattr
arptables-nft-save                     ip6tables-nft-restore        rfkill
arptables-restore                      ip6tables-nft-save           rmmod
arptables-save                         ip6tables-restore            route
atd                                    ip6tables-restore-translate  rsyslogd
atrun                                  ip6tables-save               rtacct
auditctl                               ip6tables-translate          rtcwake
auditd                                 ipmaddr                      rtkitctl
augenrules                             iprconfig                    rtmon
aureport                               iprdbg                       rtstat
ausearch                               iprdump                      runlevel
autrace                                iprinit                      runuser
avahi-daemon                           iprsos                       sa
avcstat                                iprupdate                    sasldblistusers2
badblocks                              ipset                        saslpasswd2
biosdecode                             ipset-translate              sedispatch
blkdeactivate                          iptables                     sefcontext_compile
blkdiscard                             iptables-nft                 selabel_digest
blkid                                  iptables-nft-restore         selabel_get_digests_all_partial_matches
blkzone                                iptables-nft-save            selabel_lookup
blockdev                               iptables-restore             selabel_lookup_best_match
bpftool                                iptables-restore-translate   selabel_partial_match
bridge                                 iptables-save                selinux_check_access
cache_check                            iptables-translate           selinuxconlist
cache_dump                             iptunnel                     selinuxdefcon
cache_metadata_size                    irqbalance                   selinuxenabled
cache_repair                           irqbalance-ui                selinuxexeccon
cache_restore                          iscsi-iname                  semanage
cache_writeback                        iscsiadm                     semodule
capsh                                  iscsid                       service
cfdisk                                 iscsistart                   sestatus
cgdisk                                 iscsiuio                     setcap
chcpu                                  iw                           setenforce
chgpasswd                              kexec                        setfiles
chpasswd                               kpartx                       setpci
chronyd                                kpatch                       setquota
chroot                                 lchage                       setregdomain
clock                                  ldattach                     setroubleshootd
convertquota                           ldconfig                     setsebool
cracklib-check                         ledctl                       sfdisk
cracklib-format                        ledmon                       sgdisk
cracklib-packer                        lgroupadd                    shutdown
cracklib-unpacker                      lgroupdel                    skdump
create-cracklib-dict                   lgroupmod                    sktest
criu                                   lid                          slattach
crond                                  lnewusers                    smartctl
cryptsetup                             lnstat                       smartd
ctrlaltdel                             load_policy                  sos
ctstat                                 lockdev                      sos-collector
cups-browsed                           logrotate                    sosreport
cups-genppd.5.3                        logsave                      spice-vdagentd
cups-genppdupdate                      losetup                      ss
cupsaccept                             lpadmin                      sshd
cupsctl                                lpasswd                      sss_cache
cupsd                                  lpc                          sssd
cupsdisable                            lpc.cups                     sulogin
cupsenable                             lpinfo                       swaplabel
cupsfilter                             lpmove                       swapoff
cupsreject                             lshw                         swapon
dcb                                    lsmod                        switch_root
ddns-confgen                           lspci                        sysctl
debugfs                                luseradd                     tc
delpart                                luserdel                     tcpdump
depmod                                 lusermod                     tcpslice
devlink                                lvchange                     telinit
dmeventd                               lvconvert                    thin_check
dmfilemapd                             lvcreate                     thin_delta
dmidecode                              lvdisplay                    thin_dump
dmsetup                                lvextend                     thin_ls
dmstats                                lvm                          thin_metadata_pack
dnsmasq                                lvm_import_vdo               thin_metadata_size
dosfsck                                lvmconfig                    thin_metadata_unpack
dosfslabel                             lvmdevices                   thin_repair
dump-acct                              lvmdiskscan                  thin_restore
dump-utmp                              lvmdump                      thin_rmap
dumpe2fs                               lvmpolld                     thin_trim
e2freefrag                             lvmsadc                      tipc
e2fsck                                 lvmsar                       tracepath
e2image                                lvreduce                     tracepath6
e2label                                lvremove                     tsig-keygen
e2mmpstatus                            lvrename                     tune2fs
e2undo                                 lvresize                     tuned
e4crypt                                lvs                          tuned-adm
e4defrag                               lvscan                       udevadm
eapol_test                             makedumpfile                 umount.udisks2
ebtables                               matchpathcon                 unix_chkpwd
ebtables-nft                           mcelog                       unix_update
ebtables-nft-restore                   mdadm                        unsquashfs
ebtables-nft-save                      mdmon                        update-alternatives
ebtables-restore                       mii-diag                     update-pciids
ebtables-save                          mii-tool                     update-smart-drivedb
edquota                                mkdict                       usb_modeswitch
era_check                              mkdosfs                      usb_modeswitch_dispatcher
era_dump                               mkdumprd                     useradd
era_invalidate                         mke2fs                       userdel
era_restore                            mkfs                         usermod
ether-wake                             mkfs.cramfs                  validatetrans
ethtool                                mkfs.ext2                    vbox-greeter
faillock                               mkfs.ext3                    vbox-uninstall-guest-additions
fatlabel                               mkfs.ext4                    vdpa
fdformat                               mkfs.fat                     vgcfgbackup
fdisk                                  mkfs.minix                   vgcfgrestore
filefrag                               mkfs.msdos                   vgchange
findfs                                 mkfs.vfat                    vgck
firewalld                              mkfs.xfs                     vgconvert
fix-info-dir                           mkhomedir_helper             vgcreate
fixfiles                               mklost+found                 vgdisplay
fixparts                               mksquashfs                   vgexport
flashrom                               mkswap                       vgextend
foomatic-addpjloptions                 modinfo                      vgimport
foomatic-cleanupdrivers                modprobe                     vgimportclone
foomatic-extract-text                  mount.fuse                   vgimportdevices
foomatic-fix-xml                       mount.fuse3                  vgmerge
foomatic-getpjloptions                 mount.vboxsf                 vgmknodes
foomatic-kitload                       mpathconf                    vgreduce
foomatic-nonumericalids                mpathpersist                 vgremove
foomatic-preferred-driver              mtr                          vgrename
foomatic-printermap-to-gutenprint-xml  mtr-packet                   vgs
foomatic-replaceoldprinterids          multipath                    vgscan
fsadm                                  multipathd                   vgsplit
fsck                                   named-checkzone              vigr
fsck.cramfs                            named-compilezone            vipw
fsck.ext2                              named-nzd2nzf                virt-what
fsck.ext3                              nameif                       visudo
fsck.ext4                              newusers                     vmcore-dmesg
fsck.fat                               nft                          vpddecode
fsck.minix                             nologin                      weak-modules
fsck.msdos                             nsec3hash                    wipefs
fsck.vfat                              nstat                        wpa_cli
fsck.xfs                               nvme                         wpa_passphrase
fsfreeze                               ownership                    wpa_supplicant
fstrim                                 packer                       xfs_admin
fuser                                  pam_console_apply            xfs_bmap
g13-syshelp                            pam_namespace_helper         xfs_copy
gdisk                                  pam_timestamp_check          xfs_db
gdm                                    paperconfig                  xfs_estimate
genhomedircon                          parted                       xfs_freeze
genl                                   partprobe                    xfs_fsr
getcap                                 partx                        xfs_growfs
getenforce                             pdata_tools                  xfs_info
getpcaps                               pidof                        xfs_io
getpidprevcon                          ping                         xfs_logprint
getsebool                              ping6                        xfs_mdrestore
groupadd                               pivot_root                   xfs_metadump
groupdel                               plipconfig                   xfs_mkfile
groupmems                              plymouth-set-default-theme   xfs_ncheck
groupmod                               plymouthd                    xfs_quota
grpck                                  poweroff                     xfs_repair
grpconv                                pvchange                     xfs_rtcp
grpunconv                              pvck                         xfs_spaceman
grub2-bios-setup                       pvcreate                     xfsdump
grub2-get-kernel-settings              pvdisplay                    xfsinvutil
grub2-install                          pvmove                       xfsrestore
grub2-mkconfig                         pvremove                     xqmstats
grub2-probe                            pvresize                     xtables-monitor
grub2-reboot                           pvs                          xtables-nft-multi
grub2-set-bootflag                     pvscan                       zic
grub2-set-default                      pwck                         zramctl
grub2-set-password                     pwconv
[root@host1 ~]#
```

### /usr/bin

```Shell
[root@host1 ~]#
[root@host1 ~]# ls /usr/bin
 VBoxAudioTest                          gtk-query-immodules-2.0-64    sftp
 VBoxClient                             gtk-query-immodules-3.0-64    sg
 VBoxClient-all                         gtk-update-icon-cache         sg_bg_ctl
 VBoxControl                            gtk4-launch                   sg_compare_and_write
 VBoxDRMClient                          gtk4-update-icon-cache        sg_copy_results
 VGAuthService                          gtroff                        sg_dd
 WebKitWebDriver                        gunzip                        sg_decode_sense
 X                                      gv2gml                        sg_emc_trespass
 Xorg                                   gv2gxl                        sg_format
 Xwayland                               gvcolor                       sg_get_config
'['                                     gvgen                         sg_get_elem_status
 a2x                                    gvmap                         sg_get_lba_status
 a2x.py                                 gvmap.sh                      sg_ident
 ac                                     gvpack                        sg_inq
 aclocal                                gvpr                          sg_logs
 aclocal-1.16                           gxl2dot                       sg_luns
 aconnect                               gxl2gv                        sg_map
 acyclic                                gzexe                         sg_map26
 addr2line                              gzip                          sg_modes
 airscan-discover                       hardlink                      sg_opcodes
 alias                                  hash                          sg_persist
 alsaloop                               head                          sg_prevent
 alsamixer                              hex2hcd                       sg_raw
 alsaunmute                             hexdump                       sg_rbuf
 alt-java                               host                          sg_rdac
 amidi                                  hostid                        sg_read
 amixer                                 hostname                      sg_read_attr
 anthy-agent-unicode                    hostnamectl                   sg_read_block_limits
 anthy-dic-tool-unicode                 hunspell                      sg_read_buffer
 anthy-morphological-analyzer-unicode   i386                          sg_read_long
 aplay                                  ibus                          sg_readcap
 aplaymidi                              ibus-daemon                   sg_reassign
 appstream-compose                      ibus-setup                    sg_referrals
 appstream-util                         iconv                         sg_rep_pip
 appstreamcli                           id                            sg_rep_zones
 apropos                                idiag-socket-details          sg_requests
 apropos.man-db                         iecset                        sg_reset
 ar                                     ifnames                       sg_reset_wp
 arch                                   iio_event_monitor             sg_rmsn
 arecord                                iio_generic_buffer            sg_rtpg
 arecordmidi                            info                          sg_safte
 arpaname                               infocmp                       sg_sanitize
 arping                                 infotocap                     sg_sat_identify
 as                                     install                       sg_sat_phy_event
 asciidoc                               install-catalog               sg_sat_read_gplog
 asciidoc.py                            intel-speed-select            sg_sat_set_features
 aseqdump                               interdiff                     sg_scan
 aseqnet                                intltool-extract              sg_seek
 aserver                                intltool-merge                sg_senddiag
 at                                     intltool-prepare              sg_ses
 atq                                    intltool-update               sg_ses_microcode
 atrm                                   intltoolize                   sg_start
 attr                                   ionice                        sg_stpg
 audit2allow                            ipcmk                         sg_stream_ctl
 audit2why                              ipcrm                         sg_sync
 aulast                                 ipcs                          sg_test_rwbuf
 aulastlog                              ippfind                       sg_timestamp
 ausyscall                              ipptool                       sg_turs
 authselect                             iptc                          sg_unmap
 authvar                                irqtop                        sg_verify
 autoconf                               isdv4-serial-inputattach      sg_vpd
 autoheader                             iso-info                      sg_wr_mode
 autom4te                               iso-read                      sg_write_buffer
 automake                               isosize                       sg_write_long
 automake-1.16                          itstool                       sg_write_same
 autopoint                              java                          sg_write_verify
 autoreconf                             java2html                     sg_write_x
 autoscan                               jcat-tool                     sg_xcopy
 autoupdate                             jjs                           sg_zone
 auvirt                                 jobs                          sginfo
 avinfo                                 join                          sgm_dd
 awk                                    jose                          sgmlwhich
 axfer                                  journalctl                    sgp_dd
 b2sum                                  jq                            sh
 baobab                                 json_reformat                 sha1hmac
 base32                                 json_verify                   sha1sum
 base64                                 kasumi-unicode                sha224hmac
 basename                               kbd_mode                      sha224sum
 basenc                                 kbdinfo                       sha256hmac
 bash                                   kbdrate                       sha256sum
 bashbug                                kdumpctl                      sha384hmac
 bashbug-64                             kernel-install                sha384sum
 batch                                  keytool                       sha512hmac
 bc                                     kill                          sha512sum
 bcomps                                 killall                       showconsolefont
 bg                                     kmod                          showkey
 bison                                  kvm_stat                      shred
 blkiomon                               l2ping                        shuf
 blkparse                               l2test                        signver
 blkrawverify                           last                          sim_lsmplugin
 blktrace                               lastb                         simc_lsmplugin
 bluemoon                               lastcomm                      size
 bluetooth-sendto                       lastlog                       skill
 bluetoothctl                           lchfn                         slabinfo
 bno_plot.py                            lchsh                         slabtop
 boltctl                                ld                            sleep
 bond2team                              ld.bfd                        sliceprint
 bootctl                                ld.gold                       slirp4netns
 brltty                                 ld.so                         sndfile-resample
 brltty-atb                             ldd                           snice
 brltty-cldr                            lefty                         soelim
 brltty-clip                            less                          soelim.groff
 brltty-config.sh                       lessecho                      sort
 brltty-ctb                             lesskey                       sotruss
 brltty-genkey                          lesspipe.sh                   soundstretch
 brltty-ktb                             lex                           source-highlight
 brltty-lscmds                          lexgrog                       source-highlight-esc.sh
 brltty-lsinc                           libgtop_daemon2               source-highlight-settings
 brltty-mkuser                          libgtop_server2               spa-acp-tool
 brltty-morse                           libieee1284_test              spa-inspect
 brltty-prologue.sh                     libinput                      spa-json-dump
 brltty-setcaps                         libtool                       spa-monitor
 brltty-trtxt                           libtoolize                    spa-resample
 brltty-ttb                             libwacom-list-devices         speak-ng
 brltty-tune                            libwacom-list-local-devices   speaker-test
 btattach                               libwacom-update-db            speech-dispatcher
 btmgmt                                 link                          spice-vdagent
 btmon                                  linux-boot-prober             split
 btrace                                 linux32                       splitdiff
 btrecord                               linux64                       sprof
 btreplay                               ln                            src-hilite-lesspipe.sh
 btt                                    lneato                        sscg
 buildah                                loadkeys                      ssh
 bunzip2                                loadunimap                    ssh-add
 busctl                                 locale                        ssh-agent
 bwrap                                  localectl                     ssh-copy-id
 byacc                                  localedef                     ssh-keygen
 bzcat                                  locate                        ssh-keyscan
 bzcmp                                  logger                        ssltap
 bzdiff                                 login                         sss_ssh_authorizedkeys
 bzegrep                                loginctl                      sss_ssh_knownhostsproxy
 bzfgrep                                logname                       stap
 bzgrep                                 look                          stap-merge
 bzip2                                  lp                            stap-prep
 bzip2recover                           lp.cups                       stap-profile-annotate
 bzless                                 lpoptions                     stap-report
 bzmore                                 lpq                           stapbpf
 c++                                    lpq.cups                      stapdyn
 c++filt                                lpr                           staprun
 c89                                    lpr.cups                      stapsh
 c99                                    lprm                          startx
 ca-legacy                              lprm.cups                     stat
 cal                                    lpstat                        states
 calibrate_ppa                          lpstat.cups                   stdbuf
 callgrind_annotate                     ls                            strace
 callgrind_control                      lsattr                        strace-log-merge
 canberra-boot                          lsblk                         strings
 canberra-gtk-play                      lscpu                         strip
 cancel                                 lsdiff                        stty
 cancel.cups                            lsgpio                        su
 captoinfo                              lsiio                         sudo
 cat                                    lsinitrd                      sudoedit
 catchsegv                              lsipc                         sudoreplay
 catman                                 lsirq                         sum
 cc                                     lslocks                       sushi
 ccomps                                 lslogins                      svndiff
 cd                                     lsmcli                        svndiffview
 cd-convert                             lsmd                          switcherooctl
 cd-create-profile                      lsmem                         symlinks
 cd-drive                               lsns                          sync
 cd-fix-profile                         lsof                          systemctl
 cd-iccdump                             lsscsi                        systemd-analyze
 cd-info                                lsusb                         systemd-ask-password
 cd-it8                                 lsusb.py                      systemd-cat
 cd-paranoia                            lto-dump                      systemd-cgls
 cd-read                                ltrace                        systemd-cgtop
 cdda-player                            lua                           systemd-creds
 centrino-decode                        luac                          systemd-cryptenroll
 certutil                               luksmeta                      systemd-delta
 cg_annotate                            m4                            systemd-detect-virt
 cg_diff                                mac2unix                      systemd-dissect
 cg_merge                               make                          systemd-escape
 chacl                                  make-dummy-cert               systemd-firstboot
 chage                                  man                           systemd-hwdb
 chardetect                             man-recode                    systemd-id128
 chattr                                 man.man-db                    systemd-inhibit
 chcat                                  mandb                         systemd-machine-id-setup
 chcon                                  manpath                       systemd-mount
 check-regexp                           mapscrn                       systemd-notify
 checkmodule                            mbim-network                  systemd-path
 checkpolicy                            mbimcli                       systemd-repart
 checksctp                              mcookie                       systemd-run
 cheese                                 md5sum                        systemd-socket-activate
 chfn                                   mesg                          systemd-stdio-bridge
 chgrp                                  mkafmmap                      systemd-sysext
 chmem                                  mkdir                         systemd-sysusers
 chmod                                  mkfifo                        systemd-tmpfiles
 choom                                  mkfontdir                     systemd-tty-ask-password-agent
 chown                                  mkfontscale                   systemd-umount
 chrome-gnome-shell                     mknod                         tabs
 chronyc                                mktemp                        tac
 chrt                                   mm2gv                         tail
 chsh                                   mmc-tool                      tar
 chvt                                   mmcli                         taskset
 circo                                  mmdblookup                    tbl
 cksum                                  modulemd-validator            tclsh
 clear                                  modutil                       tclsh8.6
 clevis                                 mokutil                       team2bond
 clevis-decrypt                         monitor-sensor                teamd
 clevis-decrypt-null                    more                          teamdctl
 clevis-decrypt-sss                     mount                         teamnl
 clevis-decrypt-tang                    mountpoint                    tee
 clevis-decrypt-tpm2                    mpris-proxy                   test
 clevis-encrypt-null                    ms_print                      test_ppa
 clevis-encrypt-sss                     msgattrib                     tic
 clevis-encrypt-tang                    msgcat                        time
 clevis-encrypt-tpm2                    msgcmp                        timedatectl
 clevis-luks-bind                       msgcomm                       timeout
 clevis-luks-common-functions           msgconv                       tload
 clevis-luks-edit                       msgen                         tmon
 clevis-luks-list                       msgexec                       tnameserv
 clevis-luks-pass                       msgfilter                     toe
 clevis-luks-regen                      msgfmt                        top
 clevis-luks-report                     msggrep                       totem
 clevis-luks-unbind                     msginit                       totem-video-thumbnailer
 clevis-luks-unlock                     msgmerge                      touch
 clockdiff                              msgunfmt                      tpm2
 cluster                                msguniq                       tpm2_activatecredential
 cmp                                    mutter                        tpm2_certify
 cmsutil                                mv                            tpm2_certifyX509certutil
 cockpit-bridge                         namei                         tpm2_certifycreation
 col                                    nano                          tpm2_changeauth
 colcrt                                 nautilus                      tpm2_changeeps
 colormgr                               nautilus-autorun-software     tpm2_changepps
 colrm                                  nc                            tpm2_checkquote
 column                                 ncat                          tpm2_clear
 combinediff                            ndptool                       tpm2_clearcontrol
 comm                                   neato                         tpm2_clockrateadjust
 command                                nenscript                     tpm2_commit
 conmon                                 neqn                          tpm2_create
 coredumpctl                            netstat                       tpm2_createak
 cp                                     newgidmap                     tpm2_createek
 cpio                                   newgrp                        tpm2_createpolicy
 cpp                                    newuidmap                     tpm2_createprimary
 cpp2html                               nf-ct-add                     tpm2_dictionarylockout
 cpupower                               nf-ct-events                  tpm2_duplicate
 crlutil                                nf-ct-list                    tpm2_ecdhkeygen
 cronnext                               nf-exp-add                    tpm2_ecdhzgen
 crontab                                nf-exp-delete                 tpm2_ecephemeral
 crun                                   nf-exp-list                   tpm2_encryptdecrypt
 csplit                                 nf-log                        tpm2_eventlog
 cups-calibrate                         nf-monitor                    tpm2_evictcontrol
 cupstestppd                            nf-queue                      tpm2_flushcontext
 curl                                   ngettext                      tpm2_getcap
 cut                                    nice                          tpm2_getcommandauditdigest
 cvt                                    nisdomainname                 tpm2_geteccparameters
 cvtsudoers                             nl                            tpm2_getekcertificate
 cyrusbdb2current                       nl-addr-add                   tpm2_getpolicydigest
 date                                   nl-addr-delete                tpm2_getrandom
 dbilogstrip                            nl-addr-list                  tpm2_getsessionauditdigest
 dbiprof                                nl-class-add                  tpm2_gettestresult
 dbus-binding-tool                      nl-class-delete               tpm2_gettime
 dbus-broker                            nl-class-list                 tpm2_hash
 dbus-broker-launch                     nl-classid-lookup             tpm2_hierarchycontrol
 dbus-cleanup-sockets                   nl-cls-add                    tpm2_hmac
 dbus-daemon                            nl-cls-delete                 tpm2_import
 dbus-monitor                           nl-cls-list                   tpm2_incrementalselftest
 dbus-run-session                       nl-fib-lookup                 tpm2_load
 dbus-send                              nl-link-enslave               tpm2_loadexternal
 dbus-test-tool                         nl-link-ifindex2name          tpm2_makecredential
 dbus-update-activation-environment     nl-link-list                  tpm2_nvcertify
 dbus-uuidgen                           nl-link-name2ifindex          tpm2_nvdefine
 dbxtool                                nl-link-release               tpm2_nvextend
 dc                                     nl-link-set                   tpm2_nvincrement
 dconf                                  nl-link-stats                 tpm2_nvread
 dd                                     nl-list-caches                tpm2_nvreadlock
 deallocvt                              nl-list-sockets               tpm2_nvreadpublic
 debuginfod-find                        nl-monitor                    tpm2_nvsetbits
 dehtmldiff                             nl-neigh-add                  tpm2_nvundefine
 delv                                   nl-neigh-delete               tpm2_nvwrite
 desktop-file-edit                      nl-neigh-list                 tpm2_nvwritelock
 desktop-file-install                   nl-neightbl-list              tpm2_pcrallocate
 desktop-file-validate                  nl-pktloc-lookup              tpm2_pcrevent
 detect_ppa                             nl-qdisc-add                  tpm2_pcrextend
 df                                     nl-qdisc-delete               tpm2_pcrread
 dfu-tool                               nl-qdisc-list                 tpm2_pcrreset
 diff                                   nl-route-add                  tpm2_policyauthorize
 diff3                                  nl-route-delete               tpm2_policyauthorizenv
 diffimg                                nl-route-get                  tpm2_policyauthvalue
 diffpp                                 nl-route-list                 tpm2_policycommandcode
 diffstat                               nl-rule-list                  tpm2_policycountertimer
 dig                                    nl-tctree-list                tpm2_policycphash
 dijkstra                               nl-util-addr                  tpm2_policyduplicationselect
 dir                                    nm                            tpm2_policylocality
 dircolors                              nm-connection-editor          tpm2_policynamehash
 dirmngr                                nm-online                     tpm2_policynv
 dirmngr-client                         nmcli                         tpm2_policynvwritten
 dirname                                nmtui                         tpm2_policyor
 distro                                 nmtui-connect                 tpm2_policypassword
 dmesg                                  nmtui-edit                    tpm2_policypcr
 dnf                                    nmtui-hostname                tpm2_policyrestart
 dnf-3                                  nohup                         tpm2_policysecret
 dnsdomainname                          nop                           tpm2_policysigned
 dnstap-read                            notify-send                   tpm2_policytemplate
 domainname                             nproc                         tpm2_policyticket
 dos2unix                               nroff                         tpm2_print
 dot                                    nsenter                       tpm2_quote
 dot2gxl                                nslookup                      tpm2_rc_decode
 dotty                                  nss-policy-check              tpm2_readclock
 dracut                                 nsupdate                      tpm2_readpublic
 driverless                             numfmt                        tpm2_rsadecrypt
 driverless-fax                         objcopy                       tpm2_rsaencrypt
 du                                     objdump                       tpm2_selftest
 dumpkeys                               od                            tpm2_send
 dwp                                    openssl                       tpm2_sessionconfig
 dwz                                    openvt                        tpm2_setclock
 echo                                   orbd                          tpm2_setcommandauditstatus
 ed                                     orc-bugreport                 tpm2_setprimarypolicy
 edgepaint                              orca                          tpm2_shutdown
 editdiff                               os-prober                     tpm2_sign
 efikeygen                              osage                         tpm2_startauthsession
 egrep                                  osinfo-db-export              tpm2_startup
 eject                                  osinfo-db-import              tpm2_stirrandom
 elfedit                                osinfo-db-path                tpm2_testparms
 encguess                               osinfo-db-validate            tpm2_unseal
 enchant-2                              osinfo-detect                 tpm2_verifysignature
 enchant-lsmod-2                        osinfo-install-script         tpm2_zgen2phase
 enscript                               osinfo-query                  tput
 env                                    ostree                        tr
 envsubst                               over                          tracepath
 eog                                    p11-kit                       tracer
 eps2eps                                pacat                         tracker3
 eqn                                    pack200                       tred
 escputil                               pacmd                         tree
 espdiff                                pactl                         troff
 espeak-ng                              page_owner_sort               true
 eu-addr2line                           pamon                         truncate
 eu-ar                                  pango-list                    trust
 eu-elfclassify                         pango-segmentation            tset
 eu-elfcmp                              pango-view                    tsort
 eu-elfcompress                         paperconf                     tss2
 eu-elflint                             paplay                        tss2_authorizepolicy
 eu-findtextrel                         paps                          tss2_changeauth
 eu-make-debug-archive                  parec                         tss2_createkey
 eu-nm                                  parecord                      tss2_createnv
 eu-objdump                             passwd                        tss2_createseal
 eu-ranlib                              paste                         tss2_decrypt
 eu-readelf                             pasuspender                   tss2_delete
 eu-size                                patch                         tss2_encrypt
 eu-stack                               patchview                     tss2_exportkey
 eu-strings                             patchwork                     tss2_exportpolicy
 eu-strip                               pathchk                       tss2_getappdata
 eu-unstrip                             pax11publish                  tss2_getcertificate
 eutp                                   pbm2ppa                       tss2_getdescription
 evince                                 pbmtpg                        tss2_getinfo
 evince-previewer                       pdf2dsc                       tss2_getplatformcertificates
 evince-thumbnailer                     pdf2ps                        tss2_getrandom
 evmctl                                 pdfattach                     tss2_gettpmblobs
 ex                                     pdfdetach                     tss2_import
 exempi                                 pdffonts                      tss2_list
 exiv2                                  pdfimages                     tss2_nvextend
 expand                                 pdfinfo                       tss2_nvincrement
 expr                                   pdfseparate                   tss2_nvread
 factor                                 pdfsig                        tss2_nvsetbits
 fallocate                              pdftocairo                    tss2_nvwrite
 false                                  pdftohtml                     tss2_pcrextend
 fc                                     pdftoppm                      tss2_pcrread
 fc-cache                               pdftops                       tss2_provision
 fc-cache-64                            pdftotext                     tss2_quote
 fc-cat                                 pdfunite                      tss2_setappdata
 fc-conflist                            peekfd                        tss2_setcertificate
 fc-list                                perl                          tss2_setdescription
 fc-match                               perl5.32.1                    tss2_sign
 fc-pattern                             perldoc                       tss2_unseal
 fc-query                               pesigcheck                    tss2_verifyquote
 fc-scan                                pesign                        tss2_verifysignature
 fc-validate                            pesign-client                 tss2_writeauthorizenv
 fdp                                    pf2afm                        tty
 fg                                     pfbtopfa                      turbostat
 fgconsole                              pflags                        twopi
 fgrep                                  pgrep                         type
 file                                   pic                           tzselect
 filterdiff                             piconv                        udevadm
 fincore                                pidof                         udisksctl
 find                                   pidwait                       ul
 findmnt                                pigz                          ulimit
 fips-finish-install                    pinentry                      ulockmgr_server
 fips-mode-setup                        pinentry-curses               umask
 firefox                                pinentry-gnome3               umax_pp
 firewall-cmd                           pinfo                         umount
 firewall-offline-cmd                   ping                          unalias
 fixcvsdiff                             pinky                         uname
 flatpak                                pipewire                      uname26
 flatpak-bisect                         pipewire-pulse                unexpand
 flatpak-coredumpctl                    pk12util                      unflatten
 flex                                   pkaction                      unicode_start
 flex++                                 pkcheck                       unicode_stop
 flipdiff                               pkcon                         uniq
 flock                                  pkexec                        unix2dos
 fmt                                    pkg-config                    unix2mac
 fold                                   pkgconf                       unlink
 foomatic-combo-xml                     pkill                         unpack200
 foomatic-compiledb                     pkla-admin-identities         unpigz
 foomatic-configure                     pkla-check-authorization      unshare
 foomatic-datafile                      pkmon                         unwrapdiff
 foomatic-perl-data                     pkttyagent                    unxz
 foomatic-ppd-options                   pldd                          unzip
 foomatic-ppd-to-xml                    plymouth                      unzipsfx
 foomatic-ppdfile                       pmap                          unzstd
 foomatic-printjob                      pnm2ppa                       update-ca-trust
 foomatic-rip                           pod2man                       update-crypto-policies
 foomatic-searchprinter                 pod2text                      update-desktop-database
 fprintd-delete                         pod2usage                     update-gtk-immodules
 fprintd-enroll                         podman                        update-mime-database
 fprintd-list                           policytool                    updatedb
 fprintd-verify                         post-grohtml                  upower
 free                                   powernow-k8-decode            uptime
 fribidi                                powerprofilesctl              usb-devices
 funzip                                 ppdc                          usbhid-dump
 fuse-overlayfs                         ppdhtml                       users
 fuse2fs                                ppdi                          utmpdump
 fusermount                             ppdmerge                      uuidgen
 fusermount3                            ppdpo                         uuidparse
 fwupdagent                             pphs                          valgrind
 fwupdate                               pr                            valgrind-di-server
 fwupdmgr                               pre-grohtml                   valgrind-listener
 fwupdtool                              preconv                       vdir
 g++                                    printafm                      vdodmeventd
 g13                                    printenv                      vdodumpconfig
 gapplication                           printf                        vdoforcerebuild
 gawk                                   prlimit                       vdoformat
 gc                                     prtstat                       vdosetuuid
 gcalccmd                               prune                         vdostats
 gcc                                    ps                            verify_blkparse
 gcc-ar                                 ps2ascii                      vgdb
 gcc-nm                                 ps2epsi                       vi
 gcc-ranlib                             ps2pdf                        view
 gcm-import                             ps2pdf12                      vim
 gcm-inspect                            ps2pdf13                      vimdiff
 gcm-picker                             ps2pdf14                      vimdot
 gcm-viewer                             ps2pdfwr                      vimtutor
 gcore                                  ps2ps                         vlock
 gcov                                   ps2ps2                        vm-support
 gcov-dump                              psfaddtable                   vmhgfs-fuse
 gcov-tool                              psfgettable                   vmstat
 gcr-viewer                             psfstriptable                 vmtoolsd
 gdb                                    psfxtable                     vmware-alias-import
 gdb-add-index                          pslog                         vmware-checkvm
 gdbus                                  pstack                        vmware-hgfsclient
 gdk-pixbuf-query-loaders-64            pstree                        vmware-namespace-cmd
 gdk-pixbuf-thumbnailer                 pstree.x11                    vmware-rpctool
 gdm-screenshot                         ptx                           vmware-toolbox-cmd
 gdmflexiserver                         pw-cat                        vmware-user
 gedit                                  pw-cli                        vmware-user-suid-wrapper
 gencat                                 pw-dot                        vmware-vgauth-cmd
 gendiff                                pw-dsdplay                    vmware-vmblock-fuse
 genl-ctrl-list                         pw-dump                       vmware-xferlogs
 geqn                                   pw-jack                       vmwgfxctrl
 getconf                                pw-link                       vstp
 getent                                 pw-loopback                   w
 getfacl                                pw-metadata                   wait
 getfattr                               pw-mididump                   wall
 getkeycodes                            pw-midiplay                   watch
 getopt                                 pw-midirecord                 watchgnupg
 getopts                                pw-mon                        wavpack
 getsubids                              pw-play                       wc
 gettext                                pw-profiler                   wdctl
 gettext.sh                             pw-record                     wget
 gettextize                             pw-reserve                    whatis
 ghostscript                            pw-top                        whatis.man-db
 gio                                    pwd                           whereis
 gio-querymodules-64                    pwdx                          which
 git                                    pwmake                        whiptail
 git-receive-pack                       pwscore                       who
 git-shell                              pydoc                         whoami
 git-upload-archive                     pydoc3                        wireplumber
 git-upload-pack                        pydoc3.9                      withsctp
 gitdiff                                python                        wnck-urgency-monitor
 gitdiffview                            python3                       wpctl
 gjs                                    python3.9                     wpexec
 gjs-console                            pzstd                         write
 gkbd-keyboard-display                  qemu-ga                       wvgain
 glib-compile-schemas                   qmi-firmware-update           wvtag
 glxgears                               qmi-network                   wvunpack
 glxinfo                                qmicli                        x86_64
 glxinfo64                              quota                         x86_64-redhat-linux-c++
 gmake                                  quotasync                     x86_64-redhat-linux-g++
 gml2gv                                 ranlib                        x86_64-redhat-linux-gcc
 gneqn                                  rctest                        x86_64-redhat-linux-gcc-11
 gnome-calculator                       read                          x86_64-redhat-linux-gnu-pkg-config
 gnome-characters                       readelf                       x86_energy_perf_policy
 gnome-control-center                   readlink                      xargs
 gnome-disk-image-mounter               realpath                      xauth
 gnome-disks                            recode-sr-latin               xb-tool
 gnome-extensions                       recountdiff                   xbrlapi
 gnome-font-viewer                      red                           xdg-dbus-proxy
 gnome-help                             rediff                        xdg-desktop-icon
 gnome-keyring                          rename                        xdg-desktop-menu
 gnome-keyring-3                        renew-dummy-cert              xdg-email
 gnome-keyring-daemon                   renice                        xdg-icon-resource
 gnome-logs                             rescan-scsi-bus.sh            xdg-mime
 gnome-screenshot                       reset                         xdg-open
 gnome-session                          resizecons                    xdg-screensaver
 gnome-session-custom-session           rev                           xdg-settings
 gnome-session-inhibit                  rm                            xdg-user-dir
 gnome-session-quit                     rmdir                         xdg-user-dirs-gtk-update
 gnome-session-selector                 rmid                          xdg-user-dirs-update
 gnome-shell                            rmiregistry                   xdpyinfo
 gnome-shell-extension-prefs            rnano                         xdriinfo
 gnome-shell-extension-tool             rofiles-fuse                  xev
 gnome-shell-perf-tool                  rpm                           xgamma
 gnome-software                         rpm2archive                   xgettext
 gnome-system-monitor                   rpm2cpio                      xhost
 gnome-terminal                         rpmbuild                      xinit
 gnome-thumbnail-font                   rpmdb                         xinput
 gnome-tour                             rpmkeys                       xisxwayland
 gnroff                                 rpmquery                      xkbcomp
 gpasswd                                rpmsign                       xkill
 gpg                                    rpmspec                       xlsatoms
 gpg-agent                              rpmverify                     xlsclients
 gpg-card                               rsvg-convert                  xlsfonts
 gpg-connect-agent                      rsync                         xmlcatalog
 gpg-error                              rsync-ssl                     xmllint
 gpg-wks-client                         run-parts                     xmlsec1
 gpg-wks-server                         runcon                        xmlwf
 gpg2                                   rvi                           xmodmap
 gpgconf                                rview                         xprop
 gpgme-json                             rvim                          xrandr
 gpgparsemail                           sane-find-scanner             xrdb
 gpgsplit                               scalar                        xset
 gpgtar                                 scanimage                     xsetroot
 gpgv                                   sccmap                        xsetwacom
 gpgv2                                  scp                           xsltproc
 gpic                                   scp-dbus-service              xvinfo
 gpio-event-mon                         script                        xwininfo
 gpio-hammer                            scriptlive                    xxd
 gpio-watch                             scriptreplay                  xz
 gprof                                  scsi-rescan                   xzcat
 gr2fonttest                            scsi_logging_level            xzcmp
 graphml2gv                             scsi_mandat                   xzdec
 grep                                   scsi_readcap                  xzdiff
 grepdiff                               scsi_ready                    xzegrep
 grilo-test-ui-0.3                      scsi_satl                     xzfgrep
 grl-inspect-0.3                        scsi_start                    xzgrep
 grl-launch-0.3                         scsi_stop                     xzless
 groff                                  scsi_temperature              xzmore
 grops                                  sctp_darn                     yacc
 grotty                                 sctp_status                   yelp
 groups                                 sctp_test                     yelp-build
 grub2-editenv                          sdiff                         yelp-check
 grub2-file                             sealert                       yelp-new
 grub2-menulst2cfg                      secon                         yes
 grub2-mkimage                          secret-tool                   ypdomainname
 grub2-mkpasswd-pbkdf2                  sed                           yum
 grub2-mkrelpath                        sedismod                      zcat
 grub2-mount                            sedispol                      zcmp
 grub2-script-check                     semodule_expand               zdiff
 gs                                     semodule_link                 zdump
 gsbj                                   semodule_package              zegrep
 gsdj                                   semodule_unpackage            zenity
 gsdj500                                seq                           zfgrep
 gsettings                              servertool                    zforce
 gsf-office-thumbnailer                 sestatus                      zgrep
 gslj                                   setarch                       zip
 gslp                                   setfacl                       zipcloak
 gsnd                                   setfattr                      zipgrep
 gsoelim                                setfont                       zipinfo
 gsound-play                            setkeycodes                   zipnote
 gst-inspect-1.0                        setleds                       zipsplit
 gst-launch-1.0                         setmetamode                   zless
 gst-stats-1.0                          setpriv                       zmore
 gst-transcoder-1.0                     setsid                        znew
 gst-typefind-1.0                       setterm                       zsoelim
 gstack                                 setup-nsssysinit              zstd
 gtar                                   setup-nsssysinit.sh           zstdcat
 gtbl                                   setvtrgb                      zstdgrep
 gtf                                    setxkbmap                     zstdless
 gtk-launch                             sfdp                          zstdmt
[root@host1 ~]#
[root@host1 ~]#
```