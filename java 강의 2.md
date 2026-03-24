# Java 강의 정리

## 12. Scanner

Scanner는 사용자로부터 입력을 받을 때 사용하는 클래스이다.

```java
Scanner scanner = new Scanner(System.in);

int num = scanner.nextInt();
String str = scanner.nextLine();
```

### 설명

- `System.in` : 키보드 입력
- `nextInt()` : 정수 입력
- `nextLine()` : 한 줄 문자열 입력

---

## 13. 배열 (Array)

배열은 여러 개의 데이터를 하나로 묶어서 저장하는 구조이다.

```java
int[] arr = {90, 80, 70};

for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

### 설명

- `arr.length` : 배열의 길이
- 인덱스는 0부터 시작한다

---

## 14. 2차원 배열

2차원 배열은 행과 열로 이루어진 배열이다.

```java
int[][] arr = {
    {1, 2, 3},
    {4, 5, 6}
};

for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < 3; j++) {
        System.out.print(arr[i][j]);
    }
}
```

### 설명

- `arr[i][j]` : i행 j열의 값
- 중첩 반복문을 사용하여 접근한다

---

## 15. 향상된 for문 (Enhanced for)

배열의 값을 하나씩 꺼내서 반복할 때 사용하는 문법이다.

```java
for (int n : arr) {
    System.out.println(n);
}
```

### 설명

- 배열의 모든 요소를 자동으로 순회한다
- 인덱스를 사용하지 않아도 된다

---

## 16. 메서드 (Method)

메서드는 특정 기능을 수행하는 코드 묶음이다.

```java
public static int add(int a, int b) {
    return a + b;
}
```

### 설명

- `return` : 결과값을 반환한다
- 매개변수(Parameter)를 통해 값을 전달받는다

### 특징

- 값은 복사되어 전달된다 (Call by Value)
- 코드 재사용이 가능하다

### 오버로딩 (Overloading)

같은 이름의 메서드를 여러 개 만들 수 있다.  
단, 매개변수의 개수나 타입이 달라야 한다.
