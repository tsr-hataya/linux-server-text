# linix-server-text

**目的**  
『[Linuxサーバー構築標準教科書](https://linuc.org/textbooks/server/)』の改訂するための情報提供をすること  


**環境**
- ホスト
  - Windows 10 Pro 22H2
  - VirtualBox 7.0.10
- ゲストOS
  - AlmaLinux 9.2


# 目次

## 共通事項

- [気がついたことを記録する雑多なメモ](/memo.md)
- [提案事項](/suggestions.md)
- [想定される構成パターン](/diagram.md)

## AlmaLinux9に関する情報

- [インストール画面のキャプチャ](/almalinux9.2_install.md)
- [インストールされるパッケージ一覧](/almalinux9.2_packagelist.md)
- [インストールされるコマンド一覧](/almalinux9.2_commandlist.md)
- [インストールされるコマンド一覧 GuestAddtionインストール後](/almalinux9.2_commandlist_GA.md)
- [OS情報](/almalinux9.2_osinfo.md)
- [SELinuxについて](/almalinux9.2_selinux.md)
- [Firewalldについて](/almalinux9.2_firewalld.md)
- [systemdについて](/almalinux9.2_systemd.md)
- [ネットワークについて](/almalinux9.2_network.md)
- [リポジトリについて](/almalinux9.2_repo.md)


## サーバー構築

- 第3章 DNSサーバーの構築
  - [3.6 講師マシンへのDNSキャッシュサーバーの設定](/section3.6_dns_unbound.md)
  - [3.7 受講者マシンへのDNSサーバーの設定](/section3.7_dns_bind.md)
  - [3.8 リゾルバの変更](/section3.8_dns_changeresolver.md)


- 第4章 WEBサーバーの構築


- 第5章 メールサーバーの構築
  - [5.4 Postfixのインストール](/section5.4_mail_postfix.md)
  - [5.5 アカウントの作成](/section5.5_mail_useradd.md)
  - [5.6 メールの送受信](/section5.6_mail_send.md)
  - [5.7 メールクライアントソフトでのメールの送受信](/section5.7_mail_send_mua.md)


- 第6章 ネットワークとセキュリティの管理
