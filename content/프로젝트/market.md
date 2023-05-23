---
emoji: 😂
title: 오픈마켓
date: '2022-09-05 00:00:00'
author: sangzun
tags: 자바스크립트,react
categories: 프로젝트
---

리액트를 이용하여 간단히 몇가지 기능이 있는 마켓을 만들었습니다.

## 구현사항

- 쇼핑 아이템 목록 페이지 구현
- 아이템의 상세페이지 구현
- 상세페이지 내에서 옵션,갯수 선택 가능
- 옵션과 아이템 선택 갯수에 따라 상품의 총액 계산 노출
- 장바구니 담기 구현
- 아이템 상세에서 장바구니에 담기를 클릭하면 상단에 구현된 장바구니 아이콘 옆에 담긴 상품 갯수 노출
- 장바구니 목록 페이지 구현
- 장바구니 목록에는 아이템명과 아이템의 옵션, 수량, 개별금액, 총 금액 노출
- 총 3개의 페이지 구현 → 목록 / 상세 / 장바구니
- 금액은 노출될때 천원단위 콤마 표시
- 상품목록 정렬기능

## 아쉬웠던점

- 리액트를 처음 학습하고 나서 혼자서 진행한 프로젝트를 youtube에 기록용으로 남겨두었습니다.
- 전역상태관리 라이브러리를 사용하지 않고 진행했는데 진행하면서 props drilling이 발생하는것을 발견했습니다.
  당시에는 전역상태관리 라이브러리의 필요성을 느끼지 못했고 페이지도 몇개 존재하지 않았지만
  프로젝트의 규모가 조금만 더 커져도 꼭 필요하겠다는 생각이 들었습니다.
- ```javascript
  // App.jsx
  const [products, setProducts] = useState([]);

  // Home.jsx
  const Home = ({ convertPrice, products, setProducts }) => {
    return <Main convertPrice={convertPrice} products={products} setProducts={setProducts} />;
  };

  // Main.jsx
  {
    products.map((product) => {
      return <Product key={`key-${product.id}`} product={product} convertPrice={convertPrice} />;
    });
  }
  ```

- 타입때문에 에러가 발생됐는데 문제점을 찾는데 시간이 꽤 걸렸습니다. 타입스크립트를 썼다면 빌드전부터 에러를 확인할 수 있을텐데 라는 아쉬움이 남았습니다.
  ![error](/openmarket_error.png)

  ```javascript
  <span className={styles.price}>
    {convertPrice(product.price + '')}
    <span className={styles.unit}>원</span>
  </span>
  ```

- `convertPrice`라는 천원단위마다 ,를 찍어주는 함수가 존재했는데 이 함수를 `util`로 따로 빼서 관리하는게 더 좋은 방법이라고 생각됩니다. props로 계속해서 넘기면서 결국엔 이 함수도 props drilling이 발생했습니다.

  ```javascript
  // App.jsx
  const convertPrice = (price) => {
    return price.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
  };
  ```

### 프로젝트를 진행하면서 남겨두었던 기록입니다.

---

[Youtube](https://www.youtube.com/channel/UCfYXOsh_ySGqR7Wy8Qw1vPg/videos)
[Github](https://github.com/sangzun-han/open-market)
