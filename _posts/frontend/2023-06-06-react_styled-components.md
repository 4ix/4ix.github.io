---
layout: post
title: "[React] 리액트 Styled-Components 개념"
categories: [Frontend, React]
tags: [frontend, react, component]
---

## 정의

- 스타일 적용(CSS)을 편하게 해주는 라이브러리
- 백틱(``) 사이에 css 코드를 작성
- props 및 스타일 상속 가능

```bash
npm i styled-components@latest
```

```js
import styled from "styled-components";

const Box = styled.div`
  background-color: ${(props) => props.bgColor};
  width: 100px;
  height: 100px;
`;

const Circle = styled(Box)`
  border-radius: 50px;
`;

function App() {
  return (
    <Box bgColor="yellow" />
    <Circle bgColor="blue" />
  )
}

export default App;
```

## 속성 지정

- 중복되는 컴포넌트에 동일한 속성 지정
- 아래의 예시는 input 컴포넌트에 required 및 minLength를 동일하게 지정함

```js
const Input = styled.input.attrs({ required: true, minLength: 10 })`
  background-color: yellow;
`;
```

## 애니메이션 적용 및 다른 컴포넌트 불러오기

- animation 속성에 keyframe을 적용한 컴포넌트를 불러와서 적용

```js
const rotationAnimation = keyframes`
  0% {
    transform:rotate(0deg);
    border-radius:0px
  }
  50% {
    transform:rotate(360deg);
    border-radius:100px
  }
  100% {
    transform:rotate(0deg);
    border-radius:0px
  }
`;

const Emoji = styled.span`
  font-size: 36px;
`;

const Box = styled.div`
  height: 200px;
  width: 200px;
  background-color: khaki;
  display: flex;
  justify-content: center;
  align-items: center;
  animation: ${rotationAnimation} 1s linear infinite;
  ${Emoji} {
    &:hover {
      font-size: 100px;
    }
  }
`;
```

## Themes

- light/dark 모드 설정 가능
- index.js

```js
import { ThemeProvider } from "styled-components";

const darkTheme = {
  textColor: "whitesmoke",
  backgroundColor: "#111",
};

const lightTheme = {
  textColor: "#111",
  backgroundColor: "whitesmoke",
};

root.render(
  <React.StrictMode>
    <ThemeProvider theme={darkTheme}>
      <App />
    </ThemeProvider>
  </React.StrictMode>
);
```

- App.js

```js
const Title = styled.h1`
  color: ${(props) => props.theme.textColor};
`;

const Wrapper = styled.div`
  display: flex;
  height: 100vh;
  width: 100vw;
  justify-content: center;
  align-items: center;
  background-color: ${(props) => props.theme.backgroundColor};
`;
```
