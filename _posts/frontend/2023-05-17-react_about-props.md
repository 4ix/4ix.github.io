---
layout: post
title: "[React] 리액트 Props 개념"
categories: [Frontend, React]
tags: [frontend, react, props]
---

## 정의

- 부모 컴포넌트로 부터 자식 컴포넌트에 데이터를 보낼 수 있게 하는 방법
- 아래 코드에서는 text와 inverted를 보냄

```js
function Btn({ text, inverted }) {
  return (
    <button
      style={{
        backgroundColor: inverted ? "black" : "gray",
        color: "white",
        padding: "10px 20px",
        border: 0,
        borderRadius: 10,
        fontWeight: inverted ? 700 : 0,
      }}
    >
      {text}
    </button>
  );
}

function App() {
  return (
    <div>
      <Btn text="Yes" inverted={true} />
      <Btn text="No" inverted={false} />
    </div>
  );
}
```

## Memo

- props 값이 바뀌어도 re-render 방지

```js
const MemorizedBtn = React.memo(Btn);
```

## PropTypes

- props로 넘기는 값을 잘못 넘겼을 때 에러를 보여줄 수 있음(실수 방지)

```js
Btn.propTypes = {
  text: PropTypes.string.isRequired,
  fontSize: PropTypes.number,
};
```
