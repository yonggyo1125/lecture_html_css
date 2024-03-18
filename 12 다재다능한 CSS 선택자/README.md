# 연결 선택자 
> 선택자와 선택자를 연결해 적용 대상을 한정
> 
> <code>콤비네이션 선택자</code>, <code>콤비네이션 셀렉터</code>라고도 합니다.

## 하위 선택자 - 지정한 모든 하위 요소에 스타일 적용하기

- 부모 요소에 포함된 하위 요소 모두에 스타일이 적용되는 것으로 <code>자손 선택자</code>라고도 합니다. 
- 자식 요소뿐만 아니라 손자 요소, 손자의 손자 요소 등 모든 하위 요소까지 적용됩니다. 

```
상위요소 하위요소 
```

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/12%20%EB%8B%A4%EC%9E%AC%EB%8B%A4%EB%8A%A5%ED%95%9C%20CSS%20%EC%84%A0%ED%83%9D%EC%9E%90/images/1.png)

```html
<!doctype html>
<html lang="ko">
<head>
<meta charset="utf-8">
<title>요안도라</title>
<style>
	#container ul {
		border: 1px dotted blue; /* #container 요소의 모든 하위 ul 요소에 파란 1px 실선 */
	}
</style>
</head>

<body>
  <section id="container">
  <header><h1>예약 방법 및 요금</h1></header>
  <p> 요안도라에 예약하려면?
  <ul>
    <li> 예약 방법
      <ul>
        <li>직접 통화</li>
        <li>문자 남기기</li>                       
     </ul>
   </li>	 
   <li>요금 
     <ul>
        <li>1인 : 40,000원</li>
        <li>2인 : 60,000원</li>
        <li>3인 : 80,000원</li>
	  <li>4인 : 100,000원</li>   
    </ul>        
   </li>	
</ul> 
</section>
</body>
</html>
```

## 자식 선택자 - 자식 요소에만 스타일 적용하기 

- 두 요소 사이에 '\> (부등호)'를 표시해 부모 요소와 자식 요소르를 구분합니ㅏㄷ. 
- 자식 선택자는 바로 아래 요소, 즉 자식 요소에만 스타일이 적용됩니다.

![image2](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/12%20%EB%8B%A4%EC%9E%AC%EB%8B%A4%EB%8A%A5%ED%95%9C%20CSS%20%EC%84%A0%ED%83%9D%EC%9E%90/images/2.png)

```html
<style>
  #container > ul {
	border : 1px dotted blue;  /* #container 요소의 자식 ul 요소에 파란 1px 실선 */
  }
</style>

...

<section id="container">
    <header><h1>예약 방법 및 요금</h1></header>
    <p> 요안도라에 예약하려면? </p>
    <ul>
        <li> 예약 방법
            <ul>
                <li>직접 통화</li>
                <li>문자 남기기</li>
            </ul>
        </li>
        <li>요금
            <ul>
                <li>1인 : 40,000원</li>
                <li>2인 : 60,000원</li>
                <li>3인 : 80,000원</li>
                <li>4인 : 100,000원</li>
            </ul>
        </li>
    </ul>
</section>
```

## 인접 형제 선택자 - 가장 가까운 형제 요소에 스타일 적용하기 

- 같은 부모 요소를 가지는 요소들을 형제 관계라고 부릅니다.
- 형제 관계인 요소들에서 먼저 나오는 요소를 <code>형 요소</code>, 나중에 나오는 요소를 <code>동생 요소</code>라고 합니다. 
- <code>인접 형제 선택자</code>는 문서 구조상 같은 부모를 가진 형제 요소 중 첫 번째 동생 요소에서만 스타일이 적용됩니다.

![image3](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/12%20%EB%8B%A4%EC%9E%AC%EB%8B%A4%EB%8A%A5%ED%95%9C%20CSS%20%EC%84%A0%ED%83%9D%EC%9E%90/images/3.png)

```html
<style>
  h1+ul {                 /* h1 요소 다음의 첫 번째 ul 요소에 적용할 스타일 */
    color:blue;         /* 글자색 파랑 */
    font-weight:bold;     /* 글자 굵게 */
  }
</style>

<section id="container">
    <h1>예약 방법 및 요금</h1>
    <ul>
        <li>직접 통화</li>
        <li>문자 남기기</li>
    </ul>
    <ul>
        <li>1인 : 40,000원</li>
        <li>2인 : 60,000원</li>
        <li>3인 : 80,000원</li>
        <li>4인 : 100,000원</li>
    </ul>
</section>
```

## 형제 선택자 - 형제 요소에  스타일 적용하기 

- 인접 형제 선택자와 달리 모든 형제 요소에 적용됩니다.

![image4](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/12%20%EB%8B%A4%EC%9E%AC%EB%8B%A4%EB%8A%A5%ED%95%9C%20CSS%20%EC%84%A0%ED%83%9D%EC%9E%90/images/4.png)


```html
<style>
h1~ul {
  color:blue;       /* 글자색 파랑 */
  font-weight:bold; /* 글자 굵게 */
}
</style>

<section id="container">
    <h1>예약 방법 및 요금</h1>
    <ul>
        <li>직접 통화</li>
        <li>문자 남기기</li>
    </ul>
    <ul>
        <li>1인 : 40,000원</li>
        <li>2인 : 60,000원</li>
        <li>3인 : 80,000원</li>
        <li>4인 : 100,000원</li>
    </ul>
</section>
```

---


# 속성 선택자 


## [속성] 선택자 - 지정한 속성에 스타일 적용하기

- 지정한 속성을 가진 요소를 찾아 스타일을 적용합니다.
- 대괄호([, ]) 사이에 찾으려면 속성을 지정하면 됩니다.


```
[속성]
```

```html
<style>
    a[href] {
        background:yellow;
    }
</style>

<ul>
    <li><a>메인 메뉴 : </a></li>
    <li><a href="#">메뉴 1</a></li>
    <li><a href="#">메뉴 2</a></li>
    <li><a href="#">메뉴 3</a></li>
    <li><a href="#">메뉴 4</a></li>
</ul>
```

## [속성 = 값] 선택자 - 특정 값을 갖는 속성에 스타일 적용하기 
- 주어진 속성과 속성 값이 일치하는 요소를 찾아 스타일을 적용

```
[속성 = 값]
```

```html
<style>
    a[target="_blank"] {
		 padding-right:30px;
		 background:url(images/newwindow.png) no-repeat center right;
	 }
</style>

...

<h1>HTML5 표준안 사이트 </h1>
<ul>
    <li><a href="http://www.w3c.org/TR/html" target="_blank">HTML</a></li>
    <li><a href="https://www.w3.org/TR/selectors">CSS Selector Level 3</a></li>
    <li><a href="https://www.w3.org/TR/css3-mediaqueries">미디어쿼리</a></li>
</ul>
```

## [속성 ~= 값] 선택자 - 여러 값 중 특정 값이 포함된 속성에 스타일 적용하기 
- 여러 속성 값 중에 해당 값이 포함되어 있는 요소를 선택
- 이 선택자는 하나의 속성에 속성 값이 여러 개일 때 특정 속성 값을 찾는 데 편리 
- 선택된 값은 일부만 일치하는 것이 아니라 한단어로 일치해야 합니다. 예를 들어 class="flat-button" 처럼 하이픈으로 연결되어 있거나 class="buttons" 처럼 일부만 일치할 때는 적용되지 않습니다.

```html
<style>
    [class ~="button"] {
        border: 2px solid black;
        box-shadow: rgba(0,0,0,0.4) 5px 5px;
    }
</style>

...

<ul>
    <li><a href="#">메뉴 1</a></li>
    <li><a href="#">메뉴 2</a></li>
    <li><a href="#" class="button">메뉴 3</a></li>
    <li><a href="#" class="flat button" >메뉴 4</a></li>
</ul>
```

```
[속성 ~= 값]
```

## [속성 |= 값] 선택자 - 특정 값이 포함된 속성에 스타일 적용하기 

- [속성 ~= 값]은 하이픈(-)으로 연결한 단어에 스타일을 적용하지 않는 반면, [속성 |= 값] 선택자는 속성 값이 지정한 값이거나 "값-"으로 시작하면 스타일을 적용합니다.
- 하이픈(-)으로 연결한 단어가 있더라도 스타일을 적용합니다.

```html
<style>
    a[title |="us"] {
        background: url(images/us.png) no-repeat left center;
        padding: 5px 25px;
    }
    a[title |="jap"] {
        background: url(images/jp.png) no-repeat left center;
        padding: 5px 25px;
   }
</style>

...

<ul>
    <li>외국어 서비스 : </li>
    <li><a href="#" title="us">영어</a></li>
    <li><a href="#" title="us-english">영어</a></li>
    <li><a href="#" title="japanese">일본어</a></li>
</ul>
```


## [속성 ^= 값] 선택자 - 특정 값으로 시작하는 속성에 스타일 적용하기

- 지정한 문자로 시작하는 속성 값에 대해서만 스타일을 적용합니다.

```
[속성 ^= 값]
```

```html
<style>
    a[title ^="eng"] {
        background: url(images/us.png) no-repeat left center;
        padding: 5px 25px;
    }
    a[title ^="jap"] {
        background: url(images/jp.png) no-repeat left center;
        padding: 5px 25px;
    }
    a[title ^="chin"] {
        background: url(images/ch.png) no-repeat left center;
        padding: 5px 25px;
    }
</style>

...

<ul>
    <li>외국어 서비스 : </li>
    <li><a href="#" title="english">영어</a></li>
    <li><a href="#" title="japanese">일본어</a></li>
    <li><a href="#" title="chinese">중국어</a></li>
</ul>
```

## [속성 $= 값] 선택자 - 특정 값으로 끝나는 속성에 스타일 적용하기

- 지정한 값으로 끝나는 요소를 찾아 스타일 적용 

```
[속성 $= 값]
```

```html
<style>
    a[href $= "hwp"] { /* 연결한 파일의 확장자가 hwp인 링크 */
        background: url(images/hwp_icon.gif) center right no-repeat; /* 배경으로 hwp 아이콘 표시 */
        padding-right: 25px; /* 아이콘을 표시할 수 있도록 오른쪽에 25px 여백 */
    }
    
   a[href $= "xls"] { /* 연결한 파일의 확장자가 hwp인 링크 */
        background: url(images/excel_icon.gif) center right no-repeat; /* 배경으로 hwp 아이콘 표시 */
        padding-right: 25px; /* 아이콘을 표시할 수 있도록 오른쪽에 25px 여백 */
   }
</style>

...

<h3>회사 소개 파일 다운 받기</h3>
<ul>
    <li><a href="intro.hwp">hwp 파일</a></li>
    <li><a href="intro.xls">엑셀 파일</a></li>
</ul>
```

## [속성 *= 값] 선택자 - 값의 일부가 일치하는 속성에 스타일 적용하기 

- 사용자가 지정한 속성 값의 어느 위치에든 해당 값이 포함되어 있으면 스타일이 적용 

```
[속성 *= 값]
```

```html
<style>
    [href *= "w3"] {
		 background:blue;
		 color:white;		 
	}
</style>

...

<h1>HTML5 참고 사이트 </h1>
<p>(아래 링크 중 파란색 배경의 링크는 W3C 사이트로 연결됩니다.)</p>
<ul>
    <li><a href="http://www.w3c.org/TR/html">HTML 표준안 사이트</a></li>
    <li><a href="http://www.webplatform.org">튜토리얼과 아티클</a></li>
    <li><a href="http://caniuse.com">HTML 지원 여부 체크</a></li>
    <li><a href="http://www.w3c.org/TR/css3-mediaqueries">미디어쿼리</a></li>
</ul>
```

---

# 가상 클래스와 가상 요소

## 사용자 동작에 반응하는 가상 클래스

- 특정 동작을 할 때 스타일이 바뀌도록 만들고 싶다면 가상 클래스 선택자를 사용합니다. 

- (1) **:link 가상 클래스 선택자** - 방문하지 않은 링크에 스타일 적용
  - 텍스트 링크는 기본적으로 파란색(blue) 글자와 밑줄로 표시되는데 링크의 밑줄을 없애거나 색상을 바꾸려고 할 때 :link 선택자를 사용합니다.

- (2) **:visited 가상 클래스 선택자** - 방문한 링크에 스타일 적용
  - 방문한 텍스트 링크는 기본적으로 자주색(purple)으로 표시되는ㄴ데 사용자가 방문했던 링크도 일반 텍스트 링크와 색상이 달라지지 않게 하려면 :visited 선택자를 사용해 조절합니다. 

- (3) **:hover 가상 클래스 선택자** - 웹 요소에 마우스 커서를 올려놓을 때의 스타일 적용 
- (4) **:active 가상 클래스 선택자** - 웹 요소를 활성화했을 때의 스타일 적용 
    - 링크나 이미지 등 웹 요소를 활성화했을 때(누르고 있을 때)의 스타일을 지정합니다. 
- **:focus 가상 클래스 선택자** - 웹 요소에 초점이 맞추어졌을 때의 스타일 적용
  - 예를 들어 아이디를 입력하기 위해 텍스트 필드 안에 마우스 커서를 갖다 놓거나 [Tab]을 눌러 초점을 이동했을 때의 스타일을 지정합니다.
  - (1) ~ (4) 네 가지를 모두 정의한다면 :link 선택자부터 정의하고 :visited, :hover, :active 순서대로 정의합니다. 이 순서가 바뀌면 스타일을 정의하더라도 제대로 적용되지 않습니다.

```html
<style>
  .navi a:link, .navi a:visited {
    font-size:14px;
    padding: 10px; 
    text-decoration: none;  /* 밑줄 없음 */

  }
  .navi a:hover,  .navi a:focus {
    background-color:#222;  /* 배경 색 */
    color:#fff;  /* 글자 색 */
  }

  .navi a:active {
    background-color:#f00;  /* 배경 색 */
  }
</style>

...

<nav class="navi">
  <ul>
    <li><a href="#">이용 안내</a></li>
    <li><a href="#">객실 소개</a></li>
    <li><a href="#">예약 방법 및 요금</a></li>
    <li><a href="#">예약하기</a></li>
  </ul>
</nav>  
```

## UI 요소 상태에 따른 가상 클래스 
- 사용자의 동작뿐만 아니라 웹 요소의 상태에 따라 스타일을 지정할 때도 가상 클래스 선택자를 사용합니다.
- UI(User Interface) 요소의 상태에 따라 가상 클래스는 웹 사이트나 앱 화면을 디자인할 때 웹 요소의 상태에 따라 스타일을 지정하기 위해 사용

- (1) **:enabled와 :disabled 가상 클래스 선택자** - 요소를 사용할 수 있을 때와 없을 때의 스타일 지정
- (2) **:checked 가상 클래스 선택자** - 라디오 박스나 체크 박스에서 해당 항목을 선택했을 때의 스타일 지정

```html
<style>
  input:disabled {		 
    background:#ddd;
    border:1px #ccc solid;
  }
  input:checked + span {
    color:blue;
  }
</style>

...

<form>
  <fieldset>
    <legend>사용자 정보</legend>
    <label>이름 <input type="text" disabled></label>
  </fieldset>
  <fieldset>
    <legend>신청 과목</legend>
    <p>이 달에 신청할 과목을 선택하세요</p>
    <label><input type="radio" name="subject" value="speaking"><span>회화</span></label>
    <label><input type="radio" name="subject" value="grammar"><span>문법</span></label>
    <label><input type="radio" name="subject" value="writing"><span>작문</span></label>
  </fieldset>
</form>
```

## 구조 가상 클래스

- 웹 문서 구조를 기준으로 특정 위치에 있는 요소를 찾아 스타일을 지정할 때 사용하는 가상 클래스 선택자

- (1) **:root 가상 클래스 선택자** - 문서 전체에 적용하기
  - 문서 안의 루트(root) 요소에 스타일을 적용합니다. HTML 문서에서는 루트 요소가 HTML이므로 HTML 요소에 스타일이 적용됩니다.
- (2) **:nth-child(n)와 :nth-last-child(n) 가상 클래스 선택자** - 자식 요소의 위치에 따라 스타일 적용하기 
  - :nth-child(n)는 앞에서 부터 n번째 자식 요소에 스타일을 적용 
  - :nth-last-child(n)는 끝에서 부터 n번째인 자식 요소에 스타일을 적용 
  - an+b처럼 수식을 사용할 수도 있는데 이때 n값은 0부터 차례대로 정수를 대입해 계산합니다.
  - 다만 위치에 따라 스타일을 적용하는 선택자는 해당 요소들이 모두 한 부모 요소를 갖고 있어야 합니다. 즉, 문서 구조로 표시했을 때 모두 같은 레벨의 요소여야 합니다.

```html
/* div 요소 안에서 세 번째 자식 요소인 p 요소에 스타일 적용 */
div p:nth-child(3)

/* div 요소 안에서 홀수 번째로 나타나는 자식 요소인 p 요소에 스타일 적용 */
div p:nth-child(odd), div p:nth-child(2n+1)

/* div 요소 안에서 짝수 번째로 나타나는 자식 요소인 p 요소에 스타일 적용 */
div p:nth-child(even), div p:nth-child(2n+0), div p:nth-child(2n)
```

```html
<style>
  table tr:nth-child(2n+1) {
    background:lightgray;
    color:black;
  }
</style>

...

<h1>건강에 좋은 건강 식품</h1>
<table>
  <tr>
    <td>블루베리</td>
  </tr>
  <tr>
    <td>귀리</td>
  </tr>
  <tr>
    <td>토마토</td>
  </tr>
  <tr>
    <td>시금치</td>
  </tr>
  <tr>
    <td>적포도주</td>
  </tr>
  <tr>
    <td>견과류</td>
  </tr>
  <tr>
    <td>브로콜리</td>
  </tr>
  <tr>
    <td>연어</td>
  </tr>
  <tr>
    <td>마늘</td>
  </tr>
  <tr>
    <td>녹차</td>
  </tr>
</table>
```

- (3) **:nth-of-type(n), :nth-last-of-type(n) 가상 클래스 선택자** - 특정 태그 위치에 스타일 적용하기
  - :nth-of-type(n)은 앞에서부터 세어 n번째 요소에 스타일 적용
  - :nth-last-of-type(n)은 끝에서부터 세어 n번째 요소에 스타일 적용 

- (4) **:first-child, :last-child 가상 클래스 선택자** - 첫 번째, 마지막 요소에 스타일 적용하기
  - :first-child는 첫 번째 자식 요소를 선택해 스타일을 적용 
  - :last-child는 마지막 자식 요소에 스타일을 적용 


```html
<style>
  /* 첫번째 항목의 스타일 */
  ul.navi li:first-child {
    border-top-left-radius: 1em;/* 왼쪽 상단 코너를 부드럽게 */
    border-bottom-left-radius: 1em;/* 왼쪽 하단 코너를 부드럽게 */
  }
  
  /* 마지막 항목의 스타일 */
  ul.navi li:last-child {
    border-top-right-radius: 1em; /*오른쪽 상단 코너를 부드럽게 */
    border-bottom-right-radius: 1em;/* 오른쪽 하단 코너를 부드럽게 */
  }
</style>

...

<ul class="navi">
  <li id="home"><a href="#">Home</a></li>
  <li id="html"><a href="#">HTML5</a></li>
  <li id="css"><a href="#">CSS3</a></li>
  <li id="jquery"><a href="#">JQuery</a></li>
</ul> 
```

- (5) :first-of-type, :last-of-type 가상 클래스 선택자 - 형제 관계 요소의 위치에 따라 스타일 적용하기
  - 형제 관계인 요소 중에서 :first-of-type은 첫 번째 요소, :last-of-type은 마지막 요소에 스타일을 적용합니다. 

- (6) :only-child, :only-ot-type 가상 클래스 선택자 - 하나뿐인 자식 요소에 스타일 적용하기
  - :only-child는 부모 요소 안의 자식 요소가 유일하게 하나일 때 스타일 적용 
  - :only-of-type은 :only-child와 비슷한데 해당 요소가 유일한 요소일 때 스타일을 적용합니다. 

```css
p:only-child { color: green; }
p:only-of-type { font-weight: bold; }
```

## 그 외 가상 클래스

- (1) **:target 가상 클래스 선택자** - 앵커 목적지에 스타일 적용하기
  - 같은 문서 안에서 다른 위치로 이동할 떄는 앵커(anchor)를 이용합니다. 
  - 이때 :target 선택자를 이용하면 앵커로 연결된 부분, 즉 앵커의 목적지가 되는 부분의 스타일을 지정할 수 있습니다. 

```css
#intro:target { background-color: yellow; }
```

- (2) **:not 가상 클래스 선택자** - 특정 요소가 아닐 때 스타일 적용하기 
  - not은 '괄호 안에 있는 요소를 제외한' 이라는 의미입니다. 

```css
p:not(#ex) { color: blue; }
```

## 가상 요소
- 내용의 일부만 선택해 스타일을 적용할 때 사용
- 가상 요소는 가상 클래스와 구별하기 위해 클래스 이름 앞에 콜론 두개(::)를 붙여 표시합니다. 
- (1) **::first-line 요소와 ::first-letter 요소** - 첫 번째 줄, 첫 번째 글자에 스타일 적용하기
- (2) **::before, ::after 요소** - 내용의 앞 뒤에 콘텐츠 추가하기

```html
<style>
  li.hot::after {
    content:"NEW!!";
    font-size:x-small;
    padding:2px 4px;
    margin: 0 10px;
    border-radius:2px;
    background:#f00;
    color:#fff;
  }
</style>

...

<ul>
  <li class="hot">제품 A</li>
  <li>제품 B</li>
  <li>제품 C</li>
  <li class="hot">제품 D</li>
</ul>
```