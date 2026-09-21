# TCAD 기반 CMOS Inverter 공정 설계 및 소자 특성 분석

부경대학교 전자공학과 반도체공정설계 수업 팀 프로젝트입니다.
Synopsys Sentaurus TCAD를 활용하여 NMOS 및 CMOS Inverter의 전 공정을 설계하고 전기적 특성을 분석했습니다.

**2025.05 ~ 2025.06**

---

### 역할

팀원, 반도체 공정 코드 및 전기적 연결 코드 작성 및 최적화

### 사용 기술

Synopsys TCAD Sentaurus (S-Process, S-Device), NMOS/CMOS Inverter, STI, 이온 임플란트, Gate Oxide, LDD Spacer

---

### 공정 설계

Synopsys Sentaurus TCAD를 활용하여 STI, N-Well, LDD부터 금속 컨택에 이르는 전 공정 레시피를 코드로 작성해 NMOS 및 CMOS Inverter를 설계했습니다. 도핑 농도와 산화막 두께 파라미터 변화를 통해 Vth를 조절하며, 채널 길이를 50nm에서 1μm까지 변경하여 Id-Vg, Id-Vd 특성을 비교했습니다.

---

### 특성 분석

50nm 채널에서 DIBL이 0.33V/V, SS가 130mV/dec로 급증하는 단채널 효과(SCE)를 수치적으로 확인했습니다. 이후 Gate Length 2.4μm의 CMOS Inverter를 추가로 설계하여 VTC(Voltage Transfer Characteristic) 곡선의 스위칭 특성과 고노이즈 마진(Noise Margin)을 검증함으로써, 미세 공정 파라미터 세팅이 최종 소자의 전기적 성능에 미치는 영향을 체득했습니다.

---

### 배운 점

- TCAD 시뮬레이션에서 파라미터 하나의 변화가 소자 특성에 미치는 영향을 정량적으로 확인
- 팀원에게 답을 알려주는 대신 원리를 함께 공부하여, 이후 프로젝트 속도가 향상되고 발표를 성공적으로 완수

[← 메인으로](../README.md)
