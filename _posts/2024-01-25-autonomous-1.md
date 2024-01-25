---
title: 자율주행 자동차 개발기 Chapter 1. Ubuntu(듀얼 부팅), ROS 설치
author: seyeon
date: 2024-01-25 23:00:00 +0900
categories: [AI, Autonomous]
tags: [AI]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-01-25-autonomous-1/autonomous.png
  lqip: data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAwAAAAMCAMAAABhq6zVAAAAIGNIUk0AAHomAACAhAAA+gAAAIDoAAB1MAAA6mAAADqYAAAXcJy6UTwAAAGzUExURZCZp46WpK63y6u3zTRBWCAuQEVVaFVuhXyUsLXE3fH7/93o95eis/f//6y1xYmXtpSer7jE2rLA2G19lXWGm4CSpXCInH6VsrrI4v///5ykspWfs623zEZbbmN6joqasb7J3a20xaKqvZejuerw/bCxu5uis4ORpcHI2aShqZKUo6asvI6NmZKSn52frIJ/jJKSnnB4hYuQmgAAAIaJlXKBj3N7ggAAADs9Q3N2goaYpBYdHwAAAAUGBiAiJhAQEF1dZJebpomNkwAAAAAAAAAAAAAAAAEAABUVF0BBR1FRWExNVFFSWVFSWCcoKQAAAEZUaURSZEVWZmhyiaWuw1xnf2Rrjj1MXlJjbWx/hWh7jV5nfpGaroJ/l4FtizpIWoNufZGFj25/kFpdb4KImZGLn3dmfU5RaFNXbktUZmN1hIeWpFNXY3F1gYCCknRugVFTZ0dPYkRQYWp0hJKVoHp+inF0gWlreGlocldYZFBRX2xtfnN4i5GUo3p8iGNlbmFmcj5HUis1QVRdbV9rfUBARWRjao6RoV1oeVRhc3V8jIyToJCTon+DkWZufH2Ckf///2AqHZYAAABQdFJOUwAAAAAAAAAAAAAAAAAAAAATX1l3gnlfQCcBav79/vfgUBa8yhg98PZRQPF5LuZ/E8f6YgyP3C1cmPy3G63B7Pz+/ZMmq7jJ3ez2+vTeqVEvf2jsRwAAAAFiS0dEGexutYgAAAAHdElNRQfoARkONxXR9ms/AAAApElEQVQI12NgYGRiZmFlY+fg5OJm4BEQFBIWERUTl5DkZeCTkpYJCAySlZNX4GdQVAoOCQ0Lj4iMUlZhUFWLjomNi09ITFLXYNDUSk5JTUvPyMzK1mbQ0c3JzcsvKCwqLtFj0DcoLSuvqKyqrjE0YjA2qa2rb2hsam4xNWMwt7BsbWvv6OzqtrJmsLG1s3fo6e3rd3RyZnBxdXP38PTy9vH18wcAxQkoOT1ZzCgAAAAldEVYdGRhdGU6Y3JlYXRlADIwMjQtMDEtMjVUMTQ6NTQ6MjQrMDA6MDC62pzNAAAAJXRFWHRkYXRlOm1vZGlmeQAyMDI0LTAxLTI1VDE0OjU0OjI0KzAwOjAwy4ckcQAAACh0RVh0ZGF0ZTp0aW1lc3RhbXAAMjAyNC0wMS0yNVQxNDo1NToyMSswMDowMCFoQTcAAAAASUVORK5CYII=
  alt: autonomous
typora-root-url: ../
---

# 참고사항

이 글은 동국대학교 자율주행 자동차 개발 동아리 **<u>MACARON</u>**에서 활동하며 배운 내용을 바탕으로 작성되었습니다.

제목이 **<u>자율주행 자동차 개발기</u>**이지만 제가 맡은 분야(차선 인식)를 중심으로 정리하였습니다. 따라서 실제 자율주행 자동차 개발에 필요한 모든 내용을 다루고 있지는 않습니다.

# 1. 우분투 설치

## 1. 디스크 파티션 분할

1. 윈도우 아이콘 우클릭 -> ***디스크 관리***
2. 우분투를 설치할 디스크 우클릭 -> ***볼륨 축소***
3. ***축소할 공간 입력***에 25GB(우분투 권장) 이상 입력 -> ***축소*** 버튼

## 2. 부팅 USB 제작

1. 우분투([설치 홈페이지](https://ubuntu.com/desktop)) ISO 파일 설치

2. 부팅 USB로 만들 USB 연결

3. Rufus([설치 홈페이지](https://rufus.ie/ko/)) 설치, 실행

   ![rufus](/assets/img/2024-01-25-autonomous-1/rufus.png)

4. 속성 선택

   - 장치 - 원하는 USB 선택

   - 선택 - 1에서 설치한 ISO 파일 선택

   - 파티션 구성 - 우분투를 설치할 디스크에 맞는 파티션 구성 선택

     ![디스크 우클릭 속성 클릭](/assets/img/2024-01-25-autonomous-1/image-20240125223829270.png)

     - 디스크 관리에서 우분투를 설치할 디스크 우클릭 -> 속성

     ![파티션 형식](/assets/img/2024-01-25-autonomous-1/partition.png)

     - 파티션 형식 확인(저의 경우 GPT)

   - 시작 버튼

## 3. 우분투 설치

1. 컴퓨터 재부팅 -> 바이오스 진입
2. 우분투 USB 선택
3. 정보 입력
4. ***Installation type***에서 ***Something else*** 선택
5. ***free space***(분할한 파티션) 더블 클릭 또는 `+` 입력 -> ***Mount point***에 `/` 입력 -> OK 버튼 -> Install Now -> Continue
6. 나머지 정보 입력

## 와이파이 인식이 안되는 경우!

노트북 와이파이 모듈에 따라 와이파이 인식이 안되는 경우가 있습니다.(저의 경우 Intel AX210을 사용하는 노트북이었습니다. 와이파이 모듈 정보는 메인보드 또는 노트북 회사 제품상세에서 찾을 수 있습니다.)

이 경우 와이파이 드라이버를 따로 설치해주어야 와이파이를 인식할 수 있습니다.

저는 노트북에 LAN 포트가 없어 스마트폰과 **블루투스 테더링**을 이용해 설치하였습니다. LAN 포트가 있으시다면 **유선랜**을 사용하시면 됩니다.

### 와이파이 드라이버 설치 방법

1. [이곳](https://bit.ly/3SxhuFB)에서 `.deb`로 끝나는 파일 중 최신 파일을 설치
2. 터미널에서 `cd 경로` 명령어로 설치한 경로에 이동해 `sudo dpkg -i 파일이름`을 입력
   - 만약 에러가 발생하는 경우 `sudo apt install dkms libc6-dev libc-dev-bin`를 입력 후 `sudo apt --fix-broken install`를 입력
   - 이제 다시 `sudo dpkg -i 파일이름` 입력
3. 재부팅

# 2. ROS 설치

1. ros 홈페이지에서 패키지를 받아 올 수 있도록 설정

    ``` bash
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    ```

2. `curl` 설치

    ``` bash
    sudo apt install curl
    ```

3. 설치 키 설정

    ``` bash
    curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
    ```

4. apt 업데이트

    ``` bash
    sudo apt update
    ```

5. ros noetic 설치

   ```bash
   sudo apt install ros-noetic-desktop-full
   ```


6. 터미널을 켤 때마다 setup을 해줘야 하므로 `~/.bashrc`에 setup.bash 추가(`~/.bashrc`는 터미널이 실행될 때마다 실행됨)

   ``` bash
   echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
   source ~/.bashrc
   ```

7. 필요한 라이브러리들 설치

   ``` bash
   sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential python3-roslaunch
   ```

8. `rosdep` 설정(`rosdep`은 ros dependencies의 약자로 여러 패키지를 모아놓고 관리하는 도구)

   ``` bash
   sudo rosdep init
   rosdep update
   ```
   
9. ros 실행

   ``` bash
   roscore
   ```
