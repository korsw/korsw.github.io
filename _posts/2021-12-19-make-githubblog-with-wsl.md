---
title: GitHub 블로그 설정하기
author: korsw
date: 2021-12-19 19:03:00 +0900
categories: [WSL, Blog]
tags: [github, wsl, jekyll]
---


블로그를 만들어 공부 내용 정리를 하려다가 블로그 만드는 법도 정리하고자 한다.

[**GitHub**][GitHub]의 [**GitHub page**][GitHub page]라는 기능을 이용하여 배포를 할 수 있고, [**jekyll**][jekyll]를 이용해 쉽게 생성할 수 있다.

## GitHub page 생성하기

[**GitHub page**][GitHub page]로 사용할 repository를 새로 생성해야하는데 이때, Repository name을 [username].github.io로 설정해서 생성해야한다.

![create-github.io](/assets/img/2021-12-19-make-githubblog-with-wsl/create-github.io.png){: width="1086" height="542"}
_GitHub page 생성_

## 1. Ruby 설정하기
[**jekyll**][jekyll]를 이용해 블로그 테마를 설정하고 관리하기 위해서는 [**ruby**][ruby]를 설치해야한다.

### Ubuntu
```ubuntu
sudo apt-get install ruby-full build-essential zlib1g-dev
```

### Windows

<https://rubyinstaller.org/downloads/>

## 2. Jekyll 설치 및 테마 설정하기

[**jekyll**][jekyll]를 설치해보자

```공용
gem install jekyll bundler
```

### 테마 설정하기

다음과 같은 명령어로 기본 틀을 생성할 수 있다.

```?
jekyll new [경로]
```

그러나 내가 원하는건 보다 그럴듯한 테마를 설장하고 싶기 때문에 다른 분들이 만들어둔 테마를 가져올 것이다.


<https://jekyllthemes.io/>
<http://jekyllthemes.org/>
 
위와 같이 테마를 제공해주는 사이트는 많이 존재한다. 원하는 테마를 찾으면 그 테마를 다운로드한다.

그 후 직접 테마를 fork하거나 복붙하는건 본인의 마음이다

난 복붙이 편하기 때문에 먼저 생성한 [**GitHub page**][GitHub page]를 clone했다.

```?
git clone https://github.com/[username]/[username].github.io.git
```
이렇게 clone을 하고 그 후 단순하게 해당 경로에 테마를 복붙해버렸다.

그 후 해당 경로의 최상단으로 이동한 후에

```?
bundle install
```
를 입력해 bundle을 설치해준다.

이제 한번 홈페이지를 봐보자!

```?
bundle exec jekyll serve
```

webrick 오류가 발생한다면

```?
bundle add webrick
```

http://127.0.0.1:4000/의 주소가 출력되는데 이로 접속하면 테마가 적용된 것을 확인할 수 있다.

내가 작성하지 않은 글들이 존재한다. 이걸 초기화해야한다.

```?
bash tools/init.sh
```

테마마다 다를 수 있지만 내가 적용한 테마는 해당 쉘스크립트를 통해 초기화가 가능했다.


###  _congif.yml
자신에게 맞는 블로그를 설정하기 위해선  _congif.yml를 수정해야한다.

1. timezone: Asia/Seoul 	#시간을 설정
2. title: User’s blog		#타이틀 설정
3. description: 		#서브 타이틀 설정
4. url: ‘https://username.github.io’	#GitHub pages 주소 설정

이정도만 일단 수정하자

그리고 이제 GitHub와 연결할 시간이다

```?
git add -A
git commit -m "setTheme"
git push
```

이제 https://[username].github.io에 접속하면 블로그가 보인다!

반영되는데 시간이 좀 소요된다. 10분 이상 기다렸음에도 적용되지 않는다면

settings -> Github Pages -> 생성된 branch로 설정하면된다.

[GitHub]: https://github.com/
[GitHub page]: https://pages.github.com/
[jekyll]: https://jekyllrb.com/
[ruby]: https://rubyinstaller.org/