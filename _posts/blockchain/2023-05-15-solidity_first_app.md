---
layout: post
title: "[Solidity] First App"
categories: [Blockchain, Solidity]
tags: [Blockchain, Solidity, Tutorial]
---

## First App
+ count라는 변수와, 그 수를 증감시키는 함수가 있는 컨트랙트

## Example Code
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract Counter {
    // count를 변수로 지정
    uint public count;

    // 현재 count 값 리턴 함수
    function get() public view returns (uint) {
        return count;
    }

    // count 1 증가 시키는 함수
    function inc() public {
        count += 1;
    }

    // count 1 감소 시키는 함수, 단 0일때는 실패함
    function dec() public {
        count -= 1;
    }
}

```