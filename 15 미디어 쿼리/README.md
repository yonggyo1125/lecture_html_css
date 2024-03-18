# 미디어 쿼리 이해하기 

## 미디어 쿼리란? 

- CSS3 모듈 중 하나로 사이트에 접속하는 장치에 따라 특정한 CSS 스타일을 사용하도록 해 줍니다.

## 미디어 쿼리 구문

- <code>@media</code> 속성을 사용해 특정 미디어에서 어떤 CSS를 적용할 것인지 지정해줍니다. 

```
@media [only | not] 미디어 유형 [and 조건] * [and 조건]
```

- 미디어 쿼리 구문은 \<style\>과 \</style\> 사이에 사용하며 대,소문자를 구별하지 않습니다. 
- 기본적으로 미디어 유형이 지정되어야 하고 필요할 경우, and 연산자로 조건을 적용합니다.
- 미디어 유형이 'screen'이면서 최소 너비가 '200px'이고 최대 너비가 '360px'일 경우에 적용할 CSS를 정의하는 구문입니다.


```css
@media screen and (min-width: 200px) and (max-width: 360px) {
    ...
}
```

- 미디어 쿼리 구문에서 사용할 수 있는 연산자

|연산자|설명|
|---|----|
|and|앞의 소스처럼 조건을 계속 추가할 수 있습니다.|
|,(쉼표)|동일한 스타일 유형을 사용할 미디어의 유형과 조건이 있다면 쉼표를 이용해 추가합니다.|
|only|미디어 쿼리를 지원하는 웹 브라우저에서만 조건을 인식하게 합니다. 이 키워드를 사용하면 미디어 쿼리를 지원하지 않는 웹 브라우저에서는 미디어 쿼리를 무시하고 실행하지 않습니다. IE에서는 미디어 쿼리를 제대로 인식하지 못하기 때문에 only 키워드를 사용하더라도 큰 의미가 없습니다.|
|not|not 다음에 지정하는 미디어 유형을 제외합니다. 예를 들어 'not tv'라고 지정한다면 TV를 제외한 미디어 유형에만 적용합니다.|

### 미디어 유형의 종류 

- 미디어 쿼리는 미디어별로 적용할 CSS를 따로 작성하기 때문에 <code>@media</code> 속성 다음에 미디어 유형을 알려주어야 합니다. 

|미디어 유형|사용 가능한 미디어|
|---|----|
|all|모든 미디어 유형|
|print|인쇄 장치|
|screen|컴퓨터 스크린(스마트폰 스크린 포함)|
|tv|음성과 영상이 동시 출력되는 TV|
|aural|음성 합성 장치(주로 화면을 읽어 소리로 출력해 주는 장치)|
|braille|점자 표시 장치|
|handheld|패드(pad)처럼 손에 들고 다니는 장치|
|projection|프로젝터|
|tty|디스플레이 기능이 제한된 장치(픽셀(px) 단위를 사용할 수 없음)|
|embosses|점자 프린터|

## 미디어 쿼리의 조건 

### 웹문서의 가로 너비와 세로 높이
- 뷰포트 : 실제 웹 문서의 내용이 화면에 보이는 영역
- 뷰포트의 너비와 높이를 미디어 쿼리의 조건으로 사용할 수 있습니다. 
- 이때 height(높이) 값은 미디어에 따라 달라지기 때문에 주의해야 합니다.

> screen이 아닌 미디어에서는 스크롤을 포함한 전체 문서를 height로 지정해야 하며 print에서 한 페이지 높이를 기준으로 합니다. 

|가로, 세로 값 설정하는 속성|설명|
|---|----|
|width, height|웹 페이지의 가로 노비, 세로 높이|
|min-width, min-height|최소 너비, 최소 높이|
|max-width, max-height|최대 너비, 최대 높이|

- 뷰포트의 너비가 600px 이상이고 959px 이하일 때 적용할 CSS는 다음과 같이 정의합니다. 

```css
@media all (min-width: 600px) and (max-width: 959px) {
    ...
}
```

```html
<style>
	body {
		background: url(images/bg0.jpg) no-repeat fixed;  /* 문서의 기본 배경 */
		background-size: cover;
	}
	@media screen and (max-width:1024px) {  /* 화면 너비 1024px 이하일 때의 배경 */
		body {
			background: url(images/bg1.jpg) no-repeat fixed;
			background-size: cover;
		}
	}
	@media screen and (max-width:768px) { /* 화면 너비 768px 이하일 때의 배경 */
		body {
			background: url(images/bg2.jpg) no-repeat fixed;
			background-size:cover;
		}
	}
	@media screen and (max-width:320px) { /* 화면 너비 320px 이하일 때의 배경 */
		body {
			background: url(images/bg3.jpg) no-repeat fixed;
			background-size: cover;
		}
	}
</style>
```

### 단말기의 가로 너비와 세로 높이
- 대부분의 단말기들은 단말기 해상도와 실제 브라우저의 너비가 다르다는 것 
- 단말기 너비나 높이를 고려해 미디어 쿼리를 작성해야 한다면 다음과 같은 속성을 사용합니다.

|단말의 가로, 세로 값을 설정하는 속성|설명|
|---|----|
|device-width, device-height|단말기의 가로 너비, 세로 높이|
|min-device-width, min-device-height|단말기의 최소 너비, 최소 높이|
|max-device-width, max-device-height|단말기의 최대 너비, 최대 높이|

- 단말기 너비가 320px 이상이고 높이가 480px 이상일 때 실행할 미디어 쿼리

```css
@media all and (min-device-width: 320px) and (min-device-height: 480px) {
    ...
}
```

> 단말기 크기와 뷰포트 크기를 하나로 통일해 사용하기 위해 뷰포트를 지정할 때 width="device-width"로 놓고 사용합니다.

### 화면 회전

- orientation 속성을 사용하면 화면 방향을 체크할 수 있습니다.

|속성|설명|
|---|----|
|orientaion: portrait|단말기 세로 방향|
|orientation: landscape|단말기 가로 방향|

```html
<style>
    body {
        background-color: #eee;
    }
    
    @media screen and (orientation: landscape) {  /* 가로 방향일 때 오렌지색 배경 */
        body { background-color: orange; } 
    }
    
    @media screen and (orientation: portrait) { /* 세로 방향일 때 노란색 배경 */
        body { background-color: yellow; }
    }
</style>

<h1>Media Query</h1>
```

### 화면 비율, 단말기의 물리적 화면 비율

- 화면 비율은 뷰포트, 즉 단말기 브라우저 화면의 너비 값(width)을 높이 값(height)으로 나눈 것으로 숫자 값이나 계산식을 사용할 수 있습니다.

|속성|설명|
|---|----|
|aspect-ratio|화면 비율(width 값 / height 값)|
|min-aspect-ratio|최소 화면 비율|
|max-aspect-ratio|최대 화면 비율|


- 단말기 화면 비율은 단말기의 너비 값(device-width)과 높이 값(device-height)을 이용해 계산합니다. 

|속성|설명|
|---|----|
|device-aspect-ratio|단말기 화면 비율(width 값 / height 값)|
|min-device-aspect-ratio|단말기 최소 화면 비율|
|max-device-aspect-ratio|단말기 최소 화면 비율|

- 화면 비율이 16:9일 때와 16:9 이상일 때, 16:9 이하일 때로 나누어 실행할 미디어 쿼리 정의 

```css
@media all and (device-aspect-ratio:16/9) {
    ....
}

@media all and (min-device-aspect-ratio:16/9) {
    ...
}

@media all and (max-device-aspect-ratio:16/9) {
    ...
}
```


### 미디어 쿼리 중단점 만들기 
- 미디어 쿼리를 작성할 때 서로 다른 CSS를 적용할 화면 크기를 중단점(break point)이라고 합니다. 
- 이 중단점을 어떻게 지정하는가에 따라 CSS가 달라지고 화면 레이아웃이 바뀌는데 대부분 기기의 화면 크기를 기준으로 합니다.
- 하지만 시중의 모든 기기들을 반영할 수는 없기 때문에 모바일 기기와 태블릿, 데스크톱 정도로만 구분하는 것이 좋습니다. 
- 처리속도나 화면 크기 등에서 다른 기기보다 모바일 기기의 제약 조건이 더 많기 때문에 모바일 기기의 레이아웃을 기본으로 해 CSS를 만듭니다.
- 그런 후에 사양이 휼륭하고 화면이 큰 태블릿과 데스크톱에 맞추어 더 많은 기능과 스타일을 추가합니다. 
- 이렇게 모바일을 먼저 고려해 미디어 쿼리를 작성하는 것을 <code>모바일 퍼스트(mobile first)</code>라고 합니다.
---

# 미디어 쿼리 적용하기 

## 외부 CSS 파일 연결하기 

### \<link\> 태그 사용하기 

```html
<link rel="stylesheet" media="미디어 쿼리 조건" href="css 파일 경로">
```

- 예를 들어 인쇄용 스타일 시트 print.css를 만들어 놓았다면 다음과 같이 연결할 수 있습니다. 

```html 
<link rel="stylesheet" media="print" href="css/print.css">
```

- 화면 너비가 768px 이하일 때 적용할 태블릿용 스타일 시트 파일을 만들어 놓았다면 조건을 좀 더 추가해 다음과 같이 작성할 수도 있습니다.

```html
<link rel="stylesheet" media="screen and (max-width: 768px)" href="css/table.css">
```

### @import 구문 사용하기

- 외부 CSS 파일을 연결할 때 \<link\> 태그 대신 @import 구문을 사용할 수도 있습니다.
- @import 구문은 CSS를 정의하는 \<style\> 태그와 \</style\> 태그 사이에서 사용합니다. 

```css
@import url(css 파일 경로) 미디어 쿼리 조건
```

```css
@import url("css/table.css") only screen and (min-width: 321px) and (max-width: 768px);
```

## 웹 문서에서 직접 정의하기 

- \<style\> 태그 안에서 media 속성을 사용해 조건을 지정하고 그 조건에 맞는 스타일을 정의하는 것

```html
<style media="미디어 쿼리 조건">
    스타일 규칙들 
</style>
```

```html
<style media="screen and (max-width: 320px)">
    body {
        background-color: orange;
    }
</style>
```

- 스타일을 선언할 때 @media 구문을 사용해 각 조건별로 스타일을 지정해 놓고 선택적으로 스타일을 적용하는 것 

```html
<style>
    @media 미디어 쿼리 조건 {
        스타일 규칙들 
    }
</style>
```

```html
@media screen and (max-width: 320px) {
    body {
        background-color: orange;
    }
}
```