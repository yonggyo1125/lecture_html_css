# 폼 만들기 


## \<form\> 태그 - 폼 만들기 

- \<form\> 태그는 폼을 만드는 가장 기본적인 태그로 \<form\> 태그와 \</form\> 태그 사이에 여러 폼 요소와 관련된 태그를 넣습니다. 

```html
<form [속성="속성 값"]> 여러 폼 요소 </form>
```

### form 태그의 속성
- \<form\>태그는 몇 가지 속성을 통해 사용자가 입력한 자료들을 서버로 어떤 방식으로 넘길 것인지, 서버에서 어떤 프로그램을 이용해 처리할 것인지 지정합니다. 

|속성| 설명                                                                                                                                                                                                                                          |
|---|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|method| 사용자가 입력한 내용들을 서버 쪽 프로그램으로 어떻게 넘겨줄지 지정합니다.<br>get : 주소 표시줄에 사용자가 입력한 내용이 그대로 드러납니다. 256byte~4096byte까지의 데이터만 서버로 넘길 수 있습니다.<br>post - 대부분 이 방식을 사용합니다. 사용자의 입력을 표준 입력(standard input)으로 넘겨주기 때문에 입력 내용의 길이에 제한을 받지 않고 사용자가 입력한 내용이 드러나지 않습니다.|
|name|폼의 이름을 지정합니다. 한 문서 안에 여러 개의 \<form\> 태그가 있을 경우, 폼들을 구분하기 위해 사용합니다.|
|action|\<form\> 태그 안의 내용들을 처리해 줄 서버 상의 프로그램을 지정합니다.|
|target|action 속성에서 지정한 스크립트 파일을 현재 창이 아닌 다른 위치에 열도록 지정합니다.|


```html
<form action="register.php">
    ...
</form>
```

```html
<!DOCTYPE html>

<html lang="ko">
<head>
    <meta charset="utf-8">
    <title>HTML5 폼</title>
</head>
<body>
	<form action="search.php" method="post">
		<input type="text" title="검색">
		<input type="submit" value="검색">
	</form>
</body>
</html>
```

### autocomplete 속성 - 자동 완성 

- 기본값은 on, 자동완성이 기본으로 켜져 있기 때문에 입력한 적 있는 값은 한두 글자 입력하면 입력 내용이 자동으로 완성 
- 유출되면 곤란한 비밀번호나 일회용 인증번호를 입력할 때는 자동 완성 기능을 끄는 것이 좋습니다. autocomplete 속성을 off로 지정

```html
<form action="register.php" autocomplete="off">
    ...
</form>
```

## \<label\> 태그 - 폼 요소에 레이블 붙이기 

- \<label\> 태그를 사용하면 폼 요소와 레이블 텍스트가 서로 연결되어 있다는 것을 브라우저가 알 수 있습니다.

```html
<label [속성="속성 값"]> 레이블 <input ...> </label>

예) 
<label>아이디(6자 이상) <input type="text" ...></label>
```

또는 

```html
<label for="id이름">레이블</label>
<input id="id이름" [속성="속성값"]>

예)
<label for="user-id">아이디(6자 이상)</label>
<input type="text" id="user-id">
```

### 라디오 버튼과 체크박스에서 사용하는 \<label\> 태그

- \<label\> 태그를 이용해 라디오 버튼이나 체크박스에 텍스트(label)를 연결해 놓았다면 텍스트만 터치해도 라디오 버튼이나 체크박스가 선택되어 사용이 쉬워집니다. 

```html
    <form>
		<h3>수강 분야(다수 선택 가능)</h3>
		<ul>
			<li><input type="checkbox" value="grm">문법	</li>
			<li><input type="checkbox" value="wr">작문</li>
			<li><input type="checkbox" value="rd">독해</li>
		</ul>
		<h3>수강 과목(1과목만 선택 가능)</h3>
		<ul>
			<li>
				<label><input type="radio" name="subject" value="eng">영어회화</label>
			</li>
			<li>
				<label><input type="radio" name="subject" value="ch">중국어회화</label>
			</li>
			<li>				
				<label><input type="radio" name="subject" value="jp">일어회화</label>
			</li>
		</ul>
	</form>
```

## \<fieldset\>, \<legend\> 태그 - 폼 요소 그룹으로 묶기 

- 하나의 폼 안에서 여러 구역을 나누어 표시하려고 할 때 \<fieldset\>, \<legend\> 태그를 사용합니다.
- \<fieldset\> 태그는 \<fieldset\>과 \</fieldset\> 태그 사이의 폼들을 하나의 영역으로 묶고 외곽선을 그려줍니다.
- \<legend\> 태그는 \<fieldset\> 태그로 묶은 그룹에 제목을 붙여 줍니다. 


```html
<form>
		<fieldset>
			<legend>개인 정보</legend>
			<ul>
				<li>
					<label for="name">이름</label>
					<input type="text" id="name">
				</li>
				<li>
					<label for="mail">메일 주소</label>
					<input type="text" id="mail">
				</li>
			</ul>
		</fieldset>		
		<fieldset>
			<legend>로그인 정보</legend>
			<ul>
				<li>
					<label for="id">아이디</label>
					<input type="text" id="id">
				</li>
				<li>
					<label for="pwd">비밀번호</label>
					<input type="text" id="pwd">
				</li>
			</ul>
		</fieldset>
	</form>
```

--- 

# 사용자 입력을 위한 \<input\> 태그

- 사용자가 입력할 부분은 주로 \<input\> 태그를 이용해 넣습니다.
- 입력받는 다양한 형태는 type 속성에 의해 결정됩니다.

## \<input\> 태그 - 입력 항목 만들기 

```html
<input type="유형" [속성="속성 값"]>
```

- \<input\> 태그로 만들 수 있는 폼 요소가 상당히 많은데 \<input\> 태그 안에 있는 type 속성을 이용해 구분합니다. 
- \<input type="text"\>로 지정하면 한 줄짜리 텍스트를 입력하는 필드가 만들어 집니다.
- \<input type="checkbox"\>라고 하면 체크박스가 만들어 집니다.

### id 속성 사용하기 
- 여러 번 사용된 폼 요소를 구분하기 위해 사용하는 것이 id속성 입니다.
- id를 지정해 놓으면 \<label\> 태그를 이용해 캡션을 붙일 수도 있고 CSS를 이용해 각 요소마다 다른 형태로 꾸밀 수도 있습니다. 
- id 속성 값은 최소한 한 개 이상의 문자여야 하고 공백이 있어서는 안됩니다. 

```html
<input type="text" id="user-name" size="10">
<input type="text" id="addr" size="60">
```

### \<input\> 태그와 type 속성에서 사용 가능한 유형

|유형| 설명                                                  |
|---|-----------------------------------------------------|
|hidden| 사용자에게는 보이지 않지만 서버로 넘겨지는 값을 가집니다.                    |
|text| 한 줄짜리 텍스트를 입력할 수 있는 텍스트 상자를 넣습니다.                   |
|search| 검색 상자를 넣습니다.                                        |
|tel| 전화번호를 입력 필드에 넣습니다.                                  |
|url| URL 주소를 입력할 수 있는 필드를 넣습니다.                          |
|email| 메일 주소를 입력할 수 있는 필드를 넣습니다.                           |
|password| 비밀번호를 입력할 수 있는 필드를 넣습니다.                            |
|datetime| 국제 표준시(UTC)로 설정된 날짜와 시간(연, 월, 일, 시, 분, 초, 분할 초)를 넣습니다. |
|datetime-local| 사용자가 있는 지역을 기준으로 날짜와 시간(연, 월, 일, 시, 분, 초, 분할 초)를 넣습니다. |
|date|사용자 지역을 기준으로 날짜(연, 월, 일)를 넣습니다.                      |
|month|사용자 지역을 기준으로 날짜(연, 월)를 넣습니다.                         |
|week|사용자 지역을 기준으로 날짜(연, 주)를 넣습니다.                         |
|time|사용자 지역을 기준으로 시간(시, 분, 초, 분할 초)을 넣습니다.|
|number|숫자를 조절할 수 있는 화살표를 넣습니다.|
|range|숫자를 조절할 수 있는 슬라이드 막대를 넣습니다.|
|color|색상 표를 넣습니다.|
|checkbox|주어진 항목에서 2개 이상 선택 가능한 체크박스를 넣습니다.|
|radio|주어진 항목에서 1개만 선택할 수 있는 라디오 버튼을 넣습니다.|
|file|파일을 첨부할 수 있는 버튼을 넣습니다.|
|submit|서버 전송 버튼을 넣습니다.|
|image|submit 버튼 대신 사용할 이미지를 넣습니다.|
|reset|리셋 버튼을 넣습니다.|
|button|버튼을 넣습니다.|



---

# \<input\> 태그의 다양한 속성

---

# 여러 데이터 나열해 보여 주기

---

# 기타 다양한 폼 요소들