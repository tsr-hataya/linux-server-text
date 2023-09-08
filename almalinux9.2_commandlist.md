# AlmaLinux9.2 コマンド一覧

OSインストール直後、Guest Additions インストール前の状態

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
[root@host1 ~]# ls /usr/sbin/
ModemManager                           grub2-set-password           pwck
NetworkManager                         grub2-setpassword            pwconv
accessdb                               grub2-switch-to-blscfg       pwhistory_helper
accton                                 grubby                       pwunconv
adcli                                  halt                         quotacheck
addgnupghome                           hdparm                       quotaoff
addpart                                hwclock                      quotaon
adduser                                hypervfcopyd                 quotastats
agetty                                 hypervkvpd                   raid-check
alsa-info.sh                           hypervvssd                   ras-mc-ctl
alsactl                                iconvconfig                  rasdaemon
alternatives                           ifconfig                     rdisc
anacron                                ifenslave                    rdma
applygnupgdefaults                     ifstat                       readprofile
arp                                    init                         realm
arpd                                   insmod                       reboot
arping                                 install-info                 repquota
arptables                              installkernel                resize2fs
arptables-nft                          intel_sdsi                   resizepart
arptables-nft-restore                  ip                           restorecon
arptables-nft-save                     ip6tables                    restorecon_xattr
arptables-restore                      ip6tables-nft                rfkill
arptables-save                         ip6tables-nft-restore        rmmod
atd                                    ip6tables-nft-save           route
atrun                                  ip6tables-restore            rsyslogd
auditctl                               ip6tables-restore-translate  rtacct
auditd                                 ip6tables-save               rtcwake
augenrules                             ip6tables-translate          rtkitctl
aureport                               ipmaddr                      rtmon
ausearch                               iprconfig                    rtstat
autrace                                iprdbg                       runlevel
avahi-daemon                           iprdump                      runuser
avcstat                                iprinit                      sa
badblocks                              iprsos                       sasldblistusers2
biosdecode                             iprupdate                    saslpasswd2
blkdeactivate                          ipset                        sedispatch
blkdiscard                             ipset-translate              sefcontext_compile
blkid                                  iptables                     selabel_digest
blkzone                                iptables-nft                 selabel_get_digests_all_partial_matches
blockdev                               iptables-nft-restore         selabel_lookup
bpftool                                iptables-nft-save            selabel_lookup_best_match
bridge                                 iptables-restore             selabel_partial_match
cache_check                            iptables-restore-translate   selinux_check_access
cache_dump                             iptables-save                selinuxconlist
cache_metadata_size                    iptables-translate           selinuxdefcon
cache_repair                           iptunnel                     selinuxenabled
cache_restore                          irqbalance                   selinuxexeccon
cache_writeback                        irqbalance-ui                semanage
capsh                                  iscsi-iname                  semodule
cfdisk                                 iscsiadm                     service
cgdisk                                 iscsid                       sestatus
chcpu                                  iscsistart                   setcap
chgpasswd                              iscsiuio                     setenforce
chpasswd                               iw                           setfiles
chronyd                                kexec                        setpci
chroot                                 kpartx                       setquota
clock                                  kpatch                       setregdomain
convertquota                           lchage                       setroubleshootd
cracklib-check                         ldattach                     setsebool
cracklib-format                        ldconfig                     sfdisk
cracklib-packer                        ledctl                       sgdisk
cracklib-unpacker                      ledmon                       shutdown
create-cracklib-dict                   lgroupadd                    skdump
criu                                   lgroupdel                    sktest
crond                                  lgroupmod                    slattach
cryptsetup                             lid                          smartctl
ctrlaltdel                             lnewusers                    smartd
ctstat                                 lnstat                       sos
cups-browsed                           load_policy                  sos-collector
cups-genppd.5.3                        lockdev                      sosreport
cups-genppdupdate                      logrotate                    spice-vdagentd
cupsaccept                             logsave                      ss
cupsctl                                losetup                      sshd
cupsd                                  lpadmin                      sss_cache
cupsdisable                            lpasswd                      sssd
cupsenable                             lpc                          sulogin
cupsfilter                             lpc.cups                     swaplabel
cupsreject                             lpinfo                       swapoff
dcb                                    lpmove                       swapon
ddns-confgen                           lshw                         switch_root
debugfs                                lsmod                        sysctl
delpart                                lspci                        tc
depmod                                 luseradd                     tcpdump
devlink                                luserdel                     tcpslice
dmeventd                               lusermod                     telinit
dmfilemapd                             lvchange                     thin_check
dmidecode                              lvconvert                    thin_delta
dmsetup                                lvcreate                     thin_dump
dmstats                                lvdisplay                    thin_ls
dnsmasq                                lvextend                     thin_metadata_pack
dosfsck                                lvm                          thin_metadata_size
dosfslabel                             lvm_import_vdo               thin_metadata_unpack
dump-acct                              lvmconfig                    thin_repair
dump-utmp                              lvmdevices                   thin_restore
dumpe2fs                               lvmdiskscan                  thin_rmap
e2freefrag                             lvmdump                      thin_trim
e2fsck                                 lvmpolld                     tipc
e2image                                lvmsadc                      tracepath
e2label                                lvmsar                       tracepath6
e2mmpstatus                            lvreduce                     tsig-keygen
e2undo                                 lvremove                     tune2fs
e4crypt                                lvrename                     tuned
e4defrag                               lvresize                     tuned-adm
eapol_test                             lvs                          udevadm
ebtables                               lvscan                       umount.udisks2
ebtables-nft                           makedumpfile                 unix_chkpwd
ebtables-nft-restore                   matchpathcon                 unix_update
ebtables-nft-save                      mcelog                       unsquashfs
ebtables-restore                       mdadm                        update-alternatives
ebtables-save                          mdmon                        update-pciids
edquota                                mii-diag                     update-smart-drivedb
era_check                              mii-tool                     usb_modeswitch
era_dump                               mkdict                       usb_modeswitch_dispatcher
era_invalidate                         mkdosfs                      useradd
era_restore                            mkdumprd                     userdel
ether-wake                             mke2fs                       usermod
ethtool                                mkfs                         validatetrans
faillock                               mkfs.cramfs                  vdpa
fatlabel                               mkfs.ext2                    vgcfgbackup
fdformat                               mkfs.ext3                    vgcfgrestore
fdisk                                  mkfs.ext4                    vgchange
filefrag                               mkfs.fat                     vgck
findfs                                 mkfs.minix                   vgconvert
firewalld                              mkfs.msdos                   vgcreate
fix-info-dir                           mkfs.vfat                    vgdisplay
fixfiles                               mkfs.xfs                     vgexport
fixparts                               mkhomedir_helper             vgextend
flashrom                               mklost+found                 vgimport
foomatic-addpjloptions                 mksquashfs                   vgimportclone
foomatic-cleanupdrivers                mkswap                       vgimportdevices
foomatic-extract-text                  modinfo                      vgmerge
foomatic-fix-xml                       modprobe                     vgmknodes
foomatic-getpjloptions                 mount.fuse                   vgreduce
foomatic-kitload                       mount.fuse3                  vgremove
foomatic-nonumericalids                mpathconf                    vgrename
foomatic-preferred-driver              mpathpersist                 vgs
foomatic-printermap-to-gutenprint-xml  mtr                          vgscan
foomatic-replaceoldprinterids          mtr-packet                   vgsplit
fsadm                                  multipath                    vigr
fsck                                   multipathd                   vipw
fsck.cramfs                            named-checkzone              virt-what
fsck.ext2                              named-compilezone            visudo
fsck.ext3                              named-nzd2nzf                vmcore-dmesg
fsck.ext4                              nameif                       vpddecode
fsck.fat                               newusers                     weak-modules
fsck.minix                             nft                          wipefs
fsck.msdos                             nologin                      wpa_cli
fsck.vfat                              nsec3hash                    wpa_passphrase
fsck.xfs                               nstat                        wpa_supplicant
fsfreeze                               nvme                         xfs_admin
fstrim                                 ownership                    xfs_bmap
fuser                                  packer                       xfs_copy
g13-syshelp                            pam_console_apply            xfs_db
gdisk                                  pam_namespace_helper         xfs_estimate
gdm                                    pam_timestamp_check          xfs_freeze
genhomedircon                          paperconfig                  xfs_fsr
genl                                   parted                       xfs_growfs
getcap                                 partprobe                    xfs_info
getenforce                             partx                        xfs_io
getpcaps                               pdata_tools                  xfs_logprint
getpidprevcon                          pidof                        xfs_mdrestore
getsebool                              ping                         xfs_metadump
groupadd                               ping6                        xfs_mkfile
groupdel                               pivot_root                   xfs_ncheck
groupmems                              plipconfig                   xfs_quota
groupmod                               plymouth-set-default-theme   xfs_repair
grpck                                  plymouthd                    xfs_rtcp
grpconv                                poweroff                     xfs_spaceman
grpunconv                              pvchange                     xfsdump
grub2-bios-setup                       pvck                         xfsinvutil
grub2-get-kernel-settings              pvcreate                     xfsrestore
grub2-install                          pvdisplay                    xqmstats
grub2-mkconfig                         pvmove                       xtables-monitor
grub2-probe                            pvremove                     xtables-nft-multi
grub2-reboot                           pvresize                     zic
grub2-set-bootflag                     pvs                          zramctl
grub2-set-default                      pvscan
[root@host1 ~]#
```

### /usr/sbin/

```Shell
[root@host1 ~]#
[root@host1 ~]# ls /usr/bin/
 VGAuthService                          gtk4-update-icon-cache        sg_compare_and_write
 WebKitWebDriver                        gtroff                        sg_copy_results
 X                                      gunzip                        sg_dd
 Xorg                                   gv2gml                        sg_decode_sense
 Xwayland                               gv2gxl                        sg_emc_trespass
'['                                     gvcolor                       sg_format
 a2x                                    gvgen                         sg_get_config
 a2x.py                                 gvmap                         sg_get_elem_status
 ac                                     gvmap.sh                      sg_get_lba_status
 aclocal                                gvpack                        sg_ident
 aclocal-1.16                           gvpr                          sg_inq
 aconnect                               gxl2dot                       sg_logs
 acyclic                                gxl2gv                        sg_luns
 addr2line                              gzexe                         sg_map
 airscan-discover                       gzip                          sg_map26
 alias                                  hardlink                      sg_modes
 alsaloop                               hash                          sg_opcodes
 alsamixer                              head                          sg_persist
 alsaunmute                             hex2hcd                       sg_prevent
 alt-java                               hexdump                       sg_raw
 amidi                                  host                          sg_rbuf
 amixer                                 hostid                        sg_rdac
 anthy-agent-unicode                    hostname                      sg_read
 anthy-dic-tool-unicode                 hostnamectl                   sg_read_attr
 anthy-morphological-analyzer-unicode   hunspell                      sg_read_block_limits
 aplay                                  i386                          sg_read_buffer
 aplaymidi                              ibus                          sg_read_long
 appstream-compose                      ibus-daemon                   sg_readcap
 appstream-util                         ibus-setup                    sg_reassign
 appstreamcli                           iconv                         sg_referrals
 apropos                                id                            sg_rep_pip
 apropos.man-db                         idiag-socket-details          sg_rep_zones
 ar                                     iecset                        sg_requests
 arch                                   ifnames                       sg_reset
 arecord                                iio_event_monitor             sg_reset_wp
 arecordmidi                            iio_generic_buffer            sg_rmsn
 arpaname                               info                          sg_rtpg
 arping                                 infocmp                       sg_safte
 as                                     infotocap                     sg_sanitize
 asciidoc                               install                       sg_sat_identify
 asciidoc.py                            install-catalog               sg_sat_phy_event
 aseqdump                               intel-speed-select            sg_sat_read_gplog
 aseqnet                                interdiff                     sg_sat_set_features
 aserver                                intltool-extract              sg_scan
 at                                     intltool-merge                sg_seek
 atq                                    intltool-prepare              sg_senddiag
 atrm                                   intltool-update               sg_ses
 attr                                   intltoolize                   sg_ses_microcode
 audit2allow                            ionice                        sg_start
 audit2why                              ipcmk                         sg_stpg
 aulast                                 ipcrm                         sg_stream_ctl
 aulastlog                              ipcs                          sg_sync
 ausyscall                              ippfind                       sg_test_rwbuf
 authselect                             ipptool                       sg_timestamp
 authvar                                iptc                          sg_turs
 autoconf                               irqtop                        sg_unmap
 autoheader                             isdv4-serial-inputattach      sg_verify
 autom4te                               iso-info                      sg_vpd
 automake                               iso-read                      sg_wr_mode
 automake-1.16                          isosize                       sg_write_buffer
 autopoint                              itstool                       sg_write_long
 autoreconf                             java                          sg_write_same
 autoscan                               java2html                     sg_write_verify
 autoupdate                             jcat-tool                     sg_write_x
 auvirt                                 jjs                           sg_xcopy
 avinfo                                 jobs                          sg_zone
 awk                                    join                          sginfo
 axfer                                  jose                          sgm_dd
 b2sum                                  journalctl                    sgmlwhich
 baobab                                 jq                            sgp_dd
 base32                                 json_reformat                 sh
 base64                                 json_verify                   sha1hmac
 basename                               kasumi-unicode                sha1sum
 basenc                                 kbd_mode                      sha224hmac
 bash                                   kbdinfo                       sha224sum
 bashbug                                kbdrate                       sha256hmac
 bashbug-64                             kdumpctl                      sha256sum
 batch                                  kernel-install                sha384hmac
 bc                                     keytool                       sha384sum
 bcomps                                 kill                          sha512hmac
 bg                                     killall                       sha512sum
 bison                                  kmod                          showconsolefont
 blkiomon                               kvm_stat                      showkey
 blkparse                               l2ping                        shred
 blkrawverify                           l2test                        shuf
 blktrace                               last                          signver
 bluemoon                               lastb                         sim_lsmplugin
 bluetooth-sendto                       lastcomm                      simc_lsmplugin
 bluetoothctl                           lastlog                       size
 bno_plot.py                            lchfn                         skill
 boltctl                                lchsh                         slabinfo
 bond2team                              ld                            slabtop
 bootctl                                ld.bfd                        sleep
 brltty                                 ld.gold                       sliceprint
 brltty-atb                             ld.so                         slirp4netns
 brltty-cldr                            ldd                           sndfile-resample
 brltty-clip                            lefty                         snice
 brltty-config.sh                       less                          soelim
 brltty-ctb                             lessecho                      soelim.groff
 brltty-genkey                          lesskey                       sort
 brltty-ktb                             lesspipe.sh                   sotruss
 brltty-lscmds                          lex                           soundstretch
 brltty-lsinc                           lexgrog                       source-highlight
 brltty-mkuser                          libgtop_daemon2               source-highlight-esc.sh
 brltty-morse                           libgtop_server2               source-highlight-settings
 brltty-prologue.sh                     libieee1284_test              spa-acp-tool
 brltty-setcaps                         libinput                      spa-inspect
 brltty-trtxt                           libtool                       spa-json-dump
 brltty-ttb                             libtoolize                    spa-monitor
 brltty-tune                            libwacom-list-devices         spa-resample
 btattach                               libwacom-list-local-devices   speak-ng
 btmgmt                                 libwacom-update-db            speaker-test
 btmon                                  link                          speech-dispatcher
 btrace                                 linux-boot-prober             spice-vdagent
 btrecord                               linux32                       split
 btreplay                               linux64                       splitdiff
 btt                                    ln                            sprof
 buildah                                lneato                        src-hilite-lesspipe.sh
 bunzip2                                loadkeys                      sscg
 busctl                                 loadunimap                    ssh
 bwrap                                  locale                        ssh-add
 byacc                                  localectl                     ssh-agent
 bzcat                                  localedef                     ssh-copy-id
 bzcmp                                  locate                        ssh-keygen
 bzdiff                                 logger                        ssh-keyscan
 bzegrep                                login                         ssltap
 bzfgrep                                loginctl                      sss_ssh_authorizedkeys
 bzgrep                                 logname                       sss_ssh_knownhostsproxy
 bzip2                                  look                          stap
 bzip2recover                           lp                            stap-merge
 bzless                                 lp.cups                       stap-prep
 bzmore                                 lpoptions                     stap-profile-annotate
 c++                                    lpq                           stap-report
 c++filt                                lpq.cups                      stapbpf
 c89                                    lpr                           stapdyn
 c99                                    lpr.cups                      staprun
 ca-legacy                              lprm                          stapsh
 cal                                    lprm.cups                     startx
 calibrate_ppa                          lpstat                        stat
 callgrind_annotate                     lpstat.cups                   states
 callgrind_control                      ls                            stdbuf
 canberra-boot                          lsattr                        strace
 canberra-gtk-play                      lsblk                         strace-log-merge
 cancel                                 lscpu                         strings
 cancel.cups                            lsdiff                        strip
 captoinfo                              lsgpio                        stty
 cat                                    lsiio                         su
 catchsegv                              lsinitrd                      sudo
 catman                                 lsipc                         sudoedit
 cc                                     lsirq                         sudoreplay
 ccomps                                 lslocks                       sum
 cd                                     lslogins                      sushi
 cd-convert                             lsmcli                        svndiff
 cd-create-profile                      lsmd                          svndiffview
 cd-drive                               lsmem                         switcherooctl
 cd-fix-profile                         lsns                          symlinks
 cd-iccdump                             lsof                          sync
 cd-info                                lsscsi                        systemctl
 cd-it8                                 lsusb                         systemd-analyze
 cd-paranoia                            lsusb.py                      systemd-ask-password
 cd-read                                lto-dump                      systemd-cat
 cdda-player                            ltrace                        systemd-cgls
 centrino-decode                        lua                           systemd-cgtop
 certutil                               luac                          systemd-creds
 cg_annotate                            luksmeta                      systemd-cryptenroll
 cg_diff                                m4                            systemd-delta
 cg_merge                               mac2unix                      systemd-detect-virt
 chacl                                  make                          systemd-dissect
 chage                                  make-dummy-cert               systemd-escape
 chardetect                             man                           systemd-firstboot
 chattr                                 man-recode                    systemd-hwdb
 chcat                                  man.man-db                    systemd-id128
 chcon                                  mandb                         systemd-inhibit
 check-regexp                           manpath                       systemd-machine-id-setup
 checkmodule                            mapscrn                       systemd-mount
 checkpolicy                            mbim-network                  systemd-notify
 checksctp                              mbimcli                       systemd-path
 cheese                                 mcookie                       systemd-repart
 chfn                                   md5sum                        systemd-run
 chgrp                                  mesg                          systemd-socket-activate
 chmem                                  mkafmmap                      systemd-stdio-bridge
 chmod                                  mkdir                         systemd-sysext
 choom                                  mkfifo                        systemd-sysusers
 chown                                  mkfontdir                     systemd-tmpfiles
 chrome-gnome-shell                     mkfontscale                   systemd-tty-ask-password-agent
 chronyc                                mknod                         systemd-umount
 chrt                                   mktemp                        tabs
 chsh                                   mm2gv                         tac
 chvt                                   mmc-tool                      tail
 circo                                  mmcli                         tar
 cksum                                  mmdblookup                    taskset
 clear                                  modulemd-validator            tbl
 clevis                                 modutil                       tclsh
 clevis-decrypt                         mokutil                       tclsh8.6
 clevis-decrypt-null                    monitor-sensor                team2bond
 clevis-decrypt-sss                     more                          teamd
 clevis-decrypt-tang                    mount                         teamdctl
 clevis-decrypt-tpm2                    mountpoint                    teamnl
 clevis-encrypt-null                    mpris-proxy                   tee
 clevis-encrypt-sss                     ms_print                      test
 clevis-encrypt-tang                    msgattrib                     test_ppa
 clevis-encrypt-tpm2                    msgcat                        tic
 clevis-luks-bind                       msgcmp                        time
 clevis-luks-common-functions           msgcomm                       timedatectl
 clevis-luks-edit                       msgconv                       timeout
 clevis-luks-list                       msgen                         tload
 clevis-luks-pass                       msgexec                       tmon
 clevis-luks-regen                      msgfilter                     tnameserv
 clevis-luks-report                     msgfmt                        toe
 clevis-luks-unbind                     msggrep                       top
 clevis-luks-unlock                     msginit                       totem
 clockdiff                              msgmerge                      totem-video-thumbnailer
 cluster                                msgunfmt                      touch
 cmp                                    msguniq                       tpm2
 cmsutil                                mutter                        tpm2_activatecredential
 cockpit-bridge                         mv                            tpm2_certify
 col                                    namei                         tpm2_certifyX509certutil
 colcrt                                 nano                          tpm2_certifycreation
 colormgr                               nautilus                      tpm2_changeauth
 colrm                                  nautilus-autorun-software     tpm2_changeeps
 column                                 nc                            tpm2_changepps
 combinediff                            ncat                          tpm2_checkquote
 comm                                   ndptool                       tpm2_clear
 command                                neato                         tpm2_clearcontrol
 conmon                                 nenscript                     tpm2_clockrateadjust
 coredumpctl                            neqn                          tpm2_commit
 cp                                     netstat                       tpm2_create
 cpio                                   newgidmap                     tpm2_createak
 cpp                                    newgrp                        tpm2_createek
 cpp2html                               newuidmap                     tpm2_createpolicy
 cpupower                               nf-ct-add                     tpm2_createprimary
 crlutil                                nf-ct-events                  tpm2_dictionarylockout
 cronnext                               nf-ct-list                    tpm2_duplicate
 crontab                                nf-exp-add                    tpm2_ecdhkeygen
 crun                                   nf-exp-delete                 tpm2_ecdhzgen
 csplit                                 nf-exp-list                   tpm2_ecephemeral
 cups-calibrate                         nf-log                        tpm2_encryptdecrypt
 cupstestppd                            nf-monitor                    tpm2_eventlog
 curl                                   nf-queue                      tpm2_evictcontrol
 cut                                    ngettext                      tpm2_flushcontext
 cvt                                    nice                          tpm2_getcap
 cvtsudoers                             nisdomainname                 tpm2_getcommandauditdigest
 cyrusbdb2current                       nl                            tpm2_geteccparameters
 date                                   nl-addr-add                   tpm2_getekcertificate
 dbilogstrip                            nl-addr-delete                tpm2_getpolicydigest
 dbiprof                                nl-addr-list                  tpm2_getrandom
 dbus-binding-tool                      nl-class-add                  tpm2_getsessionauditdigest
 dbus-broker                            nl-class-delete               tpm2_gettestresult
 dbus-broker-launch                     nl-class-list                 tpm2_gettime
 dbus-cleanup-sockets                   nl-classid-lookup             tpm2_hash
 dbus-daemon                            nl-cls-add                    tpm2_hierarchycontrol
 dbus-monitor                           nl-cls-delete                 tpm2_hmac
 dbus-run-session                       nl-cls-list                   tpm2_import
 dbus-send                              nl-fib-lookup                 tpm2_incrementalselftest
 dbus-test-tool                         nl-link-enslave               tpm2_load
 dbus-update-activation-environment     nl-link-ifindex2name          tpm2_loadexternal
 dbus-uuidgen                           nl-link-list                  tpm2_makecredential
 dbxtool                                nl-link-name2ifindex          tpm2_nvcertify
 dc                                     nl-link-release               tpm2_nvdefine
 dconf                                  nl-link-set                   tpm2_nvextend
 dd                                     nl-link-stats                 tpm2_nvincrement
 deallocvt                              nl-list-caches                tpm2_nvread
 debuginfod-find                        nl-list-sockets               tpm2_nvreadlock
 dehtmldiff                             nl-monitor                    tpm2_nvreadpublic
 delv                                   nl-neigh-add                  tpm2_nvsetbits
 desktop-file-edit                      nl-neigh-delete               tpm2_nvundefine
 desktop-file-install                   nl-neigh-list                 tpm2_nvwrite
 desktop-file-validate                  nl-neightbl-list              tpm2_nvwritelock
 detect_ppa                             nl-pktloc-lookup              tpm2_pcrallocate
 df                                     nl-qdisc-add                  tpm2_pcrevent
 dfu-tool                               nl-qdisc-delete               tpm2_pcrextend
 diff                                   nl-qdisc-list                 tpm2_pcrread
 diff3                                  nl-route-add                  tpm2_pcrreset
 diffimg                                nl-route-delete               tpm2_policyauthorize
 diffpp                                 nl-route-get                  tpm2_policyauthorizenv
 diffstat                               nl-route-list                 tpm2_policyauthvalue
 dig                                    nl-rule-list                  tpm2_policycommandcode
 dijkstra                               nl-tctree-list                tpm2_policycountertimer
 dir                                    nl-util-addr                  tpm2_policycphash
 dircolors                              nm                            tpm2_policyduplicationselect
 dirmngr                                nm-connection-editor          tpm2_policylocality
 dirmngr-client                         nm-online                     tpm2_policynamehash
 dirname                                nmcli                         tpm2_policynv
 distro                                 nmtui                         tpm2_policynvwritten
 dmesg                                  nmtui-connect                 tpm2_policyor
 dnf                                    nmtui-edit                    tpm2_policypassword
 dnf-3                                  nmtui-hostname                tpm2_policypcr
 dnsdomainname                          nohup                         tpm2_policyrestart
 dnstap-read                            nop                           tpm2_policysecret
 domainname                             notify-send                   tpm2_policysigned
 dos2unix                               nproc                         tpm2_policytemplate
 dot                                    nroff                         tpm2_policyticket
 dot2gxl                                nsenter                       tpm2_print
 dotty                                  nslookup                      tpm2_quote
 dracut                                 nss-policy-check              tpm2_rc_decode
 driverless                             nsupdate                      tpm2_readclock
 driverless-fax                         numfmt                        tpm2_readpublic
 du                                     objcopy                       tpm2_rsadecrypt
 dumpkeys                               objdump                       tpm2_rsaencrypt
 dwp                                    od                            tpm2_selftest
 dwz                                    openssl                       tpm2_send
 echo                                   openvt                        tpm2_sessionconfig
 ed                                     orbd                          tpm2_setclock
 edgepaint                              orc-bugreport                 tpm2_setcommandauditstatus
 editdiff                               orca                          tpm2_setprimarypolicy
 efikeygen                              os-prober                     tpm2_shutdown
 egrep                                  osage                         tpm2_sign
 eject                                  osinfo-db-export              tpm2_startauthsession
 elfedit                                osinfo-db-import              tpm2_startup
 encguess                               osinfo-db-path                tpm2_stirrandom
 enchant-2                              osinfo-db-validate            tpm2_testparms
 enchant-lsmod-2                        osinfo-detect                 tpm2_unseal
 enscript                               osinfo-install-script         tpm2_verifysignature
 env                                    osinfo-query                  tpm2_zgen2phase
 envsubst                               ostree                        tput
 eog                                    over                          tr
 eps2eps                                p11-kit                       tracepath
 eqn                                    pacat                         tracer
 escputil                               pack200                       tracker3
 espdiff                                pacmd                         tred
 espeak-ng                              pactl                         tree
 eu-addr2line                           page_owner_sort               troff
 eu-ar                                  pamon                         true
 eu-elfclassify                         pango-list                    truncate
 eu-elfcmp                              pango-segmentation            trust
 eu-elfcompress                         pango-view                    tset
 eu-elflint                             paperconf                     tsort
 eu-findtextrel                         paplay                        tss2
 eu-make-debug-archive                  paps                          tss2_authorizepolicy
 eu-nm                                  parec                         tss2_changeauth
 eu-objdump                             parecord                      tss2_createkey
 eu-ranlib                              passwd                        tss2_createnv
 eu-readelf                             paste                         tss2_createseal
 eu-size                                pasuspender                   tss2_decrypt
 eu-stack                               patch                         tss2_delete
 eu-strings                             patchview                     tss2_encrypt
 eu-strip                               patchwork                     tss2_exportkey
 eu-unstrip                             pathchk                       tss2_exportpolicy
 eutp                                   pax11publish                  tss2_getappdata
 evince                                 pbm2ppa                       tss2_getcertificate
 evince-previewer                       pbmtpg                        tss2_getdescription
 evince-thumbnailer                     pdf2dsc                       tss2_getinfo
 evmctl                                 pdf2ps                        tss2_getplatformcertificates
 ex                                     pdfattach                     tss2_getrandom
 exempi                                 pdfdetach                     tss2_gettpmblobs
 exiv2                                  pdffonts                      tss2_import
 expand                                 pdfimages                     tss2_list
 expr                                   pdfinfo                       tss2_nvextend
 factor                                 pdfseparate                   tss2_nvincrement
 fallocate                              pdfsig                        tss2_nvread
 false                                  pdftocairo                    tss2_nvsetbits
 fc                                     pdftohtml                     tss2_nvwrite
 fc-cache                               pdftoppm                      tss2_pcrextend
 fc-cache-64                            pdftops                       tss2_pcrread
 fc-cat                                 pdftotext                     tss2_provision
 fc-conflist                            pdfunite                      tss2_quote
 fc-list                                peekfd                        tss2_setappdata
 fc-match                               perl                          tss2_setcertificate
 fc-pattern                             perl5.32.1                    tss2_setdescription
 fc-query                               perldoc                       tss2_sign
 fc-scan                                pesigcheck                    tss2_unseal
 fc-validate                            pesign                        tss2_verifyquote
 fdp                                    pesign-client                 tss2_verifysignature
 fg                                     pf2afm                        tss2_writeauthorizenv
 fgconsole                              pfbtopfa                      tty
 fgrep                                  pflags                        turbostat
 file                                   pgrep                         twopi
 filterdiff                             pic                           type
 fincore                                piconv                        tzselect
 find                                   pidof                         udevadm
 findmnt                                pidwait                       udisksctl
 fips-finish-install                    pigz                          ul
 fips-mode-setup                        pinentry                      ulimit
 firefox                                pinentry-curses               ulockmgr_server
 firewall-cmd                           pinentry-gnome3               umask
 firewall-offline-cmd                   pinfo                         umax_pp
 fixcvsdiff                             ping                          umount
 flatpak                                pinky                         unalias
 flatpak-bisect                         pipewire                      uname
 flatpak-coredumpctl                    pipewire-pulse                uname26
 flex                                   pk12util                      unexpand
 flex++                                 pkaction                      unflatten
 flipdiff                               pkcheck                       unicode_start
 flock                                  pkcon                         unicode_stop
 fmt                                    pkexec                        uniq
 fold                                   pkg-config                    unix2dos
 foomatic-combo-xml                     pkgconf                       unix2mac
 foomatic-compiledb                     pkill                         unlink
 foomatic-configure                     pkla-admin-identities         unpack200
 foomatic-datafile                      pkla-check-authorization      unpigz
 foomatic-perl-data                     pkmon                         unshare
 foomatic-ppd-options                   pkttyagent                    unwrapdiff
 foomatic-ppd-to-xml                    pldd                          unxz
 foomatic-ppdfile                       plymouth                      unzip
 foomatic-printjob                      pmap                          unzipsfx
 foomatic-rip                           pnm2ppa                       unzstd
 foomatic-searchprinter                 pod2man                       update-ca-trust
 fprintd-delete                         pod2text                      update-crypto-policies
 fprintd-enroll                         pod2usage                     update-desktop-database
 fprintd-list                           podman                        update-gtk-immodules
 fprintd-verify                         policytool                    update-mime-database
 free                                   post-grohtml                  updatedb
 fribidi                                powernow-k8-decode            upower
 funzip                                 powerprofilesctl              uptime
 fuse-overlayfs                         ppdc                          usb-devices
 fuse2fs                                ppdhtml                       usbhid-dump
 fusermount                             ppdi                          users
 fusermount3                            ppdmerge                      utmpdump
 fwupdagent                             ppdpo                         uuidgen
 fwupdate                               pphs                          uuidparse
 fwupdmgr                               pr                            valgrind
 fwupdtool                              pre-grohtml                   valgrind-di-server
 g++                                    preconv                       valgrind-listener
 g13                                    printafm                      vdir
 gapplication                           printenv                      vdodmeventd
 gawk                                   printf                        vdodumpconfig
 gc                                     prlimit                       vdoforcerebuild
 gcalccmd                               prtstat                       vdoformat
 gcc                                    prune                         vdosetuuid
 gcc-ar                                 ps                            vdostats
 gcc-nm                                 ps2ascii                      verify_blkparse
 gcc-ranlib                             ps2epsi                       vgdb
 gcm-import                             ps2pdf                        vi
 gcm-inspect                            ps2pdf12                      view
 gcm-picker                             ps2pdf13                      vim
 gcm-viewer                             ps2pdf14                      vimdiff
 gcore                                  ps2pdfwr                      vimdot
 gcov                                   ps2ps                         vimtutor
 gcov-dump                              ps2ps2                        vlock
 gcov-tool                              psfaddtable                   vm-support
 gcr-viewer                             psfgettable                   vmhgfs-fuse
 gdb                                    psfstriptable                 vmstat
 gdb-add-index                          psfxtable                     vmtoolsd
 gdbus                                  pslog                         vmware-alias-import
 gdk-pixbuf-query-loaders-64            pstack                        vmware-checkvm
 gdk-pixbuf-thumbnailer                 pstree                        vmware-hgfsclient
 gdm-screenshot                         pstree.x11                    vmware-namespace-cmd
 gdmflexiserver                         ptx                           vmware-rpctool
 gedit                                  pw-cat                        vmware-toolbox-cmd
 gencat                                 pw-cli                        vmware-user
 gendiff                                pw-dot                        vmware-user-suid-wrapper
 genl-ctrl-list                         pw-dsdplay                    vmware-vgauth-cmd
 geqn                                   pw-dump                       vmware-vmblock-fuse
 getconf                                pw-jack                       vmware-xferlogs
 getent                                 pw-link                       vmwgfxctrl
 getfacl                                pw-loopback                   vstp
 getfattr                               pw-metadata                   w
 getkeycodes                            pw-mididump                   wait
 getopt                                 pw-midiplay                   wall
 getopts                                pw-midirecord                 watch
 getsubids                              pw-mon                        watchgnupg
 gettext                                pw-play                       wavpack
 gettext.sh                             pw-profiler                   wc
 gettextize                             pw-record                     wdctl
 ghostscript                            pw-reserve                    wget
 gio                                    pw-top                        whatis
 gio-querymodules-64                    pwd                           whatis.man-db
 git                                    pwdx                          whereis
 git-receive-pack                       pwmake                        which
 git-shell                              pwscore                       whiptail
 git-upload-archive                     pydoc                         who
 git-upload-pack                        pydoc3                        whoami
 gitdiff                                pydoc3.9                      wireplumber
 gitdiffview                            python                        withsctp
 gjs                                    python3                       wnck-urgency-monitor
 gjs-console                            python3.9                     wpctl
 gkbd-keyboard-display                  pzstd                         wpexec
 glib-compile-schemas                   qemu-ga                       write
 glxgears                               qmi-firmware-update           wvgain
 glxinfo                                qmi-network                   wvtag
 glxinfo64                              qmicli                        wvunpack
 gmake                                  quota                         x86_64
 gml2gv                                 quotasync                     x86_64-redhat-linux-c++
 gneqn                                  ranlib                        x86_64-redhat-linux-g++
 gnome-calculator                       rctest                        x86_64-redhat-linux-gcc
 gnome-characters                       read                          x86_64-redhat-linux-gcc-11
 gnome-control-center                   readelf                       x86_64-redhat-linux-gnu-pkg-config
 gnome-disk-image-mounter               readlink                      x86_energy_perf_policy
 gnome-disks                            realpath                      xargs
 gnome-extensions                       recode-sr-latin               xauth
 gnome-font-viewer                      recountdiff                   xb-tool
 gnome-help                             red                           xbrlapi
 gnome-keyring                          rediff                        xdg-dbus-proxy
 gnome-keyring-3                        rename                        xdg-desktop-icon
 gnome-keyring-daemon                   renew-dummy-cert              xdg-desktop-menu
 gnome-logs                             renice                        xdg-email
 gnome-screenshot                       rescan-scsi-bus.sh            xdg-icon-resource
 gnome-session                          reset                         xdg-mime
 gnome-session-custom-session           resizecons                    xdg-open
 gnome-session-inhibit                  rev                           xdg-screensaver
 gnome-session-quit                     rm                            xdg-settings
 gnome-session-selector                 rmdir                         xdg-user-dir
 gnome-shell                            rmid                          xdg-user-dirs-gtk-update
 gnome-shell-extension-prefs            rmiregistry                   xdg-user-dirs-update
 gnome-shell-extension-tool             rnano                         xdpyinfo
 gnome-shell-perf-tool                  rofiles-fuse                  xdriinfo
 gnome-software                         rpm                           xev
 gnome-system-monitor                   rpm2archive                   xgamma
 gnome-terminal                         rpm2cpio                      xgettext
 gnome-thumbnail-font                   rpmbuild                      xhost
 gnome-tour                             rpmdb                         xinit
 gnroff                                 rpmkeys                       xinput
 gpasswd                                rpmquery                      xisxwayland
 gpg                                    rpmsign                       xkbcomp
 gpg-agent                              rpmspec                       xkill
 gpg-card                               rpmverify                     xlsatoms
 gpg-connect-agent                      rsvg-convert                  xlsclients
 gpg-error                              rsync                         xlsfonts
 gpg-wks-client                         rsync-ssl                     xmlcatalog
 gpg-wks-server                         run-parts                     xmllint
 gpg2                                   runcon                        xmlsec1
 gpgconf                                rvi                           xmlwf
 gpgme-json                             rview                         xmodmap
 gpgparsemail                           rvim                          xprop
 gpgsplit                               sane-find-scanner             xrandr
 gpgtar                                 scalar                        xrdb
 gpgv                                   scanimage                     xset
 gpgv2                                  sccmap                        xsetroot
 gpic                                   scp                           xsetwacom
 gpio-event-mon                         scp-dbus-service              xsltproc
 gpio-hammer                            script                        xvinfo
 gpio-watch                             scriptlive                    xwininfo
 gprof                                  scriptreplay                  xxd
 gr2fonttest                            scsi-rescan                   xz
 graphml2gv                             scsi_logging_level            xzcat
 grep                                   scsi_mandat                   xzcmp
 grepdiff                               scsi_readcap                  xzdec
 grilo-test-ui-0.3                      scsi_ready                    xzdiff
 grl-inspect-0.3                        scsi_satl                     xzegrep
 grl-launch-0.3                         scsi_start                    xzfgrep
 groff                                  scsi_stop                     xzgrep
 grops                                  scsi_temperature              xzless
 grotty                                 sctp_darn                     xzmore
 groups                                 sctp_status                   yacc
 grub2-editenv                          sctp_test                     yelp
 grub2-file                             sdiff                         yelp-build
 grub2-menulst2cfg                      sealert                       yelp-check
 grub2-mkimage                          secon                         yelp-new
 grub2-mkpasswd-pbkdf2                  secret-tool                   yes
 grub2-mkrelpath                        sed                           ypdomainname
 grub2-mount                            sedismod                      yum
 grub2-script-check                     sedispol                      zcat
 gs                                     semodule_expand               zcmp
 gsbj                                   semodule_link                 zdiff
 gsdj                                   semodule_package              zdump
 gsdj500                                semodule_unpackage            zegrep
 gsettings                              seq                           zenity
 gsf-office-thumbnailer                 servertool                    zfgrep
 gslj                                   sestatus                      zforce
 gslp                                   setarch                       zgrep
 gsnd                                   setfacl                       zip
 gsoelim                                setfattr                      zipcloak
 gsound-play                            setfont                       zipgrep
 gst-inspect-1.0                        setkeycodes                   zipinfo
 gst-launch-1.0                         setleds                       zipnote
 gst-stats-1.0                          setmetamode                   zipsplit
 gst-transcoder-1.0                     setpriv                       zless
 gst-typefind-1.0                       setsid                        zmore
 gstack                                 setterm                       znew
 gtar                                   setup-nsssysinit              zsoelim
 gtbl                                   setup-nsssysinit.sh           zstd
 gtf                                    setvtrgb                      zstdcat
 gtk-launch                             setxkbmap                     zstdgrep
 gtk-query-immodules-2.0-64             sfdp                          zstdless
 gtk-query-immodules-3.0-64             sftp                          zstdmt
 gtk-update-icon-cache                  sg
 gtk4-launch                            sg_bg_ctl
[root@host1 ~]#
```