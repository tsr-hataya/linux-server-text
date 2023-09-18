# 第5章 メールサーバー構築


## 5.6 メールの送受信


### 5.6.1 ログ確認用端末の設定

host1.alpha.jp で1つ目の端末(またはTeraTerm)

```Shell
[root@host1 ~]#
[root@host1 ~]# tail -f /var/log/maillog
Sep 14 16:48:05 host1 postfix/postfix-script[5162]: starting the Postfix mail system
Sep 14 16:48:05 host1 postfix/master[5164]: daemon started -- version 3.5.9, configuration /etc/postfix
Sep 18 17:02:21 host1 postfix[1192]: fatal: parameter inet_interfaces: no local interface found for 192.168.1.101
　　：
　　：

```

host2.beta.jp で1つ目の端末(またはTeraTerm)

```Shell
[root@host2 ~]#
[root@host2 ~]# tail -f /var/log/maillog
Sep 14 17:23:16 host2 postfix/postfix-script[5572]: starting the Postfix mail system
Sep 14 17:23:17 host2 postfix/master[5574]: daemon started -- version 3.5.9, configuration /etc/postfix
Sep 18 17:02:24 host2 postfix[1187]: fatal: parameter inet_interfaces: no local interface found for 192.168.1.102
　　：
　　：

```


### 5.6.2 メール送受信用端末の起動とユーザーの切り替え

host1.alpha.jp で2つ目の端末(またはTeraTerm)

```Shell
[root@host1 ~]#
[root@host1 ~]# su - usera
[usera@host1 ~]$
[usera@host1 ~]$ id
uid=1001(usera) gid=1001(usera) groups=1001(usera) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
[usera@host1 ~]$
[usera@host1 ~]$
```

host2.beta.jp で2つ目の端末(またはTeraTerm)

```Shell
[root@host2 ~]#
[root@host2 ~]# su - userb
[userb@host2 ~]$
[userb@host2 ~]$ id
uid=1001(userb) gid=1001(userb) groups=1001(userb) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
[userb@host2 ~]$
```


### 5.6.3 usera@alpha.jp から userb@beta.jp へメール送信

host1.alpha.jp で2つ目の端末(またはTeraTerm)

```Shell
[usera@host1 ~]$
[usera@host1 ~]$ mail userb@beta.jp

[usera@host1 ~]$
[usera@host1 ~]$
```


### 5.6.4 userbのメール着信確認

host2.beta.jp で2つ目の端末(またはTeraTerm)

```Shell
[usera@host2 ~]$
[usera@host2 ~]$ mail

[usera@host2 ~]$
[usera@host2 ~]$
```
