# HTML5 문서 

## 시맨틱 태그가 사용된 HTML5 문서

- 웹 사이트들을 상펴보면 디자인은 서로 달라 보여도 그 구조는 크게 다르지 않습니다.
- 사이트 제목이나 로고, 검색 창이 있는 헤더(header), 여러 내용이 있는 본문(contents), 본문 외 내용을 나타내는 사이드바(sidebar)와 푸터(footer) 부분이 문서의 주요 부분이며 사이트에 따라 한두 영역이 추가됩니다.
- HTML5에서는 태그 이름만 보고도 문서 구조에서 어떤 역할을 하는지 쉽게 이해할 수 있는 <code>시맨틱 태그(semantic tag)</code>를 추가했습니다.

## 왜 시맨틱 태그로 레이아웃을 만들어야 할까?

- HTML5의 시맨틱 태그로 작성된 소스를 보면 태그만 보고도 어떤 부분이 제목이고 메뉴이고 실제 내용인지 쉽게 알 수 있습니다. 
- 소스만으로도 문서 내용을 알 수 있으면 사이트를 검색할 때 필요한 내용을 정확히 찾을 수 있어 편합니다. 
- 웹 사이트의 본문 내용을 검색해야 한다면 \<header\>나 \<nav\> 태그 부분을 검색하지 않고 실제 내용이 들어 있는 \<section\>이나 \<article\> 태그 부분만 찾아 검색하면 된다.
- 웹 접근성 시각에서 볼 떄도 시맨틱 태그는 매주 중요, 시각 장애인들은 웹 사이트를 이용할때 화면 낭독기 같은 웹 보조 기구를 이용하는데 이때 시맨틱 태그를 통해 어느 부분이 제목이고 내용인지 구별할 수 있으므로 그만큼 사이트 내용을 정확히 전달할 수 있기 때문입니다. 
- 태그에 대한 역할이 정확히 정해졌기 떄문에 어떤 장치에서든 문서를 똑같이 해석할 수 있습니다.

---

# 문서 구조를 위한 HTML5 시맨틱 태그

## \<header\> 태그 - 머리말 지정하기

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/10%20HTML5%EC%99%80%20%EC%8B%9C%EB%A9%98%ED%8B%B1%20%ED%83%9C%EA%B7%B8/images/1.png)

## \<nav\> 태그 - 문서를 연결하는 내비게이션 링크

```html
 <header>
    <h1>Joandora</h1>
    <h2>가장 제주다운 수산리집</h2>
</header>  
<nav class="navi">
    <ul>
        <li><a href="#">이용 안내</a></li>
        <li><a href="#">객실 소개</a></li>
        <li><a href="#">예약 방법</a></li>
        <li><a href="#">예약하기</a></li>
    </ul>
</nav>  
```

## \<section\> 태그 - 주제별 콘텐츠 영역 나타내기

![image2](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/10%20HTML5%EC%99%80%20%EC%8B%9C%EB%A9%98%ED%8B%B1%20%ED%83%9C%EA%B7%B8/images/2.png)

## \<article\> 태그 - 콘텐츠 내용 넣기

## \<aside\> 태그 - 본문 이외의 내용 표시하기

- 왼쪽이나 오른쪽 또는 하단에 사이드바를 만드는 태그

![image3](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/10%20HTML5%EC%99%80%20%EC%8B%9C%EB%A9%98%ED%8B%B1%20%ED%83%9C%EA%B7%B8/images/3.png)

```html
<!doctype html>
<html lang="ko">
<head>
<meta charset="utf-8">
<title>요안도라</title>
<link href="css/style2.css" rel="stylesheet" type="text/css"><!--[if lt IE 9]>
<script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
<![endif]-->
</head>

<body>
<div class="container">
		<header>
			  <h1>Joandora</h1>
				<h2>가장 제주다운 수산리집</h2>
		</header>  
    <nav class="navi">
      <ul>
        <li><a href="#">이용 안내</a></li>
        <li><a href="#">객실 소개</a></li>
        <li><a href="#">예약 방법</a></li>
        <li><a href="#">예약하기</a></li>
      </ul>
    </nav>  
		<article>
				<section class="content">
					<h2>요안도라 소개</h2>						
					<h3>¤ 요안도라는 게스트 하우스(Guest House) 형식의 농어촌 민박입니다</h3>
					<p>성산의 날씨는 다음주 내내 높은 구름에 햇살 가득이라고 합니다. 목요일이면 섭씨 27도까지 오른다고 하지만, 늘 부는 바람이 쾌적한 균형을 잡아 마당에 마당에 나가 앉아 있는 시간이 많아질듯 합니다.</p>
					<p>오늘은 사진에 보이는 긴 돌담을 따라 들어오는 요안도레 올레 입구에 특곤색의 대문을 달았습니다.</p>
					<p>
							내일은 두달 여동안 밖거리에 만든 데스트 하우스에 연백색의 황토 페인트를 칠할 예정입니다. <br>
							그리고 이것저것 사소한 저이를 마치고 나면, 나이 드시고 젊고 한 미지의 새식구들을 설렘으로 만나고 함께하고, 도시의 바븐 생활로 소원해진 오래된 친구와의 우정을 이 제주에서 새롭게 열어나가기 위해 요안도라를 세상에 알리려고 합니다.
					</p>
					<div class="banner"><img src="images/banner2.png" width="700" height="233" alt="요안도라"></div>						
				</section>	
		</article>
		<aside class="sidebar">
				<h3>¤ 알립니다</h3>
				<p>게스트하우스 예약은 전화 070-###-#### 로 직접 통화하시는게 가장 정확하고 빠릅니다.
						인터넷 전화이므로 시외 전화 요금이 부과되지 않습니다. </p>
				<img src="images/2.jpg" alt="">
				<img src="images/1.jpg" alt="">
				<img src="images/4.jpg" alt="">    
		</aside>    
</div>
</body>
</html>
```

## \<iframe\> 태그 - 외부 문서 삽입하기

- 웹 문서 안에 다른 웹문서를 가져와 표시하는 것을 인라인 프레임(inline frame)이라고 합니다. 
- 인라인 프레임을 삽입하는 태그는 \<iframe\> 태그 입니다.

```html
<iframe src="삽입할 문서 주소" [속성 = "속성 값"]></iframe>
```

|속성|설명|
|---|----|
|width|인라인 프레임의 너비입니다. 픽셀이나 백분율 값으로 표시합니다.|
|height|인라인 프레임의 높이입니다. 픽셀이나 백분율 값으로 표시합니다.|
|name|인라인 프레임의 이름입니다.|
|src|프레임에 표시할 문서의 주소를 지정합니다.|
|seamless|프레임의 테두리를 없애 마치 본문의 일부처럼 보이도록 만들며 속성 값 없이 seamless라고 쓰면 됩니다. 이 속성은 아직 크롬과 사파리에서만 지원합니다.|

```html
<h2>iframe 태그를 이용해 외부 문서(사이트) 포함시키기</h2>
<div class="content">
    <iframe src="http://www.easyspub.co.kr/" width="95%" height="500"></iframe>
</div>
```

## \<footer\> 태그 - 제작 정보와 저작권 정보 표시하기

![image4](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/10%20HTML5%EC%99%80%20%EC%8B%9C%EB%A9%98%ED%8B%B1%20%ED%83%9C%EA%B7%B8/images/4.png)


## \<address\> 태그 - 사이트 제작자 정보, 연락처 정보 나타내기

```html
<footer>
    <address>
        <p>제주특별자치도 남제주군 성산읍 수산리 000 번지 요안도라 </p>
        <p>yoan##@naver.com</p>
    </address>				
    <p> Copyright ⓒ. All rights reserved.</p>      
</footer>
```

## \<div\> 태그는 언제 사용할까?
- HTML5에서도 \<div\> 태그는 중요하게 사용됩니다. 
- HTML5에서는 주로 콘텐츠를 묶어 시각적 효과를 적용할 때 즉, 콘텐츠에 CSS를 적용할 때 \<div\> 태그를 사용합니다.