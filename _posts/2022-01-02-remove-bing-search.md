---
title: 시작 메뉴에서 bing 검색을 제거해보자
author: korsw
date: 2022-01-02 00:52:34 +0900
categories: [Tip, windows 11]
tags: [tip, bing, windows 11]
---

나는 윈도우에서 프로그램을 실행할 때, window 키를 누르고 프로그램명을 검색해서 실행하는 편이다.<br/>
이때 오타가 발생한 경우 혹은 없는 프로그램을 검색하고 엔터를 누른 경우 ms edge를 통해 해당 내용이 검색된다.<br/>
이 기능이 너무 싫기에 시작 메뉴의 웹 검색을 비활성화 방법을 찾았다.<br/>

## 레지스트리 변경


`Win` + `R`을 동시에 눌러 실행창을 실행한 후 `regdit`을 입력하여 레지스트리 편집기를 실행한다.
![run dialog box](/assets/img/posts/2022-01-02-remove-bing-search/runDialogBox.png)
_실행_
![Registry Editor](/assets/img/posts/2022-01-02-remove-bing-search/registryEditor.png)
_레지스트리 편집기_

편집기를 실행했으니 원하는 부분에 키를 생성해야한다

```registry
컴퓨터\HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows
```
위 경로로 이동한 후 우클릭을 통해 키를 생성하자

![create Key](/assets/img/posts/2022-01-02-remove-bing-search/createKey.png)

새로 만들기(N) -> 키(K)<br/>

<br/>
![rename Key](/assets/img/posts/2022-01-02-remove-bing-search/renameKey.png)
생성된 폴더이름을 `Explorer`로 수정<br/>

<br/>
![create Value](/assets/img/posts/2022-01-02-remove-bing-search/createValue.png)
폴더에 들어가서 빈 공간에서 우클릭<br/>
새로 만들기(N) -> DWORD(32-bit) 값(D)<br/>

<br/>
![rename Value](/assets/img/posts/2022-01-02-remove-bing-search/renameValue.png)
생성된 레지스트리 이름 `DisableSearchBoxSuggestions`로 수정<br/>

<br/>
![set 1](/assets/img/posts/2022-01-02-remove-bing-search/setValue.png)

더블클릭해서 값 1로 변경 후 저장<br/>
이제 재부팅하면 웹 검색이 없어진다!<br/>

![result](/assets/img/posts/2022-01-02-remove-bing-search/result.png)

## Reference
[How to Remove Bing Search Results From Windows 11 Start Menu](https://beebom.com/how-remove-bing-search-results-windows-11/){: target="_blank"}