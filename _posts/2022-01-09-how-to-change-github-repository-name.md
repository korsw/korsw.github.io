---
title: Github 저장소(repository) 이름 수정하기
author: korsw
date: 2022-01-09 23:10:52 +0900
categories: [Tip, Github]
tags: [github]
---

GitHub를 사용하다가 간혹 저장소 이름을 변경하고 싶을 경우가 있다.<br/>
생각보다 간단한 방법으로 변경할 수 있는것이 너무 좋다 ㅎㅎ<br/>
<br/>

![repositoryNameSetting](/assets/img/posts/2022-01-09-how-to-change-github-repository-name/repositoryNameSetting.png)
_Repository name 변경_
우선 GitHub에서 변경할 저장소의 Setting에 들어가 Repository name을 변경해준다.<br/>
이러면 Github 저장소의 이름과 그에 따른 주소가 변경이 되지만 로컬의 git은 설정되지 않아 정상적인 동작이 되지 않을것이다.<br/>
remote설정을 변경해주자


<br/>
```powershell
git remote set-url origin "변경된 Github URL"
```

<br/>

```powershell
git remote -v	#변경 내역 확인
```
<br/>
이러면 변경이 완료되어 로컬에서 git이 문제없이 작동될것이다.