---
emoji: 😂
title: 04. Array Cardio Day 1
date: '2022-06-10 00:00:00'
author: sangzun
tags: 자바스크립트
categories: 챌린지
---

### 04. Array Cardio Day 1

js에서 배열과 배열제어에 대한 내용

모든 과정이 `filter map sort reduce`메서드만 사용할 수 있다면 무리없이 해결할 수 있는 문제들이다.

- filter() 메서드는 주어진 함수의 조건을 만족하는 모든 요소를 모아 새로운 배열을 반환한다.
- map() 메서드는 배열내에 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환한다.
- sort() 메서드는 배열의 요소를 정렬한다. 원래 배열이 정렬되는것이므로 주의해야 한다.

  - 매개변수로 comapreFunction이 제공된다면 배열 요소는 compare 함수의 반환값에 따라 정렬된다.
    comparFunction(a,b)일때 a-b로 크기를 비교하며 a-b가 양수일때 즉 a가 b보다 클때는 양수로 리턴 같으면 a-b가 음수일때는 음수로 리턴한다.

    리턴값이 음수이면 값을 앞으로 보내고 0이면 그대로 리턴값이 양수라면 뒤로보낸다. 그래서 최종적으로 오름차순 정렬이 된다.

- reduce() 메서드는 배열의 각 요소에 대해 주어진 reducer 함수를 실행하고 하나의 결과값을 반환한다.

  - reducer 함수는 4개의 인자를 가진다. (acc,cur,idx,src)
  - 두번째 인자로 초기값을 줄 수 있다.

### 1. 1500년대에 태어난 발명가

```
inventors.filter(
  (inventor) => inventor.year >= 1500 && inventor.year < 1600)
```

### 2. 발명가의 이름과 성

```
inventors.map((inventor) => {
    return inventor.first + " " + inventor.last;
  }
)

```

### 3. 발명가들 태어난 순서대로 정렬 오름차순으로

```
const ordered = inventors.sort(function (a, b) {
  return a.year - b.year;
});
```

### 4. 발명가들 나이의 합

```
inventors.reduce((acc,inventor) => {
  return acc + inventor.passed - inventor.year;
},0)
```

### 5. 발명가들 나이순으로 정렬

```
inventors.sort(function (a, b) {
  return a.passed - a.year > b.passed - b.year ? -1 : 1;
})
```

### 7. 사람 성을 기준으로 정렬

```
people.sort(function (last, next) {
    const [aLast, aFirst] = last.split(", ");
    const [bLast, bFirst] = next.split(", ");
    return aLast > bLast ? 1 : -1;
})
```

### 8. 배열의 해당요소가 몇개가 들어있는가

```
data.reduce(function (obj, item) {
  if (!obj[item]) obj[item] = 0;
  obj[item]++;
  return obj;
}, {})
```
