# TIL
Today I Learned

**질문**

GitHub 저장소는 온라인? 그럼 내 컴퓨터의 공간에 저장된 저장소는 로컬인가요?

<details>
	<summary>0일차 학습</summary>

- GitHub 계정 생성
- GitHub 저장소 생성
- GitKraken 설치
- GitKraken을 사용하여 GitHub 저장소 데이터를 내 컴퓨터로 복제(Clone)

</details>



## 구조 디자인(HTML)
<details>
	<summary>1일차 학습</summary>

#### [HTML 이란?]

- HTML은 HyperText Markup Language로 구조를 설정할 때 사용하는 언어임
- 하이퍼링크 시스템을 가지고 있음
- 확장자 : .html

#### [시멘틱 마크업]
- 시멘틱 마크업(Semantic Markup)은 비주얼 디자인(모양, 색, 크기 등)이 목표가 아니라, 구조 설계(Structure Design)를 목표로 합니다
```html
<h1></h1> <!--제목 heading-->
<p></p> <!--단락 paragraph-->
```

#### [기본 문법]

- element : tag name / attribute name, value
- <여는 태그> 컨텐츠 </닫는 태그>
- <태그이름 속성="값"> 컨텐츠 </태그이름>
- (참고) 페이지 검사 -> console -> document.characterSet -> 문자 인코딩 반환 (UTF-8)
```html
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

#### [텅 빈 요소]

- meta는 컨텐츠를 감싸지 않아 닫는 태그를 가지지 않음.
- 이를 Empty Element라고 함.

#### [표준 호환모드]

- html(root)는 자식을 둘 가지며 그 자식은 head와 body임. 
- head와 body는 각각 다른 성질의 자식들을 가질 수 있음. 

- DTD : 문서 유형 정의(Document Type Definition)
```html
<!DOCTYPE html> <!--웹표준문서-->
```

#### [주 언어 설정]

```html
<html lang="ko-KR"> <!--ko/en/es/ja 등..-->
```
- KR : Republic of Korea 지역(locale) 정보. ko 만 사용하면 한국어를 통칭
- (참고) en-GB ⇒ 영국 영어 / en-US ⇒ 미국 영어 / en-CA ⇒ 캐나다 영어

#### [제목과 단락]

- 제목 레벨(Level): 1 ~ 6단계에서 1단계는 문서에서 하나만 작성가능, 2단계부터는 여러개의 제목을 사용할 수 있음

```html
<h1>제목 1</h1> <!-- 문서에서 단 1회만 사용 (HTML5 표준 부터는 섹션 콘텐츠 마다 사용 가능) -->
<h1>제목 2</h1>
<h1>제목 3</h1>
<h1>제목 4</h1>
<h1>제목 5</h1>
<h1>제목 6</h1>

<!--주석-->

<p>단락</p>
```

#### [이미지와 피규어]

- img : image 태그
- figure : 이미지, 차트, 도표 등을 감싸는 태그
- alt(alternative) : 대체텍스트, 이미지를 분석하여 묘사할것.

```html
<figure>
  <img src="" alt="대체 텍스트">
  <figcaption>이미지 출처 등 캡션</figcaption>
</figure>
```

#### [문법 검사]
- validator.w3.org : 문법 유효성 검사
- entitycode.com : entitycode

```html
&lt; &gt; &copy; &midot; &nbsp; &amp;
```

#### [순차/비순차 목록]

- ul : unordered lists 비순차 목록
- ol : ordered lists 순차 목록
- li : list Item

</details>

<details>
	<summary>2일차 학습</summary>

#### [앵커와 하이퍼링크]

- anchor : 현재 페이지에서 위치 이동
- hyperlink : 다른 창으로 이동
- target= "＿blank" : 새창(새탭)열림
- href="mailto:" : 이메일 링크

```html
<!--anchor-->
<a href="#intro">소개</a>
<h3 id="intro">소개</h3><!-- 위 링크를 누르면 여기로 이동 -->
<!--hyperlink-->
<a href="http://naver.com" target="_blank">
  <img src="img경로" alt="NAVER logo" />네이버
</a>
```

#### [설명 목록]

- dl : 설명목록(Description lists)
- dt : 용어(Definition Term)
- dd : 설명(Definition Description)

```html
<dl>
  <!--1-->
  <dt>용어</dt>
  <dd>설명</dd>
  <!--2-->
  <dt>용어</dt>
  <dt>용어</dt>
  <dt>용어</dt>
  <dd>설명</dd>
  <!--3-->
  <dt>용어</dt>
  <dd>설명</dd>
  <dd>설명</dd>
  <dd>설명</dd>
</dl>
```

#### [인용과 줄 바꿈]
- q (quote) : 짧은 인라인 인용문. ("") 사용가능 / 강조용으로 쓰인 경우 <q> 사용 불가. / 중첩가능
- blockquote : 긴 인용문
- cite(citation) : 출처 정보

```html
<p>어렸을 때 어른들이 <q>너 많이 컸구나</q> 하면 그게 굉장한 칭찬으로 느껴졌었습니다. 다만 시간이 지난 것뿐인데… 지금은 <q>너 아직도 노안이 안 왔구나</q> <q>너 아직 머리숱이 많구나 (혹은 너 아직도 흰머리가 덜 났구나)</q> 등의 이야기가 퍽 반갑습니다. 어렸을 때는 시간이 흐른 것 때문에 칭찬받고, 나이 들어서는 시간을 비껴간 것 때문에 칭찬 비슷한 것을 듣습니다.</p>
```
```html
<figure>
    <img src="images/sbs-drama__do-you-want-to-kiss-first.png" alt="">
    <figcaption>-이미지 출처: SBS &lt;키스 먼저 할까요?&gt; 방송화면 캡쳐-</figcaption>
  </figure>
```
```html
  <blockquote>
    <p>“…우리 같은 여자들은.”</p>
    <p>“우리?”</p>
    <p>“시절이 끝난 여자들이요. 꽃이 아닌 풀떼기가 된…(중략)”</p>
    <p>“당신 아직 안 늙었어.”</p>
    <p>“맞아요. 안 늙었어요, 나는 아직.<br>그렇게 안 봐주는 세상 때문에 매 순간 늙고 있어서 그렇지.”</p>
    <cite>_SBS 드라마 &lt;키스 먼저 할까요?&gt; 중에서</cite>
  </blockquote>
```

#### [어휘 요소들]
의미 요소(Semantic Elements)
- 강조의 의미를 부여하는 용도

&lt;strong&gt; : 내용의 중요성(importance), 심각성(seriousness), 긴급성(urgency)을 강조할 경우 사용

- [중요성] : 제목/캡션의 글자 중 일부를 더욱 강조하는데 사용

```html
<h1>챕터 1: <strong>연습</strong></h1>
	
<figcaption>피규어 1. <strong>개미 식민지 역학</strong>. 이 식민지 지역의 개미는 열원(왼쪽 위)과 식량 공급원(오른쪽 아래)의 영향을 받습니다.</figcaption>
		
<h1><strong>꽃, 꿀벌, 꿀</strong> 그리고 내가 이해하지 못하는 다른 요소</h1>
```

- [심각성] : 경고 또는 주의를 주고자 할 때 사용

```html	
<p>
	<strong>경고.</strong> 이 지하 감옥은 위험합니다.
	<strong>오리 때를 피하세요.</strong> 찾은 금은 가지고 떠나세요.
	<strong>
		<strong>다이아몬드는 사용하지 마세요.</strong>,
		그것을 사용하면 폭발할 것이며
		<strong>10미터 내에 있는 모든 것을 파괴할 것입니다.</strong>
	</strong>
	당신에게 경고 했습니다.
</p>
```

- [긴급성] : 문서의 다른 부분보다 빨리 보아야 하는 내용을 나타내는데 사용

```html
<p>리마인더 시스템 Remy에 오신 것을 환영합니다.</p>
<p>오늘 할 일1</p>
<ul>
	<li><p><strong>오븐을 끕니다.</p></strong></li>
	<li><p>휴지통에 불필요한 것을 버립니다.</p></li>
	<li><p>세탁을 합니다.</p></li>
</ul>
```

&lt;em&gt; : 특정 내용의 스트레스(Stress) 강조(Emphasis) - 문장 의미를 변경

강조가 없는 예

```html
<p>고양이는 귀여운 동물입니다.</p>
```

고양이(종)을 강조한 예

```html
<p><em>고양이</em>는 귀여운 동물입니다.</p>
```

귀여운(형용사)을 강조한 예

```html
<p>고양이는 <em>귀여운</em> 동물입니다.</p>
```

문장 전체를 강조한 예 (느낌표 사용)

```html
<p><em>고양이는 귀여운 동물입니다!</em></p>
```

&lt;b&gt; : 단순히 다른 글자와 구분된 용도로 사용. 문서 요약의 주요 단어, 리뷰 제품 이름 등

아래 조선에 부합하지 않을 경우 최종적으로 b 요소 사용을 고려

제목은 h1 ~ h6 요소를 사용하고,
강조는 em 요소를 사용해야 하며,
중요도는 strong 요소로 표시 되어야 하고,
표시 또는 강조 표시된 텍스트는 mark 요소를 사용.

b 요소 사용 예시
	
```html
<p>
	작은 방에 들어가니 <b>낡은 액자</b>와 <b>거미줄이 엮인 손전등</b>이 탁자에 놓여있었다.
</p>
```

&lt;i&gt; : 다른 글자와 구분된 용도로 사용. 기술적 용어, 다른 언어(목소리), 인물의 생각 등을 표현

i 요소 사용 예시
	
```html
<p><i class="taxonomy">펠리스 실베스트리 카터스(Felis silvestris catus)</i>는 귀여워요.</p>
<p><i>산문 내용</i> 용어는 위에 기술되어 있습니다.</p>
<p>
	Galileo Galilei는 재판을 받고 나오면서
	<i lang="la">"E pur si muove."</i>
	라고 말했습니다.
</p>
```

꿈의 연속된 장면을 i 요소로 사용한 예시

```html
<p>Raymond는 잠을 자려고 했습니다.</p>
<p>
	<i>그 배는 목요일에 멀리 출항합니다.</i>, 그는 꿈을 꾸었습니다.
	<i>그 배는 아름다운 공주 Carey를 포함하여 많은 사람들이 타고 있었습니다.
	그는 그녀가 자신을 알아주기를 매일 밤낮으로 원했지만 그런 일은 일어나지 않았습니다.</i>
</p>
<p><i>마지막 날 밤 그는 용기를 내어 그녀에게 말을 걸었습니다.</i></p>
<p>Raymond는 화재 경보기 알람 소리에 눈이 띄였습니다.</p>
```
	
#### [섹션/메인 요소]

루트 섹션(Root Section) 요소

&lt;body&gt;
- 문서에서 단 1번만 사용 가능.


섹션(Sections) 요소들
- 섹션 요소는 일반적인 컨테이너 요소가 아니며, 문서 개요에
  명시적으로 나열되는 경우에만 섹션 요소가 적합하다는 규칙이 있다.
  일반적인 컨테이너 요소로는 &lt;div&gt;, &lt;span&gt; 등이 있다.

&lt;article&gt;
- 문서, 페이지, 애플리케이션, 사이트 등에 포함된 독립적인 섹션을 말한다.
  잡지, 신문, 논문, 에세이, 보고서, 블로그, 기타 소설 미디어 일 수 있음.
  일반적인 규칙은 article 요소의 내용이 문서 개요에 명시적으로 나열되는
  경우에만 적합하다. 각 article 요소는 일반적으로 요소의 하위 항목으로
  제목(h1~h6 요소)을 포함시켜 식별해야 한다.

[예시]

```html
<aticle>
<h2>기사 제목</h2>
...
</aticle>
```

&lt;section&gt;
- section 요소는 문서, 애플리케이션의 일반적인 섹션을 말한다.
  이 컨텍스트의 섹션은 주제별로 그룹화 된 콘텐츠이다.
  웹 사이트의 섹션은 소개(introduction), 뉴스 항목(news item),
  연락처 정보(contact information)를 위한 섹션으로 나눌 수 있다.

[참고]
콘텐츠가 사이트에 포함된 독립적인 섹션의 성향이 크다면
section 요소 대신 article 요소를 사용하는 것이 좋다.

&lt;aside&gt;
- 웹 사이트의 사이드바에 해당되는 부 콘텐츠(메인 콘텐츠와 분리된) 섹션을 말한다.

&lt;nav&gt;
- 다른 페이지로 이동하는 링크 또는 사이트 내 탐색 링크를 포함하는 섹션 요소이다.

[참고]
내용을 쉽게 이해할 수 있도록 nav 요소 내부에는 비순차 목록(ul)을 사용한다.
사이트의 모든 링크를 nav에 포함하는 것은 아니며, 주로 사이트를 탐색하는 링크를 포함한다.
사이트 하단에 위치한 링크는 footer 요소로도 충분하다.


섹션 내부에 사용되는 요소들
&lt;heaader&gt;
- header 요소는 일반적으로 섹션의 제목, 목차, 검색, 로고 등을 포함하는데 사용한다.

&lt;footer&gt;
- footer 요소는 일반적으로 섹션의 저자, 링크, 저작권 정보 등을 포함하는데 사용한다.

섹션과 헤딩
- 헤딩(h1 ~ h6) 요소는 섹션의 제목에 해당된다.
  
메인(Main) 요소
&lt;main&gt;
- 문서 또는 애플리케이션 body 요소의 메인 콘텐츠에 해당한다.
  main 요소는 섹션 요소가 아니며, 보이는 요소가 2개 이상이면 안된다.
  사용되지 않는 main 요소는 화면에서 감춤(hidden) 처리해야 한다.
  article, section, aside, nav 요소는 main 요소를 자식으로 포함할 수 없다.
  반대로 main 요소는 섹션 요소들을 포함할 수 있다.
  main 내부에는 header, footer 요소를 직접적으로 포함하지 않는다.

[예시]

```html
<main>...</main>
<main hidden>...</main>
<main hidden>...</main>
```
	
</details>
