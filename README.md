RottenFruitsModel

# yolo 학습 시키기
1. [DarknetSetup.ipynb: ](https://github.com/RottenFruitsOSS/RottenFruitsModel/blob/master/DarknetSetup.ipynb) 
yolo 실행을 위한 darknet 설치 밀 환경 구축

2. [yolo-cherry.ipynb: ](https://github.com/RottenFruitsOSS/RottenFruitsModel/blob/master/yolo_cherry.ipynb)
yolo 학습 과정 정리


* 파일 설명

DarknetSetup : yolo 학습을 위해 gdrive에 darknet 설치 및 환경 구축

bazel_install : bazel 사용해서 .pb -> .tflite 변환 시도하려는 파일

tflite_convert : .weight -> .pb -> .tflite 변환 하려는 코드 / 다른 방법 시도 / tensorflow에서 제공하는 방법 사용해봄
