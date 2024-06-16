고급프로그래밍1_원혁 교수님 수업
📕프로젝트 소개
Tensorflow와 Keras를 활용한 AI 모델을 통해 피부암을 예측하는 시스템입니다. 이 프로젝트는 소비자와 환자 모두에게 피부암 예측 서비스를 제공하며, 예측을 통해 초기 치료 또는 병원에서의 진료를 받기 위한 도움을 주는 것을 목적으로 합니다.

목차
프로젝트 소개
목차
주요 기능
설치
사용 방법
출처
기여자
📌 주요 기능
데이터 로드 및 전처리
대규모 피부 이미지 데이터셋을 로드하고, 이를 AI 모델 학습에 적합하게 전처리합니다.
AI 모델 학습
Convolutional Neural Network (CNN) 기반의 AI 모델을 설계하고, 학습시킵니다.
예측 및 평가
학습된 모델을 통해 피부암 예측을 수행하고, 모델의 성능을 평가합니다.
실시간 예측
웹캠을 통해 실시간으로 피부 이미지를 캡처하고, 이를 기반으로 피부암 여부를 예측합니다.
이미지 예측
경로의 이미지를 학습된 모델로 피부암 여부를 예측합니다.
📥 설치
이 프로젝트를 설치하고 실행하려면 다음 단계를 따르세요:

데이터셋 다운로드 및 압축 해제
pip install kaggle
cd data kaggle datasets download -d kmader/skin-cancer-mnist-ham100000 tar -xvf skin-cancer-mnist-ham10000.zip del skin-cancer-mnist-ham10000.zip move skin-cancer-mnist-ham10000/* . #data하위 폴더 skin-cancer-mnist-ham10000에 데이터 파일들이 없는거라면 넘어간다 rmdir skin-cancer-mnist-ham10000 #data하위 폴더 skin-cancer-mnist-ham10000에 데이터 파일들이 없는거라면 넘어간다 cd ..

2. 필요한 라이브러리 설치
  ```shell
  pip install numpy==1.20.3
  pip install pandas==2.0.3
  pip install tensorflow==2.2.0
  pip install keras==2.4.0
  pip install opencv-python==4.9.0.80
  # 전체 복사 후 붙여넣기 하여 Enter 
  ```
  > **Note:** 이 프로젝트는 python 3.11.4 버전에서 테스트 되었습니다.

## 🛠 사용 방법
### 모델 학습
1. 데이터 디렉토리로 이동한 후 상위 디렉토리로 이동합니다:
  ```shell 
  cd data #현재의 경로가 file_last>data>가 아닌 file_last>라면 1번은 넘어가도 된다.
  cd ..
  ```
2. 모델을 학습시킵니다( 모델 학습이 되지 않는다면 pandas문제 또는 visual c++문제로
  학습을 넘어가고 ):
  ```shell
  python model_train.py
  ```
3. 학습된 모델의 데이터를 보고싶다면
```shell
python h5_out.py
읽을 모델을 입력하세요 : 이란 문구가 나오면 ./outputs/model.h5 를 입력한다.
실행 후 content 폴더에 model_content.txt파일로 데이터 파일이 txt화 된 파일이 생길 것 이다.
실시간 웹캠 예측
웹캠 프로그램을 실행합니다:
python main_cv.py
사용 할 모델의 경로를 입력합니다.
./outputs/model.h5 #모델 학습이 되지 않는다면 사전에 있던 model.h5입력
로딩 후 카메라가 켜지면 c 버튼을 눌러 캡처합니다. 캡처된 이미지는 captured 폴더에 저장됩니다.
예측 결과와 신뢰도가 터미널에 표시됩니다. q를 눌러 웹캠을 종료할 수 있습니다.
이미지 파일 예측
이미지 파일 예측 프로그램을 실행합니다:
python main_image.py
모델 경로와 이미지 경로를 입력합니다. 예시:
훈련된 모델의 경로를 입력하세요 : ./outputs/model.h5
이미지의 경로를 입력하세요 : ./image/sample/ISIC_0024315.jpg
예측 결과와 신뢰도가 터미널에 표시되며, image/output 폴더에 결과 이미지가 생성됩니다.
📚 출처
HAM10000 데이터셋: 이 프로젝트에서 사용된 데이터셋은 Kaggle의 HAM10000 데이터셋입니다.
kaggle 데이터 가져오기 데이터 셋을 가져오기 위해 참조한 코드입니다.
👥 기여자
[202336905 이성준] : 프로젝트 구현 및 README.md 작성
[202131162 박원빈] : 프로젝트 사용 PPT제작
kaggle-dataset
