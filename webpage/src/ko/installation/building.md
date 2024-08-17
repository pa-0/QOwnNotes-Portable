# QOwnNotes 빌드

## GitHub에서 빌드

소스 코드에서 직접 QOwnNotes를 빌드할 수도 있습니다.

Git 저장소에서 직접 코드를 체크아웃합니다:

```bash
git clone https://github.com/pbek/QOwnNotes.git -b release
cd QOwnNotes
git submodule update --init
```

디버깅을 위해서는 QtCreator를 사용하는 것이 가장 쉽습니다. When downloading [Qt Creator](https://www.qt.io/download-qt-installer-oss), you will also need the package `qtwebsockets` to build QOwnNotes with Qt6. Windows에서 빌드할 경우 *MinGw 64-비트*를 고수해야 합니다. 리눅스의 경우 저장소에 QtCreator용 패키지가 있을 가능성이 높습니다.

그런 다음 프로젝트 파일 `src/QOwnNotes.pro`를 열고 **빌드** / **빌드 프로젝트 QOwnNotes**를 클릭합니다.

사용법을 잘 알고 있다면 터미널에서 직접 QOwnNotes를 만들 수도 있습니다:

```bash
cd src

# build binary translation files if you want another language than English
lrelease QOwnNotes.pro

# prepare build process and build the application
qmake
make
```

이 프로젝트에 소스 코드를 제공하거나, 제안을 하거나, [QOwnNotes 문제 페이지](https://github.com/pbek/QOwnNotes/issues)에서 문제를 보고할 수 있습니다.

[GitHub의 QOnNotes](https://github.com/pbek/QOwnNotes)를 방문합니다.

::: 팁 만약 당신이 프로젝트에 소스 코드를 제공하고 싶다면, 당신의 풀 요청을 `메인` 브랜치에 하세요. :::

## 원본 보관소

[QOwnNotes 소스 보관함](https://github.com/pbek/QOwnNotes/releases) 에서 QOwnNotes 소스 보관함을 찾을 수 있습니다.

소스 아카이브는 다음과 같이 액세스할 수 있습니다:

`https://github.com/pbek/QOwnNotes/releases/download/v23.7.0/qownnotes-23.7.0.tar.xz`
