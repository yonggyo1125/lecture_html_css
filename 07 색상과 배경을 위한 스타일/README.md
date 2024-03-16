# 웹에서 색상 표현하기 

## 16진수 표기법
- \#ffff00 처럼 # 기호 다음에 6자리 16진수로 표시하는 것으로 가징 기본적인 방법입니다.
- 6자리는 앞에서부터 두 자리씩 묶어 \#RRGGBB 형식으로 표시합니다. 
- RR 자리에는 발간색(Red), GG 자리에는 초록색(Green), BB 자리에는 파란색(Blue) 양을 표시합니다. 
- \#ffff00 처럼 두 자리씩 중복될 경우 \#ff0으로 줄여서 표기할 수 있습니다.

## rgb와 rgba 표기법

- 빨간색, 초록색, 파란색의 양을 나타내는데 십진수로 표현합니다. 
- 하나도 섞이지 않았을 때는 0으로 표시하고 가득 섞였을 때는 255로 표시하며 그 사이 값으로 각 색상의 양을 조절합니다.

```
rgb(red 값, green 값, blue 값);
rgba(red 값, green 값, blue 값, alpha 값);
```

```css
color: rgb(255, 0, 0);
```

- rgba에서 맨 끝의 a, 즉 a(alpha)는 불투명도 값을 나타내는 것으로 0부터 1까지의 값 중에서 사용할 수 있습니다.
- 1은 완전 불투명, 0.9나 0.8처럼 숫자가 작아질수록 조심씩 투명해지다가 0이 되면 완전히 투명해집니다.
- 투명도를 표기할 때는 0.5 대신 소수점 앞의 0을 빼고 .5라고 표기해도 됩니다.

```css
color: rgba(255, 0, 0, 0.5);
```

## hsl과 hsla 표기법 

- hsl은 차례대로 hue(색상), saturation(채도), lightness(밝기)를 나타냅니다.

```
hsl(<hue 값>, <saturation 값>, <lightness 값>);
hsla(<hue 값>, <saturation 값>, <lightness 값>, <alpha 값>);
```

- <code>색상(hue)</code>은 색의 3요소 중 하나로 각도를 기준으로 색상을 둥글게 배치한 색상환으로 표시합니다.
- <code>채도(saturation)</code>도 색의 3요소 중 하나로 '%'로 표시하는데 아무 것도 섞이지 않은 상태가 채도가 가장 높은 상태입니다. 채도가 0%면 회색 톤, 100%면 순색으로 표시됩니다.
- <code>밝기(lightness)</code>도 %로 표시하는데 0%가 가장 어둡고 100%가 가장 밝습니다.

## 색상 이름 표기법 

- red, yellow, black 처럼 잘 알려진 색상 이름으로 표시
- 모든 브라우저에서 표현할 수 있는 색상을 웹 안정 색상(web-safe color)라고 하는데 기본 16가지 색상을 포함한 216가지 입니다. 

```html
<style>
    body {
		background:#222;
	}
	.text1 {
		color:rgb(255,255,255);
	}
	.text2 {
		color:rgba(255,255,255,0.8);
	}
	.text3 {
		color:rgba(255,255,255,0.5);
	}
	.text4 {
		color:rgba(255,255,255,0.2);
	}
</style>

<h1 class="text1">HTML5+CSS3</h1>
<h1 class="text2">HTML5+CSS3</h1>
<h1 class="text3">HTML5+CSS3</h1>
<h1 class="text4">HTML5+CSS3</h1>
```

--- 

# 배경 색과 배경 이미지 

## background-color 속성 - 배경 색 지정하기

```css
background-color: <색상>
```

- 16진수나 rgb 값 또는 색상 이름을 사용해 지정합니다.

```css
background-color: #00ff00; /* 16진수 : 세밀히 색상 조절 */
background-color: rgb(0, 255, 0); /* rgba: 필요하면 투명도도 함께 조절 가능 */
background-color: green;   /* 색상 이름 : 원색 사용 */
```

### 배경 색 스타일과 상속

- 예외적으로 background-color 값은 상속되지 않습니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>배경색</title>
    <style>
        body {
          background-color:#0094ff;
        }
        div {   
          background-color:white;   
          width:90%;  /* 너비 */
          padding:15px;  /* 패딩 */
          border:1px solid black;  /* 테두리 */
        }
        p {
          line-height:30px;
        }
    </style>
</head>
<body>
<div>
    <h1>초콜릿(Chocolate)</h1>
    <p>초콜릿은 카카오 콩을 재료로 가공한 식품이다.
        숙성한 카카오 콩을 볶은 뒤 이를 갈아서 만든 카카오 매스와 지방 성분만으로 만들어진 코코아 버터를 혼합하여 만드는데,
        설탕 등의 다른 재료를 더 넣어 만들기도 한다.
        카카오 매스의 함량에 따라 다크 초콜릿, 밀크 초콜릿, 화이트 초콜릿으로 구분한다.</p>
</div>
</body>
</html>
```

## background-clip 속성 - 배경 적용 범위 조절하기

- 박스 모델 관점에서 배경 적용 범위를 조절할 수 수도 있습니다.

> 박스 모델이란 웹 요소 형태를 박스(box)로 인식하고 테두리와 여백, 요소 사이의 간격 등을 계산하고 배치하는 방법을 말합니다. border는 테두리, padding은 테두리와 실제 내용 사이의 여백입니다. 

```css
background-clip: border-box | padding-box | content-box
```

|속성 값|설명|
|---|----|
|border-box|박스 모델의 가장 외곽인 테두리(border)까지 적용합니다.|
|padding-box|박스 모델에서 테두리를 뺀 패딩(padding) 범위까지 적용합니다.|
|content-box|박스 모델에서 내용 부분에만 적용합니다.|

- (1) background-clip: border-box;  - 테두리 부분까지 배경 색이 채워집니다.
- (2) background-clip: padding-box;  - 패딩 부분까지 배경이 채워집니다.
- (3) background-clip: content-box;  - 콘텐츠 부분만 배경이 채워집니다.

## background-image 속성 - 웹 요소에 배경 이미지 넣기 
- 배경 이미지에는 웹에서 사용 가능한 파일인 jpg나 gif, png 파일을 사용하며 이것을 <code>url(파일경로)</code> 형식으로 사용합니다.
- 파일 경로는 현재 웹 문서를 기준으로 상대 경로를 지정할 수도 있고 'http://'로 시작하는 절대 경로를 사용할 수도 있습니다. 
- 파일 경로에는 작은 따옴표(또는 큰따옴표)를 붙여도 되고 안 붙여도 됩니다.

```css
background-image: url(파일 경로)
```

```html
body { background-image: url('bg1.png'); }
#area { background-image: url('bg2.png'); }
```

## background-repeat 속성 : 배경 이미지 반복 방법 지정하기 

```css
background-repeat: repeat | repeat-x | repeat-y | no-repeat
```

|속성 값|설명|
|---|-----|
|repeat|브라우저 화면에 가득 찰 때까지 배경 이미지를 가로와 세로로 반복합니다.|
|repeat-x|브라우저 창 너비와 같아질 때까지 배경 이미지를 가로로 반복합니다.|
|repeat-y|브라우저 창 높이와 같아질 떄까지 배경 이미지를 세로로 반복합니다.|
|no-repeat|배경 이미지를 한 번만 표시하고 반복하지 않습니다.|

## background-size 속성 - 배경 이미지 크기 조절하기

```css
background-size: auto | contain | cover | <크기 값> | <백분율>
```

|속성 값|설명|
|---|----|
|auto|원래 배경 이미지 크기만큼 표시됩니다.|
|contain|요소 안에 배경 이미지가 다 들어오도록 이미지를 확대/축소합니다.|
|cover|배경 이미지로 요소를 모두 덮도록 이미지를 확대/축소합니다.|
|\<크기 값\>|너비 값과 높이 값을 지정합니다. 너비 값만 지정할 경우, 원래 배경 이미지 크기를 기준으로 축소/확애 비율을 자동으로 계산해 높이 값을 지정합니다.|
|\<백분율\>|배경 이미지가 들어갈 요소의 크기를 기준으로 백분율 값을 지정하고 그 크기에 맞도록 배경 이미지를 확대하거나 축소합니다.|

- (1) background-size: auto
    - background-size 속성 값이 모두 auto일 경우, 원래 배경 이미지 크기 그대로 표시됩니다.
- (2) background-size: 200px 150px;
    - 배경 이미지는 너비 200px, 높이 150px 크기로 표시됩니다.
    - 크기 값이 하나만 주어질 경우, 그 값을 너비 값으로 인식하고 이미지의 너비/높이 비율에 맞추어 높이 값도 자동 계산됩니다.
- (3) background-size: 60% 40%;
    - 가로 60%, 세로 40%만큼 배경 이미지를 채우라는 뜻 
    - 속성 값이 하나라면 주어진 값은 너비 값으로 인식하고 높이 값은 자동으로 계산합니다.
- (4) background-size: contain;
  - 요소 안에 모든 배경 이미지가 표시되도록 확대하거나 축소합니다.
- (5) background-size: cover;
  - 요소 전체를 모두 덮도록 배경 이미지를 확대하거나 축소합니다.
- (6) background-size: 100% 100%;
  - 요소의 너비와 높이에 맞도록 배경 이미지를 확대하거나 축소합니다.

## background-position 속성 - 배경 이미지 위치 조절하기

```css
background-position: <수평 위치> <수직 위치>;
수평 위치 : left | center | right | <백분율> | <길이 값>
수직 위치 : top | center | bottom | <백분율> | <길이 값> 
```

## background-origin 속성 - 배경 이미지 배치할 기준 조절하기 

- background-position 속성을 이용해 배경 이미지를 배치할 때 기준이 필요한데 이 기준은 background-origin 속성으로 지정합니다.

```
background-origin: border-box | padding-box | content-box 
```

|속성 값|설명|
|---|----|
|border-box|박스 모델의 가장 외곽인 테두리(border)가 기준이 됩니다.|
|padding-box|박스 모델에서 테두리를 뺀 패딩(padding)이 기준이 됩니다.|
|content-box|박스 모델에서 내용 부분이 기준이 됩니다.|

- (1) background-origin: padding-box;  - 배경 이미지가 패딩 영역부터 시작됩니다.
- (2) background-origin: border-box;  - 배경 이미지가 테두리부터 시작됩니다.
- (3) background-origin: content-box; - 배경 이미지가 콘텐츠 영역부터 시작됩니다.


## background-attachment 속성 - 배경 이미지 고정하기 

- 스크롤을 내렸을 때 배경 이미지도 함께 이동합니다. 
- 하지만 background-attachment 속성을 이용하면 배경 이미지를 고정할 수 있습니다.

```css
background-attachment: scroll | fixed
```

|속성|설명|
|---|----|
|scroll|화면 스크롤과 함께 배경 이미지도 스크롤됩니다. 기본 값입니다.|
|fixed|화면이 스크롤되더라도 배경 이미지는 고정됩니다.|

- background-attachment: fixed; 로 설정하면 웹 문서 화면을 아래로 스크롤하더라도 배경 이미지는 고정되고 내용이 이미지 위에 떠 있는 것처럼 보입니다.

## background 속성 - 속성 하나로 배경 이미지 제어하기 

- 지금까지 설명한 배경 이미지 관련 속성을 background라는 하나의 속성으로 줄여 사용할 수 있습니다.

```css
background:url('images/bg3.jpg') no-repeat fixed right bottom;
```

|속성|속성 값|
|---|----|
|background-image|url('images/bg3.jpg')|
|background-repeat|no-repeat|
|background-attachment|fixed|
|background-position|right bottom|
|background-clip|border-box|
|background-origin|padding-box|
|background-size|auto|

> 속성 값이 다르므로 입력 순서는 상관없습니다.