---
title: 자율주행 자동차 개발기 Chapter 4. 트래킹 알고리즘 개발 1
author: seyeon
date: 2024-05-19 23:00:00 +0900
categories: [Project, Autonomous]
tags: [AI]
pin: false
math: true
mermaid: false
image:
  path: /assets/img/2024-05-19-autonomous-4/autonomous.png
  lqip: data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAwAAAAMCAMAAABhq6zVAAAAIGNIUk0AAHomAACAhAAA+gAAAIDoAAB1MAAA6mAAADqYAAAXcJy6UTwAAAGzUExURZCZp46WpK63y6u3zTRBWCAuQEVVaFVuhXyUsLXE3fH7/93o95eis/f//6y1xYmXtpSer7jE2rLA2G19lXWGm4CSpXCInH6VsrrI4v///5ykspWfs623zEZbbmN6joqasb7J3a20xaKqvZejuerw/bCxu5uis4ORpcHI2aShqZKUo6asvI6NmZKSn52frIJ/jJKSnnB4hYuQmgAAAIaJlXKBj3N7ggAAADs9Q3N2goaYpBYdHwAAAAUGBiAiJhAQEF1dZJebpomNkwAAAAAAAAAAAAAAAAEAABUVF0BBR1FRWExNVFFSWVFSWCcoKQAAAEZUaURSZEVWZmhyiaWuw1xnf2Rrjj1MXlJjbWx/hWh7jV5nfpGaroJ/l4FtizpIWoNufZGFj25/kFpdb4KImZGLn3dmfU5RaFNXbktUZmN1hIeWpFNXY3F1gYCCknRugVFTZ0dPYkRQYWp0hJKVoHp+inF0gWlreGlocldYZFBRX2xtfnN4i5GUo3p8iGNlbmFmcj5HUis1QVRdbV9rfUBARWRjao6RoV1oeVRhc3V8jIyToJCTon+DkWZufH2Ckf///2AqHZYAAABQdFJOUwAAAAAAAAAAAAAAAAAAAAATX1l3gnlfQCcBav79/vfgUBa8yhg98PZRQPF5LuZ/E8f6YgyP3C1cmPy3G63B7Pz+/ZMmq7jJ3ez2+vTeqVEvf2jsRwAAAAFiS0dEGexutYgAAAAHdElNRQfoARkONxXR9ms/AAAApElEQVQI12NgYGRiZmFlY+fg5OJm4BEQFBIWERUTl5DkZeCTkpYJCAySlZNX4GdQVAoOCQ0Lj4iMUlZhUFWLjomNi09ITFLXYNDUSk5JTUvPyMzK1mbQ0c3JzcsvKCwqLtFj0DcoLSuvqKyqrjE0YjA2qa2rb2hsam4xNWMwt7BsbWvv6OzqtrJmsLG1s3fo6e3rd3RyZnBxdXP38PTy9vH18wcAxQkoOT1ZzCgAAAAldEVYdGRhdGU6Y3JlYXRlADIwMjQtMDEtMjVUMTQ6NTQ6MjQrMDA6MDC62pzNAAAAJXRFWHRkYXRlOm1vZGlmeQAyMDI0LTAxLTI1VDE0OjU0OjI0KzAwOjAwy4ckcQAAACh0RVh0ZGF0ZTp0aW1lc3RhbXAAMjAyNC0wMS0yNVQxNDo1NToyMSswMDowMCFoQTcAAAAASUVORK5CYII=
  alt: autonomous
typora-root-url: ../
---

# 참고사항

이 글은 자율주행 자동차 개발 동아리에서 활동하며 배운 내용을 바탕으로 작성되었습니다.

제목이 **<u>자율주행 자동차 개발기</u>**이지만 제가 맡은 분야(캘리브레이션)를 중심으로 정리하였습니다. 따라서 실제 자율주행 자동차 개발에 필요한 모든 내용을 다루고 있지는 않습니다.

# 트래킹이란?

- 트래킹(tracking) 알고리즘: 연속된 이미지에서 물체의 움직임을 추적하는 것
- SORT(Simple Online and Realtime Tracking) 알고리즘: 가장 유명한 트래킹 알고리즘 중 하나
  - 칼만 필터와 헝가리안 알고리즘을 이용

## 트래킹 알고리즘의 기본 원리

1. 객체 정보(이미지 내 위치)를 저장할 리스트 정의
2. 모든 이미지에 대해 다음을 반복
   1. 모든 객체에 대해 다음을 반복
      1. 객체를 이전 이미지의 객체 정보와 비교
         1. 만약 거리가 특정 값 이하면 같은 객체로 판단해 객체 정보 업데이트
      2. 이전 객체 정보에서 같은 객체로 판단된 객체가 없을 경우 새로운 객체 추가

### python 코드

- 데이터: https://www.kaggle.com/datasets/trainingdatapro/cars-video-object-tracking

- dataset.py

  ```python
  from lxml import etree
  import os
  
  import numpy as np
  import cv2
  
  class CarDataset:
      def __init__(self, DATASET_DIR=""):
  		'''
  		출처: https://www.kaggle.com/code/creativepixel/train-yolov8-for-car-tracking/notebook
  		'''
          label2id = {"car": 0, "minivan": 1}
          id2label = {v: k for k, v in label2id.items()}
  
          image_boxes_dict = dict()
          annotations = etree.parse(os.path.join(DATASET_DIR, "annotations.xml")).getroot()
  
          for image in annotations.findall('image'):
              filepath = os.path.join(DATASET_DIR, image.attrib["name"]).replace(".png", ".PNG")
              w_img, h_img = float(image.attrib['width']), float(image.attrib['height'])
  
              boxes = []
              for box in image.findall('box'):
                  label = box.attrib['label']
                  xtl, ytl = float(box.attrib["xtl"]) / w_img, float(box.attrib["ytl"]) / h_img
                  xbr, ybr = float(box.attrib["xbr"]) / w_img, float(box.attrib["ybr"]) / h_img
                  xc, yc = (xbr + xtl) / 2, (ybr + ytl) / 2
                  yolo_box = [xc, yc, xbr - xtl, ybr - ytl]
                  box_data = [label2id[label]] + yolo_box
                  boxes.append(box_data)
  
              image_boxes_dict[filepath] = boxes
  
          self.image_boxes_dict = image_boxes_dict
          self.image_paths = sorted(list(image_boxes_dict.keys()))
  
      def __getitem__(self, index):
          '''
          index: int
          return: image(ndarray), boxes(list)
  
          box is [label, x_center, y_center, width, height]
  
          '''
  
          path = self.image_paths[index]
          image = cv2.imread(path)
  
          return image, self.image_boxes_dict[path]
      
      def __len__(self):
          return len(self.image_paths)
  
  ```

  - `__init__`: 데이터셋 폴더의 경로를 받아 데이터셋 객체를 초기화
  - `__getitem__`: 배열처럼 인덱스로 데이터셋에 접근할 수 있도록 설정
    - `(image, bounding_box)` 형태의 정보를 반환
  - `__len__`: 데이터셋의 길이를 반환

- tracker.py

  ```python
  from tqdm import tqdm
  
  import numpy as np
  import cv2
  
  from car_dataset import CarDataset
  
  class TrackingInfo:
      def __init__(self, center_x, center_y):
          self.start_pos = (center_x, center_y)
          self.final_pos = self.start_pos
  
  class Tracker:
      def __init__(self, DATASET_DIR=""):
          self.car_dataset = CarDataset(DATASET_DIR)
  
      def track(self, threshold=0.01, visualize=False):
          car_tracking_info = []
          for image, bboxes in tqdm(self.car_dataset, desc="tracking", mininterval=0.01):
              image_for_show = image[:]
  
              image_height, image_width, _ = image.shape
  
              for label, center_x, center_y, width, height in bboxes:
                  is_tracked = False
                  for i, info in enumerate(car_tracking_info):
                      if (center_x - info.final_pos[0])**2 + (center_y - info.final_pos[1])**2 < threshold**2:
                          car_tracking_info[i].final_pos = (center_x, center_y)
  
                          is_tracked = True
  
                          point1 = ((center_x - width / 2) * image_width, (center_y - height / 2) * image_height)
                          point1 = (int(point1[0]), int(point1[1]))
                          point2 = ((center_x + width / 2) * image_width, (center_y + height / 2) * image_height)
                          point2 = (int(point2[0]), int(point2[1]))
                          cv2.rectangle(image_for_show, point1, point2, (255, 0, 0), 1)
                          cv2.putText(image_for_show, str(i), (point1[0], point1[1] - 10), cv2.FONT_HERSHEY_SIMPLEX, 0.9, (255, 0, 0), 2)
                          break
                  
                  if not is_tracked:
                      car_tracking_info.append(TrackingInfo(center_x, center_y))
  
              if visualize:
                  cv2.imshow("tracking", image_for_show)
                  cv2.waitKey(0)
  
          cv2.destroyAllWindows()
  ```

  - `TrackingInfo`: 객체 정보 저장을 위한 클래스, 일종의 구조체
    - `start_pos`: 객체가 처음 탐지되었을 때의 위치
    - `final_pos`: 객체가 마지막으로 탐지된 위치
  - `Tracker`: 트래킹을 수행하는 객체
    - `__init__`: 데이터셋 객체 초기화
    - `track`: 앞에서 설명한 알고리즘을 수행하는 함수
      - `threshold`: 같은 물체로 판단할 최대 거리
      - `visualize`: 시각화 여부

## 기존 트래킹 알고리즘의 한계

- 물체가 많을 경우 서로 겹처 트래킹에 오류가 생길 수 있음
- 중간에 일시적으로 객체 탐지에 실패하면 이전과 이후 물체를 다르게 판단

## 해결 방안

- 물체의 속도(위치 변화)를 저장해 겹쳤을 때 발생하는 오류를 방지
- 이전 이미지만이 아닌 $$k$$​개의 이전 이미지와 비교해 순간적으로 탐지에 실패하는 경우를 대비

# 앞으로의 목표

- 물체의 속도가 `threshold`보다 큰 경우 다른 객체로 판단되는 문제 해결
- 겹치는 문제 해결을 위해 `TrackingInfo`에 속도를 저장
- $$k$$개의 이전 이미지와 비교하기 위해 `TrackingInfo`에 `final_pos` 외에 추가적인 정보를 저장
- 하늘에서 바라본 데이터셋이 아닌 자동차에서 1인칭으로 바라본 데이터에서도 트래킹 가능하도록 개발
  - 라이다 없이 카메라 만으로 동적 물체와 정적 물체를 구분하는 것이 목표



