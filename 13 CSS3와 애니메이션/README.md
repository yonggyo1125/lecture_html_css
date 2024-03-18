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

---
# 트랜지션 

---
# 애니메이션 