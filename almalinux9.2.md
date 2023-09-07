# AlmaLinux9.2

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

## インストールパッケージ一覧

※Guest Additions インストール済みの状態※  

```Shell
[root@host1 ~]#
[root@host1 ~]# rpm -qa | sort
ModemManager-1.20.2-1.el9.x86_64
ModemManager-glib-1.20.2-1.el9.x86_64
NetworkManager-1.42.2-1.el9.x86_64
NetworkManager-adsl-1.42.2-1.el9.x86_64
NetworkManager-bluetooth-1.42.2-1.el9.x86_64
NetworkManager-config-server-1.42.2-1.el9.noarch
NetworkManager-libnm-1.42.2-1.el9.x86_64
NetworkManager-team-1.42.2-1.el9.x86_64
NetworkManager-tui-1.42.2-1.el9.x86_64
NetworkManager-wifi-1.42.2-1.el9.x86_64
NetworkManager-wwan-1.42.2-1.el9.x86_64
PackageKit-1.2.4-2.el9.x86_64
PackageKit-command-not-found-1.2.4-2.el9.x86_64
PackageKit-glib-1.2.4-2.el9.x86_64
PackageKit-gstreamer-plugin-1.2.4-2.el9.x86_64
PackageKit-gtk3-module-1.2.4-2.el9.x86_64
aardvark-dns-1.5.0-2.el9.x86_64
abattis-cantarell-fonts-0.301-4.el9.noarch
accountsservice-0.6.55-10.el9.x86_64
accountsservice-libs-0.6.55-10.el9.x86_64
acl-2.3.1-3.el9.x86_64
adcli-0.9.2-1.el9.x86_64
adobe-mappings-cmap-20171205-12.el9.noarch
adobe-mappings-cmap-deprecated-20171205-12.el9.noarch
adobe-mappings-pdf-20180407-10.el9.noarch
adobe-source-code-pro-fonts-2.030.1.050-12.el9.1.noarch
adwaita-cursor-theme-40.1.1-3.el9.noarch
adwaita-gtk2-theme-3.28-14.el9.x86_64
adwaita-icon-theme-40.1.1-3.el9.noarch
almalinux-backgrounds-90.5.1-1.1.el9.noarch
almalinux-gpg-keys-9.2-1.el9.x86_64
almalinux-indexhtml-9-2.el9.noarch
almalinux-logos-90.5.1-1.1.el9.x86_64
almalinux-release-9.2-1.el9.x86_64
almalinux-repos-9.2-1.el9.x86_64
alsa-lib-1.2.8-3.el9.x86_64
alsa-ucm-1.2.8-3.el9.noarch
alsa-utils-1.2.8-1.el9.x86_64
alternatives-1.20-2.el9.x86_64
annobin-11.05-1.el9.x86_64
anthy-unicode-1.0.0.20201109-9.el9.x86_64
appstream-0.15.5-2.el9.x86_64
appstream-data-9-20220302.el9_0.1.noarch
asciidoc-9.1.0-3.el9.noarch
at-3.1.23-11.el9.x86_64
at-spi2-atk-2.38.0-4.el9.x86_64
at-spi2-core-2.40.3-1.el9.x86_64
atk-2.36.0-5.el9.x86_64
atkmm-2.28.2-2.el9.x86_64
attr-2.5.1-3.el9.x86_64
audit-3.0.7-103.el9.x86_64
audit-libs-3.0.7-103.el9.x86_64
authselect-1.2.6-1.el9.x86_64
authselect-libs-1.2.6-1.el9.x86_64
autoconf-2.69-38.el9.noarch
automake-1.16.2-6.el9.noarch
avahi-0.8-12.el9.x86_64
avahi-glib-0.8-12.el9.x86_64
avahi-libs-0.8-12.el9.x86_64
baobab-40.0-3.el9.x86_64
basesystem-11-13.el9.noarch
bash-5.1.8-6.el9_1.x86_64
bash-completion-2.11-4.el9.noarch
bc-1.07.1-14.el9.x86_64
bind-libs-9.16.23-11.el9.x86_64
bind-license-9.16.23-11.el9.noarch
bind-utils-9.16.23-11.el9.x86_64
binutils-2.35.2-37.el9.x86_64
binutils-gold-2.35.2-37.el9.x86_64
bison-3.7.4-5.el9.x86_64
blktrace-1.2.0-19.el9.x86_64
bluez-5.64-2.el9.x86_64
bluez-libs-5.64-2.el9.x86_64
bluez-obexd-5.64-2.el9.x86_64
bolt-0.9.5-1.el9.x86_64
boost-filesystem-1.75.0-8.el9.x86_64
boost-regex-1.75.0-8.el9.x86_64
boost-system-1.75.0-8.el9.x86_64
boost-thread-1.75.0-8.el9.x86_64
bpftool-7.0.0-284.11.1.el9_2.x86_64
brlapi-0.8.2-4.el9.x86_64
brltty-6.3-4.el9.x86_64
bubblewrap-0.4.1-6.el9.x86_64
buildah-1.29.1-1.el9.x86_64
byacc-2.0.20210109-4.el9.x86_64
bzip2-1.0.8-8.el9.x86_64
bzip2-libs-1.0.8-8.el9.x86_64
c-ares-1.17.1-5.el9.x86_64
ca-certificates-2022.2.54-90.2.el9_0.noarch
cairo-1.17.4-7.el9.x86_64
cairo-gobject-1.17.4-7.el9.x86_64
cairomm-1.14.2-10.el9.x86_64
checkpolicy-3.5-1.el9.x86_64
cheese-3.38.0-6.el9.x86_64
cheese-libs-3.38.0-6.el9.x86_64
chrome-gnome-shell-10.1-14.el9.x86_64
chrony-4.3-1.el9.x86_64
clevis-18-110.el9.x86_64
clevis-luks-18-110.el9.x86_64
clutter-1.26.4-7.el9.x86_64
clutter-gst3-3.0.27-7.el9.x86_64
clutter-gtk-1.8.4-13.el9.x86_64
cockpit-286.1-1.el9.x86_64
cockpit-bridge-286.1-1.el9.x86_64
cockpit-packagekit-286.1-1.el9.noarch
cockpit-podman-63.1-1.el9.noarch
cockpit-storaged-286.1-1.el9.noarch
cockpit-system-286.1-1.el9.noarch
cockpit-ws-286.1-1.el9.x86_64
cogl-1.22.8-5.el9.x86_64
color-filesystem-1-28.el9.noarch
colord-1.4.5-4.el9.x86_64
colord-gtk-0.2.0-7.el9.x86_64
colord-libs-1.4.5-4.el9.x86_64
conmon-2.1.7-1.el9_2.x86_64
container-selinux-2.205.0-1.el9_2.noarch
containernetworking-plugins-1.2.0-1.el9.x86_64
containers-common-1-52.el9_2.x86_64
copy-jdk-configs-4.0-3.el9.noarch
coreutils-8.32-34.el9.x86_64
coreutils-common-8.32-34.el9.x86_64
cpio-2.13-16.el9.x86_64
cpp-11.3.1-4.3.el9.alma.x86_64
cracklib-2.9.6-27.el9.x86_64
cracklib-dicts-2.9.6-27.el9.x86_64
criu-3.17-4.el9.x86_64
criu-libs-3.17-4.el9.x86_64
cronie-1.5.7-8.el9.x86_64
cronie-anacron-1.5.7-8.el9.x86_64
crontabs-1.11-27.20190603git.el9_0.noarch
crun-1.8.1-1.el9.x86_64
crypto-policies-20221215-1.git9a18988.el9.noarch
crypto-policies-scripts-20221215-1.git9a18988.el9.noarch
cryptsetup-2.6.0-2.el9.x86_64
cryptsetup-libs-2.6.0-2.el9.x86_64
cups-2.3.3op2-16.el9.x86_64
cups-client-2.3.3op2-16.el9.x86_64
cups-filesystem-2.3.3op2-16.el9.noarch
cups-filters-1.28.7-11.el9.x86_64
cups-filters-libs-1.28.7-11.el9.x86_64
cups-ipptool-2.3.3op2-16.el9.x86_64
cups-libs-2.3.3op2-16.el9.x86_64
cups-pk-helper-0.2.6-14.el9.x86_64
curl-7.76.1-23.el9.x86_64
cyrus-sasl-gssapi-2.1.27-21.el9.x86_64
cyrus-sasl-lib-2.1.27-21.el9.x86_64
cyrus-sasl-plain-2.1.27-21.el9.x86_64
dbus-1.12.20-7.el9_1.x86_64
dbus-broker-28-7.el9.x86_64
dbus-common-1.12.20-7.el9_1.noarch
dbus-daemon-1.12.20-7.el9_1.x86_64
dbus-glib-0.110-13.el9.x86_64
dbus-libs-1.12.20-7.el9_1.x86_64
dbus-tools-1.12.20-7.el9_1.x86_64
dconf-0.40.0-6.el9.x86_64
dejavu-sans-fonts-2.37-18.el9.noarch
dejavu-sans-mono-fonts-2.37-18.el9.noarch
dejavu-serif-fonts-2.37-18.el9.noarch
desktop-file-utils-0.26-6.el9.x86_64
device-mapper-1.02.187-7.el9.x86_64
device-mapper-event-1.02.187-7.el9.x86_64
device-mapper-event-libs-1.02.187-7.el9.x86_64
device-mapper-libs-1.02.187-7.el9.x86_64
device-mapper-multipath-0.8.7-20.el9.x86_64
device-mapper-multipath-libs-0.8.7-20.el9.x86_64
device-mapper-persistent-data-0.9.0-13.el9.x86_64
diffstat-1.64-6.el9.x86_64
diffutils-3.7-12.el9.x86_64
dmidecode-3.3-7.el9.x86_64
dnf-4.14.0-5.el9_2.alma.noarch
dnf-data-4.14.0-5.el9_2.alma.noarch
dnf-plugins-core-4.3.0-5.el9_2.noarch
dnsmasq-2.85-6.el9.x86_64
docbook-dtds-1.0-79.el9.noarch
docbook-style-xsl-1.79.2-16.el9.noarch
dos2unix-7.4.2-4.el9.x86_64
dosfstools-4.2-3.el9.x86_64
dotconf-1.3-28.el9.x86_64
dracut-057-21.git20230214.el9.x86_64
dracut-config-rescue-057-21.git20230214.el9.x86_64
dracut-network-057-21.git20230214.el9.x86_64
dracut-squash-057-21.git20230214.el9.x86_64
dwz-0.14-3.el9.x86_64
dyninst-12.1.0-1.el9.x86_64
e2fsprogs-1.46.5-3.el9.x86_64
e2fsprogs-libs-1.46.5-3.el9.x86_64
ed-1.14.2-12.el9.x86_64
efi-srpm-macros-6-2.el9_0.0.1.noarch
efivar-libs-38-3.el9.x86_64
elfutils-0.188-3.el9.x86_64
elfutils-debuginfod-client-0.188-3.el9.x86_64
elfutils-default-yama-scope-0.188-3.el9.noarch
elfutils-devel-0.188-3.el9.x86_64
elfutils-libelf-0.188-3.el9.x86_64
elfutils-libelf-devel-0.188-3.el9.x86_64
elfutils-libs-0.188-3.el9.x86_64
emacs-filesystem-27.2-8.el9.noarch
enchant2-2.2.15-6.el9.x86_64
enscript-1.6.6-28.el9.x86_64
eog-40.3-2.el9.x86_64
espeak-ng-1.50-7.el9.x86_64
ethtool-5.16-1.el9.x86_64
evince-40.5-2.el9.x86_64
evince-libs-40.5-2.el9.x86_64
evince-nautilus-40.5-2.el9.x86_64
evince-previewer-40.5-2.el9.x86_64
evince-thumbnailer-40.5-2.el9.x86_64
evolution-data-server-3.40.4-6.el9.x86_64
evolution-data-server-langpacks-3.40.4-6.el9.noarch
exempi-2.6.0-0.2.20211007gite23c213.el9.x86_64
exiv2-0.27.5-2.el9.x86_64
exiv2-libs-0.27.5-2.el9.x86_64
expat-2.5.0-1.el9.x86_64
fdk-aac-free-2.0.0-8.el9.x86_64
file-5.39-12.el9.x86_64
file-libs-5.39-12.el9.x86_64
filesystem-3.16-2.el9.x86_64
findutils-4.8.0-5.el9.x86_64
firefox-102.10.0-1.el9_1.alma.x86_64
firewalld-1.2.1-1.el9.noarch
firewalld-filesystem-1.2.1-1.el9.noarch
flac-libs-1.3.3-10.el9.x86_64
flashrom-1.2-10.el9.x86_64
flatpak-1.12.7-2.el9.x86_64
flatpak-libs-1.12.7-2.el9.x86_64
flatpak-selinux-1.12.7-2.el9.noarch
flatpak-session-helper-1.12.7-2.el9.x86_64
flex-2.6.4-9.el9.x86_64
fontconfig-2.14.0-2.el9_1.x86_64
fonts-filesystem-2.0.5-7.el9.1.noarch
fonts-srpm-macros-2.0.5-7.el9.1.noarch
foomatic-4.0.13-19.el9.x86_64
foomatic-db-4.0-72.20210209.el9.noarch
foomatic-db-filesystem-4.0-72.20210209.el9.noarch
foomatic-db-ppds-4.0-72.20210209.el9.noarch
fprintd-1.94.0-3.el9.x86_64
fprintd-pam-1.94.0-3.el9.x86_64
freetype-2.10.4-9.el9.x86_64
fribidi-1.0.10-6.el9.2.x86_64
fstrm-0.6.1-3.el9.x86_64
fuse-2.9.9-15.el9.x86_64
fuse-common-3.10.2-5.el9.x86_64
fuse-libs-2.9.9-15.el9.x86_64
fuse-overlayfs-1.10-2.el9.x86_64
fuse3-3.10.2-5.el9.x86_64
fuse3-libs-3.10.2-5.el9.x86_64
fwupd-1.8.10-2.el9.alma.x86_64
fwupd-plugin-flashrom-1.8.10-2.el9.alma.x86_64
gawk-5.1.0-6.el9.x86_64
gawk-all-langpacks-5.1.0-6.el9.x86_64
gcc-11.3.1-4.3.el9.alma.x86_64
gcc-c++-11.3.1-4.3.el9.alma.x86_64
gcc-plugin-annobin-11.3.1-4.3.el9.alma.x86_64
gcr-3.40.0-3.el9.x86_64
gcr-base-3.40.0-3.el9.x86_64
gd-2.3.2-3.el9.x86_64
gdb-10.2-10.el9.x86_64
gdb-headless-10.2-10.el9.x86_64
gdbm-libs-1.19-4.el9.x86_64
gdisk-1.0.7-5.el9.x86_64
gdk-pixbuf2-2.42.6-3.el9.x86_64
gdk-pixbuf2-modules-2.42.6-3.el9.x86_64
gdm-40.1-21.el9.x86_64
gedit-40.0-6.el9.x86_64
geoclue2-2.6.0-7.el9.x86_64
geoclue2-libs-2.6.0-7.el9.x86_64
geocode-glib-3.26.2-5.el9.x86_64
gettext-0.21-7.el9.x86_64
gettext-common-devel-0.21-7.el9.noarch
gettext-devel-0.21-7.el9.x86_64
gettext-libs-0.21-7.el9.x86_64
ghc-srpm-macros-1.5.0-6.el9.noarch
ghostscript-9.54.0-9.el9.x86_64
ghostscript-tools-fonts-9.54.0-9.el9.x86_64
ghostscript-tools-printing-9.54.0-9.el9.x86_64
giflib-5.2.1-9.el9.x86_64
git-2.39.1-1.el9.x86_64
git-core-2.39.1-1.el9.x86_64
git-core-doc-2.39.1-1.el9.noarch
gjs-1.68.6-3.el9.x86_64
glib-networking-2.68.3-3.el9.x86_64
glib2-2.68.4-6.el9.x86_64
glibc-2.34-60.el9.x86_64
glibc-all-langpacks-2.34-60.el9.x86_64
glibc-common-2.34-60.el9.x86_64
glibc-devel-2.34-60.el9.x86_64
glibc-gconv-extra-2.34-60.el9.x86_64
glibc-headers-2.34-60.el9.x86_64
glibc-langpack-ja-2.34-60.el9.x86_64
glibmm24-2.66.1-1.el9.x86_64
glx-utils-8.4.0-12.20210504git0f9e7d9.el9.x86_64
gmp-6.2.0-10.el9.x86_64
gnome-autoar-0.4.1-2.el9.x86_64
gnome-bluetooth-3.34.5-3.el9.x86_64
gnome-bluetooth-libs-3.34.5-3.el9.x86_64
gnome-calculator-40.1-2.el9.x86_64
gnome-characters-40.0-3.el9.x86_64
gnome-classic-session-40.7-7.el9.noarch
gnome-color-manager-3.36.0-7.el9.x86_64
gnome-control-center-40.0-29.el9.x86_64
gnome-control-center-filesystem-40.0-29.el9.noarch
gnome-desktop3-40.4-1.el9.x86_64
gnome-disk-utility-40.2-2.el9.x86_64
gnome-font-viewer-40.0-3.el9.x86_64
gnome-initial-setup-40.4-3.el9.x86_64
gnome-keyring-40.0-3.el9.x86_64
gnome-keyring-pam-40.0-3.el9.x86_64
gnome-logs-3.36.0-8.el9.x86_64
gnome-menus-3.36.0-8.el9.x86_64
gnome-online-accounts-3.40.0-2.el9.x86_64
gnome-remote-desktop-40.0-7.el9.x86_64
gnome-screenshot-40.0-4.el9.x86_64
gnome-session-40.1.1-7.el9.x86_64
gnome-session-wayland-session-40.1.1-7.el9.x86_64
gnome-session-xsession-40.1.1-7.el9.x86_64
gnome-settings-daemon-40.0.1-10.el9.x86_64
gnome-shell-40.10-12.el9.x86_64
gnome-shell-extension-apps-menu-40.7-7.el9.noarch
gnome-shell-extension-background-logo-40.0~rc-4.el9.noarch
gnome-shell-extension-common-40.7-7.el9.noarch
gnome-shell-extension-desktop-icons-40.7-7.el9.noarch
gnome-shell-extension-launch-new-instance-40.7-7.el9.noarch
gnome-shell-extension-places-menu-40.7-7.el9.noarch
gnome-shell-extension-window-list-40.7-7.el9.noarch
gnome-software-41.5-2.el9.x86_64
gnome-system-monitor-40.1-3.el9.x86_64
gnome-terminal-3.40.3-1.el9.x86_64
gnome-terminal-nautilus-3.40.3-1.el9.x86_64
gnome-tour-40.1-2.el9.x86_64
gnome-user-docs-40.0-3.el9.noarch
gnome-video-effects-0.5.0-7.el9.noarch
gnupg2-2.3.3-2.el9_0.x86_64
gnutls-3.7.6-20.el9_2.x86_64
go-srpm-macros-3.2.0-1.el9.noarch
gobject-introspection-1.68.0-11.el9.x86_64
gom-0.4-6.el9.x86_64
google-droid-sans-fonts-20200215-11.el9.2.noarch
google-noto-cjk-fonts-common-20201206-4.el9.noarch
google-noto-emoji-color-fonts-20211102-1.el9.noarch
google-noto-fonts-common-20201206-4.el9.noarch
google-noto-sans-cjk-ttc-fonts-20201206-4.el9.noarch
google-noto-sans-gurmukhi-fonts-20201206-4.el9.noarch
google-noto-sans-sinhala-vf-fonts-20201206-4.el9.noarch
google-noto-serif-cjk-ttc-fonts-20201206-4.el9.noarch
gpgme-1.15.1-6.el9.x86_64
gpm-libs-1.20.7-29.el9.x86_64
graphene-1.10.6-2.el9.x86_64
graphite2-1.3.14-9.el9.x86_64
graphviz-2.44.0-25.el9.x86_64
grep-3.6-5.el9.x86_64
grilo-0.3.13-7.el9.x86_64
grilo-plugins-0.3.13-6.el9.x86_64
groff-base-1.22.4-10.el9.x86_64
grub2-common-2.06-61.el9.alma.noarch
grub2-pc-2.06-61.el9.alma.x86_64
grub2-pc-modules-2.06-61.el9.alma.noarch
grub2-tools-2.06-61.el9.alma.x86_64
grub2-tools-minimal-2.06-61.el9.alma.x86_64
grubby-8.40-63.el9.x86_64
gsettings-desktop-schemas-40.0-6.el9.x86_64
gsm-1.0.19-6.el9.x86_64
gsound-1.0.2-15.el9.x86_64
gspell-1.9.1-3.el9.x86_64
gstreamer1-1.18.4-4.el9.x86_64
gstreamer1-plugins-bad-free-1.18.4-6.el9.x86_64
gstreamer1-plugins-base-1.18.4-5.el9.x86_64
gstreamer1-plugins-good-1.18.4-6.el9.x86_64
gstreamer1-plugins-good-gtk-1.18.4-6.el9.x86_64
gstreamer1-plugins-ugly-free-1.18.4-3.el9.x86_64
gtk-update-icon-cache-3.24.31-2.el9.x86_64
gtk2-2.24.33-8.el9.x86_64
gtk3-3.24.31-2.el9.x86_64
gtk4-4.4.1-2.el9.x86_64
gtkmm30-3.24.5-1.el9.x86_64
gtksourceview4-4.8.1-5.el9.x86_64
gutenprint-5.3.4-4.el9.x86_64
gutenprint-cups-5.3.4-4.el9.x86_64
gutenprint-doc-5.3.4-4.el9.x86_64
gutenprint-libs-5.3.4-4.el9.x86_64
gvfs-1.48.1-4.el9.x86_64
gvfs-client-1.48.1-4.el9.x86_64
gvfs-fuse-1.48.1-4.el9.x86_64
gvfs-goa-1.48.1-4.el9.x86_64
gvfs-gphoto2-1.48.1-4.el9.x86_64
gvfs-mtp-1.48.1-4.el9.x86_64
gvfs-smb-1.48.1-4.el9.x86_64
gzip-1.12-1.el9.x86_64
harfbuzz-2.7.4-8.el9.x86_64
harfbuzz-icu-2.7.4-8.el9.x86_64
hdparm-9.62-2.el9.x86_64
hicolor-icon-theme-0.17-13.el9.noarch
highcontrast-icon-theme-3.28-14.el9.noarch
hostname-3.23-6.el9.x86_64
hplip-common-3.21.2-6.el9.alma.x86_64
hplip-libs-3.21.2-6.el9.alma.x86_64
hunspell-1.7.0-11.el9.x86_64
hunspell-en-US-0.20140811.1-20.el9.noarch
hunspell-filesystem-1.7.0-11.el9.x86_64
hwdata-0.348-9.7.el9.noarch
hyperv-daemons-0-0.41.20190303git.el9.x86_64
hyperv-daemons-license-0-0.41.20190303git.el9.noarch
hypervfcopyd-0-0.41.20190303git.el9.x86_64
hypervkvpd-0-0.41.20190303git.el9.x86_64
hypervvssd-0-0.41.20190303git.el9.x86_64
hyphen-2.8.8-17.el9.x86_64
ibus-1.5.25-2.el9.x86_64
ibus-anthy-1.5.13-1.el9.x86_64
ibus-anthy-python-1.5.13-1.el9.noarch
ibus-gtk2-1.5.25-2.el9.x86_64
ibus-gtk3-1.5.25-2.el9.x86_64
ibus-libs-1.5.25-2.el9.x86_64
ibus-setup-1.5.25-2.el9.noarch
iio-sensor-proxy-3.3-1.el9.x86_64
ima-evm-utils-1.4-4.el9.x86_64
info-6.7-15.el9.x86_64
inih-49-6.el9.x86_64
initscripts-rename-device-10.11.5-1.el9.x86_64
initscripts-service-10.11.5-1.el9.noarch
intltool-0.51.0-20.el9.noarch
iproute-6.1.0-1.el9.x86_64
iproute-tc-6.1.0-1.el9.x86_64
iprutils-2.4.19-5.el9.x86_64
ipset-7.11-8.el9.x86_64
ipset-libs-7.11-8.el9.x86_64
iptables-libs-1.8.8-6.el9_1.x86_64
iptables-nft-1.8.8-6.el9_1.x86_64
iputils-20210202-8.el9_1.1.x86_64
irqbalance-1.9.0-3.el9.x86_64
iscsi-initiator-utils-6.2.1.4-3.git2a8f9d8.el9.x86_64
iscsi-initiator-utils-iscsiuio-6.2.1.4-3.git2a8f9d8.el9.x86_64
isns-utils-libs-0.101-4.el9.x86_64
iso-codes-4.6.0-3.el9.noarch
itstool-2.0.6-7.el9.noarch
iw-5.9-4.el9.x86_64
iwl100-firmware-39.31.5.1-133.el9_2.noarch
iwl1000-firmware-39.31.5.1-133.el9_2.noarch
iwl105-firmware-18.168.6.1-133.el9_2.noarch
iwl135-firmware-18.168.6.1-133.el9_2.noarch
iwl2000-firmware-18.168.6.1-133.el9_2.noarch
iwl2030-firmware-18.168.6.1-133.el9_2.noarch
iwl3160-firmware-25.30.13.0-133.el9_2.noarch
iwl5000-firmware-8.83.5.1_1-133.el9_2.noarch
iwl5150-firmware-8.24.2.2-133.el9_2.noarch
iwl6000g2a-firmware-18.168.6.1-133.el9_2.noarch
iwl6000g2b-firmware-18.168.6.1-133.el9_2.noarch
iwl6050-firmware-41.28.5.1-133.el9_2.noarch
iwl7260-firmware-25.30.13.0-133.el9_2.noarch
jansson-2.14-1.el9.x86_64
java-1.8.0-openjdk-headless-1.8.0.372.b07-1.el9_1.x86_64
javapackages-filesystem-6.0.0-4.el9.noarch
jbig2dec-libs-0.19-7.el9.x86_64
jbigkit-libs-2.1-23.el9.x86_64
jna-5.6.0-8.el9.x86_64
jomolhari-fonts-0.003-34.el9.noarch
jose-11-3.el9.x86_64
jq-1.6-14.el9.x86_64
json-c-0.14-11.el9.x86_64
json-glib-1.6.6-1.el9.x86_64
julietaula-montserrat-fonts-7.210-6.el9.noarch
kasumi-common-2.5-39.el9.noarch
kasumi-unicode-2.5-39.el9.x86_64
kbd-2.4.0-8.el9.x86_64
kbd-misc-2.4.0-8.el9.noarch
kernel-5.14.0-284.11.1.el9_2.x86_64
kernel-core-5.14.0-284.11.1.el9_2.x86_64
kernel-devel-5.14.0-284.11.1.el9_2.x86_64
kernel-headers-5.14.0-284.11.1.el9_2.x86_64
kernel-modules-5.14.0-284.11.1.el9_2.x86_64
kernel-modules-core-5.14.0-284.11.1.el9_2.x86_64
kernel-srpm-macros-1.0-12.el9.noarch
kernel-tools-5.14.0-284.11.1.el9_2.x86_64
kernel-tools-libs-5.14.0-284.11.1.el9_2.x86_64
kexec-tools-2.0.25-13.el9_2.x86_64
keyutils-libs-1.6.3-1.el9.x86_64
khmer-os-system-fonts-5.0-36.el9.noarch
kmod-28-7.el9.x86_64
kmod-kvdo-8.2.1.6-75.el9_2.x86_64
kmod-libs-28-7.el9.x86_64
kpartx-0.8.7-20.el9.x86_64
kpatch-0.9.7-2.el9.noarch
kpatch-dnf-0.9.7_0.4-2.el9.noarch
krb5-libs-1.20.1-8.el9.x86_64
lame-libs-3.100-12.el9.x86_64
langpacks-core-font-en-3.0-16.el9.noarch
langpacks-core-font-ja-3.0-16.el9.noarch
langpacks-core-ja-3.0-16.el9.noarch
langpacks-ja-3.0-16.el9.noarch
lcms2-2.12-3.el9.x86_64
ledmon-0.96-5.el9.x86_64
less-590-1.el9_0.x86_64
libICE-1.0.10-8.el9.x86_64
libSM-1.2.3-10.el9.x86_64
libX11-1.7.0-7.el9.x86_64
libX11-common-1.7.0-7.el9.noarch
libX11-xcb-1.7.0-7.el9.x86_64
libXau-1.0.9-8.el9.x86_64
libXaw-1.0.13-19.el9.x86_64
libXcomposite-0.4.5-7.el9.x86_64
libXcursor-1.2.0-7.el9.x86_64
libXdamage-1.1.5-7.el9.x86_64
libXdmcp-1.1.3-8.el9.x86_64
libXext-1.3.4-8.el9.x86_64
libXfixes-5.0.3-16.el9.x86_64
libXfont2-2.0.3-12.el9.x86_64
libXft-2.3.3-8.el9.x86_64
libXi-1.7.10-8.el9.x86_64
libXinerama-1.1.4-10.el9.x86_64
libXmu-1.1.3-8.el9.x86_64
libXpm-3.5.13-8.el9_1.x86_64
libXrandr-1.5.2-8.el9.x86_64
libXrender-0.9.10-16.el9.x86_64
libXres-1.2.0-14.el9.x86_64
libXt-1.2.0-6.el9.x86_64
libXtst-1.2.3-16.el9.x86_64
libXv-1.0.11-16.el9.x86_64
libXxf86dga-1.1.5-8.el9.x86_64
libXxf86vm-1.1.4-18.el9.x86_64
liba52-0.7.4-42.el9.x86_64
libacl-2.3.1-3.el9.x86_64
libaio-0.3.111-13.el9.x86_64
libao-1.2.0-22.el9.x86_64
libappstream-glib-0.7.18-4.el9.x86_64
libarchive-3.5.3-4.el9.x86_64
libassuan-2.5.5-3.el9.x86_64
libasyncns-0.8-22.el9.x86_64
libatasmart-0.19-22.el9.x86_64
libatomic-11.3.1-4.3.el9.alma.x86_64
libattr-2.5.1-3.el9.x86_64
libbabeltrace-1.5.8-10.el9.x86_64
libbasicobjects-0.1.1-53.el9.x86_64
libblkid-2.37.4-10.el9.x86_64
libblockdev-2.28-4.el9.x86_64
libblockdev-crypto-2.28-4.el9.x86_64
libblockdev-fs-2.28-4.el9.x86_64
libblockdev-loop-2.28-4.el9.x86_64
libblockdev-lvm-2.28-4.el9.x86_64
libblockdev-mdraid-2.28-4.el9.x86_64
libblockdev-part-2.28-4.el9.x86_64
libblockdev-swap-2.28-4.el9.x86_64
libblockdev-utils-2.28-4.el9.x86_64
libbpf-1.0.0-2.el9.x86_64
libbrotli-1.0.9-6.el9.x86_64
libbytesize-2.5-3.el9.x86_64
libcanberra-0.30-26.el9.x86_64
libcanberra-gtk2-0.30-26.el9.x86_64
libcanberra-gtk3-0.30-26.el9.x86_64
libcap-2.48-8.el9.x86_64
libcap-ng-0.8.2-7.el9.x86_64
libcap-ng-python3-0.8.2-7.el9.x86_64
libcbor-0.7.0-5.el9.x86_64
libcdio-2.1.0-6.el9.x86_64
libcdio-paranoia-10.2+2.0.1-6.el9.x86_64
libcollection-0.7.0-53.el9.x86_64
libcom_err-1.46.5-3.el9.x86_64
libcomps-0.1.18-1.el9.x86_64
libconfig-1.7.2-9.el9.x86_64
libcurl-7.76.1-23.el9.x86_64
libdaemon-0.14-23.el9.x86_64
libdatrie-0.2.13-4.el9.x86_64
libdb-5.3.28-53.el9.x86_64
libdhash-0.5.0-53.el9.x86_64
libdmx-1.1.4-12.el9.x86_64
libdnf-0.69.0-3.el9_2.alma.x86_64
libdrm-2.4.114-1.el9.x86_64
libdvdnav-6.1.0-4.el9.x86_64
libdvdread-6.1.1-4.el9.x86_64
libeconf-0.4.1-2.el9.x86_64
libedit-3.1-37.20210216cvs.el9.x86_64
libepoxy-1.5.5-4.el9.x86_64
liberation-fonts-common-2.1.3-4.el9.noarch
liberation-mono-fonts-2.1.3-4.el9.noarch
liberation-sans-fonts-2.1.3-4.el9.noarch
liberation-serif-fonts-2.1.3-4.el9.noarch
libertas-sd8787-firmware-20230310-133.el9_2.noarch
libestr-0.1.11-4.el9.x86_64
libevdev-1.11.0-3.el9.x86_64
libevent-2.1.12-6.el9.x86_64
libexif-0.6.22-6.el9.x86_64
libfastjson-0.99.9-3.el9.x86_64
libfdisk-2.37.4-10.el9.x86_64
libffi-3.4.2-7.el9.x86_64
libfido2-1.6.0-7.el9.x86_64
libfontenc-1.1.3-17.el9.x86_64
libfprint-1.94.5-1.el9.x86_64
libgcab1-1.4-6.el9.x86_64
libgcc-11.3.1-4.3.el9.alma.x86_64
libgcrypt-1.10.0-10.el9_1.x86_64
libgdata-0.18.1-4.el9.x86_64
libgee-0.20.4-3.el9.x86_64
libgexiv2-0.12.3-1.el9.x86_64
libglvnd-1.3.4-1.el9.x86_64
libglvnd-egl-1.3.4-1.el9.x86_64
libglvnd-gles-1.3.4-1.el9.x86_64
libglvnd-glx-1.3.4-1.el9.x86_64
libglvnd-opengl-1.3.4-1.el9.x86_64
libgnomekbd-3.26.1-7.el9.x86_64
libgomp-11.3.1-4.3.el9.alma.x86_64
libgpg-error-1.42-5.el9.x86_64
libgphoto2-2.5.27-3.el9.x86_64
libgs-9.54.0-9.el9.x86_64
libgsf-1.14.47-5.el9.x86_64
libgtop2-2.40.0-9.el9.x86_64
libgudev-237-1.el9.x86_64
libgusb-0.3.8-1.el9.x86_64
libgweather-40.0-3.el9.x86_64
libgxps-0.3.2-3.el9.x86_64
libhandy-1.2.3-1.el9.x86_64
libibverbs-44.0-2.el9.x86_64
libical-3.0.14-1.el9.x86_64
libical-glib-3.0.14-1.el9.x86_64
libicu-67.1-9.el9.x86_64
libidn2-2.3.0-7.el9.x86_64
libieee1284-0.2.11-37.el9.x86_64
libijs-0.35-15.el9.x86_64
libini_config-1.3.1-53.el9.x86_64
libinput-1.19.3-3.el9.x86_64
libipa_hbac-2.8.2-2.el9.x86_64
libipt-2.0.4-5.el9.x86_64
libiptcdata-1.0.5-9.el9.x86_64
libjcat-0.1.6-3.el9.x86_64
libjose-11-3.el9.x86_64
libjpeg-turbo-2.0.90-6.el9_1.x86_64
libkcapi-1.3.1-3.el9.x86_64
libkcapi-hmaccalc-1.3.1-3.el9.x86_64
libksba-1.5.1-6.el9_1.x86_64
libldac-2.0.2.3-10.el9.x86_64
libldb-2.6.1-1.el9.x86_64
liblouis-3.16.1-4.el9.x86_64
libluksmeta-9-12.el9.x86_64
libmaxminddb-1.5.2-3.el9.x86_64
libmbim-1.28.2-2.el9.x86_64
libmbim-utils-1.28.2-2.el9.x86_64
libmediaart-1.9.5-2.el9.x86_64
libmnl-1.0.4-15.el9.x86_64
libmodulemd-2.13.0-2.el9.x86_64
libmount-2.37.4-10.el9.x86_64
libmpc-1.2.1-4.el9.x86_64
libmpeg2-0.5.1-24.el9.x86_64
libmspack-0.10.1-0.7.alpha.el9.x86_64
libmtp-1.1.18-6.el9.x86_64
libndp-1.8-4.el9.x86_64
libnet-1.2-6.el9.x86_64
libnetfilter_conntrack-1.0.9-1.el9.x86_64
libnfnetlink-1.0.1-21.el9.x86_64
libnftnl-1.2.2-1.el9.x86_64
libnghttp2-1.43.0-5.el9.x86_64
libnl3-3.7.0-1.el9.x86_64
libnl3-cli-3.7.0-1.el9.x86_64
libnma-1.8.40-1.el9.x86_64
libnotify-0.7.9-8.el9.x86_64
libnvme-1.2-2.el9.x86_64
libogg-1.3.4-6.el9.x86_64
libosinfo-1.10.0-1.el9.x86_64
libpaper-1.1.28-4.el9.x86_64
libpath_utils-0.2.1-53.el9.x86_64
libpcap-1.10.0-4.el9.x86_64
libpciaccess-0.16-6.el9.x86_64
libpeas-1.30.0-4.el9.x86_64
libpeas-gtk-1.30.0-4.el9.x86_64
libpeas-loader-python3-1.30.0-4.el9.x86_64
libpipeline-1.5.3-4.el9.x86_64
libpkgconf-1.7.3-10.el9.x86_64
libpng-1.6.37-12.el9.x86_64
libproxy-0.4.15-35.el9.x86_64
libproxy-webkitgtk4-0.4.15-35.el9.x86_64
libpsl-0.21.1-5.el9.x86_64
libpwquality-1.4.4-8.el9.x86_64
libqmi-1.32.2-1.el9.x86_64
libqmi-utils-1.32.2-1.el9.x86_64
libqrtr-glib-1.2.2-1.el9.x86_64
libref_array-0.1.5-53.el9.x86_64
librelp-1.10.0-4.el9.x86_64
librepo-1.14.5-1.el9.x86_64
libreport-filesystem-2.15.2-6.el9.alma.noarch
librsvg2-2.50.7-1.el9.x86_64
librsvg2-tools-2.50.7-1.el9.x86_64
libsamplerate-0.1.9-10.el9.x86_64
libsane-airscan-0.99.24-3.el9.x86_64
libsane-hpaio-3.21.2-6.el9.alma.x86_64
libsbc-1.4-9.el9.x86_64
libseccomp-2.5.2-2.el9.x86_64
libsecret-0.20.4-4.el9.x86_64
libselinux-3.5-1.el9.x86_64
libselinux-utils-3.5-1.el9.x86_64
libsemanage-3.5-1.el9.x86_64
libsepol-3.5-1.el9.x86_64
libshout-2.4.3-7.el9.x86_64
libsigc++20-2.10.7-2.el9.x86_64
libsigsegv-2.13-4.el9.x86_64
libslirp-4.4.0-7.el9.x86_64
libsmartcols-2.37.4-10.el9.x86_64
libsmbclient-4.17.5-102.el9.x86_64
libsmbios-2.4.3-4.el9.x86_64
libsndfile-1.0.31-7.el9.x86_64
libsolv-0.7.22-4.el9.x86_64
libsoup-2.72.0-8.el9.x86_64
libspectre-0.2.9-6.el9.x86_64
libsrtp-2.3.0-7.el9.x86_64
libss-1.46.5-3.el9.x86_64
libssh-0.10.4-8.el9.x86_64
libssh-config-0.10.4-8.el9.noarch
libsss_certmap-2.8.2-2.el9.x86_64
libsss_idmap-2.8.2-2.el9.x86_64
libsss_nss_idmap-2.8.2-2.el9.x86_64
libsss_sudo-2.8.2-2.el9.x86_64
libstdc++-11.3.1-4.3.el9.alma.x86_64
libstdc++-devel-11.3.1-4.3.el9.alma.x86_64
libstemmer-0-18.585svn.el9.x86_64
libstoragemgmt-1.9.5-1.el9.x86_64
libsysfs-2.1.1-10.el9.x86_64
libtalloc-2.3.4-1.el9.x86_64
libtasn1-4.16.0-8.el9_1.x86_64
libtdb-1.4.7-1.el9.x86_64
libteam-1.31-16.el9_1.x86_64
libtevent-0.13.0-1.el9.x86_64
libthai-0.1.28-8.el9.x86_64
libtheora-1.1.1-31.el9.x86_64
libtiff-4.4.0-7.el9.x86_64
libtirpc-1.3.3-1.el9.x86_64
libtool-2.4.6-45.el9.x86_64
libtool-ltdl-2.4.6-45.el9.x86_64
libtracker-sparql-3.1.2-3.el9_1.x86_64
libudisks2-2.9.4-7.el9.x86_64
libunistring-0.9.10-15.el9.x86_64
libusbx-1.0.26-1.el9.x86_64
libuser-0.63-12.el9.x86_64
libutempter-1.2.1-6.el9.x86_64
libuuid-2.37.4-10.el9.x86_64
libuv-1.42.0-1.el9.x86_64
libv4l-1.20.0-5.el9.x86_64
libverto-0.3.2-3.el9.x86_64
libvisual-0.4.0-34.el9.x86_64
libvorbis-1.3.7-5.el9.x86_64
libvpx-1.9.0-5.el9.x86_64
libwacom-1.12.1-2.el9.x86_64
libwacom-data-1.12.1-2.el9.noarch
libwayland-client-1.21.0-1.el9.x86_64
libwayland-cursor-1.21.0-1.el9.x86_64
libwayland-egl-1.21.0-1.el9.x86_64
libwayland-server-1.21.0-1.el9.x86_64
libwbclient-4.17.5-102.el9.x86_64
libwebp-1.2.0-6.el9_1.x86_64
libwnck3-40.0-2.el9.x86_64
libwpe-1.10.0-4.el9.x86_64
libxcb-1.13.1-9.el9.x86_64
libxcrypt-4.4.18-3.el9.x86_64
libxcrypt-compat-4.4.18-3.el9.x86_64
libxcrypt-devel-4.4.18-3.el9.x86_64
libxkbcommon-1.0.3-4.el9.x86_64
libxkbcommon-x11-1.0.3-4.el9.x86_64
libxkbfile-1.1.0-8.el9.x86_64
libxklavier-5.4-20.el9.x86_64
libxml2-2.9.13-3.el9_1.x86_64
libxmlb-0.3.10-1.el9.x86_64
libxshmfence-1.3-10.el9.x86_64
libxslt-1.1.34-9.el9.x86_64
libyaml-0.2.5-7.el9.x86_64
libzstd-1.5.1-2.el9.x86_64
libzstd-devel-1.5.1-2.el9.x86_64
linux-firmware-20230310-133.el9_2.noarch
linux-firmware-whence-20230310-133.el9_2.noarch
lksctp-tools-1.0.19-2.el9.x86_64
llvm-libs-15.0.7-1.el9.x86_64
lmdb-libs-0.9.29-3.el9.x86_64
lockdev-1.0.4-0.37.20111007git.el9.x86_64
logrotate-3.18.0-8.el9.x86_64
lohit-assamese-fonts-2.91.5-13.el9.noarch
lohit-bengali-fonts-2.91.5-13.el9.noarch
lohit-devanagari-fonts-2.95.4-14.el9.noarch
lohit-gujarati-fonts-2.92.4-13.el9.noarch
lohit-kannada-fonts-2.5.4-12.el9.noarch
lohit-odia-fonts-2.91.2-13.el9.noarch
lohit-tamil-fonts-2.91.3-13.el9.noarch
lohit-telugu-fonts-2.5.5-12.el9.noarch
low-memory-monitor-2.1-4.el9.x86_64
lshw-B.02.19.2-9.el9.x86_64
lsof-4.94.0-3.el9.x86_64
lsscsi-0.32-6.el9.x86_64
ltrace-0.7.91-43.el9.x86_64
lua-5.4.4-3.el9.x86_64
lua-libs-5.4.4-3.el9.x86_64
lua-posix-35.0-8.el9.x86_64
lua-srpm-macros-1-6.el9.noarch
luksmeta-9-12.el9.x86_64
lvm2-2.03.17-7.el9.x86_64
lvm2-libs-2.03.17-7.el9.x86_64
lz4-libs-1.9.3-5.el9.x86_64
lzo-2.10-7.el9.x86_64
m4-1.4.19-1.el9.x86_64
mailcap-2.1.49-5.el9.noarch
make-4.3-7.el9.x86_64
mallard-rng-1.1.0-7.el9.noarch
man-db-2.9.3-7.el9.x86_64
man-pages-5.10-6.el9.noarch
man-pages-overrides-9.0.0.0-1.el9.noarch
mcelog-189-0.el9.x86_64
mdadm-4.2-8.el9.x86_64
mesa-dri-drivers-22.3.0-2.el9.x86_64
mesa-filesystem-22.3.0-2.el9.x86_64
mesa-libEGL-22.3.0-2.el9.x86_64
mesa-libGL-22.3.0-2.el9.x86_64
mesa-libgbm-22.3.0-2.el9.x86_64
mesa-libglapi-22.3.0-2.el9.x86_64
mesa-libxatracker-22.3.0-2.el9.x86_64
mesa-vulkan-drivers-22.3.0-2.el9.x86_64
microcode_ctl-20220809-2.el9.noarch
mkfontscale-1.2.1-3.el9.x86_64
mlocate-0.26-30.el9.x86_64
mobile-broadband-provider-info-20210805-2.el9.noarch
mokutil-0.6.0-4.el9.x86_64
mozilla-filesystem-1.9-30.el9.x86_64
mpfr-4.1.0-7.el9.x86_64
mpg123-libs-1.26.2-5.el9.x86_64
mtdev-1.1.5-22.el9.x86_64
mtr-0.94-4.el9.x86_64
mutter-40.9-14.el9.x86_64
nano-5.6.1-5.el9.x86_64
nautilus-40.2-11.el9.x86_64
nautilus-extensions-40.2-11.el9.x86_64
ncurses-6.2-8.20210508.el9.x86_64
ncurses-base-6.2-8.20210508.el9.noarch
ncurses-libs-6.2-8.20210508.el9.x86_64
net-snmp-libs-5.9.1-9.el9.x86_64
net-tools-2.0-0.62.20160912git.el9.x86_64
netavark-1.5.0-2.el9.x86_64
netronome-firmware-20230310-133.el9_2.noarch
nettle-3.8-3.el9_0.x86_64
newt-0.52.21-11.el9.x86_64
nftables-1.0.4-10.el9_1.x86_64
nm-connection-editor-1.26.0-2.el9.x86_64
nmap-ncat-7.91-12.el9.x86_64
npth-1.6-8.el9.x86_64
nspr-4.34.0-18.el9_1.x86_64
nss-3.79.0-18.el9_1.x86_64
nss-softokn-3.79.0-18.el9_1.x86_64
nss-softokn-freebl-3.79.0-18.el9_1.x86_64
nss-sysinit-3.79.0-18.el9_1.x86_64
nss-tools-3.79.0-18.el9_1.x86_64
nss-util-3.79.0-18.el9_1.x86_64
numactl-libs-2.0.14-9.el9.x86_64
nvme-cli-2.2.1-2.el9.x86_64
ocaml-srpm-macros-6-6.el9.noarch
oniguruma-6.9.6-1.el9.5.x86_64
open-vm-tools-12.1.5-1.el9.x86_64
open-vm-tools-desktop-12.1.5-1.el9.x86_64
openblas-srpm-macros-2-11.el9.noarch
openjpeg2-2.4.0-7.el9.x86_64
openldap-2.6.2-3.el9.x86_64
openldap-compat-2.6.2-3.el9.x86_64
openssh-8.7p1-28.el9.x86_64
openssh-clients-8.7p1-28.el9.x86_64
openssh-server-8.7p1-28.el9.x86_64
openssl-3.0.7-6.el9_2.x86_64
openssl-devel-3.0.7-6.el9_2.x86_64
openssl-libs-3.0.7-6.el9_2.x86_64
opus-1.3.1-10.el9.x86_64
orc-0.4.31-6.el9.x86_64
orca-40.3-1.el9.noarch
os-prober-1.77-10.el9.x86_64
osinfo-db-20221130-1.el9.noarch
osinfo-db-tools-1.10.0-1.el9.x86_64
ostree-2022.6-3.el9.x86_64
ostree-libs-2022.6-3.el9.x86_64
p11-kit-0.24.1-2.el9.x86_64
p11-kit-server-0.24.1-2.el9.x86_64
p11-kit-trust-0.24.1-2.el9.x86_64
paktype-naskh-basic-fonts-5.0-6.el9.noarch
pam-1.5.1-14.el9.x86_64
pango-1.48.7-3.el9.x86_64
pangomm-2.46.1-1.el9.x86_64
paps-0.7.1-4.el9.x86_64
parted-3.5-2.el9.x86_64
passwd-0.80-12.el9.x86_64
patch-2.7.6-16.el9.x86_64
patchutils-0.4.2-7.el9.x86_64
pcaudiolib-1.1-9.el9.x86_64
pciutils-3.7.0-5.el9.x86_64
pciutils-libs-3.7.0-5.el9.x86_64
pcre-8.44-3.el9.3.x86_64
pcre2-10.40-2.el9.x86_64
pcre2-syntax-10.40-2.el9.noarch
pcre2-utf32-10.40-2.el9.x86_64
perl-AutoLoader-5.74-480.el9.noarch
perl-B-1.80-480.el9.x86_64
perl-Carp-1.50-460.el9.noarch
perl-Class-Struct-0.66-480.el9.noarch
perl-DBD-SQLite-1.66-5.el9.x86_64
perl-DBI-1.643-9.el9.x86_64
perl-Data-Dumper-2.174-462.el9.x86_64
perl-Digest-1.19-4.el9.noarch
perl-Digest-MD5-2.58-4.el9.x86_64
perl-DynaLoader-1.47-480.el9.x86_64
perl-Encode-3.08-462.el9.x86_64
perl-Errno-1.30-480.el9.x86_64
perl-Error-0.17029-7.el9.noarch
perl-Exporter-5.74-461.el9.noarch
perl-Fcntl-1.13-480.el9.x86_64
perl-Fedora-VSP-0.001-23.el9.noarch
perl-File-Basename-2.85-480.el9.noarch
perl-File-Compare-1.100.600-480.el9.noarch
perl-File-Copy-2.34-480.el9.noarch
perl-File-Find-1.37-480.el9.noarch
perl-File-Path-2.18-4.el9.noarch
perl-File-Temp-0.231.100-4.el9.noarch
perl-File-stat-1.09-480.el9.noarch
perl-FileHandle-2.03-480.el9.noarch
perl-Getopt-Long-2.52-4.el9.noarch
perl-Getopt-Std-1.12-480.el9.noarch
perl-Git-2.39.1-1.el9.noarch
perl-HTTP-Tiny-0.076-460.el9.noarch
perl-IO-1.43-480.el9.x86_64
perl-IO-Socket-IP-0.41-5.el9.noarch
perl-IO-Socket-SSL-2.073-1.el9.noarch
perl-IPC-Open3-1.21-480.el9.noarch
perl-MIME-Base64-3.16-4.el9.x86_64
perl-Math-BigInt-1.9998.18-460.el9.noarch
perl-Math-Complex-1.59-480.el9.noarch
perl-Mozilla-CA-20200520-6.el9.noarch
perl-NDBM_File-1.15-480.el9.x86_64
perl-Net-SSLeay-1.92-2.el9.x86_64
perl-POSIX-1.94-480.el9.x86_64
perl-PathTools-3.78-461.el9.x86_64
perl-Pod-Escapes-1.07-460.el9.noarch
perl-Pod-Perldoc-3.28.01-461.el9.noarch
perl-Pod-Simple-3.42-4.el9.noarch
perl-Pod-Usage-2.01-4.el9.noarch
perl-Scalar-List-Utils-1.56-461.el9.x86_64
perl-SelectSaver-1.02-480.el9.noarch
perl-Socket-2.031-4.el9.x86_64
perl-Storable-3.21-460.el9.x86_64
perl-Symbol-1.08-480.el9.noarch
perl-Term-ANSIColor-5.01-461.el9.noarch
perl-Term-Cap-1.17-460.el9.noarch
perl-TermReadKey-2.38-11.el9.x86_64
perl-Text-ParseWords-3.30-460.el9.noarch
perl-Text-Tabs+Wrap-2013.0523-460.el9.noarch
perl-Thread-Queue-3.14-460.el9.noarch
perl-Time-Local-1.300-7.el9.noarch
perl-URI-5.09-3.el9.noarch
perl-XML-Parser-2.46-9.el9.x86_64
perl-base-2.27-480.el9.noarch
perl-constant-1.33-461.el9.noarch
perl-generators-1.11-12.el9.noarch
perl-if-0.60.800-480.el9.noarch
perl-interpreter-5.32.1-480.el9.x86_64
perl-lib-0.65-480.el9.x86_64
perl-libnet-3.13-4.el9.noarch
perl-libs-5.32.1-480.el9.x86_64
perl-locale-1.09-480.el9.noarch
perl-macros-5.32.1-480.el9.noarch
perl-mro-1.23-480.el9.x86_64
perl-overload-1.31-480.el9.noarch
perl-overloading-0.02-480.el9.noarch
perl-parent-0.238-460.el9.noarch
perl-podlators-4.14-460.el9.noarch
perl-srpm-macros-1-41.el9.noarch
perl-subs-1.03-480.el9.noarch
perl-threads-2.25-460.el9.x86_64
perl-threads-shared-1.61-460.el9.x86_64
perl-vars-1.05-480.el9.noarch
perl-version-0.99.28-4.el9.x86_64
pesign-115-6.el9_1.x86_64
pigz-2.5-4.el9.x86_64
pinentry-1.1.1-8.el9.x86_64
pinentry-gnome3-1.1.1-8.el9.x86_64
pinfo-0.6.10-29.el9.x86_64
pipewire-0.3.47-2.el9_0.x86_64
pipewire-alsa-0.3.47-2.el9_0.x86_64
pipewire-gstreamer-0.3.47-2.el9_0.x86_64
pipewire-jack-audio-connection-kit-0.3.47-2.el9_0.x86_64
pipewire-libs-0.3.47-2.el9_0.x86_64
pipewire-pulseaudio-0.3.47-2.el9_0.x86_64
pipewire-utils-0.3.47-2.el9_0.x86_64
pixman-0.40.0-5.el9.x86_64
pkgconf-1.7.3-10.el9.x86_64
pkgconf-m4-1.7.3-10.el9.noarch
pkgconf-pkg-config-1.7.3-10.el9.x86_64
plymouth-0.9.5-6.20210331git1ea1020.el9.x86_64
plymouth-core-libs-0.9.5-6.20210331git1ea1020.el9.x86_64
plymouth-graphics-libs-0.9.5-6.20210331git1ea1020.el9.x86_64
plymouth-plugin-label-0.9.5-6.20210331git1ea1020.el9.x86_64
plymouth-plugin-two-step-0.9.5-6.20210331git1ea1020.el9.x86_64
plymouth-scripts-0.9.5-6.20210331git1ea1020.el9.x86_64
plymouth-system-theme-0.9.5-6.20210331git1ea1020.el9.x86_64
plymouth-theme-spinner-0.9.5-6.20210331git1ea1020.el9.x86_64
pnm2ppa-1.04-52.el9.x86_64
podman-4.4.1-3.el9.x86_64
policycoreutils-3.5-1.el9.x86_64
policycoreutils-python-utils-3.5-1.el9.noarch
polkit-0.117-11.el9.x86_64
polkit-libs-0.117-11.el9.x86_64
polkit-pkla-compat-0.1-21.el9.x86_64
poppler-21.01.0-14.el9.x86_64
poppler-cpp-21.01.0-14.el9.x86_64
poppler-data-0.4.9-9.el9.noarch
poppler-glib-21.01.0-14.el9.x86_64
poppler-utils-21.01.0-14.el9.x86_64
popt-1.18-8.el9.x86_64
power-profiles-daemon-0.11.1-1.el9.x86_64
prefixdevname-0.1.0-8.el9.x86_64
procps-ng-3.3.17-11.el9.x86_64
protobuf-c-1.3.3-12.el9.x86_64
psacct-6.6.4-12.el9.x86_64
psmisc-23.4-3.el9.x86_64
pt-sans-fonts-20141121-23.el9.noarch
publicsuffix-list-dafsa-20210518-3.el9.noarch
pulseaudio-libs-15.0-2.el9.x86_64
pulseaudio-libs-glib2-15.0-2.el9.x86_64
pulseaudio-utils-15.0-2.el9.x86_64
pyproject-srpm-macros-1.6.2-1.el9.noarch
python-srpm-macros-3.9-52.el9.noarch
python-unversioned-command-3.9.16-1.el9.noarch
python3-3.9.16-1.el9.x86_64
python3-audit-3.0.7-103.el9.x86_64
python3-brlapi-0.8.2-4.el9.x86_64
python3-cairo-1.20.1-1.el9.x86_64
python3-chardet-4.0.0-5.el9.noarch
python3-cups-2.0.1-10.el9.x86_64
python3-dasbus-1.4-5.el9.noarch
python3-dateutil-2.8.1-6.el9.noarch
python3-dbus-1.2.18-2.el9.x86_64
python3-distro-1.5.0-7.el9.noarch
python3-dnf-4.14.0-5.el9_2.alma.noarch
python3-dnf-plugins-core-4.3.0-5.el9_2.noarch
python3-file-magic-5.39-12.el9.noarch
python3-firewall-1.2.1-1.el9.noarch
python3-gobject-3.40.1-6.el9.x86_64
python3-gobject-base-3.40.1-6.el9.x86_64
python3-gobject-base-noarch-3.40.1-6.el9.noarch
python3-gpg-1.15.1-6.el9.x86_64
python3-hawkey-0.69.0-3.el9_2.alma.x86_64
python3-idna-2.10-7.el9.noarch
python3-libcomps-0.1.18-1.el9.x86_64
python3-libdnf-0.69.0-3.el9_2.alma.x86_64
python3-libs-3.9.16-1.el9.x86_64
python3-libselinux-3.5-1.el9.x86_64
python3-libsemanage-3.5-1.el9.x86_64
python3-libstoragemgmt-1.9.5-1.el9.x86_64
python3-libxml2-2.9.13-3.el9_1.x86_64
python3-linux-procfs-0.7.1-1.el9.noarch
python3-louis-3.16.1-4.el9.noarch
python3-lxml-4.6.5-3.el9.x86_64
python3-nftables-1.0.4-10.el9_1.x86_64
python3-perf-5.14.0-284.11.1.el9_2.x86_64
python3-pexpect-4.8.0-7.el9.noarch
python3-pip-wheel-21.2.3-6.el9.noarch
python3-policycoreutils-3.5-1.el9.noarch
python3-psutil-5.8.0-12.el9.x86_64
python3-ptyprocess-0.6.0-12.el9.noarch
python3-pyatspi-2.38.1-3.el9.noarch
python3-pycurl-7.43.0.6-8.el9.x86_64
python3-pysocks-1.7.1-12.el9.noarch
python3-pyudev-0.22.0-6.el9.noarch
python3-pyyaml-5.4.1-6.el9.x86_64
python3-requests-2.25.1-6.el9.noarch
python3-rpm-4.16.1.3-22.el9.x86_64
python3-setools-4.4.1-1.el9.x86_64
python3-setuptools-53.0.0-12.el9.noarch
python3-setuptools-wheel-53.0.0-12.el9.noarch
python3-six-1.15.0-9.el9.noarch
python3-speechd-0.10.2-4.el9.x86_64
python3-systemd-234-18.el9.x86_64
python3-tracer-0.7.5-4.el9.noarch
python3-urllib3-1.26.5-3.el9.noarch
qemu-guest-agent-7.2.0-14.el9_2.x86_64
qpdf-libs-10.3.1-7.el9.x86_64
qt5-srpm-macros-5.15.3-1.el9.noarch
quota-4.06-6.el9.x86_64
quota-nls-4.06-6.el9.noarch
rasdaemon-0.6.7-8.el9.x86_64
readline-8.1-4.el9.x86_64
realmd-0.17.1-1.el9.x86_64
redhat-rpm-config-199-1.el9.alma.noarch
rest-0.8.1-11.el9.x86_64
rootfiles-8.1-31.el9.noarch
rpm-4.16.1.3-22.el9.x86_64
rpm-build-4.16.1.3-22.el9.x86_64
rpm-build-libs-4.16.1.3-22.el9.x86_64
rpm-libs-4.16.1.3-22.el9.x86_64
rpm-plugin-audit-4.16.1.3-22.el9.x86_64
rpm-plugin-selinux-4.16.1.3-22.el9.x86_64
rpm-plugin-systemd-inhibit-4.16.1.3-22.el9.x86_64
rpm-sign-4.16.1.3-22.el9.x86_64
rpm-sign-libs-4.16.1.3-22.el9.x86_64
rsync-3.2.3-19.el9.x86_64
rsyslog-8.2102.0-111.el9.x86_64
rsyslog-gnutls-8.2102.0-111.el9.x86_64
rsyslog-gssapi-8.2102.0-111.el9.x86_64
rsyslog-logrotate-8.2102.0-111.el9.x86_64
rsyslog-relp-8.2102.0-111.el9.x86_64
rtkit-0.11-28.el9.x86_64
rust-srpm-macros-17-4.el9.noarch
samba-client-libs-4.17.5-102.el9.x86_64
samba-common-4.17.5-102.el9.noarch
samba-common-libs-4.17.5-102.el9.x86_64
sane-airscan-0.99.24-3.el9.x86_64
sane-backends-1.0.32-7.el9.x86_64
sane-backends-drivers-cameras-1.0.32-7.el9.x86_64
sane-backends-drivers-scanners-1.0.32-7.el9.x86_64
sane-backends-libs-1.0.32-7.el9.x86_64
sed-4.8-9.el9.x86_64
selinux-policy-38.1.11-2.el9_2.noarch
selinux-policy-targeted-38.1.11-2.el9_2.noarch
setroubleshoot-plugins-3.3.14-4.el9.noarch
setroubleshoot-server-3.3.31-2.el9_2.x86_64
setup-2.13.7-9.el9.noarch
setxkbmap-1.3.2-5.el9.x86_64
sg3_utils-1.47-9.el9.x86_64
sg3_utils-libs-1.47-9.el9.x86_64
sgml-common-0.6.3-58.el9.noarch
shadow-utils-4.9-6.el9.x86_64
shadow-utils-subid-4.9-6.el9.x86_64
shared-mime-info-2.1-5.el9.x86_64
sil-abyssinica-fonts-1.200-23.el9.noarch
sil-nuosu-fonts-2.200-4.el9.noarch
sil-padauk-fonts-3.003-9.el9.noarch
slang-2.3.2-11.el9.x86_64
slirp4netns-1.2.0-3.el9.x86_64
smartmontools-7.2-6.el9.x86_64
smc-meera-fonts-7.0.3-5.el9.noarch
snappy-1.1.8-8.el9.x86_64
sos-4.5.1-3.el9_2.alma.noarch
sound-theme-freedesktop-0.8-17.el9.noarch
soundtouch-2.1.1-8.el9.x86_64
source-highlight-3.1.9-11.el9.x86_64
speech-dispatcher-0.10.2-4.el9.x86_64
speech-dispatcher-espeak-ng-0.10.2-4.el9.x86_64
speex-1.2.0-11.el9.x86_64
spice-vdagent-0.21.0-5.el9.x86_64
sqlite-libs-3.34.1-6.el9_1.x86_64
squashfs-tools-4.4-8.git1.el9.x86_64
sscg-3.0.0-7.el9.x86_64
sssd-2.8.2-2.el9.x86_64
sssd-ad-2.8.2-2.el9.x86_64
sssd-client-2.8.2-2.el9.x86_64
sssd-common-2.8.2-2.el9.x86_64
sssd-common-pac-2.8.2-2.el9.x86_64
sssd-ipa-2.8.2-2.el9.x86_64
sssd-kcm-2.8.2-2.el9.x86_64
sssd-krb5-2.8.2-2.el9.x86_64
sssd-krb5-common-2.8.2-2.el9.x86_64
sssd-ldap-2.8.2-2.el9.x86_64
sssd-proxy-2.8.2-2.el9.x86_64
startup-notification-0.12-23.el9.x86_64
stix-fonts-2.0.2-11.el9.noarch
strace-5.18-2.el9.x86_64
sudo-1.9.5p2-9.el9.x86_64
sushi-3.38.1-2.el9.x86_64
switcheroo-control-2.4-4.el9.x86_64
symlinks-1.7-6.el9.x86_64
system-config-printer-libs-1.5.15-4.el9.noarch
system-config-printer-udev-1.5.15-4.el9.x86_64
systemd-252-13.el9_2.x86_64
systemd-libs-252-13.el9_2.x86_64
systemd-pam-252-13.el9_2.x86_64
systemd-rpm-macros-252-13.el9_2.noarch
systemd-udev-252-13.el9_2.x86_64
systemtap-4.8-2.el9.x86_64
systemtap-client-4.8-2.el9.x86_64
systemtap-devel-4.8-2.el9.x86_64
systemtap-runtime-4.8-2.el9.x86_64
taglib-1.12-6.el9.x86_64
tar-1.34-6.el9_1.x86_64
tbb-2020.3-8.el9.x86_64
tcl-8.6.10-7.el9.x86_64
tcpdump-4.99.0-6.el9.x86_64
teamd-1.31-16.el9_1.x86_64
texlive-lib-20200406-25.el9.x86_64
thai-scalable-fonts-common-0.7.2-5.el9.noarch
thai-scalable-waree-fonts-0.7.2-5.el9.noarch
time-1.9-18.el9.x86_64
totem-3.38.2-1.el9.x86_64
totem-pl-parser-3.26.6-2.el9.x86_64
totem-video-thumbnailer-3.38.2-1.el9.x86_64
tpm2-tools-5.2-2.el9_1.x86_64
tpm2-tss-3.0.3-8.el9.x86_64
tracer-common-0.7.5-4.el9.noarch
tracker-3.1.2-3.el9_1.x86_64
tracker-miners-3.1.2-3.el9.x86_64
tree-1.8.0-10.el9.x86_64
tuned-2.20.0-1.el9.noarch
twolame-libs-0.3.13-19.el9.x86_64
tzdata-2023c-1.el9.noarch
tzdata-java-2023c-1.el9.noarch
udisks2-2.9.4-7.el9.x86_64
udisks2-iscsi-2.9.4-7.el9.x86_64
udisks2-lvm2-2.9.4-7.el9.x86_64
unzip-6.0-56.el9.x86_64
upower-0.99.13-2.el9.x86_64
urw-base35-bookman-fonts-20200910-6.el9.noarch
urw-base35-c059-fonts-20200910-6.el9.noarch
urw-base35-d050000l-fonts-20200910-6.el9.noarch
urw-base35-fonts-20200910-6.el9.noarch
urw-base35-fonts-common-20200910-6.el9.noarch
urw-base35-gothic-fonts-20200910-6.el9.noarch
urw-base35-nimbus-mono-ps-fonts-20200910-6.el9.noarch
urw-base35-nimbus-roman-fonts-20200910-6.el9.noarch
urw-base35-nimbus-sans-fonts-20200910-6.el9.noarch
urw-base35-p052-fonts-20200910-6.el9.noarch
urw-base35-standard-symbols-ps-fonts-20200910-6.el9.noarch
urw-base35-z003-fonts-20200910-6.el9.noarch
usb_modeswitch-2.6.1-4.el9.x86_64
usb_modeswitch-data-20191128-6.el9.noarch
usbutils-013-4.el9.x86_64
userspace-rcu-0.12.1-6.el9.x86_64
util-linux-2.37.4-10.el9.x86_64
util-linux-core-2.37.4-10.el9.x86_64
util-linux-user-2.37.4-10.el9.x86_64
valgrind-3.19.0-3.el9.x86_64
valgrind-devel-3.19.0-3.el9.x86_64
vdo-8.2.0.2-1.el9.x86_64
vim-common-8.2.2637-20.el9_1.x86_64
vim-enhanced-8.2.2637-20.el9_1.x86_64
vim-filesystem-8.2.2637-20.el9_1.noarch
vim-minimal-8.2.2637-20.el9_1.x86_64
virt-what-1.25-3.el9.x86_64
volume_key-libs-0.3.12-15.el9.x86_64
vte-profile-0.64.2-2.el9.x86_64
vte291-0.64.2-2.el9.x86_64
vulkan-loader-1.3.239.0-1.el9.x86_64
wavpack-5.4.0-5.el9.x86_64
webkit2gtk3-2.38.5-1.el9.x86_64
webkit2gtk3-jsc-2.38.5-1.el9.x86_64
webrtc-audio-processing-0.3.1-8.el9.x86_64
wget-1.21.1-7.el9.x86_64
which-2.21-28.el9.x86_64
wireless-regdb-2020.11.20-6.el9.noarch
wireplumber-0.4.8-1.el9.x86_64
wireplumber-libs-0.4.8-1.el9.x86_64
woff2-1.0.2-15.el9.x86_64
words-3.0-39.el9.noarch
wpa_supplicant-2.10-4.el9.x86_64
wpebackend-fdo-1.10.0-3.el9.x86_64
xcb-util-0.4.0-19.el9.x86_64
xdg-dbus-proxy-0.1.3-1.el9.x86_64
xdg-desktop-portal-1.12.4-1.el9.x86_64
xdg-desktop-portal-gnome-41.2-2.el9.x86_64
xdg-desktop-portal-gtk-1.12.0-3.el9.x86_64
xdg-user-dirs-0.17-10.el9.x86_64
xdg-user-dirs-gtk-0.10-22.el9.x86_64
xdg-utils-1.1.3-11.el9.noarch
xfsdump-3.1.10-1.el9.x86_64
xfsprogs-5.14.2-1.el9.x86_64
xkbcomp-1.4.4-4.el9.x86_64
xkeyboard-config-2.33-2.el9.noarch
xml-common-0.6.3-58.el9.noarch
xmlsec1-1.2.29-9.el9.x86_64
xmlsec1-openssl-1.2.29-9.el9.x86_64
xorg-x11-drv-evdev-2.10.6-12.el9.x86_64
xorg-x11-drv-fbdev-0.5.0-11.el9.x86_64
xorg-x11-drv-libinput-1.0.1-3.el9.x86_64
xorg-x11-drv-vmware-13.2.1-18.el9.x86_64
xorg-x11-drv-wacom-1.0.0-1.el9.x86_64
xorg-x11-drv-wacom-serial-support-1.0.0-1.el9.x86_64
xorg-x11-fonts-ISO8859-1-100dpi-7.5-33.el9.noarch
xorg-x11-server-Xorg-1.20.11-17.el9.x86_64
xorg-x11-server-Xwayland-21.1.3-7.el9.x86_64
xorg-x11-server-common-1.20.11-17.el9.x86_64
xorg-x11-server-utils-7.7-44.el9.x86_64
xorg-x11-utils-7.5-40.el9.x86_64
xorg-x11-xauth-1.1-10.el9.x86_64
xorg-x11-xinit-1.4.0-11.el9.x86_64
xorg-x11-xinit-session-1.4.0-11.el9.x86_64
xz-5.2.5-8.el9_0.x86_64
xz-devel-5.2.5-8.el9_0.x86_64
xz-libs-5.2.5-8.el9_0.x86_64
yajl-2.1.0-21.el9_0.x86_64
yelp-40.3-2.el9.x86_64
yelp-libs-40.3-2.el9.x86_64
yelp-tools-40.0-3.el9.noarch
yelp-xsl-40.2-1.el9.noarch
yum-4.14.0-5.el9_2.alma.noarch
zenity-3.32.0-8.el9.x86_64
zip-3.0-35.el9.x86_64
zlib-1.2.11-39.el9.x86_64
zlib-devel-1.2.11-39.el9.x86_64
zstd-1.5.1-2.el9.x86_64
[root@host1 ~]#
```

### コマンド一覧

```Shell
[root@host1 ~]#
[root@host1 ~]# echo $PATH
/root/.local/bin:/root/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin
[root@host1 ~]#
[root@host1 ~]# ls /root/.local/bin
ls: '/root/.local/bin' にアクセスできません: そのようなファイルやディレクトリはありません
[root@host1 ~]#
[root@host1 ~]# ls /root/bin
ls: '/root/bin' にアクセスできません: そのようなファイルやディレクトリはありません
[root@host1 ~]#
[root@host1 ~]# ls /usr/local/sbin/
[root@host1 ~]#
[root@host1 ~]# ls /usr/local/bin/
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