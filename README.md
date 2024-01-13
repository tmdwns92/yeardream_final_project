# yeardream_final_project



<p>
<img src="images/Cover.png">
</p>



### 1. 프로젝트 주제

- SI 기업에서 진행했던 폴리에스테르 염색 공정 최종 염색 색상 예측 모델 고도화

### 2. 대회 기간

- 프로젝트 기간 : 23.11.06 ~ 23.12.14

### 3. 가설 도출

- 리서치 및 SI 기업의 베이스라인을 실험함으로써 가설 도출
    - 단일값만 가진 feature를 제외했을 때, 대부분이 제외되며 염료관련 feature들이 높은 영향력을 가짐.
    - 염색농도를 결정하는데, 욕비(염색염료량/피염물의 중량)이 최종 색상 예측에 중요하게 작용
    - 기본 베이스라인 LSTM 모델이 염료정보를 포함한 연관 공정들을 함께 layer로 묶어준 부분이 성능향상에 기여했을 거라고 추정하여 feature engineering에 반영

- 가설
    - 단방향 시계열 특성이 크지 않고, 염색 Layer 내 염료 feature들의 영향력이 클 것이라는 가설 도출

### 4. 프로젝트 목적

- 공정을 이해하고, 그에 맞는 feature engineering과 모델 개발
- 베이스라인 모델의 색차(cie94) 0.9보다 좋은 성능의 모델 개발
    - 기업이 제시한 색차 공식(Cie 94)은 섬유 및 그래픽 아트 산업 종사자들이 사용하는 공식으로 사람 눈에 보이는 색상과 유산한 좌표계인 CIE LAB 기반(L*, a*, b*)으로 구하는 색차이다.

![Untitled](https://github.com/jun-suk/PJT_color_prediction/assets/73885257/daff91cb-33ec-4143-ac57-3cdfa9182185)

### 5. 프로젝트 내용

- 팀원들끼리 R&R을 나눠 각 모델 별로 고도화 작업 진행
    
    ![Untitled](https://github.com/jun-suk/PJT_color_prediction/assets/73885257/c92e132a-f807-4b26-ae5c-d5a7d4f25278)
    
- 기존 베이스모델의 공정 layer 순서를 바꿔가며, 단방향 시계열 특성이 강한지 확인
    
    ![Untitled](https://github.com/jun-suk/PJT_color_prediction/assets/73885257/7765ff62-93b4-4702-9c7b-42fda6690014)
    
- TFT 모델을 맡아 단방향 시계열 특성이 약한다는 실험 결과에 따라 Varable Selection Network만 구성하여 실험

![Untitled](https://github.com/jun-suk/PJT_color_prediction/assets/73885257/b9fa029b-75e4-4b69-8d44-e08cd8bbfbb6)

### 6. 결과

- 주어진 metric인 색차(cie 94) 기준 성능 향상을 보임
    - 베이스라인 모델(0.9) → TFT 변형 모델(0.68)
- 염색공정 현업 기준에 따라, Test 데이터 셋에서 색차 1이 넘는 공정(row)의 갯수도 보조지표로 확인결과, 성능 향상을 보임
    - 베이스라인 모델(82개) → TFT 변형 모델(47개)
