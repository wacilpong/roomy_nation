---
title: "After reading concepts of programming languages, by Robert W. Sebesta"
date: "2020-06-28"
tags: ["review"]
draft: false
og_description: "프로그래밍 언어론을 읽고 내맘대로 정리해보았다."
---

프로그래밍 언어론을 읽고 내맘대로 정리해보았다.

<br />

**[기본적인 사항]**

- 프로그래밍 언어의 어휘항목은 수치 리터럴, operator, 특수어를 포함한다.
- 프로그램은 문자보다는 어휘항목들로 구성된 문자열이라고 할 수 있다.
- [단언(assertion)](<https://en.wikipedia.org/wiki/Assertion_(software_development)>)
  - 문장 앞에 위치하면 프로그램의 그 지점에서 프로그램의 변수들에 대한 제약 사항이다.
  - 문장 뒤에 위치하면 그 문장이 실행된 후 해당 변수에 대한 새로운 제약 사항을 기술한다.
- 부프로그램(subprogram)은 전체 프로그램을 구성하는 조각이며, 함수 하나라고 생각할 수도 있을 것 같다.
- 컴퓨터 과학에서 **스칼라(scalar)** 라고 지칭할 때는, 배열이든 문자열이든 상관없이 '그것'들 중의 하나를 의미한다.
- 프로그래밍 언어는 다음 세 가지 방법으로 구현(implementation)될 수 있다.

  - #### **(1) Compiler implementation**
    - 컴퓨터에서 직접 실행될 수 있는 기계어로 번역될 수 있다.
    - 컴파일러가 번역하는 언어는 원시언어(source language)이다.
    - 컴파일 단계는 대체로 아래 순서를 거친다.
      - `원시 프로그램 -> 어휘 분석기 -> 구문 분석기 -> 중간 코드 생성기 -> 코드 생성기`
      - 컴파일러에서는 주석을 사용하지 않으므로, 어휘 분석기는 원시 프로그램에 포함된 주석을 무시한다.
      - 구문 분석기는 어휘들을 가져와 구문 구조를 표현한 **파스 트리**를 생성한다.
      - 중간 코드 생성기는 원시 프로그램과 컴파일러의 최종 출력인 기계어 프로그램 간의 중간 수준에 위치한다.
      - 코드 생성기는 프로그램의 최적화된 중간 코드 버전을 동등한 기계어 프로그램으로 변환한다.
  - #### **(2) Pure interpretation**
    - 프로그램은 어떠한 번역 과정 없이 인터프리터에 의해 해석된다.
    - 원시 수준의 디버깅 연산을 쉽게 구현할 수 있다.
    - 그러나 고급 언어 문장을 해석(decode)해야 하므로, 컴파일된 시스템보다 10배 ~ 100배 실행 시간이 느리다.
    - 문장이 몇 번 실행되는지 상관없이, 그 문장은 매번 해석되어야 한다.
  - #### **(3) Hybrid implementation system**
    - 고급 언어 프로그램을 용이한 해석이 가능하도록 설계된 중간 언어로 번역한다.
    - 따라서 원시 언어 문장을 한 번만 해석(decode)되므로 순수 해석보다 빠르다.
    - `Perl` 프로그램은 해석 전에 오류를 탐지하고 부분적으로 컴파일된다.
    - JIT(Just In Time) 방식은 프로그램을 중간 언어로 번역하고, 실행 중에 중간 언어 메소드가 호출되면 그 메소드를 기게 코드로 번역한다.

<br />
<hr />

## 변수

- 변수는 name, address, value, type, lifetime, scope로 구성된다.

- #### **이름(name)**

  - 프로그램에서 어떤 개체를 식별하기 위해 사용되는 문자열이다.
  - 특수어(special word)는 수행될 행동들을 미리 정해 놓은 것이다.
    - 대부분의 언어에서 특수어는 예약어이다.
    - 어떤 언어에서 특수어는 단지 키워드이다.
    - 키워드(keyword)는 문맥에 따라 달라질 수 있다. _ex) javascript의 this_

- #### **주소(address)**

  - 그 변수와 연관된 기계 메모리 주소이다.
  - 두 개 이상의 변수 이름이 동일한 메모리 위치를 접근하는 데 사용되면, 그 변수들은 `별칭(alias)`이다.

- #### **타입(type)**

  - 그 변수가 저장할 수 있는 값들의 범위와 타입에 따른 연산들의 집합을 결정한다.

- #### **값(value)**

  - 그 변수에 연관된 추상적인 메모리 셀, 혹은 셀들의 내용이다.

- #### **바인딩(binding)**

  - 하나의 속성과 하나의 개체 간의 연관관게이다.
    - ex) 변수와 그 타입이나 값 사이, 연산과 기호 사이 등...
    - ex) `*` 기호는 보통 언어 설계 시간에 곱셈 연산에 바인딩된다.
    - ex) C의 `int` 데이터 타입은 언어 구현 시간에 가능한 값들의 범위에 바인딩된다.
  - `정적(static) 바인딩`: 실행 시간(runtime)이 시작되기 전에 일어나고, 프로그램 실행 전체에서 변하지 않는 상태로 남아있다.
    - 변수 이름과 타입이 동시에 바인딩된다.
  - `동적(dynamic) 바인딩`: 런타임 중에 일어나거나, 프로그램 실행 과정에서 변할 수 있다.
    - 변수 이름이 타입에 일시적으로 바인딩된다.
    - 동적 타입 바인딩을 사용하는 언어는 수치 데이터를 제네릭으로 작성한다.
    - 동적 타입 바인딩은 컴파일러 오류 탐지 능력이 떨어지므로 덜 신뢰적이다.

- #### **존속기간(lifetime)**

  - 변수가 특정 메모리 위치에 바인딩되어 있는 기간이다.

  - **정적**
    : 프로그램 실행이 시작되기 전에 메모리 셀에 바인딩되어, 종료될 때까지 동일한 메모리 셀에 바인딩된다.
  - **스택-동적**
    : 선언문이 구현될 때 메모리에 바인딩되고, 타입은 정적으로 바인딩된다.
    ex) javascript의 함수 내부에 선언된 지역변수 -> 따라서 재귀 호출이 가능해진다.
  - **힙-동적**
    : 실행 시간에 할당되고 회수되는 익명의 추상 메모리 셀에 바인딩되고, 포인터나 참조 변수로 참조한다.
  - **묵시적 힙-동적**
    : 값이 할당될 때마다 변수의 모든 속성이 힙 메모리에 바인딩된다.

- #### **영역(scope)**
  - 그 변수를 참조할 수 있는 문장들의 범위이다.
  - 변수가 프로그램 단위나 블록 내부에 정의되면 지역적(local)이다.
  - `정적 영역(static scope)`
    - 변수의 영역이 실행 전에 결정될 수 있다.
    - 많은 언어에서 새로운 정적 스코프를 실행 코드 중간에 정의할 수 있다.
      - 블록(block)으로 지정된 코드에 변수가 진입할 때 메모리에 할당, 빠져나올 때 회수된다.
      - 블록에 의해 생성된 영역은 subprogram(함수)에 의해 생성된 영역과 동일하게 취급된다.
      - javascript는 중첩된 함수에 대해 정적 스코프를 사용하지만, 블록 스코프는 그렇지 않다.
      - javascript에서 지역 변수는 함수의 어느 위치에서도 선언될 수 있지만, 변수의 영역은 항상 함수 전체이다.
        - **하지만 es6에서 블록-레벨 스코프인 let과 const가 나왔다!**
    - 전역 변수의 영역은 그 선언으로부터 프로그램 끝까지이다.
    - 참고로 javascript의 전역 변수는 동일한 이름을 갖는 지역 변수를 선언한 함수에서 그 전역 변수에 접근할 방법이 없다. (shadow variable)
    - 정적 영역을 사용할 때 소프트웨어는 계속 재구조화되어야 하므로, 변수와 함수에 대한 접근을 제어하기 위해 전역 변수 등을 많이 사용하게 된다.
  - `동적 영역(dynamic scope)`
    함수들이 배치된 관계가 아니라 호출 시퀀스에 기반하며, 실행 시간에 결정된다.
    ```js
    function big() {
      function sub1() {
        var x = 7;
      }
      function sub2() {
        var y = x;
        var z = 3;
      }
      var x = 3;
    }
    ```
    - 위의 sub2에서 참조되는 식별자 x의 의미는 동적이며, 컴파일 시간에 결정될 수 없다.
    - 어떠한 지역 선언에 대한 탐색이 실패하면, 그 함수의 부모에서 탐색되고, 이 과정을 반복한다. 이때 어떠한 부모에서도 발견되지 않으면 **실행-시간 오류**이다.
    - 동적 영역은 비지역 변수에 대한 참조를 정적으로 타입 검사할 수 없다.
    - 동적 영역은 참조의 의미를 결정하기 위한 함수 호출 시퀀스를 알아야 하므로 프로프램 판독이 힘들어진다.
- _(참고)_ **이름 상수(named constant)는 단지 한 번만 컴파일 시간에 값에 바인딩되는 변수이다.**
- _(참고)_ **초기화(initialization)는 변수가 메모리에 바인딩되는 시점에 값에 대한 변수의 바인딩이다.**

<br />
<hr />

## 데이터 타입

- 데이터 값들의 모임과 그 값들에 대해 미리 정의된 연산들을 의미한다.
- 타입 시스템은 오류 탐지, 모듈 간 인터페이스 보장(cross-module), 문서화(documentation)로써 중요하다.
- 식별자를 변수로 생각할 수 있으나, 어떤 언어에서는 데이터 타입을 갖지 않으므로 변수 속성 중 하나이다.
- Numeric, Boolean, String, Enum, Array, Tuple, List, Union, Pointer, Reference

- #### **문자 스트링 타입(Character string type)**

  - 값이 일련의 문자들로 구성된다.
  - 부분 스트링 참조는 주어진 문자열에서 부분 문자열에 대한 참조이며, 배열에서 논의될 때는 slice이다.
  - Perl, Javascript, Ruby, PHP는 패턴 매칭 연산자를 포함한다. 패턴 매칭 식은 수학적 정규식에 기초하고 있어서 정규식(regular expression)이라고 부른다.
  - `정적 길이 스트링(static length string)`
    - 스트링이 생성될 때 설정된다.
    - ex) Python이나 Java의 String
  - `제한된 동적 길이 스트링(limited dynamic length string)`
    - 0부터 최대 길이까지의 임의의 문자들을 저장한다.
  - `동적 길이 스트링(dynamic length string)`
    - 최대 길이의 제한이 없는 가변 길이를 갖는다.
    - ex) Javascript, Peral, C++의 String
    - 유연하지만, 동적인 메모리 할당과 회수로 복잡한 기억공간 관리가 필요한데, 3가지 방법이 있다.
      - 연결 리스트에 저장 -> 링크에 대한 여분의 메모리가 필요하며, 스트링 연산이 복잡하다.
      - 스트링을 힙에 할당된 개개의 문자들을 가리키는 포인터들의 배열로 저장 -> 연결 리스트보다는 스트링 연산이 빠르다.
      - 스트링 전체를 인접한 메모리 셀들에 저장 -> 스트링이 늘어날 수록, 메모리 영역을 찾고 이전 셀을 회수하는 관리가 필요하다.

- #### **열거 타입(Enumeration type)**

  - 이름이 있는 상수들이 열거되어, 열거 상수(enumeration constants)들을 정의하고 그룹핑하는 타입이다.
  - 값을 할당하지 않아도 전형적으로 정수 값이 묵시적으로 할당된다.
    ```ts
    enum Hello {
      First, // 0
      Second, // 1
    }
    ```

- #### **배열 타입(Array)**

  - 동질적인 데이터 원소의 집합이며 C, C++, Java에서 배열의 모든 원소는 동일한 타입이어야 한다.
  - Javascript, Python, Ruby에서는 변수가 객체나 데이터 값에 대한 타입이 없는 참조이기 때문에, 배열의 원소들은 다른 타입들을 참조할 수 있다.
  - 배열의 첨자(subscript)는 그 배열의 값을 가리키는 값이다. _ex) A[1]에서 1_
  - Javascript 배열에서는 존재하지 않는 원소에 대해 참조하면 **undefined**를 반환한다.
  - 배열의 슬라이드(slice)는 배열의 어떤 부분 구조이며, 주어진 첨자의 범위를 갖는 원소들로 구성된 배열을 반환한다.
  - 배열 원소에 접근하는 코드는 컴파일에 생성되어야 하고, 런타임에 원소의 주소를 생성하도록 실행되어야 한다.
  - **연관 배열(associative array)** 은 key-value 구조이다.
    - key를 통해 연관되는 값을 얻을 수 있는 자료구조이다.
    - Perl, Ruby 등에서 hash, Lua에서는 table타입이이 연관 배열이다.
  - `Union type vs Intersection type`

    - 유니온 타입은 명시한 모든 타입들의 합집합이다.
      ex) const test: A | B -> test는 A 또는 B타입
    - 인터섹션 타입은 명시한 여러 타입을 하나의 단일 타입으로 결합한 일종의 교집합이다.
      ex) const test: A & B -> test는 A와 B타입 각각의 멤버를 1개 이상씩 가져야 한다.

- #### **포인터 타입(Pointer)**

  - 포인터는 동적으로 할당되는 힙 메모리의 한 위치를 접근하는 데 사용된다.
  - 이미 회수된 힙-동적 변수의 주소를 가리키는 문제가 있다. (dangling pointer)
    - 이때 힙-동적 변수를 garbage라고 부르며, 메모리 누수를 일으킨다.
    - 이러한 문제로 최근의 언어들은 포인터를 참조 타입으로 대체해, 메모리 회수 문제를 최소화한다.

- #### **참조 타입(reference type)**

  - 포인터는 메모리의 주소를 참조하지만, 참조 변수는 메모리의 객체나 값을 참조한다.
  - 객체 지향 언어인 python, ruby, lua의 모든 변수는 참조 변수이다.
  - _[포인터와 참조 타입에서 쓰레기 회수]_
    - (1) 참조 계수기(reference counter)
    - (2) 표시-수집(mark-sweep)

- 변수가 타입에 대한 바인딩이 정적이면 타입 검사도 항상 정적이며, 동적이면 런타임에서 타입 검사를 한다.
- 프로그래밍 언어는 타입 오류가 항상 탐지되면 강 타입 언어(strongly typed language)이다.

<br />
<hr />

## 식과 배정문(Expression and assignment statement)

- 식(expression)은 어떠한 단일 값으로 표현될 수 있는 코드이다.
- 문(statement)은 실행가능한 독립적인 코드 조각이다.
  - 선택문(selection statement), 반복문(iterative statement)...
  - 무조건 분기문(unconditional branch statement)은 실행 제어를 프로그램상에서 명시된 위치로 이동시킨다. 보통 루프 탈출로 사용하는데, 고급언어에서는 많이 사용하지 않는다.
    ```batch
      :test
      echo "hi"
      goto test
      ...
    ```
- 많은 오류가 식 평가 과정에서 발생한다.
  - 가장 공통된 오류는 연산의 결과가 저장되어야 하는 메모리 셀에 표현될 수 없을 때 발생한다.
  - ex) 그 결과가 너무 큰지 작은지에 따라 오버플로(overflow), 언더플로(underflow)이다.
  - 소수점의 오버플로, 언더플로, 0에 의한 나누기는 런타임 오류이다.
  - 런타임에서의 오류를 **예외(exceptions)** 라고도 부른다. _에러(error)와 다르다!_
- 할당문은 변수(상태)의 값을 변경하는 부수 효과(side effect)를 야기한다.
  - **함수에서의 사이드 이펙트는 함수가 자신의 매개변수들 중 하나 혹은 전역 변수를 변경할 때 발생한다.**
  - 프로그램에서 동일한 값을 갖는 임의의 두 식이 프로그램 동작에 영향을 미치지 않으면서 임의의 위치에서 서로 다른 식으로 대체될 수 있다면, 그 프로그램은 referential transparet하다.
    ```js
    result1 = (fun(a) + b) / (fun(a) - c);
    temp = fun(a);
    result2 = (temp + b) / (temp - c);
    ```
    위 코드에서 함수 fun이 사이드 이펙트가 없다면 result1과 result2는 동일해야 한다.
- 타입 강제 변환은 컴파일러가 수행하는 묵시적 타입 변환(implicit type conversion)이다.
  - 명시적인 타입 변환은 명시적 타입 변환(Explicit Type Conversion) 또는 캐스트(cast)이다.

<br />
<hr />

## 부프로그램(Subprogram)

- **overloaded subprogram은 동일한 참조 환경에서 다른 이름을 갖는다.**
  ```ts
  function test(a: number);
  function test(a: boolean);
  function test(a) {
    return a;
  }

  test(1);
  test(true);
  test("1");  // No overload matches this call
  ```
- **generic subprogram은 호출할 떄마다 다른 타입의 데이터에 게산을 수행한다.**
  ```ts
  function test<T>(a: T) {
    return a;
  }

  test<number>(1);
  test<boolean>(1);   // type error
  ```
- 부프로그램의 header는 헤더 다음에 오는 구문이 어떤 종류(특히 프로시저, 함수)인지 명시한다.
- 간접적으로 부프로그램을 호출하는 일반적인 에시는 `콜백(callback)`이다.
- 부프로그램의 형식 부분인 배치(layout)를 활성화 레코드(activation record)라고 하며, 정적 바인딩 된다.
- 일단 **Javascript에서의 부프로그램은 함수라고 볼 수 있으므로, 함수라고 지칭하려고 한다.**
- 함수는 구조적으로 프로시저를 닮았지만 의미적으로는 수학 함수가 모델이다.
- 함수는 새로운 사용자 정의 연산자를 정의한다. 예를 들어, 어떤 언어에 지수 연산자가 없다면 이 연산을 할 수 있는 함수를 작성할 수 있다. 아래 result의 결과는 동일하다. 
  ```c++
  // c++
  float power(float base, float exp) {
    float result = 1;

    while (exp != 0) {
      result *= base;
      --exp;
    }

    return 0;
  }

  result = 3.4 * power(10.0, x)
  result = 3.4 * 10.0 ** x
  ```

- #### **매개변수**

  - 매개변수로 전달된 데이터는 함수의 지역 변수로 접근된다.
  - 접근하는 데이터가 비지역 변수라면 함수의 호출 사이에 그 비지역 변수에 새로운 값을 할당해야 한다.
    -> side effect!
  - 메소드는 비지역 참조와 매개변수를 통해 외부 데이터에 접근한다.
    -> side effect!
    - 메소드가 처리하는 데이터는 메소드가 호출된 객체이다.
    - _ex) javascript의 객체 내부에 선언된 함수를 호출_
  - Haskell과 같은 순수 함수형 프로그래밍 언어는 변화할 수 있는 데이터를 갖지 않는다.
    - 따라서 어떤 방법으로든 메모리를 변화시킬 수 없다.
    - 단순히 계산을 하고 결과 값(또는 함수, 함수도 값이다)을 반환한다.
  - `parameter: 부프로그램 헤더에 명시된 매개변수`
  - `argument: 부프로그램을 호출할 때 그 파라미터에 바인딩되는 매개변수, 인수`
    - parameter는 디폴트 값을 갖는다.
    - _ex) function test(a, b = 1)_

- #### **지역 참조 환경**

  - 지역 변수는 함수 내부에 정의되고, 스코프가 함수의 본문에 제한된다.
  - 지역 변수가 스택-동적이면 함수가 실행될 떄 메모리에 바인딩되고 끝날 때 해제된다.
    - 재귀 함수의 지역 변수는 스택-동적이어야만 한다.
    - 스택-동적 지역 변수에 대한 접근은 간접 주소 방식이다.
    - 지역 변수가 스택의 어디에 위치할지 런타임에서만 결정할 수 있기 때문이다.
    - 대부분의 현대 언어에서 함수의 지역 변수는 디폴트로 스택-동적이다.

- #### **함수**
  - 대부분의 언어에서 함수는 값을 전달하거나 참조 전달되는 매개변수를 갖는다.
    -> side effect, alias 발생
  - 특정 언어에서 부프로그램은 일급 객체이다.
    - 매개변수로 전달될 수 있고, 함수로부터 반환될 수 있고, 변수에 배정될 수 있다.
    - _ex) javascript의 function_
  - **클로저(closure)는 중첩된 부프로그램의 참조 환경이다.**
    - 부프로그램이 프로그램의 임의의 위치에서 호출되는 것을 허용한다.
    - 따라서 이때 변수의 존속기간은 정의된 함수가 아니라 전체 프로그램의 활성화 기간이다.
    - 거의 모든 함수형 프로그래밍 언어는 클로저를 지원한다.
    - 이 언어들은 **정적 스코프이며, 중첩 함수를 허용하고, 함수가 매개변수로 전달될 수 있다.**
    - 아래 예시에서 makeAdder가 호출될 때 생성되는 x의 존속기간은 프로그램 존속기간이 된다.
      ```js
      function makeAdder(x) {
        return function(y){
          return x + y;
        }
      }

      var add10 = makeAdder(10);

      document.write(add10(20));
      ```
  
- #### **코루틴**
  - 코루틴은 특별한 종류의 부프로그램이다.
  - 코루틴의 시작은 호출(call)이라기보다는 리쥼(resume)이라고 불린다.
  - 부프로그램의 특징처럼, 코루틴도 주어진 시점에서는 하나의 코루틴만 실제로 실행된다.
    - 모든 코루틴이 구성되었을 때 마스터 프로그램은 하나를 리쥼한다.
    - 나머지 코루틴들은 작업이 끝날 때까지 어떠한 순서로 서로서로 리쥼한다.
    - 코루틴 실행이 코드 끝부분에 도착하면 제어는 이 코루틴을 생성한 마스터로 전달되어 끝난다.
    - 따라서 코루틴은 병렬로 실행하는 것처럼 보인다.
  - _ex) javascript의 generator와 async/await_

<br />
<hr />
(ing...)
책의 챕터 순서와 다르게 아래 순서로 정리할 예정

1. 동시성
2. 예외 처리와 이벤트 처리
3. 객체 지향 프로그래밍 (+ 추상 데이터 타입과 캡슐화 구조)
4. 함수형 프로그래밍
5. 논리형 프로그래밍