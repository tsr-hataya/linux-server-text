# AlmaLinux9.2 メモ

## インストーラーの解像度が変更できない

CentOS7ではboot時のオプションに `resolution=1280x768` を追加することでインストーラーの解像度が変更できたが、AlmaLinux9.2ではこの方法が使えなかった。

 `inst.resolution=1280x768` とすれば良いという情報もあったが効果がなかった。


## 初期状態でpostfixがインストールされない

事前情報のとおり、OSインストール直後の初期状態で `postfix` がインストールされていなかった。
 
## SELinux無効化はコマンドでできる

CentOS7では設定ファイル(`/etc/sysconfig/selinux`)を編集して再起動をしていたが、AlmaLinux9(RHEL9系)では`grubby`コマンドで変更できる。

[almalinux9.2_selinux.md](/almalinux9.2_selinux.md)


## ドメインは example.jp か example.com が良いのでは？

インターネット上に `alpha.jp` や `beta.jp` が存在しないという保証はないので、例示用に使用が認められている `example.jp` や `example.com` が安心。

- [example.com - Wikipedia](https://ja.wikipedia.org/wiki/Example.com)
- [JPドメイン名の活用について | よくある質問 | JPRS](https://jprs.jp/faq/use/)
- [知らなかったでは済まされない!!よく見かけるexample.comのアドレスとは - Qiita](https://qiita.com/suzutsuki0220/items/4ad83ed2e2adbb6507a4)


## ホスト名とIPアドレスはリンクしたほうが良いのでは？

- 講師ホスト：192.168.1.**10** / host**10**.example.jp
- 受講者Aホスト：192.168.1.**101** / host**101**.example.jp
- 受講者Bホスト：192.168.1.**102** / host**102**.example.jp


## DNSサーバーのドメイン構成はサブドメインにしたほうが良いのでは？

- 講師ホスト：example.jp
- 受講者Aホスト：alpha.example.jp
- 受講者Bホスト：beta.example.jp


