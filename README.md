# travel_package
[Report](https://sangryu-notes.notion.site/c216db1e255349d88cf42d9765def2dd)
DACON 여행 상품 신청 여부 예측 경진대회
## 1. Project Overview
  - 목표
    - 여행 상품 신청 여부 예측(1: Taken, 0: Not Taken)
  - 모델
    - Extra Tree Classifier, Random Forest, Catboost등 다양한 분류 모델 실험

## 2. Code Structure
``` text
├── dataset (not in repo)
|   ├── sample_submission.csv
|   ├── train.csv
|   └── test.csv 
└── travel_prediction.ipynb
```

## 3. Detail 
  - Preprocess 
    - EDA를 통한 데이터 특성에 맞는 전처리 진행(Scaling, Correlation을 통한 결측치 제거 등)
  - Model
    - AutoML을 최적의 모델을 k-Fold를 이용하여 교차검증 한 후, 모델을 학습시킴(제출모델: Extra Tree Classifier)
    - 대회 마감 후, Catboost의 특성(범주화 데이터에 적합)을 이용 Optuna를 통한 Hyperparameter 최적화를 통한 추론 또한 진행
  - 최종성적
    - Public Score: 0.9011
    - Private Score: 0.89943
