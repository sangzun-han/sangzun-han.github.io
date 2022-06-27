---
emoji: 😂
title: 05. Flex-Panel Gallery
date: '2022-06-11 00:00:00'
author: sangzun
tags: 자바스크립트
categories: 챌린지
---

### 05. Flex-Panel Gallery

- flex 속성을 이용해서 레이아웃 변경
- 화면 클릭시 해당 부분이 커지거나 작아지는 처리

가장먼저 세로로 배치돼있는 요소들을 가로로 배치한다.

```
.panels {
  display:flex;
}
```

이후 panel 내부의 값들을 정렬시킨다.

```
.panel {
  display:flex;
  flex-direciton:column;
  flex: 1;
  justify-content:center;
}

.panel > * {
  display:flex;
  flex: 1 0 auto;
  align-items:center;
  justify-content:center;
}
```

그 다음은 위 아래의 글자들을 translateY를 이용해서 화면 바깥으로 숨긴다. 이후에 특정 panel을 클릭하면 글자가 보이도록 한다.

```
.panel > *:first-child {
  transform: translateY(-100%);
}

.panel.open-active > *:first-child {
  transform: translateY(0);
}

.panel > *:last-child {
  transform: translateY(100%);
}

.panel.open-active > *:last-child {
  transform: translateY(0);
}

.panel.open {
  font-size: 40px;
  flex : 4;
}
```

```
const panels = document.querySelectorAll(".panel");

function toggleOpen() {
  this.classList.toggle("open");
}
function toggleActive(e) {
  if (e.propertyName.includes("flex")) {
    this.classList.toggle("open-active");
  }
}

panels.forEach((panel) => panel.addEventListener("click", toggleOpen));
panels.forEach((panel) =>
  panel.addEventListener("transitionend", toggleActive)
);
```
