# Boston-Housing

# 🏠 Boston Housing Price Prediction

---

## 📌 과제 개요

- **목표:** Boston Housing 데이터셋을 활용해 `medv` (주택 가격)을 예측합니다.
- **핵심 내용:** 단변량/다변량 회귀 분석, 변수 선택법 (전진 선택법, 후진 제거법, 단계별 방법) 적용.
- **제출:** 개인 Notion 분석 보고서 + 분석 코드(GitHub)

---

## ✅ 데이터셋 설명

- **출처:** scikit-learn Boston Housing Dataset
- **관측치:** 506개
- **변수:** 14개 (독립변수 13개, 종속변수 1개)

| 변수 | 설명 |
|------|------|
| crim | 지역 범죄율 |
| rm | 방 개수 |
| lstat | 저소득층 비율 (%) |
| ... | ... |
| medv | **주택 가격 (종속변수)** |

---

## 📈 데이터 탐색 & 시각화

- `head()` 출력, `describe()` 출력 포함
- 주요 변수 산점도:
  - `rm` vs `medv`
  - `lstat` vs `medv`
- **가설:**  
  1️⃣ 방 개수가 많을수록 주택 가격은 상승한다.  
  2️⃣ 저소득층 비율이 높을수록 주택 가격은 하락한다.  
  - **근거:** 주거 쾌적성, 수요/이미지 영향

---

## 🔍 단변량 & 다변량 회귀분석

### ▶️ 단변량 OLS
- 변수: `rm` → `medv`
- 주요 결과:
  - R²: 약 0.48 (단일 변수)
  - P-value: 유의미
  - 기울기 해석 포함

### ▶️ 다변량 OLS
- 변수: `rm + lstat` → `medv`
- 주요 결과:
  - R²: 약 0.60 (다중 변수)
  - P-value: 두 변수 모두 유의미
  - AIC/BIC: 단변량 대비 감소 → 적합도 개선

---

## ⚙️ 변수 선택법 & 성능 비교

- **전진 선택법:** 단일 변수에서 시작해 유의미한 변수 추가
- **후진 제거법:** 전체 변수에서 불필요한 변수 제거
- **단계별 방법:** 선택과 제거를 번갈아 최적 조합 탐색

| 방법 | 변수 조합 | R² | Adj.R² | AIC | BIC |
|------|------------|-----|---------|------|------|
| 단변량 | rm | 0.48 | - | 1234 | 1245 |
| 전진 선택 | rm + lstat | 0.60 | 0.59 | 1200 | 1212 |
| 후진 제거 | rm + lstat + ptratio | 0.63 | 0.62 | 1190 | 1205 |
| 단계별 | rm + lstat + dis | 0.65 | 0.64 | 1185 | 1200 |

---

## 📊 단변량 vs 다변량 비교

- 단변량(`rm`)만 사용: 설명력 48%  
- 다변량(`rm + lstat + dis`): 설명력 65%까지 상승
- **해석:** 다중 변수 모델이 복합적인 요인을 반영하여 예측력이 높음

---

## 💡 주요 인사이트

- `rm`(방 개수)와 `lstat`(저소득층 비율)이 주택 가격에 가장 큰 영향
- 전진/후진/단계별 선택법으로 성능 비교 → 단계별 선택 조합이 가장 높음
- **한계:** 데이터는 1970년대 보스턴 지역 기준 → 최근 시장과 다를 수 있음

---

## 📎 제출 자료

- **📄 Notion 보고서:** [👉 Notion 링크 바로가기](https://your-notion-link)
- **💻 분석 코드:** `Boston_Regression_Analysis.ipynb`
- **📂 데이터:** `Boston.csv`
- **🖼️ 이미지:** 산점도, 회귀 결과 캡처 포함
- **🔗 참고:** Notion과 GitHub 링크 상호 연결

---

## ✅ 참고 사항

- Notion은 **전체 공개 상태**로 제출 필수
- README에 Notion 링크 포함되어야 평가자가 흐름 파악 가능
- 코드 실행 및 시각화 결과 일치 여부 반드시 확인

---

## ✨ Contact

- Name: [Your Name]
- 조 이름: [Team Name]
- Email: [Your Email]
