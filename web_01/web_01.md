# Web

웹 사이트의 구성 요소

- `HTML` :구조
- `CSS` : 표현
- `Javascript` : 동작



## HTML(Hyper Text Markup Language)

- 참조(HyperLink)를 통해 사용자가 한 문서에서 다른 문서로 즉시 접근할 수 있는 텍스트
- 웸 페이지를 작성(구조화)하기 위한 언어
- HTML파일 : `.html`



### HTML 기본 구조

- `html` : 문서의 최상위(root) 요소

- `head` : 문서 메타데이터 요소
  - 문서 제목, 인코딩, 스타일, 외부 파일 로딩 등 일반적으로 브라우저에 나타나지 않는 내용
    - `<title>` : 브라우저 상단 타이틀
    - `<meta>` : 문서 레벨 메타데이터 요소
    - `<link>` : 외부 리소스 연결 요소 (CSS 파일, favicon 등)
    - `<script>` : 스크립트 요소 (JavaScript 파일/코드)
    - `<style>` : CSS 직접 작성

- `body` : 문서 본문 내용
  - 실제 화면 구성과 관련된 내용


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>web_01</title>
  </head>
  <body>
    hello world
  </body>
</html>
```



#### HTML 요소(elements)

- `요소`는 `태그`를 사용해서 문서의 다른 텍스트와 구분
  - 태그는 `<`, `태그이름`, `>`로 구성
  - 태그 이름은 대소문자를 구분하지 않으므로, 대문자, 소문자, 또는 섞어서 작성 가능
- 요소는 `시작 태그`, `종료 태그` 그리고 태그 사이에 위치한 `컨텐츠(내용)`으로 구성
  - `시작 태그` : <태그이름>
  - `종료 태그` : </태그이름>
  - 요소는 태그로 `컨텐츠(내용)`를 감싸는 것으로 그 정보의 성격과 의미를 정의
  - 내용이 없는 태그들도 존재(empty elements)하며, 종료 태그가 없음
- 요소는 중첩될 수 있음
  - 중첩을 통해 하나의 문서를 구조화
  - 여는 태그와 닫는 태그의 쌍을 잘 확인해야 함



#### HTML 속성(attribute)

- `속성`을 통해 태그의 부가적인 정보를 설정할 수 있음
- 요소는 속성을 가질 수 있으며, 경로나 크기와 같은 추가적인 정보를 제공
- 요소의 시작 태그에 작성하며 보통 이름과 값이 하나의 쌍으로 존재
  - <태그이름 속성명="속성값"></태그이름>
  - 속성은 `공백 없이` 작성하고, 속성값은 `쌍따옴표` 사용
- 태그별로 사용할 수 있는 속성이 다름
  - 태그와 상관없이 사용 가능한 속성(HTML Global Attribute)들도 있음
  - `id` : 문서 전체에서 유일한 고유 식별자 지정
  - `class` : 공백으로 구분된 해당 요소의 클래스의 목록 (CSS, JS에서 요소를 선택하거나 접근)
  - `data-*` : 페이지에 개인 사용자 정의 데이터를 저장하기 위해 사용
  - `style` : inline 스타일
  - `title` : 요소에 대한 추가 정보 지정
  - `tabindex` : 요소의 탭 순서



### HTML 나타내기

#### 제목 요소

- `<h1>` - `<h6>` : 제목 또는 하위 제목을 여섯 단계로 표현 가능

```html
<h1>main title</h1>
<h2>top level heading</h2>
<h3>subheading</h3>
<h4>sub-subheading</h4>
```

#### 링크 요소

- `<a>` : `href` 속성을 활용하여 다른 URL로 연결하는 `하이퍼링크` 생성

```html
<a href="URL">대체 텍스트</a>
```

#### 이미지 요소

- `<img>` :  `src` 속성을 활용하여 이미지 표현, `alt` 속성을 활용하여 대체 텍스트

```html
<img src="이미지 파일 경로" alt="대체 텍스트">
```

#### 문단 / 줄바꿈 요소

- `<p>` : 블록 레벨 요소로 하나의 문단 표현 가능
- `<br>` : 텍스트 내 줄 바꿈 생성 

```html
<p>apple banana apple banana apple banana apple banana apple banana apple banana apple banana apple banana apple banana</p>
<p>apple <br> banana</p>
```

#### 글씨 요소

- `<b>` : 굵은 글씨 요소
- `<strong>` : 중요한 강조하고자 하는 요소(굵은 글씨)
- `<i>` : 기울임 글씨 요소
- `<em>` : 중요한 강조하고자 하는 요소(기울임 글씨)

```html
I like <b>apple</b>.<br>
I love <strong>apple</strong>.<br>
I dislike <i>banana</i>.<br>
I hate <em>banana</em>.<br>
```

#### 목록 요소

- `<ul>` : 순서 없는 목록
- `<ol>` : 순서 있는 목록
- `<li>` : 목록의 각 항목 요소

```html
<ul>
    <li>apple</li>
    <li>banana</li>
    <li>cherry</li>
    <li>mango</li>
</ul>

<ol>
    <li>small</li>
    <li>middle</li>
    <li>large</li>
</ol>
```



## CSS(Cascading Style Sheets)

- 문서에 있는 요소들에 선택적으로 스타일을 적용할 수 있는 스타일 시트 언어
- 각각의 rule set은 반드시 `{}` 중괄호로 감싸져야 함
- 각각의 선언 안에, 각 속성을 해당 값과 구분하기 위해 `:` 콜론을 사용해야 함
- 각각의 rule set 안에, 각 선언을 다음 선언으로부터 구분하기 위해 `;`세미콜론을 사용해야 함
- `인라인`, `내부참조`, `외부참조`를 통해 CSS 정의 가능



### CSS 구문 구조(rule set)

- `선택자(selector)` : 스타일을 지정할 HTML 요소 선택
- `선언(declaration)` : 요소의 스타일 속성을 명시
- `속성(property)` : 어떤 스타일 기능을 변경할지 결정
- `값(value)` : 어떻게 스타일 기능을 변경할지 결정

```html
선택자 {
  속성1: 값1; <!--선언1-->
  속성2: 값2; <!--선언2-->
}
```



### CSS 정의 방법

#### 인라인(inline)

- `해당 태그`에 직접 style 속성을 활용

```html
<!DOCTYPE html>
<html>
  <head>
    ...
  </head>
  <body>
    <!--해당 태그 직접 지정-->
    <h1 style="color: blue; font-size: 100px;">
      Hello
	</h1>
  </body>
</html>
```

#### 내부 참조(embedding)

- `<head>` 태그 내, `<style>`에 지정

```html
<!DOCTYPE html>
<html>
  <head>
    ...
    <!--head 내 style에 지정-->
    <style>
      h1 {
        color: blue;
        font-size: 100px;
      }
    </style>
  </head>
  <body>
    <h1>Hello</h1>
  </body>
</html>
```

#### 외부 참조(link file)

- 외부 CSS 파일을 만들고, `<head>` 태그 내, `<link>`를 통해 불러오기

```css
/* 외부 CSS 파일 */
h1 {
    color: blue;
    font-size: 100px;
}
```

```html
<!DOCTYPE html>
<html>
  <head>
    ...
    <!--head 내 link로 외부 파일 불러오기-->
    <link rel="stylesheet" href="외부CSS파일.css">
  </head>
  <body>
    <h1>Hello</h1>
  </body>
</html>
```



### CSS 기초 선택자

- `요소` 선택자
  - 특정 타입의 모든 HTML 요소 중에서 태그를 직접 선택
- `클래스(class)` 선택자 
  - `.` 문자로 시작하며, 해당 클래스가 적용된 항목을 선택
- `아이디(id)` 선택자
  - `#` 문자로 시작하며, 해당 아이디가 적용된 항목을 선택
  - 일반적으로 하나의 문서에 한 번만 사용
  - 여러 번 사용해도 동작하지만, 단일 id 사용을 권장
