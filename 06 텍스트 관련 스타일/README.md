# 글꼴 관련 스타일 

## font-family 속성 - 글꼴 지정하기

```css 
font-family: <글꼴 이름>[,<글꼴 이름>, <글꼴 이름>]
```

```css
p { font-family: 굴림; }
```

- 속성 값은 주로 큰 따옴표를 사용합니다. 예를 들어 텍스트 글꼴을 지정할 때 "맑은 고딕"처럼 두 단어 이상으로 된 글꼴 이름이라면 따옴표로 묶어 표시합니다.
- 웹 문서에서 글꼴을 지정할 떄는 한 가지 글꼴만 지정하기도 하지만 지정한 글꼴이 없을 경우에 대비해 두 번째, 세 번째 글꼴까지 지정해야 합니다. 
- 두 개 이상의 글꼴 이름을 지정할 떄는 글꼴 이름과 이름 사이의 쉼표(,)로 구분합니다.

```css
body { font-family: "맑은 고딕", 돋움, 굴림 }
```
- 만약 "맑은 고딕" 글꼴이 없다면 "돋움" 글꼴로 적용하고 그 글꼴마저 없다면 "굴림" 글꼴로 적용하라는 의미

## @font-face 속성 - 웹 폰트 사용하기 

- 웹폰트란 웹 문서를 작성할 떄 웹 문서 안에 글꼴 정보도 함께 저장했다가 사용자가 웹 문서에 접속하면 글꼴을 사용자 시스템으로 다운로드시키는 방식입니다. 
- 사용자 시스템이 없는 글꼴이더라도 웹 문서를 통해 필요한 글꼴들을 사용자 컴퓨터에 다운로드한 후 표시하기 때문에 웹 제작자가 의도한 대로 텍스트를 표시할 수 있습니다.

### 구글 웹 폰트 사용하기

```html
<!DOCTYPE html>

<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>웹 폰트 사용하기</title>
    <style>
      @import url('https://fonts.googleapis.com/css2?family=Nanum+Gothic&display=swap'); /* 구글 웹 폰트 */
      .ng-font {
        font-family:'Nanum Gothic', 돋움;  /* 웹 폰트 지정 */
      }
      p {
        font-size:30px; /* 글자 크기 */
      }
    </style>
</head>
<body>
  <p>브라우저 기본 글꼴 사용</p>
  <p class="ng-font">나눔고딕 웹 폰트 사용</p>
</body>
</html>
```

### 직접 웹 폰트 업로드해 사용하기
- 구글 웹 폰트처럼 웹 폰트를 제공하는 인터넷 사이트가 있기 때문에 주로 링크해 사용하지만 사이트에서 제공하지 않는 폰트이거나 자신이 가지고 있는 ttf 폰트를 변환해 사용한다면 직접 업로드해 사용해야 합니다.
- 컴퓨터에서 사용하는 글꼴은 투르타입(TrueType) 유형이고 파일 확장자는 *.ttf 입니다. 하지만 트루타입 유형의 글꼴은 파일 크기가 너무 크기 떄문에 다른 글꼴이 등장했습니다. 이렇게 등장한 웹에 적합한 여러 글꼴 유형 중에서 eot(Embedded Open Type)와 woff(Web Open Font Format) 파일이 가장 많이 사용됩니다. 
- 웹 폰트 변환사이트는 꽤 많은데 그 붕에서 Transfonter(https://transfonter.org/)에서 한글 폰트까지 변환할 수 있습니다. 

> ttf 파일을 eot나 woff로 변환해 웹 폰트로 사용하려면 허락을 받아야 합니다. ttf 글꼴을 구입했더라도 그것은 웹 폰트 사용까지 허락한 것은 아니므로 무조건 웹 폰트로 변환해 사용해서는 안됩니다. 글꼴 사용에 대해서는 사용권 범위가 까다롭기 때문에 반드시 사전에 확인해야 합니다.

### 웹폰트 적용하기

```css
@font-face {
    font-family: 글꼴 이름;
    src:url(글꼴 파일 경로) format(파일 유형);
}
```

```html
<!DOCTYPE html>

<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>웹 폰트 사용하기</title>
    <style>
      @font-face {
        font-family: 'trana'; /* 글꼴 */
        src: local('trana'),
            url('trana.eot'),
            url('trana.woff') format('woff'),
            url('trana.ttf') format('truetype');
       }
      .w-font {
        font-family:'trana', sans-serif; /* 웹 폰트 지정 */
      }
      p {
        font-size:30px; /* 글자 크기 */
      }
    </style>
</head>
<body>
  <p>Using Default Fonts</p>
  <p class="w-font">Using Trana Fonts</p>
</body>
</html>
```

## font-size 속성 - 글자 크기 조절하기

```css 
font-size: <절대 크기> | <상대 크기> | <크기> | <백분율>
```

- font-size 속성에서 사용하는 속성 값은 다음과 같습니다. 

|속성 값| 설명                                                    |
|----|-------------------------------------------------------|
|\<절대 크기\>| 브라우저에서 지정한 글자 크기 입니다. 사용할 수 있는 값은 xx-small \| x-small \| small \| medium \| large \| x-large \| xx-large 입니다. |
|\<상대 크기\>| 부모 요소의 글자 크기(font-size)를 기준으로 더 크게 표시하거나 더 작게 표시합니다. 사용할 수 있는 값은 larger \| smaller 입니다. |
|\<크기\>| 브라우저와 상관없이 글자 크기를 직접 작성합니다.                           |
|\<백분율\>| 부모 요소의 글자 크기를 기준으로 해당하는 %를 계산해서 표시합니다(%와 함께 표기해야 합니다).|

- \<크기\> 값을 직접 지정하는 방법을 사용할때 사용할 수 있는 단위

|단위|설명|
|---|----|
|em|해당 글꼴의 대문자 M의 너비를 기준으로 크기를 조절합니다.|
|ex|x-height(엑스 하이트), 해당 글꼴의 소문자 x의 높이를 기준으로 크기를 조절합니다.|
|px|픽셀 모니터에 따라 상대적 크기가 됩니다.|
|pt|포인트. 일반 문서에서 많이 사용하는 단위입니다.|

## font-weight 속성 - 글자 굵기 지정하기 

```css
font-weight: normal | bold | bolder | lighter | 100 | 200 | 300| 400 | 500 | 600 | 700 | 800 | 900
```

- 사용하는 속성은 다음과 같습니다.

| 속성값                 |설명|
|---------------------|----|
|normal               |일반적인 형태로 기본 값입니다.|
|bold\|lighter\|bolder|굵게\|원래 굵기보다 더 가늘게\|원래 굵기보다 더 굵게 나타냅니다.|
|100~900 사이의 수치|400은 normal, 700은 bold에 해당하며 숫자 값을 조절해 줌, 더 세밀히 글꼴 두께를 조절할 수 있습니다.|

## font-variant 속성 - 작은 대문자로 표시하기 

- 작은 대문자란 대문자를 소문자 크기에 맞추어 작게 표시한 것

```
font-variant: normal | small-caps
```

|속성 값|설명|
|---|----|
|normal|일반적인 형태로 표시합니다.|
|small-caps|작은 대문자로 표시합니다.|

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>Font Variant & Weight</title>
    <style>
      .accent {
        font-variant:small-caps;  /* 작은 대문자 */
        font-weight:bold; /* 굵게 */
      } 
    </style>
</head>
<body>
  <h1>세계 3대 미항</h1>
  <p><span class="accent">시드니(Sydney)</span>, 호주</p>
  <p><span class="accent">리우데자네이루(Rio de Janeiro)</span>, 브라질</p>
  <p><span class="accent">나폴리(Naples)</span>, 이탈리아</p>
</body>
</html>
```

## font-style 속성 - 글자 스타일 지정하기 

```css
font-style: normal | italic | oblique
```

|속성 값|설명|
|---|-----|
|normal|일반적인 형태로 표시합니다.|
|italic|이탤릭체로 표시합니다.|
|oblique|이탤릭체로 표시합니다.|

> italic은 기울어진 글꼴이 처음부터 디자인되어 있는 반면, oblique는 원래 글꼴을 단지 기울어지게 표시할 뿐입니다. 대부분 기울어진 형태에 맞게 글꼴이 다듬어져 있기 때문에 웹에서는 주로 italic을 사용합니다.

## font 속성 - 글꼴 속성을 한꺼번에 묶어서 표현하기
- font 속성을 이용하면 font-style과 font-variant, font-weight, font-size/line-height, font-family 속성들을 한꺼번에 묶어 약식으로 표현할 수 있습니다.

```
font: <font-style><font-variant><font-weight><font-size/line-height><font-family> | caption | icon | menu | message-box | small-caption | status-bar
```

|속성 값|설명|
|---|----|
|font-*|font로 시작하는 글꼴 관련 속성을 한꺼번에 나열합니다.|
|caption|캡션에 어울리는 글꼴 스타일로 표시합니다.|
|icon|아이콘에 어울리는 글꼴 스타일로 표시합니다.|
|menu|드롭다운 메뉴에 어울리는 글꼴 스타일로 표시합니다.|
|message-box|대화상자에 어울리는 글꼴 스타일로 표시합니다.|
|small-caption|작은 캡션에 어울리는 글꼴 스타일로 표시합니다.|
|status-bar|상태 표시줄에 어울리는 글꼴 스타일로 표시합니다.|

```css
p { font: 16px/25px "맑은 고딕" }
p { font: bold italic 12pt }
p { font: 120%/120% bold }
```


---
# 텍스트 스타일 

## color 속성 - 글자 색 지정하기

- 글자 색을 바꿀때 사용 
- color 속성에 사용할 수 있는 색상 값은 16진수나 rgb(또는 rgba), hsl(또는 hsla) 또는 색상 이름으로 표기할 수 있습니다.

```css
color: <색상>
```

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="utf-8">
  <title>뉴욕타임즈 10대 식품</title>
  <style>
    h1 {color:rgb(0,200,0);}  /* rgb 값 사용 - 녹색 계열 */
    h2 {color:blue;}  /* 색상 이름 사용 - 파랑 */
    .accent {color:#f00;} /* 16진수 사용 - 빨강, #ff0000으로도 사용 */
	img {
		float:right;  /* 오른쪽 정렬 */
		margin-right:10px; /* 오른쪽 마진 여백 */
	}
  </style>
</head>
<body>
  <h1>세계 10대 슈퍼푸드</h1>
  <img src="images/galic.jpg" alt="">
  <h2>마늘(Garlic)</h2>
  <p>일해백리(一害百利)는 마늘의 별명이다. 한가지 해가 있고 백가지 이로움이 있다는 뜻이다. 
  그 한 가지 해란, 아린 맛으로 인해 위에 부담을 준다는 것이다. </p>
  <p>마늘 특유의 아린 맛은 <span class="accent">알리신</span>이라는 성분 때문으로, 살균 및 항균 작용을 하며  
  마늘에 들어 있는 아연이 피로 회복에 도움을 준다.</p>
    
</body>
</html>
```

## text-decoration 속성 - 텍스트에 줄 표시하기/없애기

- 텍스트에 밑줄을 긋거나 취소 선을 표시할 수 있습니다.

```
text-decoration: none | underline | overline | line-through
```

|속성 값|설명|
|---|----|
|none|밑줄을 표시하지 않습니다.|
|underline|밑줄을 표시합니다.|
|overline|영역 위로 선을 그립니다.|
|line-through|영역을 가로지르는 선(취소 선)을 그립니다.|


```html
<style>
    p {line-height: 1.8;}
    a {text-decoration:none;}  /* 밑줄 없앰 */
    .edited {text-decoration:line-through;}  /* 취소선 */
</style>

<p>다양한 기기로 인터넷에 접속할 수 있는 요즘, <br>
    <span class="edited">HTML4</span> HTML5를 공부해야 할 때입니다.</p>
<p><a href="https://html.spec.whatwg.org/" target="_blank"><b>HTML5 표준 규약 살펴보기</b></a></p>
```

## text-transform 속성 - 텍스트 대,소문자 변환하기
- 텍스트를 대,소문자 또는 전각 문자로 변환합니다.
- 이 속성은 한글에는 영향을 미치지 않고 영문자에만 적용됩니다.

```
text-transform: none | capitalize | uppercase | lowercase | full-width
```

|속성값|설명|
|---|----|
|none|변환하지 않습니다.|
|capitalize|시작하는 첫 번쨰 글자를 대문자로 변환합니다.|
|uppercase|모든 글자를 대문자로 변환합니다.|
|lowercase|모든 글자를 소문자로 변환합니다.|
|full-width|가능한 모든 문자를 전각 문자로 변환합니다.|

> <code>전각 문자</code>란 고정 폭 영문자 너비의 두 배 정도 너비의 문자이며 전각 문자 너비의 절반 정도 너비인 문자를 <code>반각 문자</code>라고 부릅니다.

```html
<style>
    .trans1 {text-transform:uppercase;}  /* 대문자로 */
    .trans2 {text-transform:capitalize;}  /* 첫글자만 대문자로 */
</style>

<ul>
    <li class="trans1">html</li>
    <li class="trans1">css</li>
    <li class="trans2">javascript</li>
</ul>
```

## text-shadow 속성 - 텍스트에 그림자 효과 추가하기

- 텍스트에 그림자 효과를 추가해 텍스트를 좀 더 입체적으로 보이게 합니다. 

```
text-shadow: none | <가로 거리> <세로 거리> <번짐 정도> <색상>
```
> text-shadow 속성은 가로 거리와 세로 거리만 지정하면 나머지 값은 기본 값을 사용해 텍스트 그림자를 표시할 수 있습니다.

|속성 값|설명|
|---|----|
|\<가로 거리\>|텍스트부터 그림자까지의 가로 거리를 입력합니다. 양수 값은 글자 오른쪽, 음수 값은 글자 왼쪽에 그림자를 만듭니다. 필수 속성입니다.|
|\<세로 거리\>|텍스트부터 그림자까지의 세로 거리를 입력합니다. 양수 값은 글자 아래쪽, 음수 값은 글자 위쪽에 그림자를 만듭니다. 필수 속성입니다.|
|\<번짐 정도\>|그림자가 번지는 정도를 나타냅니다. 양수 값을 사용하면 그림자가 모든 방향으로 퍼져 나가기 때문에 그림자가 크게 표시됩니다. 반대로 음수 값은 그림자가 모든 방향으로 축소되어 보입니다. 기본값은 0입니다.|
|\<색상\>|그림자 색상을 지정합니다. 한 가지만 지정할 수도 있고 공백으로 구분해서 여러 색상을 지정할 수도 있습니다. 기본 값은 현재 글자 색입니ㅏㄷ.|

```html
<style>
    .shadow1{ 
		color:orange; /* 글자색 */
		text-shadow:1px 1px;  /* 텍스트 그림자 */
    }
  	.shadow2 {
  		text-shadow: 5px 5px 3px #f00;  /* 텍스트 그림자 */
  	}
    .shadow3 { 
		color:#fff;  /* 글자색 */
		text-shadow:7px -7px 5px #000;  /* 텍스트 그림자 */
	}
</style>

<h1 class="shadow1">HTML5</h1>
<h1 class="shadow2">HTML5</h1>
<h1 class="shadow3">HTML5</h1>
```

- 보통 그림자 값은 하나만 사용하지만 여러 개를 사용하면 마치 그래픽으로 처리한 듯한 텍스트를 만들 수도 있습니다. 

```html

```css
.shadow3 {
    color: #000; /* 글자색 */
    text-shadow: 0 0 4px #ccc, 0 -5px 4px #ff3, 2px -10px 6px #fd3, -2px -15px 11px #f80, 2px -19px 18px #f20;  /* 텍스트 그림자 */
}
```

## white-space 속성 - 공백 처리하기
- 텍스트와 함께 연속해 입력된 여러 개의 공백을 어떻게 처리할지 지정할 수 있습니다.

```
white-space: normal | nowrap | pre | pre-line | pre-wrap 
```

|속성 값|설명|
|---|----|
|normal|여러 개의 공백을 하나로 표시합니다. 기본값|
|nowrap|여러 개의 공백을 하나로 표시하고 영역 너비를 넘어가는 내용은 줄을 바꾸지 않고 계속 한 줄로 표시합니다.|
|pre|여러 개의 공백을 그대로 표시하고 영역 너비를 넘어가는 내용은 줄을 바꾸지 않고 계속 한 줄로 표시합니다.|
|pre-line|여러 개의 공백을 하나로 표시하고 영역 너비를 넘어가는 내용은 자동으로 줄을 바꿔 표시합니다.|
|pre-wrap|여러 개의 공백을 그대로 표시하고 영역 너비를 넘어가는 내용은 자동으로 줄을 바꿔 표시합니다.|

```
td { white-space: nowrap; }  /* 줄 바꿈 없음 */
```

## letter-spacing과 word-spacing 속성 - 텍스트 간격 조절하기 

- <code>letter-spacing</code>: 낱 글자 사이 간격을 조절
- <code>word-spacing</code>: 단어와 단어 사이 간격을 조절

```css
letter-spacing: normal | <크기>
word-spacing: normal | <크기>
```

```html
<style>
    .letter1 {
      letter-spacing: 0.2em;  /* 자간 */
    }
    .letter2{
      letter-spacing:0.5em; /* 자간 */
    }
</style>

<h1>HTML5</h1>
<h1 class="letter1">HTML5</h1>
<h1 class="letter2">HTML5</h1>
```

---
# 문단 스타일 

## direction 속성 - 글자 쓰기 방향 지정하기

```
direction: ltr | rtl
```

|속성 값|설명|
|---|----|
|ltr|왼쪽에서 오른쪽으로(left-to-right) 텍스트를 표시합니다. 기본 값입니다.|
|rtl|오른쪽에서 왼쪽으로(right-to-left) 텍스트를 표시합니다.|


## text-align 속성 - 텍스트 정렬하기 

```
text-align: start | end | left | right | center | justify | match-parent
```

|속성 값|설명|
|---|----|
|start|현재 텍스트 줄의 시작 위치에 맞추어 문단을 정렬합니다. left-to-right 언어라면 왼쪽으로 right-to-left 언어라면 오른쪽에 맞추어 정렬합니다.|
|end|현재 텍스트 줄의 끝 위치에 맞추어 문단을 정렬합니다. left-to-right 언어라면 오른쪽으로, right-to-left 언어라면 왼쪽으로 맞추어 정렬합니다.|
|left|왼쪽에 맞추어 문단을 정렬합니다.|
|right|오른쪽에 맞추어 문단을 정렬합니다.|
|center|가운데 맞추어 문단을 정렬합니다.|
|justify|양족에 맞추어 문단을 정렬합니다.|
|match-parent|부모 요소를 따라 문단을 정렬합니다. 다만 부모 요소의 속성 값이 start나 end일 경우, 부모 요소가 left-to-right인지, right-to-left인지에 따라 left나 right 값으로 계산해 적용합니다.|


```html
<style>
    .align-left {text-align:left;}  /* 왼쪽 정렬 */
    .align-right {text-align:right;}  /* 오른쪽 정렬 */
    .align-center {text-align:center;}  /* 가운데 정렬 */
    .align-justify {text-align:justify; }  /* 양쪽 정렬 */
</style>

<h1>텍스트 정렬 </h1>
<!-- 왼쪽 정렬 -->
<p class="align-left">
    Integer elementum massa at nulla placerat varius.
    Suspendisse in libero risus, in interdum massa.
    Vestibulum ac leo vitae metus faucibus gravida ac in neque.
    Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p>
<!-- 오른쪽 정렬 -->
<p class="align-right">
    Integer elementum massa at nulla placerat varius.
    Suspendisse in libero risus, in interdum massa.
    Vestibulum ac leo vitae metus faucibus gravida ac in neque.
    Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p>

<!-- 가운데 정렬 -->
<p class="align-center">
    Integer elementum massa at nulla placerat varius.
    Suspendisse in libero risus, in interdum massa.
    Vestibulum ac leo vitae metus faucibus gravida ac in neque.
    Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p>

<!-- 양쪽 정렬 -->
<p class="align-justify">
    Integer elementum massa at nulla placerat varius.
    Suspendisse in libero risus, in interdum massa.
    Vestibulum ac leo vitae metus faucibus gravida ac in neque.
    Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p> 
```

## text-justify 속성 - 정렬 시 공백 조절하기

- text-align 속성 값이 justify일 경우, 양쪽 끝에 맞추기 때문에 글자와 단어 사이 간격이 어색하게 벌어질 수 있습니다.
- 이때 간격을 어떻게 조절해 정렬할 것인지 지정하기 위해 사용하는 것이 text-justify 속성 입니다.

```css
text-justify: auto | none | inter-word | distribute
```

|속성 값|설명|
|---|----|
|auto|웹 브라우저에서 자동으로 지정합니다.|
|none|정렬하지 않습니다.|
|inter-word|단어 사이의 공백을 조절해 정렬합니다.|
|distribute|인접한 글자 사이의 공백을 똑같이 맞추어 정렬합니다.|

## text-indent 속성 - 텍스트 들여 쓰기 

```css
text-indent: <크기> | <백분율>
```

|속성 값|설명|
|---|----|
|\<크기\>|단위와 함께 들여 쓸 크기를 지정합니다. 음수 값도 사용할 수 있습니다.|
|\<백분율\>|부모 요소의 너비를 기준으로 상대적 크기를 지정합니다.|

```html
<style>
    .indent1 {text-indent:15px;}  /* 15px만큼 들여쓰기 */
    .indent2 {text-indent:5%;}  /* 5%만큼 들여쓰기 */
</style>

<h1>블루베리(Blueberry)</h1>
<p>블루베리는 비타민A, C, E가 풍부하고 안토니시아민, 페놀 등이 활성 산소를 없애 노화를 억제하고 블루베리의 안토니시아민은 눈의 피로와 시력 저하를 회복시키는 효능을 가지기도 한다.</p>
<p class="indent1">블루베리는 비타민A, C, E가 풍부하고 안토니시아민, 페놀 등이 활성 산소를 없애 노화를 억제하고 블루베리의 안토니시아민은 눈의 피로와 시력 저하를 회복시키는 효능을 가지기도 한다.</p>
<p class="indent2">블루베리는 비타민A, C, E가 풍부하고 안토니시아민, 페놀 등이 활성 산소를 없애 노화를 억제하고 블루베리의 안토니시아민은 눈의 피로와 시력 저하를 회복시키는 효능을 가지기도 한다.</p>
```

## line-height 속성 - 줄 간격 조절하기 

```css
line-height : normal | <숫자> | <크기> | <백분율> | inherit
```

```css
p { font-size: 15px; line-height: 30px; }
p { font-size: 15px; line-height: 2.0; }
p { font-size: 15px; line-height: 200%; }
```

```html
<style>
    .big-line {
      line-height:2;  /* 글자 크기 2배만큼의 줄간격 */
    }
    .small-line {
      line-height: 0.7;  /* 글자 크기 0.7배만큼의 줄간격 */
    }
</style>

<h2>블루베리(Blueberry)</h2>
<p>블루베리의 대표적인 기능은 항산화로 비타민A, C, E가 풍부하고 안토니시아민, 페놀 등이 활성 산소를 없애 노화를 억제한다.
    이밖에 블루베리의 안토니시아민은 눈의 피로와 시력 저하를 회복시키는 효능을 가지고 있다.</p>
<p class="small-line">블루베리의 대표적인 기능은 항산화로 비타민A, C, E가 풍부하고 안토니시아민, 페놀 등이 활성 산소를 없애 노화를 억제한다.
    이밖에 블루베리의 안토니시아민은 눈의 피로와 시력 저하를 회복시키는 효능을 가지고 있다.</p>
<p class="big-line">블루베리의 대표적인 기능은 항산화로 비타민A, C, E가 풍부하고 안토니시아민, 페놀 등이 활성 산소를 없애 노화를 억제한다.
    이밖에 블루베리의 안토니시아민은 눈의 피로와 시력 저하를 회복시키는 효능을 가지고 있다.</p>
```

## text-overflow 속성 - 넘치는 텍스트 표기하기
- 넘치는 텍스트를 어떻게 처리할지 지정하는 속성
- text-overflow 속성은 해당 요소에서 overflow 속성 값이 hidden이거나 scroll, auto이면서 white-space: nowrap 속성을 함께 사용했을 경우에만 적용됩니다. 

```css
text-overflow: clip | ellipsis
```

|속성 값|설명|
|---|----|
|clip|넘치는 텍스트를 자릅니다.|
|ellipsis|말 줄임표(...)로 잘린 텍스트가 있다고 표시합니다.|


```html
<style>
    .content {
      border:1px solid #ccc;  /* 테두리 */
      width:300px;  /* 단락의 너비 */
      white-space:nowrap;  /* 줄바꿈 없음 */
      overflow:hidden;  /* 넘치는 부분 감춤 */
      text-overflow:ellipsis;  /* 말줄임표 */
    }
	.content:hover {
		overflow:visible;  /* 넘치는 부분 보여줌*/
	}
</style>

<p class="content">귀리는 베타글루칸(항암 및 면역증강작용을 가지고 있는 불소화성 다당류) 성분을 포함하고 있다.</p>
```

--- 
# 목록 스타일

## list-style-type 속성 - 목록의 블릿과 번호 스타일 지정하기

- 순서 없는 목록의 경우, 목록 앞에 다양한 블릿(bullet)을 넣을 수 있고 순서 목록에서는 번호 스타일을 지정할 수 있습니다.

```css
list-style-type: none | \<순서 없는 목록 블릿\> | \<순서 목록의 번호\>
```

### 순서 없는 목록에서 블릿 모양 바꾸기 

|속성 값|설명|
|---|----|
|disc(●)|채운 원|
|circle(○)|빈 원|
|square(■)|채운 사각형|
|none|블릿 없애기|

### 순서 없는 목록에서 블릿 없애기

```css
ul { list-style-type: none; }
```

```html 
<style>
    .sqbullet {
      list-style-type:square; /* 채운 사각형 */
    }
    .nobullet{
      list-style-type:none;  /* 불릿 없애기 */
    }
</style>

<!-- 채운 사각형으로 불릿 바꾸기 -->
<ul class="sqbullet">
    <li>회사소개</li>
    <li>도서</li>
    <li>자료실</li>
    <li>질문답변</li>
    <li>동영상강의</li>
</ul>

<!-- 불릿 없애기 -->
<ul class="nobullet">
    <li>회사소개</li>
    <li>도서</li>
    <li>자료실</li>
    <li>질문답변</li>
    <li>동영상강의</li>
</ul>
```

### 순서 목록에서 숫자 바꾸기

|속성 값|설명|예시|
|----|-----|----|


