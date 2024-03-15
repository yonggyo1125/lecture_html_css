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

## type="hidden" - 히든 필드 만들기
- 화면상의 폼에는 보이지 않지만 사용자가 입력을 마치고 폼을 서버로 전송할 때 서버로 함께 전송되는 요소입니다.
- 사용자에게 굳이 보여 줄 필요가 없지만 관리자가 알아야 하는 것을 히든 필드로 입력합니다.

```html
<input type="hidden" name="이름" value="서버로 넘길 값">
```

## type="text" - 텍스트 필드 만들기 

- 한 줄짜리 일반 텍스트를 입력하는 필드입니다.
- 텍스트 필드에서 사용할 수 있는 속성은 다음과 같습니다.

|속성|설명|
|---|----|
|name|텍스트 필드를 구별할 수 있도록 이름을 붙입니다.|
|size|텍스트 필드의 길이를 지정합니다. 즉 화면에 몇 글자가 보이도록 할 것인지를 지정합니다. 예를 들어 최대 입력 가능 글자 수가 10개인데 size를 5로 지정하면 텍스트 필드 크기가 5개 글자 크기에 맞추어져 나머지 5개 글자는 화면에 보이지 않습니다.|
|value|텍스트 필드 요소가 화면에 표시될 때 텍스트 필드 부분에 표시될 내용입니다. 이 속성을 사용하지 않으면 빈 텍스트 필드가 표시됩니다.|
|maxlength|텍스트 필드에 입력할 수 있는 최대 문자 개수를 지정합니다.|

## type="password" - 비밀번호 입력란 만들기 

- 사용자가 입력하는 내용이 화면에 표시되지 않고 '*'나 '•'로 표시됩니다. 
- 속성도 value 속성이 없다는 점만 제외하면 텍스트 필드와 같습니다. 

```html
<input type="password" [속성="속성 값"]>
```

```html
    <form>
        <fieldset>
            <label>아이디: <input type="text" id="user_id" size="10"></label>
          <label>비밀번호: <input type="password" id="user_pw" size="10"></label>
          <input type="submit" value="로그인">
        </fieldset>
    </form>
```

## type="search", type="url", type="email", type="tel" - 분화된 텍스트 필드 

- type="search" : 검색 상자 만들기 
- type="url" : URL 입력란 만들기 
- type="email" : 메일 주소 입력란 만들기 
- type="tel" : 전화번호 입력란 만들기 


```html
        <h1>회원 가입</h1>
		<form>
			<fieldset>
				<legend>로그인 정보</legend>
				<ul>
					<li>
    				<label for="user-id">아이디 </label>
						 <input type="text" id="user-id">
					</li>
					<li>
						<label for="pwd1">비밀번호 </label>
						<input type="password" id="pwd1">
					</li>
					<li>
						<label for="pwd2">비밀번호 확인 </label>
						<input type="password" id="pwd2">				
					</li>
				</ul>
			</fieldset>
			<fieldset>
				<legend>개인 정보</legend>
				<ul>
					<li>
						<label for="user-name">이름 </label>
						<input type="text" id="user-name">
					</li>
					<li>
						<label for="mail">메일 주소</label>
						<input type="email" id="mail">
					</li>
					<li>
						<label for="phone">연락처</label>
						<input type="tel" id="phone">
					</li>
					<li>
						<label for="homep">블로그/홈페이지</label>
						<input type="url" id="homep">
					</li>
				</ul>
			</fieldset>
			<input type="submit" value="가입하기">
		</form>
```

## type="number" - 숫자 입력하기 
- 사용자가 입력한 내용을 숫자로 인식합니다. 
- 브라우저에 따라 스핀 박스가 표시되기도 합니다. 
- 스핀 박스란 입력창 오른쪽에 작은 화살표를 표시해 화살표를 클릭하면 숫자를 증감시킬 수 있게 한 것 

```html
<input type="number" [속성="속상 값"]>
```

```html
<b>주문 개수 : </b> <input type="number" min="1" max="5" value="1"> 개 
```

## type="range" - 슬라이드 막대로 숫자 지정하기

```html
<input type="range" [속성="속성 값"]>
```

- type="number" 필드와 type="range" 필드에서 사용할 수 있는 속성

|속성|설명|
|---|----|
|min|필드에 입력할 수 있는 최솟값을 지정합니다. type="range"일 때 기본 최소값은 0입니다.|
|max|필드에 입력할 수 있는 최댓값을 지정합니다. type="ranage"일 때 기본 최대값은 100입니다.|
|step|짝수나 홀수 등 특정 숫자로 제한하려고 할 때 숫자 간격을 지정할 수 있습니다. 기본 값은 1이며 생략할 수 있습니다.|
|value|필드에 표시할 초기값입니다.|

```html
    <form>
	  <fieldset>
	    <legend> 등록 정보</legend>
    	  <ul>
	        <li>
            	  <label class="reg" for="member">참여인원<small>(최대10명)</small></label>
                <input type="number" id="member" value="1" min="0" max="10" step="1">
              </li>
              <li>
            	  <label class="reg" for="stuffs">지원물품<small>(1인당 5개)</small></label>
                <input type="number" id="stuffs" value="1" min="0" max="50" step="5">
              </li>
        	  <li>
            	  <label class="reg" for="satis">희망 단계<small>(하,중,상)</small></label>
                <input type="range" id="satis" value="1" min="1" max="3">
              </li>           
            </ul>
       </fieldset>
    </form>
```

## type="radio", type="checkbox" - 라디오 버튼과 체크박스 넣기

- 여러 항목 중 원하는 항목을 선택할 때 사용하는 폼 요소 
- 라디오버튼 : 한 개만 선택하도록 할 경우 
- 체크박스 : 두개 이상 여러 가지를 선택해도 될 경우

```html
<input type="radio" [속성="속성 값"]>

<input type="checkbox" [속성="속성 값"]>
```

|속성|설명|
|---|-----|
|name|라디오 버튼이나 체크박스가 여러 개 있을 경우, 서버의 폼 프로그램에서 라디오 버튼이나 체크박스를 구분하기 위해 이름을 지정합니다. 라디오 버튼은 여러 개 중에서 하나만 선택하는 것이기 때문에 관련 있는 그룹끼리는 name 속성 값을 똑같이 만듭니다.|
|value|선택한 라디오 버튼이나 체크박스를 서버로 알려 줄 때 넘길 값을 지정합니다. 이 값은 영문이거나 숫자여야 하며 필수 속성입니다.|
|checked|라디오 버튼의 항목들은 처음에 아무것도 선택되지 않은 상태로 화면에 표시되는데 기본으로 선택해 놓은 항목이 있다면 checked 속성을 사용합니다.|

```html
    <form>
		<fieldset>
			<legend>신청 과목</legend>
			<p>이 달에 신청할 과목을 선택하세요 (1과목만 가능)</p>
			<label><input type="radio" name="subject" value="speaking">회화</label>
			<label><input type="radio" name="subject" value="grammar">문법</label>
			<label><input type="radio" name="subject" value="writing">작문</label>       
		</fieldset>
		<fieldset>
			<legend>메일링</legend>
			<p>메일로 받고 싶은 뉴스 주제를 선택해 주세요 (복수 선택 가능)</p>
			<label><input type="checkbox" name="mailing1" value="news">해외 단신</label>
			<label><input type="checkbox" name="mailing2" value="dialog">5분 회화</label>
			<label><input type="checkbox" name="mailing3" value="pops">모닝팝스</label>
		</fieldset>
  </form>
```

## type="color" - 색상 선택 상자 표시하기 

- 색상표에서 사용자가 색상을 선택할 수 있게 해줍니다. 

```html
<input type="color" [value="기본 색" [속성="속성 값"]>
```

```html
    <form>
		<fieldset>
			<legend>과 티셔츠 설문</legend>
			<p>올해 과 티(T)를 만들려고 합니다. 원하는 색상을 추천해 주세요.</p>
			<label>선호색상  <input type="color" value="#00ff00"> </label>
		</fieldset>

    </form>
```

## type="date", type="month", type="week" - 날짜 표시하기 
- 달력을 포함시키고 싶을 때 

```html
<input type="date | month | week" [value="기본 값" 속성="속성 값"]>
```
> '|'는 '또는(or)'의 의미로 날짜와 관련해 사용할 수 있는 유형


|유형| 설명                      |
|---|-------------------------|
|date|날짜를 선택합니다.               |
|month|월(month)과 연도(year)를 선택합니다.|
|week|주(week)와 연도(year)를 선택합니다.|


```html
    <form>
		<h3>조회기간 선택</h3>
		<label><input type="date" id="start"></label>
		<label><input type="date" id="end"></label>
	</form>
```

## type="time", type="datetime", type="datetime-local" - 시간 지정하기

- 시간을 지정할 때는 type="time"을 사용
- 날짜와 시간을 함께 지정하려면 type="datetime"이나 type="datetime-local"을 사용

```html
<input type="time | datetime | datetime-local" [value="기본 값" 속성="속성 값"]>
```

|속성| 설명                                                                                                                                                                                |
|---|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|min| 날짜나 시간의 최솟값을 지정합니다.                                                                                                                                                               |
|max| 날짜나 시간의 최댓값을 지정합니다.                                                                                                                                                               |
|step| 스핀 박스의 화살표를 누를 때마다 날짜나 시간을 얼마나 조절할지를 지정합니다.                                                                                                                                       |
|value| 회면에 표시할 초기값을 지정합니다. type="time"일 경우 시간은 00:00부터 23:59까지 입력하고 type="datetime"이나 type="datetime-local" 유형일 경우, 날짜 다음에 키워드 T를 쓰고 24시간제로 시간을 지정합니다. 예를들어 오후 6시를 나타내려면 T18:00라고 하면 됩니다.|

```html
    <form>		
		<h3>대관시간을 선택하세요(오늘)</h3>
		<label>시작 시간<input type="time" value="09:00" id="start1"></label>,
		<label>종료 시간<input type="time" value="18:00" id="end1"></label>

		<h3>대관시간을 선택하세요(다른날짜)</h3>
		<label>시작 시간<input type="datetime-local" value="2016-03-02T09:00" id="start2"></label>,
		<label>종료 시간<input type="datetime-local" value="2016-03-02T18:00" id="end2"></label>
	</form>
```

## type="submit", type="reset" - 서버 전송, 리셋 버튼 넣기

- 리셋(reset) 버튼 : \<input\> 요소에 입력된 모든 정보를 재설정해 사용자가 입력한 내용을 모두 지울 수 있습니다. value 속성을 사용해 버튼에 표시할 내용을 지정
- 제출(submit) 버튼 : 사용자가 폼에 입력한 정보를 서버로 전송합니다.

```html
<input type="submit | reset" [value="버튼 내용"] [속성="속성 값"]>
```

```html
    <h3>메일링 리스트 등록</h3>
	<form action="register.php" method="post">
		<label> 메일 주소 <input type="text"></label>
		<input type="submit" value="제출">
		<input type="reset" value="다시입력">
	</form>
```

## type="image" - 이미지 버튼 넣기 
- submit 버튼 대신 전송 이미지를 넣을 수 있습니다. 
- submit 버튼을 클릭할 때 처럼 사용자가 입력한 정보가 폼 처리 프로그램으로 전달됩니다.

```html
<input type="image" src="경로" alt="대체 텍스트" [속성="속성 값"]>
```

```html
    <form>
		<table>
			<tr>
				<td><label>아이디 <input type="text" size="15"></label></td>
				<td><label>비밀번호 <input type="password" size="15"></label></td>
				<td><input type="image" id="butt" src="images/login.jpg"  alt="login"></td>
			</tr>
		</table>	
	</form>
```

## type="button" - 버튼 넣기 

- 폼 안에 버튼 형태를 만듭니다. 
- 이 버튼은 submit이나 reset같은 자체 기능이 없고 오직 버튼만 넣습니다. 
- value 속성을 사용해 버튼에 표시할 내용을 지정합니다.

```html
<input type="button" [value="버튼 내용"] [속성="속성 값"]>
```

## type="file" - 파일 첨부하기 

- type="file" 필드를 넣으면 웹브라우저 화면에 [파일 선택]이나 [찾아보기] 등이 표시됩니다.
- 이 버튼을 클릭한 후 파일을 선택하면 파일이 첨부됩니다.

```html
<input type="file" [속성="속성 값"]>


<label>첨부파일 <input type="file"></label>
```


---

# \<input\> 태그의 다양한 속성

## autofocus 속성 - 입력 커서 표시하기 
- autofocus 속성을 사용하면 페이지를 불러오자마자 폼의 요소 중에서 원하는 요소에 마우스 커서를 표시할 수 있습니디. 
- 이전에는 이 기능을 구현하기 위해 자바스크립트를 이용해야 했는데 HTML5에서는 autofocus라는 속성으로 쉽게 해결할 수 있습니다.

```html
<label class="reg" for="uname">이름</label>
<input type="text" id="uname" autofocus required>
```

## placeholder 속성 - 힌트 표시하기 
- 사용자가 텍스트를 입력할 때 도움이 되도록 입력란에는 적당한 힌트 내용을 표시하고 있다가 그 필드를 클릭하면 내용이 사라지도록 만들 수 있습니다. 
- 텍스트 필드 앞에 제목을 사용하지 않고도 해당 필드에 어떤 내용을 입력해야 할지 알려 줄 수 있어 편리합니다.

```html
<label class="reg" for="uid">학번</label>
<input type="text" id="uid" placeholder="하이픈없이 입력" maxlength="8" required>
```

## readonly 속성 - 읽기 전용 필드 만들기 
- readonly 속성은 true나 false 값 중 하나만 사용하기 때문에 속성과 함께 true나 false값을 지정해도 되고 간단히 readonly라고만 쓰거나 readonly="readonly"라고 써도 readonly="true"로 인식합니다. 

```html
<label class="reg" for="subj">영어회화(초급)</label>
<input type="text" id="subj" value="오전 9:00~11:00" readonly>
```

## required 속성 - 필수 필드 지정하기 

```html
<label class="reg" for="uname">이름</label>
<input type="text" id="uname" autofocus required>
```

## min, max, step 속성

- min : 최솟값 
- max : 최댓값
- step : 증감단위

```html
<label class="reg" for="group">단체주문</label>
<input type="number" id="group" value="10" min="10" max="100" step="10">
```

## size, minlength, maxlength 속성 - 길이, 최소 길이, 최대 길이 속성 

```html
<label>아이디: <input type="text" id="user_id" size="10" minlength="4" maxlength="15"></label><small style="color:red;"> 4~15자리 이내의 영문과 숫자</small>
```

- 이외에도 \<input\> 태그에서 사용할 수 있는 속성들은 다음과 같습니다.

|속성|설명|
|---|----|
|formaction|실행할 프로그램을 연결합니다. type="submit"이나 type="image"일 때 사용할 수 있습니다.|
|formenctype|서버로 폼을 전송했을 때 폼 데이터를 어떤 방식으로 해석할 것인지 지정합니다. type="submit"이나 type="image"일 때 사용할 수 있습니다.|
|formmethod|서버로 폼을 전송하는 방식(get, post 등)을 지정합니다. 이미 \<form\> 태그 안에서 지정한 방식이 있어도 그 방식은 무시됩니다.|
|formnovalidate|\<form\> 태그 안에 novaliate 라는 속성이 있어서 서버로 전송할 때 폼 데이터가 유효(validate)한지 여부를 표시할 수 있는데 \<input\> 태그 안에서도 formnovalidate 속성을 이용해 유효성 여부를 표시할 수 있습니다.|
|formtarget|폼 데이터를 서버로 전송한 후 서버의 응답을 어디에 표시할 것인지 타깃을 지정합니다.|
|height, width|type="image"일 때 이미지의 너비와 이를 지정합니다.|
|list|\<datalist\>에 미리 정의해 놓은 옵션 값을 \<input\> 안에 나열해 보여 줍니다.|
|multiple|type="email"이나 type="file"일 때 두 개 이상의 값을 입력합니다. \<input\> 태그 안에 속성 이름만 표시하면 됩니다.|

---

# 여러 데이터 나열해 보여 주기

## \<selet\>, \<optgroup\>, \<option\> 태그 - 드롭다운 목록 만들기

- 드롭다운 목록은 \<select\> 태그와 \<option\> 태그를 이용해 표시합니다.

```html
<select 속성="속성값">
    <option value="값" [속성="속성 값"]>내용1</option>
    <option value="값" [속성="속성 값"]>내용2</option>
    <option value="값" [속성="속성 값"]>내용2</option>
    ...
</select>
```

### \<select\> 태그의 속성

|속성| 설명                                                                                                             |
|---|----------------------------------------------------------------------------------------------------------------|
|size| 화면에 표시될 드롭다운 메뉴의 항목 개수를 지정한다.<br>크롬 브라우저의 경우 size에서 지정한 개수보다 하나 더 많은 옵션이 표시됩니다. size="3" 으로 지정하면 4개의 옵션이 표시됩니다.|
|multiple|브라우저 화면에 여러 개의 옵션이 함께 표시되면서 [CTRL] 키를 누른 상태로 드롭다운 메뉴에 있는 여러 항목을 선택할 수 있습니다.|

### \<option\> 태그의 속성

- 드롭다운 목록에 표시되는 옵션들은 \<option\> 태그를 이용해서 지정

|속성|설명|
|---|----|
|value|옵션을 선택했을 때 서버로 넘겨질 값을 지정합니다.|
|selected|화면에 표시될 때 기본으로 선택되어 있는 옵션을 지정합니다.|


```html
<label class="reg" for="class">학과</label>
<select size="5" id="class" multiple>
    <option value="archi">건축공학과</option>
	<option value="mechanic">기계공학과</option>
	<option value="indust">산업공학과</option>
	<option value="elec">전기전자공학과</option>
	<option value="computer" selected>컴퓨터공학과</option>
	<option value="chemical">화학공학과</option>
</select>
```

### \<optgroup\> 태그 - 옵션끼리 묶기

- 드롭다운 목록에서 여러 항목들을 몇 가지 그룹으로 묶어야 할 경우 사용
- label 속성을 사용해 그룹의 제목을 붙입니다. 

```html
<label class="reg" for="class">학과</label>
<select id="class">
    <optgroup label="공과대학">
        <option value="archi">건축공학과</option>
        <option value="mechanic">기계공학과</option>
        <option value="indust">산업공학과</option>
        <option value="elec">전기전자공학과</option>
        <option value="computer">컴퓨터공학과</option>
        <option value="chemical">화학공학과</option>
    </optgroup>
    <optgroup label="인문대학">
        <option value="history">사학과</option>
        <option value="lang">어문학부</option>
        <option value="philo">철학</option>
    </optgroup>
</select>
```

## \<datalist\> 태그, \<option\> 태그
- 데이터 목록중에서 값을 선택하도록 만들 수 있습니다. 
- 텍스트 필드에 직접 값을 입력하는 것이 아니라 데이터 목록에 제시한 값 중에서 선택하면 그 값이 자동으로 입력됩니다. 
- 데이터 목록은 텍스트 필드와 함께 사용하기 때문에 \<input\> 태그를 함께 사용합니다. 사용하는 방법은 \<input\> 태그의 list 속성 값과 데이터 목록의 id를 같게 만들면 됩니다. 

```html
<input type="text" list="데이터 목록 id">
<datalist id="데이터 목록 id">
    <option> ... </option>
    <option> ... </option>
    ...
</datalist>
```

|속성|설명|
|---|----|
|value|사용자가 테이블을 선택했을 때 서버로 넘겨질 값을 지정합니다.|
|label|사용자를 위해 브라우저에 표시할 레이블입니다. 따로 지정하지 않을 경우, value 값을 레이블로 사용합니다.|


```html
<input type="text" id="interest" list="choices">
<datalist id="choices">
    <option value="grammar" label="문법"></option>
    <option value="voca" label="어휘"></option>
    <option value="speaking" label="회화"></option>
    <option value="listening" label="리스닝"></option>
    <option value="news" label="뉴스청취"></option>
</datalist>
```

## \<textarea\> 태그 - 여러 줄 입력하는 텍스트 영역 만들기
- 한 줄 이상의 문장을 입력할 때 사용하는 폼을 말합니다. 
- 게시판에서 게시물을 입력하거나 회원가입 양식에서 사용자 약관을 표시할 때 자주 사용합니다. 

|속성|설명|
|---|----|
|name|다른 폼 요소와 구분하기 위해 텍스트 영역의 이름을 지정합니다.|
|cols|텍스트 영역의 가로 너비를 문자 단위로 지정합니다.|
|rows|텍스트 영역의 세로 길이를 줄 단위로 지정합니다. 지정한 숫자보다 줄 개수가 많아지면 스크롤 막대가 생깁니다.|

```html
<textarea name="intro" cols="60" rows="5">
열심히 사는 사람들의 손을 잡아주는 곳 - 이지스 퍼블리싱

우리는 책을 내기 전에 다시 한번 물어봅니다
"이 책이 사람들에게 도움이 되는가?"

더 쉽게, 더 빠르게 지식을 전달하고 싶습니다.
이지스퍼블리싱의 책과 앱을 만나보세요.
</textarea>
```

---


# 기타 다양한 폼 요소들