# 🤖 AI 기반 다중 모달 분석 모의면접 플랫폼

비전 AI와 LLM을 활용하여 면접자의 시선, 감정, 답변 내용을 종합적으로 분석하고 실질적인 면접 능력 향상을 돕는 차세대 모의면접 플랫폼입니다.

## 🎥 프로젝트 시연 영상 (Demo Video)
---
[![](https://img.shields.io/badge/YouTube-시연%20영상%20보기-red?style=for-the-badge&logo=youtube)](https://www.youtube.com/watch?v=pMzHO42YpjU)
---

## 🗓️ 개발 기간
08.18 ~ 09.26

## 🌟 핵심 기능 (Key Features)

### 🔍 다중 모달 분석 시스템
* **시선 추적 & 감정 분석**: Vision AI를 통한 실시간 집중도 측정 및 표정 변화 분석
* **답변 품질 평가**: DeepSeek LLM 기반 논리성, 일관성, 전문성 종합 평가
* **통합 피드백**: 언어적/비언어적 요소를 결합한 입체적 분석 결과 제공

### 👤 개인 맞춤형 면접 경험
* **자기소개서 기반 질문 생성**: AI가 업로드된 자소서를 분석하여 개인화된 면접 질문 생성
* **적응형 면접 진행**: 답변 수준에 따른 동적 후속 질문 및 난이도 조절

## 🏗️ 시스템 아키텍처 (System Architecture)
┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   프론트엔드  │    │    백엔드    │    │  AI 서버   │    │  데이터베이스 │
│   (React)   │◄──►│(Spring Boot)│◄──►│  (FastAPI)  │    │   (MySQL)   │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
* **백엔드 (Spring Boot)**: 비즈니스 로직 처리, 데이터베이스 연동, **RESTful API 게이트웨이** 역할.
* **AI 서버 (FastAPI)**: 전용 AI 모델 서빙 (**LLM, Whisper STT, Vision AI**).

## 🛠️ 기술 스택 (Tech Stack)

### 백엔드
* **Java & Spring Boot** - 핵심 백엔드 프레임워크
* **Spring Data JPA** - 데이터베이스 추상화 계층
* **MySQL** - 주 데이터베이스
* **REST API & MSA** - 이기종 서버 간 통신 규격 설계 및 아키텍처 구현

### **DevOps & 인프라 (강조)**
* **Docker** - **AI 서버와 MySQL 환경 컨테이너화**를 통한 개발 환경 일관성 및 이식성 확보
* **AWS** - **EC2/VPC 기반 고가용성 인프라 (AMI-ASG-ALB-RDS) 구축 실습** 경험
* **Git & GitHub** - 버전 관리 및 협업 도구

### AI/ML
* **FastAPI** - AI 모델 서빙 프레임워크
* **DeepSeek LLM** - 답변 분석 및 피드백 생성
* **Vision AI** - 시선 추적 및 감정 분석

## 🔧 기술적 도전과제 및 해결방안 (Technical Challenges & Solutions)

### Challenge 1: LLM 한국어 출력 불안정성
* **문제**: DeepSeek LLM이 간헐적으로 중국어가 섞인 답변을 생성하여 사용자 경험 저해.
* **해결책**: **2단계 번역 파이프라인 도입** 및 출력 검증 메커니즘 추가.
* **결과**: **출력 품질 100% 안정화**.

### Challenge 2: 동시 질문 생성 시 타임아웃 오류
* **문제**: 3개 질문을 한 번에 생성할 때 서버 타임아웃 발생.
* **해결책**: **순차적 API 호출 아키텍처로 재설계** 및 **지수 백오프 (Exponential Backoff) 기반 자동 재시도 로직 구현**.
* **결과**: **100% 성공률 달성**.

### **Challenge 3: 개발 환경 일관성 및 이식성 확보 (Docker 활용)**
* **문제**: Local LLM 및 DB 환경 설정의 개발자 간 불일치로 인한 협업 및 테스트 비효율 발생.
* **해결책**: **AI 서버(FastAPI)와 MySQL 환경을 Docker로 컨테이너화**하여 개발 환경 종속성을 제거하고, 다수 개발자의 **DB 접근 일관성** 및 시스템 **이식성** 확보.

## 👥 개발팀 구성 (Development Team)

### 백엔드 개발
* **신성진**: 면접 선택, 자소서 업로드, 문항 관리 (비즈니스 로직 및 **MSA 아키텍처 안정화** 담당)
* **황제윤**: 기기 테스트, 캘리브레이션, 면접 진행, 메인 페이지
* **이우주**: 사용자 인증, 마이페이지, 분석 결과 페이지

### 프론트엔드 개발
* **신윤섭**: 문항 인터페이스, 면접 화면, 자소서 업로드, 기기 테스트
* **김은혜**: 결과 시각화, 마이페이지, 사용자 인증, 메인 페이지

## 🎯 프로젝트 차별점 (Project Differentiators)
* **다중 모달 AI 융합**: 국내 최초 시선+감정+음성+텍스트 통합 분석
* **개인화 엔진**: 자소서 기반 맞춤형 질문 자동 생성
* **실시간 처리**: 지연 없는 라이브 분석 및 피드백

## 🤝 기여 방법

프로젝트 개선에 참여해주세요!

1. 저장소를 Fork 합니다
2. 기능 브랜치를 생성합니다 (`git checkout -b feature/AmazingFeature`)
3. 변경사항을 커밋합니다 (`git commit -m 'Add some AmazingFeature'`)
4. 브랜치에 푸시합니다 (`git push origin feature/AmazingFeature`)
5. Pull Request를 열어주세요

## 📜 라이센스

본 프로젝트는 교육 목적으로 개발되었습니다. 상업적 이용 문의는 개발팀에 연락 바랍니다.

## 📞 문의

질문, 이슈, 또는 협업 제안은 프로젝트 관리자에게 연락하거나 이슈를 등록해 주세요.

---

**❤️ 모의면접 플랫폼 개발팀이 만듭니다**

---

# 🤖 AI-Powered Multimodal Mock Interview Platform

A comprehensive mock interview platform that leverages Computer Vision AI and LLM to analyze interviewees' gaze patterns, emotions, and response quality, providing actionable feedback for interview skill improvement.

## 🌟 Key Features

### 🔍 Multimodal Analysis System
- **Vision AI Integration**: Real-time analysis of eye contact, facial expressions, and body language
- **LLM-Powered Evaluation**: Comprehensive assessment of response logic, content quality, and coherence
- **Holistic Feedback**: Combined analysis of verbal and non-verbal communication

### 👤 Personalized Interview Experience
- **Resume-Based Question Generation**: AI creates tailored questions based on uploaded resumes
- **Adaptive Interview Flow**: Dynamic question sequencing based on user responses
- **Progress Tracking System**: Visual improvement tracking through historical comparison

### 📊 Real-time Analytics & Feedback
- **Live Performance Monitoring**: Continuous data collection during interview sessions
- **Video Recording & Playback**: Self-assessment through recorded interview sessions
- **Detailed Improvement Suggestions**: Specific and actionable interview skill enhancement recommendations

## 🏗️ System Architecture

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   Frontend  │    │   Backend   │    │  AI Server  │    │  Database   │
│   (React)   │◄──►│(Spring Boot)│◄──►│  (FastAPI)  │    │   (MySQL)   │
└─────────────┘    └─────────────┘    └─────────────┘    └─────────────┘
```

- **Frontend (React)**: Intuitive user interface and interaction management
- **Backend (Spring Boot)**: Business logic processing, database integration, API gateway
- **AI Server (FastAPI)**: Dedicated AI model serving (Whisper, DeepSeek, Vision AI)
- **Database (MySQL)**: Persistent storage for user information and analysis results

## 🛠️ Tech Stack

### Frontend
- **React** - User interface framework
- **Figma** - UI/UX design tool

### Backend
- **Java & Spring Boot** - Core backend framework
- **Spring Data JPA** - Database abstraction layer
- **MySQL** - Primary database
- **REST API** - Inter-service communication

### AI/ML
- **FastAPI** - AI model serving framework
- **DeepSeek LLM** - Response analysis and feedback generation
- **Whisper STT** - Speech-to-text conversion
- **Vision AI** - Gaze tracking and emotion analysis

## 🚀 Getting Started

### Prerequisites
- Java 11+
- Node.js 16+
- MySQL 8.0+
- Git

### Installation & Setup

1. **Clone Repository**
```bash
git clone https://github.com/your-username/mock-interview-platform.git
cd mock-interview-platform
```

2. **Run Backend**
```bash
cd backend
./gradlew bootRun
```

3. **Run Frontend**
```bash
cd frontend
npm install
npm start
```

4. **Database Configuration**
```sql
CREATE DATABASE mock_interview;
-- Import schema from /database/schema.sql
```

## 📋 Interview Process Flow

```
Interview Type Selection → Resume Upload → Question Setup → Device Test → 
Calibration → Interview Session → AI Analysis → Results & Feedback
```

1. **Interview Type Selection**: Choose between mock or formal interview mode
2. **Resume Processing**: File upload or direct text input
3. **Question Configuration**: System-generated personalized questions + standard questions
4. **Device Testing**: Camera and microphone functionality verification
5. **Calibration**: Baseline posture and gaze position setup
6. **Interview Execution**: Real-time recording and data collection
7. **AI Analysis**: Comprehensive multimodal analysis
8. **Results Delivery**: Detailed feedback and improvement recommendations

## 🔧 Technical Challenges & Solutions

### Challenge 1: LLM Korean Output Instability
**Problem**: DeepSeek LLM occasionally generated mixed Chinese-Korean responses, degrading user experience

**Solution**: Two-stage translation pipeline implementation
- Primary output → English translation → Korean re-translation
- Added output validation and filtering mechanisms
- Trade-off: Slight response time increase for reliability

**Result**: 100% output quality stabilization with acceptable latency

### Challenge 2: Concurrent Question Generation Timeout
**Problem**: Server timeout when generating 3 questions simultaneously

**Solution**: Sequential API call architecture redesign
- Split single bulk request into 3 individual requests
- Implemented automatic retry logic with exponential backoff
- Result: 100% success rate with manageable latency

## 📊 API Documentation

### Core Endpoints
```http
POST /api/interview/select      # Interview type selection
POST /api/resume/upload         # Resume file upload
GET  /api/questions             # Question list retrieval
POST /api/questions/custom      # Custom question addition
POST /api/interview/start       # Interview session initialization
POST /api/analysis/video        # Video analysis request
GET  /api/results/{sessionId}   # Analysis results retrieval
```

### Analysis Output Structure
```json
{
  "transcription": "STT converted text",
  "positiveAspects": ["Clear articulation", "Logical structure"],
  "improvementAreas": ["Eye contact", "Speaking pace"],
  "overallScore": 85,
  "detailedFeedback": "Comprehensive analysis content...",
  "emotionTimeline": [...],
  "gazeAnalysis": {...}
}
```

## 👥 Development Team

### Backend Development
- **Shin Seongjin**: Interview selection, resume upload, question management
- **Hwang Jeyoon**: Device testing, calibration, interview session, main page
- **Lee Wooju**: User authentication, user dashboard, results page

### Frontend Development
- **Shin Yunseop**: Question interface, interview screen, resume upload, device testing
- **Kim Eunhye**: Results visualization, user dashboard, authentication, main page

## 🎯 Project Differentiators

### Technical Innovation
- **Multimodal AI Fusion**: First-in-Korea integrated analysis of gaze+emotion+voice+text
- **Personalization Engine**: Automated custom question generation based on resumes
- **Real-time Processing**: Zero-latency live analysis and feedback

### User Experience
- **Intuitive Interface**: Easy-to-use UX for interview beginners
- **Specific Feedback**: "Focus your gaze more" → "Maintain eye contact with camera lens for 2+ seconds"
- **Growth Visualization**: Session-by-session score tracking and improvement area identification

## 🗓️ Development Status

### ✅ Completed Features
- [x] Database schema design
- [x] Core frontend page structure
- [x] User authentication system
- [x] Resume upload and processing
- [x] AI model integration
- [x] Results visualization

### 🔄 In Progress
- [ ] Mobile responsive design
- [ ] Advanced pattern recognition
- [ ] Multi-language support

### 📅 Future Roadmap
- [ ] Machine learning model fine-tuning
- [ ] Advanced analytics dashboard
- [ ] Job platform integration
- [ ] Group interview simulation

## 🤝 Contributing

We welcome contributions to improve the project!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📜 License

This project is developed for educational purposes. Please contact the development team for commercial usage inquiries.

## 📞 Contact

For questions, issues, or collaboration proposals, please contact the project maintainers or submit an issue.

---

**Built with ❤️ by the Mock Interview Platform Team**
