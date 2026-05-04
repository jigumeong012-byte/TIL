# Spring Security 정리

## 1. 개요
**Spring Security**는 Spring 기반 애플리케이션에서  
**인증(Authentication)** 과 **인가(Authorization)** 를 담당하는 보안 프레임워크이다.

- 모든 요청을 **Filter 기반**으로 처리
- 보안 로직을 직접 구현하지 않아도 됨

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
- `principal` : 사용자 정보
- `credentials` : 비밀번호
- `authorities` : 권한 목록
- `authenticated` : 인증 여부

---

## 5. SecurityContext

### 구조
SecurityContextHolder
→ SecurityContext
→ Authentication

### 특징
- 인증 정보 저장소
- 전역에서 접근 가능
- 로그인 유지 (세션 사용)

---

## 6. SecurityContextPersistenceFilter
- SecurityContext 생성, 저장, 조회 담당
- 요청마다 인증 정보 유지

---

## 7. 인증 흐름
UsernamePasswordAuthenticationFilter
→ AuthenticationManager
→ AuthenticationProvider
→ UserDetailsService
→ DB 조회
→ 인증 성공
→ SecurityContext 저장

---

## 8. AuthenticationManager & Provider

### AuthenticationManager
- 인증 전체 관리
- 적절한 Provider 선택

### AuthenticationProvider
- 실제 인증 처리
- supports()로 처리 가능 여부 판단

---

## 9. 인가 (Authorization)

### 개념
사용자가 특정 자원에 접근 가능한지 판단

---

## 10. FilterSecurityInterceptor
- 마지막 필터
- 접근 허용/거부 결정

### 예외
- 인증 없음 → `AuthenticationException`
- 권한 없음 → `AccessDeniedException`

---

## 11. AccessDecisionManager & Voter

### AccessDecisionManager
- 최종 접근 허용 여부 결정

### AccessDecisionVoter
- 권한 판단 수행

### 결정 방식
- **AffirmativeBased** : 하나라도 허용하면 승인
- **ConsensusBased** : 다수결
- **UnanimousBased** : 만장일치

---

## 12. 전체 요약

- Spring Security는 **Filter 기반 보안 프레임워크**
- 인증 → 인가 순서로 처리
- 인증 정보는 `SecurityContextHolder`에 저장
- FilterChainProxy가 핵심 역할 수행