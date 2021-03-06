---
title: "After reading <clean architecture>"
date: "2019-12-10"
tags: ["review"]
draft: false
og_description: "클린 아키텍쳐를 읽고 내맘대로 정리해보았다."
---

by Robert C. Martine

클린 아키텍쳐를 읽고 내맘대로 정리해보았다.

### **컴포넌트**

모든 언어에서 컴포넌트는 배포할 수 있는 단위 입자

- 동일한 시점에 동일한 이유로 변경되는 것들을 한데 묶고, 서로 다른 시점에 다른 이유로 변경되는 것들은 서로 분리하자.
- 필요하지 않는 것에 의존하지 말자.
- 컴포넌트에 대한 균형적인 응집 : 프로젝트 초기에 재사용성을 고민하는 것은 비효율적이다.
- 컴포넌트가 의존하는 그래프에 순환이 있으면 안된다. 순환이 생기면 그 순환 속에 있는 모든 컴포넌트가 동일한 릴리즈를 사용해야 한다. 그러나 프로젝트 초기부터 설계할 수 있는 대상이 아니기 때문에, 여러 순환 고리가 생기는 시점에 드디어 재사용성(!)을 고려해서 순환을 끊어야 한다.
- 더 안정적인 컴포넌트에 의존하자.

<br />

**안정성 지표**

- `불안정성(I) = out / (in + out)`
- 해당 컴포넌트로 들어오고 나가는 의존성의 개수를 통해 간단하게 측정할 수 있다.
- 불안정성이 0이면 가장 안정적인 상태 → 해당 컴포넌트에 의존하는 다른 컴포넌트가 있지만, 해당 컴포넌트 자체는 다른 컴포넌트에 의존하지 않으므로 해당 컴포넌트를 변경하도록 강제하는 의존성이 없음.
  - ex) [1, 2, 3 --> A컴포넌트]로 의존하고 있을 때, A의 불안정성은 0. A는 다른 컴포넌트에는 영향을 주지만, 본인에게 영향을 주는 컴포넌트가 하나도 없다.
  - ex) `HOC` → 받은 컴포넌트를 한번 래핑하고 조정한 후 그 컴포넌트를 반환하는 컴포넌트. 즉, 사이드 이펙트가 없는 순수 컴포넌트(?).
  - ex) `컨테이너 - 컴포넌트` → 상위와 하위 수준을 분리

<br />

: 모든 컴포넌트가 안정적인 것은 불가능하다. 즉, 목적성을 따져서 불안정한 것과 안정적인 컴포넌트들을 잘 결합시키자.
<br /><br /><hr>

### **좋은 아키텍트**

#### 1. 세부사항에 대한 결정을 가능한 오래 미룬다.

> _좋은 아키텍트는 세부사항에 대한 결정을 가능한 한 오랫동안 미룰 수 있는 방향으로 정책을 설계한다._

: 심지어 프레임워크까지도. 오히려 결정되지 않은 사항의 수를 최대화하여 프로젝트의 유연성을 높이는 것. 3rd party libs들도 이와 같은 관점에서 비용(시간, 금전)을 따졌을 때 미룰 수 있다면 최대한 미루는 방향이 코드의 유연성을 가져갈 수 있지 않을까. 물론 비용 중 어느 하나라도 포기할 수 없다면 유연하게 적용하는 게 맞고.
<br /><br />

#### 2. 작성한 코드가 진짜 중복일까? 혹은 우발적 중복일까?

> _중복에도 종류가 있다. 그중 하나는 진짜 중복이다. 이 경우 한 인스턴스가 변경되면 동일한 변경을 그 인스턴스의 모든 복사본에 반드시 적용해야 한다. 또 다른 중복은 거짓된 또는 우발적인 중복이다. 중복으로 보이는 두 코드 영역이 각자의 경로로 발전한다면, 즉 서로 다른 속도와 다른 이유로 변경된다면 진짜 중복이 아니다._

: 유스케이스의 화면 구조가 매우 비슷해서 코드를 통합하고 싶은 유혹에 빠질 때가 많지만, 해당 케이스 자체가 다른 유스케이스로 분리되는 상황이라면 시간이 지나면서 두 화면은 다르게 분기하고 변화할 것이다. 비슷한 뷰, 비슷한 알고리즘, 심지어 비슷한 DB스키마를 가져도 '자동반사적'으로 중복을 제거해버리면 나중에 이 둘을 분리해내느라 힘들 것.
<br /><br /><hr>

### **아키텍처의 테마**

> _여러분의 애플리케이션 아키텍처는 뭐라고 소리치는가? 상위 수준의 디렉터리 구조, 최상위 패키지에 담긴 소스 파일을 볼 때, 이 아키텍처는 "헬스 케어 시스템이야." 또는 "재고 관리 시스템이야." 라고 소리치는가? 아니면 "레일즈", "스프링/하이버네이트" 혹은 "ASP"라고 소리치는가?_

- 아키텍처는 유스케이스를 지원하는 구조여야만 한다. 아키텍처는 프레임워크에 대한 것이 아니고, 그래서도 안 된다.
- 아키텍처를 프레임워크로부터 제공받아서는 안됨. 단일적인 유스케이스가 엔티티(핵심적이거나 순수한 규칙들)를 조작하는, 즉 저수준이 고수준을 참조하도록 설계할 수 없게 만든다.

> _헬스 케어 시스템을 구축하고 있다면 새로 들어온 프로그래머가 소스 저장소를 봤을 때 첫 인상은 "헬스 케어 시스템이구나"이어야만 한다. 시스템이 어떻게 전달될지 알지 못한 상태에서도 시스템의 모든 유스케이스를 이해할 수 있어야 한다._

- 아키텍처의 관점에서 극대화하여 말하면, 아키텍처의 시작점은 그 시스템이 어떠한지만 보여주면 되는 것. 적용한 프레임워크가 무엇이고 어떤 기술을 썼는지와 무관함. 그 목적성 외에는 모든 사항이 세부사항임.
