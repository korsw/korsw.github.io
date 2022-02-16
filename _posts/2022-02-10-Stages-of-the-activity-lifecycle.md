---
title: 안드로이드 활동 수명 주기 단계
author: korsw
date: 2022-02-10 22:27:07 +0900
categories: [Android, Android Theory]
tags: [android, activity, lifecycle]
---

<h1><span style ='color: red; font-weight:bold'>잘못된 정보가 많을 수 있는 포스트입니다. 점차 수정중입니다</span></h1>
<br/>
<br/>
안드로이드에도 최초 초기화부터 메모리 회수까지의 라이프 사이클이 존재한다.<br/>
액티비티를 실행하고, 뒤로가고, 일시정지하고, 등등... 다양한 경우가 있기 때문에 이에 맞춰 변하는 라이프 사이클을 알면 좋을 것 같아서 글을 작성한다<br/>
<br/>

## Activity Lifecycle

![Activity Lifecycle](/assets/img/posts/2022-02-10-Stages-of-the-activity-lifecycle/The-Activity-Lifecycle.png){: width="345" height="403"}
_액티비티 라이프 사이클_
<br/>
액티비티는 액티비티 스택에 의해서 관리된다.<br/>
보통 새로운 액티비티가 시작되면 스택의 맨 위에 배치되어 실행된다.<br/>
그 전에 실행되고 있던 액티비티는 스택의 아래에 남아있고, 새로운 액티비티가 종료되기 전까지는 다시 나타나지 않는다.<br/>
물론 한 화면에 여러개의 액티비티가 보일 수 있다.<br/>
<br/>
액티비티의 상태에는 네 가지가 존재한다.

| 상태 | 의미 |
|:---:|:---|
| **running** | 스택의 가장 높은 위치에 존재하며 화면에 실행중인 상태 |
| **visible** | 포커스는 잃었지만, 사용자에게 보이는 상태<br/>- 모든 상태와 정보를 유지하는 중 |
| **stopped** or **hidden** | 액티비티가 다른 엑티비티로 인해 완전히 가려지는 경우<br/>- 모든 상태와 정보를 유지하는 중<br/>- 다른 곳에서 메모리가 필요하면 kill 가능 |
| **destroyed** | 시스템으로부터 액티비티 종료가 되거나, kill 당하는 상태<br/>- 다시 표시될 때, 완전히 다시 시작하고 이전 상태로 복원해야 함 |

이러한 상태를 그림으로 표현하면 아래와 같다


![Activity Lifecycle Diagram](/assets/img/posts/2022-02-10-Stages-of-the-activity-lifecycle/Activity-Lifecycle-Diagram.png)
_액티비티 라이프 사이클 다이어그램_


## Reference

[Activity Lifecycle](https://developer.android.com/reference/android/app/Activity.html?hl=ko#activity-lifecycle){: target="_blank"}<br/>
[활동 수명 주기에 관한 이해](https://developer.android.com/guide/components/activities/activity-lifecycle?hl=ko){: target="_blank"}

