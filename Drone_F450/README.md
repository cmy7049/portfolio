# 부경대학교 학술동아리 (OSD) — F450 쿼드콥터 드론 제작

## 개요

학술동아리 OSD에서 Arduino MCU 기반의 센서 연동, 모터 제어, 배선 설계를 수행하며 하드웨어 제어의 기초를 다졌습니다.

쿼드콥터 제작 전, RC카 제작 및 미세먼지 센서 모듈화 등 미니 프로젝트를 통해 낯선 부품의 회로도를 분석하고 직접 배선을 설계하는 감각을 길렀습니다. 조별 세미나에서 각자의 트러블슈팅 사례와 해결책을 공유하며 하드웨어 전반에 대한 시야를 넓혔습니다.

**2023.05 ~ 2024.02**

---

### 역할
조원, 하드웨어 제작 보조 및 PID 제어 담당

### 사용 기술

Arduino Due, F450 프레임, MPU9250(IMU), BLDC 모터, PID 제어, 회로도 분석/배선 설계

---

### 기초 프로젝트

Arduino MCU를 활용한 다양한 미니 프로젝트(RC카, 미세먼지 센서 등)를 수행하며 센서 연동, 모터 제어, 배선 설계 등 하드웨어 제어의 기초를 다졌습니다.

---

## 프로젝트 사진

### 드론 설계 구조

<img width="942" height="465" alt="image" src="https://github.com/user-attachments/assets/e1c915aa-6299-4c40-ba02-bdd2537409d1" />
<img width="1193" height="486" alt="image" src="https://github.com/user-attachments/assets/9b15d1ac-0182-4232-aaf3-833dcf081bb4" />
<img width="1159" height="475" alt="image" src="https://github.com/user-attachments/assets/fba1f472-b0f4-4397-a9d7-28ef59baffb1" />
<img width="1136" height="439" alt="image" src="https://github.com/user-attachments/assets/dde7c58c-27ac-48b5-ac69-243055322397" />
<img width="1018" height="593" alt="image" src="https://github.com/user-attachments/assets/5c727f3d-3dc2-4ac5-9045-d7703fa7bf60" />
<img width="1108" height="563" alt="image" src="https://github.com/user-attachments/assets/87fc637c-161f-4172-a1da-54220023f361" />
<img width="1079" height="592" alt="image" src="https://github.com/user-attachments/assets/dbc994d7-55b9-44a7-a53d-68adfe3fea7e" />
<img width="1018" height="459" alt="image" src="https://github.com/user-attachments/assets/929cc071-09f5-4c68-8da8-0d770ff2f20d" />
<img width="1163" height="567" alt="image" src="https://github.com/user-attachments/assets/70c7393e-6b36-4e96-b371-d7c91fe35b1f" />
<img width="1211" height="514" alt="image" src="https://github.com/user-attachments/assets/1cb8ef23-9dd4-4c62-ad46-98b1b262f834" />
<img width="1180" height="553" alt="image" src="https://github.com/user-attachments/assets/f16a8afd-f856-4aea-919e-74ea8224f3f3" />
<img width="1072" height="553" alt="image" src="https://github.com/user-attachments/assets/546418c7-cf07-40a5-966b-79a1c6e63f5f" />
<img width="589" height="514" alt="image" src="https://github.com/user-attachments/assets/1f7585d0-7d03-47b3-bb8a-9313dc97d43b" />

<img width="747" height="538" alt="image" src="https://github.com/user-attachments/assets/f6a05b74-e4c5-491e-b1a4-a8c23ef9811d" />
<img width="999" height="550" alt="image" src="https://github.com/user-attachments/assets/4108b339-7de4-4912-a1e4-af098dfc0388" />
<img width="1087" height="545" alt="image" src="https://github.com/user-attachments/assets/ef055e16-8773-47d9-bb10-e6b9bbb404bc" />

### 회로결선
<img width="479" height="474" alt="image" src="https://github.com/user-attachments/assets/2affba07-24d6-40f7-ae88-a5b4a216b422" />
<img width="889" height="551" alt="image" src="https://github.com/user-attachments/assets/ec0d0fbc-8321-44c9-b239-19431288731e" />
<img width="868" height="560" alt="image" src="https://github.com/user-attachments/assets/4f260c70-9d48-4839-a841-03efcf29bdd7" />

---

### 쿼드콥터 제작

이러한 역량을 바탕으로, F450 프레임과 Arduino Due를 활용해 쿼드콥터 기체를 직접 조립했습니다. MPU9250(IMU) 센서를 연동해 기체의 기울기 데이터를 수집하고, 이를 기반으로 4개의 BLDC 모터를 구동하는 PID 기반 자세 제어 시스템을 하드웨어적으로 구현했습니다.

이 과정을 통해 낯선 부품들의 회로도를 분석하고 직접 배선을 설계하며 하드웨어를 제어하는 실무 엔지니어링 감각을 길렀습니다.
<img width="1159" height="585" alt="image" src="https://github.com/user-attachments/assets/09e6f8c4-16dd-44a0-b492-d12c38577a64" />

---

### 핵심 코드 - MPU6050 기반 PID 자세 제어

// Outer P control (각도 제어)
Pitch_Err = mPitch - PID_Pitch_Setpoint;
Roll_Err  = mRoll  - PID_Roll_Setpoint;
Pitch_P = Pitch_Err * P_Gain;
Roll_P  = Roll_Err  * P_Gain;

// Inner PID control (각속도 제어)
Pitch_Rate_Err = Pitch_P + Gyro_Pitch_Input;
Roll_Rate_Err  = Roll_P  + Gyro_Roll_Input;

// 모터 속도 = 스로틀 + PID 출력 (X 배열)
nMotorSpeed01 = nThrottle + (Pitch_Rate_PID + Roll_Rate_PID);
nMotorSpeed02 = nThrottle + (-Pitch_Rate_PID + Roll_Rate_PID);
nMotorSpeed03 = nThrottle + (-Pitch_Rate_PID - Roll_Rate_PID);
nMotorSpeed04 = nThrottle + (Pitch_Rate_PID - Roll_Rate_PID);

---

### 결과

- GND 루프 해결 후 안정적 호버링 및 비행 달성
- 오실로스코프 파형 분석으로 하드웨어 문제의 근본 원인 규명
- "감이 아닌 측정 데이터로 문제를 진단한다"는 원칙을 체득


[← 메인으로](../README.md)
