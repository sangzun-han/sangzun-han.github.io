---
emoji: 
title: interview 
date: '2021-11-17 00:00:00'
author: sangzun
tags: interview
categories: intervirew
---

### 9. What is the difference between == and === operators

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



### 17. What is the purpose of the let keyword

The let statement declares a block scope local variable. Hence the variables defined with let keyword are limited in scope to the block, statement, or expression on which it is used. Whereas variables declared with the var keyword used to define a variable globally, or locally to an entire function regardless of block scope

--해석--

let은 block scope 변수를 선언하는데 사용되는 키워드이다. 그러므로 block, statement, expression의 범위를 제한한다. 반면 var는 block scope에 상관없이 전역변수 또는 함수 전체의 지역변수로 정의된다. 


### 18. What is the difference between let and var

|var|let|
|---|---|
|It is been available from the beginning of JavaScript|Introduced as part of ES6|
|It has function scope|It has block scope|
|Variables will be hoisted|Hoisted but not initalized|

--해석--


|var|let|
|---|---|
|자바스크립트 초기부터 사용할 수 있었다.|ES6에서 도입되었다.|
|function scope|block scope|
|변수가 호이스팅 된다.|호이스팅 되지만 초기화는 되지 않는다.|

### 25. What is Hoistring

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of thier scope before code execution. Remember that JavaScript only hoists declarations, not initialisation.

--해석--

코드를 실행하기 전에 변수나 함수를 가장 위로 올리는것을 호이스팅이라고 한다. 자바스크립느는 선언문을 호이스팅하며 초기화는 하지 않는다.


<a href="https://github.com/sudheerj/javascript-interview-questions">질문 목록