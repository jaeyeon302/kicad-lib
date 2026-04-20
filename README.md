# kicad-lib
kicad library for custom symbol, footprint and 3d model.

## KiCad 환경설정 안내


이 라이브러리를 사용하려면 KiCad의 라이브러리 경로 관리(Preferences → Configure Paths)에서 아래 경로 변수를 추가해야 합니다:


```
${KICAD_USER_GIT_LIB}$
```

※ `${KICAD_USER_GIT_LIB}$`는 본 kicad-lib git 디렉토리를 의미합니다.

이 경로가 KiCad의 라이브러리 경로 변수에 명시되어 있어야 라이브러리 파일을 정상적으로 참조할 수 있고, 특히 3D file loading이 가능합니다.

