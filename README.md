# container-monitoring-limited-http

# HTTP가 제한된 환경에서의 컨테이너 모니터링 도구 개발

## 📌 프로젝트 개요  
본 프로젝트는 **HTTP가 제한된 환경에서 컨테이너를 모니터링하는 도구**를 개발하는 것을 목표로 합니다.  
센서 네트워크 환경에서는 HTTP 프로토콜 사용이 제한적이므로, 기존 Prometheus 기반의 모니터링 솔루션을 적용하기 어려운 문제가 발생합니다.  
이를 해결하기 위해, **Kafka를 활용한 비(非)HTTP 기반의 메트릭 수집 및 저장 시스템을 설계 및 개발**합니다.

## 🎯 목표 및 주요 기능  
- **메트릭 수집 도구 및 Kafka Connector 제작**  
  - HTTP 사용이 제한된 환경에서도 **Kafka를 이용한 메트릭 전송**이 가능하도록 개발  
  - 로깅 및 정상 동작 여부를 모니터링할 수 있도록 **컨테이너 로그 수집 기능** 추가  
- **메트릭 저장 및 환경 구성 개발**  
  - Kafka에서 수집된 데이터를 **API 서버 및 DB에 저장**하는 시스템 구축  
  - 저장된 데이터를 시각화할 수 있도록 **웹 기반 대시보드** 개발  
- **웹 기반 UI/UX 개발**  
  - 사용자가 시스템 정상 동작을 모니터링할 수 있는 대시보드 제공  
  - **알람 기능 추가**: 특정 임계값(threshold)을 초과하면 사용자에게 경고  

## 🛠 기술 스택  
- **백엔드**: Python, Java Spring, Kafka  
- **프론트엔드**: React.js (TypeScript), TailwindCSS  
- **기타**: Docker, GitHub Actions  

## 📌 기대 효과  
- HTTP 제한이 있는 환경에서도 안정적으로 **컨테이너 상태 및 성능을 모니터링** 가능  
- 디지털 트윈 기반의 센서 감시 시스템을 효율적으로 운영할 수 있도록 지원  
- 보안상의 이유로 HTTP를 사용할 수 없는 환경에서도 **오픈소스 기반의 모니터링 솔루션** 제공  

## 📂 프로젝트 구조  
```plaintext
📦 프로젝트 루트
 ┣ 📂 backend       # 백엔드 (Kafka, Spring Boot 등)
 ┣ 📂 frontend      # 프론트엔드 (React.js)
 ┣ 📂 collector     # 컨테이너 모니터링 수집기
 ┣ 📂 docs          # 문서화 관련 자료
 ┣ 📜 README.md     # 프로젝트 설명 문서
 ┗ 📜 .gitignore    # Git 제외 파일 설정
```

## 📢 설치 및 실행 방법  
### 1. **프로젝트 클론**  
```sh
git clone https://github.com/knu-capstone-design-2/container-monitoring.git
cd container-monitoring
```
### 2. **백엔드 실행**  
```sh
cd backend
docker-compose up -d
```
### 3. **프론트엔드 실행**  
```sh
cd frontend
npm install
npm start
```
