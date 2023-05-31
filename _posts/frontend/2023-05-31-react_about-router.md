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
        <Route path="/movie" element={<Detail />}></Route>
        <Route path="/" element={<Home />}></Route>
      </Routes>
    </Router>
  );
}

export default App;
```
