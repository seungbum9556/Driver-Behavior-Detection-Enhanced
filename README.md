<img width="1627" height="619" alt="image" src="https://github.com/user-attachments/assets/0bbae7ec-c621-411e-8f88-2143e1b768ef" /># Driver-Behavior-Detection-Reproduction-and-Improvement-using-ResNet

# Driver Behavior Detection with ResNet


ResNet 기반 운전자 행동 인식 모델을 재현하고,  
ROI 기반 multi-input 구조와 다양한 최적화 기법을 통해 성능을 개선한 프로젝트

---

## Result
- Final Kaggle Score: 0.206  
- Best Validation Loss: 0.16  

---

## Overview
본 프로젝트는 운전자의 행동을 분류하는 모델을 재현하고,  
데이터, 모델 구조, 학습 전략 전반에 걸친 개선을 통해 성능 향상을 목표로 하였다.

---

## Key Contributions

### ROI 기반 Multi-Input 설계
- Full Image, Head, Hand 입력 구조 적용  
- 불필요한 영역 제거를 통한 성능 및 효율 개선  

---

### Data Augmentation 전략
- Color Jitter 기반 augmentation 적용  
- 방향성 정보 보존을 위해 Flip 제거  
- Cutmix 적용을 통한 generalization 성능 향상  

---

### 모델 구조 개선
- SE Block 도입을 통한 채널 중요도 학습  
- ROI별 중요도 반영 구조 설계 및 실험  

---

### 클래스 혼동 문제 분석
- Safe(c0) vs Passenger(c9) 혼동 문제 분석  
- 시선 방향 및 상황 정보 부족이 주요 원인으로 확인  

---

### 2단계 모델 (Ambiguous Model)
- 확률 기반 ambiguous 데이터 추출  
- 2차 모델 학습을 통한 성능 보완  

---

### 최적화 및 앙상블
- Threshold tuning (0.2 → 0.05)  
- Hyperparameter tuning (LR, Dropout 등)  
- Ensemble 기반 최종 성능 도출  

---

## Tech Stack
- Python  
- PyTorch  
- OpenCV  

---

## Highlights
- 단순 구현이 아닌 문제 분석 → 가설 → 실험 → 개선 과정 수행  
- 데이터, 모델, 학습 전략을 모두 활용한 end-to-end 최적화  
- 실제 Kaggle 성능 기반 검증된 결과  

---

## How to Run

```bash
pip install -r requirements.txt
python train.py
