# 이미지 

## 웹에서 사용하는 이미지 형식 
- 웹 페이지에서 사용할 수 있는 이미지 파일은 크기가 크지 않으면서도 화질이 좋아야 하기 때문에 몇 가지 파일 형식만 사용할 수 있습니다.

|파일 형식|설명|
|---|----|
|GIF(Graphic Interchange Form)|표시할 수 있는 색상 수가 최대 256가지 뿐이지만 다른 이미지 파일 형식에 비해 파일 크기가 작기 때문에 아이콘이나 불릿 등 작은 이미지에 주로 사용합니다. 투명한 배경이나 움직이는 이미지를 만들 수 있다는 장점이 있습니다.|
|JPG/JPEG(Joint Photographic Experts Group)|사진을 위해 개발된 형식으로 GIF보다 다양한 색상과 명암을 표현할 수 있습니다. 저장을 반복하다 보면 화질이 떨어질 수도 있습니다.|
|PNG(Portable Network Graphic)|투명 배경을 만들면서 다양한 색상도 표현할 수 있으며 네트워크용으로 개발되었기 때문에 최근 많이 사용합니다.|


## \<img\> 태그 - 이미지 삽입하기

```html
<img src="경로" [속성="값"]>
```
> 기본형에서 [, ]로 묶은 부분의 기타 속성들은 생략할 수 있습니다.  

```html
<img src="images/cover.jpg" alt="빠른연산">
```

### src 속성 - 이미지 파일 경로 지정하기 

- <code>경로</code> : 현재 HTML 문서에서 이미지 파일까지 찾아가기 위한 길로 이 길이 정확하지 않다면 웹 문서에 이미지가 표시되지 않습니다.

### 내 컴퓨터의 이미지 파일 경로 지정하기
- 이미지 파일의 경로는 웹 문서의 파일 위치를 기준으로 정해집니다.
- 웹 문서 파일과 이미지 파일이 같은 경로에 있다면 src 속성에는 간단히 이미지 파일의 이름만 적으면 됩니다.
- 예를 들어 index.html과 lotus.jpg 파일이 같은 폴더에 있다면 src 속성에 파일 이름만 적으면 됩니다. 

```html
<img src="lotus.jpg">
```

- 웹 문서가 있는 폴더에 하위 폴더를 만들고 그 폴더에 이미지 파일을 저장했다면 src 속성에 하위 폴더와 함께 이미지 파일 이름을 적어야 합니다.
- 예를 들어 images라는 하위 폴더가 있고 거기에 있는 lotus.jpg 파일을 웹 문서에 표시하려면 다음과 같이 작성합니다.

```html
<img src="images/lotus.jpg">
```

> 반대로 한 단계 위로 이동하기 위해서는 '..' 기호를 사용합니다. 이 기호는 같은 레벨에 있는 폴더끼리 파일을 사용할 때 사용합니다. 

```css 
body {
    background-image: url("../images/background.png");
}
```

### 웹 상의 링크를 복사해 이미지 경로 지정하기

- 웹 이미지 파일의 경로를 src 속성의 값으로 지정합니다.
- 웹 이미지는 인터넷에 접속할 수 있어야 화면에 표시됩니다.

```html
<img src="https://www.imdak.com/web/upload/wp/167417/logo.toppc.png">
```

## alt 속성 - 이미지를 설명해 주는 대체 텍스트 

- 이미지를 설명하는 대체 텍스트를 삽입할 때 사용합니다.
- 웹 문서에 삽입한 이미지는 시각적인 요소이기 때문에 시각 장애인들은 그 내용을 알 수 없습니다. 웹 문서를 읽어 주는 화면 낭독기도 문서 상의 텍스트만 읽어 주기 떄문에 이미지를 만나면 그대로 건너뜁니다.
- \<img\> 태그의 alt 속성을 이용하면 이미지에 대한 설명을 넣을 수 있고 alt 속성의 텍스트를 화면 낭독기가 시각장애인에게 읽어 줄 수 있습니다.
- 대체 텍스트를 사용하면 연결 속도가 느리거나 이미지를 제대로 표시할 수 없는 상황에서 이미지 자리에 alt 속성에 쓴 내용이 표시되어 어떤 이미지가 사용되었는지 짐작할 수 있습니다.

```html
<img src="home.jpg" alt="홈으로 가기">
```

## width, height 속성 - 이미지 크기 조정하기

- 이미지 파일을 넣을 때 브라우저 창에 원하는 크기로 조정해 넣고 싶다면 width 속성과 height 속성을 사용하면 된다.
- width 속성과 height 속성을 사용하지 않으면 원본 이미지 크기 그대로 브라우저 화면에 표시됩니다.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>이미지 삽입하기</title>
</head>
<body>
  <h1>이미지 크기 조절</h1>
  <img src="images/gugudan.jpg" alt="바빠구구단">
  <img src="images/gugudan.jpg" width="250" height="250" alt="바빠구구단">
</body>
</html>
```

## \<figure\>, \<figcaption\> 태그 - 이미지에 설명 글 붙이기 

### \<figure\> 태그 - 설명 글을 붙일 대상 지정
- \<figure\> 태그 안에 \<figcaption\> 태그를 사용해 설명 글을 표시합니다. 
- 이미지만 삽입한다면 \<figure\> 태그를 사용하지 않아도 되지만 이미지에 설명 글을 넣으려면 이미지를 \<figure\> 태그로 묶어 주어야 합니다.

### \<figcaption\> 태그 - 설명 글 붙이기

```html
<figcaption> 설명 글 </figcaption>
```

```html
<figure>
    <img src="image/prod.jpg" alt="예멘 모카 마타리">
    <figcaption>예멘 모카 마타리(Yemen Mocha Mattari)</figcaption>
</figure>
```

---

# 링크 만들기


---

# SVG 이미지 