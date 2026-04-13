## java spring boot 게시판에서 쓰인 기술

---

### Spring Boot
전체 프로젝트의 뼈대  

    -서버 실행을 쉽게 함  
    -복잡한 설정을 자동으로 처리함  
    -실행하면 바로 서버가 켜짐  
### Spring MVC
사용자의 요청을 처리하는 구조  

    -URL 요청을 Controller가 받음  
    -@GetMapping, @PostMapping 사용  
흐름  
    
    Client 요청 -> Controller가 받음 -> 처리 시작  
웹의 입구 역할  
### Spring Data JPA  
데이터 베이스를 쉽게 다루는 기술  
    
    -DB 테이블 <-> 자바 객체 연결  
    -SQL 없어도 데이터 저장 가능  
예)
```
memberRepository.save(member);
```
이 한 줄이 INSERT SQL의 역할을 대신함  
### Lombok
반복 코드 제거 도구  
    
    -getter/setter 자동 생성  
    -생성자 자동 생성  
예)
```
@Getter
@RequiredArgsConstructor
```
코드 길이를 확 줄여줌  
### Controller
입구 담당  
    
    -사용자의 요청을 받음  
    -어떤 기능 실행할지 결정  
예)
```
@GetMapping("/members")
```
### Service
두뇌 담당  
    
    -실제 로직 처리  
    -계산, 조건, 흐름 제어  
Controller가 시키면 일하는 곳  
### Repository
DB 담당  
    
    -데이터 저장 조회  
    -JPA 사용  
DB랑 직접 대화하는 유일한 계층
### 전체 흐름
Client -> Controller -> Service -> Repository -> DB -> Client
### Entity
    -DB 테이블과 연결된 클레스  
    -@Entity 사용  
테이블 = 클래스라고 보면 됨  
### DTO
    -데이터 전달용 객체
    -Entity가 대신 사용  
이유:  
    
    -보안   
    -구조 정리  
### 설정 파일

    -application.yml 또는 .properties  
역할:  

    -DB 연결  
    -포트 설정  
    -환경 설정  