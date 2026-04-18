# Spring Annotation 정리

## 1. Annotation이란?
코드에 `@`를 붙여서  
**추가적인 기능이나 정보를 제공하는 메타데이터**

### 핵심
- 코드 동작을 직접 작성하지 않아도 됨
- Spring이 자동으로 처리

### 한줄 정리
→ 코드에 기능을 붙이는 표식

---

## 2. 사용하는 이유

- 객체 생성 및 관리 자동화
- XML 설정 제거 → 코드 간결화
- 유지보수 및 가독성 향상

### 한줄 정리
→ 반복 작업을 줄이고 자동화하기 위해 사용

---

## 3. 주요 Annotation

### 3.1 DI (의존성 주입)

- `@Autowired`  
  → 타입 기준 자동 주입

- `@Qualifier`  
  → 같은 타입 중에서 선택

- `@Resource`  
  → 이름 기준 주입

### 핵심
→ 객체를 직접 생성하지 않고 주입받는다

---

### 3.2 Bean 등록

- `@Component`  
  → 기본 Bean 등록

- `@Controller`  
  → 요청 처리

- `@Service`  
  → 비즈니스 로직

- `@Repository`  
  → DB 접근

### 핵심
→ 객체를 Spring 컨테이너에 등록

---

### 3.3 웹 관련

- `@RequestMapping`  
  → URL 매핑

- `@GetMapping`, `@PostMapping`  
  → 요청 방식 구분

- `@RequestParam`  
  → 파라미터 받기

- `@PathVariable`  
  → URL 값 받기

- `@ResponseBody`  
  → JSON 반환

### 핵심
→ 요청을 메서드와 연결

---

### 3.4 REST

- `@RestController`  
  → Controller + ResponseBody

### 핵심
→ 데이터(JSON) 반환

---

### 3.5 기타

- `@Transactional`  
  → 트랜잭션 처리

- `@ExceptionHandler`  
  → 예외 처리

### 핵심
→ 안정성과 유지보수 담당

---

## 4. 동작 원리

1. Annotation 선언  
2. Spring이 스캔  
3. Reflection으로 처리  

### 핵심
→ 실행 전에 Spring이 미리 준비

---

## 전체 정리

```text id="flow-annotation"
Annotation → Spring 스캔 → 객체 생성 → 의존성 주입 → 요청 처리
