# 텍스트 관련 태그들 

## 텍스트를 덩어리로 묶어 주는 태그 
- 블록 레벨 태그
- 단락을 표시(줄바꿈)

### \<hn\> 태그 - 제목 표시하기
- 일반 텍스트 보다 굵고 진하게 표시됩니다.
- \<hn\> 태그는 제목을 뜻하는 heading의 줄임말인 'h'와 제목 크기를 나타내는 숫자(1~6)를 사용해서 \<h1\>에서 \<h6\> 까지 표현합니다.
- \<h1\>이 가장 큰 제목, \<h6\>이 가장 작은 크기의 제목 

```html
<h1>제목</h1>
<h2>제목</h2>
<h3>제목</h3>
<h4>제목</h4>
<h5>제목</h5>
<h6>제목</h6>
```

### \<p\> 태그 - 단락 만들기 
- \<p\>태그는 paragraph의 줄임말
- 텍스트 단락을 만드는데 이때 '단락'이란 앞뒤에 줄바꿈이 있는 텍스트 덩어리를 말합니다. 

```html
<p> 텍스트 </p>
```

> \<br\> 태그를 두 개 삽입하면 텍스트 단락이 생긴 것 처럼 보이지만 실제로 웹 브라우저는 이것을 텍스트 단락으로 인식하지 않습니다.

### \<br\> 태그 - 줄 바꾸기 
- 줄을 바꿀 위치에 \<br\> 태그를 사용합니다.
- \<br\> 태그는 break의 줄임말이고 닫는 태그가 없습니다.

```html
<br>
```

### \<hr\> 태그 - 분위기 전환을 위한 수평 줄 넣기

- horizontal의 줄임말
- 수평줄을 삽입할 때 사용
- 닫는 태그는 없습니다.

```html
<hr>
```

### \<blockquote\> 태그 - 인용문 넣기

- 다른 불로그나 사이트의 글을 인용할 경우, \<blockquote\> 태그를 이용해 표시 

```html 
<blockquote> 인용 내용 </blockquote>
```

- 인용한 문장은 다른 텍스트보다 안으로 들여 써지므로 다른 텍스트와 구별됩니다.
- 인용한 사이트 주소가 명확할 경우 <code>cite</code> 속성을 이용해 인용 사이트 주소를 표시할 수도 있습니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>제주 이색 여행지</title>
</head>
<body>
    <h1>제주 이색 여행지</h1>
    <h2>야외 텐트를 닮은 건축물 "테쉬폰"</h2>
    <p>아일랜드 출신 임피제 신부가 1954년 제주에 오면서 목장 숙소로 짓기 시작한 후 사료공장, 성당으로 활용됐습니다.</p>
    <p>제주에서 점차 다른 지방으로 보급됐지만 현재 제주에만 건축물이 남아있는데, <br>
    국내 근현대 건축사의 한 페이지를 보여주는 가치를 지닌다고 전문가들은 평가합니다.</p>
    <hr>
    <blockquote>성이시돌목장은 제주특별자치도 제주시 한림읍 금악리에 있는 목장이다. 특히 이시돌목장은 제주 지역 최초의 전기업목장(全企業牧場)으로 1961년 11월 말 제주시 한림읍 금악리에 세워 양돈 사업을 실시하였으며 면양을 사육하였던 것으로 알려져 있다. 이시돌목장의 특색있는 건축양식으로 테쉬폰도 유명하다. (출처:향토문화전자대전)</blockquote>
</body>
</html>
```

### \<pre\> 태그 - 입력하는 그대로 화면에 표시하기 
- HTML에서는 아무리 많은 공백을 넣더라도 브라우저 창에는 한 개의 공백만 표시 됩니다.
- \<pre\> 태그를 사용할 경우, 소스에 표시한 공백이 브라우저에 그대로 표시됩니다.
- \<code\>나 \<samp\>, \<kbd\> 같은 태그를 사용해 프로그램 소스를 표시할 때도 소스의 형태를 그대로 브라우저 창에 보여주어야 하기 때문에 \<pre\> 태그가 함께 사용됩니다.
- \<pre\> 태그는 preformat의 줄임말

```html
<pre> 텍스트 </pre>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>로컬 스토리지(Local Storage)를 저장하는 함수</title>
</head>
<body>
	<h3>로컬 스토리지(Local Storage)를 저장하는 함수 :  </h3>
	<pre>
     function savetheLocal(){
          var second = document.getElementById("second");
          var thevalue = second.value;
          localStorage.setItem(1, thevalue);
          gettheLocal();
     }    
	</pre>
</body>
</html>
```

---

## 텍스트를 한 줄로 표시하는 태그

- 인라인 레벨 태그
- 줄바꿈 없이 텍스트를 표시

### \<strong\> 태그, \<b\> 태그 - 굵게 표시하기

```html
<strong> 굵게 강조할 텍스트 </strong>
<b>굵게 표시할 텍스트</b>
```


### \<em\>태그, \<i\>태그 - 이텔릭체로 표시하기 
- \<em\>태그는 emphasis의 줄임말
 \<i\>태그는 italic의 줄임말


```html
<i>이탤릭체로 표시할 텍스트</i>
<em>이탤릭체로 강조할 텍스트</em>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>제주 이색 여행지</title>
    <style>
        p { 
            font-size:16px;  /* 글자 크기 */  
            line-height:25px;  /* 줄 간격 */
        }
    </style>
</head>
<body>
    <h2>제주 이색 여행지 - 이중섭 거리</h2>
    <p><strong>주말</strong>마다 <b>'서귀포문화예술디자인시장'</b>이 열립니다.</p>
    <p><em>'아트마켓'</em>이라고도 부르는데, <i>문화예술체험</i>이나 <i>공연관람</i>을 할 수도 있고 <br>
     작가들이 직접 만든 창작예술품 등을 판매하기도 합니다.</p>
</body>
</html>
```

### \<q\> 태그 - 인용 내용 표시하기
- \<blockquote\>태그와 다른 점은 \<blockquote\> 태그는 블록 레벨 태그이기 때문에 인용 내용이 줄이 바뀌어 나타나고 다른 내용과 구별되도록 안으로 들여 써진다.
- \<q\> 태그는 인라인 레벨 태그이기 때문에 줄바꿈 없이 다른 내용과 함께 한 줄로 표시되고 인용 내용에 따옴표를 붙여 표시한다는 점 

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>웹 접근성(Web Accessibility)</title>
</head>
<body>
	<h1>웹 접근성</h1>
	<p>웹의 창시자인 팀 버너스 리 (Tim Berners-Lee)의 <q cite="http://www.w3.org/standards/webdesign/accessibility">웹의 힘은 보편성에 있다. 장애에 구애없이 모든 사람이 접근할 수 있는 것이 필수적인 요소이다.</q>라는 말로 웹 접근성을 설명한다. </p>
</body>
</html>
```

### \<mark\> 태그 - 형광펜 표과 내기

```html
<mark>텍스트</mark>
```
> CSS의 background-color 속성을 사용해 \<mark\>태그의 배경색을 바꿀 수 있습니다.

### \<span\> 태그 - 줄바꿈 없이 영역 묶기

```html
<span>내용</span>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>제주 이색 여행지</title>
</head>
<body>
    <h2>야외 텐트를 닮은 건축물 <mark>"테쉬폰"</mark></h2>
    <p>아일랜드 출신 임피제 신부가 1954년 제주에 오면서 목장 숙소로 짓기 시작한 후 사료공장, 성당으로 활용됐습니다. 제주에서 점차 다른 지방으로 보급됐지만 현재 제주에만 건축물이 남아있으며, <span style="color:blue;">국내 근현대 건축사의 한 페이지를 보여주는 가치를 지닌다</span>고 전문가들은 평가합니다.</p>
</body>
</html>
```

### \<ruby\> 태그 - 동아시아 글자 표시하기
- \<ruby\> 태그는 주로 동아시아 국가들의 글자에 주석을 함께 표기하기 위한 용도로 사용
- 주석으로 표시할 내용을 \<ruby\> 태그 안에 \<rt\> 태그로 표시합니다.


```html
<ruby> 내용 <rt> 주석 </rt></ruby>
```

```html
<!doctype html>
<html lang="ko">
	<head>
		<meta charset="utf-8">
		<title>Ruby</title>
	</head>
	<body>
		<p>루비(Ruby)는 1995년, 일본의 프로그래머인 마츠모토 유키히로 (<ruby>松本行弘<rt>まつもとゆきひろ</rt></ruby>)가 만든 프로그래밍 언어입니다.</p>
	</body>	
</html>

```

### 기타 텍스트 관련 태그들

|태그|설명| 예시                               |
|---|----|----------------------------------|
|\<abbr\>|약자 표시 title 속성을 함께 사용할 수 있음| \<p\>\<b\>\<abbr title="Internet of Things"\>IoT\\</abbr\>\</b\>란 각종 사물에 센서와 통신 기능을 내장해 인터넷에 연결하는 기술을 의미한다.\</p\> |
|\<cite\>|웹 문서나 포스트에서 참고 내용을 표시| \<p\>내가 경험한 가장 흥미진진한 일은 누군가를 만나는 일이다 - 영화, \<cite\>'비포선셋'\</cite\> 중 |
|\<code\>|컴퓨터 인식을 위한 소스 코드| \<pre\>\<code\> function savethelocal() {....}\</code\>\<\pre\> |
|\<kbd\>|키보드 입력이나 음성 명령 같은 사용자 입력 내용| \<p\> 웹 화면을 다시 불러오려면 \<kbd\>F5\<kbd\>키를 누릅니다.\</p\> |
|\<small\>|부가 정보처럼 작게 표시해도 되는 텍스트| \<p\>가격 : 13,000원 \<small\>(부가세 별도)\</small\>\</p\> |
|\<sub\>|아래 첨자| \<p\>물의 화학식은 \<b\>H\<sub\>2\</sub\>O\</b\>다\</p\> |
|\<sup\>|위 첨자| \<p\>E = mc\<sup\>2\</sup\>\</p\>|
|\<s\>|취소선|\<p\>\<s\>34,000원\</s\>\<strong\>19,000원\</strong\>\</p\>|
|\<u\>|밑줄|\<p\>링크 표시 용도가 아니라 단순히 밑줄을 긋는다면 \<u\> u 태그\</u\>\</p\>|

---

## 목록을 만드는 태그 

### \<ul\> 태그, \<li\> 태그 - 순서 없는 목록 만들기


```html 
<ul>
 <li>내용</li>
 <li>내용</li>
 ...
</ul>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>제주 관광 안내</title>
</head>
<body>
	<h1>관광 안내 전화 </h1>
	<p>한국관광공사에서는 전국의 관광안내소와 공동으로 여러분의 여행편의를 위해 관광안내전화 1330 서비스를 연중무휴 실시하고 있습니다.</p>
	<p>1330에는 해당 지역의 지도와 관광 가이드북, 관광안내소를 대신할 수 있을 정도의 다양한 정보가 있습니다. 원하는 관광지는 물론이며 숙박, 교통, 음식점 등의 자세한 정보를 한국어를 비롯한 영어, 중국어, 일어의 3개 국어로도 이용 가능합니다.</p>
	<ul>
		<li>일반 전화 : (국번없이) 1330</li>
		<li>휴대 전화 : 064-1330</li>
	</ul>
</body>
</html>
```

### \<ol\> 태그, \<li\> 태그 - 순서 목록 만들기 

```html
<ol>
 <li>내용</li>
 <li>내용</li>
 ...
</ol>
```

#### \<ol\> 태그 속성으로 순서 목록의 숫자와 순서 바꾸기

- type 속성 : 숫자의 종류를 다양하게 조절할 수있습니다.

|속성 값|설명|
|---|----|
|1|숫자(기본값)|
|a|영문 소문자|
|A|영문 대문자|
|i|로마숫자 소문자|
|I|로마숫자 대문자|

- start 속성 : 순서 목록은 기본적으로 1부터 시작, start 속성을 이용하면 중간 번호부터 시작할 수 있습니다.
- reversed 속성 : 항목을 역순으로 표시합니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>1박 2일 가족 여행 코스</title>
</head>
<body>
	<h1>1박 2일 가족 여행 코스</h1>
	<ul>
		<li>1일차
			<ol type="a">
				<li>해녀박물관</li>
				<li>낚시체험</li>
			</ol>
		</li>
		<li>2일차
			<ol type="a" start ="3">
				<li>용눈이오름</li>
				<li>만장굴</li>
				<li>카약체험</li>
			</ol>
		</li>
	</ul>

</body>
</html>
```

### \<dl\>, \<dt\>, \<dd\> 태그 - 설명 목록 만들기
- \<dl\> 태그는 목록을 만듭니다.
- \<dt\> 태그는 제목을 만듭니다.
- \<dd\> 태그는 설명을 표시합니다. 
- 하나의 \<dt\> 태그에 여러 개의 \<dd\> 태그 값을 가질 수도 있고 여러 개의 \<dt\> 태그를 가질 수 도 있습니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>제주 올레</title>
	<style>
		dl {
			line-height:25px;   /* 줄 간격 */
		}
	</style>
</head>
<body>
	<h1>제주 올레 </h1>
	<dl>
		<dt>올레 1코스</dt>
		<dd>코스 : 시흥 초등학교 옆 - 광치기 해변</dd>
		<dd>거리 : 14.6km(4~5시간)</dd>
		<dd>난이도 : 중</dd>
		<dt>올레 2코스</dt>
		<dd>코스 : 광치기 해변 - 온평 포구</dd>
		<dd>거리 : 14.5km(4~5시간)</dd>
		<dd>난이도 : 중</dd>
	</dl>
</body>
</html>
```

```html
<!doctype html>
<html lang="ko">
<head>
	<title>온라인 프로필</title>
	<meta charset="utf-8">
    <link rel="stylesheet" href="css/style.css">
</head>

<body>
    <div id="container">
        <!-- 사이드바 -->
        <!-- <aside>
            <div id="namecard">

            </div>
            <div id="detail">
                               
            </div>
            <div id="sns">
                <h2>SNS</h2>

            </div>        
        </aside> -->
        <div id="main">
            <!-- 자기 소개 -->
            <section>
                <h2 class="subtitle">Who am I?</h2>
                <p><mark>프런트엔드 웹 기술(Front-end Web Tech.)</mark>에 관심이 많습니다. <br>현재 제주의 한 시골 마을에서 코딩 중입니다.</p>
            </section>

            <!-- 경력 -->
            <section>
                <h2 class="subtitle">Experience</h2>
                <ul>
                    <li>프론트엔드 개발
                        <ul>
                            <li>업무 내용 업무 내용 업무 내용 </li>
                            <li>업무 내용 </li>
                            <li>업무 내용 업무 내용</li> 
                        </ul>
                    </li>
                    <li>웹 디자인
                        <ul>
                            <li>업무 내용 </li>
                            <li>업무 내용 업무 내용</li>
                        </ul>                        
                    </li>
                </ul>             
            </section>

            <!-- 숙련도 -->
            <section>
                <h2 class="subtitle">Skills</h2>

            </section>

            <!-- 학력 -->
            <section>
                <h2 class="subtitle">Education</h2>

            </section>
        </div>        
    </div>
</body>
</html>
```

---

## 표를 만드는 태그 

### \<table\>, \<tr\>, \<td\>, \<th\> 태그 - 기본적인 표 만들기

```html
<table>
    <tr>
        <td>내용</td>
        <td>내용</td>
        ...
    </tr>
    ...
</table>
```

- 1. \<table\> 태그로 표 자리를 먼저 만듭니다.

```html
\<table\>
    
\</table\>
```

- 2. \<tr\> 태그로 2개의 행을 만듭니다.

```html
<table>
 <tr>
  
 </tr>
 <tr>
  
 </tr>
</table>
```

- 3. \<td\> 태그로 각 행마다 셀을 3개식 만듭니다.

```html
<table>
    <tr>
        <td>...</td>
        <td>...</td>
        <td>...</td>
    </tr>
    <tr>
        <td>...</td>
        <td>...</td>
        <td>...</td>
   </tr>
</table>
```

- 4. 각 셀에 들어갈 내용은 \<td\>와 \</td\> 사이에 입력합니다.


### \<th\> 태그 - 표에 제목 셀 만들기

- \<td\> 태그와 마찬가지로 셀을 만드는 태그로 해당 셀에 들어가는 내용을 셀의 중앙에 배치하고 굵게 표시합니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>표 만들기</title>
	<style>
		table, th, td {
			border:1px solid #ccc;
		}		
		td {
			padding:5px;  /* 셀 테두리와 내용 사이의 간격(패딩) */
		}
	</style>
</head>
<body>
	<table>
		<tr>
			<th>제목 셀</th>
			<td>1행 2열</td>
			<td>1행 3열</td>
		</tr>
		<tr>
			<th>제목 셀</th>
			<td>2행 2열</td>
			<td>2행 2열</td>
		</tr>
	</table>
</body>
</html>
```

### colspan, rowspan 속성 - 행 또는 열 합치기 

- 여러 열을 하나로 합치려면 \<td\> 태그나 \<th\> 태그 안에서 colspan 속성을 사용해 몇 개의 셀을 가로로 합칠지 지정합니다.

```html
<td colspan="합칠 셀의 개수">내용</td>
<th colspan="합칠 셀의 개수">내용</th>
```

- \<td\>태그나 \<th\> 태그에서 rowspan 속성을 이용해 새로 합칠 셀의 개수를 지정합니다.

```html
<td rowspan="합칠 셀의 개수">내용</td>
<th rowspan="합칠 셀의 개수">내용</th>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>표 만들기</title>
	<style>
		table, th, td {
			border:1px solid #ccc;
		}		
		th {
			padding:15px;   /* 셀 테두리와 내용 사이의 간격(패딩) */
		}
		tr > td:nth-child(odd) { 
			width:120px;  /* 홀수번째 열의 너비 : 120px */
		}
		tr > td:nth-child(even) { 
			width:300px;  /* 짝수번째 열의 너비 : 120px */
		}
	</style>
</head>
<body>
	<table>
		<tr>
			<th>이름</th>
			<td></td>
			<th>연락처</th>
			<td></td>
		</tr>
		<tr>
			<th>주소</th>
			<td colspan="3"></td>
		</tr>		
		<tr>
			<th>자기소개</th>
			<td colspan="3"></td>
		</tr>
	</table>
</body>
</html>
```

### \<caption\> 태그, \<figcaption\> 태그 - 표에 제목 붙이기

#### \<caption\> 태그 사용하기 
- \<table\> 태그 바로 다음에 사용 
- \<caption\> 태그를 사용한 표 제목은 표의 위쪽 중앙에 표시된다. 

```html
<caption>표 제목</caption>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>표 만들기</title>
	<style>
		table, th, td {
			border:1px solid #ccc;
		}		
		td, th {
			padding:10px;   /* 셀 테두리와 내용 사이의 간격(패딩) */
		}
	</style>
</head>
<body>	
	<table>
		<caption>
			<strong>Modern Browser</strong>
			<p>국내에서 자주 사용하는 모던 브라우저</p>
		</caption>
		<tr>
			<th>브라우저</th>
			<th>제조업체</th>
			<th>다운로드</th>
		</tr>
		<tr>
			<th>크롬(Chrome)</th>
			<td>Google</td>
			<td>https://www.google.com/chrome/ </td>
		</tr>
		<tr>
			<th>파이어폭스(Firfox)</th>
			<td>Mozilla</td>
			<td>https://www.mozilla.org/ko/firefox/</td>
		</tr>
		<tr>
			<th> 엣지(Edge) </th>
			<td> Microsoft </td>
			<td>https://www.microsoft.com/ko-kr/windows/microsoft-edge</td>
		</tr>
	</table>

</body>
</html>
```

#### \<figcaption\> 태그 사용하기
- \<figcaption\> 태그는 figure와 caption의 합성어로 설명 글을 붙이고 싶은 대상을 \<figure\> 태그로 감싼 후 \<figcaption\> 태그를 이용해 제목이나 설명 글을 입력합니다.
- \<caption\> 태그와 달리 중앙에 정렬되지 않습니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>표 만들기</title>
	<style>
		table, th, td {
			border:1px solid #ccc;
		}		
		td, th {
			padding:10px;   /* 셀 테두리와 내용 사이의 간격(패딩) */
		}
	</style>
</head>
<body>	
	<figure>
		<figcaption>
			<p>국내에서 자주 사용하는 <b>모던 브라우저</b></p>
		</figcaption>
		<table>
			<tr>
				<th>브라우저</th>
				<th>제조업체</th>
				<th>다운로드</th>
			</tr>
			<tr>
				<th>크롬(Chrome)</th>
				<td>Google</td>
				<td>https://www.google.com/chrome/ </td>
			</tr>
			<tr>
				<th>파이어폭스(Firfox)</th>
				<td>Mozilla</td>
				<td>https://www.mozilla.org/ko/firefox/</td>
			</tr>
			<tr>
				<th> 엣지(Edge) </th>
				<td> Microsoft </td>
				<td>https://www.microsoft.com/ko-kr/windows/microsoft-edge</td>
			</tr>
		</table>
	</figure>
</body>
</html>
```

#### aria-describedby 속성 - 표에 대한 설명 제공하기
- 화면 낭독기에서 표를 읽어줄 때 도움이 되도록 표 설명을 별도의 문장으로 작성한 후 <table>태그 안에 aria-describedby 속성을 추가해 연결하면 표를 이해하는 데 도움이 됩니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="utf-8">
	<title>표 만들기</title>
	<style>
		table, th, td {
			border:1px solid #ccc;
		}
		td, th {
			padding:10px;  /* 셀 테두리와 내용 사이의 간격(패딩) */
		}
	</style>
</head>
<body>	
	<p id="summary">다음 표는 HTMl5를 지원하는 모던(Modern Browser)를 정리한 것입니다. 최신 버전일수록 HTML5를 좀더 많이 지원하기 때문에 최신 버전을 다운로드하는 것이 좋습니다. </p>
	<table aria-describedby="summary">
		<caption>Modern Browser</caption>
		<tr>
			<th>브라우저</th>
			<th>제조업체</th>
			<th>다운로드</th>
		</tr>
		<tr>
			<th>크롬(Chrome)</th>
			<td>Google</td>
			<td>https://www.google.com/chrome/ </td>
		</tr>
		<tr>
			<th>파이어폭스(Firfox)</th>
			<td>Mozilla</td>
			<td>https://www.mozilla.org/ko/firefox/</td>
		</tr>
		<tr>
			<th> 엣지(Edge) </th>
			<td> Microsoft </td>
			<td>https://www.microsoft.com/ko-kr/windows/microsoft-edge</td>
		</tr>
	</table>
</body>
</html>
```


### \<thead\>, \<tbody\>, \<tfoot\> 태그 - 표 구조 정의하기

- table의 t와 제목 부분(head), 본문(body), 요약 부분(foot)이란 말이 합쳐진 \<thead\>와 \<tbody\>, \<tfood\> 태그 입니다.

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/02%20%ED%85%8D%EC%8A%A4%ED%8A%B8%20%EA%B4%80%EB%A0%A8%20%ED%83%9C%EA%B7%B8%EB%93%A4/images/1.png)

```html
<thead>
    <tr> ... </tr>
</thead>
<tbody>
    <tr> ... </tr>
</tbody>
<tfoot>
    <tr> ... </tr>
</tfoot>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>표 만들기</title>
	<style>
		table, th, td {
			border:1px solid #ccc;
		}
		th, td {
			width:80px;  /* 셀의 너비 */
			padding:10px; /* 셀 테두리와 내용 사이의 간격(패딩) */
		}
		thead, tfoot { 
			background : #eeeeee;  /* thead와 tfoot의 배경 색 */
		}
	</style>
</head>
<body>
	<table>
		<caption>제주특별자치도 학교현황(2015.4.1 기준)</caption>
		<thead>
			<tr>
				<th>구분</th>
				<th>학교수</th>
				<th>학급수</th>
				<th>학생수</th>
				<th>교원수</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<th>유치원</th>
				<td>117</td>
				<td>252</td>
				<td>5,547</td>
				<td>474</td>
			</tr>
			<tr>
				<th>초등학교</th>
				<td>111</td>
				<td>1,720</td>
				<td>37,686</td>
				<td>2,632</td>
			</tr>
			<tr>
				<th>중학교</th>
				<td>44</td>
				<td>699</td>
				<td>21,274</td>
				<td>1,412</td>
			</tr>
			<tr>
				<th>고등학교</th>
				<td>29</td>
				<td>676</td>
				<td>22,019</td>
				<td>1,433</td>
			</tr>
			<tr>
				<th>특수학교</th>
				<td>3</td>
				<td>90</td>
				<td>428</td>
				<td>160</td>
			</tr>
		</tbody>
		<tfoot>
			<tr>
				<th>합계</th>
				<td>300</td>
				<td>3,437</td>
				<td>86,954</td>
				<td>6,111</td>
			</tr>
		</tfoot>
	</table>
</body>
</html>
```

### \<col\>, \<colgroup\> 태그 - 여러 열 묶어 스타일 지정하기 
- 표에서 하나의 열에 스타일을 지정하거나 열(column)을 몇 개씩 묶어 스타일을 한꺼번에 지정할 수도 있습니다.
- \<col\> 태그를 사용해 둘 이상의 열을 묶어 같은 스타일을 지정하려면 <code>span</code> 속성을 이용해 몇 개를 함께 묶어줄지 지정할 수 있습니다.

```html
기본형
<col>
```

```html
기본형
<colgroup>
    <col>
    ...
</colgroup>
```

```html 
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>표 만들기</title>
	<style>
		table, th, td {
			border:1px solid #ccc;
		}
		td {
			width:100px;  /* 셀 너비 */
			height:30px;  /* 셀 높이 */
		}
	</style>
</head>
<body>
	<table>
		<caption>colgroup 연습</caption>
		<colgroup>
			<col>
			<col span="2" style="background-color:blue;">
			<col style="background-color:yellow">
		</colgroup>
		<tr>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
		<tr>
			<td></td>
			<td></td>
			<td></td>
			<td></td>
		</tr>
	</table>
</body>
</html>
```
