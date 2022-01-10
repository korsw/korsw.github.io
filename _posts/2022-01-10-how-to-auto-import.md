---
title: 안드로이드 스튜디오, import 자동 설정
author: korsw
date: 2022-01-10 22:56:55 +0900
categories: [Android, Android Kotlin]
tags: [android, androidstudio]
---

다른 클래스를 사용하거나 추가적은 라이브러리를 사용하는 등, import를 할 상황은 많이 있다. 너무 귀찮다!<br/>
다행히 안드로이드 스튜디오에서 이러한 import를 자동적으로 할 수 있는 설정을 제공하고 있다.<br/>
물론 자동 추가뿐만 아니라 사용하지 않는 import는 자동적으로 삭제해준다.

![SettingforNewProjects](/assets/img/posts/2022-01-10-how-to-auto-import/SettingforNewProjects.png)

1. File > New Project Settings > Preferences for New Projects

![AutoImport](/assets/img/posts/2022-01-10-how-to-auto-import/AutoImport.png)

2. Other Settings > Auto Import > **Add unambiguous imports on the fly, Optimize imports on the fly (for current project)** 체크

Add unambiguous imports on the fly는 자동 추가이며, Optimize imports on the fly는 자동 삭제이다<br/>

이렇게 설정하면 import가 정말 편해진다.
