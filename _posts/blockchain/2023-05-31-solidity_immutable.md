---
layout: post
title: "[Solidity] 불변객체"
categories: [Blockchain, Solidity]
tags: [blockchain, solidity, tutorial]
---

## Immutable

- 상수와 비슷함. 구조체(constructor) 안에 선언되나 한번 선언되면 추후 수정할 수 없음.

## Example Code

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract Immutable {
    address public immutable MY_ADDRESS;
    uint public immutable MY_UINT;

    constructor(uint _myUint) {
        MY_ADDRESS = msg.sender;
        MY_UINT = _myUint;
    }
}
```
