# Linux Shell 개념 정리

## 1. 운영체제 구조
운영체제는 크게 두 가지 레벨로 구성된다.

| 구분 | 설명 |
|------|------|
| User Level | 사용자가 직접 상호작용하는 영역 |
| Kernel Level | 시스템 자원을 관리하는 핵심 영역 (사용자 직접 접근 불가) |

---

## 2. Shell이란?
Shell은 **사용자와 커널 사이에서 명령을 전달하는 인터페이스(명령어 해석기, Command Interpreter)**이다.

- 사용자의 명령어를 해석하여 커널에 전달
- 커널의 처리 결과를 사용자에게 출력

---

## 3. Shell의 종류

### 3.1 GUI Shell
(Graphical User Interface Shell)

- 특징: 그래픽 기반 인터페이스
- 장점: 직관적이고 사용이 쉬움
- 단점: 속도가 느리고 자원 사용량이 많음

---

### 3.2 CLI Shell
(Command-Line Interface Shell)

- 특징: 명령어 기반 인터페이스
- 장점: 빠르고 정밀한 작업 가능
- 단점: 비직관적이며 명령어 암기 필요

> 리눅스 서버 환경에서는 CLI Shell이 주로 사용된다.

---

## 4. 주요 Shell 종류

| Shell | 설명 |
|------|------|
| sh | Bourne Shell (기본적인 Shell) |
| bash | Bourne-Again Shell (sh 확장, 가장 널리 사용됨) |
| ash / dash | 경량 Shell (빠른 실행 속도) |
| zsh | 강력한 기능과 커스터마이징 지원 |

---

## 5. 명령어 사용 예시
Shell에서는 다양한 명령어를 통해 시스템을 제어할 수 있다.

- ls : 파일 및 디렉토리 목록 확인
- cd : 디렉토리 이동
- pwd : 현재 위치 확인

> 자세한 명령어 사용법은 별도 문서에서 다룬다.

---

## 6. 핵심 정리
- Shell은 사용자와 커널을 연결하는 인터페이스이다.
- 명령어를 해석하는 Command Interpreter 역할을 수행한다.
- CLI Shell은 서버 환경에서 필수적으로 사용된다.
- bash는 가장 대표적인 Shell이다.
