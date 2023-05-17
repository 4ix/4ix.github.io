---
layout: post
title: "[React] 리액트 Effects 개념"
categories: [Frontend, React]
tags: [frontend, react, effects]
---

## useEffect

- 컴포넌트가 최초 한번 렌더링 되고 이후로는 되지 않게 함
- state가 변화하더라도 최초 한번만 실행됨
- 아래의 예시는 keyword가 변화하면 실행

```js
const [keyword, setKeyword] = useState("");

useEffect(() => {
  if (keyword !== "" && keyword.length > 5) {
    console.log(keyword);
  }
}, [keyword]);
return () => console.log("hide");
```
