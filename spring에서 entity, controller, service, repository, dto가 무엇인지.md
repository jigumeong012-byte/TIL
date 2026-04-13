# Spring에서 사용되는 주요 구조 정리 (Entity, Controller, Service, Repository, DTO)


---

## Entity

### 개념
Entity는 데이터베이스 테이블과 매핑되는 객체이다.  
JPA를 통해 관리되며, 실제 데이터가 저장되는 구조를 표현한다.

### 특징
- 클래스 = 테이블
- 필드 = 컬럼
- `@Entity` 어노테이션 사용
- 영속성 컨텍스트에 의해 관리됨

### 정리
데이터베이스의 구조를 객체로 표현한 클래스

---

## Repository

### 개념
Repository는 데이터베이스에 접근하는 계층이다.  
JPA를 사용하면 인터페이스만으로도 CRUD 기능이 자동으로 구현된다.

### 특징
- DB 접근 담당
- `JpaRepository` 상속
- SQL 없이 데이터 처리 가능

### 정리
데이터베이스와 직접 통신하는 계층

---

## Service

### 개념
Service는 비즈니스 로직을 처리하는 계층이다.  
Controller와 Repository 사이에서 실제 기능을 수행한다.

### 특징
- 로직 처리 담당
- 트랜잭션 관리 (`@Transactional`)
- 여러 Repository를 조합 가능

### 정리
애플리케이션의 핵심 로직을 담당하는 계층

---

## Controller

### 개념
Controller는 클라이언트의 요청을 받아 처리하는 계층이다.  
HTTP 요청을 받아 Service로 전달하고 결과를 반환한다.

### 특징
- 요청/응답 처리
- URL 매핑 (`@GetMapping`, `@PostMapping`)
- `@Controller`, `@RestController` 사용

### 정리
사용자 요청을 처리하는 진입점

---

## DTO (Data Transfer Object)

### 개념
DTO는 계층 간 데이터 전달을 위한 객체이다.  
Entity를 직접 노출하지 않고 필요한 데이터만 전달하기 위해 사용된다.

### 특징
- 필요한 데이터만 포함
- 보안 및 유지보수 향상
- Entity와 분리된 구조

### 정리
데이터 전달을 위한 전용 객체

---

## 전체 흐름

1. 클라이언트 요청 → Controller
2. Controller → Service 호출
3. Service → Repository 호출
4. Repository → DB 접근
5. 결과 → DTO로 변환 → 반환

---

## 최종 정리

| 구성요소   | 역할               |
|------------|--------------------|
| Entity     | DB 테이블 매핑     |
| Repository | DB 접근            |
| Service    | 비즈니스 로직      |
| Controller | 요청 처리          |
| DTO        | 데이터 전달        |