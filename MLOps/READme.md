# MLOps

## MLOps 세분화
---
MLOps = ModelOps + DataOps + DevOps

- ModelOps : 모델을 개발하면서 생기는 운영(모델 관리)
- DataOps : 데이터와 관련된 운영(데이터 엔지니어링, 데이터 관리)
- DevOps : 소프트웨어 개발과 관련된 운영(CI/CD)

## Data science steps for ML
---
먼저 business use case와 success criteria들을 정하고 나서 ML 모델을 프로덕션에 배포하기까지, 수동이든 자동이든, 모든 ML 프로젝트에는 다음과 같은 스텝들이 수반된다.

1. Data Extraction(데이터 추출)\
    데이터 소스에서 관련 데이터 추출

2. Data Analysis(데이터 분석)\
    데이터의 이해를 위한 탐사적 데이터 분석(EDA) 수행
    모델에 필요한 데이터 스키마 및 특성 이해

3. Data Preparation(데이터 준비)\
    데이터의 학습, 검증, 테스트 세트 분할

4. Model Training(모델 학습)\
    다양한 알고리즘 구현, 하이퍼 파라미터 조정 및 적용
    output은 학습된 모델.

5. Model Evaluation(모델 평가)\
    holdout test set에서 모델을 평가
    output은 모델의 성과 평가 metric.

6. Model Validation(모델 검증)\
    기준치 이상의 모델 성능이 검증되고, 배포에 적합한 수준인지 검증

7. Model Serving(모델 서빙)\
   - 온라인 예측을 제공하기 위해 REST API가 포함된 마이크로 서비스
   - 배치 예측 시스템
   - 모바일 서비스의 embedded 모델

8. Model Monitoring(모델 모니터링)\
    모델의 예측 성능을 모니터링