# 한국폴리텍대학교 하이테크과정 — 반도체 장비 제어·설계·품질 분석

반도체융합기계 하이테크과정에서 PLC 장비 제어, SolidWorks 장비 설계, SPC 품질 분석을 동시에 이수하며 반도체 장비 엔지니어의 핵심 역량을 습득하고 있습니다.

**2026.03 ~ 현재 | 1200시간 과정 (832시간 이수 중)**

---

### 사용 기술

- PLC : Mitsubishi MELSEC Q5, GX-Works2/3, LS XG-5000, 인터록 설계
- HMI : M2I 화면 설계
- 3D 설계 : SolidWorks (3D 모델링/어셈블리/2D 도면 해독, KS 기계 제도법)
- 품질 분석 : Minitab (Cp/Cpk, 히스토그램, 관리도), FMEA, 8D Report

---

### PLC 장비 제어 및 인터록 설계

Mitsubishi PLC(GX-Works2/3, MELSEC Q5)와 LS XG-5000으로 3상 인버터 컨베이어 구동 및 지능형 신호 제어 시스템을 구축했습니다.

설비 기동 시 운전자가 아무것도 모른다고 가정하고, PLC가 '동작'보다 '정지'에 더 큰 가치를 두도록 인터록을 설계했습니다. 비상정지·도어 열림·과전류 조건에서 즉시 시퀀스가 차단되도록 래더 로직을 구성했습니다.

---

### 솔레노이드 밸브 트러블슈팅

실습 중 솔레노이드 밸브가 PLC 출력 신호에 반응하지 않았습니다. 즉시 차단기를 내리고 릴레이 배선을 물리적으로 추적하여 쇼트 지점을 발견했습니다.

회로도를 직접 그려 동료들에게 원인을 설명한 뒤, GX-Works3 래더 로직의 출력 접점 할당을 수정하여 정상 동작을 확인했습니다.

<img width="4032" height="3024" alt="KakaoTalk_20260922_113043457" src="https://github.com/user-attachments/assets/cceeba1d-7260-4faf-ab77-875f282680af" />

---

## SolidWorks PECVD 장비 3D 모델링

### PECVD 장비란?

PECVD(Plasma-Enhanced Chemical Vapor Deposition)는 반도체 제조 공정에서 절연막(SiO₂, SiNx), 패시베이션막 등을 웨이퍼 위에 증착하는 장비입니다.

**원리** 
반응 가스(SiH₄, N₂O, NH₃ 등)를 진공 챔버에 주입한 뒤, RF 플라즈마를 인가하여 저온(200~400°C)에서 박막을 증착

**특징**
일반 CVD 대비 낮은 온도에서 증착이 가능하여, 금속 배선이 형성된 후공정(BEOL)에서도 적용 가능

**구성**
PM Chamber(공정 챔버), Load Lock Chamber(웨이퍼 출입), Transfer System(웨이퍼 이송), 진공 배기 라인, 프레임 구조물

### 역할
실제 PECVD 장비의 2D 도면(부품도 + 조립도)을 KS 규격에 따라 해독하고, SolidWorks에서 개별 부품을 3D 모델링한 후 전체 Assembly로 조립

### 설계 과정

**1단계. 2D 도면 해독**
실제 장비의 부품도와 조립도를 KS 기계 제도법(제3각법)에 따라 해독했습니다. 각 부품의 치수, 공차, 표면 거칠기, 재질 정보를 파악하여 3D 모델링에 반영했습니다.

**2단계. 개별 부품 모델링**

| 서브 어셈블리 | 설명 |
|-------------|------|
| PM Chamber Body | 공정 챔버 본체 (샤워헤드, 서셉터 포함) |
| Load Lock Chamber Body | 웨이퍼 출입용 로드락 챔버 |
| Door / Door Support | 챔버 도어 및 힌지 지지 구조물 |
| Lid Door Assy | 챔버 상부 리드 도어 |
| Transfer Assy | 웨이퍼 이송 시스템 |
| Driving Screw Assy | 웨이퍼 이송용 구동 스크류 |
| NW40 Pipe 배기 Line | 진공 배기 배관 |
| Table Frame | 장비 하부 지지 프레임 |
| Frame Cover (Sheet Metal) | 상부 외장 커버 |


**3단계. 전체 어셈블리 조립**
모델링된 부품들을 메이트(Mate) 조건으로 조립하여 전체 장비 어셈블리를 완성하고, 실제 장비 사진과 비교하여 구조적 정확성을 검증했습니다.

### 프로젝트 사진

<img width="1163" height="749" alt="image" src="https://github.com/user-attachments/assets/2f716fec-097d-462e-9bc6-5c36537f23a5" />
SolidWorks로 모델링한 3D 어셈블리(좌)와 실제 PECVD 장비 사진(우). PM Chamber, Load Lock Chamber, Frame 구조가 실물과 동일하게 구현되었습니다.

<img width="1070" height="1058" alt="image" src="https://github.com/user-attachments/assets/8018fac0-f217-4764-9f83-9c2e404d1eb9" />
외장 커버(Sheet Metal)를 포함한 전체 장비의 등각 투영(Isometric) 뷰. 좌측에 PM Chamber 영역, 우측에 Load Lock Chamber 영역이 배치됩니다.

<img width="1077" height="1057" alt="image" src="https://github.com/user-attachments/assets/6babd106-d2b8-4705-852f-86f74e0a7f63" />
웨이퍼가 외부에서 진공 챔버로 출입하는 Load Lock Chamber. 전면에 웨이퍼 투입구(View Port) 2개가 있으며, 하단에 NW40 진공 배기 라인이 연결됩니다.

<img width="1065" height="1095" alt="image" src="https://github.com/user-attachments/assets/9bdda082-ba31-4eb8-b214-549d8dd1d358" />
외장 커버를 씌운 상태에서 상부 커버를 분리한 뷰. PM Chamber가 안착되는 우측 상단 개구부와, 진공 펌프 연결을 위한 좌측 원형 홀이 보입니다.

<img width="1076" height="598" alt="image" src="https://github.com/user-attachments/assets/dcfa267a-025b-4042-a17f-2104ca0e35db" />
장비 하부를 지지하는 Table Frame의 Foot Plate 상세. 레벨링을 위한 조절 볼트 구조와 프레임 용접부 마감이 모델링되어 있습니다.

<img width="1059" height="662" alt="image" src="https://github.com/user-attachments/assets/01e294c9-12fd-48fa-bd03-1b14fb6c1f83" />
PM Chamber 영역과 Load Lock Chamber 영역을 연결하는 상부 프레임 접합부. 볼트 체결 홀과 플레이트 맞닿음(fit-up) 구조가 확인됩니다.

<img width="1065" height="1150" alt="image" src="https://github.com/user-attachments/assets/92994ee3-0b9d-488e-af9f-2f9ea86bafad" />
장비 전체를 지지하는 Table Frame Assembly. 각형 강관(Square Tube)으로 구성되며, PM Chamber 영역(좌)과 Load Lock Chamber 영역(우)을 별도 섹션으로 지지합니다.

<img width="922" height="568" alt="image" src="https://github.com/user-attachments/assets/ed434906-c1b1-4de2-9cb0-4cb746b4fece" />

<img width="903" height="558" alt="image" src="https://github.com/user-attachments/assets/c36aadd0-6079-4108-b2d2-6b8b7520056b" />

<img width="1008" height="601" alt="image" src="https://github.com/user-attachments/assets/13a21872-674e-478d-90c7-64d8f2aed156" />

<img width="1009" height="629" alt="image" src="https://github.com/user-attachments/assets/813c74ba-9e07-47e8-945d-42c45add7b8e" />

<img width="1006" height="610" alt="image" src="https://github.com/user-attachments/assets/398fa0cb-5991-45f1-b8e6-2c310754cd6a" />

<img width="1114" height="710" alt="image" src="https://github.com/user-attachments/assets/dfb552fa-52d4-480d-a951-11c995d49471" />

<img width="1144" height="725" alt="image" src="https://github.com/user-attachments/assets/bfffc6d9-a32b-4fc2-a8b3-d5fa4174c5d6" />


---

### SPC 기반 데이터 분석

생성형 AI를 활용하여 식각 균일도, 증착 두께 등 반도체 공정의 가상 데이터를 생성한 뒤, 이 데이터로 8D Report를 작성하며 불량의 근본 원인을 단계별로 추적하는 프로세스를 실습했습니다.

FMEA를 통해 잠재적 고장 모드와 RPN을 산출했습니다. AI가 시각화한 결과를 직접 Minitab으로 동일하게 분석하여 N=160개 샘플의 Cp/Cpk를 산출하고 히스토그램·관리도로 공정 산포를 시각화하여, AI 출력과 실제 통계 분석 간 차이를 교차 검증하고 보정했습니다.

---

### 배운 점

**도면 해독**
2D 도면에서 3차원 형상을 읽어내는 능력 확보. 투상법(제3각법), 단면도, 치수 공차를 실무 수준으로 이해

**장비 구조**
PECVD 장비의 챔버·진공 배기·웨이퍼 이송·RF 전극의 공간 배치를 부품 단위로 파악

**인터록 설계**
장비의 '안전한 정지'가 '정상 동작'보다 우선한다는 설비 제어 철학을 체득

**데이터 분석**
Cp/Cpk 수치로 공정 능력을 정량적으로 판단하는 실무적 감각 확보

[← 메인으로](../README.md)
