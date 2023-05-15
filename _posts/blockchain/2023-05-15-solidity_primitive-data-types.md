---
layout: post
title: "[Solidity] 기본 데이터 타입"
categories: [Blockchain, Solidity]
tags: [Blockchain, Solidity, Tutorial]
---

## Primitive Data Types
+ 솔리디티 기본 데이터 타입
1. boolean
2. uint256
3. int256
4. address

### boolean
+ true, false
  
```
bool public boo = true;
```

### uint256
+ 부호 없는 정수
+ uint8: 0 ~ 255
+ uint16: 0 ~ 65535
+ uint32: 0 ~ 4294967295
+ uint64: 0 ~ 18446744073709551615
+ uint128: 0 ~ 340282366920938463463374607431768211455
+ uint256: 0 ~ 115792089237316195423570985008687907853269984665640564039457584007913129639935
  
```
uint8 public u8 = 1;
uint public u256 = 456;
uint public u = 123; // 단순히 unit로 선언시 uint256과 동일함
```

### int256
+ 부호 있는 정수
+ int8: -128 ~ 127
+ int16: -32768 ~ 32767
+ int32: -2147483648 ~ 2147483647
+ int64: -9223372036854775808 ~ 9223372036854775807
+ int128: -170141183460469231731687303715884105728 ~ 170141183460469231731687303715884105727
+ int256: -57896044618658097711785492504343953926634992332820282019728792003956564819968 ~ 57896044618658097711785492504343953926634992332820282019728792003956564819967

```
int8 public i8 = -1;
int public i256 = 456;
int public i = -123; // 단순히 int 선언시 int256과 동일함

// int의 최소값과 최대값
int public minInt = type(int).min;
int public maxInt = type(int).max;
```

### address
+ 지갑 주소

```
address public addr = 0x0e7B49de284A13a2D172C5D111e3e1e44CcEAe51;
```