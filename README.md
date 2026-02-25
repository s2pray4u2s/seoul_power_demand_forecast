# 🔋 서울시 환경 기반 전력 수요 예측 모델

> 기상 및 환경 데이터를 활용한 서울시 시간별 전력 수요 예측 및 운영 대책 제언

---

## 📌 프로젝트 개요

| 항목 | 내용 |
|------|------|
| 분석 기간 | 2023년 1월 ~ 2024년 12월 (17,544시간) |
| 분석 단위 | 서울시 전체 (서울본부 + 남서울본부 합산) |
| 타겟 변수 | 시간별 전력사용량 (MWh) |
| 활용 데이터 | 전력수요 + 기상 + 미세먼지 (3종 통합) |

---

## 📁 폴더 구조
```
├── 1_data/
│   ├── raw/          # 원본 데이터 (gitignore)
│   └── processed/    # 전처리 완료 데이터
├── 2_notebooks/
│   ├── 01_preprocessing.ipynb
│   ├── 02_EDA.ipynb
│   ├── 03_modeling.ipynb
│   ├── 04_LSTM.ipynb
│   └── 05_insight.ipynb
├── 3_scripts/
├── 4_output/         # 시각화 결과물
├── 5_fonts/          # Pretendard 폰트
└── 6_models/         # 학습된 모델 (gitignore)
```

---

## 🛠 기술 스택

`Python` `Pandas` `Scikit-learn` `XGBoost` `PyTorch` `Matplotlib` `Seaborn`

---

## 📊 모델 성능

| 모델 | R² | RMSE | MAPE |
|------|-----|------|------|
| Linear Regression | 0.941 | 365.7 | 5.03% |
| Random Forest | 0.963 | 288.4 | 3.10% |
| **XGBoost** | **0.971** | **255.4** | **2.84%** |
| LSTM | 0.660 | 878.2 | 13.35% |

---

## 💡 주요 인사이트

- 기온 1°C 상승 시 전력수요 **38.3 MWh 증가**
- 폭염일(33°C↑) 수요 일반일 대비 **70% 급증** (3,533 MWh↑)
- 주말·공휴일 수요 평일 대비 **14.4% 감소**
- 계절별 피크 시간: 여름 **14시** / 겨울 **11시** / 가을 **18시**

---

## ⚙️ 설치 및 실행
```bash
pip install pandas numpy scikit-learn xgboost torch matplotlib seaborn holidays
```