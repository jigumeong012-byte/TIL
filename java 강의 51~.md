# java 강의 정리 51~

## 1. 클래스 & 객체 (Class & Object)
- 클래스(Class): 데이터(변수)와 기능(메서드)을 함께 정의한 설계도  
- 객체(Object): 클래스를 기반으로 생성된 실제 인스턴스  
- 객체 생성 방법:
    ClassName obj = new ClassName();
- 객체는 각각 독립적인 메모리를 가지며 서로 다른 값 저장 가능  
- `.`(dot)을 사용해 변수 및 메서드 접근  

---

## 2. 배열과 객체의 관계
- 배열은 같은 타입의 데이터를 연속적으로 저장  
- 객체 배열을 통해 여러 객체를 관리할 수 있음  

    Student[] students = new Student[3];
    students[0] = new Student();

- 반복문과 함께 자주 사용됨  

---

## 3. 메서드 (Method)
- 특정 작업을 수행하는 코드 블록  
- 코드 재사용성과 가독성 향상  

    int add(int a, int b) {
        return a + b;
    }

### 메서드 특징
- 입력값(Parameter)  
- 반환값(Return)  
- 메서드 이름은 동사 형태로 짓는 것이 좋음  

---

## 4. 메서드 호출과 스택 구조
- 메서드는 호출되면 스택(Stack)에 쌓임  
- 실행이 끝나면 스택에서 제거됨  
- 호출 순서에 따라 실행 흐름이 관리됨  

---

## 5. 참조형과 기본형
### 기본형 (Primitive Type)
- int, double, boolean 등  
- 값 자체를 저장  

### 참조형 (Reference Type)
- 객체, 배열 등  
- 주소(참조값)를 저장  

차이 핵심  
- 기본형 → 값 복사  
- 참조형 → 주소 공유  

---

## 6. 객체 전달
- 메서드에 객체를 넘기면 참조값이 전달됨  
- 메서드 내부에서 객체 값을 변경하면 외부에도 영향 있음  

    void change(Student s) {
        s.name = "변경됨";
    }

---

## 7. 생성자 (Constructor)
- 객체 생성 시 초기값을 설정하는 특별한 메서드  
- 클래스 이름과 동일  
- 반환 타입 없음  

    class Student {
        String name;

        Student(String name) {
            this.name = name;
        }
    }

### 특징
- `new`로 객체 생성 시 자동 호출  
- 여러 개 정의 가능 (오버로딩)  

---

## 8. this 키워드
- 현재 객체 자신을 가리킴  

    this.name = name;

- 멤버 변수와 매개변수 이름이 같을 때 사용  

---

## 9. 접근 제어자 (Access Modifier)
| 접근 제어자 | 설명 |
|------------|------|
| public     | 어디서든 접근 가능 |
| default    | 같은 패키지에서만 |
| private    | 해당 클래스 내부만 |

- 캡슐화를 위해 private 사용  

---

## 10. 캡슐화 (Encapsulation)
- 데이터 보호 및 외부 접근 제한  

    private int age;

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

- getter / setter 사용  

---

## 11. 패키지 (Package)
- 클래스들을 그룹으로 묶는 개념  
- 폴더 구조와 유사  

    package com.example;

- 이름 충돌 방지 및 구조 정리  

---

## 12. import
- 다른 패키지의 클래스를 사용하기 위해 필요  

    import java.util.Scanner;

---

## 13. static (정적)
- 클래스 레벨에서 공유되는 값  

    static int count;

### 특징
- 객체 생성 없이 사용 가능  
- 공통 데이터 관리에 사용  

---

## 14. final
- 값을 변경할 수 없음  

    final int MAX = 10;

- 상수 정의에 사용  

---

## 15. null과 NullPointerException
- null: 참조 대상이 없음  

    Student s = null;

- null 상태에서 접근하면 에러 발생  

    s.name; // 오류

- null 체크 필요  

---

## 16. 기본형 vs 참조형 정리
| 구분 | 기본형 | 참조형 |
|------|--------|--------|
| 저장값 | 실제 값 | 주소 |
| 예시 | int, double | 객체, 배열 |
| 전달 | 값 복사 | 참조값 전달 |

---

## 17. 자바 메모리 구조
- 스택(Stack): 메서드 실행 정보  
- 힙(Heap): 객체 저장  
- 메서드 영역(Method Area): 클래스 정보  

---

## 18. 전체 흐름 핵심 요약
- 클래스 → 객체 생성 → 데이터 저장  
- 메서드 → 기능 분리 및 재사용  
- 생성자 → 객체 초기화  
- 참조형 → 주소 공유  
- 캡슐화 → 데이터 보호  
- static → 공통 데이터 관리  
