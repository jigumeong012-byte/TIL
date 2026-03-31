## Java 강의
### 17. 클래스와 객체
#### 클래스(Class)

객체를 생성하기 위한 설계도

구성: 필드(데이터) + 메서드(기능)

ex)
```
class Person {
    String name;
    int age;

    void introduce() {
        System.out.println("이름: " + name);
    }
}
```
#### 객체(Object)

클래스를 기반으로 생성된 실제 인스턴스
```
Person p = new Person();
p.name = "Tom";
p.introduce();
```
#### 참조 타입 (Reference Type)

객체의 주소값을 저장하는 타입
```
Person p1 = new Person();
Person p2 = p1; // 같은 객체를 참조
```
#### String 클래스

문자열을 다루는 클래스
```
String str = "Hello";

System.out.println(str.length());        // 길이
System.out.println(str.substring(0, 2)); // He
System.out.println(str.equals("Hello")); // true
```
#### 필드(Field)

객체의 상태(데이터)를 저장
```
class Car {
    String color;
    int speed;
}
```
#### 메서드(Method)

객체의 동작(기능)을 정의
```
void run() {
    System.out.println("달린다");
}
```
static과 scope
```
class Test {
    static int count = 0;

    void increase() {
        count++;
    }
}
```
static: 객체 생성 없이 사용 가능 (공용 변수 느낌)
scope: 변수의 사용 범위
#### enum (열거형)
```
enum Day {
    MON, TUE, WED
}
```
상수 집합을 정의할 때 사용
### 18. 클래스 다듬기
생성자(Constructor)
```
class Person {
    String name;

    Person(String name) {
        this.name = name;
    }
}
```
객체 생성 시 자동 호출
this

현재 객체 자신을 가리킴

#### 메서드 오버로딩 (Overloading)
```
int add(int a, int b) {
    return a + b;
}

double add(double a, double b) {
    return a + b;
}
```
같은 이름, 다른 매개변수
#### 패키지 (Package)
```
package com.example;
```
클래스를 그룹으로 관리 (폴더 개념)
### 19. 상속 (Inheritance)
상속
```
class Animal {
    void sound() {
        System.out.println("소리");
    }
}

class Dog extends Animal {
}
```
기존 클래스 재사용
#### 오버라이딩 (Overriding)
```
class Dog extends Animal {
    void sound() {
        System.out.println("멍멍");
    }
}
```
부모 메서드를 자식에서 재정의
super
```
class Dog extends Animal {
    Dog() {
        super();
    }
}
```
#### 부모 클래스 호출
접근제한자
public : 어디서든 접근 가능
protected : 상속 관계에서 접근 가능
default : 같은 패키지 내
private : 같은 클래스 내
추상 클래스 (Abstract Class)
abstract class Animal {
    abstract void sound();
}
객체 생성 불가
반드시 구현해야 하는 메서드 포함 가능
형변환 (Casting)
Animal a = new Dog(); // 업캐스팅
Dog d = (Dog) a;      // 다운캐스팅
### 20. 인터페이스 (Interface)
인터페이스 정의
```
interface Animal {
    void sound();
}
```
구현 (implements)
```
class Dog implements Animal {
    public void sound() {
        System.out.println("멍멍");
    }
}
```
default method
```
interface Test {
    default void hello() {
        System.out.println("기본 메서드");
    }
}
```
인터페이스에 기본 구현 가능
익명 클래스
```
Animal a = new Animal() {
    public void sound() {
        System.out.println("익명");
    }
};
```
이름 없이 즉석에서 구현
### 21. 예외 처리 (Exception Handling)
try-catch
```
try {
    int a = 10 / 0;
} catch(Exception e) {
    System.out.println("에러 발생");
}
```
throws
```
void test() throws Exception {
}
```
#### 예외를 호출한 쪽으로 전달
사용자 정의 예외
```
class MyException extends Exception {
}

throw new MyException();
```
직접 예외 클래스 정의 가능
