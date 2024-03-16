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




---
# 텍스트 스타일 

---
# 문단 스타일 

--- 
# 목록 스타일