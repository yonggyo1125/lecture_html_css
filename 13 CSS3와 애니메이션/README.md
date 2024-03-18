#  변형 

## 2차원 변형과 3차원 변형 

- <code>2차원 변형(2D Transform)</code> 
  - 웹 요소를 변형시킬 때 단순히 수평이나 수직으로 이동하고 회전하는 것을 말합니다.
  - 수평이나 수직으로 옮기는 것은 x축과 y축으로 이동하는 것이기 때문에 2차원 좌표를 사용힙니다. 

- <code>3차원 변형(3D Transform)</code>
    - x축과 y축에 원근감을 주는 z축을 추가해 변형시키는 것을 말합니다. 

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/13%20CSS3%EC%99%80%20%EC%95%A0%EB%8B%88%EB%A9%94%EC%9D%B4%EC%85%98/images/1.png)

## transform과 변형 함수
- 이미지를 회전시키거나 이동하는 등 웹 요소를 변형하려면 transform 속성을 사용
- transform: 다음에 변형 함수를 함께 입력해 사용합니다. 

```css
transform: 변형 함수;
```

```css
.photo { transform: translate(50px, 100px); }
```

### 2차원 변형 함수

|변형 함수|설명|
|---|----|
|translate(tx, ty)|지정된 크기만큼 x축과 y축으로 이동합니다.|
|translateX(tx)|지정한 크기만큼 x축으로 이동합니다.|
|translateY(ty)|지정한 크기만큼 y축으로 이동합니다.|
|scale(sx, sy)|지정한 크기만큼 x축과 y축으로 확대/축소합니다.|
|scaleX(sx)|지정한 크기만큼 x축으로 확대/축소합니다.|
|scaleY(sy)|지정한 크기만큼 y축으로 확대/축소합니다.|
|rotate(각도)|지정한 각도만큼 회전합니다.|
|skew(ax, ay)|지정한 각도만큼 x축과 y축으로 왜곡합니다.|
|skewX(ax)|지정한 각도만큼 x축으로 왜곡합니다.|
|skewY(ay)|지정한 각도만큼 y축으로 왜곡합니다.|

### 3차원 변형 함수

|변형 함수|설명|
|---|----|
|matrix3d(n, [,n])|4X4 행렬을 이용해 이동과 확대/축소, 회전 등의 변환을 지정합니다.|
|translate3d(tx, ty, tz)|지정한 크기만큼 x축과 y축, z축으로 이동합니다.|
|traslateZ(tz)|지정한 크기만큼 z축으로 이동합니다.|
|scale3d(sx, sy, sz)|지정한 크기만큼 x축과 y축, z축으로 확대/축소 합니다.|
|scaleZ(sz)|지정한 크기만큼 z축으로 확대/축소합니다.|
|rotate3d(rx, ry, rz, 각도)|지정한 각도만큼 회전합니다.|
|rotateX(각도)|지정한 각도만큼 x축으로 회전합니다.|
|rotateY(각도)|지정한 각도만큼 y축으로 회전합니다.|
|rotateZ(각도)|지정한 각도만큼 z축으로 회전합니다.|
|perspective(길이)|입체적으로 보일 수 있는 깊이 값을 지정합니다.|


## translate 변형 함수 - 요소 이동시키기
- 2차원과 3차원에서 모두 가능한 변형 함수 
- x축 방ㅅ향이나 y축 방향 또는 양쪽 방향으로 이동할 거리를 지정해 해당 요소를 지정한 크기만큼 이동시킵니다.

```css
transform:translate(tx, ty)
transform:translate3d(tx, ty, tz)
transform:translateX(tx)
transform:translateY(ty)
transform:translateZ(tz)
```

```html
<style>
  .movex:hover { transform: translateX(50px); }
  .movey:hover { transform: translateY(20px); }
  .movexy:hover { transform: translate(10px, 20px); }
</style>

...

<div class="origin">
  <div class="movex">
    <img src="images/bus.jpg">
  </div>
</div>
<div class="origin">
  <div class="movey">
    <img src="images/bus.jpg">
  </div>
</div>
<div class="origin">
  <div class="movexy">
    <img src="images/bus.jpg">
  </div>
</div>
```

## scale 변형 함수 - 요소 확대/축소하기
- 괄호 안의 값이 1보다 크면 확대되고 1보다 작으면 축소됩니다.

```css
transform:scale(sx, sy)
transform:scale3d(sx, sy, sz)
transform:scaleX(sx)
transform:scaleY(sy)
transform:scaleZ(sz)
```

```html
<style>
  .scalex:hover { transform: scaleX(1.2); /* 마우스 오버하면 가로로 1.2배 확대 */ }
  .scaley:hover { transform: scaleY(1.5); /* 마우스 오버하면 세로로 1.5배 확대 */ }
  .scale:hover { transform: scale(0.7); /* 마우스 오버하면 가로, 세로로 0.7배 확대 */ }
</style>

...

<div class="origin">
  <div class="scalex">
    <img src="images/fruit.jpg">
  </div>
</div>
<div class="origin">
  <div class="scaley">
    <img src="images/fruit.jpg">
  </div>
</div>
<div class="origin">
  <div class="scale">
    <img src="images/fruit.jpg">
  </div>
</div>
```

## rotate 변형 함수 - 요소 회전하기

- 지정한 각도만큼 웹 요소를 시계 방향이나 시계 반대 방향으로 회전시킵니다. 
- 2차원 함수일 때와 3차원 함수일 때의 기본형이 다릅니다. 

```css
transform:rotate(각도)
```

```css
transform:rotate(rx, ry, 각도)
transform:rotate3d(rx, ry, rz, 각도)
transform:rotateX(각도)
transform:rotateY(각도)
transform:rotateZ(각도)
```

- rotate 변형 함수에서는 일반적인 각도(degree)나 래디안(radian) 값을 사용합니다. 
- 1래디안은 180º / π 입니다.
- 회전 각도가 양수일 경우 시계 방향으로 회전
- 음수일 경우, 시계 반대 방향으로 회전

- 이미지 2차원 회전하기
```html
<style>
.rotate1:hover { transform: rotate(20deg); /* 시계 방향으로 20도 회전 */ }
.rotate2:hover { transform: rotate(-40deg);  /* 시계 반대 방향으로 40도 회전 */ }
</style>

...

<div class="origin">
  <div class="rotate1">
    <img src="images/fruit.jpg">
  </div>
</div>
<div class="origin">
  <div class="rotate2">
    <img src="images/fruit.jpg">
  </div>
</div>
```

- 이미지 3차원 회전하기

```html
<style>
   .origin { perspective: 200px; } 
  .rotatex { transform: rotateX(45deg); /* X축을 기존으로 시계 방향으로 45도 회전 */ }
  .rotatey { transform: rotateY(45deg); /* Y축을 기준으로 시계 방향으로 45도 회전 */ }
  .rotatez { transform: rotateZ(45deg); /* Z축을 기준으로 시계 방향으로 45도 회전 */ }
  .rotatexyz { transform: rotate(2.5, 1.2, -1.5, 45deg); /* X축으로 2.5, Y축으로 1.2, Z축으로 -1.5 만큼의 방향 벡터로 45도 회전 */ }
</style>

...

<div class="origin">
  <div class="rotatex"><img src="images/fruit.jpg" alt=""></div>
</div>
<div class="origin">
  <div class="rotatey"><img src="images/fruit.jpg" alt=""></div>
</div>
<div class="origin">
  <div class="rotatez"><img src="images/fruit.jpg" alt=""></div>
</div>
<div class="origin">
  <div class="rotatexyz"><img src="images/fruit.jpg" alt=""></div>
</div>
```
> 3차원에서 입체적인 느낌을 주기 위해 화면에 깊이감을 주는 perspective 속성을 사용합니다.

## skew 변형 함수 - 요소를 비틀어 왜곡하기
- 2차원 변형만 가능
- 요소를 지정한 각도만큼 비틀어 왜곡합니다.
- 양쪽 방향이나 한쪽 방향으로만 비틀 수 있습니다. 

```css
transform:skew(ax, ay)
transform:skewX(ax)
transform:skewY(ay)
```

```html
<style>
  .skewx:hover { transform: skewX(30deg); /* x축 기준으로 30도 비틀기 */ }
  .skewy:hover { transform: skewY(15deg); /* y축 기준으로 15도 비틀기 */ }
  .skewxy:hover { transform: skew(-25deg, -15deg); /* x축으로 -25도, y축으로 -15도 비틀기 */ }
</style>
  
...

<div class="origin">
  <div class="skewx">
    <img src="images/rose.jpg">
  </div>
</div>
<div class="origin">
  <div class="skewy">
    <img src="images/rose.jpg">
  </div>
</div>
<div class="origin">
  <div class="skewxy">
    <img src="images/rose.jpg">
  </div>
</div>
```

---
# 변형과 관련된 속성들 
- 2차원 변형에 원근감을 추가하면 3차원 변형을 만들 수 있는데, 이때 단순히 z축만 쿠가한다고 해서 원근감이 생기지는 않습니다. 
- 다시 말해 변형할 때 기준이 되는 지점을 바꾸거나 요소의 원근감을 표현하기 위한 다른 속성도 필요합니다.

## transform-origin 속성 - 변형 기준점 설정하기
- transform-origin 속성을 이용하면 축이 아닌 특정 지점을 변형의 기준으로 설정할 수 있습니ㅏㄷ. 
- 2차원 변형과 3차원 변형 모두 사용 가능

```css
transform-origin: <x축> <y축> <z축> | initial | inherit; 
```

- 변형 기준점은 다음과 같이 설정할 수 있습니다. 

|속성 값| 설명                                                                 |
|---|--------------------------------------------------------------------|
|\<x축\>| 원점 기준의 x 좌푯값으로 길이 값이나 \<백분율\>, left, center, right 중에서 사용할 수 있습니다. |
|\<y축\>| 원점 기준의 y 좌표값으로 길이 값이나 \<백분율\>, top, center, bottom 중에서 선택할 수 있습니다. |
|\<z축\>|원점 기준의 z 좌표값으로 값만 사용할 수 있습니다.|

```html
<style>
  .rose { transform: rotateZ(10deg); }
  .ltop .rose { transform-origin: left top; /* 왼쪽 윗부분을 기준으로 변형 */ }
  .rtop .rose { transform-origin: right top; /* 오른쪽 윗부분을 기준으로 변형 */ }
  .lbottom .rose { transform-origin: left bottom; /* 왼쪽 아랫부분을 기준으로 변형 */ }
  .rbottom .rose { transform-origin: right bottom; /* 오른쪽 아랫부분을 기준으로 변형 */ }
</style>

...

<div class="origin">
  <div class="ltop">
    <img src="images/rose.jpg" class="rose">
  </div>
</div>
<div class="origin">
  <div class="rtop">
    <img src="images/rose.jpg" class="rose">
  </div>
</div>
<div class="origin">
  <div class="lbottom">
    <img src="images/rose.jpg" class="rose">
  </div>
</div>
<div class="origin">
  <div class="rbottom">
    <img src="images/rose.jpg" class="rose">
  </div>
</div>
```

## perspective, perspective-origin 속성 - 원근감 표현하기 

- perspective 속성은 3차원 변형에서 사용되는 속성 
- 원래 위치에서 사용자가 있는 방향이나 반대 방향으로 잡아당기거나 밀어내 원근감을 갖게 합니다.
- 속성은 0보다 커야 하며 값이 클수록 사용자로부터 멀어집니다. 

```css
perspective: <크기> | none;
```

|속성 값|설명|
|---|----|
|\<크기\>|원래 위치에서 사용자가 있는 방향으로 얼마나 이동하는지를 픽셀 크기로 지정합니다.|
|none|perspective를 지정하지 않습니다. 기본값|

- perspective-origin 속성을 사용하면 좀 더 높은 곳에서 원근을 조절하는 듯한 느낌을 만들 수 있습니다. 
- 이 속성을 사용하려면 perspective 속성이 함께 지정되어 있어야 합니다. 

```css
perspective-origin: <x축 값> | <y축 값>;
```

|속성 값|설명|
|---|----|
|\<x축 값\>|웹 요소가 x축에서 어디에 위치하는지를 지정합니다. 사용할 수 있는 값은 길이 값이나 백분율, left, right, center 입니다. 기본 값은 50% 입니다.|
|\<y축 값\>|웹 요소가 y축에서 어디에 위치하는지를 지정합니다. 사용할 수 있는 값은 길이 값이나 백분율, top, center, bottom 입니다. 기본 값은 50% 입니다.|

```html
<style>
  .rotatex img { transform: rotateX(50deg); }
  #pers { perspective: 300px; }
</style>

<h4>원본 이미지</h4>
<div>
  <img src="images/sunset.jpg" alt="">
</div>
<div id="no-pers">
  <div class="rotatex">
    <img src="images/sunset.jpg" alt="">
  </div>
</div>
<div id="pers">
  <div class="rotatex">
    <img src="images/sunset.jpg" alt="">
  </div>
</div>
```

## transform-style 속성 - 3D 변형 적용하기

- 여러가지 변형을 동시에 적용할 때 transform-style 속성을 사용하면 부모 요소에 적용한 3D 변형을 하위 요소에도 적용할 수 있습니다. 

```css
transform-style: flat | preserve-3d
```

|속성 값|설명|
|---|----|
|flat|하위 요소를 평면으로 처리합니다.|
|perserve-3d|하위 요소들에 3D효과를 적용합니다.|

```html
<style>
  .box1 {
    background: #82cbd8;
    transform: rotateY(45deg);  /* y축을 기준으로 회전 */
  }
  .box2 {
    background: #0d6097;
    transform-origin: left top;  /* 왼쪽 윗부분 꼭지점을 기준으로 x축 회전 */
    transform: rotateX(45deg);
  }
  #tr-style1 { transform-style: flat; }
  #tr-style2 { transform-style: preserve-3d;
</style>

...

<div class="container">
  <div class="box1" id="tr-style1">
    <div class="box2"></div>
  </div>
</div>
<div class="container">
  <div class="box1" id="tr-style2">
    <div class="box2"></div>
  </div>
</div>
```

## backface-visibility 속성 - 요소의 뒷면 표시하기

- backface-visibility 속성으로 요소의 뒷면, 즉 반대쪽 면을 표시할 것인지를 결정합니다. 

```css
backface-visibility: visible | hidden;
```

|속성 값|설명|
|---|----|
|visible|뒷면을 표시합니다. 기본값|
|hidden|뒷면을 표시하지 않습니다.|

```html
<style>
  .box {
    background: #82cbd8;
    transform: rotateY(135deg);
  }
  #back1 { backface-visibility: hidden; }
  #back2 { backface-visibility: visible; }
</style>

...

<div class="container">
  <div class="box" id="back1">
    <h1>BACK</h1>
  </div>
</div>
<div class="container">
  <div class="box" id="back2">
    <h1>BACK</h1>
  </div>
</div>
```

---
# 트랜지션 

> 트랜지션(transition)은 변형을 넘어 하나의 스타일에서 다른 스타일로 완전히 바꿉니다. 이렇게 스타일이 바뀌는 시간을 조절하면 애니메이션 효과도 낼 수 있습니다.

## 트랜지션이란? 
- 트랜지션(transition)이란 웹 요소의 배경 색이 바뀌거나 도형의 테두기가 원형으로 바뀌는 것처럼 스타일 속성이 바뀌는 것을 말합니다. 
- 시간에 따라 웹 요소의 스타일 속성이 조금씩 바뀌는 것을 트랜지션이라고 합니다.

|속성|설명|
|---|----|
|transition-property|트랜지션 대상을 설정합니다.|
|transition-duration|트랜지션 진행 시간을 설정합니다.|
|transition-timing-function|트랜지션 속도 곡선을 설정합니다.|
|transition-delay|트랜지션 지연 시간을 설정합니다.|
|transition|transition-property와 transition-duration, transition-timing-function, transition-delay 속성을 한꺼번에 설정합니다.|

## transition-property 속성 - 트랜지션을 적용할 속성 지정하기 

- 트랜지션을 어느 속성에 적용할 것인지 선택하는 것 
- transition-property를 사용하지 않을 경우, 모든 속성이 트랜지션 대상이 되고 특정 속성 이름을 입력하면 그 속성에 트랜지션이 적용됩니다. 

|속성 값| 설명                                                                                                                    |
|---|-----------------------------------------------------------------------------------------------------------------------|
|all| all 값을 사용하거나 transition-property를 생략할 경우, 요소의 모든 속성이 트랜지션 대상이 됩니다. 기본 값                                               |
|none| 트랜지션 동안 아무 속성도 바뀌지 않습니다.                                                                                              |
|\<속성 이름\>| 트랜지션 효과를 적용할 속성 이름을 지정합니다. 예를 들어 배경 색만 바꿀 것인지, width 값만 바꿀것인지 원하는 대상만 골라 지정할 수 있습니다. 속성이 여러 개일 경우, 쉼표(,)로 구분해서 나열합니다. |


```css
transition-property: all; /* 해당 요소의 모든 속성에 트랜지션 적용 */
transition-property: background-color; /* 해당 요소의 배경 색에 트랜지션 적용 */
transition-property: width, height; /* 해당 요소의 너비와 높이에 트랜지션 적용 */
```

## transition-duration 속성 - 트랜지션 진행 시간 지정하기

- 진행 시간을 지정해야 그 시간 동안 속성이 자연스럽게 바뀌는 애니메이션 효과를 만들 수 있습니다. 
- 시간 단위는 초(seconds) 또는 밀리초(milliseconds)입니다. 
- 트랜지션 대상이 되는 속성이 여러 개라면 트랜지션 진행 시간도 쉼표(,)로 구분해 순서대로 여러 개를 지정할 수 있습니다.

```html 
<style>
  .tr1 {
	width: 100px;
	height: 100px;
	background-color: blue;
	border: 1px solid black;
	transition-property: width, height; /* 너비와 높이에 트랜지션 적용 */
	transition-duration: 2s, 1s;  /* 너비 값은 2초, 높이 값은 1초에 걸쳐 트랜지션 */	
  }
</style>


<div class="tr1"></div>
```

![image2](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/13%20CSS3%EC%99%80%20%EC%95%A0%EB%8B%88%EB%A9%94%EC%9D%B4%EC%85%98/images/2.png)

- 처음 2개 속성(background-color, transform)에 2s와 3s가 적용되고 다시 2개 속성(width, height)에 2s, 3s가 적용됩니다. 
- 만약 다른 속성이 있다면 다시 2s,. 

```html
<style>
  tr1 {
		width: 100px;
		height: 100px;
		background-color: red;
		border: 1px solid black;
		transition-property: background-color, transform, width, height;
		transition-duration: 2s, 3s;
  }
  .tr1:hover {
		width: 200px;
		height: 200px;
		background-color: #ff6e5f;
		transform: rotate(180deg);
  }
</style>

...

<div class="tr1"><h1>!</h1> </div>
```

## transition-timing-function 속성 - 트랜지션 속도 곡선 지정하기 

- 시작과 중간, 끝에서의 속도를 지정해 속도 곡선을 만들 수 있습니다. 
- 속도 곡선은 미리 정해진 키워드나 <code>베지에 곡선</code>을 이용해 표현합니다.

```css
transition-timing-function: linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier(n, n, n, n)
```
> 베지에 곡선은 n개의 점을 이용해 (n-1)차 곡선을 만들어 내는 함수입니다.

|속성 값|설명|
|---|----|
|linear|시작부터 끝까지 똑같은 속도로 트랜지션을 진행합니다.|
|ease|처음에는 천천히 시작하고 점점 빨라지다가 마지막에는 천천히 끝납니다. 기본값|
|ease-in|시작을 느리게 합니다.|
|ease-out|느리게 끝냅니다.|
|ease-in-out|느리게 시작하고 느리게 끝납니다.|
|cubic-bezier(n,n,n,n)|베지에 함수를 직접 정의해 사용합니다. n에서 사용할 수 있는 값은 0~1입니다.|


```css
transition-timing-function: linear;
```

## transition-delay 속성 - 지연 시간 설정하기

- 트랜지션이 언제부터 시작할 것인지 설정합니다.
- 지정하는 시간만큼 기다렸다가 트랜지션이 시작됩니다. 
- 사용할 수 있는 값은 초(seconds)나 밀리초(milliseconds)이며 기본값은 0s입니다.

```css 
#no-delay {
  transition-duration: 3s;  /* 즉시 실행되는 트랜지션(no-delay 상자) */
}

#delay {
  transition-duration: 3s; 
  transition-delay: 1s;  /* 1초 늦게 실행되는 두 번째 트랜지션(delay 상자) */
}
```

## transition 속성 - 트랜지션 속성 한꺼번에 표기하기 

```
transition: <transition-property 값> | <transition-duration 값> | <transition-timing-function 값> | <transition-delay 값>
```

```html
<style>
	.tr1 {
		width: 200px;
		height: 200px;
		background-color: red;
		border: 1px solid black;
		transition: 2s ease-in;
	}
	.tr1:hover {
		width: 100px;
		height: 100px;
		background-color: #ff6e5f;
		transform: rotate(270deg);			
	}
</style>

...

<div class="tr1"></div>
```

## 두 개 이상의 변형 동시에 사용하기

> 트랜지션이나 애니메이션을 만들다 보면 이동하면서 확대하거나 회전하면서 축소하는 등 두 개 이상의 변형을 동시에 사용하는 경우가 있습니다. 이럴 때는 transform 속성에 여러 개의 속성을 나열하면 됩니다. 예를 들어 크기를 2배로 확대하면서 x축을 기준으로 180º 회전시키려면 2차원 변형 함수 scale()과 3차원 변형 함수 rotateX()를 사용해야 합니다. 

```css
transform: scale(2);
perspective: 120px;
transform: rotateX(100deg);
```

- 이 변형 함수들을 동시에 적용하려면 transform 속성을 이용해 다음과 같이 작성하면 됩니다.

```css
transform: scale(2) perspective(120px) rotateX(180deg);
```

```html
<style>
  div {
          width:100px;
          height:100px;
          margin:100px;
          background:#0094ff;
  }
  .box {
      transition: 2s ease-in;
  }
  .box:hover {
      transform: scale(2) perspective(120px) rotateX(180deg);			
  }
</style>

... 

<div class="box"></div>
```
