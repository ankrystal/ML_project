<img width="1296" alt="image" src="https://user-images.githubusercontent.com/104750108/184453454-5e0c65b4-c903-402d-b9cd-f833d187c45f.png">

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
- 2016.1.1 ~ 2020.12.31 5개년도 데이터
- 총 4개 데이터셋을 전처리 수행, 최종 1227개의 데이터 확보
<img width="1101" alt="image" src="https://user-images.githubusercontent.com/104750108/184449049-a58556bb-f637-475a-be64-8e6a16237b8f.png">

### 2. Library
- scikit-learn을 활용하여 ML-pipeline을 설계했습니다.
```
pip install scikit-learn 
```

### 3. Preprocessing
- 결측치에 대한 고민
```
- 거래가 발생하지 않는 주말 및  공휴일의 데이터를 모두 제거하는 것이 모델의 성능 저하를 유발할까?
- 거래가 발생하지 않는 날 중 주말 데이터만 제거하고 공휴일의 가격 데이터는 0원으로 처리했을 때 모델 성능의 변화를 알 수 있을까? 
```
- 평균온도가 없는 날 존재
```
- 하루 전/후 평균값으로 대체
```
- 요일정보 숫자 변환
```
- One-Hot Encoding을 이용하여 요일정보 숫자로 변환
```
- 날짜 데이터 변환
```
- 날짜를 Year / Month / Day로 구분하여 데이터 처리
```

### 4. EDA & Model Selection

- 연도별 토마토 가격 추이 (단위 : 원/상품/5kg)
<img width="728" alt="image" src="https://user-images.githubusercontent.com/104750108/184451197-77089baa-3540-41c9-9a8f-c7541e03ea26.png">
 
- 월별 토마토 가격 추이 (단위 : 원/상품/5kg)
<img width="668" alt="image" src="https://user-images.githubusercontent.com/104750108/184451466-bb18e698-edae-40f3-835c-e999b016c05d.png">

- 컬럼 제거 전후 설명

|Model No|Group|Explanation|
|:------:|:---:|:---:|
|Model 1|원본 데이터|컬럼을 따로 제거 하지 않고 진행|
|Model 2|평균온도 제거|평균온도, 합계 일조시간, 합계 일사량, 평균 지면온도|
|Model 3|유류가격 제거|고급휘발유, 보통휘발유, 자동차용경유|
|Model 4|일조량 제거|강수량, 풍속, 평균 상대습도, 일 최심적설|
|Model 5|타국 수입량 제거|중국, 미국, 이탈리아, 칠레, 스페인 물량|

* 컬럼 제거 전 / 후 모델 성능 비교

||Model 1|Model 2|Model 3|Model 4|Model 5|
|:------:|:---:|:---:|:---:|:---:|:---:|
|Train_set|0.516|0.374|0.454|0.508|0.442|
|Test_set|0.526|0.411|0.458|0.518|0.458|


* 최종모델 선정

<img width="438" alt="image" src="https://user-images.githubusercontent.com/104750108/184452913-31b9c2a6-1c75-4147-8f2e-2a3fc3d347be.png">

-------

## 🍃 Limitations & Direction After




