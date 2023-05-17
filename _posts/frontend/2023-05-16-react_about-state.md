---
layout: post
title: "[React] 리액트 State 개념"
categories: [Frontend, React]
tags: [frontend, react, state]
---

## 정의

- 데이터가 저장되는 곳
- useState를 사용하여 modifier 함수에 원하는 결과를 지정하면 state값이 변할 때 마다 렌더링 자동 진행

## Example Code

```js
const [counter, setCounter] = React.useState(0);
const onClick = () => {
  setCounter((current) => current + 1);
};
```
