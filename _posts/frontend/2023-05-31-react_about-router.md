---
layout: post
title: "[React] 리액트 Route 개념"
categories: [Frontend, React]
tags: [frontend, react, route]
---

## 정의

- 접속하고자 원하는 url 마다 path를 걸어주는 기능

```bash
npm install react-router-dom
```

```js
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import Home from "./routes/Home";
import Detail from "./routes/Detail";

function App() {
  return (
    <Router>
      <Routes>
        <Route path="/movie:id" element={<Detail />}></Route>
        <Route path="/" element={<Home />}></Route>
      </Routes>
    </Router>
  );
}

export default App;
```

### Parameter

- 라우트에서 id를 넘기고 나서 넘어간 페이지에서 해당 id를 확인할 수 있는 기능

```js
const { id } = useParams();
```

## createBrowserRouter

1. Router.tsx

```js
import { createBrowserRouter } from "react-router-dom";
import Home from "./screens/Home";
import About from "./screens/About";
import Root from "./Root";

const router = createBrowserRouter([
  {
    path: "/",
    element: <Root />,
    children: [
      {
        path: "",
        element: <Home />,
      },
      {
        path: "about/:id",
        element: <About />,
      },
    ],
  },
]);

export default router;
```

2. Root.tsx

```js
import { Outlet } from "react-router-dom";
import Header from "./components/Header";

function Root() {
  return (
    <div>
      <Header />
      <Outlet />
    </div>
  );
}

export default Root;
```

### errorElement

- 에러가 발생했을 경우 렌더링

```js
        errorElement: <NotFound />,
```

### useNavigate

- 링크 전달

```js
import { useNavigate } from "react-router-dom";

const navigate = useNavigate();

const onHomeClick = () => {
  navigate("/");
};
```

### Outlet

- children으로 렌더링 하고자 할 경우 사용
- context를 사용하여 값을 넘겨줄 수 있음

```js
import { Outlet } from "react-router-dom";

<Outlet context={{ darkMode: true }} />;
```

```js
import { useOutletContext } from "react-router-dom";

interface DarkModeContext {
    darkMode: boolean;
}

  const { darkMode } = useOutletContext<DarkModeContext>();

```

### useSearchParams

- 주소창의 params를 읽어오거나 값을 수정할 수 있음

```js
import { useSearchParams } from "react-router-dom";

const [readSearchParams, setSearchParams] = useSearchParams();
console.log(readSearchParams);
```
