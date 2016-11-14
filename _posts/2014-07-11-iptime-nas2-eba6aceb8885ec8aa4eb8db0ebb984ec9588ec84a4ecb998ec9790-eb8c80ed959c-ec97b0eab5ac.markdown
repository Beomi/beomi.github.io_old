---
author: livingmethod
comments: true
date: 2014-07-11 23:33:10+00:00
layout: post
link: http://blog.jblee.kr/2014/07/11/iptime-nas2-%eb%a6%ac%eb%88%85%ec%8a%a4%eb%8d%b0%eb%b9%84%ec%95%88%ec%84%a4%ec%b9%98%ec%97%90-%eb%8c%80%ed%95%9c-%ec%97%b0%ea%b5%ac/
slug: iptime-nas2-%eb%a6%ac%eb%88%85%ec%8a%a4%eb%8d%b0%eb%b9%84%ec%95%88%ec%84%a4%ec%b9%98%ec%97%90-%eb%8c%80%ed%95%9c-%ec%97%b0%ea%b5%ac
title: iptime nas2 리눅스(데비안)설치에 대한 연구
wordpress_id: 12
categories:
- Tech
tags:
- Debian
- Linux
- NAS2
- ssh
---

우선은 iptime nas2에 데비안을 올린 HDD로 부팅이 된다고 일전에 말했던것을 기준으로 말하겠습니다.

그런데 제가 ssh 연것이 필요했던 이유는 u-boot나 bios부팅순서 변경이 필요해서였지요.
하지만, 조금의 실험을 거쳐보니, 그런것 필요없이 일단 ext3의 primary, bootable HDD만 연결되어있으면(둘 이상의 hdd를 꼽을시 os하드는 1번하드칸에) HDD에 설치된 os인 데비안으로 부팅이 되덥니다.

굳이 as포기하며 ssh오픈하지 않아도, 충분히 사설 리눅스를 깔 수 있을것 같은데, 실험해보실수 있는 분이 필요합니다.
(참조: 데비안 깐 hdd로 부트시 내부 ip주소가 달라집니다)

제가 세운 가설은,
1. 사실 iptime은 HDD가 부트 우선순위였다!
- 이경우는 위 게시글처럼 debian kiriwood설치된 HDD면 바로 사용가능해야합니다. ssh 오픈을 하지 않더라도요.
2. ssh오픈시 HDD1에 리눅스파일이 옮겨지는데, 그 설정이 부팅시 영향이 있어 데비안이 깔린곳이 우선적으로 부트가 되었다.
- 이경우는 ssh오픈을 한 상태에서 데비안깔린 HDD를 꼽고 켤때 데비안으로 부팅이 되야 합니다.

실험해보실분?ㅎㅎ
1번가설대로라면, as포기하지도 않고 바로 리눅스로 올림이 가능하다는 것이니까요~^^
