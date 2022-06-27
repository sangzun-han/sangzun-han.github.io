---
emoji: 😂
title: 06. Type Ahead
date: '2022-06-12 00:00:00'
author: sangzun
tags: 자바스크립트
categories: 챌린지
---

### 06. Type Ahead

- fetch API를 이용해서 데이터를 배열에 저장
- 배열에 저장된 데이터를 기반으로 검색창에 입력된 값을 정규식을 이용하여 filter

```
const cities = [];

fetch(endpoint)
  .then((res) => {
    return res.json();
  })
  .then((data) => {
    cities.push(...data);
  });
```

```
const input = document.querySelector(".search");
const suggestion = document.querySelector(".suggestions");

const findMatch = (cities, wordToMatch) => {
  const regex = new RegExp(wordToMatch, "gi");
  return cities.filter(
      (place) => place.city.match(regex) || place.state.match(regex)
    );
  };

  const getCity = () => {
    suggestion.innerHTML = findMatch(cities, input.value)
    .map((place) => {
      const regex = new RegExp(input.value, "gi");
      const city = place.city.replace(
        regex,
        `<span class="hl">${input.value}</span>`
      );
      const state = place.state.replace(
        regex,
        `<span class="hl">${input.value}</span>`
      );
      return `
            <li>
              <span class="name">${city} ${state}</span>
              <span class="population">${place.population}</span>
            </li>
            `;
    }).join("");
  };

input.addEventListener("change", getCity);
input.addEventListener("keyup", getCity);
```
