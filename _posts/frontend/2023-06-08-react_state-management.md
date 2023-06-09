---
layout: post
title: "[React] State-management"
categories: [Frontend, React]
tags: [frontend, react, state-management, recoil]
---

## 정의

- Recoil은 state를 atom에 넣어서 관리하는 library
- prop 관리가 편함

```bash
npm install recoil
```

1. index.js

```js
import { RecoilRoot } from "recoil";

root.render(
  <React.StrictMode>
    <RecoilRoot>
      <QueryClientProvider client={queryClient}>
        <App />
      </QueryClientProvider>
    </RecoilRoot>
  </React.StrictMode>
);
```

2. atoms.ts (사용하고자 하는 state 정의)

```ts
import { atom } from "recoil";

export const isDarkAtom = atom({
  key: "isDark",
  default: false,
});
```

### useRecoilValue

```js
import { useRecoilValue } from "recoil";
import { isDarkAtom } from "../atoms";

const isDark = useRecoilValue(isDarkAtom);
```

### useRecoilState

```js
const setDarkAtom = useSetRecoilState(isDarkAtom);
const toggleDarkAtom = () => setDarkAtom((prev) => !prev);
```

### useRecoilState

```js
const [isDark, setDarkAtom] = useRecoilState(isDarkAtom);
```

### selector

- 기존 state를 통해 새로운 state를 사용할 수 있음
- atom의 output을 변환
- get: state를 가져와서 수정된 값을 리턴
- set: state를 직접 수정

```js
import { atom, selector } from "recoil";

export const minuteState = atom({
  key: "minutes",
  default: 0,
});

export const hourSelector = selector({
  key: "hours",
  get: ({ get }) => {
    const minutes = get(minuteState);
    return minutes / 60;
  },
  set: ({ set }, newValue) => {
    const minutes = Number(newValue) * 60;
    set(minuteState, minutes);
  },
});
```
