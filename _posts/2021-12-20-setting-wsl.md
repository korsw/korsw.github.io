---
title: Windows 11에서 WSL2 사용 (Ubuntu 20.04 LTS)
author: korsw
date: 2021-12-20 21:01:59 +0900
categories: [WSL, ubuntu]
tags: [wsl, ubuntu]
---

윈도우가 10에서 11로 오면서 제일 크게 변했다고 생각하는 기능은 WSL이 아닐까 싶을 정도로 많이 좋아졌다.<br/>
GUI가 그냥 된다!<br/>


## WSL 설치하기

### 자동 설치
다 귀찮으니 깔끔하게 자동 설치하는 방법이 있다.

```powershell
wsl --install
```
이렇게 입력하면 최신 Linux 커널과, WSL 2를 다운로드 및 설정하며 Ubuntu가 설치된다.

### 수동 설치

수동 설치 방법도 있다. 생각보다 간단하다

1. Windows Subsystem for Linux 옵션 활성화
```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
<br/>
2. Virtual Machine Platform 옵션 활성화
```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
<br/>
3. Linux 커널 업데이트 패키지 다운<br/>
[**x64 WSL2 Linux 커널 업데이트 패키지**](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)<br/>
해당 파일을 받아 Linux 커널 업데이트 패키지를 설치한다.<br/>
<br/>
4. WSL 버전을 2로 설정
```powershell
wsl --set-default-version 2
```
<br/>
5. 원하는 Linux 설치
[**Microsoft Store**](https://aka.ms/wslstore)에 들어가서 해당 목록에 있는 것들 설치하거나 설치하고자하는 버전을 검색해서 다운로드 받으면 된다.<br/>
혹은 Powershell에서 검색해서 설치하는 방법도 있다.
```powershell
wsl --list --online
```
<br>
작성일 기준으로 아래와 같은 목록들이 출력된다.
```console
NAME		FRIENDLY NAME
Ubuntu		Ubuntu
Debian		Debian GNU/Linux
kali-linux	Kali Linux Rolling
openSUSE-42	openSUSE Leap 42
SLES-12		SUSE Linux Enterprise Server v12
Ubuntu-16.04	Ubuntu 16.04 LTS
Ubuntu-18.04	Ubuntu 18.04 LTS
Ubuntu-20.04	Ubuntu 20.04 LTS
```
이 목록들 중에서 원하는 리눅스를 설치하면 된다.
```powershell
wsl --install -d <distribution>
```
distribution에 원하는 리눅스 이름을 넣으면 설치가 진행된다.

## ubuntu 서버를 카카오 미러 서버로 변경
느린 패키지 업데이트 속도를 올리는 방법이다. 꼭 하자 정말 차원이 다르다<br/>
나는 Ubuntu 20.04 LTS를 설치했기때문에 그 기준으로 설명하겠다.<br/>
wsl Ubuntu 20.04 LTS를 실행하여 터미널을 키자.<br/>
```console
sudo vim /etc/apt/sources.list
```
/etc/apt/sources.list를 켜서 해당 리스트에 있는 서버를 몽땅 바꿀것이다.
```console
:%s /archive.ubuntu.com/mirror.kakao.com/
```
이러면 진짜 삶이 달라진다.<br/>

## GUI를 써보자
먼저 wsl을 업데이트 해주자
```powershell
wsl --update
```
윈도우 파워셸에서 입력하는 것이다<br/>
```powershell
wsl --shutdown
```
재부팅도 시켜주자<br/>
<br/>
그 후 wsl을 실행시킨 후 혹시 모르니 패키지도 업데이트 해주자
```console
sudo apt update
```
위 명령어로 패키지가 업데이트 될것이다.<br/>
기본 설정은 완료했으니 GUI 앱을 설치하여 실행할 것이다.
```console
sudo apt install gedit -y	#에디터
sudo apt install gimp -y	#이미지 편집기
sudo apt install nautilus -y	#GNOME desktop 파일 관리자
sudo apt install vlc -y		#멀티미디어 플레이어
sudo apt install x11-apps -y	#xclock, xcalc, xeyes 등 
```
```console
gedit	#gedit 실행!
```
![run-gedit](/assets/img/posts/2021-12-20-setting-wsl/run-gedit.png){: width="1086" height="542"}
_실행된 gedit 모습_
[테마](https://www.gnome-look.org/p/1403328/){: target="_blank"}를 설정해서 저런 모습이지만 GUI가 잘 실행된다.

## Reference

[Install WSL](https://docs.microsoft.com/en-us/windows/wsl/install){: target="_blank"}<br/>
[Manual installation steps for older versions of WSL](https://docs.microsoft.com/en-us/windows/wsl/install-manual){: target="_blank"}<br/>
[Run Linux GUI apps on the Windows Subsystem for Linux (preview)](https://docs.microsoft.com/en-us/windows/wsl/tutorials/gui-apps){: target="_blank"}<br/>