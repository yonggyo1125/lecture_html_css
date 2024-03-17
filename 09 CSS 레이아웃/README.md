# CSS 포지셔닝과 주요 속성들

## CSS 포지셔닝이란? 
- 브라우저 화면 안에 각 콘텐츠 영역을 어떻게 배치할지를 결정하는 것

## box-sizing 속성 - 박스 너비 기준 정하기

- CSS의 width 속성은 콘텐츠 영역의 너비를 나타내기 때문에 해당 요소에 적용한 패딩이나 테두리 크기는 따로 계산해서 배치해야 합니다. 
- 이럴 때 box-sizing 속성을 사용하면 콘텐츠 영역의 너비에 패딩과 테두리 크기까지 합쳐서 width 속성을 지정할 수 있습니다.

```css
box-sizing: content-box | border-box;
```

![image1](https://raw.githubusercontent.com/yonggyo1125/lecture_html_css/master/09%20CSS%20%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83/images/1.png)

|속성 값|설명|
|---|----|
|content-box|width 속성 값을 콘텐츠 영역 너비 값으로 사용합니다. 기본 값입니다.|
|border-box|width 속성 값을 콘텐츠 영역에 테두리까지 포함한 박스 모델 전체 너비 값으로 사용합니다.|


```html
    <style>
		div {
			float:left;
			margin-right:20px;
		}
		.box1 {
			box-sizing:content-box; /* 콘텐츠 영역 기준 */
			width: 300px; /* 콘텐츠 영역 너비 300px */
			height: 150px; /* 높이 */
			margin: 10px; /* 마진 */
			padding: 30px; /* 패딩 */
			border:2px solid red; /* 테두리 */
		}
		.box2 {
			box-sizing:border-box;  /* 테두리까지(박스 전체) 기준*/
			width: 300px; /* 박스 모델 전체 너비 */
			height: 150px; /* 박스 높이 */
			margin: 10px; /* 마진 */
			padding: 30px; /* 패딩 */
			border: 2px solid red; /* 테두리 */
		}
	</style>

    <div class="box1"> box-sizing = "content-box" </div>
    <div class="box2"> box-sizing = "border-box"</div>
```

> CSS를 이용해 여러 박스 모델을 화면상에 배치하려면 박스 모델의 너비 값을 정확히 계산해야 합니다. 만약 width 값을 계산하기 어렵다면 box-sizing: border-box로 지정해 박스 모델 너비를 알기 쉽게 바꾸어 놓는 것도 좋은 방법입니다.

--- 

# 다단으로 편집하기

---

# 표 스타일