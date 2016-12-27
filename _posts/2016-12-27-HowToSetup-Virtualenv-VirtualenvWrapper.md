---
title: "Virtualenv/VirtualenvWrapper OS별 설치&이용법"
date: 2016-12-27 17:00:00+09:00
layout: post
published: false
---

<p align="center">
<img src="http://aeguana.com/blog/wp-content/uploads/2015/06/python-virtualenv.jpg" style="max-height:250px;" />
</p>

# Virtualenv란?

Virtualenv란 시스템 OS에 설치된 주 python뿐만 아니라 여러 버전의 Python과 프로젝트별로 다른 종류의 라이브러리를 사용하는 것에 있어 가장 핵심된 기능을 제공한다.

예를들어, 어떤 옛날 프로젝트에서는 Python2.7버전에 pip로 Django1.6을 사용했다고 가정해보자. 하지만 이번에 새로 시작하는 프로젝트는 Python3.6에 pip로 Django1.10을 사용하려고 한다. 물론 가장 쉬운 방법은 개발 환경별로 다른 컴퓨터를 사용하는 것이지만, 공간적/금전적/편의적으로 어렵다.

따라서 우리는 Python실행파일과 pip로 설치된 라이브러리들을 독립된 폴더에 넣어버리는 방법을 선택할 수 있는데, 이것이 Virtualenv의 핵심이다.

아래 가이드는 OS별로 나누어져있다. [\[MAC OS가이드\]](#macos) [\[LINUX 가이드\]](#linux) [\[WINDOWS 가이드\]](#windows)

<span id="macos"></span>

# MAC OS(OS X)의 경우

## Virtualenv를 설치해보자 [MAC OS]

MAC OS에는 시스템 전역에 기본적으로 Python2가 설치되어있다. 따라서 아래 명령어로 쉽게 pip를 설치할 수 있다.

```
$ sudo easy_install pip
```

만약 sudo로 시스템 전역에 설치하기가 싫다면 [HomeBrew](http://brew.sh/)를 이용해 Python을 유저영역에 설치할 수도 있다.

```
$ brew install python
(Python3의 경우는 brew install python3)
```

pip가 성공적으로 설치되었는지 확인하려면 다음 명령어로 pip의 버전을 확인해 보면 된다.

```
$ pip -V (Python3 pip의 경우에는 pip3 -V)
```

![](https://www.dropbox.com/s/ouazxdbx2ql7cxa/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202016-12-27%2017.56.54.png?dl=1)

만약 pip나 pip3이라는 명령어가 먹히지 않는다면 아래의 명령어로 Python의 모듈로서 pip를 호출할 수 있다.

```
Python2의 경우
$ python -m pip -V

Python3의 경우
$ python3 -m pip -V
```

![](https://www.dropbox.com/s/1iq7nss1tgenriu/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202016-12-27%2017.57.57.png?dl=1)

Virtualenv와 VirtualenvWrapper는 pip를 통해 설치가 가능하다.

```
Python2의 경우
$ pip install virtualenv virtualenvwrapper

Python3의 경우
$ pip3 install virtualenv virtualenvwrapper
```

만약 `pip`/`pip3` 명령이 먹지 않는다면 아래 명령어로 대체할 수 있다.
(시스템에 easy_install로 pip를 설치한 경우 sudo권한이 필요할 수 있다. 이때는 `sudo pip install`으로 명령어 앞에 sudo를 붙여주자.)

```
Python2 pip의 경우
$ python -m pip install virtualenv virtualenvwrapper

Python3 pip의 경우
$ python3 -m pip install virtualenv virtualenvwrapper
```

지금까지 사용한 `pip`와 `pip3`은 virtualenv를 어느 pip에 설치할까에 대한 내용일 뿐, 파이썬 가상환경에 어떤 Python이 설치될지와는 무관하다.

## Virtualenv의 기본적 명령어 [MAC OS]

Virtualenv는 기본적으로 아래의 명령어로 동작한다.

```
$ virtualenv --python=파이썬버전 가상환경이름
ex)
$ virtualenv --python=python3.5 test_env
$ virtualenv --python=python2.7 test_env2
```

![](https://www.dropbox.com/s/hehcdglqiu14mik/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202016-12-27%2018.13.11.png?dl=1)

이와 같이 Python버전을 명시해주고 가상환경을 만들 수 있다. (단, 선택할 Python은 시스템에 깔려있는 버전이어야 한다.)

만든 가상환경에 진입(가상환경을 활성화)하려면 아래 명령어를 이용하면 된다.

```
$ source 가상환경이름/bin/activate
```

Python3이 설치된 test_env로 진입한 경우

![](https://www.dropbox.com/s/xiymbhfyezjj6wa/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202016-12-27%2018.14.28.png?dl=1)

Python2가 설치된 test_env2로 진입한 경우

![](https://www.dropbox.com/s/ovxyqj9ig38433h/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7%202016-12-27%2018.15.53.png?dl=1)

각각 다른 python버전이 실행되고 있다는 것을 알 수 있다.

이후 pip를 통해 외부 모듈과 라이브러리들을 설치하는 경우, source 명령어로 가상환경에 진입하지 않으면 라이브러리들을 불러쓸 수 없게된다. 즉, 프로젝트 별로 다른 라이브러리만이 설치된 환경을 구성한 것이다.


