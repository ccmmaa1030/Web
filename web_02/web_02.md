# Web 02



## CSS(Cascading Style Sheets)



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
- 하나의 박스는 네 부분(영역)으로 구성
  - `margin` : 테두리 바깥 영역(외부 여백)
  - `border` : 테두리 영역
  - `padding` : 테두리 안쪽 영역(내부 여백)
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



### CSS Display

- display에 따라 크기와 배치가 달라짐
  - display: block
    - `블록 레벨` : 너비가 100%로 한 줄을 차지하여 자동으로 줄넘김
    - \<p>, \<h1>~\<h6>, \<ul>, \<ol>, \<li>, \<div> 등
    - 블록 레벨 요소 안에 인라인 레벨 요소가 들어갈 수 있음

  - display: inline
    - `인라인 레벨` : content 만큼의 영역만 차지해서 줄이 자동으로 바뀌지 않음
    - \<a>, \<img>, \<object>, \<br>, \<span>, \<input>, \<textarea>, \<label>, \<button>

  - display: inline-block
    - `인라인-블록 레벨` : 인라인과 블록의 합성 속성
    - 인라인처럼 한 줄에 표시할 수 있고, 블록처럼 여러 속성을 지정할 수 있음

  - display: flex 
    - 간단하게 수평 레아아웃 구성 가능

  - display: none
    - 해당 요소를 화면에 표시하지 않고, 공간조차 부여되지 않음

