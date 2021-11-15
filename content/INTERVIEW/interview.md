---
emoji: 
title: interview 
date: '2021-11-15 20:00:00'
author: sangzun
tags: interview
categories: intervirew
---

9. What is the difference between == and === operators

JavaScript provides both strict(===, !==) and type-converting(==, !=) equality comparison. 

The strict operators take type of variable in consideration, while non-strict operators make type correction/conversion based upon values of variables. The strict operators follow the below conditions for different types,


- Two strings are strictly equal when they have the same sequence of characters, same length, and same characters in corresponding positions.


- Two numbers are strictly equal when they are numerically equal. i.e, Having the same number value. There are two special cases in this,

  a.NaN is not equal to anything, including NaN.

  b.Positive and negative zeros are equal to one another.

- Two Boolean operands are strictly equal if both are true or both are false.

- Two objects are strictly equal if they refer to the same Object.

- Null and Undefined types are not equal with ===, but equal with ==. i.e, null===undefined --> false but null==undefined --> true

--해석--

JS는 strict와 equlity comparion을 제공한다.

strict 연산자는 변수의 타입을 고려하고 non-strict 연산자는 변수의 값을 고려한다. strict 연산자는 타입이 다르면 아래의 조건에 따른다.

- 두 문자열은 문자의 순서,길이,위치가 같아야한다.

- 두 숫자는 수학적으로 같아야 한다. 즉 숫자값이 같아야한다. 두가지 특별한 경우

  a. NaN은 NaN을 포함하여 어떤것도 같지 않다.

  b. +0과 -0은 같다.

- boolean은 둘다 true 또는 둘다 false일때 같다.

- null과 undefined타입은 ===로 비교할때 같지 않다 ==로 비교할때는 같다.

<a href="https://github.com/sudheerj/javascript-interview-questions">질문 목록