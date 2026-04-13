# HTTP와 HTTPS

## 1. HTTP

HTTP(HyperText Transfer Protocol)는 사용자의 웹 브라우저와 웹 서버 간에 데이터를 주고받기 위한 통신 규약이다.

- 기본 포트: **80**
- 클라이언트는 TCP 80번 포트를 통해 서버에 연결
- 1989년 팀 버너스 리가 설계
- 월드 와이드 웹(WWW)의 기반 기술

초기의 HTTP는 단순한 데이터 전송 프로토콜이었지만, 이후 요청(Request)과 응답(Response) 구조로 발전하였다.

하지만 HTTP는 데이터를 **암호화하지 않고 평문으로 전송**하기 때문에 보안에 취약하다.

---

## 2. HTTPS

HTTPS(HyperText Transfer Protocol Secure)는 HTTP에 보안 기능을 추가한 프로토콜이다.

- 기본 포트: **443**
- SSL/TLS 프로토콜을 사용하여 데이터 암호화
- 넷스케이프에서 개발
- 보안이 중요한 서비스(로그인, 결제 등)에 사용

HTTPS는 데이터를 암호화하여 전송하기 때문에 중간에서 데이터를 가로채더라도 내용을 확인하기 어렵다.  
또한 HTTPS를 사용하려면 **SSL/TLS 인증서**가 필요하다.

---

## 3. HTTP Method

HTTP Method는 클라이언트가 서버에 요청할 때 **수행할 작업의 종류**를 나타낸다.

| Method | 설명 |
|--------|------|
| GET    | 데이터 조회 |
| POST   | 데이터 생성 |
| PUT    | 데이터 수정 |
| DELETE | 데이터 삭제 |

### 예시
```
GET /users
POST /users
```

---

## 4. HTTP Status Code

HTTP Status Code는 서버가 요청 처리 결과를 **숫자로 반환하는 코드**이다.

| 코드 | 의미 |
|------|------|
| 200  | OK (요청 성공) |
| 201  | Created (생성 성공) |
| 400  | Bad Request (잘못된 요청) |
| 401  | Unauthorized (인증 필요) |
| 404  | Not Found (리소스 없음) |
| 500  | Internal Server Error (서버 오류) |

### 분류
- 1xx: 정보
- 2xx: 성공
- 3xx: 리다이렉션
- 4xx: 클라이언트 오류
- 5xx: 서버 오류

---

## 5. HTTP의 무상태성 (Stateless)

HTTP는 **무상태성(Stateless)** 을 가진다.

서버가 클라이언트의 이전 요청을 기억하지 않는다.

### 예시
로그인 후 다른 페이지로 이동하면 서버는 로그인 상태를 기억하지 못한다.

### 해결 방법
- 쿠키(Cookie)
- 세션(Session)

이러한 기술을 통해 사용자 상태를 유지한다.

---

## 6. HTTP vs HTTPS

| 구분 | HTTP | HTTPS |
|------|------|------|
| URL | http:// | https:// |
| 보안 | 없음 (평문) | 있음 (암호화) |
| 포트 | 80 | 443 |
| 속도 | 빠름 | 거의 차이 없음 |
| 인증서 | 필요 없음 | 필요 |

---

## 7. 정리

- HTTP는 암호화되지 않은 통신 방식으로 보안에 취약하다.
- HTTPS는 SSL/TLS로 데이터를 암호화한다.
- HTTP는 Method와 Status Code를 사용한다.
- HTTP는 Stateless 구조이며, 쿠키와 세션으로 이를 보완한다.
- 현재는 HTTPS 사용이 사실상 표준이다.
