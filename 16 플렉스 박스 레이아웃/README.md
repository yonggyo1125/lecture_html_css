# 플렉스 박스 레이아웃 기본 속성들 

## 플렉스 박스 레이아웃이란?
- 그리드 레이아웃을 기본으로 해 플렉스 박스를 원하는 위치에 배치하는 것입니다. 
- 이 플렉스 박스를 이용하면 여유 공간에 따라 너비나 높이, 위치를 자유롭게 변형할 수 있습니다.
- 화면 크기에 따라 레이아웃의 배치나 크기를 조절해야 할 떄 편리하게 사용할 수 있습니다.

## display 속성 - 플렉스 컨테이너 지정하기
- 플렉스 박스 레이아웃을 만들려면 먼저 웹 콘텐츠를 플렉스 컨테이너로 묶어 주어야 합니다. 
- 즉, 배치하려는 웹 요소들이 있다면 그 요소들을 감싸는 부모 요소를 만들고 그 부모 요소를 플렉스 컨테이너로 만들어야 합니다. 
- 이때 특정 요소가 플렉스 컨테이너로 동작하려면 display 속성을 이용해 플렉스 박스 형태로 지정해야 합니다.

```css
display: flex | inline-flex
```

|속성 값|설명|
|---|----|
|flex|플렉스 박스를 박스 레벨 요소로 정의합니다.|
|inline-flex|플렉스 박스를 인라인 레벨 요소로 정의합니다.|


```html
<style>
    #container {
        display: flex;
    }
</style>
<div id="container">
    <div></div>
    <div></div>
</div>
```

## flex-direction 속성 - 플렉스 방향 지정하기
- 플렉스 컨테이너를 지정했다면 플렉스 항목을 배치할 방향을 알려 주어야 합니다.
- flex-direction 속성을 사용해 플렉스 항목의 주측을 가로(row)로 할지, 세로(column)로 할지 지정합니다. 
- 따로 지정하지 않으면 기본값인 row로 인식합니다.

```css
flex-direction: row | row-reverse | column | column-reverse
```

|속성 값|설명|
|---|----|
|row|주축을 가로로 교차축을 세로로 지정합니다. 플렉스 항목은 주축 시작점에서 끝점으로(왼쪽에서 오른쪽으로) 배치됩니다.|
|row-reverse|주축을 가로로 교차측을 세로로 지정합니다. 플렉스 항목은 주측 끝점에서 시작점으로(오른쪽에서 왼쪽으로) 배치됩니다.|
|column|주축을 세로로 교차축을 가로로 지정합니다. 플렉스 항목은 주축 시작점에서 끝점으로(위쪽에서 아래쪽으로) 배치됩니다.|
|column-reverse|주측을 세로로 교차축을 가로로 지정합니다. 플렉스 항목은 주축 끝점에서 시작점으로(아래쪽에서 위쪽으로) 배치됩니다.|


- 플렉스 항목 가고로 배치하기
```html
<style>
    #container {
        width:500px;
        height:300px;
        margin:0 auto;
        display:flex;
        border:2px solid black;
    }	
    #container div {
        width:200px;
        border: 2px solid black;
        background:#ccc;
    }
</style>

...

<div id="container">
    <div id="box1"><h2>1</h2></div>
    <div id="box2"><h2>2</h2></div>
    <div id="box3"><h2>3</h2></div>
</div>
```
- 플렉스 항목 세로로 배치하기 

```html
<style>
    #container {
        ...
        display: flex;
        flex-direction: column;
    }
</style>
```

## flex-wrap 속성 - 플렉스 항목을 한 줄 또는 여러 줄로 배치하기 

```css
flex-wrap: no-wrap | wrap |wrap-reverse
```

|속성 값|설명|
|---|-----|
|no-wrap|플렉스 항목들을 한 줄에 표시합니다. 기본값|
|wrap|플렉스 항목을 여러 줄에 표시합니다.|
|wrap-reverse|플렉스 항목을 여러 줄에 표시하되 기존 방향과 반대로 배치합니다.|

- 플렉스 항목 왼쪽에서 오른똑으로 배치하기 / 여러 줄로 표시된 플렉스 항목

```html
<style>
    #container {
        display: flex;
        flex-wrap: wrap;
    }
</style>
```

- flex-wrap 값을 wrap으로 지정하면 가로로 왼쪽에서 오른쪽으로 배치하고 세로로 위에서 아래로 배치합니다.
- wrap-reverse로 지정하면 주축은 시작점에서 끝점으로(왼쪽 -> 오른쪽) 배치하고 교차축은 끝점에서 시작점으로(아래 -> 위) 배치합니다/
- 플렉스 항목 오른쪽에서 왼쪽으로 배치하기 / 교차축의 끝점에서 시작점으로 배치

```html
<style>
    #container {
        display: flex;
        flex-wrap: wrap-reverse;
    }
</style>
```

## flex-flow 속성 - 플렉스 방향과 여러 줄의 배치를 한꺼번에 지정하기

```css 
flex-flow: <플렉스 방향> <플렉스 줄 배치>
```

```css
flex-flow: row; /* 왼쪽에서 오른쪽으로, 한 줄에 표시 */
flex-flow: column wrap; /* 위에서 아래로, 여러 줄에 표시 */
```

## order 속성 - 플렉스 항목의 배치 순서 바꾸기 
- order 속성을 이용하면 배치 순서를 바꿀 수 있습니다.
- order 값이 0이라면 소스에 입력한 순서대로 배치되고 order 값을 숫자로 하면 그 순서에 따라 배치됩니다. 

```css
order: 0  | 숫자
```
> order 값에 음수를 지정하면 0으로 취급합니다.

- 플렉스 항목 배치 순서 바꾸기

```html
<style>
    #container {
        display: flex;
    }
    #box1 { order: 2; }
    #box2 { order: 3; }
    #box3 { order: 1; }
</style>

<div id="container">
    <div id="box1"><h2>box1</h2></div>
    <div id="box2"><h2>box2</h2></div>
    <div id="box3"><h2>box3</h2></div>
</div>
```

---

# 플렉스 박스 항목 배치를 위한 속성들

## justify-content 속성 - 주측의 기준의 배치 방법 지정하기

```css
justify-content: flex-start | flex-end | center | space-between | space-around 
```

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/16%20%ED%94%8C%EB%A0%89%EC%8A%A4%20%EB%B0%95%EC%8A%A4%20%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83/images/1.png)

## align-items 속성, align-self 속성 - 교차측 기준의 배치 방법 지정하기

```css
align-items: stretch | flex-start | flex-end | center | baseline
```

![image2](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/16%20%ED%94%8C%EB%A0%89%EC%8A%A4%20%EB%B0%95%EC%8A%A4%20%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83/images/2.png)

- <code>align-self</code> 속성을 이용하면 플렉스 항목을 개별적으로 배치할 수 있습니다.
- 플렉스 컨테이너에서 플렉스 항목 전체의 배치 방법을 결정하지만 <code>align-self</code> 속성으로 특정 플렉스 항목만 배치 방법을 바꿀 수 있습니다. 

```css
align-self : auto | stretch | flex-start | flex-end | center | baseline
```

- align-self의 속성 값은 플렉스 항목의 부모 속성 값을 상속받는 auto를 제외하면 align-items에서의 속성 값과 같습니다.
- 교차축의 배치 방법 지정하기

```html
<style>
    #container {
        display: flex;
        align-items: center;
    }
    
    #box1 { 
       align-self: flex-start; /* 첫 번째 박스만 교차축의 시작점에 배치 */     
    }
</style>
```

## align-content 속성 - 여러 줄일 때의 배치 방법 지정하기 

- 플렉스 항목이 여러 줄에 걸쳐 표시될 때 align-content 속성을 사용하면 교차축 방향의 배치 방법을 지정할 수 있습니다.
- align-content 속성에서 사용하는 값은 justify-content의 속성 값과 같습니다.

```css
align-content: flex-start | flex-end | center | space-between | space-around
```

![image3](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/16%20%ED%94%8C%EB%A0%89%EC%8A%A4%20%EB%B0%95%EC%8A%A4%20%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83/images/3.png)
