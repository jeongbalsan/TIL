# TIL
Today I Learned

**질문**

GitHub 저장소는 온라인? 그럼 내 컴퓨터의 공간에 저장된 저장소는 로컬인가요?

<details>
	<summary>0 일차 학습</summary>


- GitHub 계정 생성
- GitHub 저장소 생성
- GitKraken 설치
- GitKraken을 사용하여 GitHub 저장소 데이터를 내 컴퓨터로 복제(Clone)

</details>



# 구조 디자인(HTML)

## 1일차 학습

### [HTML 이란?]

- HTML은 HyperText Markup Language로 구조를 설정할 때 사용하는 언어임
- 하이퍼링크 시스템을 가지고 있음
- 확장자 : .html

### [시멘틱 마크업]
- 시멘틱 마크업(Semantic Markup)은 비주얼 디자인(모양, 색, 크기 등)이 목표가 아니라, 구조 설계(Structure Design)를 목표로 합니다
```
<h1></h1> <!--제목 heading-->
<p></p> <!--단락 paragraph-->
```

### [기본 문법]

- element : tag name / attribute name, value
- <여는 태그> 컨텐츠 </닫는 태그>
- <태그이름 속성="값"> 컨텐츠 </태그이름>
- (참고) 페이지 검사 -> console -> document.characterSet -> 문자 인코딩 반환 (UTF-8)
```
<html>
	<head>
	<meta charset="utf-8">
		<title>HTML 문서 작성을 위한 기본 문법</title>
	</head>
	<body>
		<p title="Development"> 개발 도구(DevTools)</p>
	</body>
</html>
```

### [텅 빈 요소]

- meta는 컨텐츠를 감싸지 않아 닫는 태그를 가지지 않음.
- 이를 Empty Element라고 함.

### [표준 호환모드]

- html(root)는 자식을 둘 가지며 그 자식은 head와 body임. 
- head와 body는 각각 다른 성질의 자식들을 가질 수 있음. 

- DTD : 문서 유형 정의(Document Type Definition)
```
<!DOCTYPE html> <!--웹표준문서-->
```

### [주 언어 설정]

```
<html lang="ko-KR"> <!--ko/en/es/ja 등..-->
```
- KR : Republic of Korea 지역(locale) 정보. ko 만 사용하면 한국어를 통칭
- (참고) en-GB ⇒ 영국 영어 / en-US ⇒ 미국 영어 / en-CA ⇒ 캐나다 영어

### [제목과 단락]

- 제목 레벨(Level): 1 ~ 6단계에서 1단계는 문서에서 하나만 작성가능, 2단계부터는 여러개의 제목을 사용할 수 있음

```
<h1>제목 1</h1> <!-- 문서에서 단 1회만 사용 (HTML5 표준 부터는 섹션 콘텐츠 마다 사용 가능) -->
<h1>제목 2</h1>
<h1>제목 3</h1>
<h1>제목 4</h1>
<h1>제목 5</h1>
<h1>제목 6</h1>

<!--주석-->

<p>단락</p>
```

### [이미지와 피규어]

- img : image 태그
- figure : 이미지, 차트, 도표 등을 감싸는 태그
- alt(alternative) : 대체텍스트, 이미지를 분석하여 묘사할것.

```
<figure>
  <img src="" alt="대체 텍스트">
  <figcaption>이미지 출처 등 캡션</figcaption>
</figure>
```

### [문법 검사]
- validator.w3.org : 문법 유효성 검사
- entitycode.com : entitycode

```
&lt; &gt; &copy; &midot; &nbsp; &amp;
```

### [순차/비순차 목록]
- ul : unordered lists 비순차 목록
- ol : ordered lists 순차 목록
- li : list Item