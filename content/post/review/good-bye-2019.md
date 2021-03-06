---
title: "Good bye 2019"
date: "2019-12-27"
tags: ["review"]
draft: false
og_description: "난생 처음 쓰는 회고. 간단하게 월별로 내가 뭘 했는지 한번 기록해보자."
---

난생 처음 쓰는 회고. 간단하게 월별로 내가 뭘 했는지 한번 기록해보자.

<br />

## 월별기록

- [1월, 2월](#1-2)
  - 프론트엔드 개발자, 혹은 팬케이크형 인간으로의 진화
  - 이직을 결심하게 된 이유
- [3월](#3)
  - React? Angular? 채용과정에서의 과제
  - 공부, 공부, 공부!
- [4월, 5월](#4-5)
  - React 묻고 리팩토링 더블로 가!
  - Typescript에 대한 얇고 쓸모있는 깨달음
  - 예상치 못한 변수의 등장
  - 협업 컨벤션 만들기
- [6월](#6)
  - css도 모듈화가 필요하다구요!
  - 🏊‍♀️ 어푸어푸, 물이 너무 좋은데 왜 수영을 못하지?
- [7월](#7)
  - 모여서 각자 코딩하지만 지식은 같이 올라가는 magic ☆
  - 실무에서의 첫 테스트 코드
- [8월](#8)
  - SEO 삽질
  - Ruby on rails, 혹은 Javascript(?) 삽질
  - flex 로 grid 해버렸자너, 나만의 공식
  - 🎐 동해에는 해파리가 많아요
- [9월](#9)
  - 프로젝트에 디버깅 툴 적용해보기, ft. sentry
- [10월](#10)
  - Webpack 직접 설정해본 소감
  - 새로운 프로젝트 = react + redux-saga + typescript
  - ✏️ 대한민국 편지쓰기 공모전 참가
- [11월](#11)
  - 별건 아니고, 나의 첫 오픈소스 라이브러리 final-flex
  - 🧘 내일은 요가왕
- [12월](#12)
  - 사내 연말파티 MC!?

<br />

#### 그밖의 기록들

- [독서](#read)
- [영화](#watch)
- [여행](#trip)
- [알고리즘](#algorithm)

<br />

---

## 1월, 2월

#### **_프론트엔드 개발자, 혹은 팬케이크형 인간으로의 진화_**

이때는 초대권 기반의 티켓 전달 서비스 회사에 다녔는데, 처음으로 프론트엔드 개발자 포지션으로 1년여간 일했다. Angular 프레임워크로 된 기존 프로젝트를 유지보수 및 개발했고, 굉장히 규모가 작은 스타트업이어서 프론트엔드 전담개발, 서비스 기획, UI/UX, 심지어 IR까지 했던...

나는 언론정보학과(!)를 전공하여 발표에 그나마 능했던 직원으로서, VC 앞에서 발표까지 했다. 발표가 나쁘진 않았던 모양인지 성공적으로 투자유치까지 했었다. 하지만 정작 중요한 본업, 개발에 많은 시간을 쓰지 못하게 되어 갔다.

<br /><br />

---

## 3월

#### **_이직을 결심하게 된 이유_**

1년여간 다녔던 회사에서 처음으로 마크업도 제대로 해보고, SPA도 처음 다뤄봐서 의미는 있었지만, 협업에 대한 갈망이 커졌다. 다른 개발자들과 코드리뷰도 하고 함께 토론하면서 발전하고 싶다는 생각이 커졌다. 물론 우리의 친구인 구글과 스택오버플로우, 그리고 정보의 바다인 웹과 함께라면 얼마든지 발전할 수 있겠지만...! 혼자 있으면 확실히 나태해진다. 부정할 수 없다. 특히 개발자가 혼자여서 실무 위주로 빠르게 일을 쳐내야 했기 때문에 더더욱 구조에 대한 고민이나 코드 품질에 대한 생각을 하기가 어려웠다.

그래서 이직을 결심했다.

<br />

#### **_React? Angular? 채용과정에서의 과제_**

이번에 내가 지원했던 대부분의 회사는 알고리즘 테스트보다는 과제 위주였다. 대부분의 회사 주업무가 React 기반의 서비스 개발이었으나, 과제에서는 어떤 프레임워크 or 라이브러리를 쓰든, 혹은 바닐라로 하든 상관없는 곳이 대부분이었다. 그런데 내가 지원한 회사의 과제들이 규모가 작고, 상태관리를 어떻게 할 것인지가 중요한 과제들이었기 때문에 주로 React를 사용해서 과제를 제출했다. 이때 React를 처음 써봤는데, 뭔가 앵귤러를 할 때와 굉장히 다른 느낌이었다. 단방향으로 이루어지는 데이터 흐름이 이해하기 어려웠고, `props`와 `state` 개념도 잘 와닿진 않았다.

다만, React는 함수형과 정말 궁합이 잘 맞는다는 생각이 들었다. 함수형, 함수형 말만 들었지 도대체 어떻게 쓰는 것인가 이해가 가지 않았는데, React의 가장 핵심 메소드라고 할 수 있는 `setState()`자체가 함수형스러웠다! 왜냐하면 이 녀석은 항상 새로운 객체를 반환한다. 따라서 객체는 불변함을 유지하게 될 뿐만 아니라, 불변해야만 이전 state를 기억하여 재렌더링을 일으킬 수 있다. 하지만 아쉽게도 과제를 빠르게 끝내야 했기에 제대로 이해하지 못한 채로 기능구현에 급급하여 제출해서 아쉬웠다.

<br />

#### **_공부, 공부, 공부!_**

그리고 과제를 하면서 깨달은 것은, 생각보다 내가 알던 세계는 너무 좁았다는 것이다. 부끄럽게도 자바스크립트 문법 자체를 헷갈려서 오래 걸리거나 해내지 못한 게 많았다. 객체의 불변성을 유지하면서 코드를 작성하는 연습도 되어있지 않았다. 이러한 이직과정을 통해 자바스크립트에 대한 부족함을 많이 느껴 좌절했지만, 학습에 대한 동기부여가 되기도 했다.

<br /><br />

---

## 4월, 5월

#### **_React 묻고 리팩토링 더블로 가!_**

과제를 제출했던 회사들 중에 한곳에 합격하여 현재도 다니고 있다. 들어와서 두 달 정도는 React 생태계에 대해 이해했다. 그런데 기존에 있던 코드품질이 생각보다 좋은 편이 아니어서 리팩토링까지 함께 해야했다. 리덕스로 거의 모든(!!) 상태를 관리하고 있던 프로젝트여서, 상황에 맞게 분리시키는 작업과 더불어 React `v16.8`에서 도입된 hooks를 이용해 클래스형 컴포넌트들을 함수형 컴포넌트로 리팩토링했다. 내가 들어왔을 때는 큰 기능 하나를 만들어야했기 때문에 기능구현을 하면서 진행했다.

<br />

#### **_Typescript에 대한 얇고 쓸모있는 깨달음_**

이 과정에서 기존 코드나 React 생태계, 심지어 자바스크립트도 깊이 있게 모른 채로 진행해서 삽질을 좀 많이 했다. 그래도 별 수 있나. 모르는 부분은 집에서 새벽까지 했다... 해당 프로젝트에 `typescript`도 얹었다. 여기서 또! 부끄러웠던 지점은, 앵귤러로 개발할 때는 타입스크립트의 소중함을 몰랐다는 것... 꼭 필요한 부분도 아닌데 `any`로 타입을 허용해 타입스크립트의 장점을 활용하지 못했다. 그런데 이번 기회에 ts를 좀더 심도있게 해보면서 활용할 지점이 많다는 걸 알았다.

<br />

- API 혹은 외부 데이터에 대한 타입을 알 수 있다는 점만으로도 해당 데이터를 예측할 수 있으니 생산성이 올라갔다.<br />
- 또한 컴파일 단계에서 걸러주니 타입에러가 날 염려가 없다. 자바스크립트는 의도치 않은 타입 에러를 내는 경우가 많다. 돔 렌더링이 이루어지지 않았는데 참조하려고 한다거나, 정의되지 않은(`undefined`) 프로퍼티나 메소드를 참조하려고 한다거나...<br />
- 그리고 코드가 Testable하게 쓰여진다! 실제로 테스트코드를 작성했는지 여부와 무관하게, 지정하지 않은 타입이 들어올 수 없는 안전한 코드를 작성하게 된다. 즉, 들어오는 값에 대해 어느정도 제어할 수 있고, 어떤 값이 반환될 지도 알 수 있기 때문이다.

<br />

#### **_예상치 못한 변수의 등장_**

그런데 일을 하면서 예상치 못한 변수가 있었는데, 바로 백오피스 페이지였다. 웹팀이 맡아야 하는 프로젝트가 두개였는데, 그중 `Ruby on Rails`로 작성된 프로젝트이다. 말이 rails이지 그냥 `JQuery`로 굉장히 명령형으로 작성되어있는 프로젝트였다. 내가 들어오기 전부터도 유지보수가 정말 힘들다고 알려준 프로젝트여서 마음을 졸이며 확인했는데... WOW!! 그나마 다행(?)이었던 건, 옛날에 SI 유지보수할 때와 비슷한 코드라는 점이었다. 빠르게 성장한 회사이고, 앞선 개발자 분들도 시간에 쫓기며 빠르게 쳐내야 했다고 들어서 이해했다. 하지만 문제가 터질 때마다 해결하기 정말 힘들었던 건 사실이다.

그래도, 모든 회사의 레거시는 일단 respect!

<br />

#### **_협업 컨벤션 만들기_**

아무튼 리팩토링과 더불어 4월과 5월은 프로젝트 세팅하고, 회사 적응하고, 동료와 여러가지 룰을 정하면서 함께 협업하느라 시간이 빨리 갔다. 커밋메시지나 코드 컨벤션 등의 룰을 정해보았는데, 커밋메시지는 기존에 내가 사용하던 컨벤션이 있어 제안했고, 동료 분도 괜찮다고 하여 그렇게 진행했다.

잠깐 말하자면 나는 모든 코드는 결국 CRUD라고 생각한다. 그래서 `Create: blah / Update: blah / Delete: blah`의 형식으로 커밋 메시지를 남기고 있다. 버그 혹은 에러 수정은 `Fix:`로 쓰는데, 이외에 단순 오타 수정이나 정말 별거 아닌 커밋이 존재하기 마련이다. 이런 것은 `Chore:`와 `ETC:` 중에서 고민하다가 후자를 선택했다. 지극히 개인적으로 ETC가 대문자라서 좀더 이렇게 외쳐주는 느낌.

```s
 ETC: 나는 크게 중요하진 않지만 한 커밋 정도는 차지해야 합니다.
```

<br /><br />

---

## 6월

#### **_css도 모듈화가 필요하다구요!_**

이때는 회사에서 모든 팀이 함께 작업해야 하는 큰 sprint가 있었기에, 웹팀도 열심히 작업했다. 특히 디자인 시안이 막 나오고 있던 때여서 마크업 위주로 화면을 설계했다. 마침 마크업을 건드리다보니 프로젝트 전체의 css 구조도 살펴보게 되었다. 그런데 해당 프로젝트 레거시에서 큰 문제 중 하나가 css를 여러 번 import하고, base와 reset의 기능을 하는 코드가 한군데 섞여있는 등 css의 모듈화(?)가 제대로 되어있지 않다는 점이었다.

그래서 여러 번 불리는 css가 한번만 불리도록 하고, font도 한군데서 관리하며, `SASS` 문법을 활용해 전체 구조에서 필요한 css 변수들을 묶었다. 이 과정에서 동료와 함께 `css module`을 도입해 적용하기 시작했다. 이처럼 뷰와 관련된 작업을 주로 했다.

<br />

## 🏊‍♀️

#### **_어푸어푸, 물이 너무 좋은데 왜 수영을 못할까?_**

회사에서 점심시간에 필라테스를 하러 가는 모임이 있었는데, 평소 운동을 좋아했던 나도 약간 끌렸다. 그런데 마침 회사 근처에 수영장이 점심시간에만 자유수영을 여는 것이었다. 그래서 나는 물을 너무너무너무너무 좋아하지만 수영을 배워본 적 없었기에 혼자 연습도 할 겸 일주일에 3번정도 점심시간에 가기 시작했다. 한 2주 동안은 물만 먹고 앞으로 나아가지도 못했다...

그런데 열심히 회사 중간에 나와서 *어푸어푸*하는 내가 불쌍했는지 안전요원 분께서 한 5분? 10분? 정도 간단하게 자유형을 알려주셨다! 그런데 OMG... 사람은 역시 제대로 배워야 한다는 것을 다시금 깨달았다. 그 짧은 배움만으로도 일주일만에 자유형을 할 수 있게 된 것이다! 물론 여전히 레일 끝까지 가지는 못했지만 발이 닿는 곳까지는 나아갈 수 있었다.

<br /><br />

---

## 7월

#### **_모여서 각자 코딩하지만 지식은 같이 올라가는 magic ☆_**

좋은 자료 공유나 소식을 받기 위해 개발 관련 오픈카톡방에 들어가 있는데, 여기서 `모각코 - 모여서 각자 코딩`을 주도하는 분이 계셨다. 주마다 참여 인원을 모집해서 지식 공유도 하고 개인 공부도 하는 그런 모임이었다. 그래서 같이의 가치(...)를 느끼고 자극을 받고자 한번 가보았는데, 생각보다 집중이 잘됐다. 게다가 역시 *백지장도 맞들면 낫다*는 말처럼 함께 나누고 developing하는 지식이 어마무시했다. 참고로 해당 모임은 [github repository - free study community](https://github.com/limlimlim-study/free-study-community)로 관리되고 있다.

7월은 빠짐없이 매주 수요일마다 갔고, es6+ 문법을 다시 한번 상기시키기 및 공부하고 `nextjs`와 `antd` 등 해보고 싶었던 것들로 간단한 보일러플레이트를 작성했다.

<br />

#### **_실무에서의 첫 테스트 코드_**

회사에서는 7월에 처음으로 테스트 코드를 작성해봤다. 컴포넌트 단위의 통합테스트까지는 여력이 안됐지만, util 함수 등에는 테스트 코드를 작성하기로 했었다. 그래서 마침 날짜 관련 데이터 format이 여러군데서 통일성 없이 쓰여 있었기에 이를 유틸함수로 빼고 테스트 코드를 작성했다. 비록 프로젝트의 전체 coverage를 논할 것도 없는 자그마한 작업이었으나, 실무에서 테스트 코드를 작성해본다는 점이 의미 있었다.

테스트 코드 작성은 일부러 에러를 내면서 코드를 커버하고, 케이스를 생각하면서 작성해야 하기 때문에 처음 시간은 더 드는 것이 사실이다. 그러나 이렇게 작성해두니 이쪽에서 문제가 발생한 적은 (아직까지는) 한번도 없었다. 물론 뭔가 수정했을 때 컴파일 단계에서 테스트가 깨져서 사전에 고친 적은 있지만, 이건 테스트 코드의 존재 이유이자 원했던 바!

<br /><br />

---

## 8월

#### **_SEO 삽질_**

프로젝트 SEO 관련해서 삽질을 좀 했었다. 클라이언트 사이드 렌더링 기반에서 헤드리스 브라우저를 이용한 SEO 작업을 했는데, 뭔가 개발 테스트에서와 라이브에서 의도하는 바가 맞지 않았다. 여러 삽질을 하다가 이런 포스트도 작성했었다. [prerendering](https://wacilpong.github.io/blog/post/prerender-status-code/) 물론 삽질을 한 부분은 해당 포스트에서 작성한 프리렌더와는 무관하게 코드 내에 특정 케이스에 대한 문제였다. 그래도 삽질을 하면서 SEO에 대해 좀 더 알게 되었다!

<br />

#### **_Ruby on rails, 혹은 Javascript(?) 삽질_**

기존 백오피스 페이지에서 이미지를 업로드할 때 S3로 직접 태우는 방식이었는데, 회사에서 이미지 용량을 줄이기 위해 중간에 사내 API로 한번 보내기로 했다. 그래서 업로드하는 부분을 수정해야 했다. 사실 자바스크립트 ajax로 보내도록 수정하는 게 가장 쉬울 거라고 예상할 수 있겠지만, 해당 프로젝트는 자바스크립트쪽 코드가 훨씬 보기가 힘들었다. 게다가 업로드하는 rails쪽 코드만 _샥_ 바꿔서 여러군데 수정하지 않아도 되니까 아예 업로드 관련 모듈로 따로 만들었다.

해당 프로젝트에서 사용중이었던 http 관련 모듈 gem에서 multipart로 post 요청 시 파일을 자꾸 스트링으로 바꾸는 이슈가 있었다. 그래서 multipart 관련 gem을 사용하여 해결했다. 업로드 모듈은 class로 빼고 생성자 함수를 만들어 공통 컨트롤러에서 세션정보를 주입받도록 했다. 그래서 비교적 깔끔하게 해결하리라 생각했지만, 정말 이해가 안되는 문제가 발생했다.

<br />

## 😭

###### **DOM에 대한 의존은 최소화합시다**

바로 특정 환경에서만 알 수 없는 문자열이 파일 파라미터로 들어오는 것이었다! 특정 브라우저도 아니고, 특정 OS 버전문제도 아니었다. 엄청나게 삽질한 끝에 발견한 것은, 파일을 업로드한 후 해당 썸네일을 그리기 위해 뭔가 굉장히 DOM에 의존적인 방식으로 정규식을 사용해 엘리먼트의 style 속성을 가져와서 replace 하고 있다는 것을 알았다. 이 코드를 분석해본 결과 이미지의 url을 `background: url(...)`에서 가져오고 있었다.

그래서 해당 코드를 모두 지우고 html의 `dataset`을 이용해 미리 url을 가지고 있다가 필요할 때 꺼내는 방식으로 수정했다. 아마 DOM에 너무 의존적이다보니 특정 상황에서 다른 문자열이 정규식을 통해 뽑힌 것 같다.

<br />

#### **_flex 로 grid 해버렸자너! 나만의 공식_**

`flex`로 그리드 레이아웃을 그리는 데 있어서도 삽질을 좀 했다. 해당 css 속성에 박스 정렬을 맡기고 간격값을 계산하지 않는 방법을 고민했는데, 여러 시도를 해보다가 아래처럼 공식을 만들었다! flex가 여분의 공간을 계산해서 보여주는 `space-between`속성을 이용하면서 마지막 row만 왼쪽으로 정렬을 맞춰주는 것이다. 이를 위해서는 마지막 row에만 숨겨진 박스를 심어주면 된다고 생각했다.

```javascript
1. 총 데이터 = 18
2. 한 row에 들어오는 elements = 5
3. 마지막 row에 들어오는 elements = 18 % 5 = 3
4. 마지막 row에 들어와야 할 elements = 5 - (18 % 5) = 2
```

정말 별거 아니지만, 그래도 개인적으로는 코드가 명확한 것 같아서 이러한 공식을 사용하고 있다.

<br />

## 🎐

#### **_동해에는 해파리가 많아요_**

8월말, 여름의 끝자락에 동해로 놀러갔다! 그동안 회사 점심시간에 수영했던 실력을 갈고닦아 여유롭게 바다수영을 해보고 싶었...으나... 내가 갔던 바다만 그런 건지, 아니면 동해가 그런 건지, 파도가 엄청났다. 수심은 얕은데 파도가 쳐서 물싸대귀 맞으면서 수영했다(ㅋㅋ) 스노클링 안경도 가져가서 끼고 해봤는데 물고기는 꽤 보여서 재밌었다. 그런데 해파리가 너무 많이 보여서 징그러웠다. 다음에 동해에서 놀 때는 그냥 튜브 타고 노는 걸로.

<br /><br />

---

## 9월

#### **_프로젝트에 디버깅 툴 적용해보기, ft. sentry_**

웹 프로젝트에 에러 트랙킹 툴이 없어서 서버 에러로만 의존해야 하는 점이 불편했다. 그래서 함께 일하는 동료가 [sentry](https://sentry.io/welcome/)를 알려주어서 한번 파보기 시작했다! 시험삼아 테스트해보니 프로덕션에서 기기별, 브라우저별, 유저의 UI 작동 히스토리까지 나와서 정말 편했다. 그런데 아쉬웠던 점은 자꾸 `.min.js` 소스코드를 참조한다는 점이었다. 그래서 소스맵을 generating하여 참조시켜보았지만 해결되지 않았다. 배포할 때 소스맵을 따로 센트리에 함께 업로드시키는 bash script도 작성해서 `postbuild`훅으로 실행해보았는데도 해결되지 않았다. (ㅠㅠ)

문서에 의하면 아래의 4가지 이유로 소스맵이 깨질 수 있다고 한다.

1. Missing or incorrect source map directive
2. Missing original source files
3. Bad source maps caused by multiple transformations
4. Files are incorrectly versioned or missing versions

<br />

내 생각에는 배포를 aws 등을 통해 자체적으로 구축하면 해결될 수 있을 것 같았다. 프로젝트 자체도 [Create-react-app](https://github.com/facebook/create-react-app)으로 되어 있어 번들링을 제어하기 쉽지 않고, [Netlify](https://www.netlify.com/)로 배포하여 해당 툴을 거쳐서 cdn으로 가기 때문에 중간에서 여러 transformation이 일어나기 때문이다. 그래서 아쉽지만 당장 해결되기 힘들다고 판단하고 보류해두고 있다. 그래도 센트리를 적용해서 많은 에러를 고친 것은 사실이다!

특히 IE, IE, IE...

<br /><br />

---

## 10월

#### **_Webpack 직접 설정해본 소감_**

7월부터 꾸준히 수요일마다 갔던 모각코 모임에서 나만의 무언가를 만들고 싶어서 프로젝트를 시작했다. 특정 영상을 크롤링해서 보여주는 웹앱을 만들고 싶었고, 이를 위해 프로젝트를 세팅했다. 이름하야 [videowl](https://github.com/wacilpong/videowl). 그동안 보일러플레이트 등을 활용해 프로젝트를 구성했어서, [webpack](https://webpack.js.org/)과 같은 트랜스파일링 및 번들링 툴을 직접 설정해본 적이 없다. 그래서 웹팩부터 천천히 적용해봤다. 수요일에만 해서 그런지 한 달동안 웹팩 설정만 한 건 함정.

특히 백엔드와 프론트엔드 configuration을 한 프로젝트 내에서 함께 번들링하는 것을 시도했기에 여러 삽질을 했다. 이 과정에서 웹팩의 로더들, 엔트리와 아웃풋을 지정해 번들링되는 과정 등을 이해할 수 있었다. 물론 아직도 모르는 것 투성이지만! 해당 프로젝트 세팅을 마치고 실제로 크롤러를 구현하다보니 깨달은 점은, 그냥 유튜브 API를 이용해 유튜브의 영상만 크롤링해보는 것이 낫겠다는 것이었다. 그래서 유튜브 API를 클라이언트 사이드에서 활용해 구현해보려고 했..는데 내가 게으른 탓에 방치중. 내년에는 다시 잡아서 잘 해보자!

<br />

## 😆

##### **_새로운 프로젝트 = react + redux-saga + typescript_**

드디어 회사에서 백오피스 페이지를 React 기반으로 다시 만들기로 하여, 차근차근 설정을 시작했다. Create-react-app으로 시작했고, 예측가능하게 만들 상태를 관리하기 위헤 `redux`를 적용하고, 이에 따른 비동기 상태를 관리하기 위해 `redux-saga`를 적용했다. 물론 리덕스 스토어로 관리될 필요가 없는 비동기 상태는 각 사용처에서 프로미스로 상태관리하도록 했다.

사실 사가를 사용한 결정적 이유는 테스트코드 작성이 비교적 쉬우므로, 테스트 코드를 작성하고 싶어서였다. 그러나 밀린 일이 너무나 많고... 혼자서 처리하다보니 시간이 없다. 그래도 http 통신부를 mocking해서 요청 및 응답, 인터셉터와 관련해 비교적 광범위하게 쓰이는 부분에 대해서는 테스트 코드를 작성했다. 내년에는 각 사가 미들웨어 코드에 대해서도 견고하게 테스트 코드를 조금씩 작성해보자!

<br />

## ✏️

##### **_대한민국 편지쓰기 공모전 참가_**

평소에 글쓰기를 좋아하고, 작년까지는 짧은 쪽글소설도 가끔 쓴 적이 있다. [글쓰기 전용 블로그](https://aroomy.tistory.com/)까지 있으나 업데이트된 지 일년 넘은 건 함정. 핑계일 수도 있으나 이런 취미생활을 영위하기에는 공부나 업무만으로 너무 바빴다. 그래도 틈틈이 글을 써보고 싶었고, 아예 대회에 출품할 글을 써보면 동기부여가 될 수 있을 것 같았다. 이때 [대한민국 편지쓰기 공모전](http://www.lettercontest.kr/)을 알게 되어서 틈틈이 편지를 써보았다.

편지 주제는 _나와 다른 남을 이해하고 배려하기_ 였다. 그래서 서로의 입장에서 좀더 생각해보면 좋겠다는 마음으로, _나_ 라는 화자가 _너_ 라는 청자에게 주었던 상처가 되는 말들에 대해 사과하는 편지를 써보았다. 본인은 쉽게 말했지만 상대방에게 상처가 되는 그런 말들에 대해 돌이켜보고, 깨닫고, 사과하는 과정을 담은 편지다. 이런 글을 써보면서 평소에 나도 남들에게 쉽게 내뱉었던 말들에 대해 돌아볼 수 있었다.

물론 상은 못받았다! 하지만 뚜렷하게 대회라는 목표가 있으니 틈틈이 글을 쓰는 데 동기부여가 됐다. 그래서 내년에도 대회 하나쯤 한번 더 도전해볼 예정이다. 내년에는 쪽글 소설도 심심할 때 써봐야지.

<br /><br />

---

## 11월

##### **_별건 아니고, 나의 첫 오픈소스 라이브러리 [final-flex](https://www.npmjs.com/package/final-flex)_**

8월에 작업했던 flex로 grid 그리는 간단한 공식을 오픈소스로 만들어보면 어떨까 생각이 들었다. 진짜 별거 아니지만... 이를 추후 발전시킬 수도 있고, 확장시킬 수도 있겠다는 생각이 들어서 시작했다. 패키지 이름도 거창한 [final-flex](https://www.npmjs.com/package/final-flex)! flex를 끝장내겠다는 다짐! 원래 의도는 데이터를 주입받으면 css까지 입혀서 그려주는 라이브러리로 만들려고 했는데, npm으로 배포하는 것도 처음이어서 일단은 가장 간단하게 구현했다. 작은 규모이고 설정할 것들이 별로 없어서 `gulp`로 번들링했다.

내년에는 좀더 발전시켜서 고정형 및 반응형 그리드까지 다룰 수 있는 라이브러리로 만들어봐야겠다!

<br />

## 🧘

##### **_내일은 요가왕_**

평소에 헬스장에서 근력운동을 하거나 수영을 하며 운동했는데, 수영장이 공사해서 1월까지 못가게 되었다. 그래서 친언니가 갑자기 요가영상을 공유해줘서 따라해봤는데, 완전 신세계였다. 엄청나게 시원했다! 심지어 에러 및 버그들로 더러워진(?) 나의 정신을 수련하기에도 적합했다. 이렇게 정적인 운동이 잘 맞을 거라고 생각 못했는데 너무 잘맞아서 놀랐다. 이후로 거의 매일매일 짧게는 30분, 길게는 2시간동안 요가하는 삶을 보내고 있다.

특히 나의 최애 요가는 [이것](https://www.youtube.com/watch?v=WwwAdze4HDA)인데, 30분짜리여서 매일매일 하기에도 적합하다. 요가를 하다보니 평소에 자세도 좋아지고, 몸도 유연해지고, 근육도 붙고, 심지어 의도치 않았는데 체중감량도 했다. 뭐 내가 재밌어서 많이 하니까 효과가 좀더 나왔겠지만.

모두들 요가하세요.. 요가는 좋은 운동입니다...

언젠가 기회가 되면 요가자격증도 따볼 생각이다!

<br /><br />

---

## 12월

## 🎤

##### **_사내 연말파티 MC!?_**

어쩌다보니 사내 연말파티를 기획 및 진행하게 되었다. 솔직히 말하면 일이 바빠서 하고 싶지 않았지만, 어쨌든 업무로써 나에게 주어진 것이므로 열심히 기획해보려 노력했다. 회사가 다음 발전을 위해 인원을 많이 충원하는 시기여서 총 인원의 절반 이상이 새로운 분들이었다. 물론 나도 오래된 건 아니지만(ㅋㅋ) 그래서 서로 동료로서 친해질 수 있는 게임들을 준비했다.

1. **_천하제일 하찮은 대회_** : 사전에 선물 줄 대상을 뽑아서, 파티 당일에 그 대상을 위한 하찮고 예쁜 선물을 준비해온다.
2. **_나는 누구일까요?_** : 모든 동료에게 10문 10답을 받아서, 파티 당일에 스무고개 형식으로 문제를 내고 누구인지 맞춘다.
3. **_어워즈_** : 동료들의 특징이나 많이 뱉는 말 등을 이용해 관련된 상품을 주면서 상장을 수여한다.

특히 2번 게임의 경우 서로를 많이 알 수 있어서 의미는 있지만, 재미가 있을까 싶었다. 그런데 생각보다 누구인지 맞춰보면서 대화도 많이 나누고, 서로 재미있어하는 모습을 보고 안도했다! 이날 드레스코드도 정해서 베스트 드레서도 뽑았는데 진짜 의도한 건 아닌데 내가 뽑혔다. 걱정도 많았고 준비나 MC본 것도 힘들었지만 모든 동료들이 서로서로 더 알 수 있게 되어 뿌듯했다.

<br />

12월은 쉬는 날도 껴있고, 가족행사도 있어서 마무리하는 느낌으로 보내고 있다.

<br /><br />

---

## 📚

## Read

독서는 많이는 못했다. 특히 _죄와 벌_ 을 작년부터 읽고 있었는데 거의 뭐, 작년 내내 읽다가 올해 드디어 다 읽었다. 다 읽은 달을 기준으로 작성했다. 요즘은 http 도서를 읽어보고자 _러닝 HTTP/2_ 를 읽고 있다. 내년 1월까지는 다 읽어보자!

- (2019-02) **[죄와 벌]**, 도스토예프스키
- (2019-03) **[한밤의 모험]**, 발터 뫼어스
- (2019-03) **[잃어버린 은띠를 찾아서]**, 발터 뫼어스
- (2019-05) **[동물농장]**, 조지 오웰
- (2019-07) **[1984]**, 조지 오웰
- (2019-09) **[실전 리액트 프로그래밍]**, 이재승
- (2019-11) **[타르튀프]**, 몰리에르
- (2019-11) **[클린 아키텍쳐]**, 로버트 C. 마틴
- (2019-12) **[코어 자바스크립트]**, 정재남
- (2019-12 ~) **[러닝 HTTP/2]**, 스티븐 루딘

<br />

## 🎥

## Watch

[나의 왓챠기록 click!](https://watcha.com/ko-KR/users/Mr95n9n1dvZPG/contents/movies)

올해도 여름에 _[부천 국제 판타스틱 영화제](https://www.bifan.kr/)_ 를 다녀왔다. 부천영화제는 특이한 소재의 영화가 많이 걸려서 2014년도부터 매년 가는 중이다. 특히 심야에 3~4개를 연달아 상영해주는 심야공포 패키지가 정말 재밌다! 내년에도 꼭 가야지.

- (2019-01) **[극한직업]**, 이병헌, 2018
- (2019-01) **[더풀-인티머데이션]**, 보리스 본 시솝스키, 2001
- (2019-02) **[살인마 잭의 집]**, 라스 폰 트리에, 2018
- (2019-02) **[해피 데스데이 2유]**, 크리스토퍼 B. 랜던, 2019
- (2019-02) **[알리타: 배틀 엔젤]**, 로버트 로드리게즈, 2019
- (2019-03) **[캡틴 마블]**, 애너 보든, 2019
- (2019-03) **[어스]**, 조던 필, 2019
- (2019-04) **[샤잠!]**, 데이비드 F. 샌드버그, 2019
- (2019-04) **[앨리스]**, 얀 슈반크마이에르, 1988
- (2019-04) **[판타스틱 플래닛]**, 르네 랄루, 1973
- (2019-04) **[장난스런 키스]**, 프랭키 첸, 2019
- (2019-04) **[뱀파이어와의 인터뷰]**, 닐 조던, 1994
- (2019-04) **[헬보이]**, 닐 마샬, 2019
- (2019-04) **[공포의 묘지]**, 데니스 위드마이어, 2019
- (2019-04) **[창궐]**, 김성훈, 2018
- (2019-04) **[경찰서를 털어라]**, 레스 메이필드, 1999
- (2019-04) **[요로나의 저주]**, 마이클 차베즈, 2019
- (2019-05) **[어벤져스: 엔드게임]**, 안소니 루소, 2019
- (2019-05) **[유전]**, 아리 에스터, 2018
- (2019-05) **[호텔 뭄바이]**, 안소니 마라스, 2018
- (2019-05) **[서스페리아]**, 루카 구아다니노, 2018
- (2019-05) **[오퍼나지 - 비밀의 게단]**, 후안 안토니오 바요나, 2007
- (2019-05) **[명탐정 피카츄]**, 롭 레터맨, 2019
- (2019-05) **[더 보이]**, 데이빗 야로베스키, 2019
- (2019-05) **[걸캅스]**, 정다원, 2018
- (2019-06) **[기생충]**, 봉준호, 2019
- (2019-06) **[어쩌다 로맨스]**, 토드 스트라우스-슐슨, 2019
- (2019-06) **[알라딘]**, 가이 리치, 2019
- (2019-06) **[몬스터]**, 패티 젠킨스, 2003

---

_부천영화제 상영작_

- (2019-06) **[종말 - 그 후]**, 캐롤라이나 헬스가드, 2018
- (2019-06) **[아홉번째 걸음]**, 마리사 크레스포 아브릴 & 모아세즈 로메라 페레즈, 2017
- (2019-06) **[컨덕트]**, 알리야 막시모프, 2018
- (2019-06) **[나이트메어 - 야간근무자]**, 데니슨 라말호, 2018
- (2019-06) **[나이트메어 시네마]**, 믹 개리스 & 죠 단테 & 데이비드 슬레이드 & 기타무라 류헤이 & 알레한드로 브루게스, 2018
- (2019-07) **[오버로드]**, 줄리어스 에이버리, 2018
- (2019-07) **[주디와 펀치의 위험한 대결]**, 미라 폴크스, 2019
- (2019-07) **[히비키]**, 츠키가와 쇼, 2018
- (2019-07) **[돌연변이 대격돌]**, 페르난도 알리, 2018
- (2019-07) **[달링]**, 폴리애너 맥킨토시, 2019
- (2019-07) **[온다]**, 나카시마 테츠야, 2018
- (2019-07) **[늑대의 아이들]**, 아드리안 파네크, 2018

---

- (2019-07) **[어느날 갑자기 세 번째 이야기 - D-day]**, 김은경, 2006
- (2019-07) **[더 퍼스트 타임]**, 존 캐스단, 2011
- (2019-07) **[스파이더맨: 파 프롬 홈]**, 존 왓츠, 2019
- (2019-08) **[마이펫의 이중생활 2]**, 크리스 리노드, 2019
- (2019-08) **[비카인드 리와인드]**, 미셸 공드리, 2007
- (2019-08) **[분노의 질주: 홉스 & 쇼]**, 데이빗 리이치, 2019
- (2019-08) **[존 윅 3: 파라벨룸]**, 채드 스타헬스키, 2019
- (2019-08) **[더 웨이 홈]**, 찰스 마틴 스미스, 2019
- (2019-08) **[무서운 이야기]**, 임대웅 & 민규동 & 홍지영 & 김곡 & 김선 & 정범식, 2012
- (2019-08) **[매직 마이크]**, 스티븐 소더버그, 2012
- (2019-09) **[다크 스카이]**, 스콧 찰스 스튜어트, 2013
- (2019-09) **[더 비지트]**, M. 나이트 샤말란, 2015
- (2019-09) **[애드 아스트라]**, 제임스 그레이, 2019
- (2019-10) **[조커]**, 토드 필립스, 2019
- (2019-10) **[스위트하트]**, J.D. 딜라드, 2019
- (2019-10) **[노크 노크]**, 일라이 로스, 2015
- (2019-11) **[블라인드 앨리]**, 안토니오 트라쇼라스, 2011
- (2019-11) **[겨울왕국 2]**, 크리스 벅 & 제니퍼 리, 2019
- (2019-12) **[더 허슬]**, 크리스 에디슨, 2019
- (2019-12) **[무비 43]**, 엘리자베스 뱅크스 & 그리핀 던 & 스티브 카 & 피터 패럴리 & 제임스 더피 & 스티븐 브릴 & 제임스 건 & 패트릭 포스버그 & 밥 오든커크 & 브렛 래트너, 2013

<br />

## 🧳

## Trip

이렇게 기록해보니 한달에 한번은 여행을 갔구나... 내년에는 조금 더 먼 곳들도 가보고 싶다!

- (2019-04) 2박 3일 **[도쿄, 일본]**
- (2019-05) 3박 4일 **[오키나와, 일본]**
- (2019-06) 1박 2일 호캉스 **[노보텔 앰배새더 독산 호텔 서울]**
- (2019-06) 1박 2일 호캉스 **[프레이저 플레이스 센트럴 서울]**
- (2019-07) 1박 2일 호캉스 **[스탠포드 호텔 서울]**
- (2019-08) 1박 2일 **[동해, 대한민국]**
- (2019-09) 1박 2일 **[양평, 대한민국]**
- (2019-10) 1박 2일 **[인천, 대한민국]**
- (2019-11) 2박 3일 **[제주, 대한민국]**
- (2019-11) 1박 2일 **[부산, 대한민국]**

<br />

## 🤖

## Algorithm

올해 8월 즈음부터 알고리즘의 부족함을 느끼고 조금씩 풀어본 문제들. 기초를 위한 연습문제는 기록하지 않았다. 내년에는 더 열심히 풀어보며 뇌를 말랑말랑하게 해보자.

[나의 알고리즘 문제풀이 기록 click!](https://gist.github.com/wacilpong/78647b1ba830aa5a100a9f4392a0f0f5)

- _Capture infinite string_ : 주어지는 초에서 전광판에 찍힐 문자열 구하기
- [Add Two Numbers linked lists](https://leetcode.com/problems/add-two-numbers/)
- [Reverse Integer](https://leetcode.com/problems/reverse-integer/)
- [Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/)
- [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
- [Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/)
- [Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)
- [Palindrome Number](https://leetcode.com/problems/palindrome-number/)
- [String to Integer (atoi)](https://leetcode.com/problems/string-to-integer-atoi/)
- [Container With Most Water](https://leetcode.com/problems/container-with-most-water/)
- [Two Sum](https://leetcode.com/problems/two-sum/)
- [Integer to Roman](https://leetcode.com/problems/integer-to-roman/)
- [Roman to Integer](https://leetcode.com/problems/roman-to-integer/)
- [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)
- [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
- [나머지 한 점](https://programmers.co.kr/learn/courses/18/lessons/1878)
- [가장 큰 정사각형](https://programmers.co.kr/learn/courses/18/lessons/1879)
  - [Maximal square](https://leetcode.com/problems/maximal-square/)
- [숫자 게임](https://programmers.co.kr/learn/courses/30/lessons/12987)
- [스티커 모으기](https://programmers.co.kr/learn/courses/18/lessons/1881)
- [땅따먹기](https://programmers.co.kr/learn/courses/30/lessons/12913)
- [위장](https://programmers.co.kr/learn/courses/30/lessons/42578)
- [수박수박수?](https://programmers.co.kr/learn/courses/30/lessons/12922)
- _소수 (prime number)_ : 숫자 n까지의 모든 소수 구하기
- _약수 (divisor)_ : 숫자 n의 모든 약수 구하기
- [체육복](https://programmers.co.kr/learn/courses/30/lessons/42862)
- [콜라츠 추측](https://programmers.co.kr/learn/courses/30/lessons/12943)
- [이상한 문자 만들기](https://programmers.co.kr/learn/courses/30/lessons/12930)
- [예산](https://programmers.co.kr/learn/courses/30/lessons/12982)
- [완주하지 못한 선수](https://programmers.co.kr/learn/courses/30/lessons/42576)
- [모의고사](https://programmers.co.kr/learn/courses/30/lessons/42840)
- [정수 내림차순](https://programmers.co.kr/learn/courses/30/lessons/12933)
- [영어 끝말잇기](https://programmers.co.kr/learn/courses/30/lessons/12981)
