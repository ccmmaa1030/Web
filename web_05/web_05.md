# Web 05



## HTML(Hyper Text Markup Language)



## Bootstrap

- 웹사이트를 쉽게 만들 수 있게 도와주는 HTML, CSS, JS 프레임워크
- 하나의 CSS로 휴대폰, 테블릿, 데스크탑까지 다양한 기기에서 작동(반응형 웹사이트 개발)



### CDN(Content Delivery(Distribution) Network)

- 컨텐츠(CSS, JS, Image, Text 등)을 효율적으로 전달하기 위해 여러 노드에 가진 네트워크에 데이터를 제공하는 시스템
- 개별 end-user의 가까운 서버를 통해 빠르게 전달 가능(지리적 이점)
- 외부 서버를 활용하으로써 본인 서버의 부하가 적어짐

```html
<!-- CSS only -->
<!-- <head>에 추가 -->
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-gH2yIJqKdNHPEq0n4Mqa/HGKIhSkIHeL5AyhkYV8i59U5AR6csBvApHHNl/vI1Bx" crossorigin="anonymous">
```

```html
<!-- JavaScript Bundle with Popper -->
<!-- <body>에 추가 -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-A3rJD856KowSb7dwlZdYEkO39Gagi7vIsF0jrRAoQmDKKtQBHUuLZ9AsSv4jD4Xa" crossorigin="anonymous"></script>
```



### Layout 레이아웃

#### Breakpoints

- 반응형 디자인 컴포넌트로 레이아웃을 특정 뷰포트 크기 또는 기기에서 조정할 수 있는 시기를 제어할 수 있음
- `grid tiers`라고 하는 6개의 `Breakpoints` 포함
  - `X-small` : 576px 미만
  - `Small` : 576px 이상 (`sm`)
  - `Medium` : 768px 이상 (`md`)
  - `Large` : 992px 이상 (`lg`)
  - `Extra large` : 1200px 이상 (`xl`)
  - `Extra extra large` : 1400px 이상 (`xxl`)



### Content

#### Reboot

- Normalize를 기반으로 빌드되어 초기에 일관되고 간단한 디자인 기준선을 제공함
- 추가 스타일링은 클래스에서만 수행됨



#### Typography

- 제목 
  - `h1`, `h2`, `h3`, `h4`, `h5`, `h6` : HTML 요소를 사용할 수 없을 때 클래스도 사용 가능
- 사용자 정의 제목
  - `text-muted` : 보조 제목 텍스트 생성
- 표시 제목 : 제목 스타일
  - `display-1` : 5rem  
  - `display-2` :  4.5rem
  - `display-3` :  4rem
  - `display-4` :  3.5rem
  - `display-5` :  3rem
  - `display-6` :  2.5rem

- 서두
  - `.lead` : 서두 단락을 추가
- 인라인 텍스트 요소
  - `<mark>` : 참조 도는 표기 목적으로 표시되는 강조된 텍스트
  - `<small>` : 저작권 및 법적 텍스트와 같은 부가적인 댓글과 작은 텍스트
  - `<s>` : 더 이상 관련이 없거나 정확하지 않은 요소를 나타냄
    - `text-decoration-line-through` 과 동일한 스타일
  - `<u>` : 텍스트가 아닌 주석이 있음을 나타내는 방식으로 렌더링되어야 하는 범위를 나타냄
    - `text-decoration-underline` 과 동일한 스타일
- 인용문
  - `<blockquote class="blockquote">` : 인용문을 표시하기 위해 해당 태그로 감쌈
- 출처 표기
  - `<figure>` : `<blockquote>`와 `<figcaption>`을 해당 태그로 감쌈
  - `<figcaption class="blockquote-footer">` : 출처를 해당 태그로 감쌈
- 목록
  - `list-unstyled` : 기본 스타일과 항목 왼쪽 여백 제거
  - `list-inline`, `list-inline-item` : 목록과 각 항목의 글 머리 기호 제거, 약간의 margin 적용



#### Image

- 반응형 이미지
  - `img-fluid` : max-width: 100%;, height: auto; 적용으로 자동 크기 조정
- 이미지 썸네일
  - `img-thumbnail` : 이미지에 둥근 1px 테두리 모양 표시



#### Table
- `<table>`로 table을 생성하고, `<thead>`, `<tbody>`, `<tfoot>` 요소를 활용해 각 영역을 명시
  -  `<thead>` : header 부분을 의미
  -  `<tbody>` : body 부분을 의미
  -  `<tfoot>` : footer 부분을 의미
- `<tr>`, `<th>`, `<td>` 요소를 활용하여 table을 구성
  - `<tr>` : table의 행
  - `<th>` : table의 열 제목이 들어가는 셀
  - `<td>` : table 내용이 들어가는 셀
- `colspan`, `rowspan` 속성을 활용하여 셀 병합
  - `colspan` : 가로로 이웃한 셀 병합
  - `rowspan` : 세로로 이웃한 셀 병합
- `<caption>`을 통해 표 설명 또는 제목을 나타냄

```html
<body>
    <table>
        <thead>
            <tr>
            	<th>Name</th>
            </tr>
        </thead>
        <tbody>
        	<tr>
            	<td>홍길동</td>
            </tr>
            <tr>
            	<td>전우치</td>
            </tr>
        </tbody>
        <tfoot>
        	<tr>
            	<td>총계</td>
                <td colspan="2">2명</td>
            </tr>
        </tfoot>
        <caption>1반 학생 명단</caption>
    </table>
</body>
```

- 테이블 강조
  - `table-striped` : 테이블 행 줄무늬 추가
  - `table-hover` : 마우스 오버 상태 활성화
- 테이블 활성화
  - `table-active` : 테이블 행 또는 셀 강조
- 수직 정렬
  - `table-align-middle` : 텍스트 수직 정렬
- 테이블 테두리
  - `table-bordered` : 모든 면에 테두리
  - `table-borderless` : 테두리 없음



#### Figure

- `<figure>` : 선택적 캡션이 있는 이미지와 텍스트 등을 표시해야 할 때 사용
  - `figure-img` : 캡션을 표시할 이미지에 속성 적용
  - `<figcaption class="figure-caption">` : 캡션 추가



### Forms

- `<form>`은 정보(데이터)를 서버에 제출하기 위해 사용하는 태그
  - `action` : form을 처리할 서버의 URL(데이터를 보낼 곳)
  - `method` : form을 제출할 때 사용할 HTTP 메서드(GET 혹은 POST)
  - `enctype` : method가 post인 경우 데이터의 유형
    - application/x-www-form-urlencoded : 기본값
    - multipart/form-data : 파일 전송시(input type이 file인 경우)

```html
<form action="/search" method="GET">
    <input type="text" name="q">
</form>
```



#### form control

- `form control` : 크기 조절/설정
- `disabled` : 비활성화
- `readonly` : 읽기 전용
  - `form-control-plaintext` : 기본 필드 스타일 삭제하고 일반 텍스트로 표시



#### input

- `<input>` : 대화형 컨트롤 폼을 생성하며, 다양한 종류의 입력 데이터 유형과 컨트롤 위젯이 존재
  - `name` : form control에 적용되는 이름(이름/값 페어로 전송됨)
  - `value` : form control에 적용되는 값(이름/값 페어로 전송됨)
  - required, readonly, autofocus, autocomplete, disabled 등
- `<label>` : label을 클릭하여 input 자체의 조첨을 맞추거나 활성화 시킬 수 있음
  - 사용자는 선택할 수 있는 영역이 늘어나 웹/모바일(터치) 환경에서 편하게 사용 가능
  - `<input>`에 `id` 속성을, `<label>`에는 `for` 속성을 활용하여 상호 연관을 시킴

```html
<label for="agreement">개인정보 수집에 동의합니다.</label>
<input type="checkbox" name="agreement" id="agreement">
```

- 일반 유형 : 일반적으로 입력을 받기 위해 제공되며 타입별로 검증 혹은 추가 속성 활용 가능

  - `text` : 일반 텍스트 입력

  - `password` : 입력 시 값이 보이지 않고 문자를 특수기호(*)로 표현

  - `email` : 이메일 형식이 아닌 경우 form 제출 불가

  - `number` : min, max, step 속성을 활용하여 숫자 범위 설정 가능

  - `file` : accept 속성을 활용하여 파일 타입 지정 가능

```html
<input type="text" name="name" id="name">
<input type="password" name="password" id="password">
<input type="email" name="email" id="email">
<input type="number" name="age" id="age">
<input type="file" name="application" id="application">
```

- 선택 유형 : 일반적으로 label 태그와 함께 사용하여 선택 항목을 작성
  - 동일 항목에 대하여는 name을 지정하고 선택된 항목에 대한 value를 지정해야 함
  - `checkbox` : 다중 선택
  - `radio` : 단일 선택


```html
<!-- 체크박스 -->
<div>
	<p>checkbox</p>
	<input id="html" type="checkbox" name="language" value="html">
	<label for="html">HTML</label>
	<input id="python" type="checkbox" name="language" value="python">
	<label for="python">파이썬</label>
	<input id="python" type="checkbox" name="language" value="java">
	<label for="java">자바</label>
	<hr>
</div>
<!-- 라디오버튼 -->
<div>
	<p>radiobutton</p>
	<input id="happy" type="radio" name="mood" value="행복">
	<label for="happy">행복</label>
	<input id="sad" type="radio" name="mood" value="슬픔">
	<label for="sad">슬픔</label>
	<input id="mid" type="radio" name="mood" value="중립">
	<label for="mid">중립</label>
	<hr>
</div>
```

- 기타 유형 : 다양한 종류의 input을 위한 `picker`를 제공
  - `color` : color picker
  - `date` : date picker
  - `hidden` : 사용자에게 보이지 않는 input



### Utilities 유틸리티

#### spacing

- bootstrap 공백 설정 : `{property}{sides}-{size}`

- property

  - `m`, `p` : margin, padding

- sides

  - `t`, `b` : top, bottom

  - `s`, `e` : left(start), right(end)

  - `x` : left, right

  - `y` : top, bottom
  - `auto` : 블록 요소 중앙 정렬

- size
  - `0` : 0rem, 0px
  - `1` : 0.25rem, 4px
  - `2` : 0.5rem, 8px
  - `3` : 1rem, 16px
  - `4` : 1.5rem, 24px
  - `5` : 3rem, 48px



#### color

- 색상 변경 : `{property}-{color}`
- property
  - `bg` : background 배경 색
  - `text` : 텍스트 색
  - `border` : 테두리 색
- color
  - `primary`, `secondary`, `success`, `info`, `warning`, `danger`, `light`, `dark`  등 테마 색상



#### text

- 텍스트 정렬

  - `text-start` : 왼쪽 정렬

  - `text-center` : 가운데 정렬 (=mx-auto)

  - `text-end` : 오른쪽 정렬

- 텍스트 꾸미기

  - `text-decoration-none` : 텍스트 꾸미기 없음
  - `text-decoration-underline` : 밑줄 설정
  - `text-decoration-line-through` : 가운데줄 설정
  - `mark` : 하이라이트 표시
  - `small` : 부가적인 작은 텍스트로 표시

- 글꼴 크기(font-size : .fs)

  - `1`, `2`, `3`, `4`, `5`, `6` : HTML 제목 요소와 일치하므로 숫자가 증가할수록 크기가 작아짐

- 글꼴 굵기(font-weight : .fw)와 기울임체(font-style : .fst)

  - `fw-bold` : 굵게

  - `fw-normal` : 일반

  - `fw-light` : 얇게

  - `fst-normal` : 일반

  - `fst-italic` : 기울임

- 줄바꿈
  - `text-wrap` : 텍스트 줄바꿈
  - `text-nowrap` : 텍스트 오버플로우
  - `text-break` : 단어 기준 줄바꿈



#### display

- display 형식 : `d-{value} for xs`
- breakpoints 적용되는 display 형식 : `d-{breakpoint}-{value} for sm, md, lg, xl, and xxl.`
- value
  - `none`
  - `inline`
  - `inline-block`
  - `block`
  - `grid`
  - `table`
  - `table-cell`
  - `table-row`
  - `flex`
  - `inline-flex`
- 요소 숨기기
  - 모든 요소 숨기기 : `d-none`
  - 특정 요소만 숨기기 : `d-{sm, md, lg, xl, xxl}-none`
- 인쇄할 때 표시
  - `d-print-{value}`



#### position

- 위치 지정

  - `position-static`
  - `position-relative`
  - `position-absolute`
  - `position-fixed`
  - `position-sticky`

- 요소 정렬

  - 위치 값으로 위치 지정 : `{property}-{position}`

    - property
      - `top`, `bottom`, `start`, `end` : 상 하 좌 우

    - position
      - 0, 50, 100 : 순서대로 0, 50%, 100% edge position

- 중앙 정렬

  - `translate-middle` : 요소를 중앙에 배치
    - translate-middle-x : 가로 중앙 배치
    - translate-middle-y : 세로 중앙 배치

