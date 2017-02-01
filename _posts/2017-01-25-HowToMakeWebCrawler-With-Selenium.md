---
title: "나만의 웹 크롤러 만들기(3): Selenium으로 무적 크롤러 만들기"
date: 2017-01-25 19:30:00+09:00
layout: post
categories:
- Python
published: false
---

<p align="center">
<img src="/img/2017-01-25-HowToMakeWebCrawler-With-Selenium/selenium1.jpg" style="max-height:256px;" />
</p>

이전게시글: [나만의 웹 크롤러 만들기(2): Login with Session](/python/2017/01/20/HowToMakeWebCrawler-With-Login.html)

# Selenium이란?

Selenium은 주로 웹앱을 테스트하는데 이용하는 프레임워크다. `webdriver`라는 API를 통해 운영체제에 설치된 Chrome등의 브라우저를 제어하게 된다.

브라우저를 직접 동작시킨다는 것은 JavaScript를 이용해 비동기적으로 혹은 뒤늦게 불러와지는 컨텐츠들을 가져올 수 있다는 것이다. 즉, '눈에 보이는' 컨텐츠라면 모두 가져올 수 있다는 뜻이다. 우리가 requests에서 사용했던 `.text`의 경우 브라우저에서 '소스보기'를 한 것과 같이 동작하여, JS등을 통해 동적으로 DOM이 변화한 이후의 HTML을 보여주지 않는다. 반면 Selenium의 ``
