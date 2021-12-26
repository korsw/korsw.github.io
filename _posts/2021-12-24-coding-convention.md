---
title: 코딩 규칙(coding convention)을 알아보자! 카멜 표기법, 파스칼 표기법, 스네이크 표기법
author: korsw
date: 2021-12-24 18:16:07  +0900
categories: [Dev, common]
tags: [coding convention]
---

프로젝트를 여러명이 진행할때 서로의 코드 작성방식이 어려우면 가독성이 떨어질 수 있다. 이를 방지하기 위해 코딩 작성 규칙(coding convention)이 존재한다.<br/>

## 카멜 표기법(camelCase)

| 케이스 | 작성방법 | 예시 |
|---|:---|:---|
| 함수, 변수명 | 첫 단어만 소문자, 이후 단어의 첫 글자를 대문자로 작성 | fun `onCreateActivity()`<br/>var `numValue`: Int |

보통 함수, 변수명 등에 사용된다.

## 파스칼 표기법(PascalCase)

| 케이스 | 작성방법 | 예시 |
|---|:---|:---|
| 클래스명 | 단어의 첫 글자를 대문자로 작성 | class `MainActivity` |

보통 클래스명에 사용되지만 함수, 변수명에도 사용된다.

## 스네이크 표기법(snake_case)

| 케이스 | 작성방법 | 예시 |
|---|:---|:---|
| 함수, 변수명 | 모두 소문자로 작성하며 단어를 _로 구분 | fun `on_create_activity()`<br/>var `num_value`: Int |

보통 함수, 변수명 등에 사용된다.

## 상수

| 케이스 | 작성방법 | 예시 |
|---|:---|:---|
| 상수 | 모두 대문자로 작성 | const val `HELLO`: String = "hello"<br/>const val `CHECK_MESSAGE`: String = "check" |

상수는 대문자로 쓰자!

## Reference

[Kotlin 스타일 가이드](https://developer.android.com/kotlin/style-guide?hl=ko){: target="_blank"}<br/>
[고돈호 (2021). 이것이 안드로이드다 with 코틀린, 한빛미디어](http://www.kyobobook.co.kr/product/detailViewKor.laf?ejkGb=KOR&mallGb=KOR&barcode=9791162243947&orderClick=LEa&Kc=){: target="_blank"}<br/>