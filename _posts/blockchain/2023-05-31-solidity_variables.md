---
layout: post
title: "[Solidity] 변수 종류들"
categories: [Blockchain, Solidity]
tags: [blockchain, solidity, tutorial]
---

## Variables

- 솔리디티 변수 종류들

1. local: 함수 안에서 선언, 블록체인 안에 저장 안됨
2. state: 함수 밖에서 선언, 블록체인에 저장됨
3. global: 블록체인 관련 정보 제공

## Example Code

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract Variables {
    // State 변수들(함수 밖에서 선언함)은 블록체인에 저장됨.
    string public text = "Hello";
    uint public num = 123;

    function doSomething() public {
        // Local 변수들(함수 안에서 선언함) 블록체인에 저장 안됨.
        uint i = 456;

        // 블록체인 관련 정보 제공
        uint timestamp = block.timestamp; // 현재 블록 타임스탬프
        address sender = msg.sender; // 컨트랙트 호출자 주소
    }
}
```
