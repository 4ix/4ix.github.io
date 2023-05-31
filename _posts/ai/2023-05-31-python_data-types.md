---
layout: post
title: "[Python] 데이터 타입"
categories: [AI, Python]
tags: [ai, python, tutorial]
---

## 기본 데이터 타입

1. int: 정수형
2. float: 실수형
3. str: 문자열

## 데이터 타입 변환

- 데이터 타입 변환 방법

```py
score = 79 # 79로 선언했기에 기본 int임
print(type(score), score)

score = float(score) # float로 변환
print(type(score), score)

score = int(score) # int로 변환
print(type(score), score)

score = str(score) # str으로 변환
print(type(score), score)
```
