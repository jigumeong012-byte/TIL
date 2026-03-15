# Java 기초 정리

## 1. 개발 환경 설정

Java 프로그램을 개발하려면 **JDK와 개발 도구**가 필요하다.

- **JDK (Java Development Kit)** : Java 프로그램을 컴파일하고 실행하는 도구
- **IDE** : 코드 작성과 실행을 쉽게 도와주는 개발 프로그램  
  (예: IntelliJ, Eclipse)

### Java 실행 과정

1. `.java` 파일 작성  
2. `javac` 명령어로 컴파일 → `.class` 파일 생성  
3. `java` 명령어로 프로그램 실행  

---

# 2. Hello World

Java 프로그램의 기본 구조

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}```
설명

class : Java 프로그램의 기본 단위

main() : 프로그램이 실행될 때 시작되는 메서드

System.out.println() : 콘솔에 문자열을 출력하는 명령어

3. 주석 (Comment)

주석은 코드 설명이나 기록을 위해 사용한다.
주석은 프로그램 실행에는 영향을 주지 않는다.

// 한 줄 주석

/*
여러 줄
주석
*/
4. 변수 (Variable)

변수는 데이터를 저장하는 메모리 공간이다.

기본 구조
자료형 변수이름 = 값;
예시
int age = 20;
String name = "Tom";

int number = 10;
double score = 95.5;
5. 변수 타입 (Data Type)

Java에서 사용하는 기본 자료형

자료형	설명
int	정수
double	실수
boolean	true / false
char	문자
String	문자열
예시
int age = 20;
double height = 175.5;
boolean isStudent = true;
String name = "Kim";
6. 변수 명명 규칙

변수 이름을 지을 때 다음 규칙을 따라야 한다.

숫자로 시작할 수 없다

공백을 사용할 수 없다

Java 예약어(int, class 등)를 사용할 수 없다

관례

Java에서는 camelCase 방식을 사용한다.

예시
studentAge
userName
totalScore
7. 연산자 (Operator)

연산자는 값을 계산하거나 비교할 때 사용한다.

산술 연산자
연산자	의미
+	더하기
-	빼기
*	곱하기
/	나누기
int a = 10 + 5;
문자열 연결

Java에서는 + 연산자로 문자열을 연결할 수 있다.

String name = "Tom";
System.out.println("Hello " + name);
증감 연산자

변수를 1 증가 또는 감소시킨다.

연산자	설명
++a	먼저 증가 후 사용
a++	사용 후 증가
--a	먼저 감소 후 사용
a--	사용 후 감소
int a = 10;

a++;
a--;
++a;
--a;
비교 연산자

값을 비교할 때 사용한다.

연산자	의미
>	크다
>=	크거나 같다
<	작다
<=	작거나 같다
==	같다
!=	다르다
int age = 20;

if (age > 18) {
    System.out.println("성인");
}
논리 연산자

조건을 결합할 때 사용한다.

연산자	의미
&&	AND
||	OR
!	NOT
if (age > 18 && age < 30) {
    System.out.println("20대");
}
8. 조건문 (Condition)

조건에 따라 다른 코드를 실행한다.

if 문
int age = 20;

if (age >= 20) {
    System.out.println("성인");
} else {
    System.out.println("미성년자");
}
else if

여러 조건을 처리할 때 사용한다.

int score = 85;

if (score >= 90) {
    System.out.println("A");
} else if (score >= 80) {
    System.out.println("B");
} else {
    System.out.println("C");
}
switch 문

여러 값을 비교할 때 사용한다.

int num = 2;

switch(num) {
    case 1:
        System.out.println("One");
        break;
    case 2:
        System.out.println("Two");
        break;
    default:
        System.out.println("Other");
}
Java 14 이후 switch
int num = 2;

switch(num) {
    case 1 -> System.out.println("One");
    case 2 -> System.out.println("Two");
    default -> System.out.println("Other");
}
삼항 연산자

간단한 조건식을 한 줄로 작성할 수 있다.

int age = 20;

String result = (age >= 20) ? "성인" : "미성년자";
9. 반복문 (Loop)

반복문은 같은 코드를 여러 번 실행할 때 사용한다.

Java의 대표적인 반복문

while

do-while

for

while 문

조건이 true인 동안 반복한다.

int i = 0;

while (i < 5) {
    System.out.println(i);
    i++;
}
do-while 문

조건과 상관없이 최소 1번 실행된다.

int i = 0;

do {
    System.out.println(i);
    i++;
} while (i < 5);
차이점

while → 조건 먼저 검사

do-while → 실행 후 조건 검사

break / continue

반복문 제어에 사용한다.

break

반복문을 즉시 종료한다.

for(int i = 0; i < 10; i++) {
    if(i == 5) {
        break;
    }
    System.out.println(i);
}
continue

현재 반복을 건너뛰고 다음 반복을 진행한다.

for(int i = 0; i < 10; i++) {
    if(i == 5) {
        continue;
    }
    System.out.println(i);
}
for 문

반복 횟수가 정해져 있을 때 많이 사용한다.

for(int i = 0; i < 5; i++) {
    System.out.println(i);
}

구조

초기값 → 조건 → 증감
중첩 반복문

반복문 안에 반복문을 넣을 수 있다.

for(int i = 0; i < 3; i++) {
    for(int j = 0; j < 3; j++) {
        System.out.println(i + " " + j);
    }
}
10. 스코프 (Scope)

스코프는 변수가 사용 가능한 범위를 의미한다.

public class Test {

    public static void main(String[] args) {

        int a = 10;

        if(true) {
            int b = 20;
            System.out.println(a);
            System.out.println(b);
        }

        // System.out.println(b); 오류 발생
    }
}
설명

a → 전체 블록에서 사용 가능

b → if 블록 내부에서만 사용 가능

지역 변수 (Local Variable)

메서드 또는 블록 안에서 선언된 변수

void test() {
    int num = 10;
}
특징

해당 블록 안에서만 사용 가능

11. 형변환 (Type Casting)

데이터 타입을 다른 타입으로 변환하는 것

자동 형변환

작은 타입 → 큰 타입으로 변환될 때 자동으로 발생한다.

int a = 10;
double b = a;
명시적 형변환

큰 타입 → 작은 타입으로 변환할 때 직접 지정해야 한다.

double a = 10.5;
int b = (int) a;

결과
→ 소수점이 잘린다.

계산과 형변환

Java에서는 연산 시 자동 형변환이 발생한다.

int a = 10;
double b = 3;

double result = a / b;

결과
→ 정수와 실수 연산이므로 실수 결과가 나온다.

정리

Java 기초에서 배우는 주요 개념

변수

자료형

연산자

조건문

반복문

스코프

형변환
