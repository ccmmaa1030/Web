# Web 09



## JavaScript 01

- `JavaScript`는 웹 페이지에서 복잡한 기능을 구현할 수 있도록 브라우저를 조작하는 스크립팅 언어
- DOM API를 통해 HTML과 CSS를 동적으로 수정, 사용자 인터페이스를 업데이트하는 일에 가장 많이 쓰임
- 확장자 `.js` 파일을 만들어 외부 파일로 분리할 수 있음



### DOM(Document Object Model)

- HTML, XML과 같은 `문서`를 조작하기 위한 문서 프로그래밍 인터페이스
- 문서를 구조화하고 각 요소는 객체로 취급하여 다루는 논리적 트리 모델
- 단순한 속성 접근, 메서드 활용뿐만 아니라 프로그래밍 언어적 특성을 활용한 조작 가능
- 주요 객체
  - `window` : DOM을 표현하는 창으로 가장 최상위 객체(작성 시 생략 가능)
  - `document` : 페이지 컨텐츠의 Entry Point 역할을 하며, \<body> 등과 같은 수많은 다른 요소들을 포함
  - `navigator`, `location`, `history`, `screen`

- `파싱(Parsing)` : 브라우저가 구문 분석, 해석을 통해 DOM Tree로 만드는 과정



#### DOM 조작

- DOM 조작 순서

  1. `선택(Select)` 

  2. `변경(Manipulation)` 

- DOM 객체 상속 구조

  - `EventTarget` : Event Listener를 가질 수 있는 객체가 구현하는 DOM 인터페이스
  - `Node` : 여러가지 DOM 타입들이 상속하는 인터페이스
  - `Element` : Document 안의 모든 객체가 상속하는 가장 범용적인 인터페이스로, 부모인 Node와 EventTarget의 속성을 상속
  - `Document` : 브라우저가 불러온 웹 페이지를 나타내며, DOM 트리의 진입점(entry point) 역할을 수행
  - `HTMLElement` : 모든 종류의 HTML 요소로, 부모 Element의 속성을 상속



##### DOM 선택

- 선택 관련 메서드 중에서 id, class 그리고 tag 선택자 등을 모두 사용 가능하여, 더 구체적이고 유연하게 선택 가능한 `querySelector()`, `querySelectorAll()`를 사용

- `document.querySelector(selector)`
  - 제공한 선택자와 일치하는 `element 중 첫 번째 객체`를 반환하며 없으면 null 
- `document.querySelectorAll(selector)`
  - 제공한 선택자와 일치하는 `여러 element`를 선택해서 NodeList를 반환
  -  querySelectorAll()의 반환 NodeList만 `Static Collection`



##### DOM 변경

- Creation
  - `document.createElement()` : 작성한 태그 명의 HTML 요소를 생성하여 반환
- Append
  - `Element.append()` : 특정 부모 Node의 자식 NodeList 중 마지막 자식 다음에 Node 객체나 DOMString을 삽입하는데 여러 개를 추가 할 수 있으며, 반환 값이 없음
  - `Node.appendChile()` : 한 Node를 특정 부모 Node의 자식 NodeList 중 마지막 자식으로 삽입하며 Node 객체 하나만 추가 가능하고, 추가된 Node 객체를 반환함
- Property
  - Node.innerText : Node 객체와 그 자손의 DOMString을 표현하는데, 줄 바꿈을 인식하고 숨겨진 내용을 무시하는 등 최종적으로 스타일링이 적용된 모습으로 표현
  - Element.innerHTML : element 내에 포함된 HTML 마크업을 반환
- 삭제
  - `ChildNode.remove()` : Node가 속한 트리에서 해당 Node를 제거
  - `Node.removeChild()` : DOM에서 자식 Node를 제거하고 제거된 Node를 반환
- 속성
  - `Element.setAttribute(name, value)` : 지정된 요소의 값을 설정하는데, 속성이 이미 존재하면 갱신하고, 존재하지 않으면 지정된 이름과 값으로 새 속성을 추가
  - `Element.getAttribute(attributeName)` : 해당 요소의 지정된 값(문자열)을 반환



### 문법과 자료형

- 기본
  - 대소문자를 구별하며 유니코드 문자셋 이용
  - 한 줄에 하나의 명령문이라면 세미콜론(;)이 필요하지 않지만, 한 줄에 두 개 이상의 명령문이 사용될 경우 반드시 구분해야 함
    - 필요하지 않더라도 항상 세미콜론으로 끝마치는 습관
  - 일반적으로 위에서 아래, 왼쪽에서 오른쪽으로 탐색하면서 실행
  - 스페이스, 탭, 줄바꿈 문자는 공백으로 간주
- 주석

``` js
// 한 줄 주석

/* 여러 줄
 * 주석
 */
```

- 선언
  - `var` : 변수를 선언. 추가로 동시에 값을 초기화
  - `let` : 블록 스코프 지역 변수를 선언. 추가로 동시에 값을 초기화
  - `const` : 블록 스코프 읽기 전용 상수를 선언, 재선언 불가능
  - 식별자 규칙 : 문자, 언더바(_) 혹은 달러($)로 시작해야 하고, 맨 앞에 숫자가 올 수 없음
  - `변수 호이스팅` : 나중에 선언된 변수를 참조 할 수 있음
- 자료형
  - `Boolean`, `null`, `undefined`, `Number`, `BigInt`, `String`, `Symbol`, `Object`



### 제어문

- `블록문` : 가장 기본적인 명령문으로, 명령문들을 한 쌍의 중괄호를 이용해서 그룹으로 묶어 나타냄
  - `if`, `for`, `while` 같은 제어 흐름 명령문과 많이 사용됨 

- `조건문` : 지정한 조건이 참인 경우에 실행하는 명령 집합
  - `if-else`, `switch` 두 종류의 조건문을 지원

```js
if ([조건문]) {
    [명령문];
} else if ([조건문]) {
    [명령문];
} else {
    [명령문];
}
```

```js
switch ([표현식]) {
    case label_1:
        [명령문];
        break;
    case label_2:
        [명령문];
        break;
    default:
        [명령문];
}
```

- 예외 처리 명령문 : `throw`, `try-catch`



### 반복문

- `for` : 어떤 특정한 조건이 거짓으로 판별될 때까지 반복

```js
for ([초기문]; [조건문]; [증감문];) {
    [명령문];
}
```

- `do-while` : 특정한 조건이 거짓으로 판별될 때까지 반복하고, 명령문이 한번은 무조건 실행되며 매 실행 마지막마다 조건문 확인

```js
do {
    [명령문];
} while ([조건문]);
```

- `while` : 조건문이 참이면 명령문을 계속 실행

```js
while ([조건문]) {
    [명령문];
}
```

- `label` : loop를 식별하기 위해 label을 사용해서 식별자 제공
- `break` : 반복문, switch문, label문 등을 빠져나올 때 사용
  - `break;` : 가장 가까운 반복문 종료하고 넘어감
  - `break [label];` : 특정 label문에서 끝남
- `continue` : 다시 조건으로 이동해서 loop 진행을 계속함
  - `continue;` : 조건 판별로 이동한 후 계속 진행
  - `continue [label];` :  특정 label에 적용

- `for-in`, `for-of`



### 함수

- 함수 정의

  - 함수 선언

  ```js
  function 함수이름(매개변수) {
      함수정의
  }
  ```

  - 함수 표현식

  ```js
  var 함수이름 = function(매개변수) { 함수정의 };
  ```

- 함수 호출

  ```js
  함수이름(전달인자);
  // func(5);
  ```

  

### 연산자

- 할당 연산자

| 이름                         | 단축 연산자 | 뜻             |
| ---------------------------- | ----------- | -------------- |
| 할당                         | x = y       | x = y          |
| 더하기 할당                  | x += y      | x = x + y      |
| 빼기 할당                    | x -= y      | x = x - y      |
| 곱하기 할당                  | x *= y      | x = x * y      |
| 나누기 할당                  | x /= y      | x = x / y      |
| 나머지 할당                  | x %= y      | x = x % y      |
| 거듭제곱 할당                | x **= y     | x = x ** y     |
| 왼쪽 시프트 할당             | x <<= y     | x = x << y     |
| 오른쪽 시프트 할당           | x >>= y     | x = x >> y     |
| 부호 없는 오른쪽 시프트 할당 | x >>>= y    | x = x >>> y    |
| 비트 AND 할당                | x &= y      | x = x & y      |
| 비트 XOR 할당                | x ^= y      | x = x ^ y      |
| 비트 OR 할당                 | x \|= y     | x = x \| y     |
| 논리 AND 할당                | x && y      | x && (x = y)   |
| 논리 OR 할당                 | x \|\|= y   | x \|\| (x = y) |
| 널 병합 할당                 | x ??= y     | x ?? (x = y)   |

- 비교 연산자

| 연산자         | 설명                                               |
| -------------- | -------------------------------------------------- |
| 동등 ==        | 피연산자가 서로 같으면 true 반환                   |
| 부등 !=        | 피연산자가 서로 다르면 true 반환                   |
| 일치 ===       | 두 피연산자의 값과 타입이 모두 같으면 true 반환    |
| 불일치 !==     | 피연산자의 값 또는 타입이 서로 다를 경우 true 반환 |
| 크다 >         | 왼쪽이 오른쪽보다 크면 true 반환                   |
| 크거나 같다 >= | 왼쪽이 오른쪽과 같거나 더 크면 true 반환           |
| 작다 <         | 왼쪽이 오른쪽보다 작으면 true 반환                 |
| 작거나 같다 <= | 왼쪽이 오른쪽과 같거나 더 작으면 true 반환         |

- 산술 연산자

| 연산자        | 설명                                                         |
| ------------- | ------------------------------------------------------------ |
| 나머지 %      | 두 피연산자를 나눈 후 나머지 반환                            |
| 증가 ++       | 피연산자에 1을 더함 / 전위 연산자로 사용하면 1을 더한 값을 반환 / 후위 연산자로 사용하면 1을 더하기 전의 값을 반환 |
| 감소 --       | 피연산자에 1을 뺌 / 전위 연산자로 사용하면 1을 뺀 값을 반환 / 후위 연산자로 사용하면 1을 빼기 전의 값을 반환 |
| 단항 부정 -   | 피연산자의 부호를 반대로 바꾼 값을 반환                      |
| 단항 플러스 + | 피연산자가 숫자 타입이 아니면 숫자로 변환 시도               |
| 거듭제곱 **   | 거듭제곱한 결과 반환                                         |

- 논리 연산자

```js
var a1 = true && true;      // t && t는 true 반환
var a2 = true && false;     // t && f는 false 반환
var a3 = false && true;     // f && t는 false 반환
var a4 = false && (3 == 4); // f && f는 false 반환
var a5 = 'Cat' && 'Dog';    // t && t는 Dog 반환
var a6 = false && 'Cat';    // f && t는 false 반환
var a7 = 'Cat' && false;    // t && f는 false 반환
```

```js
var o1 = true || true;      // t || t는 true 반환
var o2 = false || true;     // f || t는 true 반환
var o3 = true || false;     // t || f는 true 반환
var o4 = false || (3 == 4); // f || f는 false 반환
var o5 = 'Cat' || 'Dog';    // t || t는 Cat 반환
var o6 = false || 'Cat';    // f || t는 Cat 반환
var o7 = 'Cat' || false;    // t || f는 Cat 반환
```

```js
var n1 = !true;  // !t는 false 반환
var n2 = !false; // !f는 true 반환
var n3 = !'Cat'; // !t는 false 반환
```

- 문자열 연산자
  - 문자열 연결(+) 연산자를 이용해서, 두 문자열을 연결한 새로운 문자열을 반환할 수 있음



