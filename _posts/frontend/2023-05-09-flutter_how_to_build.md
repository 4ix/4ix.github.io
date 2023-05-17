---
layout: post
title: "[Flutter] 플러터 안드로이드 APK 파일로 빌드하기"
categories: [Frontend, Flutter]
tags: [frontend, flutter, apk]
---

## 플러터 안드로이드 APK 파일로 빌드하기

1. 커맨드 창에 빌드하고자 하는 플러터 프로젝트 디렉토리로 이동

```bash
cd C:\Users\Jasper\Documents\dev\smartfarm
```

2. 명령어 입력

```bash
flutter build apk --release --target-platform=android-arm64
```

3. 빌드 된 APK 파일은 아래의 경로에서 찾을 수 있음

- build\app\outputs\apk\release
