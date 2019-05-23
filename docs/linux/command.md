---
layout: default
title: Linux Command
parent: linux
nav_order: 3
---

# Linux Command
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

자주 쓰는 리눅스 명령어

## IP 확인

```shell
$ ifconfig | egrep "(^\\w|inet )"
$ ifconfig | grep "inet "
$ ip addr | grep "inet "
$ ifconfig -a | grep "inet " | grep "Bcast:" | awk '{print $2}' | awk -F: '{print $2}'
ip addr | grep "inet " | grep brd | awk '{print $2}' | awk -F/ '{print $1}'
192.168.0.39
```

## scp(secure copy) 사용

```shell
# 원격파일을 로컬로 복사
$ scp -P포트번호 username@원격서버주소:해당경로폴더/해당파일명 로컬저장소위치
(ex)  scp -P22 hanadmin@location.pg1.krane.9rum.cc:/hanmail/location_data/200_user_sample_20190429.dat /Users/kakao/desktop (로컬에서 입력)

# 로컬 폴더를 원격서버로 올리기
$ scp  -r 포트번호 로컬경로/해당파일 username@원격서버주소:해당경로폴더/
(ex) scp -r ./test_folder garden@192.168.0.30:/home/garden/dev (로컬에서 입력)
```

## 서버 외부와 통신
```shell
setproxy sudo -E [명령어]

# ex
setproxy sudo -E npm install express
```

## 파일 찾기

```shell
find [path?] -name '[file|folder]'

# example
$ find / -name "mongo*"
```

## 디렉토리 찾기
```shell
find [path?] -name '[file|folder]' -type d
```

## 폴더 이름 바꾸기

```shell
$ mv [before name] [after name]
```

## 파일 삭제
```shell
$ rm -rf [file|folder]
```