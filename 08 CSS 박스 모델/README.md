# CSS와 박스 모델 

> CSS 박스 모델이란 웹 문서의 내용을 박스 형태로 정의하는 방법을 가리킵니다. 이 박스 모델들이 모여 웹 문서를 이룹니다. 또한 그 안에는 마진과 패딩, 테두리 등 여러 겹의 박스가 들어 있습니다.

## 블록 레벨 요소와 인라인 레벨 요소

### 블록 레벨(block-level) 요소
- 태그를 사용해 요소를 삽입했을 때 혼자 한 줄을 차지하는 요소입니다.
- 한 줄을 차지한다는 것은 해당 요소의 너비가 100%라는 의미로 그 요소의 왼쪽이나 오른쪽에 다른 요소가 올 수 없습니다.
- 너비나 마진, 패딩 등을 이용해 크기나 위치를 지정하려면 블록 레벨 요소여야 합니다.
- \<div\> 태그나 \<p\> 태그 등이 블록 레벨 요소를 만드는 대표적인 태그 입니다.

### 인라인 레벨(inline-level) 요소
- 줄을 차지 하지 않는 요소 
- 화면에 표시되는 콘텐츠만큼 영역을 차지하고 나머지 공간에는 다른 요소가 올 수 있습니다. 따라서 한 줄에 여러 개의 인라인 레벨 요소를 표시할 수 있습니다. 
- \<img\> 태그나 \<string\> 태그 등이 인라인 레벨 요소를 만드는 태그 입니다.

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/08%20CSS%20%EB%B0%95%EC%8A%A4%20%EB%AA%A8%EB%8D%B8/images/1.png)

- 다음은 블록 레벨 요소와 인라인 레벨 요소를 만드는 대표적인 태그들 입니다.

|종류|해당 태그|
|---|----|
|블록 레벨 태그|\<p\>,\<h1\>~\<h6\>, \<ul\>, \<ol\>, \<div\>, \<blockquote\>,\<form\>, \<hr\>, \<table\>, \<fieldset\>, \<address\>|
|인라인 레벨 태그|\<img\>, \<object\>, \<br\>, \<sub\>, \<sup\>, \<span\>, \<input\>, \<textarea\>, \<label\>, \<button\>|

## 박스 모델(box model) - 박스 형태의 콘텐츠

- 웹 문서의 블록 레벨 요소들은 모두 박스 형태입니다. 
- 예를 들어 \<p\> 태그를 사용하는 텍스트 단락은 블록 레벨 요소인데 텍스트 단락 앞뒤에 빈 줄이 생기면서 텍스트 단락이 하나의 박스 형태를 가집니다.
- 스타일 시트에서는 이렇게 박스 형태인 요소를 <code>박스 모델(box model) 요소</code>라고 부릅니다.
- 박스 모델은 실제 콘텐츠 영역, 박스와 콘텐츠 영역 사이의 여백인 패딩(padding), 박스의 테두리(border), 그리고 여러 박스 모델 사이의 여백인 마진(margin) 등의 요소로 구성됩니다.

![image2](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/08%20CSS%20%EB%B0%95%EC%8A%A4%20%EB%AA%A8%EB%8D%B8/images/2.png)


## width, height 속성 - 콘텐츠 영역의 크기

- width : 컨텐츠 영역의 너비
- height: 컨텐츠 영역의 높이  

```
width: <크기> | <백분율> | auto
height: <크기> | <백분율> | auto
```

|속성 값|설명|
|---|----|
|\<크기\>|너비나 높이 값을 px(픽셀)이나 cm(센티미터) 같은 단위와 함께 수치로 지정합니다.|
|\<백분율\>|박스 모델을 포함하는 부모요소를 기준으로 너비나 높이 값을 백분율(%)로 지정합니다.|
|auto|박스 모델의 너비와 높이 값이 콘텐츠 양에 따라 자동으로 결정됩니다. 기본 값입니다.|

```html
<!doctype html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>박스모델</title>
	<style>
		.box1{
			width:400px; /* 고정 너비 */
			height:100px; /* 높이 */
			background:#ff6a00; /* 배경색 */
		}
		.box2{
			width:50%; /* 가변 너비 - 브라우저 창 너비의 50% */
			height:100px; /* 높이 */
			background:#0094ff; /* 배경색 */
		}
		div {
			margin:10px; /* div 간의 여백 */
		}
	</style>
</head>
<body>
	<div class="box1"></div>
	<div class="box2"></div>
</body>
</html>
```

### 실제 콘텐츠 크기 계산하기 
- CSS 박스 모델의 width 속성은 콘텐츠 영역의 너비를 말하기 때문에 여러 요소를 웹문서에 배치할 때 실제 박스가 차지하는 너비는 width 값에 좌우 패딩 두께와 좌우 테두리 두께를 합쳐 계산합니다.
- 모던 브라우저에서 박스 모델 전체 너비 = width 값 + 좌우 패딩 + 좌우 테두리


## display 속성 - 화면 배치 방법 결정하기 
- display 속성을 사용하면 블록레벨 요소를 인라인 레벨 요소로 바꾸거나 인라인 레벨 요소를 블록 레벨 요소로 바꿀 수 있습니다. 
- 세로로 표시되는 목록을 가로 내비게이션으로 바꿀 때, 한 줄로 표시되는 이미지에 여백과 테두리를 추가해 갤러리로 표시할 때 이 방법을 사용합니다. 

```
display: none | contents | block | inline | inline-block | table | table-cell 등 
```

### block 속성 값
- 해당 요소를 블록 레벨로 지정합니다. 
- \<img\> 태그 같은 인라인 레벨 요소도 블록 레벨 요소로 바꿀 수 있습니다.

```html
<style>
    #block img {
        display:block;
        margin:10px;
    }
</style>

<div id="inline">
    <img src="images/pic1.jpg">
    <img src="images/pic2.jpg">
    <img src="images/pic3.jpg">
</div>
<div id="block">
    <img src="images/pic1.jpg">
    <img src="images/pic2.jpg">
    <img src="images/pic3.jpg">
</div>
```

### inline 속성 값 
- 블록 레벨 요소를 인라인 레벨 요소로 바꿀 수 있습니다.
- 서로 다른 줄에 배치되는 요소들을 한 줄로 함께 표기하기 위해 사용되는데 주로 목록에서 사용됩니다.

```html
<style>
    nav ul li {
        display: inline;
        ...
    }
</style>

<nav>
    <ul>
        <li><a href="#">애완견 종류</a></li>
        <li><a href="#">입양하기</a></li>
        <li><a href="#">건강돌보기</a></li>
        <li><a href="#">더불어살기</a></li>
    </ul>
</nav>
```

### inline-block 속성 값
- 웹 요소를 display: inline으로 지정하면 한 줄로 배치할 수는 있지만 너비나 높이, 위 아래 마진, float 같은 값이 정확히 적용되지 않습니다. 
- 요소를 인라인 레벨로 배치하면서 내용에는 블록 레벨 속성을 지정하고 싶다면 display 속성 값 중 inline-block을 사용하면 됩니다. 
- 이 속성은 블록 레벨 요소와 인라인 레벨 요소 두 가지 특성 모두 가집니다.

```html
<style>
    nav ul li {
        display: inline-block;
        margin:20px;
    }
</style>

<nav>
    <ul>
        <li><a href="#">애완견 종류</a></li>
        <li><a href="#">입양하기</a></li>
        <li><a href="#">건강돌보기</a></li>
        <li><a href="#">더불어살기</a></li>
    </ul>
    <h2>애완견 종류</h2>
</nav>
```

### none 속성 값 
- 이 속성 값을 지정하면 해당 요소를 화면에 아예 표시하지 않습니다. 
- visibility: hidden; 도 비슷한 역할을 하는데 visibility 속성은 화면에서 감추기만 할 뿐 원래 요소가 있는 공간은 그대로 차지하지만 display: none;은 아예 공간조차 차지하지 않습니다.

### 기타 display 속성 값들

|속성 값| 설명                                                                                                                          |
|---|-----------------------------------------------------------------------------------------------------------------------------|
|inherit| 상위 요소의 display 속성을 상속받습니다.                                                                                                  |
|table| 블록 레벨의 표로 만듭니다.                                                                                                             |
|inline-table| 인라인 레벨의 표로 만듭니다\<table\> 태그 사용한 것처럼).                                                                                       |
|table-row| 표의 행으로 만듭니다.(\<tr\> 태그 사용한 것처럼).                                                                                            |
|table-row-group| 표의 행 그룹으로 만듭니다.\<tbody\>태그 사용한 것처럼).                                                                                        |
|table-header-group| 표의 제목 영역(header) 그룹으로 만듭니다(\<thead\> 태그 사용한 것처럼).                                                                           |
|table-footer-group| 표의 요약 영역(footer) 그룹으로 만듭니다(\<tfoot\> 태그 사용한 것처럼).                                                                           |
|table-column| 표의 열로 만듭니다(\<col\> 태그 사용한 것처럼).                                                                                             |
|table-column-group| 표의 열 그룹으로 만듭니다(\<colgroup\> 태그 사용한 것처럼).                                                                                    |
|table-cell| 표에서 하나의 셀로 만듭니다(\<td\>나 \<th\> 태그 사용한 것처럼).                                                                                 |
|table-caption| 표의 캡션을 만듭니다(\<caption\> 태그 사용한 것처럼).                                                                                        |
|list-item| 목록의 항목을 표시할 수 있도록 기본적인 블록 박스와 표시자 박스를 만듭니다(\<li\> 태그 사용한 것처럼).<br>'기본적인 블록 박스'란 항목의 내용이 표시되는 부분이며, '표시자 박스'란 블릿이 표시되는 부분입니다.|

---
# 테두리 관련 속성들


## border-style 속성 - 테두리 스타일 지정하기 

```
border-style: none | hidden | dashed | dotted | double | groove | inset | outset | ridge | solid 
```

|속성 값|설명|
|---|----|
|none|테두리가 나타나지 않습니다. 기본 값입니다.|
|hidden|테두리가 나타나지 않습니다. border-collapse: collapse일 경우, 다른 테두리도 표시되지 않습니다.|
|dashed|테두리를 짧은 선(직선으로 된 점선)으로 표시합니다.|
|dotted|테두리를 점선으로 표시합니다.|
|double|테두리를 이중선(겹선)으로 표시합니다. 두 선 사이의 간격은 border-width 값으로 지정합니다.|
|groove|테두리를 창에 조작한 것처럼 표시합니다. 홈이 파인 듯 입체적으로 보입니다.|
|inset|border-collapse:separate일 경우, 전체 박스 테두리가 창에 박혀 있는 것처럼 표시되고 border-collapse:collapse일 경우, groove와 똑같이 표시됩니다.|
|outset|border-collapse:separate일 경우, 전체 박스 테두리가 창에서 튀어나온 것처럼 표시되고 border-collapse:collapse일 경우, ridge와 똑같이 표시됩니다.|
|ridge|테두리를 창에서 튀어나온 것처럼 표시합니다.|
|solid|테두리를 실선으로 표시합니다.|

> border-collapse 속성은 표에서 셀과 셀 사이의 테두리가 두 번 그려지는 것을 겹쳐 하나로 표시할 것인지(border-collapse:collapse), 두 개로 표시할 것인지(border-collapse
> :separate)를 지정하는 것입니다.

```html
	<style>
		div {
			width:200px;
			height:100px;
			display:inline-block;
			margin:15px;			
			border-width:5px;  /* 테두리 굵기 */
		}
		.box1 { border-style:solid; }  /* 실선 */
		.box2 { border-style:dotted; }  /* 점선 */
		.box3 { border-style:dashed; }  /* 선으로 된 점선 */
	</style>

	<div class="box1"> </div>
	<div class="box2"> </div>
	<div class="box3"> </div>
```

## border-width 속성 - 테두리 두께 지정하기


```css
border-top-width: <크기> | thin | medium | thick
border-right-width: <크기> | thin | medium | thick
border-botom-width: <크기> | thin | medium | thick
border-left-width: <크기> | thin | medium | thick
border-width: <크기> | thin | medium | thick
```
- border-width 속성에는 border-top-width, border-right-width, border-bottom-width, border-left-width가 있는데, 이 속성들은 차례대로 위쪽, 오른쪽, 아래쪽, 왼족 테두리 두께를 지정합니다.
- border-width 속성을 이용해 한거번에 지정할 수도 있습니다.
- 속성 값이 2개라면 위아래와 좌우를 묶어 지정하고 4개라면 시계 방향(top -> right -> bottom -> left)으로 적용합니다.

```css
.box1 { border-width: 2px; }
```
> 네 방향의 테두리 굵기를 모두 2px로 표시합니다.

```css
.box2 { border-width: thick thin; }
```
> 위와 아래는 thick(굵게), 왼쪽과 오른쪽은 thin(가늘게)으로 표시합니다.

```css
.box3 { border-width: 5px 10px 15px 20px; }
```
> 네 방향의 테두리 굵기를 모두 다르게 해 차례대로 top, right, bottom, left의 두께를 지정합니다.

## border-color 속성 - 테두리 색상 지정하기

```css
border-top-color: <색상>
border-right-color: <색상>
border-bottom-color: <색상>
border-left-color: <색상>
border-color: <색상>
```
> 박스 모델의 테두리를 지정할 때 border-color 속성만 사용해서는 화면에서 결과를 확인할 수 없고 border-width 속성과 border-style 속성을 이용해 미리 테두리 두께와 스타일을 결정해야 합니다.

- border-color 속성에는 border-top-color, border-right-color, border-bottom-color, border-bottom-color, border-left-color가 있습니다. 이 속성들은 차례대로 위쪽, 오른쪽, 아래쪽, 왼쪽 테두리 색상을 지정합니다.
- border-color 속성을 이용하면 네 방향 테두리의 색상을 한꺼번에 지정할 수 있습니다.

```html
    <style>
		div {
			width:200px;
			height:100px;
			display:inline-block;
			margin:15px;			
			border-style:dashed;  /* 테두리 스타일 - 선으로 된 점선 */
			border-width:2px; /* 테두리 굵기 - 2px */
		}
		.box1 { border-color:red;	}  /* 색상 - 빨강 */
		.box2 { border-color:blue; }  /* 색상 - 파랑 */
	</style>

    <div class="box1"> </div>
    <div class="box2"> </div>	
```

## border 속성 - 테두리 스타일 묶어 지정하기 

```css
border-top: <두께> <색상> <스타일>
border-right: <두께> <색상> <스타일>
border-bottom: <두께> <색상> <스타일>
border-left: <두께> <색상> <스타일>
border: <두께> <색상> <스타일>
```

- 네 방향의 테두리 스타일을 다르게 지정하고 싶다면 border-top이나 border-right 처럼 속성 이름에 방향을 함께 써 따로 지정하고
- 네 방향의 테두리 스타일이 같다면 같단히 border 속성을 이용할 수 있습니다. 
- 두께, 색상, 스타일 순서는 상관 없습니다. 

```html
    <style>
		h1 {
			padding-bottom: 5px;
			border-bottom: 3px solid #ccc; /* 아랫 부분 - 3px짜리 회색 실선*/
		}
		p {
			padding: 10px;
			border: 3px dotted black; /* 모든 방향 - 3px짜리 검정 점선 */
		}
	</style>

    <h1>박스 모델</h1>
    <p>박스 모델은 실제 콘텐츠 영역, 박스와 콘텐츠 영역 사이의 여백인 패딩(padding), 박스의 테두리(border), 그리고 여러 박스 모델 간의 여백인 마진(margin) 등의 요소로 구성되어 있습니다. </p>	
```

## border-radius 속성 - 박스 모서리 둥글게 만들기 

```css
border-top-left-radius: <크기> | <백분율>
border-top-right-radius: <크기> | <백분율>
border-bottom-right-radius: <크기> | <백분율>
border-bottom-left-radius: <크기> | <백분율>
border-radius: <크기> | <백분율>
```

- 모서리 원의 반지름이 border-radius 속성 값이 됩니다. 이 값은 크기를 직접 지정하거나 백분율로 지정할 수 있습니다.

|속성 값|설명|
|---|----|
|\<크기\>|둥글게 처리할 반지름 크기를 px이나 em같은 단위와 함께 수치로 표시합니다.|
|\<백분율\>|현재 요소의 크기를 기준으로 둥글게 처리할 반지름 크기를 %로 지정합니다|

```html
    <style>
		.round {
			border:2px solid red; /* 2px짜리 빨강 실선 */
			border-radius:20px;  /* 모서리 20px 만큼 라운딩 */
		}
		#bg {
			background:url(images/pic1.jpg) no-repeat; /* 배경 이미지 */			
			background-size:cover;  /* 영역을 다 채우게 */
		}
	</style>

    <div class="round"></div>
    <div class="round" id="bg"></div>
```

- 네 모서리를 다르게 조절하고 싶다면 border-top-left-radius(왼쪽 위), border-top-right-radius(오른쪽 위), border-bottom-left-radius(왼쪽 아래), border-bottom-right-radius(오른쪽 아래) 속성을 사용해 각 모서리의 반지름 값을 따로 지정할 수도 있습니다. 


```css
.round1 {
    border: 2px solid blue;  /* 2px짜리 파랑 실선 */
    border-top-left-radius: 20px;  /* 왼쪽 위 라운딩 - 20px */
    border-top-right-radius: 20px;  /* 오른쪽 위 라운딩 - 20px */
}
```

- border-radius 속성을 이용하면 네 방향 모서리를 한꺼번에 지정할 수 있다.

```css
.round2 {
    background: #0c78c8; /* 배경 색 */
    border-radius: 20px 70px;  /* 라운딩 - 20px 70px 20px 70px */
}
```

### 타원 형태로 둥글게 만들기

- 타원 형태로 둥글게 만들고 싶다면 가로 반지름 크기와 세로 반지름 크기를 함께 지정

```css
border-top-left-radius: <가로 크기> <세로 크기>
border-top-right-radius: <가로 크기> <세로 크기>
border-bottom-right-radius: <가로 크기> <세로 크기>
border-bottom-left-radius: <가로 크기> <세로 크기>
border-radius: <가로 크기> <세로 크기>
```

- 각 모서리마다 다로 지정한다면 가로 반지름과 세로 반지름을 차례로 입력하면 되지만 네 방향을 한꺼번에 지정하기 위해 border-radius 속성을 이용할 경우, 가로 반지름과 세로 반지름 사이에 슬래시(/)를 넣어 구분합니다.

```css
    <style>
		div {
			width:200px;
			height:100px;
			display:inline-block;
			margin:15px;
			border:2px solid black;
			background:#ffd800;			
		}
		.round1 { border-top-left-radius:100px 50px; } /* 왼쪽 위 라운딩 */
		.round2 { border-bottom-right-radius:50% 30%; }
		.round3 { border-top-right-radius:50px;}
	</style>
	
	<div class="round1"></div>
	<div class="round2"></div>
    <div class="round3"></div>
```

## box-shadow 속성 - 선택한 요소에 그림자 효과 내기 

```css 
box-shadow: none | <그림자 값> [, <그림자 값>]*;
<그림자 값> = <수평 거리> <수직 거리> <흐림 정도> <번짐 정도> <색상> inset 
```

- box-shadow 속성에서 수평 거리와 수직 거리는 반드시 지정해야 하며(필수) 기타 속성 값은 옵션이므로 필요할 때만 사용하면 됩니다.

|속성 값|설명|
|---|----|
|\<수평 거리\>|그림자의 수평 옵셋 거리(수평으로 얼마나 떨어져 있는지)입니다. 양수 값은 요소의 오른쪽, 음수 값은 요소의 왼쪽에 그림자를 만듭니다. 필수 속성입니다.|
|\<수직 거리\>|그림자의 수직 옵셋 거리(세로로 얼마나 떨어져 있는지)입니다. 양수 값은 요소의 아래쪽, 음수 값은 요소의 위쪽에 그림자를 만듭니다. 필수 속성입니다.|
|\<흐림 정도\>|그림자의 흐림 정도(blur radius)를 지정합니다. 이 값을 생략하면 0을 기본 값으로 해 진한 그림자를 표시합니다. 이 값이 커질수록 부드러운 그림자를 표시하며 반대로 음수 값은 사용할 수 없습니다.|
|\<번짐 정도\>|그림자의 번지는 정도를 나타냅니다. 양수 값을 사용하면 그림자가 모든 방향으로 퍼져 나가기 때문에 그림자가 박스보다 크게 표시됩니다. 반대로 음수 값은 그림자가 모든 방향으로 축소되어 보입니다. 기본 값은 0입니다.|
|\<색상\>|그림자의 색상을 지정합니다. 한 가지만 지정할 수도 있고 공백으로 구분해 여러 개의 색상을 지정할 수도 있습니다. 필요한 경우에만 사용하는 옵션 값이며 기본 값은 현재 글자 색입니다.|
|\<색상\>|이 키워드를 함께 표시하면 안쪽 그림자로 그립니다. 필요한 경우에만 사용하는 옵션 값입니다.|

- 두 개 이상의 그림자를 사용할 경우, 쉼표로 그림자 속성 값을 구분해 나열하며 앞의 그림자부터 차례로 적용됩니다.

```html
    <style>
		div {
			width:200px;
			height:100px;
			display:inline-block;
			margin:15px;
			border:2px solid;
			border-radius:20px;
		}
		.box1{ box-shadow:2px -2px 5px 0px black;}
		.box2{ box-shadow:5px 5px 15px 5px gray;}
	</style>

    <div class="box1"></div>
    <div class="box2"></div>
```

---

# 여백을 조절하는 속성들

## margin 속성 - 요소 주변 여백 설정하기 

- 마진(margin) : 현재 요소 주변의 여백입니다. 마진을 이용하면 한 요소와 다른 요소 사이의 간격을 조절할 수 있습니다.

```css
margin-top: <크기> | <백분율> | auto
margin-right: <크기> | <백분율> | auto
margin-bottom: <크기> | <백분율> | auto
margin-left: <크기> | <백분율> | auto
margin: <크기> | <백분율> | auto
```

|속성 값| 설명                                                            |
|---|---------------------------------------------------------------|
|\<크기\>| 너비나 높이 값을 px(픽셀)이나 cm(센티미터) 같은 단위와 함께 수치로 지정합니다. 예) margin: 10px;|
|\<백분율\>| 박스 모델을 포함하고 있는 부모 요소 기준으로 너비나 높이 값을 %로 지정합니다. 예) margin: 0.1%;|
|auto|display 속성에서 지정한 값에 맞게 적절한 값을 자동으로 지정합니다.|


- margin 속성에 값이 하나만 있다면 그 값은 네 방향에 모두 적용됩니다. 
- 값이 2개라면 첫 번째 값은 서로 마주보는 margin-top과 margin-bottom 값이고 두 번째 값은 margin-right와 margin-left 값입니다. 

```css
p { margin: 30px 50px; } /* 위 아래 마진 - 30px, 좌우 마진 - 50px */
p { margin: 50px; } /* 네 방향 마진 모두 50px */
```

- margin 값이 4개라면 그 순서는 top -> right -> bottom -> left(시계 방향)입니다.

```css
P { margin: 30px 50px 30px 50px; } 
```

- 값을 3개만 지정했다면 위쪽 마진, 좌우 마진, 아래쪽 마진

```css
p { margin: 30px 20px 50px; } /* 위 마진 - 30px, 좌우 마진 - 20px, 아래 마진 - 50px; */
```

```html
    <style>
		div {
			width:200px;  /* 너비 */
			height:100px;  /* 높이 */
			background:#0094ff;  /* 배경색 */
		}
		.box1 { margin:30px 50px 30px 50px;}  /* 마진 - 30px 50px 30px 50px */
		.box2 { margin:30px 50px;} /* 마진 - 30px 50px 30px 50px */
		.box3 { margin:50px;}  /* 마진 - 50px 50px 50px 50px */
		.box4 { margin:30px 5px 10px; }  /* 마진 - 30px 5px 10px 5px */
	</style>

    <div class="box1"></div>
    <div class="box2"></div>
    <div class="box3"></div>
    <div class="box4"></div>
```

- margin-left와 margin-right를 auto로 지정하면 요소의 너비 값을 뺸 나머지 공간의 좌우 마진을 똑같이 맞춥니다. 이 방법은 웹 요소를 중앙에 배치하려고 할 때 자주 사용합니다.


```html
    <style>
		.box {
			width:200px;  /* 너비 */
			height:300px;  /* 높이 */
			background:#ff6a00;  /* 배경색 */			 
			margin:0 auto; /* 마진 - 0 auto 0 auto */
		}  
	</style>
    <div class="box"></div>
```

## 마진 중첩(margin overlap) 현상

- 요소를 세로로 배치할 경우, 마진과 마진이 만날 때 마진 값이 큰 쪽으로 겹치는 것
- 이런 형산을 마진 중첩(margin overlap) 또는 마진 상쇄(margin collapse)라고 합니다.
- 마진 중첩은 아래 마진과 위 마진이 서로 만날 때 큰 마진 값으로 합쳐지는 것이고 오른쪽 마진과 왼쪽 마진이 만날 경우에는 중첩되지 않습니다.

```html
<style>
    * {
      box-sizing:border-box;
    }
	div {
		width:200px;  /* 너비 */
		height:100px;  /* 높이 */
  		margin:30px;  /* 마진 */
	}
    #box1 {
      background:rgb(0, 77, 243);
    }
    #box2 {
      background:rgb(255, 72, 0);
    }
    #box3 {
      background:rgb(18, 219, 0);
    }
	</style>

    <div id="box1"></div>
    <div id="box2"></div>
    <div id="box3"></div>
```

## padding 속성 - 콘텐츠 영역과 테두리 사이 여백 설정하기

- 패딩(padding) : 콘텐츠 영역과 테두리 사이의 여백, 다시 말해 테두리 안쪽의 여백이라고 생각하면 됩니다.\
- padding 속성은 margin 속성과 사용법이 비슷합니다.

```css
padding-top: <크기> | <백분율> | auto
padding-right: <크기> | <백분율> | auto
padding-bottom: <크기> | <백분율> | auto
padding: <크기> | <백분율> | auto
```

```html
    <style>
		div {
			width:200px;  /* 너비 */
			height:auto;  /* 높이 */
			background:#0094ff;  /* 배경색 */
			display:inline-block;  /* 가로로 배치 */
			margin:15px;  /* 마진 - 15px 15px 15px 15px */
			color:white;  /* 글자색 */
		}
		.box1 { padding:10px 30px 10px 30px;}  /* 패딩 - 10px 30px 10px */
		.box2 { padding:10px 30px;} /* 패딩 - 10px 30px 10px 30px */
		.box3 { padding:10px;}  /* 패딩 - 10px 10px 10px 10px */
	</style>

    <div class="box1">패딩(padding)이란 콘텐츠 영역과 테두리 사이의 여백을 말합니다. </div>
    <div class="box2">패딩(padding)이란 콘텐츠 영역과 테두리 사이의 여백을 말합니다. </div>
    <div class="box3">패딩(padding)이란 콘텐츠 영역과 테두리 사이의 여백을 말합니다. </div>
```
