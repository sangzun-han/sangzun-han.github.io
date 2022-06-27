---
emoji: 😂
title: 07. Array Cardio Day 2
date: '2022-06-27 00:00:00'
author: sangzun
tags: 자바스크립트
categories: 챌린지
---

### 07. Array Cardio Day 2

자바스크립트의 메소드 익히기

- `some` : 배열 안의 어떤 요소라도 주어진 함수를 통과하는가
- `every` : 배열 안의 모든 요소가 주어진 함수를 통과하는가
- `find` : 함수를 만족하는 첫번째 요소의 값 반환
- `findIndex` : 함수를 만족하는 배열의 첫번째 요소의 인덱스 반환

### 19세 이상인 사람이 1명이상 있는지?

```
people.some((person) => {
  const curYear = new Date().getFullYear();
  return curYear - person.year >= 19;
})
```

### 모든 사람이 19세 이상인지?

```
people.every((person) => {
  const curYear = new Date().getFullYear();
  return curYear - person.year >= 19;
})
```

### ID가 823423인 사람 찾기

```
comments.find((comment) => comment.id === 823423);
```

### ID가 823423인 사람을 찾고 지우기

```
const index = comments.findIndex((comment) => comment.id === 823423);
const newComments = [
  ...comments.splice(0,index),
  ...comments.splice(index+1),
];
```
