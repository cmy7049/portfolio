# CMOS 이미지센서 DTI 구조 최적화 시뮬레이션
<img width="776" height="1095" alt="image" src="https://github.com/user-attachments/assets/94008047-90f8-4a54-bd43-d5d51bb4cf08" />



2024년 전자공학전공 캡스톤디자인 경진대회 프로젝트입니다.
Ansys Lumerical FDTD를 활용하여 CMOS 이미지 센서의 수광율(QE)을 13.6% 최적화했습니다.

**2024.07 캡스톤디자인 경진대회 장려상** (부경대학교 정보융합대학장)

---

### 역할

FDTD 시뮬레이션 설계 및 DTI 구조 모델링·최적화, SEMICON Korea 참관하여 High-k/Low-k 박막 물성 데이터 직접 확보했습니다.

### 사용 기술

Ansys Lumerical FDTD, FSI(Front-Side Illumination) CMOS Image Sensor, BSI(Back-Side Illumination) CMOS Image Sensor, DTI(Deep Trench Isolation), ARC(Anti-Reflection Coating)

---

### 연구 배경

고해상도 카메라 수요 급증으로 픽셀이 미세화(0.8μm 이하)되면서, 인접 픽셀 간의 빛 누설(Crosstalk) 및 수광율 저하 문제가 발생했습니다. 이를 개선하기 위해 Ansys Lumerical FDTD를 활용하여 CMOS 이미지 센서 구조 최적화를 진행했습니다.
<img width="409" height="377" alt="image" src="https://github.com/user-attachments/assets/018e4573-6bc9-4d7f-920f-0ba3e449f75a" />

---

## 프로젝트 사진

### 시뮬레이션 Setup

<img width="1360" height="775" alt="image" src="https://github.com/user-attachments/assets/65f49b06-f5ca-4cef-bafd-1b371542235a" />

<img width="1381" height="763" alt="image" src="https://github.com/user-attachments/assets/fa93e4d3-ec23-4757-b365-bed932b45d43" />

### 입사각(Sweep Angle)에 따른 화소별 투과 효율(QE) 계산

<img width="867" height="526" alt="image" src="https://github.com/user-attachments/assets/e050469e-5e9b-4fde-bd3e-5a13ec60d439" />

### DTI(왼쪽) 및 BSI(오른쪽) 구조 단면도 차이

<img width="645" height="767" alt="image" src="https://github.com/user-attachments/assets/45b4d7e9-ceb9-4b50-b773-4ad1f816c062" />

<img width="1351" height="654" alt="image" src="https://github.com/user-attachments/assets/354a0ed4-a67d-4948-9144-1aa3f1497fa2" />

### DTI 소재별 Crosstalk 억제 효과 비교 (SiO₂, HfO₂, BlackDiamond)



---

### DTI 격벽 소재 및 두께 최적화

Crosstalk을 억제하기 위해 격벽의 두께 변수를 조정하며 시뮬레이션을 진행했습니다. 기존 SiO₂ 격벽의 광 흡수율 한계를 파악하고, 박막 물성 데이터를 기반으로 High-k 물질인 TiO₂로 소재를 변경해 포토다이오드 도달 광량을 확보했습니다.

격벽 두께를 2nm에서 600nm까지 50nm 단위로 분할하고, 물질별(SiO₂, TiO₂, HfO₂, W, BlackDiamond)로 각 30회씩 시뮬레이션을 수행했습니다.

---

### ARC 설계

파장 550nm 조건에서 표면 반사 손실을 최소화하기 위해, 굴절률(n=2.435)을 참고하여 최적의 ARC(무반사 코팅) 두께(d=56.5nm)를 설계 및 적용했습니다.

---

### 팀원 설득 — 조건부 합의

팀원들은 기존 Low-k 소재를 유지하자고 주장했습니다. 데이터 없이 논쟁하는 것은 비효율적이라고 판단하여, "물성 데이터를 확보하면 신소재로, 못 하면 기존안을 따르자"는 조건을 제안했습니다.

부산에서 서울 SEMICON Korea까지 직접 방문하여 소재 기업 부스 엔지니어로부터 TiO₂의 최신 박막 물성 데이터(실측 굴절률)를 수집했습니다. 이 데이터를 시뮬레이션에 반영하여 팀원들을 설득했습니다.

---

### 결과

ARC 및 최적 DTI 조합을 적용해 수광 효율을 약 13.6%(0.374→0.425) 향상시켰으며, 파라미터 최적화 역량을 인정받아 캡스톤 경진대회 장려상을 수상했습니다.
<img width="829" height="1156" alt="image" src="https://github.com/user-attachments/assets/5be16428-ca5c-4e92-8579-ac4c344dfa33" />

[← 메인으로](../README.md)
