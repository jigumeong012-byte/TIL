# Spring Bean / IoC / DI 관계 정리

## 1. 전체 구조

Spring은 Bean을 생성하고, IoC로 관리하며, DI로 연결한다
Spring Container  
├── Bean 생성 (객체 생성)  
├── IoC (객체 관리)  
└── DI (객체 간 의존성 연결)  

---

## 2. Spring Bean

### 정의
- Spring Container가 생성하고 관리하는 객체

### 특징
- 객체의 생성, 초기화, 소멸까지 관리됨
- 기본적으로 싱글톤(Singleton)
- 애플리케이션의 핵심 구성 요소

```java
@Service
public class MemberService {}
```

---

## 3. IoC (Inversion of Control)

### 개념
- 객체 생성과 관리의 제어권이 개발자에서 스프링으로 넘어감

### 기존 방식

```
MemberService service = new MemberService();
```
### IoC 적용

```
@Autowired
MemberService memberService;
```

### 핵심
- 객체를 직접 생성하지 않음
- 스프링 컨테이너가 Bean을 생성하고 관리

---

## 4. DI (Dependency Injection)

### 개념

- 객체 간 의존관계를 외부(스프링)에서 주입
   
### 기존 방식 (강한 결합)

```
class A {
    B b = new B();
}
```
### DI 적용 (느슨한 결합)

```
class A {
   private B b;

   public A(B b) {
   this.b = b;
   }
}
```
### 핵심
- 필요한 객체를 직접 생성하지 않음
- 스프링이 Bean을 주입

---

## 5. IoC + DI + Bean 관계

### 역할 정리

|개념|역할|
|---|---|
|Bean|스프링이 관리하는 객체|
|IoC|객체 생성 및 관리 권한|
|DI|객체 간 의존성 연결 방식|

---

## 6. 동작 흐름
1. 스프링 컨테이너 생성
2. Bean 생성 
3. IoC 적용 (객체 관리 시작)
4. DI 적용 (의존 관계 주입)
5. 애플리케이션 실행

---

7. 구조로 이해하기

```
[Spring Container] 
    ↓ (IoC: 관리)
  Bean A
    ↓ (DI: 주입)
  Bean B
```

---

## 8. 핵심 요약

- Bean: 스프링이 만든 객체
- IoC: 객체 관리 권한이 스프링에 있음
- DI: 객체 간 관계를 스프링이 연결

---

## 정리

- Spring은 IoC로 Bean을 관리하고, DI로 Bean을 연결한다