# 최종 최적화 모델 및 적용
Model 학습: https://github.com/RottenFruitsOSS/image-classification

Application: https://github.com/RottenFruitsOSS/RottenFruitsCamera

# Rotten Cherry Model 을 만들기 위해 진행한 model 학습
- 단계: 모델 학습 -> tflite 변환 -> application 적용
- yolo model은 object detection ML Kit 제공하는 application에 모델 교체 불가능
- image classification 사용해야됨

# Yolo Model 
[yolo_model_data](yolo_model_data) : yolo 모델 만들기

[metadata_create](metadata_create) : 메타데이타 만들기 위해 필요한 파일
### simple step
0. dataset: https://github.com/RottenFruitsOSS/DataSet
1. darknet 설치 -> [DarknetSetup.ipynb](yolo_model_data/DarknetSetup.ipynb)
2. configure file 설정하기 
```
custom_data.data
custome-train-yolo.cfg
classes.names   
train.txt       
test.txt        
```
3. yolo 학습 -> [yolo_cherry.ipynb](https://github.com/RottenFruitsOSS/RottenFruitsModel/blob/master/yolo_model_data/yolo_cherry.ipynb)

4. 파일 변환 과정 필요
```
.model -> .pb -> .tflite
```
tflite로 변환하기 위해서 .pb 파일에 추가적인 메타데이터 생성하여 tflite 파일 만들기

# Keras Model 만들기 
[fruits_360](fruits_360) : keras fruits-360모델 만들기

[Fresh_vs_Rotten](Fresh_vs_Rotten) : keras Fresh vs Rotten model 만들기

# Image Classification Model
[VGG16,RestNet50](VGG16,RestNet50) : 전이학습한 모델
### simple step
0. dataset: https://github.com/RottenFruitsOSS/DataSet
1. 설정 값 정의
```
BATCH_SIZE = 32
STEP_SIZE = 8
NUM_EPOCHS = 48
...
```
2. 전이학습 모델 변경
- 모델 정의 부분
```
baseModel = VGG16(weights="imagenet", include_top=False,
	input_tensor=Input(shape=(224, 224, 3)))
```
```
baseModel = ResNet50(weights="imagenet", include_top=False,
	input_tensor=Input(shape=(224, 224, 3)))
```
3. 학습
4. 변환 과정
