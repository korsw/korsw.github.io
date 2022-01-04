---
title: 안드로이드 스튜디오 설치 및 프로젝트 만들기
author: korsw
date: 2022-01-01 21:13:09 +0900
categories: [Android, Android Kotlin]
tags: [android, androidstudio]
---

안드로이드를 개발하려면 안드로이드의 IDE(Integrated Development Environment)부터 설치해야한다.<br/>
안드로이드의 IDE는 안드로이드 스튜디오다

## 1. 안드로이드 스튜디오 설치
[안드로이드 스튜디오](https://developer.android.com/studio?hl=ko){: target="_blank"}에서 안드로이드 스튜디오 설치 파일을 받아서 설치하자 <br/>

## 2. 프로젝트 생성
설치가 완료된 안드로이드 스튜디오를 실행하면 프로젝트를 생성할 수 있는 화면이 나온다.
![start AndroidStudio](/assets/img/posts/2022-01-01-start-androidstudio/welcomeToAndroidStudio.png){: width="1086" height="542"}
_안드로이드 스튜디오 실행 화면_

여기서 new project를 누른다.

![new Project Board](/assets/img/posts/2022-01-01-start-androidstudio/newProject.png){: width="1086" height="542"}
_Project 생성_

안드로이드 스튜디오에서 제공하는 여러가지 템플릿들을 확인할 수 있다.<br/>
우리는 여기서 빈 엑티비티 하나만 있는 프로젝트를 생성하기 위해 Empty Activity선택해 생성해보자

![setEmptyActivity](/assets/img/posts/2022-01-01-start-androidstudio/setEmptyActivity.png){: width="1086" height="542"}
_crates project!_
위와 같은 프로젝트 기본 설정 화면이 나올것이다.

| Tage | 의미 |
|---|:---|
| name | 프로젝트 이름 |
| Package name | Android System에서 인식하기 위한 고유 이름<br/>보통 `조직이름.앱 이름`형태로 소문자로 구성 |
| Save location | 프로젝트 저장 경로 |
| Language | 개발 언어 선택<br/>`Kotlin`, `Java` |
| Minimum SDK | 요구할 안드로이드 최소 버전 |

위 표는 각 tage별 설명을 간략화 한것이다.<br/>
우리는 Kotlin을 사용할 것이고, 보통 안드로이드 4.4이상을 요구하기 때문에 이것만 설정하고 나머지는 자신의 환경에 맞게 설정하자<br/>
할건 다 했다. Finish를 누르자!

![projectBoard](/assets/img/posts/2022-01-01-start-androidstudio/projectBoard.png){: width="1086" height="542"}
_프로젝트 실행 화면_

하단에 로딩이 진행중일 것이다. 조금 기다리면 모든 설정이 끝난다.<br/>
여기서 안드로이드 스마트폰을 연결하여 Run - Run 'app'`Shift + F10`을 누르면 스마트폰에 어플 설치 및 실행이 진행된다.<br/>
난 안드로이드 스마트폰이 없고, 있어도 연결하기 귀찮다면? 가상으로 만들자!

## 3. AVD(Android Virtual Device) 만들기

AVD(Android Virtual Device)는 말 그대로 안드로이드 가상 머신이다. 설치 방법 정말 쉽다!<br/>
Tools -> AVD Manager -> + Create Virtual Device -> 원하는 기기 선택 -> 원하는 버전 다운~~모르면 맨 위꺼 받자~~ -> AVD name 작성 -> Finish<br/>
끝! 이제 가상머신을 활용할 수 있다!

## Reference
[Android 스튜디오 소개](https://developer.android.com/studio/intro?hl=ko)
