Driver_Motion_With_CNN
----------------
![스크린샷 2024-10-08 205416](https://github.com/user-attachments/assets/1918145c-92ed-4a3b-80d6-19f5fe99abc9)

프로젝트 소개
----
이 프로젝트는 CNN 기법을 활용해 운전 중 발생할 수 있는 다양한 행동을 인식하고 분류하는 시스템을 구현하였으며, 
TensorFlow 데이터셋을 생성하고, 커스텀 CNN 아키텍처를 설계하여 입력 데이터에 대해 동작 인식 모델을 학습하도록 설계

프로젝트 전체 과정 및 커스텀 CNN 모델 아키텍처
---
![image](https://github.com/user-attachments/assets/54a012b7-a407-4372-8279-6ce6d6012336)


주요 기능
----
● TPU를 사용하여 학습 진행

● 데이터 로드 및 전처리 : os와 OpenCV를 사용하여 폴더에서 이미지 데이터를 로드하고, 해당 이미지에 레이블을 할당

● 데이터 증강: Tensorflow의 tf.keras.layers.를 사용해 랜덤 회전, 플립, 대비 조정을 통한 데이터 증강을 수행하여 모델의 일반화 성능 향상

● Tensorflow Dataset 생성 : tf.data.Dataset을 사용해 이미지 데이터와 레이블을 Tensorflow Dataset으로 변환, 데이터셋을 배치로 나누고 셔플 및 병렬 처리 적용

● CNN 모델 아키텍처 설계 : 여러 층의 Conv2D, BatchNormalization, MaxPooling2D 등을 쌓아 CNN 아키텍처 구현

● 모델 학습 및 검증 : sparse_categorical_crossentropy 손실 함수와 Adam 옵티마이저를 사용해 모델을 컴파일, EarlyStopping 콜백을 통해 검증 손실에 따라 학습 조기 종료

● 정확도, 손실 및 혼동 행렬(Confusion Matrix) 시각화 : Matplotlib을 사용하여 학습 과정에서의 정확도, 손실 및 혼동 행렬(Confusion Matrix) 시각화

개발 환경
----
● Google Colab : 클라우드 기반 Python 개발 환경으로 , TPU를 사용한 딥러닝 모델 학습에 사용

● Python : 주요 프로그래밍 언어로 사용

● Google Drive : 데이터를 저장하고 불러오는 파일 시스템으로 사용

기술 스택
----
● Tensorflow & Keras : 딥러닝 모델 구축 및 학습을 위해 사용. CNN 기반 모델과 데이터 증강 기법 사용

● OpenCV : 이미지 전처리 및 변환에 사용(이미지 파일 로드 및 색상 변환 등)

● Scikit-learn : 학습 데이터와 검증 데이터를 분리하는 데 사용 (train_test_split 함수)

● Matplotlib : 학습 과정에서의 정확도, 손실 및 혼동 행렬(Confusion Matrix)그래프 시각화

● tf.data API : Tensorflow 데이터셋 생성 및 배치 처리에 사용

● Data Augmentation : 랜덤 회전 , 수평 플립 , 대비 조정 등을 사용하여 데이터 증강

성능 평가
--
![image](https://github.com/user-attachments/assets/a1f5e178-9207-49ad-bb49-f06e77f79722)

● 훈련 및 검증 정확도가  각각 97%, 99%에 도달하고 손실이 각각 5%, 3%에 도달하여 모델의 학습이 성공적으로 이루어지고 있음을 확인

● Confusion Matrix 결과, 모델이 대부분의 클래스를 정확히 분류했으며, 일부 클래스에서 소수의 오차가 있었지만 전반적인 분류 성능에 큰 영향을 미치지 않음

이미지 예측
---
![image](https://github.com/user-attachments/assets/a1900427-0893-4d1e-b18d-bf83d190935d)

