---
layout: post
title: "[React] TypeScript 적용하기"
categories: [Frontend, React]
tags: [frontend, react, typescript]
---

## TypeScript

- 변수 혹은 컴포넌트에 타입을 지정
- 컴파일 단계를 추가적으로 거치면서 JavaScript의 실행 후 에러를 사전에 방지
- 리액트에 적용하기 위해서는 새롭게 CRA를 해주는게 좋음

```bash
npx create-react-app my-app --template typescript
cd my-app
npm i --save-dev @types/styled-components
npm i styled-components@latest
```

- index.tsx 수정

```js
const root = ReactDOM.createRoot(document.getElementById("root") as HTMLElement);
```

## 컴포넌트에 타입 지정

- interface를 사용해서 타입을 지정할 수 있음

```js
import styled from "styled-components";

interface ContainerProps {
  bgColor: string;
  borderColor: string;
}

const Container =
  styled.div <
  ContainerProps >
  `
    width: 200px;
    height: 200px;
    background-color: ${(props) => props.bgColor};
    border-radius: 100px;
    border: 1px solid ${(props) => props.borderColor};
`;

interface CircleProps {
  bgColor: string;
  borderColor?: string;
  text?: string;
}

function Circle({ bgColor, borderColor, text = "default text" }: CircleProps) {
  return (
    <Container bgColor={bgColor} borderColor={borderColor ?? bgColor}>
      {text}
    </Container>
  );
}

export default Circle;
```

## State 및 Form 사용 방법

```js
import { useState } from "react";

function App() {
  const [value, setValue] = useState("");
  const onChange = (event: React.FormEvent<HTMLInputElement>) => {
    const {
      currentTarget: { value },
    } = event;
    setValue(value);
  };
  const onSubmit = (event: React.FormEvent<HTMLFormElement>) => {
    event.preventDefault();
    console.log("hello", value);
  };
  return (
    <>
      <form onSubmit={onSubmit}>
        <input
          value={value}
          onChange={onChange}
          type="text"
          placeholder="username"
        />
        <button>Log in</button>
      </form>
    </>
  );
}

export default App;
```

## 참고 링크

- https://styled-components.com/docs/api#typescript
