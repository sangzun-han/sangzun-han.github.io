---
emoji: 😂
title: 03. CSS Variables
date: '2022-06-09 00:00:00'
author: sangzun
tags: 자바스크립트
categories: 챌린지
---

### 03. CSS Variables

- `dataset.@@@`은 data-@@@로 이루어진 데이터를 가져온다.
- `document.documentElement`는 최상위 요소인 html을 가리킨다.

핵심적인 내용은 css값들이 변수로 지정됐다는것이다. `--base, --spacing, --blur`

addEventListener를 이용해서 spacing, blur, base에 변화가 일어난다면 setProperty를 이용해서 값을 수정해주면 된다.

range-bar로 이루어진 두 input 태그는 data-sizing="px"이고 색을 결정하는 input 태그는 data-sizing이 존재하지 않기 때문에 or연산자를 이용해서 변수에 담아준다.

```
const inputs = document.querySelectorAll(".controls input");

const handleUpdate = (event) => {
  const suffix = event.target.dataset.sizing || "";
  document.documentElement.style.setProperty(
    `--${event.target.name}`,
    event.target.value + suffix
  );
};

inputs.forEach((input) => input.addEventListener("change", handleUpdate));
inputs.forEach((input) => input.addEventListener("mousemove", handleUpdate));

```

- 변수 suffix는 range-bar를 건드린다면 px 색을 건드린다면 ""값을 대입한다.
- 최상위 요소인 html에 event.target.name -> spacing,blur,base 중 1개의 값 event.target.value -> 0~200까지의 값 또는 색
  - ex) spacing 30px의 값을 대입한다.
