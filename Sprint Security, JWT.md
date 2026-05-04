# Spring Security + JWT 정리

## 1. 개요
Spring Security는 Spring 기반 애플리케이션에서  
인증(Authentication)과 인가(Authorization)를 담당하는 보안 프레임워크이다.

- 모든 요청을 Filter 기반으로 처리
- 보안 로직을 직접 구현하지 않아도 됨
- JWT와 함께 사용하면 세션 없이 인증 처리 가능 (Stateless)

---

## 2. 전체 흐름
클라이언트 요청
→ DelegatingFilterProxy
→ FilterChainProxy
→ 인증(Authentication)
→ 인가(Authorization)
→ Controller

---

## 3. 주요 아키텍처

### 3.1 DelegatingFilterProxy
- 서블릿 컨테이너와 스프링 컨테이너 연결
- 요청을 스프링 빈(FilterChainProxy)에 위임
- 실제 보안 처리는 하지 않음

---

### 3.2 FilterChainProxy
- 실제 보안 처리 담당
- 여러 개의 SecurityFilterChain 관리
- URL에 맞는 필터 체인을 선택

---

## 4. 인증 (Authentication)

### 개념
사용자가 누구인지 확인하는 과정

### Authentication 객체 구조
- principal : 사용자 정보
- credentials : 비밀번호
- authorities : 권한 목록
- authenticated : 인증 여부

---

## 5. SecurityContext
SecurityContextHolder
→ SecurityContext
→ Authentication

### 특징
- 인증 정보 저장소
- 전역에서 접근 가능
- 기본적으로 세션 기반 저장

---

## 6. 인증 흐름
UsernamePasswordAuthenticationFilter
→ AuthenticationManager
→ AuthenticationProvider
→ UserDetailsService
→ DB 조회
→ 인증 성공
→ SecurityContext 저장

---

## 7. JWT (JSON Web Token)

### 7.1 JWT란
JSON 기반의 인증 토큰으로, 클라이언트가 인증 상태를 저장하는 방식이다.  
서버는 세션을 유지하지 않는 Stateless 구조를 가진다.

---

### 7.2 JWT 구조
Header.Payload.Signature

#### 구성 요소
- Header : 토큰 타입, 서명 알고리즘
- Payload : 사용자 정보, 권한
- Signature : 토큰 위변조 방지

---

### 7.3 JWT 특징

장점:
- 세션이 필요 없음
- 서버 부하 감소
- 확장성 우수 (REST API, MSA 구조에 적합)

단점:
- 토큰 탈취 시 보안 위험
- 서버에서 강제 로그아웃 어려움

---

## 8. Spring Security + JWT 인증 흐름
[로그인 요청]
→ UsernamePasswordAuthenticationFilter
→ AuthenticationManager
→ 인증 성공
→ JWT 생성
→ 클라이언트에 반환

[이후 요청]
→ JWT 필터 (Custom Filter)
→ 토큰 검증
→ Authentication 생성
→ SecurityContext 저장
→ Controller

---

## 9. JWT 필터 동작 과정

1. 요청 헤더에서 JWT 추출 (Authorization)
2. 토큰 유효성 검사
3. 사용자 정보 추출
4. Authentication 객체 생성
5. SecurityContextHolder에 저장

---

## 10. 세션 vs JWT 비교

| 구분 | 세션 방식 | JWT 방식 |
|------|----------|----------|
| 저장 위치 | 서버 | 클라이언트 |
| 상태 | Stateful | Stateless |
| 확장성 | 낮음 | 높음 |
| 보안 | 상대적으로 안전 | 토큰 탈취 위험 |

---

## 11. 핵심 정리

- Spring Security는 Filter 기반 인증/인가 처리
- JWT는 토큰 기반 Stateless 인증 방식
- JWT 사용 시 매 요청마다 토큰 검증 필요

---
