---
layout: post
title: "Hello World"
categories: [Blockchain, Solidity]
tags: [Blockchain, Solidity, Tutorial]
---

## Hello World
+ pragma는 솔리디티 컴파일러 버전을 지정하는 개념

## Example Code
```
// SPDX-License-Identifier: MIT
// compiler version must be greater than or equal to 0.8.17 and less than 0.9.0
pragma solidity ^0.8.17;

contract HelloWorld {
    string public greet = "Hello World!";
}
```