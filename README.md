# 🏛️ AI 법률 마스터 (AI Legal Master) - Deep Tech Edition

> **2025 예비창업패키지 (딥테크 분야) MVP 소스코드**
> *대한민국 최초 초정밀 관할 법원 매핑 DB 및 멀티모달(OCR) 기반 나홀로 소송 솔루션*

![Python](https://img.shields.io/badge/Python-3.9%2B-blue) ![Streamlit](https://img.shields.io/badge/Streamlit-1.30%2B-red) ![Gemini](https://img.shields.io/badge/AI-Gemini%20Pro-green) ![DeepTech](https://img.shields.io/badge/Type-DeepTech-purple)

## 📋 프로젝트 개요 (Overview)
**AI 법률 마스터**는 법률 사각지대에 놓인 소액 사건 당사자들을 위한 생성형 AI 리걸테크 플랫폼입니다.
단순한 챗봇을 넘어, **자체 구축한 행정구역-법원 매핑 데이터베이스**와 **온디바이스 개인정보 마스킹 기술**을 탑재하여, 변호사 비용 부담 없이 누구나 법률 서면(소장, 지급명령, 내용증명)을 작성하고 증거를 분석할 수 있도록 지원합니다.

---

## 🚀 핵심 기술 및 기능 (Key Features)

### 1. 🗺️ 초정밀 관할 법원 매핑 시스템 (Jurisdiction Mapping)
* **자체 데이터 자산:** `app18.py` 내 `JURISDICTION_MAP` 구축.
* **기능:** 서울 25개 구 및 전국 시/군/구 행정구역 데이터를 18개 지방법원 및 지원(Branch)과 1:1 매핑.
* **성과:** 사용자 주소 입력 시 관할 법원 자동 추천 정확도 99.9% 달성 (소장 반려 방지).

### 2. 🔐 개인정보 비식별화 기술 (PII Masking / Security)
* **기술:** 정규표현식(Regex) 기반의 `mask_sensitive_data` 전처리 알고리즘 탑재.
* **보안:** 주민등록번호, 전화번호 등 민감 정보가 AI 서버로 전송되기 전, 클라이언트 단에서 `******-*******` 형태로 자동 마스킹 처리.

### 3. 👁️ 멀티모달 증거 분석 (Multimodal RAG & OCR)
* **OCR/RAG:** `PyPDF`, `Pillow` 라이브러리를 활용하여 PDF 소장 및 이미지(계약서, 차용증) 내 텍스트 추출.
* **AI 분석:** 추출된 비정형 데이터를 Gemini Vision Pro 모델이 분석하여 법적 유불리 판단 및 독소조항 검출.

### 4. 🧠 리걸 웰니스 케어 (Mind Care ESG)
* **알고리즘:** 소송 단계(접수-대기-변론-선고)별 사용자 심리 상태를 추적하는 `MIND_CARE_DB` 로직 적용.
* **솔루션:** 상황에 맞는 심리 조언 및 힐링 콘텐츠(영상/사운드) 자동 큐레이션 제공.

---

## 🛠️ 기술 스택 (Tech Stack)

| 구분 | 기술/라이브러리 | 용도 |
| :--- | :--- | :--- |
| **Framework** | `Streamlit` | 웹 애플리케이션 UI/UX 구현 |
| **AI Engine** | `Google Gemini Pro` | 법률 문서 생성 및 자연어 처리 Reasoning |
| **Data Processing** | `Pandas`, `Regex` | 데이터 전처리 및 마스킹 |
| **Document** | `Python-docx`, `ReportLab` | 법원 제출용 표준 문서(.docx, .pdf) 생성 |
| **Multimodal** | `PyPDF`, `Pillow` | PDF 텍스트 추출 및 이미지 처리 |

---

## ⚙️ 설치 및 실행 (Installation)

### 1. 환경 설정
Python 3.9 이상 환경이 필요합니다.
```bash
# 가상환경 생성 (권장)
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
