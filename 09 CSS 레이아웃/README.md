# CSS 포지셔닝과 주요 속성들

## CSS 포지셔닝이란? 
- 브라우저 화면 안에 각 콘텐츠 영역을 어떻게 배치할지를 결정하는 것

## box-sizing 속성 - 박스 너비 기준 정하기

- CSS의 width 속성은 콘텐츠 영역의 너비를 나타내기 때문에 해당 요소에 적용한 패딩이나 테두리 크기는 따로 계산해서 배치해야 합니다. 
- 이럴 때 box-sizing 속성을 사용하면 콘텐츠 영역의 너비에 패딩과 테두리 크기까지 합쳐서 width 속성을 지정할 수 있습니다.

```css
box-sizing: content-box | border-box;
```

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/09%20CSS%20%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83/images/1.png)

|속성 값|설명|
|---|----|
|content-box|width 속성 값을 콘텐츠 영역 너비 값으로 사용합니다. 기본 값입니다.|
|border-box|width 속성 값을 콘텐츠 영역에 테두리까지 포함한 박스 모델 전체 너비 값으로 사용합니다.|


```html
    <style>
		div {
			float:left;
			margin-right:20px;
		}
		.box1 {
			box-sizing:content-box; /* 콘텐츠 영역 기준 */
			width: 300px; /* 콘텐츠 영역 너비 300px */
			height: 150px; /* 높이 */
			margin: 10px; /* 마진 */
			padding: 30px; /* 패딩 */
			border:2px solid red; /* 테두리 */
		}
		.box2 {
			box-sizing:border-box;  /* 테두리까지(박스 전체) 기준*/
			width: 300px; /* 박스 모델 전체 너비 */
			height: 150px; /* 박스 높이 */
			margin: 10px; /* 마진 */
			padding: 30px; /* 패딩 */
			border: 2px solid red; /* 테두리 */
		}
	</style>

    <div class="box1"> box-sizing = "content-box" </div>
    <div class="box2"> box-sizing = "border-box"</div>
```

> CSS를 이용해 여러 박스 모델을 화면상에 배치하려면 박스 모델의 너비 값을 정확히 계산해야 합니다. 만약 width 값을 계산하기 어렵다면 box-sizing: border-box로 지정해 박스 모델 너비를 알기 쉽게 바꾸어 놓는 것도 좋은 방법입니다.

## float 속성 - 왼쪽이나 오른쪽으로 배치하기 
- float 속성은 웹 요소를 문서 위에 떠 있게 만듭니다. 
- '떠 있다'라는 의미는 왼쪽 구석이나 오른쪽 구석에 요소가 배치된다는 뜻입니다. float 속성에서 사용할 수 있는 값에는 왼쪽(left)과 오른쪽(right), 그리고 좌우 어느 쪽도 아닌 것(none)이 있습니다.

```css
float: left | right | none
```

|속성 값| 설명 |
|---|----|
|left|해당 요소를 문서의 왼쪽으로 배치합니다.|
|right|해당 요소를 문서의 오른쪽으로 배치합니다.|
|none|좌우 어느 쪽으로도 배치하지 않습니다.|

```html
<style>
    .left-img {
         float:left;
         margin-right:25px;
    }
</style>

<img src="images/cover.jpg" class="left-img" alt="">
<h1>바쁜 3, 4학년을 위한 빠른 분수</h1>
<h2>3, 4학년이 꼭 알아야 할 분수를 한 권에 모았어요!​</h2>
<p>한국 교육과정평가원이 최근 발표한 보고서에 따르면 ‘수포자’는 초등 3학년 때 분수를 배우면서 시작된다고 합니다. 분수를 어려워하는 이유는 분모와 분자, 2개의 수가 나와 낯설기 때문입니다. 이렇게 낯설고 어려운 분수, 어떻게 공부해야 할까요?</p>
```

- float: left나 float: right를 지정하면 너비 값은 콘텐츠를 표시할 때 필요한 만큼만 차지하고 다른 요소가 들어올 만큼의 공간을 비워 둡니다.

```html
    <style>
		.box1{
			padding:20px;
			margin-right:10px;
			background:#ffd800;
			float:left;
		}
		.box2 {
			background: #0094ff;
			padding:20px;
			margin-right:10px;
			float:left;
		}
		.box3 {
			background: #00ff21;
			padding:20px;
			float:left;
		}
		.box4 {
			background:#ffffff;
			padding:20px;
			float:right;
			border:1px solid black;
		}
	</style>

    <div class="box1">박스1</div>
    <div class="box2">박스2</div>
    <div class="box3">박스3</div>
    <div class="box4">박스4</div>
```


## clear 속성 - float 속성 해제하기
- float 속성을 이용해 웹 페이지 요소를 왼쪽이나 오른쪽에 배치하면 그 다음에 넣는 다른 요소들에도 똑같은 속성이 전달됩니다. 
- 따라서 float 속성이 더 이상 유용하지 않다고 알려 주는 속성이 필요한데 그것이 바로 clear 속성 입니다.


```css
clear: none | left | right | both
```

> float:left를 해제하기 위해 clear:left라고 지정하면 되지만 float 속성 값을 일일이 기억하기 번거롭다면 clear:both라고 한꺼번에 지정하기도 합니다.

```html
    <style>
		div {
			padding:20px;
			margin:10px;
		}
		.box1{
			background:#ffd800;
			float:left;
		}
		.box2 {
			background: #0094ff;
			float:left;
		}
		.box3 {
			background: #00ff21;
		}
		.box4 {
			background:#a874ff;
			clear:both;
		}
	</style>

    <div class="box1">박스1</div>
    <div class="box2">박스2</div>
    <div class="box3">박스3</div>
    <div class="box4">박스4</div>
```

## position 속성 - 배치 방법 지정하기 

- position 속성은 웹 문서 안의 요소들을 자유자재로 배치해 주는 속성

```css
position: static | relative | absolute | fixed
```

|속성 값|설명|
|---|----|
|static|요소를 문서의 흐름에 맞추어 배치합니다.|
|relative|이전 요소에 자연스럽게 연결해 배치하되 위치를 지정할 수 있습니다.|
|absolute|원하는 위치를 지정해 배치합니다.|
|fixed|지정한 위치에 고정해 배치합니다. 화면에서 요소가 잘릴 수도 있습니다.|

- position 속성 중 static을 제외한 나머지 속성 값에서는 좌표를 이동해 각 요소의 위치를 조절할 수 있습니다. 
- 이때 위치는 top과 bottom, left, right로 지정합니다. 
- top: 위쪽에서 얼마나 떨어져 있는지
- bottom: 아래에서 얼마나 떨어져 있는지
- left: 왼쪽에서 알마나 떨어져 있는지
- right: 오른쪽에서 얼마나 떨어져 있는지

### static 속성 값 - 문서의 흐름대로 배치하기

- static은 position 속성의 기본 값으로 요소를 나열한 순서대로 배치하며 top이나 right, bottom, left 같은 속성을 사용할 수 없습니다. 

### relative 속성 값 - 문서 흐름 따라 위치 지정하기

- static에서처럼 나열한 순서대로 배치되지만 top이나 right, bottom, left 속성을 사용할 수 있으며 좌푯값을 이용해 위치를 지정할 수 있습니다. 

```html
    <style>
		.box1{
			float:left;
			width:100px;
			background:#ffd800;
			margin-right:10px;
			padding:20px;
		}
		.box2 {
			position:relative;
			left:-50px;
			top:30px;
			width:300px;
			background:#0094ff;
			float:left;
			padding:20px;
		}
	</style>

    <div class="box1">박스1</div>
    <div class="box2">박스2</div>
```

### absolute 속성 값 - 원하는 위치에 배치하기 

- 문서의 흐름과 상관 없이 left와 right, top, bottom 속성 값을 이용해 원하는 위치에 배치할 수 있습니다. 
- 이때 기준이 되는 위치는 가장 가까운 부모 요소나 조상 요소 중 position 속성이 relative인 요소 입니다.
- absolute 속성 값을 이용해 자유자재로 요소를 배치하기 위해서는 반드시 부모 요소가 relative로 지정되어 있어야 합니다.

```html
    <style>
		#wrap{
			position:relative;
			width:300px;
			height:300px;
			border:1px solid #ccc;
		}
		.box{
			position:absolute;
			width:50px;
			height:50px;
			background:#0094ff;
		}
		#crd1{ top:0; left:0; }
		#crd2{ top:0; right:0; }
		#crd3{ bottom:0; left:0; }
		#crd4{ bottom:0; right:0; }
		#crd5{ top:100px; left:100px; }
	</style>

    <div id="wrap">
        <div class="box" id="crd1"></div>
        <div class="box" id="crd2"></div>
        <div class="box" id="crd3"></div>
        <div class="box" id="crd4"></div>
        <div class="box" id="crd5"></div>
    </div>
```

### fixed 속성 값 - 브라우저 창 기준으로 배치하기
- absolute 속성 값처럼 문서의 흐름과 상관없이 위치를 좌표로 결정하지만 부모 요소가 아닌 브라우저 창이 기준이 됩니다. 
- 브라우저 창의 왼쪽 위 꼭지점을 원점으로 두고 좌표가 계산됩니다.
- 한 번 배치되면 fixed라는 이름처럼 브라우저 창을 스크롤하더라도 계속 고정되어 표시됩니다.


```html
    <style>
		#fx{
			position:fixed;
			top:5px;
			right:5px;
			width:50px;
			height:50px;
			background:#ff6a00;
		}
		#content { width:400px;	}
		p { line-height:30px;}
	</style>

    <div id="fx"></div>
    <div id="content">
        <p>fixed 값을 사용하는 요소 역시 absolute 값을 사용하는 요소처럼 문서 흐름과는 상관 없이 좌표로 위치를 결정하지만, 기준이 되는 요소가 부모 요소가 아니라 브라우저 창이 기준이 됩니다. 브라우저 창의 왼쪽 위 모서리 부분을 원점으로 좌표가 계산되고 한번 배치되면 fixed라는 이름처럼 브라우저 창을 스크롤하더라도 계속 고정되어 표시됩니다. </p>
        <p>fixed 값을 사용하는 요소 역시 absolute 값을 사용하는 요소처럼 문서 흐름과는 상관 없이 좌표로 위치를 결정하지만, 기준이 되는 요소가 부모 요소가 아니라 브라우저 창이 기준이 됩니다. 브라우저 창의 왼쪽 위 모서리 부분을 원점으로 좌표가 계산되고 한번 배치되면 fixed라는 이름처럼 브라우저 창을 스크롤하더라도 계속 고정되어 표시됩니다. </p>
    </div>
```

## visibility 속성 - 요소를 보이게 하거나 보이지 않게 하기 

```css 
visibility: visible | hidden | collapse 
```

|속성 값|설명|
|---|----|
|visible|화면에 요소를 표시합니다. 기본값|
|hidden|화면에서 요소를 감춥니다. 하지만 크기는 그대로 유지하기 때문에 배치에 영향을 미칩니다.|
|collapse|표의 행, 열, 행 그룹, 열 그룹 등에서 지정하면 서로 겹치도록 조절합니다. 그 외의 영역에서 사용하면 'hidden' 처럼 처리합니다.|

```css
div { visibility: hidden; }
```

- visibility를 hidden으로 지정하면 화면에서 감춘 요소들은 눈에 보이지 않지만 실제로는 공간을 차지합니다. 

> display: none을 이용해 화면에서 요소를 감추었을 경우, 실제 공간을 차지하지 않으므로 마치 없는 요소처럼 생각하고 다른 요소를 배치할 수 있습니다.

```html
    <style>
        img {
			margin:10px;
			padding:5px;
			border:1px solid black;
		}
		.invisible {
			visibility:hidden;
		}
    </style>

    <img src="images/pic1.jpg">
    <img src="images/pic2.jpg" class="invisible">
    <img src="images/pic3.jpg">
```

## z-index 속성 - 요소 쌓는 순서 정하기 

- 요소 위에 요소를 쌓을 때 쌓는 순서를 지정하는 것이 z-index 속성입니다. 
- z-index 값이 작을수록 아래에 쌓이고 z-index 값이 클수록 z-index 값이 작은 요소보다 위에 쌓입니다. 
- z-index 값을 명시하지 않을 경우 웹 문서에 맨 처음 삽입하는 요소가 z-index: 1값을 가지며 그 후 삽입하는 요소들은 z-index값이 점점 커집니다. 

```html
    <style>
			div#wrapper {
				position: relative;
			}
			.box {
				position:absolute;
				width:100px;
				height:100px;
				border:1px solid black;
				font-size:26px;
			}
			#b1 {				
				left:50px;
				top:50px;
				background:#ff0000;
				z-index:1;
			}
			#b2 {				
				left:110px;
				top:70px;
				background:#ffd800;
				z-index:3;
			}
			#b3 {
				left:70px;
				top:110px;
				background:#0094ff;
				z-index:1;
			}
    </style>
    <div id="wrapper">
        <div id="b1" class="box">1</div>
        <div id="b2" class="box">2</div>
        <div id="b3" class="box">3</div>
    </div>
```

--- 

# 다단으로 편집하기

## column-width - 단의 너비 고정하고 다단 구성하기

- 한 화면을 여러 단으로 구성할 때 단의 너비를 고정해 놓고 화면을 분할할 수도 있고 단의 개수를 고정해 좋고 화면을 분할할 수도 있습니다.
- 화면이 커지면 단의 개수가 많아지고 화면이 좁아지면 단의 개수가 줄어듭니다. 
- 다단으로 편집할 때 단의 너비를 고정해 놓으려면 column-width 속성을 이용합니다. 

```css
column-width: <크기> | auto
```

|속성 값|설명|
|---|----|
|\<크기\>|단 너비를 직접 지정합니다.|
|auto|단의 개수(column-count) 값을 다른 속성에 따라 단의 너비가 자동 계산됩니다.|


```html
    <style>
		body {
			font-family: "맑은 고딕", "고딕", "굴림";
		}

		.multi {
			-webkit-column-width: 120px;
			-moz-column-width: 120px;
			column-width: 120px;
		}
	</style>

    <header>
        <h2>건강에 좋은 식품 - Super Food</h2>
    </header>
    <div class="multi">
        <p><b>코코넛 오일 </b>: 남미 파나마에서는 “코코넛오일 한 컵이면 모든 병이 낫는다”라고 이야기할 정도로 그 효능이 뛰어나다. 코코넛 오일에 들어있는 중사슬 지방산은 콜레스테롤 수치에 나쁜 영향을 주지 않는 건강한 지방산이다. 또 라우르산이 풍부해 세균을 물리치고 염증을 가라앉히는 효과가 있다. 하루 권장량은 성인기준 2~4스푼(30~40mL) 정도이다.</p>
        <p><b>블루베리 </b>: 블루베리는 우리 몸이 산화하는 현상을 막아주는 '항산화 물질'이 가장 많은 식품으로 알려졌다. 미국 농무부 인간영양연구소에서 밝힌 자료에 따르면 블루베리의 '안토시아닌'이라는 물질은 시력 향상에 뛰어난 효과가 있다. 그뿐만 아니라 다이어트에도 좋다. 블루베리의 폴리페놀 성분은 체내 지방세포를 녹여주는 역할을 한다. 하루 권장량은 성인기준 50g 전후로, 20~30알 정도이다.</p>
        <p><b>아몬드 </b>: 혈관질환에 좋은 오메가3, 섬유소, 비타민 E가 풍부해 항산화 효과가 높으며 콜레스테롤 수치를 낮추는 L-아르기닌 등의 좋은 영양소도 들어 있다. 또한, 식욕을 감소시키고 뇌 내 행복감을 촉진하는 세로토닌 분비를 증가시키는 것으로 나타났다. 특히 껍질에 비타민 E, 플라보노이드, 카테킨 등의 항산화 성분이 풍부하니 껍질째 먹는 것이 좋다. 하루 권장량은 30g(23알 내외) 정도이며, 과도하게 섭취하면 장의 흡수기능이 저하되니 주의해야 한다.</p>
    </div>
```

## column-count 속성 - 단의 개수 고정하고 다단 구성하기
- 다단 화면을 만들 때 단의 개수를 고정해 놓을 수도 있습니다. 
- 브라우저 청의 너비와 상관없이 단의 개수를 항상 일정하게 유지해야 하기 때문에 창의 너비가 커지면 단의 너비도 커집니다.

```css
column-count: <숫자> | auto
```

|속성 값|설명|
|---|----|
|\<숫자\>|콘텐츠가 들어갈 단의 개수를 지정합니다. 0보다 큰 수를 사용합니다.|
|auto|단의 너비(column-width)와 같은 다른 속성에 따라 단의 개수가 자동 계산됩니다.|

```html
<style>
    body {
	    font-family: "맑은 고딕", "고딕", "굴림";
	}
	.multi {
		-webkit-column-count: 3;
		-moz-column-count: 3;
		column-count: 3;
	}
</style>

<header>
    <h2>건강에 좋은 식품 - Super Food</h2>
</header>
<div class="multi">
    <p><b>코코넛 오일 </b>: 남미 파나마에서는 “코코넛오일 한 컵이면 모든 병이 낫는다”라고 이야기할 정도로 그 효능이 뛰어나다. 코코넛 오일에 들어있는 중사슬 지방산은 콜레스테롤 수치에 나쁜 영향을 주지 않는 건강한 지방산이다. 또 라우르산이 풍부해 세균을 물리치고 염증을 가라앉히는 효과가 있다. 하루 권장량은 성인기준 2~4스푼(30~40mL) 정도이다.</p>
    <p><b>블루베리 </b>: 블루베리는 우리 몸이 산화하는 현상을 막아주는 '항산화 물질'이 가장 많은 식품으로 알려졌다. 미국 농무부 인간영양연구소에서 밝힌 자료에 따르면 블루베리의 '안토시아닌'이라는 물질은 시력 향상에 뛰어난 효과가 있다. 그뿐만 아니라 다이어트에도 좋다. 블루베리의 폴리페놀 성분은 체내 지방세포를 녹여주는 역할을 한다. 하루 권장량은 성인기준 50g 전후로, 20~30알 정도이다.</p>
    <p><b>아몬드 </b>: 혈관질환에 좋은 오메가3, 섬유소, 비타민 E가 풍부해 항산화 효과가 높으며 콜레스테롤 수치를 낮추는 L-아르기닌 등의 좋은 영양소도 들어 있다. 또한, 식욕을 감소시키고 뇌 내 행복감을 촉진하는 세로토닌 분비를 증가시키는 것으로 나타났다. 특히 껍질에 비타민 E, 플라보노이드, 카테킨 등의 항산화 성분이 풍부하니 껍질째 먹는 것이 좋다. 하루 권장량은 30g(23알 내외) 정도이며, 과도하게 섭취하면 장의 흡수기능이 저하되니 주의해야 한다.</p>
</div>
```

## column-gap 속성 - 단과 단 사이 여백 지정하기

```css
column-gap: <크기> | normal
```

|속성 값|설명|
|---|----|
|\<크기\>|단과 단 사이의 여백을 숫자로 지정합니다.|
|normal|여백을 자동으로 지정합니다. W3C에서 권장하는 여백은 1em 입니다.|

## column-rule 속성 - 구분선의 색상, 스타일, 너비 지정하기

- 단과 단 사이에 구분하기 위한 수직선을 넣기도 합니다. 
- 선의 스타일을 지정하는데 색상과 형태, 너비를 따로 지정하고 싶다면 column-rule-color, column-rule-style, column-rule-width 속성을 사용합니다.

```css
column-rule-color: <색상>
column-rule-style: none | hidden | dotted | dashed | solid | double | groove | ridge | inset | outset 
column-rule-width: <크기> | thin | medium | thick 
column-rule: <너비> <스타일> <색상>
```

```css
column-rule-color: #ccc; 
column-rule-style: dotted;
column-rule-width: 1px;
```

- column-rule 속성 하나로 묶어 지정하는 것이 편리합니다.

```html
<style>
    .multi {
        ...
        column-rule: 2px dotted #000;
        ...
    }
</style>
```

## break-after 속성 - 다단 위치 지정하기 

- 다단을 어디부터 시작할지 지정하는 속성 

```css
break-after: column | avoid-column
break-before: column | avoid-column
break-inside: column | avoid-column
```

![image2](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/09%20CSS%20%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83/images/2.png)

- 특정 요소의 앞부분에서 단을 나누려면 break-before: column;
- 특정 요소의 뒤에서 단을 나누러면 break-after: column;
- 특정 요소의 앞뒤에서 강제로 단을 나누지 않게 하려면 break-before: avoid-column이나 break-after:avoid-column을 사용합니다.
- break-inside: column과 break-inside: avoid-column은 해당 요소 안에서 강제로 단을 나누거나 나누지 않게 하는 속성입니다.

```html
<style>
    .multi {
         -webkit-column-count: 4;
         -moz-column-count: 4;
         column-count: 4;
         -webkit-column-rule: 2px dotted #000;
         -moz-column-rule: 2px dotted #000;
         column-rule: 2px dotted #000;
         text-align: justify;
    }
    .multi h3 {
        break-before: column;
    }
</style>


<section>
    <h2>건강에 좋은 식품 - Super Food</h2>
    <h3>코코넛 오일</h3>
    <p>남미 파나마에서는 “코코넛오일 한 컵이면 모든 병이 낫는다”라고 이야기할 정도로 그 효능이 뛰어나다. 코코넛 오일에 들어있는 중사슬 지방산은 콜레스테롤 수치에 나쁜 영향을 주지 않는 건강한 지방산이다. 또 라우르산이 풍부해 세균을 물리치고 염증을 가라앉히는 효과가 있다. 하루 권장량은 성인기준 2~4스푼(30~40mL) 정도이다.</p>
    <div class="multi">
        <h3>아보카도</h3>
        <p>나무에서 열리는 버터라고 불릴 만큼 몸에 좋은 지방인 오메가 3와 단백질, 비타민 E와 같은 항산화 성분이 풍부한 과일이다. 알파 카로틴이 풍부하게 들어 있어 여러 항암 효과가 뛰어난 것으로 알려져 있다. 그뿐만 아니라 세포의 콜라겐 합성을 도와 피부 탄력을 높이는 데 도움을 준다. 하루 권장량은 성인기준 1개이며, 꾸준히 섭취하면 콜레스테롤 수치를 낮춰준다.</p>
        <h3>케일</h3>
        <p>케일은 브로콜리, 양배추, 유채, 청경채와 같은 배추과 식물로써 세계보건기구에서 최고의 녹황색 채소로 선정되었다. 베타카로틴과 엽록소가 풍부해 체내 유전자를 회복하도록 돕는 항암효과가 뛰어나다. 또한, 위염, 위궤양에 좋은 비타민 U와 유산균을 늘리는 비타민 M과 같은 식물성 영양소를 함유하고 있다. 하루 권장량은 성인기준 150g 정도이다.</p>
        <h3>블루베리</h3>
        <p>블루베리는 우리 몸이 산화하는 현상을 막아주는 '항산화 물질'이 가장 많은 식품으로 알려졌다. 미국 농무부 인간영양연구소에서 밝힌 자료에 따르면 블루베리의 '안토시아닌'이라는 물질은 시력 향상에 뛰어난 효과가 있다. 그뿐만 아니라 다이어트에도 좋다. 블루베리의 폴리페놀 성분은 체내 지방세포를 녹여주는 역할을 한다. 하루 권장량은 성인기준 50g 전후로, 20~30알 정도이다.</p>
        <h3>아몬드</h3>
        <p>혈관질환에 좋은 오메가3, 섬유소, 비타민 E가 풍부해 항산화 효과가 높으며 콜레스테롤 수치를 낮추는 L-아르기닌 등의 좋은 영양소도 들어 있다. 또한, 식욕을 감소시키고 뇌 내 행복감을 촉진하는 세로토닌 분비를 증가시키는 것으로 나타났다. 특히 껍질에 비타민 E, 플라보노이드, 카테킨 등의 항산화 성분이 풍부하니 껍질째 먹는 것이 좋다. </p>
    </div>
</section>
```

## column-span 속성 - 여러 단을 하나로 합치기 

- 여러개로 나난 단의 흐름을 따라가다가 중간에 단을 합쳐 내용을 표시해야 할 경우 

```css
column-span: 1 | all
```

|속성 값|설명|
|---|----|
|1|단을 하나만 합치는 것이므로 합치지 않는 것과 같습니다. 기본값|
|all|전체 단ㅇ늘 하나로 합쳐 표현합니다. 단의 일부만 합칠 수는 없습니다.|

```html
<style>
    .no-col{
        ...
        column-span:all;
    }
</style>

<section>
    <h2>건강에 좋은 식품 - Super Food</h2>
    <div class="multi">
        <h3>코코넛 오일</h3>
        <p>남미 파나마에서는 “코코넛오일 한 컵이면 모든 병이 낫는다”라고 이야기할 정도로 그 효능이 뛰어나다. 코코넛 오일에 들어있는 중사슬 지방산은 콜레스테롤 수치에 나쁜 영향을 주지 않는 건강한 지방산이다. 또 라우르산이 풍부해 세균을 물리치고 염증을 가라앉히는 효과가 있다. 하루 권장량은 성인기준 2~4스푼(30~40mL) 정도이다.</p>
        <h3>아보카도</h3>
        <p>나무에서 열리는 버터라고 불릴 만큼 몸에 좋은 지방인 오메가 3와 단백질, 비타민 E와 같은 항산화 성분이 풍부한 과일이다. 알파 카로틴이 풍부하게 들어 있어 여러 항암 효과가 뛰어난 것으로 알려져 있다. 그뿐만 아니라 세포의 콜라겐 합성을 도와 피부 탄력을 높이는 데 도움을 준다. 하루 권장량은 성인기준 1개이며, 꾸준히 섭취하면 콜레스테롤 수치를 낮춰준다.</p>
        <h3>케일</h3>
        <p>케일은 브로콜리, 양배추, 유채, 청경채와 같은 배추과 식물로써 세계보건기구에서 최고의 녹황색 채소로 선정되었다. 베타카로틴과 엽록소가 풍부해 체내 유전자를 회복하도록 돕는 항암효과가 뛰어나다. 또한, 위염, 위궤양에 좋은 비타민 U와 유산균을 늘리는 비타민 M과 같은 식물성 영양소를 함유하고 있다. 하루 권장량은 성인기준 150g 정도이다.</p>
        <h3>블루베리</h3>
        <p>블루베리는 우리 몸이 산화하는 현상을 막아주는 '항산화 물질'이 가장 많은 식품으로 알려졌다. 미국 농무부 인간영양연구소에서 밝힌 자료에 따르면 블루베리의 '안토시아닌'이라는 물질은 시력 향상에 뛰어난 효과가 있다. 그뿐만 아니라 다이어트에도 좋다. 블루베리의 폴리페놀 성분은 체내 지방세포를 녹여주는 역할을 한다. 하루 권장량은 성인기준 50g 전후로, 20~30알 정도이다.</p>
        <div class="no-col">
            <h3>아몬드</h3>
            <p>혈관질환에 좋은 오메가3, 섬유소, 비타민 E가 풍부해 항산화 효과가 높으며 콜레스테롤 수치를 낮추는 L-아르기닌 등의 좋은 영양소도 들어 있다. 또한, 식욕을 감소시키고 뇌 내 행복감을 촉진하는 세로토닌 분비를 증가시키는 것으로 나타났다. 특히 껍질에 비타민 E, 플라보노이드, 카테킨 등의 항산화 성분이 풍부하니 껍질째 먹는 것이 좋다. 하루 권장량은 30g(23알 내외) 정도이며, 과도하게 섭취하면 장의 흡수기능이 저하되니 주의해야 한다.</p>
        </div>
    </div>
</section>
```

---
# 표 스타일

## caption-side 속성 - 표 제목 위치 정하기

- 기본적으로 캡션은 표의 위쪽에 표시되지만 caption-size 속성을 이용하면 캡션의 위치를 표 아래쪽으로 옮길 수 있습니다.

```css
caption-side: top | bottom
```

|속성 값|설명|
|---|----|
|top|캡션을 표의 윗부분에 표시합니다. 기본값|
|bottom|캡션을 표의 아랫부분에 표시합니다.|

## border 속성 - 표 테두리 스타일 결정하기

- 표를 삽입할 떄 기본적으로 \<table\> 태그의 border 속성을 이용해 \<table border="1"\> 처럼 사용하면 표에 테두리를 그릴 수 있습니다. 
- 여기에 CSS의 border 속성을 이용해 테두리 색상이나 형태, 너비 등을 지정할 수 있습니다. 

```html
    <style>
			body{
				font-family:"맑은 고딕", "고딕", "굴림";
			}
			.table1 {
				border:1px solid black;
			}
			.table1 td {
				border:1px dotted black;
				padding:10px;
				text-align:center;
			}
    </style>

    <table class="table1">
        ...
    </table>
```

## border-collapse 속성 - 테두리 통합, 분리하기 

- \<table\>태그와 \<td\>태그에서 border 속성을 사용하면 두 줄로 표시되는데 이때 border-collapse 속성을 이용하면 표의 바깥 테두리와 셀의 각 테두리가 떨어져 있는 것을 그대로 둘 것인지, 두 테두리를 하나로 합칠 것인지 결정할 수 있습니다.

```css
border-collapse: collapse | separate
```

|속성 값|설명|
|---|----|
|collapse|테두리를 하나로 합쳐 표시합니다.|
|separate|테두리를 따로 표시합니다. 기본값|

```html
<style>
    .table1 {
	    border:1px solid black;
		border-collapse:collapse;
	}
	.table1 td {
		border:1px dashed black;
		padding:10px;
		text-align:center;
	}
</style>

<table class="table1">
    ...
</table>
```

## border-spacing 속성 - 인접한 셀 테두리 사이 거리 지정하기

- border-spacing 속성은 border-collapse: separate를 사용해 셀들을 분리했을 경우, 인접한 셀 테두리 사이의 거리를 지정합니다.

```css
border-spacing: <크기>
```

|속성 값|설명|
|---|----|
|\<크기\>|px이나 em등 크기의 단위를 직접 지정합니다.|

- 표에서 테두리를 하나로 합치지 않고 셀의 테두리 사이 간격을 좌우 20px, 상하 10px로 지정합니다(table1).
- 만약 바깥 테두리를 따로 지정하지 않는다면 셀의 테두리만 표시됩니다(table2).

```html
<!DOCTYPE html>
<html lang="ko">
	<head>
		<meta charset="utf-8">
		<title>표 스타일</title>
    <style>
			body{
				font-family:"맑은 고딕", "고딕", "굴림";
			}
			table {
				margin-bottom:50px;
			}
			.table1 {
				border:1px solid black;
				border-collapse:separate;
				border-spacing:20px 10px;
			}
			.table2 {
				border-collapse:separate;
				border-spacing:20px 10px;				
			}
			td {
        border:1px solid black;
        padding:10px;
        text-align:center;
      }
		</style>
	</head>
	<body>		
		<table class="table1">
			<caption>프로축구 경기 일정</caption>
			<tr>
				<td>울산</td>
				<td>울산 vs 인천</td>
			</tr>		
			<tr>
				<td>부산</td>
				<td>부산 vs 대전</td>
			</tr>		
			<tr>
				<td>서울</td>
				<td>서울 vs 강원</td>
			</tr>		
		</table>
		<table class="table2">
				<caption>프로축구 경기 일정</caption>
				<tr>
					<td>울산</td>
					<td>울산 vs 인천</td>
				</tr>		
				<tr>
					<td>부산</td>
					<td>부산 vs 대전</td>
				</tr>		
				<tr>
					<td>서울</td>
					<td>서울 vs 강원</td>
				</tr>		
			</table>
	</body>	
</html>
```

## empty-cells 속성 - 빈 셀의 표시 여부 지정하기 

- border-collapse: separate를 사용해 셀들을 분리했을 경우, empty-cells 속성을 사용해 내용이 없는 빈 셀들의 표시 여부를 지정합니다.

```css
empty-cells: show | hide
```

|속성 값| 설명                             |
|---|--------------------------------|
|show| 빈 셀 주위에 테두리를 그려 빈 셀을 표시합니다. 기본값|
|hide|빈 셀에 테두리를 그리지 않고 비워 둡니다.|

```html
<!DOCTYPE html>
<html lang="ko">
	<head>
		<meta charset="utf-8">
		<title>표 스타일</title>
    <style>
			body{
				font-family:"맑은 고딕", "고딕", "굴림";
			}
			.schedule {
				border-collapse:separate;
				margin:20px;
			}
			td {
				border:1px solid black;
				padding:10px;
				text-align:center;				
			}
			#tb1 td{
				empty-cells:show;
			}
			#tb2 td {
				empty-cells:hide;
			}
		</style>
	</head>
	<body>		
		<table class="schedule" id="tb1">
			<caption>프로축구 경기 일정</caption>
			<tr>
				<td>울산</td>
				<td>울산 vs 인천</td>
				<td>TV 중계</td>
			</tr>		
			<tr>
				<td>부산</td>
				<td>부산 vs 대전</td>
				<td></td>
			</tr>		
			<tr>
				<td>서울</td>
				<td>서울 vs 강원</td>
				<td></td>
			</tr>					
		</table>

		<table class="schedule" id="tb2">
			<caption>프로축구 경기 일정</caption>
			<tr>
				<td>울산</td>
				<td>울산 vs 인천</td>
				<td>TV 중계</td>
			</tr>
			<tr>
				<td>부산</td>
				<td>부산 vs 대전</td>
				<td></td>
			</tr>
			<tr>
				<td>서울</td>
				<td>서울 vs 강원</td>
				<td></td>
			</tr>
		</table>
	</body>
</html>
```

## width, height 속성 - 표 너비와 높이 지정하기

```css
table {
    border-collapse: collapse;
    width: 300px;  
}
```

## table-layout 속성 - 콘텐츠에 맞게 셀 너비 지정하기

- table-layout 속성을 이용하면 셀 안의 내용 양에 따라 셀 너비를 변하게 할지, 고정시킬지를 결정할 수 있습니다.

|속성 값|설명|
|---|----|
|fixed|셀 너비를 고정합니다. 즉, 셀 내용에 따라 너비가 달라지지 않습니다.|
|auto|셀 내용에 따라 셀의 너비가 달라집니다. 기본값|

- table-layout 속성을 fixed로 지정하면 다른 셀의 너비 떄문에 셀이 한쪽으로 몰리는 것을 방지할 수 있습니다.
- table-layout: fixed로 설정해 너비를 고정하면 셀 너비보다 긴 내용은 셀 밖으로 밀려나가 버립니다. 
- 각 셀의 너비를 고정한 상태에서 셀 너비 안에 셀 내용을 표시하려면 word-break: break-all 속성을 추가해야 합니다. 
- 또한 예상치 못했던 줄 바꿈이 생기면 높이 값(height)도 예측하기 쉽지 않기 때문에 셀의 height 속성도 auto로 지정해야 합니다.

```html
<!DOCTYPE html>
<html lang="ko">
	<head>
		<meta charset="utf-8">
		<title>표 스타일</title>
    <style>
			body{
				font-family:"맑은 고딕", "고딕", "굴림";
			}
			table, td {
				border:1px solid #ccc;
			}
			.table1 {
				border-collapse:collapse;
				width:300px;
				table-layout:fixed;
				word-break:break-all;
				height:auto;
			}			
			.table1 td {
				width:150px;
				border:1px solid black;
				padding:5px;
			}
		</style>
	</head>
	<body>
		<h1>Table Layout</h1>
		<table class="table1">
			<tr>
				<td>
					한글로띄어쓰기없기길게붙여쓰기
				</td>
				<td>
					long_description_without_space				
				</td>
			</tr>
		</table>
	</body>
</html>
```

## text-align 속성 - 셀 안에서 수평 정렬하기

- 셀 안에서 텍스트의 수평 정렬 방법을 지정

```html
text-align: left | right | center
```

## vertical-align 속성 - 셀 안에서 수직 정렬하기

- 수직 정렬 방법을 지정하는 속성이기 때문에 inline이나 inline-block으로 배치한 요소의 새로 정렬 방법으로 지정합니다.

```
vertical-align: baseline | top | bottom | middle | sub | super | text-top | text-bottom | <길이 값> | <백분율 값> 
```

|속성 값|설명|
|---|----|
|baseline|인라인 요소의 기준선을 부모 요소의 기준선(baseline)에 맞춥니다.|
|sub|인라인 요소의 기준선을 부모 요소의 아래 첨자 위치에 맞춥니다.|
|super|인라인 요소의 기준선ㅇ늘 부모 요소의 위 첨자 위치에 맞춥니다.|
|top|인라인 요소의 윗부분을 부모 요소의 윗부분에 맞춥니다.|
|middle|인라인 요소의 중앙 부분을 부모 요소의 기준선에서 x-높이(소문자 x의 높이 값)의 반만큼 올려서 맞춥니다.|
|bottom|인라인 요소의 아랫부분을 부모 요소의 아랫부분에 맞춥니다.|
|text-top|인라인 요소의 윗부분을 부모 요소 글꼴의 윗부분에 맞춥니다.|
|text-bottom|인라인 요소의 아랫부분을 부모 요소 글꼴의 아랫부분에 맞춥니다.|
|\<길이 값\>|기준선을 0px로 생각하고 길이 값이 양수면 기준선 위로, 음수면 기준선 아래로 지정한 크기만큼 옮깁니다.|
|\<백분율 값\>|기준선을 0%로 생각하고 line-height의 몇 %인지에 따라 양수면 위로, 음수면 아래로 옮깁니다.|

- 표의 셀에서 사용할 경우 기준선이나 위, 아래, 가운데 등으로 정렬할 수 있습니다. 

|속성 값|설명|
|---|----|
|baseline|셀의 기준선에 내용의 기준선을 맞춥니다.|
|top|패딩의 위쪽 가장자리에 내용의 윗부분을 맞춥니다.|
|middle|패딩 박스의 중앙에 내용을 맞춥니다.|
|bottom|패딩의 아래쪽 가장자리에 내용의 아랫부분을 맞춥니다.|


```html
<style>
    .va1 { vertical-align:top; }
    .va2 { vertical-align:bottom; }
    .va3 { vertical-align:middle; }
</style>

<table>
    <caption>vertical-alignment</caption>
    <tr>
        <td class="va1">alignment</td>
        <td class="va2">alignment</td>
        <td class="va3">alignment</td>
    </tr>
</table>
```