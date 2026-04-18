# Spring Annotation 정리

## Spring Annotation이란?
Spring에서 제공하는 어노테이션은  
코드에 `@` 형태로 추가되어 **객체 생성, 의존성 주입, 요청 처리 등 다양한 기능을 자동으로 수행하도록 하는 메타데이터**이다.

---

# 주요 어노테이션 개념

## 1. DI 관련 어노테이션 (의존성 주입)

### 개념
객체를 직접 생성하지 않고,  
Spring이 대신 객체를 생성하여 주입하는 방식

### 종류
- `@Autowired`  
  타입(Type) 기준으로 자동 주입

- `@Qualifier`  
  같은 타입의 Bean이 여러 개일 경우 특정 Bean 선택

- `@Resource`  
  이름(Name) 기준으로 주입

### 예시
```java
@Autowired
private MemberService memberService;
