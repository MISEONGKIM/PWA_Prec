# PWA

- Progressive Web Application
- 웹과 네이티브 앱의 장점을 결합한 웹 기술
- 네이티브 앱과 유사한 사용자 경험을 제공하는 웹 애플리케이션이다.
- 일반 웹 사이트와 같이 웹에서 실행되지만 앱처럼 사용이 가능함.

## PWA 대표기능

- PUSH 알림
- 오프라인 환경
- 홈 화면에 추가

## PWA의 요건

- 3가지의 요건을 필수적으로 만족해야 함.

1. HTTPS
   - PWA는 보안이 연결된, 즉 신뢰할 수 있는 사이트에서만 동작하기 때문에 웹 페이지는 HTTPS 도메인에서 제공되어야 한다.
2. Service Worker(서비스 워커)
   - 백그라운드에서 실행되는 Javascript 파일 형태의 스크립트이다. 오프라인 환경에서도 웹이 작동할 수 있도록 네트워크 요청을 가로채서 네트워크 불량 상태 등 접속성이 안 좋은 상황을 커버한다.
   - 서비스 워커는 네트워크 요청을 중간에 가로챌 수 있다는 점에서 중간자 공격에 취약하기 때문에 보안이 강화된 HTTPS에서만 작동한다. 이는 PWA를 만들기 위해서 HTTPS 연결을 해야 하는 또 다른 이유가 된다!
3. Manifest(매니페스트)
   - PWA에 대해 브라우저에 알려주고 사용자의 데스크탑이나 모바일 디바이스에 설치할 때 어떻게 작동해야 하는지 알려주는 JSON파일이다.
   - manifest파일에는 웹 페이지의 url과 웹의 이름, 화면 표시 방식 등 기능과 표시 방법에 대한 정보들이 포함된다.

## 좋은 PWA를 만들기 위한 Checklist

https://web.dev/i18n/ko/pwa-checklist/

### 핵심 체크리스트(Core checklist)

디바이스의 크기와 입력 유형에 상관없이 모든 사용자가 앱을 설치하고 사용할 수 있는 지에 대한 체크리스트

- 앱은 빠르게 로드되고, 빠르게 유지되어야한다.
- PWA는 모든 브라우저에서 작동해야 한다.
- 모든 화면 크기에 대응해야 한다. 화면 크기에 상관없이 콘텐츠가 표시되어야 하며 모든 기능을 사용할 수 있어야 한다.
- 오프라인 환경에서는 브라우저의 기본 오프라인 페이지가 아닌 맞춤형 오프라인 페이지를 제공한다.
- 설치가 가능해야 한다.

### 최적의 체크리스트(Optimal checklist)

PWA가 실행 중인 장치의 일부인 것처럼 느끼게 하는 체크리스트

- 연결이 절대적으로 필요하지 않은 경우에도 앱은 오프라인에서도 온라인과 동일하게 작동합니다.

- 모든 사용자 상호작용이 WCAG 2.0 접근성 요구사항을 충족합니다.

  - WCAG 2.0 : 웹 콘텐츠 접근성(Web Content Accessibility Guidelines) 버전 2.0 가이드라인
    1.  인식 가능성(Perceivable): 사용자는 제공되는 콘텐츠를 인지할 수 있어야 합니다.
        - 대체 텍스트 제공(이미지요소 대체 텍스트)
        - 멀티미디어 대체 수단(오디오,비디오 등 콘텐츠 대체수단)
        - 색에 의존하지 않음
    2.  운용 가능성(Operable): 사용자는 콘텐츠와 상호 작용할 수 있어야 합니다.
        - 키보드 접근성(모든 기능 키보드만으로 이용 가능)
        - 충분한 시간 제공(제한 시간 내에 콘텐츠 읽고 사용하도록 충분한 시간 제공)
        - 발작 예방(발작 일으키는 콘텐츠 피함)
    3.  이해 가능성(Understandable): 사용자는 콘텐츠의 이해와 사용에 어려움을 겪지 않아야 합니다.
        - 가독성(텍스트 읽고 이해하기 쉽게)
        - 예측 가능성(콘텐츠의 동작을 예측할 수 있어야함)
        - 도움말과 지원
    4.  견고성(Robust): 콘텐츠는 다양한 기술과 플랫폼에서 견고하게 동작해야 합니다.
        - 웹 표준 준수

- PWA가 검색을 통해 쉽게 발견될 수 있도록 해야 합니다.

- 마우스, 키보드, 스타일러스, 터치 등 모든 입력 방식으로 PWA를 동일하게 사용할 수 있어야 합니다.

- 강력한 API 사용에 대한 허가를 요청할 때는 문맥을 제공하고 API가 필요한 시점에만 요청해야 합니다.

- 건전한 코드베이스를 보장, 알려진 취약점이 있는 라이브러리 사용 방지, 사용되지 않는 API를 사용하지 않는지 확인, 코드베이스에서 웹 안티 패턴 제거 등

## 우리가 만든 웹이 PWA의 요건을 충족하는 지 확인하는 방법

1. Lighthouse

   - Chrome DevTools에서 제공하는 Lighthouse를 사용
   - 웹 페이지의 품질을 개선하기 위한 자동 오픈소스 도구로 성능, 접근성, PWA, SEO 등에 대한 검사를 진행할 수 있다.

   * 검사 진행하면 Progressive Web App 나오는 데 클릭하면 어떤게 충족하지 않았는 지 상세하게 설명되어 있음.

2. PWA Builder
   - https://www.pwabuilder.com/
   - PWA의 3가지 요건을 만족하는지에 대한 점수를 매기고 Manifest와 Service Worker를 쉽게 작성할 수 있도록 도와줌.

## HTTPS 연결

1. Github Pages
   - 해당 프로젝트repository > settings > pages에서 None => main(branch)으로 변경 후 Save 클릭하면 URL 생성됨
2. ngrok
   - NAT와 방화벽 뒤에 있는 로컬 서버를 보안 터널을 통해 공용 인터넷에 노출시켜주는 도구.
   - 외부에서 로컬에 접속할 수 있도록 해주는 터널 프로그램.
   - 보통 로컬 환경에서 SSL을 사용할 때나 localhost를 외부에서 호출할 때 사용함.

## Manifest에 들어가야할 내용

- Manifest가 100점이 나오지 않으면(pwa builder에서) 최종적으로 PWA를 퍼블리싱 할 수 없다. 특히 아이콘 이미지가 제대로 업로드 되었는 지 확인한 후 진행해야 함.

### Manifest에 들어가야 할 내용

**web.dev에서 소개하는 매니페스트에 포함 되어야 할 내용 리스트**

- short_name 또는 name
  - name : 앱의 이름
  - short_name : 홈 스크린의 아이콘 이름과 같이 앱의 이름을 표시할 충분한 공간이 없을 경우 사용자에게 표시되는 이름.
- icons : 192px과 512px 아이콘
  - 홈화면에 추가하면 생길때 사용할 아이콘을 설정하는 옵션
  - 설정한 아이콘 이미지들은 앱 실행, 작업 전환, 스플래시 화면 등의 장소에서 사용하게 됨. 아이콘 사이는 48px 단위로 제공해야 함.
- start_url
  - 웹 애플리케이션 시작할 때 로드되어야 할 기본 url
  * 일반적으로 앱의 root url을 말함. https://miseongkim.github.io/PWA_Prec/와 같은 것
- display : fullscreen, standalone, minial-ui 중 하나이어야 함.
  - 개발자가 선호하는 디스플레이 모드 설정
  * 앱이 사용자에게 어떻게 표시될 지 결정하는 것으로 앱을 표시하는 방식
  * browser : 일반 브라우저와 동일하게 보임
  * standalone : 다른 앱들처럼 최상단에 상태표시줄을 제외한 전체화면으로 보임
  * fullscreen 상태표시줄도 제외한 전체화면(ex. 게임)
  * minimul-ui : fullscreen 과 비슷하지만 뒤로가기, 새로고침등 최소한의 영역만 제공(모바일 크롬 전용)
- prefer_related_aplications : 존재하지 않거나 false이어야 함.

**그 외**

- description
  - 앱이 어떤 작업을 수행하는지에 대한 설명
- background color와 theme color
  - background color는 웹이 처음 시작될때 splashScreen 에서 사용하기 위해 사용 됨, theme color는 상단부의 테마 부분의 색상을 지정.

* splashScreen

  - 스플래시 화면을 설정하게 되면 초기 렌더링시 흰화면 대신 스플래시 이미지가 보이면서 사용하는 사용자에게 좀더 친화적인 환경을 제공
  - 스플래시 이미지는 따로 설정하지 않고 name, background_color, icons 설정이 되어있으면 이를 조합하여 보여주게 됨.

* scope
  - 애플리케이션 context의 탐색 범위를 정의, 매니페스트가 적용되는 동안 볼 수 있는 웹 페이지를 제한한다.
  - 만약 사용자가 제한된 범위인 외부를 탐색하면 브라우저 탭 또는 창 내부의 일반 웹 페이지로 되돌아간다.
* orientation
  - 웹 페이지의 기본 방향을 정의
* language
  - 앱의 기본 언어
* shortcuts

  - 사용자가 PWA를 설치한 후 홈 화면에 추가할 수 있는 단축 아이콘을 정의할 수 있다. 이를 통해 사용자는 PWA에 더 쉽게 액세스할 수 있게 됨.
  - shortcuts 속성은 배열 형태로 여러 개의 단축 아이콘을 정의할 수 있음.

  * 사용자가 이러한 단축 아이콘을 홈 화면에 추가하면 해당 PWA의 특정 기능에 빠르게 액세스할 수 있음

  ```
  "shortcuts": [
  {
     "name": "카메라",
     "description": "사진 찍기",
     "url": "/camera",
     "icons": [
        {
        "src": "/icons/camera-icon.png",
        "sizes": "192x192"
        }
     ]
  },
  {
     "name": "갤러리",
     "description": "사진 보기",
     "url": "/gallery",
     "icons": [
        {
        "src": "/icons/gallery-icon.png",
        "sizes": "192x192"
        }
     ]
  }
  ]
  ```

### Manifest 등록

```
  <link rel="manifest" href="manifest.json" />
```

## Service Worker 설정하기

- Service Worker Options로 이동하면 오프라인 환경에 대한 설정을 할 수 있음.
- PWA Builder에서는 미리 만들어진 서비스 워커 패키지들을 제공함.

### Servie Worker 등록

```
  <script type="module">
        import 'https://cdn.jsdelivr.net/npm/@pwabuilder/pwaupdate';
        const el = document.createElement('pwa-update');
        document.body.appendChild(el);
     </script>
```
