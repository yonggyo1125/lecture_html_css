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