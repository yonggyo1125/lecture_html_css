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



---

# 가상 클래스와 가상 요소