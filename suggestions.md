# 提案事項


## (solved)ドメインは example.jp か example.com が良いのでは？

**-----解決方法-----**  
`example.com` を使う  
https://github.com/lpi-japan/server-text/blob/main/Chapter4.md  
**-----**

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


## OSインストールの時点ではDNSは8.8.8.8などの名前解決ができるDNSにしておいたほうが良いのでは？

OSインストールの手順(P.20)ではDNSサーバーの設定を講師マシン(192.168.1.10)にすることになっているが、DNSの環境が整うまでは `8.8.8.8` や `8.8.4.4` など名前解決ができるDNSサーバーを設定しておかないとdnf(yum)が使えずにかなり面倒なことになる。  

もしくはインターネットに接続できないクローズな環境を前提としてリポジトリをDVDメディアにするような記述が良いかもしれない。  
└> DVDメディアにないパッケージをインストールしようとすると面倒かも・・  

講師マシンは事前に構築しておき名前解決ができるようにしておくことができればスムーズかもしれない。  
└> 補足資料(Appendix)として「講師が事前に準備すること」という資料があっても良いと思う。  


## 想定するネットワーク構成を明確にしたほうが良いのでは？


**-----解決方法(1)-----**  
`NAT` ＋ `ホストオンリーアダプター` とする。  
https://github.com/lpi-japan/server-text/blob/main/Chapter4.md  

受講者マシンはこれで良いが、講師マシンは受講者マシンからのDNS問い合わせを受け付けるので工夫が必要。  
**-----**

VirtualBoxで使用するアダプタをどうするか？  
- ブリッジ
  - シンプルだが、既存のネットワークに影響がでる可能性があるのでネットワーク管理者に相談する必要あり
  - IPアドレス設計、IPアドレス管理が必要
- NAT
  - 仮想マシンが1台の場合
  - インターネットへなNAT通信するのでdnf(yum)やaptは使える
  - ホストを含め外部から仮想マシンに接続できない
  - ホストマシンから通信できないのでTeraTermが使えない
  - ホストを含め外部から仮想マシンに接続するにはポートフォワーディングの設定が必要
- NATネットワーク
  - VirtualBox内に複数の仮想マシンを作成し相互に通信させたい場合
  - インターネットへなNAT通信するのでdnf(yum)やaptは使える
  - ホストを含め外部から仮想マシンに接続できない
  - ホストマシンから通信できないのでTeraTermは使えない
  - ホストを含め外部から仮想マシンに接続するにはポートフォワーディングの設定が必要
- ホストオンリーアダプター
  - インターネット接続に関係なくホストマシンと仮想マシンで通信できる
  - ホストマシンからTeraTermで接続できる
- 内部ネットワーク
  - VirtualBox内で完全に閉じてしまいたい場合
  - インターネットに接続できないのでdnf(yum)やaptが使えない
  - ホストマシンから通信できないのでTeraTermは使えない

VirtualBoxの仮想マシンが前提なら次のような構成が安全と考える。  
- 講師マシンは `ブリッジ` とし受講者マシンからネットワーク接続できるようにする
- 受講者マシンは `NAT` or `NATネットワーク` ＋ `ホストオンリーアダプター` とし、ホストオンリーアダプターのIPにTeraTerm接続する  