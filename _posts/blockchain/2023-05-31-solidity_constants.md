---
layout: post
title: "[Solidity] 상수"
categories: [Blockchain, Solidity]
tags: [blockchain, solidity, tutorial]
---

## Constants

- 한번 선언 후 변환되지 않을 경우에 사용. 가스비 절약 용도.
- 값은 보통 하드 코딩됨.

## Example Code

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract Constants {
    // 일반적으로 대문자로 선언함
    address public constant MY_ADDRESS = 0x0e7B49de284A13a2D172C5D111e3e1e44CcEAe51;
    uint public constant MY_UINT = 123;
}

```
