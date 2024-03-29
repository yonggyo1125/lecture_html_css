# 이미지 

## 웹에서 사용하는 이미지 형식 
- 웹 페이지에서 사용할 수 있는 이미지 파일은 크기가 크지 않으면서도 화질이 좋아야 하기 때문에 몇 가지 파일 형식만 사용할 수 있습니다.

|파일 형식|설명|
|---|----|
|GIF(Graphic Interchange Form)|표시할 수 있는 색상 수가 최대 256가지 뿐이지만 다른 이미지 파일 형식에 비해 파일 크기가 작기 때문에 아이콘이나 불릿 등 작은 이미지에 주로 사용합니다. 투명한 배경이나 움직이는 이미지를 만들 수 있다는 장점이 있습니다.|
|JPG/JPEG(Joint Photographic Experts Group)|사진을 위해 개발된 형식으로 GIF보다 다양한 색상과 명암을 표현할 수 있습니다. 저장을 반복하다 보면 화질이 떨어질 수도 있습니다.|
|PNG(Portable Network Graphic)|투명 배경을 만들면서 다양한 색상도 표현할 수 있으며 네트워크용으로 개발되었기 때문에 최근 많이 사용합니다.|


## \<img\> 태그 - 이미지 삽입하기

```html
<img src="경로" [속성="값"]>
```
> 기본형에서 [, ]로 묶은 부분의 기타 속성들은 생략할 수 있습니다.  

```html
<img src="images/cover.jpg" alt="빠른연산">
```

### src 속성 - 이미지 파일 경로 지정하기 

- <code>경로</code> : 현재 HTML 문서에서 이미지 파일까지 찾아가기 위한 길로 이 길이 정확하지 않다면 웹 문서에 이미지가 표시되지 않습니다.

### 내 컴퓨터의 이미지 파일 경로 지정하기
- 이미지 파일의 경로는 웹 문서의 파일 위치를 기준으로 정해집니다.
- 웹 문서 파일과 이미지 파일이 같은 경로에 있다면 src 속성에는 간단히 이미지 파일의 이름만 적으면 됩니다.
- 예를 들어 index.html과 lotus.jpg 파일이 같은 폴더에 있다면 src 속성에 파일 이름만 적으면 됩니다. 

```html
<img src="lotus.jpg">
```

- 웹 문서가 있는 폴더에 하위 폴더를 만들고 그 폴더에 이미지 파일을 저장했다면 src 속성에 하위 폴더와 함께 이미지 파일 이름을 적어야 합니다.
- 예를 들어 images라는 하위 폴더가 있고 거기에 있는 lotus.jpg 파일을 웹 문서에 표시하려면 다음과 같이 작성합니다.

```html
<img src="images/lotus.jpg">
```

> 반대로 한 단계 위로 이동하기 위해서는 '..' 기호를 사용합니다. 이 기호는 같은 레벨에 있는 폴더끼리 파일을 사용할 때 사용합니다. 

```css 
body {
    background-image: url("../images/background.png");
}
```

### 웹 상의 링크를 복사해 이미지 경로 지정하기

- 웹 이미지 파일의 경로를 src 속성의 값으로 지정합니다.
- 웹 이미지는 인터넷에 접속할 수 있어야 화면에 표시됩니다.

```html
<img src="https://www.imdak.com/web/upload/wp/167417/logo.toppc.png">
```

## alt 속성 - 이미지를 설명해 주는 대체 텍스트 

- 이미지를 설명하는 대체 텍스트를 삽입할 때 사용합니다.
- 웹 문서에 삽입한 이미지는 시각적인 요소이기 때문에 시각 장애인들은 그 내용을 알 수 없습니다. 웹 문서를 읽어 주는 화면 낭독기도 문서 상의 텍스트만 읽어 주기 떄문에 이미지를 만나면 그대로 건너뜁니다.
- \<img\> 태그의 alt 속성을 이용하면 이미지에 대한 설명을 넣을 수 있고 alt 속성의 텍스트를 화면 낭독기가 시각장애인에게 읽어 줄 수 있습니다.
- 대체 텍스트를 사용하면 연결 속도가 느리거나 이미지를 제대로 표시할 수 없는 상황에서 이미지 자리에 alt 속성에 쓴 내용이 표시되어 어떤 이미지가 사용되었는지 짐작할 수 있습니다.

```html
<img src="home.jpg" alt="홈으로 가기">
```

## width, height 속성 - 이미지 크기 조정하기

- 이미지 파일을 넣을 때 브라우저 창에 원하는 크기로 조정해 넣고 싶다면 width 속성과 height 속성을 사용하면 된다.
- width 속성과 height 속성을 사용하지 않으면 원본 이미지 크기 그대로 브라우저 화면에 표시됩니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>이미지 삽입하기</title>
</head>
<body>
  <h1>이미지 크기 조절</h1>
  <img src="images/gugudan.jpg" alt="바빠구구단">
  <img src="images/gugudan.jpg" width="250" height="250" alt="바빠구구단">
</body>
</html>
```

## \<figure\>, \<figcaption\> 태그 - 이미지에 설명 글 붙이기 

### \<figure\> 태그 - 설명 글을 붙일 대상 지정
- \<figure\> 태그 안에 \<figcaption\> 태그를 사용해 설명 글을 표시합니다. 
- 이미지만 삽입한다면 \<figure\> 태그를 사용하지 않아도 되지만 이미지에 설명 글을 넣으려면 이미지를 \<figure\> 태그로 묶어 주어야 합니다.

### \<figcaption\> 태그 - 설명 글 붙이기

```html
<figcaption> 설명 글 </figcaption>
```

```html
<figure>
    <img src="image/prod.jpg" alt="예멘 모카 마타리">
    <figcaption>예멘 모카 마타리(Yemen Mocha Mattari)</figcaption>
</figure>
```

---

# 링크 만들기

- <code>링크</code>는 웹 문서가 다른 문서와 구분되는 가장 큰 특징입니다.
- 클릭만 하면 연결된 곳으로 즉시 이동해 웹 사용을 더욱 편리하게 해줍니다.

## \<a\> 태그, href 속성 - 링크 만들기 

- 링크를 만드는 \<a\> 태그는 텍스트와 함께 사용하면 텍스트 링크가 되고 이미지와 함꼐 사용하면 이미지 링크가 됩니다.

```html
<a href="링크할 주소" [속성="속성 값"]>텍스트</a>
<a href="링크할 주소" [속성="속성 값"]><img src="이미지 파일 경로"></a>
```
- \<a\> 태그 안에서 사용할 수 있는 주요 속성

|속성|설명|
|---|----|
|href|링크한 문서나 사이트의 주소를 입력합니다.|
|target|링크한 내용이 표시될 위치(현재 창 또는 새창)을 지정합니다.|
|download|링크한 내용을 보여 주는 것이 아니라 다운로드 합니다.|
|rel|현재 문서와 링크한 문서의 관계를 알려줍니다.|
|hreflang|링크한 문서의 언어를 지정합니다.|
|type|링크한 문서의 파일 유형을 알려줍니다.|

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>링크 만들기</title>
</head>
<body>
	<h1>텍스트 링크 만들기</h1>
	<a href="http://www.easyspub.com">이지스퍼블리싱 홈페이지</a>
	<h1>이미지 링크 만들기</h1>
	<a href="http://www.easyspub.com">
		<img src="images/easyspub.jpg" alt="이지스퍼블리싱 홈페이지로 가기">
	</a>
</body>
</html>
```

### 텍스트 링크의 밑줄과 글자 색 바꾸기

- 텍스트 링크는 기본적으로 밑줄이 있는 파란색(blue)글자로 표시됩니다.
- 텍스트 링크를 클릭해 링크된 내용을 한 번 살펴보고 나면 텍스트 링크 색은 보라색(purple)으로 바귑니다. 
- 텍스트 링크를 누르고 있으면 즉, 링크를 활성화시키면 글자 색은 빨간색(red)으로 바뀝니다.
- 이런 텍스트 링크의 색상들이 사이트 디자인에 어울리지 않는 경우가 많습니다. 그럴 경우 CSS를 이용해 텍스트 링크의 색을 바꾸고 밑줄을 없앨 수 있습니다.

```html
<style>
    a {
        text-decoration: none;
        color: black;  
    }
</style>
```

## target 속성 - 새 탭에서 링크 열기

- target 속성을 사용하면 현재 화면 뿐만 아니라 새로운 화면에서도 링크를 열 수 있습니다. 
- target 속성에서 사용할 수 있는 값

|속성 값|설명|
|---|----|
|_blank|링크 내용이 새 창이나 새 탭에서 열립니다.|
|_self|target 속성의 기본 값으로 링크가 있는 화면에서 열립니다.|
|_parent|프레임을 사용했을 때 링크 내용을 부모 프레임에 표시합니다.|
|_top|프레임을 사용했을 때 프레임에 벗어나 링크 내용을 전체 화면에 표시합니다.|

```html
	<h1>텍스트 링크 만들기</h1>
	<p><a href="http://www.easyspub.com">이지스퍼블리싱 홈페이지(현재 화면)</a></p>
	<p><a href="http://www.easyspub.com" target="_blank">이지스퍼블리싱 홈페이지(새 창 또는 새 탭)</a></p>
```

- 아이프레임과 target 

## 한 페이지 안에서 점프하는 앵커 만들기
- 한 페이지 내에서도 링크를 만들 수 있습니다. 
- <code>앵커(anchor)</code>라고 불리는 이 기능은 페이지가 긴 웹 문서에서 특정 요소를 클릭하면 그 위치로 한 번에 이동하도록 도와줍니다.
- 앵커를 사용하려면 우선 이동하고 싶은 위치마다 id 속성을 이용해 앵커를 만들고 각각 다른 이름을 지정해야 합니다. 
- 이렇게 붙여 놓은 앵커 이름들은 마치 링크를 만들 때처럼 \<a\> 태그의 href 속성을 사용해 링크합니다. 
- 앵커 이름 앞에 #을 붙여 앵커를 표시합니다.

```html
<태그 id="앵커 이름"> 텍스트 또는 이미지 </태그>
<a href="#앵커 이름"> 텍스트 또는 이미지 </a>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>링크 만들기</title>
</head>
<body>
	<h1>앵커 만들기</h1>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<ul id="menu">
		<li><a href="#content1">메뉴1</a></li>
		<li><a href="#content2">메뉴2</a></li>
		<li><a href="#content3">메뉴3</a></li>
	</ul>
	<h2 id="content1">내용1</h2>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p><a href="#menu">[메뉴로]</a></p>
	<h2 id="content2">내용2</h2>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p><a href="#menu">[메뉴로]</a></p>
	<h2 id="content3">내용3</h2>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p>웹 문서가 너무 길 경우 필요한 곳마다 문서 안에 이름을 붙여놓고 그 위치로 한번에 이동하는 링크를 만들 수 있는데, 이 기능을 앵커(anchor)라고 합니다. </p>
	<p><a href="#menu">[메뉴로]</a></p>
</body>
</html>
```

## \<map\> 태그, \<area\> 태그, usemap 속성 - 이미지 맵 지정하기

- 하나의 이미지에 여러 개의 링크를 걸 수도 있습니다. 즉, 한 이미지상에서 클릭 위치에 따라 서로 다른 링크가 열리는 것 
- 이를 <code>이미지 맵</code>이라고 합니다. 
- 이미지 맵은 이미지에 영역을 만든 후 링크를 추가해야 하기 때문에 \<map\> 태그를 이용해 이미지 맵을 만들고 \<img\> 태그에서 usemap 속성으로 이미지 맵을 지정합니다. 
- 이미지 맵으로 사용할 이미지에 영역을 표시할 때는 \<area\> 태그를 사용합니다.

```html
<map name="맵이름">
    <area>
    <area>
    ...
</map>

<img src="이미지 파일" usemap="#맵이름">
```

- \<area\> 태그에서 사용할 수 있는 속성

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/03%20%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80%20%ED%95%98%EC%9D%B4%ED%8D%BC%EB%A7%81%ED%81%AC/images/1.png)

- 예를 들어 (0,0)에서 (80,100) 위치까지 사각 형태의 영역을 클릭했을 때 페이스북 사이트로 연결되게 하려면 다음과 같이 사용합니다.

```html
<map name="fb">
    <area shape="rect" coords="0,0,80,100" href="http://www.facebook.com" alt="페이스북">
</map>
```

```html
<!doctype html>
<html>
<head>
<meta charset="utf-8">
<title>이미지맵</title>
	<style>
		a {
			text-decoration:none
		}
	</style>
</head>

<body>
<img src="images/kids.jpg"  alt="" usemap="#favorites">
<map name="favorites">
  <area shape="rect" coords="10,10,160,200" href="http://cafe.naver.com/doithtml5" target="_blank" alt="do it html5 네이버 카페로 가기">
  <area shape="rect" coords="220,10,380,200" href="http://www.facebook.com/do.it.html5" target="_blank" alt="do it html5 페이스북 페이지로 가기">
</map>
</body>
</html>
```