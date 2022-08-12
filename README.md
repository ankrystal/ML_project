<img width="926" alt="image" src="https://user-images.githubusercontent.com/104750108/184321347-d7decdef-5b89-4fa3-9aa9-7ef57b782b9d.png">



# 📑 목차
* [1. Introduction](#-1-Introduction)
  * [기획 의도 및 프로젝트 목표](#-기획-의도-및-프로젝트-목표)

----------
## :tomato: Introduction
- 토마토는 가격 변동이 큰 작물로, 지역별 날씨 데이터 & 다양한 변수를 활용하여  예측한다면 가격 안정화를 시키는 의미있는 연구가 될 것으로 예상
- 타국 토마토 수입량 Top 5를 선정해서 추가적인 변수를 고려하면 가격을 예측하는데 좀 더 정확한 결과를 얻을 것으로 예상하고 해당 프로젝트를 진행
<img width="611" alt="image" src="https://user-images.githubusercontent.com/104750108/184447585-ef4b82b1-db09-47a1-aec5-63a4c7273eb5.png"> 
<img width="564" alt="image" src="https://user-images.githubusercontent.com/104750108/184447632-1b9eb8b3-6814-41c0-a373-a9e3ece594e9.png">

----------
## 🎯 Result

### 성능 비교 및 오차 결과
- Multiple Linear > Ridge > Lasso
<img width="730" alt="image" src="https://user-images.githubusercontent.com/104750108/184448121-743c8346-8e65-4756-be9a-c4bcbd9f1302.png">
<img width="672" alt="image" src="https://user-images.githubusercontent.com/104750108/184448409-1a5a81fb-dc09-4df7-ace4-f948852730a3.png">

----------

## :tokyo_tower: Modeling

### 1. Dataset
- 기상청, 농산물 유통정보서비스, 오피넷, 국가통계포털에서 정보수집
- 총 4개 데이터셋을 전처리 수행, 최종 1227개의 데이터 확보
<img width="1101" alt="image" src="https://user-images.githubusercontent.com/104750108/184449049-a58556bb-f637-475a-be64-8e6a16237b8f.png">

### 2. Library
!pip install scikit-learn





## 목표 : 토마토 예측 가격과 실제 가격의 오차 분석
## 기획 의도 : 
- 토마토는 가격 변동이 큰 작물로, 지역별 날씨 데이터 및 다양한 변수를 활용하여 예측한다면 가격 안정화를 시키는 의미있는 연구가 될 것으로 예상
- 타국 토마토 수입량 Top 5를 선정해서 추가적인 변수를 고려하면 가격을 예측하는데 좀 더 정확한 결과를 얻을 것으로 예상하고 해당 프로젝트를 진행 
## 데이터 수집 사이트
- 기상청
- 농산물유통종합정보시스템
- 국가통계포털
- 오피넷
## 모델 : Linear, Ridge, Lasso
