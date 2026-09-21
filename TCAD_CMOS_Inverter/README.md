# TCAD 기반 CMOS Inverter 공정 설계 및 소자 특성 분석

#### 프로젝트 요약
부경대학교 전자공학과 반도체공정설계 팀 프로젝트로, Synopsys Sentaurus TCAD를 활용하여 NMOS 및 CMOS Inverter의 전 공정을 설계하고 전기적 특성을 분석했습니다.

특히 n-well 도핑 농도를 최적화하는 시뮬레이션을 통해 NMOS와 PMOS의 대칭 동작을 유도했으며, 이를 기반으로 정상적인 VTC(Voltage Transfer Characteristic) 곡선을 확보하여 인버터의 소자 특성 타당성을 검증했습니다.

**2025.05 ~ 2025.06**

---

### 역할

팀원: 반도체 가상 공정(S-Process) 코드 및 전기적 결선(S-Device) 코드 설계, 소자 파라미터 최적화 담당

### Simulation Tool

#### Synopsys TCAD Sentaurus (S-Process / S-Device)
— 구조 설계 및 전기적 특성 분석
#### Process
- STI Oxide Isolation, Well & S/D Ion Implantation, Gate Oxide Growth, LDD Spacer Structure
#### Device Simulation
- Hydrodynamic Transport Model, HighFieldSaturation & IALmob Mobility, VTC Load Circuit 

---

### 공정 설계(Process Simulation)

#### 1. 전 공정 레시피 하드코딩
STI(소자 격리), N-Well 형성, LDD, 소스/드레인 이온 주입부터 금속 콘택(Metal Contact)에 이르는 전 공정 플로우를 Tcl 코드로 직접 작성하여 NMOS 및 CMOS Inverter 구조를 설계했습니다.

#### 2. 수렴성 및 마스킹 최적화
가변 메시 라인(line x/y) 설정을 통해 시뮬레이션 연산 수렴성을 확보했으며, 희생 산화막 성장 후 문턱 전압(Vth) 보정을 위한 타깃별 이온 주입 및 마스크 공정을 수행했습니다.

#### 3. 단채널 효과 제어 구조 구현
핫 캐리어 억제를 위해 틸트 각도(tilt=7)를 반영한 LDD 이온 주입을 설계하고, 사이드월 산화막 증착 및 식각을 통해 LDD Spacer 구조를 물리적으로 결합했습니다.

#### 4. 인버터 회로 수준 결선
일반적인 단일 소자 모델링을 넘어, 폴리실리콘 증착 및 이방성 식각공정을 통해 게이트-드레인 인터커넥트 쇼트(Gate-Drain Short) 구조를 가상 공정상에서 완벽히 통합 구현했습니다.

---

<img width="643" height="617" alt="image" src="https://github.com/user-attachments/assets/aec650ef-ed79-4964-be32-46f59486749a" />

<img width="650" height="872" alt="image" src="https://github.com/user-attachments/assets/f51c2bad-0adc-4835-b9cc-9d52396eba27" />

<img width="661" height="905" alt="image" src="https://github.com/user-attachments/assets/0ddb7e18-0494-4f73-8a31-caee727f5dff" />

---

<img width="667" height="664" alt="image" src="https://github.com/user-attachments/assets/a06d6d9c-774a-4cd2-ae35-bb2a150641f7" />

<img width="673" height="1037" alt="image" src="https://github.com/user-attachments/assets/b539a947-1380-4384-b44e-50488f0e7ddd" />

<img width="662" height="1046" alt="image" src="https://github.com/user-attachments/assets/c62633f2-07e5-4e33-ba75-3e59f809fe9e" />

<img width="669" height="796" alt="image" src="https://github.com/user-attachments/assets/db171d43-ea70-486a-be8c-ac8e2d2550f5" />

<img width="658" height="742" alt="image" src="https://github.com/user-attachments/assets/0ec2d8c4-f001-4715-8033-a68007aed5ce" />

---

<img width="657" height="1033" alt="image" src="https://github.com/user-attachments/assets/f7fded14-cf38-4c8b-ba24-f65182337c85" />

<img width="649" height="895" alt="image" src="https://github.com/user-attachments/assets/85661d32-7624-4594-9bf6-9e41b017bfcb" />

<img width="673" height="883" alt="image" src="https://github.com/user-attachments/assets/1f26a55c-4e4a-411f-97f9-d24b19c4ba24" />

<img width="642" height="683" alt="image" src="https://github.com/user-attachments/assets/f718d9ee-0bfc-4e45-8b7b-df1f8dc50c27" />

<img width="698" height="1028" alt="image" src="https://github.com/user-attachments/assets/2e6c84b3-d306-4b82-bc78-076a4f0ca4ba" />

<img width="686" height="538" alt="image" src="https://github.com/user-attachments/assets/248b3e62-fd15-4a92-a3bc-93dca770ed85" />

---

<img width="685" height="939" alt="image" src="https://github.com/user-attachments/assets/e2e8fa0e-2c05-48aa-8b3b-6b76fafbc037" />
<img width="657" height="546" alt="image" src="https://github.com/user-attachments/assets/5e81885c-dbfc-45d6-aab5-a5615e886d6d" />

---

### CMOS invertor 공정 설계

<img width="665" height="879" alt="image" src="https://github.com/user-attachments/assets/cc23c285-437e-4c33-882d-db7562445d8a" />

<img width="671" height="802" alt="image" src="https://github.com/user-attachments/assets/02800a36-01ff-4332-a32e-3bf709eb94a8" />

<img width="652" height="1006" alt="image" src="https://github.com/user-attachments/assets/ca52fe7d-f0c9-40d0-8bcd-e8b0df1e863d" />

<img width="704" height="1050" alt="image" src="https://github.com/user-attachments/assets/e9275000-46dc-46cc-94e6-df17b0eb3fdc" />

<img width="706" height="875" alt="image" src="https://github.com/user-attachments/assets/9f898b5c-58c5-44bb-92c9-3b216424221b" />

<img width="695" height="707" alt="image" src="https://github.com/user-attachments/assets/0a58e0b0-4cb8-490b-90cf-a7688f135840" />

<img width="660" height="1080" alt="image" src="https://github.com/user-attachments/assets/d327b4f1-3a3b-4304-8e5a-740a079bd8c9" />

<img width="644" height="838" alt="image" src="https://github.com/user-attachments/assets/28b8d1d9-2ece-45c3-b3d7-8cbd24c7dbb1" />

<img width="661" height="856" alt="image" src="https://github.com/user-attachments/assets/06429438-e7b6-470b-a1c6-d20418adf89b" />

<img width="694" height="1046" alt="image" src="https://github.com/user-attachments/assets/f348e4ce-7103-4bfa-9bb2-971cf9f5ccca" />

<img width="658" height="573" alt="image" src="https://github.com/user-attachments/assets/5e1dd1b3-347a-4635-906d-192f832fdac7" />

<img width="639" height="637" alt="image" src="https://github.com/user-attachments/assets/030b49ed-9a96-4fe1-9f68-27e59d8c3550" />

<img width="691" height="792" alt="image" src="https://github.com/user-attachments/assets/3f307511-b4b0-4759-83a9-123528ac2ad6" />

<img width="670" height="697" alt="image" src="https://github.com/user-attachments/assets/a35b0cb6-96f9-4685-8703-7797a42dcac5" />

### CMOS Inverter S-Process CODE
<img width="684" height="899" alt="image" src="https://github.com/user-attachments/assets/1d2343ae-bcf8-4349-821e-b3ba405c007c" />

<img width="668" height="1059" alt="image" src="https://github.com/user-attachments/assets/d97c093d-50e8-4b37-990b-8e1c54cd01df" />

### S-Device Code

<img width="661" height="913" alt="image" src="https://github.com/user-attachments/assets/896d7be4-aade-4b33-a264-ac8f69964deb" />

<img width="671" height="1058" alt="image" src="https://github.com/user-attachments/assets/4386dd84-a728-4ac0-ba70-92beb6ba311b" />

---

### 특성 분석

50nm 채널에서 DIBL이 0.33V/V, SS가 130mV/dec로 급증하는 단채널 효과(SCE)를 수치적으로 확인했습니다. 이후 Gate Length 2.4μm의 CMOS Inverter를 추가로 설계하여 VTC(Voltage Transfer Characteristic) 곡선의 스위칭 특성과 고노이즈 마진(Noise Margin)을 검증함으로써, 미세 공정 파라미터 세팅이 최종 소자의 전기적 성능에 미치는 영향을 체득했습니다.

---

### 배운 점
<img width="635" height="660" alt="image" src="https://github.com/user-attachments/assets/9f6d3c3b-5c18-4656-85a6-a0ca1558bb43" />

<img width="640" height="266" alt="image" src="https://github.com/user-attachments/assets/5b07ee6c-d27d-4d18-9781-5aa52e777bf7" />


[← 메인으로](../README.md)
