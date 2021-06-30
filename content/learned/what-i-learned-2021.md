---
title: "2021"
date: "2021-01-01"
description: "About what I learned at 2021"
og_description: "About what I learned at 2021"
draft: false
---

## **2021-06-30**

- Referrer-Policy
  - 최근 회사에서 레퍼러를 수집하는데 사내 도메인에서만 남지 않는 현상을 발견했는데, 보니까 이 정책을 바꾼 것이 원인이었다.
  - http 헤더의 하나로, 해당 페이지가 어디서 열렸는지 알 수 있는 레퍼러(referrer) 정책을 설정한다.
    - `no-referrer`: 레퍼러 정보를 전혀 넘기지 않는다.
    - `origin`: 뒤에 경로는 빼고 도메인만 넘긴다.
    - `no-referrer-when-downgrade`: 넘기는 프로토콜 보안레벨이 같거나 더 높을 때 넘긴다.
      - ex) http -> http, http -> https
    - `same-origin`: 도메인과 프로토콜 보안레벨이 같을 때만 넘긴다.
    - `strict-origin`: 이동하는 페이지가 https일 때만 넘긴다.
    - `strict-origin-when-cross-origin`: 디폴트. 동일 도메인 혹은 교차 허용된 도메인에서 동일한 프로토콜 보안레벨로 이동시킬 때 넘긴다.
    - `unsafe-url`: 조건 없이 전체 주소를 넘긴다.

<br />
<hr />

## **2021-06-23**

- 덕 타이핑 (duck typing)은 덕 테스트 (duck test)에서 유래한 것으로, 아래 명제에서 시작한다.
  > 만약 어떤 새가 오리처럼 걷고, 헤엄치고, 꽥꽥거리는 소리를 낸다면 나는 그 새를 오리라고 부를 것이다.
  - 객체의 변수와 메서드의 집합이 그 객체의 타입을 결정하는 것을 의미한다.
  - 타입을 미리 지정하지 않고 런타임에 해당 메서드들을 확인해 타입을 정하는 동적 타이핑의 한 종류다.
  - **ts 또한 결국 덕 타이핑 기반의 js의 런타임 동작을 모델링해 타입을 체크한다.**
  - 따라서 아래에서 Vector2D와 NamedVector의 관계를 선언하지 않아도 타입에러가 발생하지 않는다.
  - 즉, NamedVector타입인 param을 Vector2D타입의 인자를 받는 caculateLength로 실행해도 정상적이다.
  - 좋든 싫든 ts의 타입 시스템에서 타입은 확장될 수 있도록 '열려' 있다.
    ```ts
    interface Vector2D {
      x: number;
      y: number;
    }

    interface NamedVector {
      name: string;
      x: number;
      y: number;
    }

    function caculateLength(v: Vector2D) {
      return Math.sqrt(...);
    }

    const param: NamedVector = {x: 3, y: 4, name: 'haha'}
    caculateLength(param)
    ```

<br />
<hr />

## **2021-05-05**

- **colon(:) in vim**
  옛날에는 터미널로 모든 상호작용을 해야 했으므로, ex(extended)라는 짧은 니모닉 명령으로 구성되었다. `:substitute/foo/bar`와 같은 명령으로 상호작용했다. 하지만 시간이 지나면서 vi가 ex commands를 통합하고 `i`, `x`와 같이 더 많은 대화형 명령들을 도입했다. 따라서 콜론(:)은 ex모드로 전환하는 명령어이다. 참고로 [vim의 모드](http://vimdoc.sourceforge.net/htmldoc/intro.html#Normal)는 아래 6가지이다.
  - **normal mode**: 모든 편집기 명령을 할 수 있는 모드, command mode
  - visual mode: 문자열 혹은 라인을 하이라이팅할 수 있는 모드, "v" 혹은 "V"로 시작
  - select mode: 커서로 문자열 혹은 라인을 하이라이팅할 수 있는 모드, "gh"로 시작
  - **insert mode**: 가장 자주 쓰이고 텍스트를 삽입 혹은 대체할 수 있는 모드, "i"로 시작이 일반적
  - ex mode: ex 명령어들을 사용할 수 있는 모드로 vi 자체가 비주얼된 ex, ":"으로 시작
  - command-line mode: ex commands를 사용할 수 있기 위한 모드
    - Ex commands (`:`)
    - search patterns (`/` and `?`)
    - filter commands (`!`)

<br />
<hr />

## **2021-04-14**

- **npm ci**
  - 상태를 클린하게 유지하기 위해 `node_modules`를 모두 지움
  - `package-lock.json`으로 명시된 버전으로 의존성을 설치함
  - package-lock.json 파일을 수정하지 않는데, 이 파일이 없으면 설치도 안됨
  - 따라서 CI에서 배포 전 의존성 설치로 사용하기에 적합
- **npm install**
  - 모든 의존성을 설치하거나 기존 dependency를 업데이트
  - 설치 후 변경사항이 있으면 그에 맞게 package-lock.json를 수정함

<br />
<hr />

## **2021-03-26**

- [border-radius 속성](https://www.w3.org/TR/css-backgrounds-3/#border-radius)은 각 모서리에 지정한 반지름을 가진 원으로 라운딩 처리를 한다. 이때 radius를 50%, 100%, 999px 이런 식으로 줘도 일정 비율 이상 커브가 생기지 않는데 그 이유는 각 원이 겹치지 않게 처리하기 떄문이다. 아래는 공식문서에 적힌 내용이다.

  > Let f = min(Li/Si), where i ∈ {top, right, bottom, left}, Si is the sum of the two corresponding radii of the corners on side i, and Ltop = Lbottom = the width of the box, and Lleft = Lright = the height of the box. If f < 1, then all corner radii are reduced by multiplying them by f.

  **각 코너에 준 값에 대한 비율을 계산해 그 중 최소비율값을 곱하면 각 radii끼리 겹치지 않게 된다.** 그래서 999px, 10px, 999px, 10px 이런 식으로 주면 일정 비율을 곱하기 때문에 직사각형 왼쪽의 원이 필요한 것보다 줄어들게 된다. [이 문서 - what-happens-when-border-radii-overlap](https://css-tricks.com/what-happens-when-border-radii-overlap/)가 설명을 잘 해놨더라.

<br />
<hr />

## **2021-03-24**

- angular 프레임워크를 사용할 때 생성자 메서드를 주의하자. constructor는 단지 ES6 클래스 문법에서 객체를 생성하는 시점에 호출되므로 angular가 초기화 작업을 수행하기 전이다. 따라서 앵귤러 컴포넌트에서 바인딩한 속성이나 부모 컴포넌트로부터 전달받은 속성 등의 초기화를 보장하지 않는다. 생성자에는 순수하게 객체의 생성 시점에 필요한, static한 값을 초기화할 때만 사용하자.
- **Angular Application Bootstrap: 모듈 셋업 외에는 모두 component bootstrap이다.**
  - Module setup - 모듈 초기화, 의존성 주입 등
  - View creation - 템플릿 코드를 실제 DOM으로 생성
  - Change detection

<br />
<hr />

## **2021-02-24**

- cmd에서 작업하던 소스를 단위(hunk)별로 stage에 올리고 싶으면 `--patch` 옵션 사용하면 된다.

  ```sh
  $ git add --patch
  ```

- 반영할지 말지 선택하는 옵션들은 아래와 같다. 보통 y로 반영하고, n으로 반영하지 않는다.

  ```txt
  y - stage this hunk
  n - do not stage this hunk
  q - quit; do not stage this hunk or any of the remaining ones
  a - stage this hunk and all later hunks in the file
  d - do not stage this hunk or any of the later hunks in the file
  g - select a hunk to go to
  / - search for a hunk matching the given regex
  j - leave this hunk undecided, see next undecided hunk
  J - leave this hunk undecided, see next hunk
  k - leave this hunk undecided, see previous undecided hunk
  K - leave this hunk undecided, see previous hunk
  s - split the current hunk into smaller hunks
  e - manually edit the current hunk
  ? - print help
  ```

<br />
<hr />

## **2021-02-10**

- 타입을 export하지 않고 있는 3rd party library 등을 ts에서 사용할 때 `d.ts` 파일에 모듈을 선언해두는 과정이 필요한데, 모호성 때문인지 이걸 Ambient declarations 부르더라. 그래서 타입스크립트 내에는 이 이름 그대로 [TypeScript/ambients.d.ts](https://github.com/microsoft/TypeScript/blob/master/scripts/types/ambient.d.ts) 파일이 있다. 외부 모듈을 declare해서 tsc가 이해할 수 있도록 한다.

<br />
<hr />

## **2021-02-09**

- [sapper](https://sapper.svelte.dev/)는 svelte로 구동시키는 웹앱 프레임워크다. 아래의 구조로 이루어진다. routes연결부분이 rails랑 비슷하다는 생각이 들었다.

  ```txt
  src
      client.js
      server.js
      service-worker.js
      template.html
  src/routes
      ...
  static
  ```

  - template.html에 `%sapper.head%`와 같은 태그를 명시하여 서버에서 받은 응답을 처리할 수 있다. 동적으로 메타를 바꿔야 하므로 SSR 필수요소.
  - src/routes에 svelte컴포넌트를 넣으면 해당 컴포넌트 자체가 하나의 라우트 엔트리가 된다.
  - static은 리액트와 마찬가지로 static 리소스들을 몰아 넣는 곳.

<br />

- 프로젝트에 절대경로를 사용하고 싶으면 webpack, rollup같은 번들러에 alias 관련 플러그인을 설정하면 잘 되는데, 에디터에 빨간 줄이 나와도 당황하지 말자. jsconfig 혹은 tsconfig에 `paths`를 명시해서 에디터가 알 수 있도록 해주자.
  ```txt
  "compilerOptions": {
      ...
      "baseUrl": "./",
      "paths": {
        "@/*": ["src/*"]
      }
  }
  ```