---
author: livingmethod
comments: true
date: 2014-08-03 14:33:36+00:00
layout: post
link: http://blog.jblee.kr/2014/08/03/%ed%8f%ac%ea%b3%a0%ed%94%8c%eb%9f%ac%ea%b7%b8-v4-%eb%aa%a8%eb%b0%94%ec%9d%bc%ec%9a%a9-debian-%ec%9e%90%eb%8f%99-%ec%84%a4%ec%b9%98-%ec%8a%a4%ed%81%ac%eb%a6%bd%ed%8a%b8/
slug: '%ed%8f%ac%ea%b3%a0%ed%94%8c%eb%9f%ac%ea%b7%b8-v4-%eb%aa%a8%eb%b0%94%ec%9d%bc%ec%9a%a9-debian-%ec%9e%90%eb%8f%99-%ec%84%a4%ec%b9%98-%ec%8a%a4%ed%81%ac%eb%a6%bd%ed%8a%b8'
title: 포고플러그 v4, 모바일용 Debian 자동 설치 스크립트
wordpress_id: 24
---

포고카페에 있는 예전 게시글(시라키님: http://cafe.naver.com/pogolinux/3632 )을 참조하여,
포고리눅스 한국미러서버로 링크를 변경한것입니다.
포고v4, 모바일 모두 사용가능합니다.

*주의 : 한방팩이 아닌, 순수 os설치만 담당합니다.
기본적으로 apt-get와 데몬설정등을 건드리실 수 있으신분들에게 권합니다.
(그만큼 빠르게 됩니다.)

++
@2014.07.09
-구글서버용 스크립트를 추가하였습니다.
-스크립트용 파일을 게시글에 업로드하였습니다.
@2014.07.29
-한국서버 주소를 미러2로 옮겼습니다
(사유: 미러1 다운)
@2014.08.03
-구글서버용 스크립트 제거
(사유: wget --no-check-certificate 명령어가 포고 순정에서 먹히지 않아서 오류발생)

[설치법]

포고 ssh접속후

cd /tmp

(한국서버)
wget http://pogolinux.iptime.org/ppv4-debian-install.sh

chmod +x ppv4-debian-install.sh

./ppv4-debian-install.sh

이렇게 하신후 
O P N P 1 엔터 엔터 W
하신후 기다리시면 설치가 완료됩니다.

다시 명령어 입력 가능상태가 되시면
/sbin/reboot
재부팅합니다.

약 3분 후 다시 ssh접속하시면 완료됨을 알 수 있습니다.
