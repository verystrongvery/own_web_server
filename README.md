# 📜 **프로젝트 요약**

- TCP/IP 기반의 간단한 웹서버 구현

# 📅 프로젝트 기간

- 2024.01 ~ 2024.01

# 🫙 Github

- https://github.com/verystrongvery/own_web_server
# 🛠 기술 스택

- C, Linux

# 🏫 프로젝트에서 배운점

### 소켓 통신을 위한 System Call 사용하기

- **socket**: 소켓 통신을 위한 서버 소켓을 생성하는 역할
- **bind**: 서버 소켓에 IP 주소와 포트 번호 할당하는 역할
- **listen**: 클라이언트의 요청을 받을 수 있도록 연결 대기 상태로 설정하는 역할
- **accept**: 클라이언트의 요청을 수락하고, 클라이언트 소켓을 생성하는 역할
- **close**: 다 사용한 소켓을 제거하는 역할

# 🖥 **프로젝트 구현 내용**

### 1. 네트워크 통신을 할 때, 앤드포인트 역할을 하는 서버의 소켓 생성

- `socket`를 호출하여 서버의 소켓 생성
- IPv4 프로토콜, TCP 소켓 사용

### 2. 서버의 소켓 초기화

- 서버 소켓에 할당할 주소 데이터를 네트워크 바이트 순서에 맞게 변환
- `bind`를 호출하여 서버의 소켓에 IP 주소와 포트 번호 할당
- `listen`를 호출하여 클라이언트의 요청을 받을 수 있도록 연결 대기 상태로 설정

### 3. 클라이언트의 요청

- `accept`를 호출하여 서버에서 클라이언트의 요청을 수
- 클라이언트의 소켓 생성
- `pthread_create`를 호출하여 클라이언트에게 정적 컨텐츠(HTML 파일)를 제공하는 역할을 하는 쓰레드 생성

### 4. 요청 메시지 읽기

- `fdopen`를 호출하여 클라이언트 소켓을 통해 입력 스트림 열기
- `fgets`를 호출하여 입력 스트림을 통해 요청 메시지 읽기
- 요청 메시지를 통해 클라이언트가 조회하려는 정적 컨텐츠(HTML 파일)  확인

### 5. 응답 메시지 전송

- `fdopen`를 호출하여 클라이언트 소켓을 통해 출력 스트림 열기
- `fputs`를 호출하여 출력 스트림을 통해 응답 메시지에 `Status Line`과 정적 컨텐츠(HTML 파일) 전송

# 🍊 프로젝트 실행

### 1. 웹서버에 클라이언트가 요청 하려는 정적 컨텐츠(HTML 파일)

![Untitled](https://github.com/verystrongvery/own_web_server/assets/147907168/91e0d21d-5abe-442f-bf2a-3fd2950da494)

### 2. 소스 컴파일 및 실행

![Untitled (1)](https://github.com/verystrongvery/own_web_server/assets/147907168/f818fbf9-5aa4-4330-96f5-0cd1a5124e6f)

### 3. 클라이언트가 웹서버에 요청

![Untitled (2)](https://github.com/verystrongvery/own_web_server/assets/147907168/a73dedaf-77ba-4873-b22a-fd1a039e192c)
