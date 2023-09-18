# 第5章 メールサーバー構築


## 5.5 アカウントの作成


### 5.5.1 host1.alpha.jp に usera を作成

```Shell
[root@host1 ~]#
[root@host1 ~]# useradd usera
[root@host1 ~]# passwd usera
ユーザー usera のパスワードを変更。
新しい パスワード:
正しくないパスワード: このパスワードは辞書チェックに失敗しました - 辞書の単語に基づいています
新しい パスワードを再入力してください:
passwd: すべての認証トークンが正しく更新できました。
[root@host1 ~]#
[root@host1 ~]#
[root@host1 ~]# id usera
uid=1001(usera) gid=1001(usera) groups=1001(usera)
[root@host1 ~]#
[root@host1 ~]# grep usera /etc/passwd
usera:x:1001:1001::/home/usera:/bin/bash
[root@host1 ~]#
[root@host1 ~]# grep usera /etc/group
usera:x:1001:
[root@host1 ~]#
```


### 5.5.2 host2.beta.jp に userb を作成

```Shell
[root@host2 ~]#
[root@host2 ~]# useradd userb
[root@host2 ~]# passwd userb
ユーザー userb のパスワードを変更。
新しい パスワード:
正しくないパスワード: このパスワードは辞書チェックに失敗しました - 辞書の単語に基づいています
新しい パスワードを再入力してください:
passwd: すべての認証トークンが正しく更新できました。
[root@host2 ~]#
[root@host2 ~]# id userb
uid=1001(userb) gid=1001(userb) groups=1001(userb)
[root@host2 ~]#
[root@host2 ~]# grep userb /etc/passwd
userb:x:1001:1001::/home/userb:/bin/bash
[root@host2 ~]#
[root@host2 ~]# grep userb /etc/group
userb:x:1001:
[root@host2 ~]#
```

