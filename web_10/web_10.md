# Web 10



## JavaScript 02



### 변수와 식별자

- 식별자(identifier)

  - 대소문자를 구분하며, 클래스명 외에는 모두 소문자로 시작
  - 반드시 문자, 달러($), 밑줄(_)로 시작
  - 예약어는 사용 불가능

- 선언

  - `var` : 변수를 선언. 추가로 동시에 값을 초기화
    - 재할당, 재선언 모두 가능
    - 호이스팅에 의해 문제 발생이 가능하므로 const와 let을 사용하는 것을 권장

  - `let` : 블록 스코프 지역 변수를 선언. 추가로 동시에 값을 초기화
    - 재할당은 가능하지만, 재선언 불가능

  - `const` : 블록 스코프 읽기 전용 상수를 선언
    - 재할당, 재선언 모두 불가능

| 키워드 | 재선언 | 재할당 | 스코프      |
| ------ | ------ | ------ | ----------- |
| let    | X      | O      | 블록 스코프 |
| const  | X      | X      | 블록 스코프 |
| var    | O      | O      | 함수 스코프 |

- 호이스팅(hoisting)
  - 변수를 선언 이전에 참조할 수 있는 특성
  - 변수 선언 이전의 위치에서 접근 시 undefined 반환



### 데이터 타입

- 원시 타입(primitive type)
  - `Number` : 정수, 실수 구분 없는 하나의 숫자 타입으로 부동소수점 형식을 따름
  - `String` : 텍스트 데이터를 나타내는 타입으로, 작은따옴표 또는 큰따옴표 모두 가능
  - `Boolean` : 논리적 참 또는 거짓을 나타내는 타입으로, true 또는 false로 표현
  - `undefined` : 변수의 값이 없음을 나타내는 데이터 타입으로, 값을 할당하지 않으면 자동으로 undefined가 할당됨
  - `null` : 변수의 값이 없음을 의도적으로 표현할 때 사용하는 데이터 타입
  - `Symbol`


- 참조 타입(reference type)
  - Objects
    - `Array` 
    - `Function` 
    - ....etc



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



### 조건문

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
- `label` : loop를 식별하기 위해 label을 사용해서 식별자 제공
- `break` : 반복문, switch문, label문 등을 빠져나올 때 사용
  - `break;` : 가장 가까운 반복문 종료하고 넘어감
  - `break [label];` : 특정 label문에서 끝남
- `continue` : 다시 조건으로 이동해서 loop 진행을 계속함
  - `continue;` : 조건 판별로 이동한 후 계속 진행
  - `continue [label];` :  특정 label에 적용



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

- `for-in` : 주로 객체(object)의 속성들을 순회할 때 사용 

- `for-of` : 반복 가능한 객체(Array, Map, Set, String 등)를 순회하며 값을 꺼낼 때 사용

```js
// array
const fruits = ['딸기', '바나나', '멜론']
// for-in
for (let fruit in fruits) {
    console.log(fruit) // 0, 1, 2
}
// for-of
for (let fruit of fruits) {
    console.log(fruit) // 딸기, 바나나, 멜론
}

// object
const capitals = {
    Korea: '서울',
    France: '파리',
    USA: '워싱턴 D.C.'
}
// for-in
for (let capital in capitals) {
    console.log(capital) // Korea, France, USA
}
// for-of
for (let capital of capitals) {
    console.log(capital) // Error
}
```



### 함수

- 함수 정의

  - 함수 선언식(declaration)

  ```js
  function 함수이름(매개변수) {
      함수정의
  }
  ```

  - 함수 표현식(expression)

  ```js
  var 함수이름 = function(매개변수) { 
      함수정의 
  }
  ```

- 함수 호출

  ```js
  함수이름(전달인자);
  // func(5);
  ```

|        | 함수 선언식 declaration       | 함수 표현식 expression      |
| ------ | ----------------------------- | --------------------------- |
| 공통점 | 데이터 타입, 함수 구성 요소   | 데이터 타입, 함수 구성 요소 |
| 차이점 | 익명 함수 불가능 / 호이스팅 O | 익명 함수 가능 / 호이스팅 X |



### 화살표 함수

- 화살표 함수(Arrow Function) : 함수를 비교적 간결하게 정의할 수 있는 문법
  - function 키워드 생략 가능
  - 함수의 매개변수가 단 하나 뿐이라면 '( )'도 생략 가능
  - 함수 몸통이 표현식 하나라면 '{ }'과 return도 생략 가능

```js
const arrow1 = function (name) {
	return `hello, ${name}`
}

// 1. function 키워드 삭제
const arrow2 = (name) => { return `hello, ${name}` }

// 2. 매개변수가 1개일 경우에만 ( ) 생략 가능
const arrow3 = name => { return `hello, ${name}` }

// 3. 함수 바디가 return을 포함한 표현식 1개일 경우에 { } & return 삭제가능
const arrow4 = name => `hello, ${name}`
```



### 문자열

- `includes` : 특정 문자열의 존재여부를 참/거짓으로 반환
  - string.includes(value)

```js
const str = 'a santa at nasa’
// value 존재여부 반환
str.includes('santa') // true
str.includes('asan') // false
```

- `split` : 문자열을 토큰 기준으로 나눈 배열 반환
  - string.split(value)

```js
const str = 'a cup’
// value가 없을 경우, 기존 문자열을 배열에 담아 반환
str.split() // ['a cup’]
// value가 빈 문자열일 경우, 각 문자로 나눈 배열 반환
str.split('') // ['a', ' ', 'c', 'u', 'p']
// value가 기타 문자열일 경우, 해당 문자열로 나눈 배열을 반환
str.split(' ') // ['a', 'cup']
```

- `replace` : 해당 문자열을 대상 문자열로 교체하여 반환
  - string.replace(from, to)
  - string.repalceAll(from, to)

```js
const str = 'a b c d'
// 문자열에 from 값이 존재할 경우, 1개만 to 값으로 교체하여 반환
str.replace(' ', '-') // 'a-b c d'
// 문자열에 from 값이 존재할 경우, 모두 to 값으로 교체하여 반환
str.replaceAll(' ', '-') // 'a-b-c-d'
```

- `trim` : 문자열의 좌우 공백 제거하여 반환
  - string.trim()
  - string.trimStart()
  - string.trimEnd()

```js
const str = ' hello '
// 문자열 시작과 끝의 모든 공백문자(스페이스, 탭, 엔터 등)를 제거한 문자열 반환
str.trim() // 'hello'
// 문자열 시작의 공백문자(스페이스, 탭, 엔터 등)를 제거한 문자열 반환
str.trimStart() // 'hello '
// 문자열 끝의 공백문자(스페이스, 탭, 엔터 등)를 제거한 문자열 반환
str.trimEnd() // ' hello'
```

- `forEach` : 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행하며, 반환 값 없음
  - array.forEach(callback(element[, index[,array]]))

```js
const fruits = ['딸기', '수박', '사과', '체리']
// 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
fruits.forEach((fruit, index) => {
	console.log(fruit, index)
	// 딸기 0
	// 수박 1
	// 사과 2
	// 체리 3
})
```

- `map` : 콜백 함수의 반환 값을 요소로 하는 새로운 배열 반환
  - array.map(callback(element[, index[, array]]))

```js
const numbers = [1, 2, 3, 4, 5]
// 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
cost doubleNums = numbers.map((num) => {
    return num * 2
})
console.log(doubleNums) // [2, 4, 6, 8, 10]
```

- `filter` : 콜백 함수의 반환 값이 참인 요소들만 모아서 새로운 배열을 반환
  - array.filter(callback(element[, index[, array]]))

```js
const numbers = [1, 2, 3, 4, 5]
// 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
// 콜백 함수의 반환 값이 참인 요소만 모아서 새로운 배열 반환
cost oddNums = numbers.filter((num, index) => {
    return num % 2
})
console.log(oddNums) // 1, 3, 5
```

- `reduce` : 콜백 함수의 반환 값들을 하나의 값(acc)에 누적 후 반환
  - array.reduce(callback(acc, element, [index[, array]])[, initialValue])

```js
const numbers = [1, 2, 3]
// 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
// 콜백 함수의 반환 값들을 하나의 값(acc)에 누적 후 반환
const result = numbers.reduce((acc, num) => {
    return acc + num
}, 0)
console.log(result) // 6
```

- `find` : 콜백 함수의 반환 값이 참이면 해당 요소를 반환, 없으면 undefined 반환
  - array.find(callback(element[, index[, array]]))

```js
const avengers = [
    { name: 'Tony Stark', age: 45 },
    { name: 'Steve Rogers', age: 32 },
    { name: 'Thor', age: 40 },
]
// 배열의 각 요소에 대해 콜백 함수를 한 번씩 실행
// 콜백 함수의 반환 값이 참이면, 조건을 만족하는 첫 번째 요소를 반환
const result = avengers.find((avenger) => {
    return avenger.name === 'Tony Stark'
})
console.log(result) // {name: "Tony Stark", age: 45}
```

- `some` : 배열의 요소 중 하나라도 판별 함수를 통과하면 참을 반환
  - array.some(callback(element[, index[, array]]))

```js
const numbers = [1, 3, 5, 7, 9]
// 배열의 요소 중 하나라도 주어진 판별 함수를 통과하면 참을 반환 
const hasOddNumber = numbers.some((num) => {
    return num % 2
})
console.log(hasOddNumber) // true
// 모든 요소가 통과하지 못하거나, 빈 배열은 거짓 반환
const hasEvenNumber = numbers.some((num) => {
    return num % 2 === 0
})
console.log(hasEvenNumber) // false
```

- `every` : 배열의 모든 요소가 판별 함수를 통과하면 참을 반환
  - array.every(callback(element[, index[, array]]))

```js
const numbers = [2, 4, 6, 8, 10]
// 배열의 모든 요소가 주어진 판별 함수를 통과하거나, 빈 배열은 참을 반환
const isEveryNumberEven = numbers.every((num) => {
    return num % 2 === 0
})
console.log(isEveryNumberEven) // true
// 하나도 통과하지 못하면 거짓 반환
const isEveryNumberOdd = numbers.every((num) => {
    return num % 2
})
console.log(isEveryNumberOdd) // false
```



### 배열

- `배열(Arrays)` : 키와 속성들을 담고 있는 참조 타입의 객체(Object)
  - 순서를 보장하는 특징이 있음
  - 주로 대괄호를 이용하여 생성하고, 0을 포함한 양의 정수 인덱스로 특정 값에 접근 가능
  - 배열의 길이는 `array.length` 형태로 접근 가능

```js
const numbers = [1, 2, 3, 4, 5]
// 0과 양의 정수 인덱스로 특정 값에 접근 가능
console.log(numbers[0]) // 1
console.log(numbers[-1]) // undefined
// numbers.length로 배열의 길이 반환
console.log(numbers.length) // 5
// numbers.length - 1로 마지막 원소 접근 가능
console.log(numbers[numbers.length - 1]) // 5
```

- `reverse` :  원본 배열의 요소들의 순서를 반대로 정렬
  - array.reverse()

```js
const numbers = [1, 2, 3, 4, 5]
numbers.reverse()
console.log(numbers) // [5, 4, 3, 2, 1]
```

- `push` & `pop` : 배열의 가장 뒤에 요소를 추가 또는 제거
  - array.push()
  - array.pop()

```js
const numbers = [1, 2, 3, 4, 5]
// 배열의 가장 뒤에 요소 추가
numbers.push(100)
console.log(numbers) // [1, 2, 3, 4, 5, 100]
// 배열의 마지막 요소 제거
numbers.pop()
console.log(numbers) // [1, 2, 3, 4, 5]
```

- `unshift` & `shift` : 배열의 가장 앞에 요소를 추가 또는 제거
  - array.unshift()
  - array.shift()

```js
const numbers = [1, 2, 3, 4, 5]
// 배열의 가장 앞에 요소 추가
numbers.unshift(100)
console.log(numbers) // [100, 1, 2, 3, 4, 5]
// 배열의 첫 번째 요소 제거
numbers.shift()
console.log(numbers) // [1, 2, 3, 4, 5]
```

- `includes` : 배열에 특정 값이 존재하는지 판별 후 참/거짓 반환
  - array.includes(value)

```js
const numbers = [1, 2, 3, 4, 5]
console.log(numbers.includes(1)) // true
console.log(numbers.includes(100)) // false
```

- `indexOf` : 배열에 특정 값이 존재하는지 판별 후 인덱스 반환, 없을 경우 -1 반환
  - array.indexOf(value)

```js
const numbers = [1, 2, 3, 4, 5]
let result
// 특정 값이 존재하는지 확인 후 가장 첫 번째로 찾은 요소의 인덱스 반환
result = numbers.indexOf(3) // 2
console.log(result)
// 해당 값이 없을 경우 -1 반환
result = numbers.indexOf(100) // -1
console.log(result)
```

- `join` : 배열의 모든 요소를 구분자를 이용하여 연결, 구분자 생략 시 쉼표 기준
  - array.join([separator])

```js
const numbers = [1, 2, 3, 4, 5]
let result
// 구분자 생략 시 쉼표 기준으로 연결
result = numbers.join() // 1,2,3,4,5
console.log(result)
// 공백 없이 연결
result = numbers.join('') // 12345
console.log(result)
// 공백으로 구분해서 연결
result = numbers.join(' ') // 1 2 3 4 5
console.log(result)
// '-'로 구분해서 연결
result = numbers.join('-') // 1-2-3-4-5
console.log(result)
```



### 객체

- `객체(Objects)` : 속성(property)의 집합이며, 중괄호 내부에 key와 value의 쌍으로 표현
  - key는 문자열 타입만 가능
  - value는 모든 타입(함수 포함) 가능
  - 객체 요소 접근은 점 또는 대괄호로 가능

```js
const me = {
	name: 'jack',
	phoneNumber: '01012345678',
	'samsung products': {
		buds: 'Galaxy Buds pro',
		galaxy: 'Galaxy s20’,
	},
}
// 객체 요소접근은 점 또는 대괄호 사용
console.log(me.name)
console.log(me.phoneNumber)
console.log(me['samsung products'])
console.log(me['samsung products'].buds)
```

- `메서드` : 객체의 속성이 참조하는 함수
  - `객체.메서드명()`으로 호출 가능
  - 메서드 내부에서는 this 키워드가 객체를 의미

```js
const me = {
	firstName: 'John',
	lastName: 'Doe’,
	getFullName: function () {
		return this.firstName + this.lastName
	}
}
```

