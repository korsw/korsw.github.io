---
title: Kotlin의 List를 알아보자
author: korsw
date: 2021-12-28 00:43:59 +0900
categories: [Kotlin]
tags: [kotlin, list]
---

List는 여러개의 값을 순서 있게 저장하는 데이터 유형이다.<br/>

| List | 형태 | 의미 | 예시 |
|---|:---|:---|:---|
| List | List<T> | 생성 이후 수정 불가 | val numbers: List<Int> = listOf(1, 2, 3) |
| MutableList | MutableList<T> | 생성 이후 수정 가능 | val numbers: MutableList<Int> = mutableListOf(1, 2, 3) |

List와 MutableList 두가지가 있지만 List사용을 권장하고 있다. 그래도 List와 MutableList의 기능엔 무엇이 있는지 알아보자 

| List | 형태 | 의미 | 예시 |
|---|:---|:---|:---|
| reversed() | .reversed() | 리스트 역순 출력 | list.reversed() |
| sorted() | .sorted() | 리스트 요소 정렬 후 출력 | list.sorted() |


| MutableList | 형태 | 의미 | 예시 |
|---|:---|:---|:---|
| add | .add(index, elements) | 인덱스(생략시 맨 뒤)에 요소 추가<br/>성공시 `true`, 실패시 `false` 반환 | mutableList.add(3)<br/>mutableList.add(0, 3) |
| addAll | .add(index, list) | 인덱스(생략시 맨 뒤)에 리스 추가 | mutableList.add(List)<br/>mutableList.add(0, List) |
| set | set(index, elements) | 인덱스의 값을 요소값으로 변환 후<br/>인덱스에 있던 값 반환 | mutableList.set(1, 3) |
| iterator<br/> | iterator()<br/>listIterator() | iterator 반환 | mutableList.iterator()<br/>mutableList.listIterator() |
| clear | .clear() | 요소 삭제 | mutableList.clear() |
| remove | .remove(elements) | 요소 찾아서 삭제<br/>삭제시 `true`, 실패시 `false` 반환 | mutableList.remove(1) |
| removeAll | .remove(list) | 주어진 list에 포함된 요소 찾아서 삭제<br/>삭제시 `true`, 실패시 `false` 반환 | mutableList.remove(list) |
| removeAt | .removeAt(index) | 해당 인덱스 요소 반환 후 삭제 | mutableList.removeAt(1) |
| retainAll | .retainAll(list) | list에 존재하는 요소 빼고 전부 삭제 | mutableList.retainAll(list) |






