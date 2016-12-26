---
title: '[DjangoTDDStudy]#01: 개발환경 세팅하기(Selenium / ChromeDriver)'
date: 2016-12-27 01:00:00+09:00
layout: post
categories:
- DjangoTDDStudy
---

<p align="center">
<img src="http://www.seleniumhq.org/images/big-logo.png" style="max-height:350px;" />
<img src="https://lh4.googleusercontent.com/-gjxoCu8Fu3c/AAAAAAAAAAI/AAAAAAABWTs/rbrvG-G2yDI/s0-c-k-no-ns/photo.jpg" style="max-height:350px;" />
</p>

# Web을 직접 테스트한다고?

웹 서비스를 개발하는 과정에서 꼭 필요한 것이 있다. 바로 실제로 기능이 동작하는지 테스트 하는 것.
이 테스트를 개발자가 직접 할 수도 있고, 혹은 전문적으로 테스트만 진행하는 QA팀에서 진행할 수도 있다.
하지만 위의 두 방법은 '사람이 직접 해야한다'는 공통점이 있다. 이걸 자동화 할 수 있다면 어떨까?

## Selenium

Selenium은 위의 질문에 대한 답변을 준다. 사람이 하기 귀찮은 부분을 자동화!

```py
from selenium import webdriver

browser = webdriver.Chrome('chromedriver')
# chromedriver가 Python파일과 같은 위치에 있거나, 혹은 OS의 PATH에 등록되어 쉘에서 실행 가능한 경우 위와같이 한다.
# 혹은 browser = webdriver.Chrome('/path/to/chromedriver')의 절대경로로 해도 된다.
browser.get('http://localhost:8000')

assert 'Django' in browser.title
```

위 코드는 Chrome 브라우저를 작동시키는 WebDriver를 이용해 새 크롬 창을 띄우고 `http://localhost:8000`이라는 url로 들어간 후 브라우저의 title에 'Django'라는 글자가 들어가 있는지를 확인(Assert)해준다.

현재 상황에서는 django웹서버를 실행하지 않았기 때문에 당연하게도 AssertionError가 난다.

