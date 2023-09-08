# SELinux

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

```Shell
[root@host1 ~]#
[root@host1 ~]# systemctl list-unit-files -t service
UNIT FILE                                  STATE           PRESET
accounts-daemon.service                    enabled         enabled
alsa-restore.service                       static          -
alsa-state.service                         static          -
arp-ethers.service                         disabled        disabled
atd.service                                enabled         enabled
auditd.service                             enabled         enabled
autovt@.service                            alias           -
avahi-daemon.service                       enabled         enabled
blk-availability.service                   disabled        disabled
bluetooth.service                          enabled         enabled
bolt.service                               static          -
brltty.service                             disabled        disabled
canberra-system-bootup.service             disabled        disabled
canberra-system-shutdown-reboot.service    disabled        disabled
canberra-system-shutdown.service           disabled        disabled
chrony-wait.service                        disabled        disabled
chronyd.service                            enabled         enabled
cni-dhcp.service                           disabled        disabled
cockpit-motd.service                       static          -
cockpit-wsinstance-http.service            static          -
cockpit-wsinstance-https-factory@.service  static          -
cockpit-wsinstance-https@.service          static          -
cockpit.service                            static          -
colord.service                             static          -
configure-printer@.service                 static          -
console-getty.service                      disabled        disabled
container-getty@.service                   static          -
cpupower.service                           disabled        disabled
crond.service                              enabled         enabled
cups-browsed.service                       disabled        disabled
cups.service                               enabled         enabled
dbus-broker.service                        enabled         enabled
dbus-daemon.service                        disabled        disabled
dbus-org.bluez.service                     alias           -
dbus-org.fedoraproject.FirewallD1.service  alias           -
dbus-org.freedesktop.Avahi.service         alias           -
dbus-org.freedesktop.hostname1.service     alias           -
dbus-org.freedesktop.locale1.service       alias           -
dbus-org.freedesktop.login1.service        alias           -
dbus-org.freedesktop.ModemManager1.service alias           -
dbus-org.freedesktop.nm-dispatcher.service alias           -
dbus-org.freedesktop.timedate1.service     alias           -
dbus.service                               alias           -
debug-shell.service                        disabled        disabled
display-manager.service                    alias           -
dm-event.service                           static          -
dnf-makecache.service                      static          -
dnf-system-upgrade-cleanup.service         static          -
dnf-system-upgrade.service                 disabled        disabled
dnsmasq.service                            disabled        disabled
dracut-cmdline.service                     static          -
dracut-initqueue.service                   static          -
dracut-mount.service                       static          -
dracut-pre-mount.service                   static          -
dracut-pre-pivot.service                   static          -
dracut-pre-trigger.service                 static          -
dracut-pre-udev.service                    static          -
dracut-shutdown-onfailure.service          static          -
dracut-shutdown.service                    static          -
emergency.service                          static          -
firewalld.service                          enabled         enabled
flatpak-system-helper.service              static          -
fprintd.service                            static          -
fstrim.service                             static          -
fwupd-offline-update.service               static          -
fwupd-refresh.service                      static          -
fwupd.service                              static          -
gdm.service                                enabled         enabled
geoclue.service                            static          -
getty@.service                             enabled         enabled
grub-boot-indeterminate.service            static          -
grub2-systemd-integration.service          static          -
hypervfcopyd.service                       static          -
hypervkvpd.service                         static          -
hypervvssd.service                         static          -
iio-sensor-proxy.service                   static          -
initrd-cleanup.service                     static          -
initrd-parse-etc.service                   static          -
initrd-switch-root.service                 static          -
initrd-udevadm-cleanup-db.service          static          -
iprdump.service                            disabled        disabled
iprinit.service                            disabled        disabled
iprupdate.service                          disabled        disabled
irqbalance.service                         enabled         enabled
iscsi-init.service                         static          -
iscsi-onboot.service                       enabled         enabled
iscsi-shutdown.service                     static          -
iscsi.service                              enabled         enabled
iscsid.service                             disabled        disabled
iscsiuio.service                           disabled        disabled
kdump.service                              enabled         enabled
kmod-static-nodes.service                  static          -
kpatch.service                             disabled        disabled
kvm_stat.service                           disabled        disabled
ldconfig.service                           static          -
ledmon.service                             disabled        disabled
libstoragemgmt.service                     enabled         enabled
logrotate.service                          static          -
low-memory-monitor.service                 enabled         enabled
lvm2-lvmpolld.service                      static          -
lvm2-monitor.service                       enabled         enabled
man-db-cache-update.service                static          -
man-db-restart-cache-update.service        disabled        disabled
mcelog.service                             enabled         enabled
mdadm-grow-continue@.service               static          -
mdadm-last-resort@.service                 static          -
mdcheck_continue.service                   static          -
mdcheck_start.service                      static          -
mdmon@.service                             static          -
mdmonitor-oneshot.service                  static          -
mdmonitor.service                          enabled         enabled
microcode.service                          enabled         enabled
mlocate-updatedb.service                   static          -
ModemManager.service                       enabled         enabled
modprobe@.service                          static          -
multipathd.service                         enabled         enabled
NetworkManager-dispatcher.service          enabled         enabled
NetworkManager-wait-online.service         enabled         disabled
NetworkManager.service                     enabled         enabled
nftables.service                           disabled        disabled
nis-domainname.service                     enabled         enabled
nm-priv-helper.service                     static          -
nvmefc-boot-connections.service            enabled         enabled
nvmf-autoconnect.service                   disabled        disabled
nvmf-connect@.service                      static          -
ostree-boot-complete.service               static          -
ostree-finalize-staged-hold.service        static          -
ostree-finalize-staged.service             static          -
ostree-prepare-root.service                static          -
ostree-readonly-sysroot-migration.service  disabled        disabled
ostree-remount.service                     enabled         enabled
packagekit-offline-update.service          static          -
packagekit.service                         static          -
pam_namespace.service                      static          -
pesign.service                             disabled        disabled
plymouth-halt.service                      static          -
plymouth-kexec.service                     static          -
plymouth-poweroff.service                  static          -
plymouth-quit-wait.service                 static          -
plymouth-quit.service                      static          -
plymouth-read-write.service                static          -
plymouth-reboot.service                    static          -
plymouth-start.service                     static          -
plymouth-switch-root-initramfs.service     static          -
plymouth-switch-root.service               static          -
podman-auto-update.service                 disabled        disabled
podman-clean-transient.service             disabled        disabled
podman-kube@.service                       disabled        disabled
podman-restart.service                     disabled        disabled
podman.service                             disabled        disabled
polkit.service                             static          -
power-profiles-daemon.service              enabled         enabled
psacct.service                             disabled        disabled
qemu-guest-agent.service                   enabled         enabled
quotaon.service                            static          -
raid-check.service                         static          -
ras-mc-ctl.service                         disabled        disabled
rasdaemon.service                          disabled        disabled
rc-local.service                           static          -
rdisc.service                              disabled        disabled
realmd.service                             static          -
rescue.service                             static          -
rpmdb-rebuild.service                      disabled        disabled
rsyslog.service                            enabled         enabled
rtkit-daemon.service                       enabled         enabled
selinux-autorelabel-mark.service           enabled         enabled
selinux-autorelabel.service                static          -
selinux-check-proper-disable.service       disabled        disabled
serial-getty@.service                      disabled        disabled
setroubleshootd.service                    static          -
smartd.service                             enabled         enabled
speech-dispatcherd.service                 disabled        disabled
spice-vdagentd.service                     indirect        enabled
sshd-keygen@.service                       disabled        disabled
sshd.service                               enabled         enabled
sshd@.service                              static          -
sssd-autofs.service                        indirect        disabled
sssd-kcm.service                           indirect        disabled
sssd-nss.service                           indirect        disabled
sssd-pac.service                           indirect        disabled
sssd-pam.service                           indirect        disabled
sssd-ssh.service                           indirect        disabled
sssd-sudo.service                          indirect        disabled
sssd.service                               enabled         enabled
switcheroo-control.service                 enabled         enabled
system-update-cleanup.service              static          -
systemd-ask-password-console.service       static          -
systemd-ask-password-plymouth.service      static          -
systemd-ask-password-wall.service          static          -
systemd-backlight@.service                 static          -
systemd-binfmt.service                     static          -
systemd-bless-boot.service                 static          -
systemd-boot-check-no-failures.service     disabled        disabled
systemd-boot-system-token.service          static          -
systemd-boot-update.service                enabled         enabled
systemd-coredump@.service                  static          -
systemd-exit.service                       static          -
systemd-firstboot.service                  static          -
systemd-fsck-root.service                  static          -
systemd-fsck@.service                      static          -
systemd-halt.service                       static          -
systemd-hibernate-resume@.service          static          -
systemd-hibernate.service                  static          -
systemd-hostnamed.service                  static          -
systemd-hwdb-update.service                static          -
systemd-hybrid-sleep.service               static          -
systemd-initctl.service                    static          -
systemd-journal-catalog-update.service     static          -
systemd-journal-flush.service              static          -
systemd-journald.service                   static          -
systemd-journald@.service                  static          -
systemd-kexec.service                      static          -
systemd-localed.service                    static          -
systemd-logind.service                     static          -
systemd-machine-id-commit.service          static          -
systemd-modules-load.service               static          -
systemd-network-generator.service          enabled         enabled
systemd-pcrphase-initrd.service            static          -
systemd-pcrphase-sysinit.service           static          -
systemd-pcrphase.service                   static          -
systemd-poweroff.service                   static          -
systemd-pstore.service                     disabled        enabled
systemd-quotacheck.service                 static          -
systemd-random-seed.service                static          -
systemd-reboot.service                     static          -
systemd-remount-fs.service                 enabled-runtime disabled
systemd-repart.service                     static          -
systemd-rfkill.service                     static          -
systemd-suspend-then-hibernate.service     static          -
systemd-suspend.service                    static          -
systemd-sysctl.service                     static          -
systemd-sysext.service                     disabled        disabled
systemd-sysupdate-reboot.service           indirect        disabled
systemd-sysupdate.service                  indirect        disabled
systemd-sysusers.service                   static          -
systemd-timedated.service                  static          -
systemd-tmpfiles-clean.service             static          -
systemd-tmpfiles-setup-dev.service         static          -
systemd-tmpfiles-setup.service             static          -
systemd-udev-settle.service                static          -
systemd-udev-trigger.service               static          -
systemd-udevd.service                      static          -
systemd-update-done.service                static          -
systemd-update-utmp-runlevel.service       static          -
systemd-update-utmp.service                static          -
systemd-user-sessions.service              static          -
systemd-vconsole-setup.service             static          -
systemd-volatile-root.service              static          -
teamd@.service                             static          -
tuned.service                              enabled         enabled
udisks2.service                            enabled         enabled
upower.service                             enabled         enabled
usb_modeswitch@.service                    static          -
user-runtime-dir@.service                  static          -
user@.service                              static          -
vgauthd.service                            enabled         disabled
vmtoolsd.service                           enabled         enabled
wacom-inputattach@.service                 static          -
wpa_supplicant.service                     disabled        disabled

259 unit files listed.
[root@host1 ~]#
```
