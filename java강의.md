# 강의 정리

## 1. Scanner
- 입력을 받는

```java
Scanner scanner = new Scanner(System.in);
int num = scanner.nextInt();
String str = scanner.nextLine();
```

---

## 2. 배열
- 데이터를 모은것

```java
int[] arr = {90, 80, 70};

for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

---

## 3. 2차원 배열
- 행과 열로 구성된 배열

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

---

## 4. 향상된 for문
- 배열을 하나씩 꺼내서 반복

```java
for (int n : arr) {
    System.out.println(n);
}
```

---

## 5. 메서드
- 기능을 묶은 코드

```java
public static int add(int a, int b) {
    return a + b;
}
```

- 값은 복사되어 전달됨
- 오버로딩: 같은 이름, 다른 매개변수

---
