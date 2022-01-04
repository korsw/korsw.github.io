---
title: TextView 사용법
author: korsw
categories: [Android, Android Kotlin]
tags: [android, kotlin, View]
---

안드로이드에서 텍스트를 띄우는 방법은 간단하다.<br/>
그냥 TextView를 쓰면 된다!

## TextView 생성 및 위치 설정

![textViewDragAndDrop](/assets/img/posts/2022-01-04-create-TextView/textViewDragAndDrop.png)
안드로이드 스튜디오를 킨 후 xml Palette에서 드래그 앤 드롭을 하거나,

![textViewWriteInXml](/assets/img/posts/2022-01-04-create-TextView/textViewWriteInXml.png){: width="100%" height="100%"}
우측 상단에 code를 누른 후 xml에 직접 작성해주면 된다.<br/>

이때 두 방법 모두 에러가 발생하는 것을 알 수 있는데 두가지 이유이다.<br/>
1. **<span style="color:red">Missing Constraints in ConstraintLayout</span>**<br/>레이아웃 배치가 명확하지 않아 앱 실행시 원하는 위치에 보이지 않을 가능성에 대한 경고
2. **<span style="background-color:yellow" >Hardcoded text</span>**<br/>@string resource 사용 권장

2번은 편의성을 위한 경고이지만 1번은 심각하다. 정말 원하는 동작이 이루워지지 않을 가능성이 크기 때문이다.<br/>
이를 해결하기 위한 방법은 단순하다 Layout에 대한 수평(horizontal), 수직(vertical)을 설정해주면 된다.<br/>

![setHorizontalVerticalDesign](/assets/img/posts/2022-01-04-create-TextView/setHorizontalVerticalDesign.png)
_디자인뷰에서 설정_
파란색 원을 드래그해서 상위레이아웃에 제약조건을 맞추거나 직접 숫자를 설정하면 된다.

![setHorizontalVerticalWriteInXml](/assets/img/posts/2022-01-04-create-TextView/setHorizontalVerticalWriteInXml.png)
_xml에 작성방법_
직접 작성하기 위해선 알아야할것이 margin과 layout_constrain형식들이다.<br/>

### margin

| margin | 의미 | 예시 |
|---|:---|:---|
| layout_marginStart | 시작(왼쪽)으로부터의 간격 | android:layout_marginStart="100dp" |
| layout_marginTop | 상단으로부터의 간격 | android:layout_marginTop="100dp" |
| layout_marginEnd | 끝(오른쪽)으로부터의 간격 | android:layout_marginEnd="100dp" |
| layout_marginBottom | 하단으로부터의 간 | android:layout_marginBottom="100dp" |

모두 안하고 수직,수평 하나씩 해줘도 된다.

### layout_constrain

| layout_constrain | 의미 | 예시 |
|---|:---|:---|
| layout_constraintTop_toTopOf | 시작(왼쪽)으로 제약 | app:layout_constraintBottom_toBottomOf="parent" |
| layout_constraintStart_toStartOf | 상단으로 제약 | app:layout_constraintEnd_toEndOf="parent" |
| layout_constraintEnd_toEndOf | 끝(오른쪽)으로 제약 | app:layout_constraintStart_toStartOf="parent" |
| layout_constraintBottom_toBottomOf | 하단으로 제약 | app:layout_constraintTop_toTopOf="parent" |

모두 안하고 수직,수평 하나씩 해줘도 된다. 굳이? 정말?

이와 같이 두가지 방법이 존재한다. 

## 텍스트 내용 설정
