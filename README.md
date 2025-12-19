# 🚌 서울시 버스 데이터 정제 및 시각화 프로젝트  
### Seoul Bus Data Analysis & Visualization

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-red)

---

## 📖 프로젝트 개요
- 서울시 버스 이용 데이터 기반 **노선별 혼잡도**, **정류장별 승하차 패턴**, **요일별 이용 추이** 분석 및 시각화 수행  
- 단순 집계 중심 분석을 넘어 **IQR 기반 이상치 탐지** 적용  
- **지하철 환승 연계성(Last Mile)** 관점의 복합 패턴 분석을 통한 숨겨진 인사이트 도출

---

## 📂 데이터셋 정보
- **기간**: 2025.07 ~ 2025.11 (5개월)  
- **규모**: 정류장 약 40,512개, 노선 662개  
- **출처**: 공공데이터포털 

---

## 🛠 사용 기술
- **Language**: Python  
- **Libraries**
  - **Pandas**: 데이터 전처리, 병합(Merge), 그룹화(GroupBy)
  - **Matplotlib / Seaborn**: 데이터 시각화
  - **NumPy**: 수치 계산

---

## 📊 주요 분석 결과

### 1) 데이터 정제 (이상치 탐지)
- **방법**: IQR(Interquartile Range) 기반 정상 범위 산출 및 범위 초과 혼잡 데이터 식별  
- **결과**
  - 승차 인원 **상한선(약 360명)** 초과 데이터 비중 **약 5.99%** 확인  
  - 데이터 오류가 아닌 **출퇴근 시간대(Peak Time) 실제 혼잡**으로 해석 후 분석 포함

### 2) 정류장 및 노선 분석 (Hotspots)
- **최다 승차 정류장**: 회기역(00001) — 승차 약 70만 명  
  - 하차 대비 승차 **2배 이상** 패턴 확인  
  - 인근 대학가·주거지 → 지하철 환승 거점 역할 추정  
- **핵심 노선**: 143번(정릉~개포)  
  - 강북~강남 관통, 누적 승객 **약 541만 명** 수송  
  - 서울 주요 간선 축(대동맥) 역할 정의

### 3) 복합 패턴 분석 (Advanced Insights)
- **마을버스 역할(Last Mile)**  
  - 동대문01 노선의 회기역 승객 수송 핵심 기여 확인  
  - 지하철역~주거지 연결 단거리 고수요 구간 중요성 도출  
- **관광 vs 출퇴근 노선 구분**
  - 01A/01B(남산 순환) 주말 이용객 **주중 대비 약 1.4배** → 관광 수요 특성  
  - 일반 간선 버스 주말 이용객 **주중의 약 60% 수준** → 출퇴근 수요 특성

---

## 📈 시각화 예시
- Top 10 혼잡 정류장 막대 그래프
  <img width="1281" height="579" alt="output_1" src="https://github.com/user-attachments/assets/63fe391f-d9fb-48e4-970e-927b699d4117" />

- 노선별 주중/주말 이용 패턴 비교
  <img width="1409" height="653" alt="output" src="https://github.com/user-attachments/assets/d22cf568-c9eb-4a02-881a-3d601ee290fb" />

