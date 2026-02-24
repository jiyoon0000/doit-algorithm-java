# chapter03.미리 보는 코딩 테스트 오답노트
# 📝 코딩테스트 오답 유형 정리

코딩테스트에서 틀리는 이유는 알고리즘을 몰라서라기보다  
세부 구현에서의 실수인 경우가 많다.

---

## 1. 예상치 못한 음수 결과 (Overflow)

- `int` 범위 초과로 음수 출력 가능
- 중간 계산부터 `long` 사용
- 곱셈 전 형 변환 필수
```java
long result = (long) a * b;
```

---

## 2. 시간 초과 (TLE)

**1단계: 시간복잡도 점검**
- N이 큰데 O(N²) → 로직 변경 필요

**2단계: 입출력 최적화**
- `Scanner` → `BufferedReader`
- `print` → `BufferedWriter`
- 단, 먼저 시간복잡도부터 확인

---

## 3. 인덱스에 의미 부여

- 배열 인덱스를 값의 의미로 활용
- 카운팅 정렬 → O(N + K)
- 비교 정렬보다 빠른 해결 가능

---

## 4. 나머지 연산

- `(A × B) % C = ((A % C) × (B % C)) % C`
- 곱할 때마다 나머지 연산 수행
```java
result = (result * i) % MOD;
```

---

## 5. 정렬 실수 주의

- `Collections.reverseOrder()`는 `Integer[]`만 가능
- 기본형 배열은 정렬 후 뒤집기 권장
- `Integer.MIN_VALUE`는 부호 반전 시 오버플로 가능

---

## 6. 다중 조건 정렬

- `Comparable` → 내부 기준 (1개)
- `Comparator` → 외부 기준 (여러 개)
- 실전에서는 `Comparator` 체이닝 사용

---

## 7. 이차원 ArrayList 초기화
```java
for (int i = 0; i <= N; i++) {
    graph.add(new ArrayList<>());
}
```

- 초기화하지 않으면 `NullPointerException` 발생 가능

---

## 🔎 핵심 정리 및 알게된 점

코딩테스트 오답의 대부분은 다음 중 하나다.

- 자료형 문제 (Overflow)
- 시간복잡도 문제
- 조건식 / 초기값 실수
- 정렬 기준 실수
- 자료구조 초기화 누락

문제를 많이 푸는 것만큼, 틀린 이유를 정리하는 과정이 중요하다.
