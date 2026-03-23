# 강의 정리

## 1. Scanner

### 개념
- 사용자로부터 입력을 받기 위한 클래스
- 사용하려면 반드시 선언 필요

```java
Scanner scanner = new Scanner(System.in);
```

### 정수 입력
```java
int num = scanner.nextInt();
```

### 문자열 입력
```java
String str = scanner.nextLine();
```

### 문자열 반복 입력 + 종료
```java
Scanner scanner = new Scanner(System.in);

while (true) {
    System.out.print("문자열 입력(exit: 종료): ");
    String str = scanner.nextLine();

    if (str.equals("exit")) {
        System.out.println("프로그램 종료");
        break;
    }

    System.out.println("입력값: " + str);
}
```

---

## 2. 배열

### 개념
- 같은 타입의 데이터를 하나로 묶은 자료구조

### 선언 및 생성
```java
int[] students;
students = new int[5];
```

### 값 대입
```java
students[0] = 90;
students[1] = 80;
```

### 출력
```java
for (int i = 0; i < students.length; i++) {
    System.out.println(students[i]);
}
```

### 선언과 초기화 동시에
```java
int[] students = {90, 80, 70, 60, 50};
```

---

## 3. 2차원 배열

### 개념
- 행(row)과 열(column)로 구성된 배열

### 선언
```java
int[][] arr = new int[2][3];
```

### 값 대입
```java
arr[0][0] = 1;
arr[1][2] = 6;
```

### 출력
```java
for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < 3; j++) {
        System.out.print(arr[i][j] + " ");
    }
    System.out.println();
}
```

### 초기화
```java
int[][] arr = {
    {1, 2, 3},
    {4, 5, 6}
};
```

---

## 4. 향상된 for문

### 개념
- 배열을 하나씩 자동으로 꺼내서 반복

```java
int[] numbers = {1, 2, 3, 4, 5};

for (int num : numbers) {
    System.out.println(num);
}
```

### 특징
- 인덱스 사용 불가
- 단순 출력 및 탐색에 적합

---

## 5. 메서드

### 개념
- 특정 기능을 수행하는 코드 묶음

### 기본 구조
```java
public static 반환타입 메서드이름(매개변수) {
    // 실행 코드
}
```

---

### 반환값 없는 메서드
```java
public static void print() {
    System.out.println("출력");
}
```

---

### 반환값 있는 메서드
```java
public static boolean odd(int num) {
    return num % 2 == 1;
}
```

---

### 값 전달 특징
- 메서드는 값을 복사해서 전달
- 원본 변수는 변경되지 않음

```java
public static void change(int num) {
    num = num * 2;
}
```

---

### 메서드 오버로딩

#### 개념
- 같은 이름, 다른 매개변수로 여러 메서드 정의 가능

```java
public static int add(int a, int b) {
    return a + b;
}

public static int add(int a, int b, int c) {
    return a + b + c;
}
```

### 조건
- 매개변수의 개수, 타입, 순서 중 하나 이상 달라야 함
- 반환 타입은 오버로딩 조건에 포함되지 않음

---
