---
layout: post
title: "[Solidity] 상태 변수"
categories: [Blockchain, Solidity]
tags: [blockchain, solidity, tutorial]
---

## State Variable

- 상태 변수의 값을 읽거나 업데이트 하기 위해서는 트랜잭션 실행 필요.
- 단순히 값을 읽는 것에 가스비 소모 없음.

## Example Code

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract SimpleStorage {
    // 숫자를 저장하기 위한 상태변수 선언
    uint public num;

    // 상태 변수 값을 기록하기 위해 트랜잭션 실행 필요
    function set(uint _num) public {
        num = _num;
    }

    // 트랜잭션 실행 없이 상태 변수 값을 읽을 수 있음
    function get() public view returns (uint) {
        return num;
    }
}

```
