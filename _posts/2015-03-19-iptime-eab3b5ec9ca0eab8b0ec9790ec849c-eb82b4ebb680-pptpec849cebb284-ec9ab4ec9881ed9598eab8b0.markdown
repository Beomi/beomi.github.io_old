---
author: livingmethod
comments: true
date: 2015-03-19 11:28:32+00:00
layout: post
link: http://blog.jblee.kr/2015/03/19/iptime-%ea%b3%b5%ec%9c%a0%ea%b8%b0%ec%97%90%ec%84%9c-%eb%82%b4%eb%b6%80-pptp%ec%84%9c%eb%b2%84-%ec%9a%b4%ec%98%81%ed%95%98%ea%b8%b0/
slug: iptime-%ea%b3%b5%ec%9c%a0%ea%b8%b0%ec%97%90%ec%84%9c-%eb%82%b4%eb%b6%80-pptp%ec%84%9c%eb%b2%84-%ec%9a%b4%ec%98%81%ed%95%98%ea%b8%b0
title: Iptime 공유기에서 내부 PPTP서버 운영하기
wordpress_id: 80
---

Iptime 공유기는 아래 사진과 같이 자체 PPTP vpn기능을 갖고있다.

[![iptimepptp1](https://livingmethod.files.wordpress.com/2015/03/iptimepptp1.png?w=660)](https://livingmethod.files.wordpress.com/2015/03/iptimepptp1.png)

하지만, Iptime에서 제공하는 공유기 자체 vpn은 속도가 5Mbps로 QoS가 걸려있는데, Iptime사측의 설명은 공유기의 성능상의 문제로 제한하고 있다는데, 5Mbps로는 외부에서 도저히 파일전송을 할 수 없는 속도이다.

따라서 내부에 NAS등을 구축하여 vpn서버를 만들게 되는데, 그때 PPTP를 사용한다면 포트를 두가지 열어주어야 한다.
첫번째는 1723/all 포트이며, 두번째는 GRE(47port)이다.

하지만, 수동으로 추가하는 방식으로는 사용가능한 프로토콜이 TCP/UDP 2가지 뿐이라, GRE 선택지가 존재하지 않는다.

헌데 Iptime측의 답변에서는 존재하고, 포트포워딩 설정창에서 세팅하면 된다고 언급하여,
정의된 리스트를 확인해 보았더니, 아래와 같았다.

정의된 리스트중 PPTP를 선택할 경우에 1723/all와 47/gre가 모두 포워딩 된것을 확인할 수 있었다.
[![iptimepptp](https://livingmethod.files.wordpress.com/2015/03/iptimepptp.png?w=660)](https://livingmethod.files.wordpress.com/2015/03/iptimepptp.png)

즉, 1723/all만 해서 되지 않는 경우에는 저렇게 숨겨진 GRE포트포워딩 고정세팅을 이용하면 된다는 것이다.(하지만 iptime에서는 명시적으로 안내를 해두지 않았다. 왜일까..)
