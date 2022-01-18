---
title: 코틀린의 가변인자(vararg)를 알아보자
author: korsw
date: 2022-01-19 01:13:22 +0900
categories: [Kotlin]
tags: [kotlin, vararg]
---

## vararg
<br/>
코틀린을 사용하다가 함수나 클래스 등등에 여러개의 파라미터를 넘겨야 할 경우가 생기는 경우가 빈번하게 발생한다.<br/>
이럴때 사용할 수 있는게 **vararg**(Variable number of arguments)이다<br/>
<br/>
```kotlin
fun <T> asList(vararg ts: T): List<T> {
    val result = ArrayList<T>()
    for (t in ts)
        result.add(t)
    return result
}
```
<br/>
위와 같이 파라미터에 vararg를 사용하여 함수의 파라미터를 받을 수 있다.<br/>
이때 파라미터 하나에만 사용할 수 있으며 보통 마지막 파라미터에 사용한다<br/>
<br/>
```kotlin
val list = asList(1, 2, 3)
```
<br/>
이렇게 사용한다
<br/>
### 배열을 vararg로 넘길 경우
<br/>
소제목부터 이게 무슨소리인가? 배열을 vararg로 넘기다니?<br/>
말 그대로이다. vararg 인자를 받는 함수의 파라미터로 배열을 넣는것이다.<br/>
그냥 넣으면 오류가 발생한다. 이 오류를 해결하기 위해 spread operator(스프레드 연산자)를 사용한다.<br/>
사용 방법은 간단하다. 파라미터로 넘길때 해당 파라미터 앞에 **`*`**를 붙여주면 된다.
<br/>
```kotlin
val a = arrayOf(1, 2, 3)
val list = asList(-1, 0, a, 4) // 오류발생! 스프레드 연산자가 없어요!
val list = asList(-1, 0, *a, 4)
```
<br/>
이런식으로 말이다.
<br/>
### 기본형 배열(primitive type array)을 vararg로 넘길 경우
<br/>
[ByteArray, ShortArray, IntArray](https://kotlinlang.org/docs/basic-types.html#primitive-type-arrays){: target = "_blank"}와 같은 기본형 배열들의 경우 그냥 vararg 파라미터로 넘길 경우 오류가 발생한다.<br/>
이를 방지하기 위해 toTypedArray() 함수를 사용하여 일반형(regular)으로 변환한 후 파라미터로 넘겨야한다.<br/>
<br/>
```kotlin
val a = intArrayOf(1, 2, 3) // 기본형 배열 IntArray
val list = asList(-1, 0, *a.toTypedArray(), 4)
```
<br/>
위와 같이 `*배열.toTypedArray()` 형태로 사용하면 된다.
<br/>
<br/>
## Reference
[Variable number of arguments (varargs)﻿](https://kotlinlang.org/docs/functions.html#variable-number-of-arguments-varargs){: target="_blank"}