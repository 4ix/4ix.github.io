---
layout: post
title: "[React] 리액트 React-Query 개념"
categories: [Frontend, React]
tags: [frontend, react, react-query]
---

## 정의
- 서버 state를 fetching, caching, synchronizing, updating할 수 있도록 도와주는 라이브러리
- 데이터를 캐싱하고 있기 때문에 매번 state값이 바뀌면서 로딩이 되지 않게 함

```bash
npm install @tanstack/react-query
```

- index.tsx
```js
import { QueryClient, QueryClientProvider } from "react-query";

const queryClient = new QueryClient();

root.render(
    <React.StrictMode>
        <QueryClientProvider client={queryClient}>
            <ThemeProvider theme={theme}>
                <App />
            </ThemeProvider>
        </QueryClientProvider>
    </React.StrictMode>
);
```
- coins.tsx
```js
import { useQuery } from "react-query";
...

const { isLoading, data } = useQuery<ICoin[]>(["allCoins"], fetchCoins); // "allCoins"는 쿼리 키 값(고유값), fetchCoin는 함수명
const { isLoading: infoLoading, data: infoData } = useQuery<InfoData>(["info", coinId], () => fetchCoinInfo(coinId)); // 함수에서 인자가 필요한 경우
const { isLoading: tickersLoading, data: tickersData } = useQuery<TickerData>(["tickers", coinId], () => fetchCoinTickers(coinId), {refetchInterval: 5000,}); // 3번째 인자로 인터벌을 넣어서 자동으로 fetch 할수 있음
```

