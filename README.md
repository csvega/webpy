# Web Python Playground

브라우저에서 바로 Python 코드를 작성하고 실행할 수 있는 온라인 Python 실행 환경입니다.
서버 없이 [Pyodide](https://pyodide.org/)를 사용하여 클라이언트 측에서 Python이 실행됩니다.

## 주요 기능

- **브라우저 내 Python 실행** — 설치 없이 바로 코드 작성 및 실행
- **input() 지원** — `input()` 함수를 통한 사용자 입력 처리 (여러 줄 붙여넣기 지원)
- **코드 에디터** — CodeMirror 기반의 구문 강조, 자동 괄호 닫기, 줄 번호 표시
- **다크/라이트 모드** — 테마 전환 버튼으로 모드 변경 (설정 자동 저장)
- **글씨 크기 조절** — 에디터와 출력창의 글씨 크기를 자유롭게 조절
- **예제 코드** — Hello World, 반복문, 리스트, 함수, 계산기, 숫자 맞추기 게임 등
- **패널 크기 조절** — 에디터와 출력창 사이의 구분선을 드래그하여 크기 조절
- **오프라인 지원** — Service Worker를 통한 리소스 캐싱
- **보안** — 위험한 Python 모듈 및 함수 실행 차단

## 실행 방법

별도의 빌드 과정이 필요 없는 정적 웹 페이지입니다.

### 로컬 실행

아무 웹 서버로 프로젝트 폴더를 서빙하면 됩니다.

```bash
# Python 내장 서버 사용
cd webpy
python3 -m http.server 8000
```

브라우저에서 `http://localhost:8000` 접속

### GitHub Pages 배포

1. GitHub에 저장소를 생성하고 코드를 push합니다.
2. 저장소 Settings > Pages에서 Source를 `main` 브랜치로 설정합니다.
3. `https://사용자이름.github.io/저장소이름/` 에서 접속할 수 있습니다.

## 단축키

| 단축키 | 동작 |
|---|---|
| `Ctrl + Enter` | 코드 실행 |
| `Tab` | 들여쓰기 (4칸) |
| `Shift + Tab` | 내어쓰기 |
| `Ctrl + /` | 주석 토글 |

## 기술 스택

- **Pyodide v0.27.5** — WebAssembly 기반 Python 인터프리터
- **CodeMirror 5** — 코드 에디터
- **Service Worker** — 오프라인 캐싱

## 파일 구조

```
webpy/
├── index.html   # 메인 페이지 (HTML + CSS + JS 단일 파일)
├── sw.js        # Service Worker (오프라인 캐싱)
└── README.md
```

## 라이선스

MIT License
