---
title: 자율주행 자동차 개발기 Chapter 2. Ros Publisher, Subscriber
author: seyeon
date: 2024-01-26 23:00:00 +0900
categories: [Project, Autonomous]
tags: [AI]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-01-26-autonomous-2/autonomous.png
  lqip: data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAwAAAAMCAMAAABhq6zVAAAAIGNIUk0AAHomAACAhAAA+gAAAIDoAAB1MAAA6mAAADqYAAAXcJy6UTwAAAGzUExURZCZp46WpK63y6u3zTRBWCAuQEVVaFVuhXyUsLXE3fH7/93o95eis/f//6y1xYmXtpSer7jE2rLA2G19lXWGm4CSpXCInH6VsrrI4v///5ykspWfs623zEZbbmN6joqasb7J3a20xaKqvZejuerw/bCxu5uis4ORpcHI2aShqZKUo6asvI6NmZKSn52frIJ/jJKSnnB4hYuQmgAAAIaJlXKBj3N7ggAAADs9Q3N2goaYpBYdHwAAAAUGBiAiJhAQEF1dZJebpomNkwAAAAAAAAAAAAAAAAEAABUVF0BBR1FRWExNVFFSWVFSWCcoKQAAAEZUaURSZEVWZmhyiaWuw1xnf2Rrjj1MXlJjbWx/hWh7jV5nfpGaroJ/l4FtizpIWoNufZGFj25/kFpdb4KImZGLn3dmfU5RaFNXbktUZmN1hIeWpFNXY3F1gYCCknRugVFTZ0dPYkRQYWp0hJKVoHp+inF0gWlreGlocldYZFBRX2xtfnN4i5GUo3p8iGNlbmFmcj5HUis1QVRdbV9rfUBARWRjao6RoV1oeVRhc3V8jIyToJCTon+DkWZufH2Ckf///2AqHZYAAABQdFJOUwAAAAAAAAAAAAAAAAAAAAATX1l3gnlfQCcBav79/vfgUBa8yhg98PZRQPF5LuZ/E8f6YgyP3C1cmPy3G63B7Pz+/ZMmq7jJ3ez2+vTeqVEvf2jsRwAAAAFiS0dEGexutYgAAAAHdElNRQfoARkONxXR9ms/AAAApElEQVQI12NgYGRiZmFlY+fg5OJm4BEQFBIWERUTl5DkZeCTkpYJCAySlZNX4GdQVAoOCQ0Lj4iMUlZhUFWLjomNi09ITFLXYNDUSk5JTUvPyMzK1mbQ0c3JzcsvKCwqLtFj0DcoLSuvqKyqrjE0YjA2qa2rb2hsam4xNWMwt7BsbWvv6OzqtrJmsLG1s3fo6e3rd3RyZnBxdXP38PTy9vH18wcAxQkoOT1ZzCgAAAAldEVYdGRhdGU6Y3JlYXRlADIwMjQtMDEtMjVUMTQ6NTQ6MjQrMDA6MDC62pzNAAAAJXRFWHRkYXRlOm1vZGlmeQAyMDI0LTAxLTI1VDE0OjU0OjI0KzAwOjAwy4ckcQAAACh0RVh0ZGF0ZTp0aW1lc3RhbXAAMjAyNC0wMS0yNVQxNDo1NToyMSswMDowMCFoQTcAAAAASUVORK5CYII=
  alt: autonomous
typora-root-url: ../
---

# 참고사항

이 글은 자율주행 자동차 개발 동아리에서 활동하며 배운 내용을 바탕으로 작성되었습니다.

제목이 **<u>자율주행 자동차 개발기</u>**이지만 제가 맡은 분야(캘리브레이션)를 중심으로 정리하였습니다. 따라서 실제 자율주행 자동차 개발에 필요한 모든 내용을 다루고 있지는 않습니다.

# 1. ROS의 구조

## 1. 마스터(master)

- 전체를 관리하는 관리자
- 노드들에게 이름을 부여하며 서로간의 연결을 관리
- `roscore` 명령어를 통해 실행됨

## 2. 노드(node)

- 실행할 수 있는 최소 단위
- 값을 받거나 내보낼 수 있음

## 3. 메시지(message)

- 노드가 데이터를 주고 받을 때 사용하는 데이터
- `string`, `Int` 등의 기본 메시지를 사용하거나 필요에 따라 커스텀 메시지를 만들 수도 있음

## 4. 토픽(topic)

- 메시지를 교환하는 버스
- 노드는 자신이 **어떤 노드와 통신하는지 모르지만** 특정 **토픽을 구독**해서 정보를 받아옴

## 5. 퍼블리셔(publisher)

- 메시지를 보내는 역할

## 6. 서브스크라이버(subscriber)

- 메시지를 받는 역할

# 2. Catkin 워크스페이스 생성

- catkin: ros의 빌드 시스템
- catkin 워크스페이스를 만들어 패키지를 관리

```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src
catkin_init_workspace
cd ~/catkin_ws
catkin_make
source ~/catkin_ws/devel/setup.bash
```

- `mkdir -p ~/catkin_ws/src`: home을 기준으로 catkin_ws 폴더와 그 안에 src 폴더를 생성
- `cd ~/catkin_ws/src`: 1.에서 만든 src 폴더로 이동
- `catkin_init_workspace`: 워크스페이스 초기화
- `cd ~/catkin_ws`: catkin_ws로 이동
- `catkin_make`: 패키지 빌드
- `source ~/catkin_ws/devel/setup.bash`: 셋업
  - 터미널을 켤때마다 실행해주어야 함
  - 자동 실행을 원한다면 `echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc` 명령어 입력
    - 터미널이 켜질때마다 실행되는 `.bashrc` 파일에 셋업 명령어를 등록

# 3. Catkin 패키지 생성

``` bash
cd ~/catkin_ws/src
catkin_create_pkg 패키지명 라이브러리 # 추천: catkin_create_pkg 패키지명 std_msgs rospy roscpp
```

- `cd ~/catkin_ws/src`: 패키지가 저장되는 경로인 `./src`로 이동
- `catkin_create_pkg 패키지명 std_msgs rospy roscpp`: 원하는 패키지명과 라이브러리들을 추가하여 패키지 생성
  - `catkin_create_pkg 패키지명 std_msgs rospy roscpp`와 같이 여러 라이브러리를 추가할 수 있음
- `rospack find 패키지명` 명령어를 통해 패키지가 정상적으로 생성되었는지 확인 가능

# 4. Publisher

1. `~/catkin_ws/src/패키지명/src` 경로에 파이썬 파일 생성

   - `cat  > pub.py` 또는 vscode, 텍스트 에디터 등을 이용해 생성

2. publisher 코드

   ``` python
   #!/usr/bin/python3
   
   import rospy # rospy 라이브러리 추가
   from std_msgs.msg import Int64 # 사용할 메시지 타입 추가 (Int64, String 등)
   
   if __name__ == '__main__':
   	rospy.init_node("node_name1") # 노드 초기화, 노드 이름 설정
   	
   	publisher = rospy.Publisher(name="topic_name", data_class=Int64) # publisher 생성, 토픽 이름, 메시지 타입 설정
   	
   	r = rospy.Rate(1) # hz 설정, 1초에 몇번 통신할지 설정 (여기서는 1번)
   	
   	while not rospy.is_shutdown(): # rospy가 종료되지 않았다면 계속 실행
   		msg = Int64() # 메시지 선언
   		msg.data = 123 # 메시지에 값 할당
   		
   		rospy.loginfo(msg) # 메시지 정보 출력
   		
   		publisher.publish(msg) # 메시지 전송(publish)
   		
   		r.sleep() # rospy.Rate()를 통해 설정된 주기까지 잠시 정지
   ```

3. `chmod +x pub.py`: 생성한 파이썬 파일을 실행 가능한 상태로 변경

## 5. Subscriber

1. `~/catkin_ws/src/패키지명/src` 경로에 파이썬 파일 생성

   - `cat  > sub.py` 또는 vscode, 텍스트 에디터 등을 이용해 생성

2. subscriber 코드

   ``` python
   #!/usr/bin/python3
   
   import rospy # rospy 라이브러리 추가
   from std_msgs.msg import Int64 # 사용할 메시지 타입 추가 (Int64, String 등)
   
   def callback(msg): # 메시지를 받았을 때 실행할 콜백 함수
       rospy.loginfo(msg) # 메시지 정보 출력
   
   if __name__ == '__main__':
       rospy.init_node("node_name2") # 노드 초기화, 노드 이름 설정
   
       subscriber = rospy.Subscriber(name="topic_name", data_class=Int64, callback=callback) # subscriber 생성, 토픽 이름, 메시지 타입 설정, 콜백 함수 설정
   
       r = rospy.Rate(1) # hz 설정, 1초에 몇번 통신할지 설정 (여기서는 1번)
       while not rospy.is_shutdown(): # rospy가 종료되지 않았다면 계속 실행
           r.sleep() # rospy.Rate()를 통해 설정된 주기까지 잠시 정지
   ```

3. `chmod +x sub.py`: 생성한 파이썬 파일을 실행 가능한 상태로 변경

# 6. Publisher, Subscriber 테스트

아래 코드는 각각 다른 터미널에서 진행해야 합니다.(`# 터미널 n`으로 표기했습니다.)

``` bash
# 터미널 1
catkin_make
roscore
```

- 빌드 후 ros 실행

``` bash
# 터미널 2
rosrun 패키지명 pub.py
```

- publisher 실행

``` bash
# 터미널 3
rosrun 패키지명 sub.py
```

- subscriber 실행

``` bash
# 터미널 4
rosrun rqt_graph rqt_graph
rostopic echo topic_name
```

- `rosrun rqt_graph rqt_graph`: 모든 노드들과 이들 사이에 오고가는 토픽 확인

  ![rqt_graph](/assets/img/2024-01-26-autonomous-2/rqt_graph.png)

- `rostopic echo topic_name`: `topic_name`에서 오고가는 메시지 확인
