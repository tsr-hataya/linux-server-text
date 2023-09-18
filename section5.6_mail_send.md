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
[usera@host1 ~]$ echo "This is Test mail from usera" | mail -v -s "Test mail from usera" userb@beta.jp
s-nail: No such file to load: /home/usera/.mailrc
s-nail: Warning -- v15-compat=yes will be default in v14.10.0!
s-nail: P(seudo)R(andom)N(umber)G(enerator): *TLS RAND_*
Mail Delivery Status Report will be mailed to <usera>.
[usera@host1 ~]$
```

host1.alpha.jp で1つ目の端末(またはTeraTerm)

```Shell
[root@host1 ~]#
[root@host1 ~]# tail -f /var/log/maillog
    :
Sep 18 17:56:48 host1 postfix/pickup[2693]: A082930F22DC: uid=1001 from=<usera>
Sep 18 17:56:48 host1 postfix/cleanup[2736]: A082930F22DC: message-id=<20230918085648.A082930F22DC@mail.alpha.jp>
Sep 18 17:56:48 host1 postfix/qmgr[2694]: A082930F22DC: from=<usera@mail.alpha.jp>, size=347, nrcpt=1 (queue active)
Sep 18 17:56:48 host1 postfix/smtp[2738]: A082930F22DC: to=<userb@beta.jp>, relay=mail.beta.jp[192.168.1.102]:25, delay=0.03, delays=0.01/0/0.02/0.01, dsn=2.0.0, status=sent (250 2.0.0 Ok: queued as A593E21C183F)
Sep 18 17:56:48 host1 postfix/cleanup[2736]: A775030F22DF: message-id=<20230918085648.A775030F22DF@mail.alpha.jp>
Sep 18 17:56:48 host1 postfix/qmgr[2694]: A775030F22DF: from=<>, size=2006, nrcpt=1 (queue active)
Sep 18 17:56:48 host1 postfix/bounce[2741]: A082930F22DC: sender delivery status notification: A775030F22DF
Sep 18 17:56:48 host1 postfix/qmgr[2694]: A082930F22DC: removed
Sep 18 17:56:48 host1 postfix/smtp[2738]: A775030F22DF: to=<usera@mail.alpha.jp>, relay=none, delay=0, delays=0/0/0/0, dsn=5.4.6, status=bounced (mail for mail.alpha.jp loops back to myself)
Sep 18 17:56:48 host1 postfix/qmgr[2694]: A775030F22DF: removed
    :
```

### 5.6.4 userbのメール着信確認

host2.beta.jp で1つ目の端末(またはTeraTerm)

```Shell
[root@host2 ~]#
[root@host2 ~]# tail -f /var/log/maillog
    :
Sep 18 17:56:48 host1 postfix/pickup[2693]: A082930F22DC: uid=1001 from=<usera>
Sep 18 17:56:48 host1 postfix/cleanup[2736]: A082930F22DC: message-id=<20230918085648.A082930F22DC@mail.alpha.jp>
Sep 18 17:56:48 host1 postfix/qmgr[2694]: A082930F22DC: from=<usera@mail.alpha.jp>, size=347, nrcpt=1 (queue active)
Sep 18 17:56:48 host1 postfix/smtp[2738]: A082930F22DC: to=<userb@beta.jp>, relay=mail.beta.jp[192.168.1.102]:25, delay=0.03, delays=0.01/0/0.02/0.01, dsn=2.0.0, status=sent (250 2.0.0 Ok: queued as A593E21C183F)
Sep 18 17:56:48 host1 postfix/cleanup[2736]: A775030F22DF: message-id=<20230918085648.A775030F22DF@mail.alpha.jp>
Sep 18 17:56:48 host1 postfix/qmgr[2694]: A775030F22DF: from=<>, size=2006, nrcpt=1 (queue active)
Sep 18 17:56:48 host1 postfix/bounce[2741]: A082930F22DC: sender delivery status notification: A775030F22DF
Sep 18 17:56:48 host1 postfix/qmgr[2694]: A082930F22DC: removed
Sep 18 17:56:48 host1 postfix/smtp[2738]: A775030F22DF: to=<usera@mail.alpha.jp>, relay=none, delay=0, delays=0/0/0/0, dsn=5.4.6, status=bounced (mail for mail.alpha.jp loops back to myself)
Sep 18 17:56:48 host1 postfix/qmgr[2694]: A775030F22DF: removed
    :
```

host2.beta.jp で2つ目の端末(またはTeraTerm)

```Shell
[usera@host2 ~]$
[userb@host2 ~]$ mail
s-nail version v14.9.22.  Type `?' for help
/var/spool/mail/userb: 1 message 1 new
?N  1 usera@mail.alpha.jp   2023-09-18 17:56   18/651   "Test mail from usera                                "
& 1
[-- Message  1 -- 18 lines, 651 bytes --]:
Date: Mon, 18 Sep 2023 17:56:48 +0900
To: userb@beta.jp
Subject: Test mail from usera
Message-Id: <20230918085648.A082930F22DC@mail.alpha.jp>
From: usera@mail.alpha.jp

This is Test mail from usera

& q
Held 1 message in /var/spool/mail/userb
メールが /var/spool/mail/userb にあります
[usera@host2 ~]$
```
