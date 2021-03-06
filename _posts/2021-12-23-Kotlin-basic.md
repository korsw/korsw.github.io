---
title: 코틀린을 알아보자
author: korsw
date: 2021-12-23 17:03:33 +0900
categories: [Kotlin]
tags: [Kotlin]
---

이 글은 Kotlin In Action을 읽으며 정리한 글입니다. 자세한 내용은 책을 구매해서 봅시다!

## 코틀린이란?
자바 플랫폼에서 돌아가는 언어로, 간결하고 자바와 상호운용성을 중시하는 것이 특징이다.<br/>

## 코틀린의 특성
코틀린의 특성을 몇가지 정의해보면 다음과 같다.

### 실행 플랫폼
자바가 실행되는 모든 곳에서 사용이 가능하다. 심지어 자바스크립트도!

### 정적 타입 지정 언어
자바와 동일한 특성인데, 이를 설명하면 프로그램 구성 요소의 타입을 컴파일 시점에서 알 수 있고, 프로그램 안에서 객체의 필드, 메소드를 사용할때 마다 컴파일러가 타입을 검증해준는 것이다.<br/>
~~한마디로 타입 지정을 안해도 알아서 정의해준다.~~<br/>
타입 시스템은 크래스, 인터페이스, 제네릭스 등과 같이 자바와 같지만 한가지 다른점 하나는 nullable type을 지원한다는것이다. 이로 인해 널포인터 오류 발생여부를 확인할 수 있다는 장점이 존재한다.<br/>
이게 그치지 않고 함수 타입을 지원해서 여러가지 이점이 생겼다.

1. 함수의 파라미터로 다른 함수를 받을 수 있고, 새로은 함수를 반환할 수 있다.
2. 람다식을 지원한다.
3. 데이터 클래스는 불변적(immutable) 값 객체를 간편하게 만들 수 있는 구문 제공
4. 객체와 컬렉션을 함수형 스타일로 다룰 수 있는 API 제공




