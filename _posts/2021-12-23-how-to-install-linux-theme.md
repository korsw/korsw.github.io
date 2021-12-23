---
title: Linux에 테마 적용하기 (WhiteSur Gtk Theme)
author: korsw
date: 2021-12-23 00:55:39 +0900
categories: [WSL, ubuntu]
tags: wsl, ubuntu, theme, gnome
---

GUI를 사용하는김에 기본 우분투의 ui보단 이쁜걸 써보자<br/>
이번에 적용할 테마는 맥 감성을 지닌 [**WhiteSur Gtk Theme**](https://www.gnome-look.org/p/1403328/)다.
<br/>
생각보다 간단하게 적용할 수 있었다.<br/><br/>

## 그놈 기능 개선 도구 (Gnome Tweaks tool) 설치
그놈 기능 개선 도구(Gnome Tweaks tool)는 Gnome 확장 플러그인 관리 도구이다.<br/>
이 트윅을 설치해야 앞으로 적용할 테마를 적용할 수 있다.<br/>
```console
sudo apt install gnome-tweak-tool -y
```
위 명령어로 그놈 트윅을 설치할 수 있다.<br/>
```console
gnome-tweaks
```
위 명령어로 그놈 트윅을 실행할 수 있다.
![run-gnome-tweaks](/assets/img/posts/2021-12-23-how-to-install-linux-theme/run gnome-tweaks.png){: width="1086" height="542"}
_실행된 gnome-tweaks_



## 테마 설치
[**WhiteSur Gtk Theme**](https://www.gnome-look.org/p/1403328/)에서 맥스러운 테마를 다운받고,<br/>
압축을 푼 후 해당 디렉토리로 가서 명령어 한줄만 입력하면 된다.<br/>
```console
./install.sh -s
```
![run ./install.sh -s](/assets/img/posts/2021-12-23-how-to-install-linux-theme/run to install.sh -s.png){: width="1086" height="542"}
_./install.sh -s 실행_
<br/>
끝이다! 이제 그놈 트윅에서 설정만 하면 된다.

![set theme from an appearance](/assets/img/posts/2021-12-23-how-to-install-linux-theme/set theme from an appearance.png){: width="1086" height="542"}
_Appearance 탭에서 테마 설정_
gnome-tweaks을 실행한 후 Appearance - Theme - Applications에서 원하는 테마를 선택하면 적용된다.<br/>
![set WhiteSur-light theme from an appearance](/assets/img/posts/2021-12-23-how-to-install-linux-theme/set WhiteSur-light theme from an appearance.png){: width="1086" height="542"}
_WhiteSur-light theme 설정_
WhiteSur-light 테마를 적용했다. 뭔가 부족해보인다<br/>
좀 더 맥 감성을 살리기 위해 타이틀 바 탭에서도 몇가지 설정을 해주자<br/>
Windows Titlebars에서 세가지 설정을 해줘야한다.
![set WhiteSur-light theme from an titlebar](/assets/img/posts/2021-12-23-how-to-install-linux-theme/set WhiteSur-light theme from an titlebar.png){: width="1086" height="542"}
_titlebar 설정_
1. Maximize 체크
2. Minimize 체크
3. placement left 체크

테마 적용 완료!<br/>
추가적으로 [**파이어폭스에 테마 적용하는 방법**](https://github.com/vinceliuice/WhiteSur-gtk-theme/tree/master/src/other/firefox)대로 설정을 해봤지만 어쩌서인지 적용되지 않았다.<br/>
뭔가 잘못 설정한것 같다.<br/>
또한 sudo 권한으로 실행시 테마가 적용되지 않는 모습을 볼 수 있었다.