## 📌 프로젝트 개요
스마트 팩토리 환경에서 실시간으로 PCB 생산 데이터를 수집, 분석, 시각화하는 WPF 기반 데스크톱 애플리케이션입니다.  
PLC, MySQL, OpenCV, YOLO 모델을 연동하여 설비의 생산성과 품질을 통합적으로 관리할 수 있도록 구현하였습니다.

> **기간**: 2025.07.01 ~ 2025.07.30
> **인원**: 2인  
> **목표**: PCB 생산 상태의 실시간 모니터링 제어 및 품질 불량 자동 감지

---

## 🔍 주요 기능
- ✅ 실시간 설비 상태 모니터링 (온도, 습도, 오염도 등)
- ✅ 카메라 기반 불량 탐지 (YOLO + OpenCV)
- ✅ MySQL 연동을 통한 설비 이력 저장
- ✅ MVVM 패턴 기반 WPF 구조 적용
- ✅ PLC 릴레이 스위치로 설비 제어
- ✅ LiveCharts를 이용한 시각적 데이터 표현
- ✅ 다중 탭 구성으로 설비별 개별 관리

---

## 🛠️ 사용 기술

| 분류 | 기술 |
|------|------|
| Frontend | WPF (.NET 8), XAML, MVVM |
| Backend | C#, DispatcherTimer, MySQL |
| AI Vision | OpenCV, Pyzbar, YOLOv5 |
| Communication | Modbus TCP/IP |
| Data | MySQL |
| Chart | LiveCharts.Wpf, C1.WPF.Gauge |
| Tooling | Visual Studio, Git, MySQL Workbench, XG5000 |

---

## 📂 프로젝트 구조
```
POP_Project/
├── Models/           # 데이터 모델
├── ViewModels/       # MVVM 구조의 ViewModel
├── Views/            # UI 화면
├── Repository/       # DB 연동
|
├── Communication/    # PLC 연동 로직
|   
├── OPENCV_Python/    # OpenCV 및 YOLO 기반 비전 처리
└── App.xaml.cs
```

## 📸 시연 화면

### 🔧 대시보드
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/05acb1d6-7cbc-45c8-9b0f-70799af99c70" />#

### 🔧 생산, 설비, 이력 상태
<img width="300" height="200" alt="facility" src="https://github.com/user-attachments/assets/de4ea78f-4c86-4c96-ad69-66e120caeacb" />
<img width="300" height="200" alt="facility" src="https://github.com/user-attachments/assets/e1cbcf93-8fd8-451f-9b25-aea04264319b" />
<img width="300" height="200" alt="log" src="https://github.com/user-attachments/assets/2cb62824-c8b1-4eae-8566-4b913db5945f" />

### 🔌 PLC 모니터
<img width="600" height="400" alt="PLC_LD" src="https://github.com/user-attachments/assets/3b2ddd0f-55b9-482b-b475-d90ca7e05cf7" />


### 📷 불량 인식 화면
<img width="1281" height="498" alt="image" src="https://github.com/user-attachments/assets/b33cede2-6758-4b0c-a7fb-1a6f695bbe2c" />


---

## 💡 트러블슈팅 & 개선

- **LD 이중코일**  
  램프1, 2로 불량 검출 램프를 분리하여 직관성 향상 

- **PLC 통신 IP 대역**  
  PLC IP 대역을 0으로 변경하여 통일

- **Modbus 로직 매핑**  
  Modbus 비트 읽기, 쓰기 영역을 메모리 타입인 %MX0~로 보완하고 ModbusControl ip, port 명시

- **순환 참조**  
  OpenCV를 키는 파일에 QR코드 리더기 로직을 추가하여 기능 통합

- **QR코드 read 반복**  
  QR에 반제품/완제품을 미리 구별하여 DB에 UPDATE 후
  반제품일때 → 1차 검사만 진행
  완제품일때 → 2차 검사만 진행

- **Git 업로드 및 충돌 문제**  
  .gitignore 파일 작성 후 git rm –cached로 Git에 스테이징 된 부분 삭제 및 .gitignore 파일 수정

---

## ✨ 주요 성과

- PLC – WPF – OpenCV – MySQL 간 실시간 통신 구조 구현
- 카메라 영상에서 불량 자동 감지 성공
- LiveCharts 기반 공장 상태 시각화 구현

---

## 👨‍💻 개발자

| 이름 | GitHub | Email |
|------|--------|-------|
| 유현수 | [github.com/your-id](https://github.com/HYUN-SU123) | gustn8608@naver.com |

---

## 📎 기타
- 본 프로젝트는 개인 포트폴리오 및 스마트팩토리 연계 실습 과제로 제작되었습니다.  
- 사용된 모델 및 데이터는 테스트용이며 상용 목적이 아닙니다.
