<img width="3907" height="2050" alt="20250723-공학교육혁신센터, ‘2025 사물인터넷 인벤톤 프로그램’ 성료" src="https://github.com/user-attachments/assets/c8337e01-8b2e-41cd-b6a1-4b79905d5072" />

# AIoT 스마트 자동 급식기

국립부경대학교·경상국립대학교·부산대학교 공과대학 공학교육혁신센터 주관, 2025 사물인터넷 인벤톤(IoT Invent-On) 경진대회에서 제작한 프로젝트입니다.

YOLOv11 객체 인식 기반 스마트 자동 급식기를 Onshape로 3D 모델링하고, 라즈베리파이와 아두이노를 연동하여 시스템을 구현했습니다.

PIR 센서가 반려동물의 움직임을 감지하면, 라즈베리파이 카메라가 YOLOv11으로 강아지/고양이를 구분합니다. 인식 결과에 따라 서보모터가 해당 방향으로 회전하여 맞춤 사료를 배출합니다. 초음파 센서는 사료통 잔량을 측정하여 30% 이하일 경우 다이오드(LED)가 점등되어 부족 알람을 알립니다.

## 2025.08.12 장려상 수상 (부경대학교 공학교육혁신센터)

---

### 팀 구성 및 역할

- 원래 3인 팀이었으나 대회 당일 1명(UART 통신 담당) 불참, 2인 체제로 진행
- 본인 : 기구물 3D 모델링(Onshape), 아두이노(MCU) 구동부 및 센서 제어 및 배선 설계, 하드웨어 통합
- 팀원 : YOLOv11 객체 인식 모델 학습 및 튜닝

### 사용 기술

YOLOv11, ONNX Runtime, Raspberry Pi 4, Arduino Uno, UART 시리얼 통신, MG996R 서보모터, PIR 센서, HC-SR04 초음파 센서, Onshape 3D 모델링, 3D 프린터

---

### 시스템 동작 흐름

1. PIR 센서가 움직임 감지 → 카메라 활성화
2. 라즈베리파이 카메라가 3초간 촬영
3. YOLOv11 ONNX 모델로 강아지/고양이 인식
4. 인식 결과를 UART 통신으로 아두이노에 전송
5. MG996R 서보모터가 해당 사료통 방향으로 회전(0도 ~ 180도) 후 사료 배출
(+ 사료량 측정 -> 초음파 센서로 사료량 30% 이하 감지 시 LED 알림)

### 프로젝트 사진

#### 시스템 구성도

<img width="709" height="985" alt="스크린샷 2026-09-21 110558" src="https://github.com/user-attachments/assets/fe586b95-e2af-4a38-997c-e4e9a70e0afe" />

<img width="711" height="612" alt="스크린샷 2026-09-21 111430" src="https://github.com/user-attachments/assets/0bf3d200-6b8f-4761-9f6b-2896c8c92287" />

<img width="709" height="822" alt="스크린샷 2026-09-21 111440" src="https://github.com/user-attachments/assets/00d85e79-12a7-4c25-bcb5-e1917b0d7e31" />


#### YOLOv11 학습 데이터 (강아지 40장 + 고양이 40장 + 검증 각 10장 = 총 100장)
<img width="714" height="1024" alt="image" src="https://github.com/user-attachments/assets/91e9aef2-505d-457f-bc94-a48b6d9d5915" />

<img width="701" height="1043" alt="image" src="https://github.com/user-attachments/assets/f10e4ceb-7f85-4f47-83e3-95f9632a17be" />

<img width="726" height="763" alt="image" src="https://github.com/user-attachments/assets/ce39f067-8691-43c3-86ad-90faf5367483" />

<img width="714" height="940" alt="image" src="https://github.com/user-attachments/assets/24c5d110-f2f5-4bc1-8898-593038b48d9b" />


#### 아두이노 설계도

<img width="770" height="1034" alt="image" src="https://github.com/user-attachments/assets/8ab8f334-c247-46fd-aad4-356564a4f6a9" />


#### 아두이노 코드(센서 연동)

<img width="700" height="1001" alt="image" src="https://github.com/user-attachments/assets/4aec788a-238a-49bf-a48e-7f3dea7d1135" />
<img width="708" height="1002" alt="image" src="https://github.com/user-attachments/assets/81d455db-da3a-4d6e-bfbb-8d505de02820" />


#### 라즈베리파이 코드(카메라 인식)

<img width="696" height="1071" alt="image" src="https://github.com/user-attachments/assets/ec57960d-0894-4c20-9ca1-2e3911cc8876" />

<img width="736" height="1055" alt="image" src="https://github.com/user-attachments/assets/3c9cdbfd-89d4-4c5c-bbbc-eb71de7eb711" />


#### 학습 결과 (Confusion Matrix, 100 epoch, 640x640, batch 16)

<img width="704" height="1041" alt="image" src="https://github.com/user-attachments/assets/47908947-0cf6-460f-8fc2-ac6fe37a9f33" />


---

### 기구 설계 및 구동부 최적화

Onshape로 사료통(상부 지름 115mm, 벽 두께 2.5mm, 하부 입구 84mm) 및 본체를 설계하고 3D 프린터로 제작했습니다.

테스트 중 사료 하중으로 인한 서보모터(MG996R)의 토크 부족이 발생하여, 모터 구동 방식을 재모색하고 배출구의 3D 모델링 두께를 재설계했습니다. 외부 전원(12V, 1.5A)을 독립적으로 인가하여 안정적인 사료 배출(0°~180° 회전) 시스템을 완성했습니다.

#### 초기 구상도
<img width="714" height="911" alt="image" src="https://github.com/user-attachments/assets/b847cf96-a48d-42c7-a76d-75c99e76c168" />

<img width="693" height="1037" alt="image" src="https://github.com/user-attachments/assets/b7e4c4fc-7737-4da2-8d87-fd80d635c311" />

---

### 센서 제어 알고리즘 구현

Arduino Uno를 활용해 PIR 센서(움직임 감지)를 연동하고, HC-SR04 초음파 센서로 사료통 내부 거리를 측정하여 임계값 6.25cm 도달 시 잔량 부족 알람(LED 점등)이 작동하도록 하드웨어 로직을 구현했습니다.

PIR 센서가 물체를 인식하면 아두이노는 명령에 따라 MG996R 서보모터를 강아지면 0°, 고양이면 180°로 회전시켜 5초간 사료를 배출한 뒤 90°(중립)로 복귀합니다.

---

### 트러블슈팅

**서보모터 기동 시 전압 강하 → 메인보드 리셋**

서보모터(MG996R) 기동 시 5V 레귤레이터 출력이 4.95V에서 4.2V까지 떨어지며 Arduino가 리셋되는 현상이 반복됐습니다.

동료는 소프트웨어 통신 오류를 의심했으나, 전압 강하 패턴이 모터 기동 시점과 정확히 일치하는 것을 확인하고 전원 회로 문제라고 판단했습니다. 멀티미터로 각 모듈의 구동 전압을 개별 측정한 결과, Arduino와 서보모터가 동일 전원을 공유하면서 모터의 돌입 전류가 레귤레이터 허용 한계를 초과한 것이 원인이었습니다.

모터 구동용 외부 직류전원(12V)을 독립 인가하여 해결했습니다. 시연 당일 다른 팀 절반이 모터 고장으로 실패했으나 안정적으로 구동됐습니다.

**UART 통신 전압 불일치**

Raspberry Pi(3.3V)와 Arduino(5V) 간 UART 직렬 통신에서 전압 차이로 신호가 깨졌습니다. 10kΩ + 20kΩ 저항으로 전압 분배 회로를 구성하여 5V → 3.3V 레벨 시프팅을 구현했습니다.

---

### 결과

<img width="530" height="514" alt="image" src="https://github.com/user-attachments/assets/cdc3faed-22ec-49f0-b3d6-dc30a9148326" />

전체 시스템 동작 구현까지 완성하여 장려상을 수상했습니다.

[← 메인으로](../README.md)
