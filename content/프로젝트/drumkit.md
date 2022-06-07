---
emoji: 😂
title: 01. JavaScript Challenge
date: '2022-06-07 00:00:00'
author: sangzun
tags: 자바스크립트
categories: 프로젝트
---

라이브러리나 프레임워크 사용 없이 모던자바스크립트만으로 하루에 하나씩 30일동안 30가지 미니 프로젝트를 만드는 챌린지입니다. 프로젝트 아이디어를 떠올리기 어려워 주제와 디자인이 정해진 미니 프로젝트를 따라 만들어보는것으로 시작했습니다.

### 01. drum-kit

- `keydown`이벤트를 이용해서 입력값을 받아서 정해진 오디오를 재상한다.
- 오디오를 재생할 때 해당 키에 .playing 이라는 클래스를 추가해주고 오디오 재생이 끝나면 .playing클래스를 제거한다.
- `transitionend`는 transition의 완료를 감지할 수 있는 이벤트이다.

```
const play = (event) => {
  const audio = document.querySelector(`audio[data-key="${event.keyCode}"]`);
  const key = document.querySelector(`.key[data-key="${event.keyCode}"]`);

  if (!audio) return;
  audio.currentTime = 0;
  audio.play();
  key.classList.add("playing");
};

const removeTransition = (event) => {
  if (event.propertyName === "transform")
    event.target.classList.remove("playing");
};

const pianoKeys = document.querySelectorAll(".key");
pianoKeys.forEach((el) =>
  el.addEventListener("transitionend", removeTransition)
);

window.addEventListener("keydown", play);

```
