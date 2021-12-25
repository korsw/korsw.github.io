---
title: Kotlin 키워드 (fun, val, var)
author: korsw
date: 2021-12-24 15:08:09 +0900
categories: [Kotlin]
tags: [kotlin, class]
---

## 함수
코틀린에서 함수를 정의할때 **fun** 키워드를 사용한다.

```kotlin
fun main() {
	foo()
}
```
이런식으로 작성하여 사용한다.<br/>
함수를 사용하다보면 파라미터를 넣어야할 경우가 생기는데 파라미터를 넣을때 뒤에 **: 자료형** 형태로 정의해야한다
```kotlin
fun main(bar: String) {
	foo()
} 
```
위의 코드에서 main함수에 String형태의 bar를 넘겨준것을 알 수 있다.<br/>
함수의 경우도 반환값이 있을 수 있다. 이 또한 함수 선언 뒤에 **: 자료형** 형태로 정의해야한다.
```kotlin
fun main(bar: String): Int {
	foo()
} 
```
Int값을 반환하는 함수를 선언했다.
물론 반환값이 없거나 의미없는 경우도 있을텐데 이 경우 **Unit**을 사용한다.
```kotlin
fun main(bar: String): Unit {
	println("foo")()
} 
```
다행스럽게도 Unit은 생략가능하다.

## 변수

코틀린에서 변수는 val, var두가지가 존재한다.

### val
val는 읽기전용 지역변수를 선언할때 사용된다. 즉, 값 변경이 불가능하다.
```kotlin
fun main() {
	val foo: Int = 0
	val bar = 0
	val foobar: Int
} 
```
여기서 확인할 수 있는건 foo 변수와 같이 **: 자료형** 형태로 자료형을 정의할 수 있다는 것이다.<br/>
물론 bar 변수와 같이 선언해도 자동으로 Int형으로 유추해서 설정해준다.<br/>
또한 foobar 변수처럼 초기화가 안됐을 때 변수 선언만 하고 나중에 초기화할 수 있다.

### var
var는 수정 가능한 변수이다.
```kotlin
fun main() {
	var foo: Int = 0
	foo = 1
} 
```
foo가 0에서 1로 변경된다.


## Reference

[Basic syntax](https://kotlinlang.org/docs/basic-syntax.html){: target="_blank"}<br/>