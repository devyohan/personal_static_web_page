---
layout: post
category: note
title: Python을 활용하여 이메일 보내기
tags: smtp 이메일
---

서버에 이벤트가 발생하면 알림을 보내기 위한 방법 중에 이메일에 내용을 넣어 보내는 방법을 확인해봅시다.

## 이메일 전송을 위한 SMTP

HTTP 처럼 이메일을 전송하기 위한 Simple Mail Transfer Protocol(SMTP) 이 있습니다.

                  +----------+                +----------+
      +------+    |          |                |          |
      | User |<-->|          |      SMTP      |          |
      +------+    |  Client- |Commands/Replies| Server-  |
      +------+    |   SMTP   |<-------------->|    SMTP  |    +------+
      | File |<-->|          |    and Mail    |          |<-->| File |
      |System|    |          |                |          |    |System|
      +------+    +----------+                +----------+    +------+
                   SMTP client                SMTP server

## SMTP 서비스

- SPARK POST
  - 30 일에 15,000 건 까지 무료
  - https://www.sparkpost.com
- Amazon Simple Email Service(SES)
  - https://aws.amazon.com/ses/
- mailgun
  - 30 일에 10,000 건 까지 무료
  - 이메일 인증 서비스도 가능
  - https://www.mailgun.com

## 코드
{% highlight python %}
import smtplib
smtpGmail = smtplib.SMTP('smtp.gmail.com', 587)
smtpGmail.ehlo() # 일종의 핸드세이크 하는 과정인것 같습니다.
smtpGmail.starttls()
smtpGmail.login('asdf@gmail.com', 'SECRET_PASSWORD')
smtpGmail.sendmail('asdf@gmail.com', '받는사람@gmail.com', 'Subject: 제목 \ 내용')
smtpGmail.quit() # 연결 끊기
{% endhighlight %}

## 참고한 내용

- https://tools.ietf.org/html/rfc5321
- 파이썬 프로그래밍으로 지루한 작업 자동화하기 - 알 스웨이가트 지음
