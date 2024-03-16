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

---
# 여백을 조절하는 속성들