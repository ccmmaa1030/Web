# Web 03



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

  

### CSS 크기 단위

- `px` (픽셀)
  - 모니터 해상도의 한 화소인 '픽셀' 기준
  - 크기가 변하지 않는 고정적인 단위
- `%`
  - 백분율 단위
  - 가변적인 레이아웃에서 자주 사용
- `em`
  - 바로 위, 부모 요소에 대한 상속의 영향을 받음
  - 배수 단위, 요소에 지정된 사이즈에 상대적인 사이즈를 가짐
- `rem`
  - 바로 위, 부모 요소에 대한 상속의 영향을 받지 않음
  - 최상위 요소(html)의 사이즈를 기준으로 배수 단위를 가짐

```css
.px { width: 36px; }
.percent { height: 100%; }
.em { font-size: 36em; }
.rem { font-size: 36rem; }
```



### CSS 색상 단위

- 색상 키워드
  - 대소문자를 구분하지 않음
  - 특정 색을 직접 글자로 나타냄
- RGB 색상
  - 16진수 표기법 혹은 함수형 표기법을 사용해서 특정 색을 나타냄
- HSL 색상
  - 색상, 채도, 명도를 통해 특정 색을 표현하는 방식
- a (alpha)
  - 투명도

```css
/* 색상 키워드 */
.a { color: black; }
/* RGB 색상 */
.b { color: #0000; }
.c { color: rgb(0, 0, 0); }
.d { color: rgba(0, 0, 0, 0.5); }
/* HSL 색상 */
.e { color: hsl(120, 100%, 0); }
.f { color: hsla(120, 100%, 0.5); }
```



### CSS 적용 우선순위

1. 중요도(importance) : 사용시 주의
   - !important
2. 우선 순위(Specificity)
   - 인라인 > id > class, 속성, pseudo-class > 요소, pseudo-element
3. CSS 파일 로딩 순서



### CSS Box model

- 모든 요소는 네모(`box model`)이고, 위에서부터 아래로, 왼쪽에서 오른쪽(`좌측 상단`)으로 쌓임
- 하나의 박스는 `content`, `padding`, `border`, `margin` 네 부분(영역)으로 구성

#### content

- `content` : 요소의 실제 내용

- content의 크기 지정 방법은 `width`, `height` 속성을 이용
  - `box-sizing` : 기본적으로 모든 요소의 box-sizing은 `content-box`
    - 순수 contents 영역만이 box로 지정되어 있지만, box-sizing을 이용해서 변경 가능
    - 보통 테두리인 border 영역까지를 까지 하나의 box로 보려고 함

```css
/* border 영역까지의 크기를 box로 지정 */
/* border를 포함한 크기가 너비 300px, 높이 300px */ 
.box {
    box-sizing: border-box;
    width: 300px;
    height: 300px;
}
```

#### border

- `border` : 테두리 영역

- border는 테두리 뿐만 아니라 그림, 표, 양식 등의 요소에도 적용 가능
  - `border-width` : 테두리 두께 지정
  - `border-color` : 테두리 색상 지정
  - `border-style` : 테두리 스타일 지정
  - `border` : 테두리 두께, 색상, 스타일을 한 번에 지정 가능
  - `border-radius` : 박스 모서리 둥글게 하기

```css
/* 상하좌우 두께 */
.box1 { border-width: 1px; }
/* 상하, 좌우 두께 */
.box2 { border-width: 1px 2px; }
/* 상, 좌우, 하 두께 */
.box3 { border-width: 1px 2px 1px; }
/* 상, 우, 하, 좌 두께 */
/* 시계방향 */
.box4 { border-width: 1px 2px 1px 2px; }
/* 두께 각각 지정 */
.box5 {
    border-top-width: 1px;
    border-bottom-width: 1px;
    border-right-width: 2px;
    border-left-width: 2px;
}
```

```css
/* 상하좌우 색상 */
.box1 { border-color: red; }
/* 상하, 좌우 색상 */
.box2 { border-color: red blue; }
/* 상, 좌우, 하 색상 */
.box3 { border-color: red blue green; }
/* 상, 우, 하, 좌 색상 */
/* 시계방향 */
.box4 { border-color: red blue green orange; }
/* 색상 각각 지정 */
.box5 {
    border-top-color: red;
    border-bottom-color: blue;
    border-right-color: green;
    border-left-color: orange;
}
```

```css
/* 없음(기본값) */
.box1 { border-style: none; }
/* 숨김 */
.box1 { border-style: hidden; }
/* 실선 */
.box1 { border-style: solid; }
/* 짧은선 */
.box1 { border-style: dashed; }
/* 점선 */
.box1 { border-style: dotted; }
/* 겹선 */
.box1 { border-style: double; }
/* 양각 */
.box1 { border-style: ridge; }
/* 음각 */
.box1 { border-style: groove; }
/* 오목 */
.box1 { border-style: inset; }
/* 볼록 */
.box1 { border-style: outset; }
```

```css
.box1 {
    border: 1px red solid;
    border-radius: 10px;
}
.box2 {
    border: 1px red solid;
    border-top-left-radius: 5px;
    border-top-right-radius: 10px;
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 10px;
}
```

#### padding / margin

- `padding` : 테두리 안쪽 영역(내부 여백)
- `margin` : 테두리 바깥 영역(외부 여백)
- margin, padding의 영역의 크기를 지정할 수 있음 
  - `margin` : 테두리 바깥 영역(외부 여백) 크기 지정
  - `padding` : 테두리 안쪽 영역(내부 여백) 크기 지정
  - `auto` : display 속성에서 지정한 값에 맞게 자동으로 크기 조절 가능

```css
/* 상하좌우 여백 */
.box1 { margin: 10px; }
/* 상하, 좌우 여백 */
.box2 { margin: 5px 10px; }
/* 상, 좌우, 하 여백 */
.box3 { margin: 5px 10px 5px; }
/* 상, 우, 하, 좌 여백 */
/* 시계방향 */
.box4 { margin: 5px 10px 5px 10px; }
/* 여백 각각 지정 */
.box5 {
    margin-top: 5px;
    margin-bottom: 5px;
    margin-right: 10px;
    margin-left: 10px;
}
/* content의 크기를 뺀 나머지 margin 영역의 크기를 똑같게 자동으로 조절 */
.box-auto {
    margin: 0 auto;
}
```



### CSS Layout

- `Normal flow` : 모든 요소는 네모(박스모델), 좌측상단에 배치 

#### Display

- display에 따라 크기와 배치가 달라짐
  - `display: block`
    - `블록 레벨` : 너비가 100%로 한 줄을 차지하여 자동으로 줄넘김
    - \<p>, \<h1>~\<h6>, \<ul>, \<ol>, \<li>, \<div> 등
    - 블록 레벨 요소 안에 인라인 레벨 요소가 들어갈 수 있음

  - `display: inline`
    - `인라인 레벨` : content 만큼의 영역만 차지해서 줄이 자동으로 바뀌지 않음
    - \<a>, \<img>, \<object>, \<br>, \<span>, \<input>, \<textarea>, \<label>, \<button>

  - `display: inline-block`
    
    - `인라인-블록 레벨` : 인라인과 블록의 합성 속성
    - 인라인처럼 한 줄에 표시할 수 있고, 블록처럼 여러 속성을 지정할 수 있음
    
  - `display: flex` 
    - 간단하게 수평 레아아웃 구성 가능
  
  - `display: none`
    - 해당 요소를 화면에 표시하지 않고, 공간조차 부여되지 않음
    

#### Position

- position으로 위치의 기준을 변경
  - `static` : 모든 태그의 기본 값(default)
    - 일반적인 요소의 배치 순서에 따름(normal flow)
    - 부모 요소 내에서 배치될 때는 부모 요소의 위치를 기준으로 배치 됨
  - `relative` : 본인의 원래 위치
    - normal flow 유지
    - 요소가 차지하는 공간은 static과 동일
    - top, bottom, right, left 속성을 이용해 오프셋 적용 가능
  - `absolute` : 특정 부모의 위치
    - normal flow 벗어남
    - static이 아닌 가장 가까이 있는 부모/조상 요소/브라우저 화면을 기준으로 이동
    - top, bottom, right, left 속성을 이용해 오프셋 적용 가능
    - 특정 영역 위에 존재해야 할 경우에 사용
  
  - `fixed` : 화면의 위치
    - normal flow 벗어남
    - 부모 요소와 관계없이 viewport를 기준으로 이동하여 스크롤 시에도 항상 같은 위치
    - top, bottom, right, left 속성에 의해 최종 위치가 정해짐
    - 브라우저 기준 우측 하단에 위치하여 스크롤 이동에도 따라다녀야 할 경우에 사용
  
  - `sticky` : 기본적으로 static이나 스크롤 이동에 따라 fixed로 변경
    - normal flow 벗어남
    - 평소에는 static 상태와 같지만 스크롤 위치가 임계점에 이르면 fixed와 같아짐
    - top, bottom, right, left 속성에 의해 최종 위치가 정해짐
    - 일반적으로 Navigation Bar에서 사용
  

```css
/* normal : 본인의 원래 위치 기준 */
.relative {
    position: relative;
    top: 100px;
    left: 100px;
}

/* absolute : 부모/조상 요소 기준 */
.parent { 
    position: relative; 
}
.absolute {
    position: absolute;
    top: 50px;
    left: 50px;
}

/* fixed : viewport 기준  */
.fixed {
    bottom: 0;
    right: 0;
}
```

#### Float

- 박스를 왼쪽 혹은 오른쪽으로 이동시켜 텍스트를 포함 인라인 요소들이 주변을 wrapping 하도록 함
- 요소가 Normal flow를 벗어나도록 함

```css
/* Float Left : 왼쪽에 위치하고 주변을 다른 요소들이 감쌈 */
.left { float: left; }

/* Float Right : 오른쪽에 위치하고 주변을 다른 요소들이 감쌈 */ 
.right { float: right; }
```

#### Flexbox

- 행과 열로 아이템들을 배치하는 1차원 레이아웃 모델

- 축으로 수평 방향의 `main axis`와 수직 방향의 `cross axis`를 가짐

- 부모 요소인 `Flex Container`와 자식 요소인 `Flex Item`으로 구성
  - `Flex Container`
    - Flex Item들이 놓여있는 영역
    - display 속성을 flex 혹은 inline-flax로 지정
    
  - `Flex Item`
    - 컨테이너에 속해 있는 컨텐츠(박스)
    
##### 배치 설정 속성

  - `flex-direction` 속성 : 정렬해야 하는 방향을 지정
  
    - `row` : 요소들을 텍스트의 방향과 동일하게 정렬
    
    - `row-reverse` : 요소들을 텍스트의 반대 방향으로 정렬
    
    - `column` : 요소들을 위에서 아래로 정렬
    
    - `column-reverse` : 요소들을 아래에서 위로 정렬
    - *reverse의 경우 요소들의 start와 end의 순서도 뒤바뀜*
    - *column의 경우 justify-content의 방향이 세로, align-items의 방향이 가로로 바뀜*
  
  - `flex-wrap` 속성 : 몇 줄에 걸쳐 정렬할 것인지 지정
  
    - `nowrap` : 모든 요소들을 한 줄에 정렬
    
    - `wrap`: 요소들을 여러 줄에 걸쳐 정렬
    
    - `wrap-reverse` : 요소들을 여러 줄에 걸쳐 반대로 정렬
  
  - `flex-flow` : flex-direction과 flex-wrap의 각 속성을 공백문자로 구분해서 입력받아 사용

#####  공간 나누기 속성

  - `justify-content` 속성 : 수평 방향 정렬
  
    - `flex-start` : 요소들을 컨테이너의 왼쪽으로 정렬
    - `flex-end` : 요소들을 컨테이너의 오른쪽으로 정렬
    - `center` : 요소들을 컨테이너의 가운데로 정렬
    - `space-between` : 요소들 사이에 동일한 간격을 둠
    - `space-around` : 요소들 주위에 동일한 간격을 둠
  
  - `align-content` : 여러 줄들 사이의 간격을 지정하며, 한 줄만 있는 경우 효과를 보이지 않음
  
    - `flex-start` : 여러 줄들을 컨테이너의 꼭대기로 정렬
    
    - `flex-end` : 여러 줄들을 컨테이너의 바닥으로 정렬
    
    - `center` : 여러 줄들을 컨테이너의 세로선 상의 가운데로 정렬
    
    - `space-between` : 여러 줄들 사이에 동일한 간격을 둠
    
    - `space-around` : 여러 줄들 주위에 동일한 간격을 둠
    - `stretch` : 여러 줄들을 컨테이너에 맞도록 늘림
    


#####  정렬 속성

  - `align-items` 속성 : 수직 방향 정렬
    - `flex-start` : 요소들을 컨테이너의 꼭대기로 정렬
    
    - `flex-end` : 요소들을 컨테이너의 바닥으로 정렬
    
    - `center` : 요소들을 컨테이너의 세로선 상의 가운데로 정렬
    
    - `space-between` : 요소들을 컨테이너의 시작 위치에 정렬
    
    - `space-around` : 요소들을 컨테이너에 맞도록 늘림
    
  - `align-self` 속성 : align-items가 사용하는 값들을 인자로 받아 개별 요소에 적용 가능
  
  - `order` 속성 : flex 아이템의 나열 순서 재조정 가능
    - 기본 값은 0, 양수나 음수로 값을 지정할 수 있음
    - 값이 작은 수부터 출력



