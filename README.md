# 딥러닝을 이용한 농작물 질병 분류 모델 성능 측정 및 비교 (Capstone design 2021-1)
* 소프트웨어융합학과 정환석

## 1. 과제 개요

### 가. 과제 선정 배경 및 필요성

한국의 기후 특성상 여름철 긴 장마 후 생육이 불량하고 고온 다습한 환경에서농작물 병해충으로 인한피해가 빈 번히 발생한다. 병해충에 걸린 농작물은 잎, 줄기, 열매 등에서 증상이 나타나는데 병해충으로인한 피해를 줄이기 위해서는 감염된 작물의 증상을 통해 초기에 진단하여 신속한 조치를 취해 확산을막는 것이 가장 중요하다. 하지 만 작물별 병해충의 종류는 매우 다양하고 그 진행 양상도 다르므로 인간이다양한 종류의 작물에 걸린 병을 모 두 진단하는데는 한계가 있다. 따라서 농작물의 증상을 통해 병을진단하는 연구가 필요하다.

### 나. 과제 주요내용

- 병해충에 걸린 농작물 데이터 수집

- 이미지 분류에서 높은 성능을 보인 VggNet, GoogLeNet, ResNet 모델의 사용 

- Drop Out, Batch Normalization, Data Augmentation 등 성능 향상을 시도

- 학습에 사용한 모델의 성능 측정 및 비교


## 2. 과제의 목표

### 가. 최종결과물의 목표 (정량적/정성적 목표 설정)

1) 농작물의 질병을 분류하는 딥러닝 모델의 성능을 90% 이상의 정확도를 목표로 한다.

2) Data Augmentation 추가하여 성능을 비교한다.

3) 학습에 사용한 각 모델별 성능을 비교한다.

### 나. 최종결과물의 세부내용 및 구성


1) 데이터 수집 및 전처리 (PlantVillage, AIHub)

2) CNN Architecture (VGGNet, GoogLeNet, ResNet)

3) Data Augmentation

4) 모델 성능 평가 지표

5) 모델별 성능 비교


## 3. 기대효과 및 활용방안

일반적으로 농가에서는 병해충에 대한 자기 진단이 어려워 전문가의 도움을 필요로 한다. 하지만, 농작물 질병 분 류 모델을 통해서 작물의 병해충을 초기에 인식하고, 그 병해충에 걸맞는 조치를 취해 병해충의 확산을 신속하게 방지할 수 있게 된다. 이러한 결과로, 수확량을 증가시킬 수 있을 것으로 예상되며, 농작물의 품질 또한 개선될 것 으로 예측된다. 19년 한국 농가의 병해충 피해액은 약 342억으로 집계됐다. 농작물 질병 분류 모델의 활용은 이 러한 한국 농가의 경제적 부담, 그리고 정부의 농가 지원금 부담을 조금은 덜어줄 것이라고 예상된다. 또한 현재 농업 분야에서 고령화 문제가 대두되고 있는 만큼, 이러한 농작물 질병 분류 모델은 농업의 진입장벽을 낮춰 젊은 층의 유입을 기대해 볼 수 있다.

## 4. 수행방법

### 가. 과제수행을 위한 도구적 방법

Python, Colab, Pytorch

### 나. 과제수행 계획

이미지 데이터 수집 → 훈련데이터와 테스트데이터 분할 → CNN 모델로 학습 → 모델 성능 측정 → 성능 향상을 위해 Data Augmentation 기법 적용 → 모델 학습 → 모델 성능 측정 → 모델별 성능 비교

## Schedule
| Contents | March | April |  May  | June  |   Progress   |
|----------|-------|-------|-------|-------|--------------|
|  데이터 수집  |   O   |       |       |       |     Link1    |
|  관련 기법 학습  |   O   |       |       |       |     Link2    |
|  모델 구축 및 수정  |       |   O   |   O   |       |     Link3    |
|  성능 비교  |       |       |   O   |       |     Link4    |
|  보고서 작성  |       |       |       |   O   |     Link5    |


## Results
### 모델별 F1-Score
|     Model   | No Aug | Aug V1 | Aug V2 | Aug V3 |
|-------------|--------|--------|--------|--------|
|    VGGNet   |0.713845|0.832381|0.651829|0.846327|
|  GoogLeNet  |0.928199|<b>0.956804</b>|0.852320|0.893094|
|    ResNet   |0.805398|0.918766|0.877319|0.801247|


## Conclusion

* PlantVillage 로 학습한 모델은 테스트셋에서는 좋은 성능을 보였지만 추가적으로 수집한 실제 농가의 데이터에 서는 분류를 거의 하지 못하는 것을 보았다. 따라서 PlantVillage 에서 수집한 데이터로 학습한 모델로는 실제 농 업 현장에서 사용하는데 어려움이 있을 것으로 판단된다.

* AIHub 에서 수집한 데이터는 실제 농가에서 촬영된 데이터이기 때문에 이것으로 학습한 모델은 실제 농업현장 에서 사용 가능 할 것으로 예상된다. 이 데이터로 학습한 모델의 최종 결과를 보면 Data Augmentation V1 을 사 용한 GoogleNet 이 가장 좋은 성능을 보였다. 

* 최종 결과들을 통해 Data Augmentation 만으로 모델의 성 능을 향상시킬 수도 있지만, 부적절한 기법을 사용할 경우 반대로 성능이 떨어질 수 있다는 것을 확인하였고 특정 Data Augmentation 기법을 적용한 모델의 성능이 향상되었다고 다른 모델에 같은 기법을 적용했을 때도 성 능이 무조건 향상되는 것은 아니라는 것을 알 수 있었다.

## Reports
`* Upload or link (e.g. Google Drive files with share setting)
* Midterm: [Report](reports/Midterm.pdf)
* Final: [Report](reports/Final.pdf), [Demo video](https://youtu.be/N3kYhG69XGU)
