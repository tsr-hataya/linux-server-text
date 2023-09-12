# 気がついたことを記録する雑多なメモ

## インストーラーの解像度が変更できない

CentOS7ではboot時のオプションに `resolution=1280x768` を追加することでインストーラーの解像度が変更できたが、AlmaLinux9.2ではこの方法が使えなかった。

 `inst.resolution=1280x768` とすれば良いという情報もあったが効果がなかった。


## 初期状態でpostfixがインストールされない

事前情報のとおり、OSインストール直後の初期状態で `postfix` がインストールされていなかった。


## SELinux無効化はコマンドでできる

CentOS7では設定ファイル(`/etc/sysconfig/selinux`)を編集して再起動をしていたが、AlmaLinux9(RHEL9系)では`grubby`コマンドで変更できる。

[almalinux9.2_selinux.md](/almalinux9.2_selinux.md)

