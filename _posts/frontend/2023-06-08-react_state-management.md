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
