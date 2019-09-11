## Домашнее задание


#### Установка почтового сервера
1. Установить в виртуалке postfix+dovecot для приёма почты на виртуальный домен любым обсужденным на семинаре способом
2. Отправить почту телнетом с хоста на виртуалку
3. Принять почту на хост почтовым клиентом

#### Результат
1. Полученное письмо со всеми заголовками
2. Конфиги postfix и dovecot

Всё это сложить в git, ссылку прислать в "чат с преподавателем"

Отправляем письмо TELNETомс с хоста WEB:

```
[vagrant@web ~]$ telnet otus.local 25
Trying 172.20.10.50...
Connected to otus.local.
Escape character is '^]'.
220 mail.otus.local ESMTP Postfix (2.10.1)
helo otus.local
250 mail.otus.local
mail from: web@otus.local
250 2.1.0 Ok
rcpt to: vagrant@otus.local
250 2.1.5 Ok
data
354 End data with <CR><LF>.<CR><LF>
Звонок для преподавателя!
.
250 2.0.0 Ok: queued as BEF362064B28

```
И само письмо: 

```
[root@server ~]# cat /home/vagrant/Maildir/new/1568195
1568195528.V801I2064b2aM26593.server   1568195795.V801I2064b2bM460379.server
[root@server ~]# cat /home/vagrant/Maildir/new/1568195795.V801I2064b2bM460379.server
Return-Path: <web@otus.local>
X-Original-To: vagrant@otus.local
Delivered-To: vagrant@otus.local
Received: from otus.local (unknown [172.20.10.51])
        by mail.otus.local (Postfix) with SMTP id BEF362064B28
        for <vagrant@otus.local>; Wed, 11 Sep 2019 09:56:01 +0000 (UTC)

Звонок для преподавателя!
```