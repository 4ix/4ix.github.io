---
layout: post
title: "[Flutter] 플러터 안드로이드 APK 파일로 빌드 시 버전 변경 방법"
categories: [Frontend, Flutter]
tags: [frontend, flutter, apk]
---

## 3가지의 파일 수정

1. pubspec.yaml

```
version: 1.0.3+4
```

2. android\app\build.gradle

```
def flutterVersionCode = localProperties.getProperty('flutter.versionCode')
if (flutterVersionCode == null) {
    flutterVersionCode = '4'
}
def flutterVersionName = localProperties.getProperty('flutter.versionName')
if (flutterVersionName == null) {
    flutterVersionName = '1.0.3'
}
```

3. android\local.properties

```
flutter.versionName=1.0.3
flutter.versionCode=4
```

## 버전 바꾸는 규칙

### 일반적인 규칙

1. 버전 번호는 Major, Minor, Patch의 형태로 배포. 각각 자연수 있고 절대 앞에 0이 붙으면 안됨.
2. 각 번호의 수는 항상 증가해야 함.
3. 특정 버전으로 패키지를 배포하고 나면, 그 버전의 내용은 절대 변경하면 안됨. 변경분이 있다면 새로운 버전으로 배포.
4. Major 버전이 변경될 때 Minor, Patch는 0으로 초기화.
5. Minor 버전이 변경될 때 Patch는 0으로 초기화.

### Major 버전 증가

1. 하위 버전과 호환되지 않는 변화가 생겼을 시
2. 대대적인 변화가 일어났을 시
3. 클라이언트가 1.0.0 버전의 API 접근 방식으로 2.0.0 버전에 접속할 수 없을 시

### Minor 버전 증가

1. 하위 버전과 호환이 되면서, 새로운 기능이 추가 될 때
2. 새로운 기능이 추가된 API가 나왔지만, 기존의 공개된 API가 하위 호환되고 있을 때
3. 기존의 기능이 변경되거나 사용 방법이 변경 되었을 때

### Patch 버전 증가

1. 버그 수정
2. 기존 클라이언트가 알아차리지 못할 정도의 작은 변화가 있을 때
3. 서버 코드 내부적으로 소스가 수정되었을 때
