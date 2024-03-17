# 웹과 멀티미디어

## 멀티미디어의 웹 표준화

- HTML5는 PC뿐만 아니라 웹 브라우저가 설치된 모든 기기에 적용되는 웹 표준이므로 플러그인 프로그램 없이 웹 브라우저 자체에서 멀티미디어를 재생할 수 있습니다.
- 웹에서 지원되는 비디오/오디오 파일에는 여러 종류가 있습니다.

|종류|확장자|설명|
|---|----|----|
|비디오|mp4|고화질 영상을 지원해 많은 사이트에서 사용되고 있습니다. 라이선스가 있지만 웹에서 사용할 경우에는 무료로 사용할 수 있습니다.|
|비디오|webm|화질이 우수하고 무료로 제공되어 최근 많이 사용되고 있습니다.|
|비디오|ogv|화질은 다른 비디오 유형보다 떨어지지만 무료라는 장점 때문에 webm 형식이 등작하기 전에 많이 사용되었습니다.|
|오디오|mp3|대부분의 음원에서 사용되지만 라이선스 때문에 유료로 사용해야 합니다.|
|오디오|ogg|무료이므로 게임 등에서 많이 사용합니다.|

> 최신 모든 웹 브라우저에서는 비디오 파일의 경우 mp4나 webm, 오디오 파일의 경우 mp3나 ogg 파일을 주로 사용합니다.


--- 

# 오디오 & 비디오 재생하기

## \<audio\> 태그 - 오디오 파일 삽입하기 

```html
<audio src="오디오 파일 경로" [속성] [속성="속성 값"]></audio>
```

|속성|설명|
|---|-----|
|autoplay|오디오를 자동 재생합니다.|
|controls|웹 화면에 컨트롤 막대를 표시합니다. 컨트롤 막대에는 재생/멈춤, 진행 바, 볼륨 등이 표시됩니다.|
|loop|오디오를 반복 재생합니다.|
|muted|오디오를 재생해 진행하지만 소리는 끕니다.|
|preload|재생 버튼을 눌러 재생하기 전에 오디오 파일을 다운로드해 준비해 둡니다.|


- 플레이어와 함께 오디오 삽입하기

```html
<audio src="media/bgsound.mp3" controls></audio>
```

- 플레이어 표시 없이 배경 음악 삽입하기

```html
<audio src="media/bgsound.mp3" autoplay loop></audio>
```

## \<video\> 태그 - 비디오 파일 삽입하기

```html
<video src="비디오 파일 경로" [속성] [속성="속성 값"]></video>
```

- 컨트롤 막대가 있는 비디오 삽입하기

```html
<video src="media/Painting.mp4" controls></video>
```

- 컨트롤 막대가 없는 비디오 삽입하기

```html
<video src="media/Painting.mp4"></video>
```

## \<source\> 태그 - 여러 미디어 파일 한꺼번에 지정하기 
- 브라우저에 따라 지원하는 오디오 코덱이나 비디오 코덱이 다르기 때문에 한 가지 파일만 사용했을 경우, 일부 오래된 브라우저에서는 지원하지 않을 수 있습니다. 
- 예를 들어 mp4 파일은 최신 브라우저에서는 모두 지원하지만 이전 버전에서는 재생되지 않을 수도 있습니다.
- 사용자들의 브라우저 환경을 모두 고려한다면 최신 브라우저와 이전 브라우저에서 모두 재생할 수 있도록 ogv 파일도 함께 지정해 주어야 합니다.
- 이렇게 여러 형식의 비디오 파일을 함게 사용하려면 \<video\> 태그와 \<source\> 태그를 함게 사용해 여러 개의 파일을 지정해야 합니다.

```html
<source src="video.ogv" type="video/ogg; codecs='theora,vorbis'">
```

|속성|설명|
|---|----|
|src|미디어 파일의 경로를 지정하는 필수 속성으로 파일 경로를 지정할 때는 경로에 공백이 있으면 안됩니다.|
|type|웹 브라우저가 해당 미디어 파일을 재생할 수 있는지 여부를 확인할 수 있도록 미디어 파일의 유형을 알려 줍니다.|
|codecs|비디오 코덱을 지정합니다.|

```html
<video controls>
    <source src="Painting.mp4" type="video/mp4">
    <source src="Painting.webm" type="video/webm">
    <source src="Painting.ogv" type="video/ogg">
</video>
```

## 이전 브라우저에서는 어떻게 해야 할까?

- \<video\> 태그를 지원하지 않는 이전 브라우저를 고려해 다음과 같이 HTML5 지원 브라우저가 필요하다는 대체 텍스트를 표시할 수 있습니다.

```html
<video controls>
    <source src="Painting.mp4" type="video/mp4">
    <source src="Painting.webm" type="video/webm">
    <source src="Painting.ogv" type="video/ogg">
    이 영상을 보기 위해서는 HTML5를 지원하는 브라우저가 필요합니다.
</video>
```

## \<audio\> 태그와 \<video\> 태그의 속성
- width, height 속성 - 비디오 크기 조절 
- controls 속성 - 컨트롤 막대 표시
- preload 속성 - 파일 다운로드 여부

|속성 값| 설명                                                                                                                                           |
|---|----------------------------------------------------------------------------------------------------------------------------------------------|
|none| 미디어 파일을 미리 다운로드하지 않고 사용자가 재생 버튼을 눌러야만 다운로드하기 시작합니다.<br> \<video src="media/Painting.mp4" controls preload="none"\>\</video\>                 |
|metadata| 미디어 파일을 즉시 사용하지 않을 것이라고 생각해 미디어 파일 전체를 다운로드하지 않고 메타 정보만 다운로드 합니다.<br>\<video src="media/Painting.mp4" controls preload="metadata"\>\</video\>|
|auto|사용자가 즉시 이용할 수 있도록 웹 문서를 로드할 때 미디어 파일도 모두 다운로드합니다. 다만, 다운로드가 끝나도 사용자가 재생 버튼을 눌러야만 재생됩니다. 속성 값을 지정하기 않고 preload라고만 설정하면 auto 값을 기본으로 합니다. 따라서 아래 두 소스는 같은 의미 입니다.<br>\<video src="media/Painting.mp4" controls preload="auto"\>\</video\><br>\<video src="media/Painting.mp4" controls preload>\</video\>|

- muted 속성 - 소리는 끄고 화면만 재생
- autoplay 속성 - 자동 재생
- loop 속성 - 반복 재생 
- poster 속성 - 문제상황 표시 
  - 브라우저 문제나 인터넷 연결 문제 등 비디오를 재생할 수 없을 경우, 비디오 화면 자리에 대힌 표시하는 이미지를 <code>포스터 이미지</code>라고 부릅니다. 

```html
<video src="media/Paiting.mp4" controls poster="fireworks.jpg"></video>
```