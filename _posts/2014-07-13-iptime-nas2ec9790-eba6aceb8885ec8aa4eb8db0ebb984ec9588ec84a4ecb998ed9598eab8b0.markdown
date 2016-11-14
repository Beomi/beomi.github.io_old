---
author: livingmethod
comments: true
date: 2014-07-13 01:33:12+00:00
layout: post
link: http://blog.jblee.kr/2014/07/13/iptime-nas2%ec%97%90-%eb%a6%ac%eb%88%85%ec%8a%a4%eb%8d%b0%eb%b9%84%ec%95%88%ec%84%a4%ec%b9%98%ed%95%98%ea%b8%b0/
slug: iptime-nas2%ec%97%90-%eb%a6%ac%eb%88%85%ec%8a%a4%eb%8d%b0%eb%b9%84%ec%95%88%ec%84%a4%ec%b9%98%ed%95%98%ea%b8%b0
title: iptime nas2에 리눅스(데비안)설치하기
wordpress_id: 14
categories:
- Tech
tags:
- Debian
- Linux
- NAS2
---

어제 간단한 사실을 놓쳐 끙끙대던게 아주 간단히 해결되고나서 오늘 아침 10분만에 Debian 설치완료!

이제 iptime도 쓸만하겠어요:)

간단히 정리해보면
1. hdd를 1번2번슬롯에 다 끼운다. 데비안이 설치될 HDD는 2번에.
2. 기타설정에서 ssh 활성화.
(단 1번하드는 ext3 or ext4 파티션이 첫번째로 1개 있고, 2번하드는 파티션이 하나도 없어야한다 - umount시 hdd is busy에러 방지용)
3. ssh접속.(putty등)
4. fdisk -l 으로 파티션 확인시 1번하드는 /dev/sda로, 2번하드는 /dev/sdb로 인식됨을 확인할 수 있다.
5. fdisk /dev/sdb 로 들어가서
O(파티션테이블리셋) P(primary) N(new partition) P(primary) 1(1번파티션) 엔터 엔터(실린더 처음~끝 지정-파티션크기) W(write)
6. 파티션 테이블 지정됬다는 Alert가 뜸.
7. 다시 fdisk /dev/sdb
a(부팅가능) 1(1번파티션 지정)
8. 데비안 설치(2번하드root에)
9. 뒤 버튼을 눌러 nas 강제종료
10. 1번하드를 제거후 부팅
10.데비안 완성!

ps. fdisk -l 해도 파티션 목록이 안떠요. 왜그럴까요?
