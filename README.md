# 🚗 으랏차 🚗 


### 프로젝트 소개
------------
자율  주행  RC카인  ‘으랏차’는  아두이노와 라즈베리파이를 이용하여  구현했습니다. <br>
‘으랏차’의  기능은  초음파  센서를  이용한  장애물  인식과 카메라를  이용한  신호등  인식, 차선  인식이  존재합니다. 

### 팀 내 역할
------------
차선 인식 및 차선 인식에 따른 방향 제어

###  주요 기능 및 실행 화면
------------
* 차선 인식
> 흑백화
```
gray = cv2.cvtColor(src, cv2.COLOR_BGR2GRAY)
```
> 모서리 검출
```
can = cv2.Canny(gray, 50, 200, None, 3)
```
> 관심구역 설정
```
rectangle = np.array([[(0, height), (120, 300), (520, 300), (640, height)]])
```
> 직선 검출
```
line_arr = cv2.HoughLinesP(masked_image, 1, np.pi / 180, 20, minLineLength=10, maxLineGap=10)
```
> 원본에 합성
```
mimg = cv2.addWeighted(src, 1, ccan, 1, 0)
```

<br>

* 방향제어
> arctan2 함수를 사용하여 각도를 계산하여 각도에 따른 진행 방향을 결정
```
 line_arr2[i] = np.append(line_arr[i], np.array((np.arctan2(l[1] - l[3], l[0] - l[2]) * 180) / np.pi))
```

### 사용 기술
------------
* Raspberry Pi
* Python
* OpenCV

### 프로젝트 진행 기간
------------
2021년 9월 ~ 2021년 10월
