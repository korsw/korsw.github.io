---
title: AndroidTest의 AndroidJUnit4 requires a public constructor that takes a Class 에러 해결
author: korsw
date: 2022-02-06 22:54:12 +0900
categories: [Android, AndroidTest]
tags: [android, androidtest]
---

안드로이드 테스트를 공부하던 중에 정말 짜증나는 에러가 있었다.<br/>

```consloe
java.lang.RuntimeException: Delegate runner androidx.test.internal.runner.junit4.AndroidJUnit4ClassRunner for AndroidJUnit4 requires a public constructor that takes a Class<?>.
```
<br/>

위 에러코드가 발생하면서 테스트 코드가 정상작동하지 않았다. 하루종일 헤매다가 gradle을 만지다가 해결했다.

```kotlin
dependencies {
    /**
     * dependencies 
     */
    implementation 'androidx.test.ext:junit-ktx:1.1.3'
    androidTestImplementation 'junit:junit:4.12'
    androidTestImplementation 'com.android.support.test.espresso:espresso-contrib:3.0.2'
}
```

문제없다고 생각했던,,, gradle 모듈을

```kotlin
dependencies {
    /**
     * dependencies 
     */
    implementation 'androidx.test.ext:junit-ktx:1.1.3'
    testImplementation 'junit:junit:4.+'
    androidTestImplementation 'androidx.test.ext:junit:1.1.2'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.3.0'
    androidTestImplementation 'androidx.test.espresso:espresso-contrib:3.3.0'
    debugImplementation "androidx.fragment:fragment-testing:1.3.3"
}
```
위와 같이 변경했더니 해결되었다.<br/>
~~아니 이게 뭐여~~

    

